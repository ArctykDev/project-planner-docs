---
title: Data Structure Reference
date:
  created: 2026-01-26
  updated: 2026-01-26
readtime: 2
---

# Data Structure Reference

This page provides a comprehensive reference for how Project Planner stores and organizes data within your Obsidian vault.

## Storage Locations

### Primary Data File

**Location**: `.obsidian/plugins/obsidian-project-planner/data.json`

This JSON file contains all project and task data for the plugin. It's the single source of truth for the plugin's internal state.

**Structure**:
```json
{
  "projects": [],
  "tasksByProject": {},
  "tags": [],
  "settings": {}
}
```

### Markdown Task Files

**Location**: `{ProjectName}/Tasks/{TaskTitle}.md`

When [Markdown Sync](markdown-sync.md) is enabled, tasks are also stored as individual markdown files with YAML frontmatter.

### View Preferences

**Location**: Browser `localStorage`

View-specific preferences (e.g., panel split widths, zoom levels) are stored in your browser's localStorage and persist between sessions.

---

## Data Schema

### Project Object

```json
{
  "id": "unique-project-id",
  "name": "Project Name",
  "buckets": [
    {
      "id": "bucket-id",
      "name": "Bucket Name",
      "order": 0
    }
  ],
  "createdDate": "2026-01-26",
  "lastUpdatedDate": "2026-01-26",
  "lastSyncTimestamp": 1706284800000
}
```

**Fields**:

- `id` (string, required): Unique identifier for the project
- `name` (string, required): Display name of the project
- `buckets` (array, optional): Board view column definitions
  - `id` (string): Unique bucket identifier
  - `name` (string): Bucket display name
  - `order` (number): Sort order in Board view
- `createdDate` (string, optional): ISO date when project was created
- `lastUpdatedDate` (string, optional): ISO date of most recent task change
- `lastSyncTimestamp` (number, optional): Unix timestamp for sync throttling

### Task Object

```json
{
  "id": "unique-task-id",
  "title": "Task Title",
  "status": "In Progress",
  "completed": false,
  "priority": "High",
  "parentId": "parent-task-id",
  "bucketId": "bucket-id",
  "startDate": "2026-01-20",
  "dueDate": "2026-01-30",
  "createdDate": "2026-01-15",
  "lastModifiedDate": "2026-01-26",
  "tags": ["tag-id-1", "tag-id-2"],
  "description": "Task description in markdown",
  "subtasks": [
    {
      "text": "Subtask item",
      "completed": false
    }
  ],
  "links": [
    {
      "text": "Link Text",
      "url": "https://example.com"
    }
  ],
  "dependencies": ["FS:predecessor-task-id"],
  "collapsed": false
}
```

**Required Fields**:

- `id` (string): Unique identifier (UUID format)
- `title` (string): Task name/title
- `status` (string): Current status (e.g., "Not Started", "In Progress", "Completed")
- `completed` (boolean): Completion flag

**Optional Fields**:

- `parentId` (string): ID of parent task for hierarchical organization
- `priority` (string): Priority level ("Low", "Medium", "High", "Critical")
- `bucketId` (string): Board view bucket assignment
- `startDate` (string): Start date in YYYY-MM-DD format
- `dueDate` (string): Due date in YYYY-MM-DD format
- `createdDate` (string): Creation date in YYYY-MM-DD format
- `lastModifiedDate` (string): Last modification date in YYYY-MM-DD format
- `tags` (array): Array of tag IDs
- `description` (string): Markdown-formatted description
- `subtasks` (array): Checklist items
  - `text` (string): Subtask text
  - `completed` (boolean): Completion state
- `links` (array): External and wiki links
  - `text` (string): Link display text
  - `url` (string): Link URL
- `dependencies` (array): Task dependency relationships
  - Format: `{TYPE}:{TASK_ID}`
  - Types: `FS` (Finish-to-Start), `SS` (Start-to-Start), `FF` (Finish-to-Finish), `SF` (Start-to-Finish)
- `collapsed` (boolean): Whether child tasks are collapsed in Grid view

### Tag Object

```json
{
  "id": "tag-id",
  "name": "Tag Name",
  "color": "#FF5733"
}
```

**Fields**:

- `id` (string, required): Unique tag identifier
- `name` (string, required): Tag display name
- `color` (string, optional): Hex color code for visual identification

---

## Data Organization

### tasksByProject Structure

Tasks are organized by project in the main data file:

```json
{
  "tasksByProject": {
    "project-id-1": [
      { "id": "task-1", "title": "Task 1", ... },
      { "id": "task-2", "title": "Task 2", ... }
    ],
    "project-id-2": [
      { "id": "task-3", "title": "Task 3", ... }
    ]
  }
}
```

Each project ID maps to an array of task objects. This structure enables:

- Fast project-specific task lookups
- Efficient filtering by project
- Isolated task management per project
- Easy project export/import

### Hierarchical Relationships

Task hierarchy is established through the `parentId` field:

```json
[
  {
    "id": "parent-task",
    "title": "Parent Task",
    "parentId": null
  },
  {
    "id": "child-task-1",
    "title": "Child Task 1",
    "parentId": "parent-task"
  },
  {
    "id": "child-task-2",
    "title": "Child Task 2",
    "parentId": "parent-task"
  }
]
```

- Root tasks have `parentId: null` or no `parentId` field
- Child tasks reference their parent's `id`
- Multiple levels of nesting are supported
- Orphaned tasks (parent doesn't exist) are treated as root tasks

---

## Markdown File Format

When Markdown Sync is enabled, tasks are stored as markdown files:

````markdown
---
id: abc123-def456-ghi789
title: Implement login feature
status: In Progress
completed: false
priority: High
bucketId: bucket-1
startDate: 2026-01-10
dueDate: 2026-01-20
createdDate: 2026-01-05
lastModifiedDate: 2026-01-26
tags:
  - frontend
  - authentication
dependencies:
  - FS:task-id-predecessor
---

This is the task description. It can contain any markdown content.

## Subtasks

- [x] Design login UI
- [ ] Implement authentication logic
- [ ] Add password reset

## Links

- [[Related Design Document]]
- [External API Docs](https://example.com)

---

_Task from Project: My Project_
````

**Format Notes**:

- YAML frontmatter contains all task metadata
- Description appears in markdown body before any headings
- Subtasks use checkbox list syntax (`- [ ]` or `- [x]`)
- Links can be wiki-style (`[[Page]]`) or external (`[text](url)`)
- Footer automatically added with project reference

---

## Date Format

### Current Format (v0.6.5+)

Dates are stored in simple **YYYY-MM-DD** format:

```json
{
  "startDate": "2026-01-20",
  "dueDate": "2026-01-30",
  "createdDate": "2026-01-15"
}
```

### Legacy Format (v0.6.4 and earlier)

Older versions used ISO 8601 format:

```json
{
  "startDate": "2026-01-20T00:00:00.000Z",
  "dueDate": "2026-01-30T00:00:00.000Z"
}
```

**Backward Compatibility**: The plugin automatically handles both formats for seamless migration.

---

## Settings Schema

```json
{
  "enableMarkdownSync": true,
  "autoCreateTaskNotes": true,
  "syncOnStartup": false,
  "enableDailyNoteSync": true,
  "dailyNoteTagPattern": "#planner",
  "dailyNoteScanFolders": ["Daily Notes"],
  "dailyNoteDefaultProject": "Inbox",
  "statuses": [
    { "name": "Not Started", "color": "#808080" },
    { "name": "In Progress", "color": "#007bff" },
    { "name": "Completed", "color": "#28a745" }
  ]
}
```

**Fields**:

- `enableMarkdownSync` (boolean): Enable bidirectional sync
- `autoCreateTaskNotes` (boolean): Auto-create markdown files for tasks
- `syncOnStartup` (boolean): Perform initial sync on plugin load
- `enableDailyNoteSync` (boolean): Enable daily note task tagging
- `dailyNoteTagPattern` (string): Tag pattern for daily note scanning
- `dailyNoteScanFolders` (array): Folders to scan for daily notes
- `dailyNoteDefaultProject` (string): Default project for daily note tasks
- `statuses` (array): Custom status definitions

---

## Data Backup

### Best Practices

1. **Regular Backups**: Back up `.obsidian/plugins/obsidian-project-planner/data.json` regularly
2. **Version Control**: Commit `data.json` to git for change tracking
3. **Markdown Sync**: Enable markdown sync for redundant storage
4. **Vault Backup**: Include plugin data in your Obsidian vault backups
5. **Export Before Updates**: Save a copy of `data.json` before major plugin updates

### Recovery Options

**From data.json**:
- Restore from backup copy
- Use git history to recover previous versions
- Manually edit JSON if needed

**From Markdown Files**:
- Re-enable markdown sync
- Use "Sync All Tasks Now" to rebuild from markdown
- Tasks will be recreated from YAML frontmatter

---

## Performance Considerations

### File Size Limits

- **data.json**: Can handle thousands of tasks efficiently
- **Individual Markdown Files**: One file per task is more scalable than monolithic storage
- **Browser localStorage**: Minimal data stored, no performance impact

### Optimization Tips

1. **Archive Completed Projects**: Move old projects to separate data files
2. **Use Filters**: Reduce visible tasks in views to improve rendering speed
3. **Markdown Sync**: Disable if not needed to reduce file system operations
4. **Daily Note Scanning**: Limit scan folders to necessary directories

### Recommended Limits

- **Projects**: 20-30 active projects for best Dashboard UX
- **Tasks per Project**: Hundreds to low thousands perform well
- **Hierarchy Depth**: 3-4 levels recommended for Grid view clarity
- **Tags**: No hard limit, but 20-50 tags is typical

---

## Data Migration

### Upgrading from Older Versions

The plugin automatically handles data migration:

- **Date Format**: Converts ISO dates to YYYY-MM-DD format
- **New Fields**: Adds `createdDate` and `lastModifiedDate` if missing
- **Project Timestamps**: Adds `createdDate` and `lastUpdatedDate` to projects

### Exporting Data

**Current Methods**:
- Copy `data.json` file directly
- Export via markdown sync (creates individual files)
- Use git to track and export changes

**Future Methods** (planned):
- CSV export for spreadsheet import
- JSON export with filtering options
- Integration with external tools

---

## Technical Notes

### UUID Generation

Task IDs use UUID v4 format for guaranteed uniqueness:
```
abc123-def456-ghi789-012345
```

### Sync Conflict Resolution

- **Last Write Wins**: The most recent save operation takes precedence
- **Sync Loop Prevention**: 200ms debounce with `syncInProgress` tracking
- **Metadata Cache**: Uses Obsidian's metadata cache for reliable YAML detection

### Data Integrity

The plugin maintains data integrity through:

- Automatic orphan detection (tasks with missing parents)
- Circular dependency prevention
- Validation on save operations
- Graceful handling of malformed data

---

## Related Documentation

- [Markdown Sync](markdown-sync.md) - Bidirectional sync between JSON and markdown
- [Daily Note Tagging](daily-notes-tagging.md) - Import tasks from daily notes
- [URI Linking](uri-linking.md) - Deep linking to specific tasks
- [FAQ](../getting-started/faq.md) - Frequently asked questions

---

**Need Help?**

- Check the [FAQ](../getting-started/faq.md) for common questions
- Report data issues on [GitHub Issues](https://github.com/ArctykDev/obsidian-project-planner/issues)
- Review [Privacy Policy](../about/privacy-policy.md) for data handling information
