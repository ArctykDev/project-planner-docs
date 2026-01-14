---
title: Daily Note Task Tagging
date:
  created: 2026-01-14
readtime: 6
---

# Daily Note Task Tagging

The Project Planner plugin supports automatically importing tasks from daily notes (or any markdown note) into your projects by using tag patterns.

## Quick Start

1. **Enable the feature**: Settings → Project Planner → Daily Note Task Tagging → Toggle "Enable Daily Note Sync"
2. **Set a default project**: In the same settings, select a "Default Project" from the dropdown
3. **Tag your tasks**: Add `#planner` to any task in any note
4. **Watch them appear**: Tasks automatically import to your planner!

## How It Works

When **Enable Daily Note Sync** is enabled in settings, the plugin automatically scans your vault for tasks tagged with a special pattern (default: `#planner`) and imports them into your project planner.

The scanner:

- Watches for file changes in real-time
- Detects tasks using the format: `- [ ] Task text #planner`
- Extracts metadata like priority, due dates, and additional tags
- Automatically routes tasks to the correct project
- Prevents duplicates using content-based IDs

## Basic Usage

### Simple Task Import

Add tasks in any note with the planner tag:

```markdown
## Today's Tasks

- [ ] Review pull request #planner
- [ ] Write documentation #planner
- [x] Morning standup #planner
```

These tasks will be automatically imported into your **Default Project** (configured in settings).

### Project-Specific Tasks

Target a specific project by adding the project name to the tag:

```markdown
## Work Tasks

- [ ] Fix login bug #planner/Work
- [ ] Update API docs #planner/Work

## Personal Tasks

- [ ] Buy groceries #planner/Personal
- [ ] Call dentist #planner/Personal
```

Tasks will be automatically routed to the matching project. Project names are case-insensitive.

**For projects with spaces in the name**, you can use either format:

- `#planner/Project Planner` - Direct format with spaces
- `#planner/Project-Planner` - Hyphens (converted to spaces)

Both will match a project named "Project Planner".

## Advanced Features

### Priority Indicators

Add priority to tasks using these patterns:

```markdown
- [ ] Critical bug fix !!! #planner → Critical priority
- [ ] Important feature !! #planner → High priority
- [ ] Regular task ! #planner → Medium priority
- [ ] Review code (high) #planner → High priority
- [ ] Update docs (low) #planner → Low priority
```

### Due Dates

Specify due dates using these formats:

```markdown
- [ ] Submit report 📅 2026-01-20 #planner
- [ ] Code review due: 2026-01-15 #planner
- [ ] Finish slides @2026-01-18 #planner
```

### Additional Tags

Combine planner tags with other tags for organization:

```markdown
- [ ] Update frontend #planner #frontend #urgent
- [ ] Fix database issue #planner #backend #bug
```

The plugin will automatically match tags with those defined in your settings and apply them to the task.

### Task Status

Tasks are imported with their completion status:

```markdown
- [ ] Not started task #planner → Status: Not Started
- [x] Completed task #planner → Status: Completed
```

## Configuration

### Settings

Navigate to **Settings → Project Planner → Daily Note Task Tagging** to configure:

#### Enable Daily Note Sync

Toggle this on to activate automatic task scanning and import.

#### Tag Pattern

Default: `#planner`

Change this to customize your tag pattern. Examples:

- `#task` - Use `#task` instead of `#planner`
- `#project` - Use `#project`

Project-specific tagging will always use the pattern: `{tag-pattern}/{ProjectName}`

#### Scan Folders

Comma-separated list of folders to scan. Examples:

- `Daily Notes` - Only scan the Daily Notes folder
- `Daily Notes, Journal` - Scan both folders
- Leave empty - Scan all notes in your vault

#### Default Project

**Required!** Select which project should receive tasks when no specific project tag is found (e.g., just `#planner` without `/ProjectName`).

If no default project is selected, tasks without a specific project tag will not be imported.

### Manual Scanning

Use any of these methods to manually trigger a vault scan:

**Settings Panel:**

- Click **Scan Now** in Settings → Project Planner → Daily Note Task Tagging

**Ribbon Icon:**

- Click the scan icon (📡) in the left sidebar

**Command Palette:**

- Press `Ctrl/Cmd + P`
- Type "Scan Daily Notes"
- Press Enter

Manual scanning is useful when:

- You've just enabled the feature
- You want to import existing tagged tasks
- You've made bulk changes to notes
- You need to force an immediate refresh

**Note:** A notification will appear showing how many tasks were found and imported.

## Automatic Scanning

The plugin uses intelligent file watching for real-time updates:

### How It Works

- **Automatic Detection** - Watches for file changes in real-time
- **Debounced Scanning** - Waits 1 second after the last change before scanning
- **Efficient Processing** - Only scans modified files, not entire vault
- **Background Operation** - Scanning happens automatically as you work

### What Triggers a Scan

- **Creating a new note** - Automatically scanned when saved
- **Editing existing notes** - Rescans 1 second after you stop typing
- **Multiple rapid changes** - Batched together to prevent excessive scanning

### Refresh Frequency

The debouncing system ensures:

- No lag while typing
- Changes processed quickly (1 second after you stop editing)
- Minimal performance impact
- No duplicate scans

If you need immediate results, use the manual scan options above.

## Task Metadata

Imported tasks include:

- **Source Link** - Automatic link back to the originating note
- **Description** - Shows "Imported from: [[Note Name]]"
- **Unique ID** - Generated from file path and task title to prevent duplicates

## Best Practices

### Daily Notes Integration

Perfect for daily note workflows:

```markdown
# 2026-01-14

## Morning

- [x] Review emails #planner/Work
- [ ] Team standup !! #planner/Work

## Afternoon

- [ ] Design review 📅 2026-01-14 #planner/Work #design
- [ ] Update project timeline (high) #planner/Work

## Personal

- [ ] Gym session #planner/Personal
- [ ] Grocery shopping #planner/Personal
```

### Meeting Notes

Capture action items from meetings:

```markdown
# Team Meeting - 2026-01-14

## Action Items

- [ ] @John Update API documentation due: 2026-01-20 #planner/Engineering
- [ ] @Sarah Create design mockups !! #planner/Design
- [ ] Schedule follow-up meeting @2026-01-21 #planner/Management
```

### Project Journal

Keep project-specific journals with task extraction:

```markdown
# Engineering Journal - Week 3

## Completed This Week

- [x] Implemented login feature #planner/Engineering
- [x] Fixed authentication bug #planner/Engineering

## Next Week

- [ ] Add password reset !!! #planner/Engineering
- [ ] Improve error handling #planner/Engineering
```

## Avoiding Duplicates

The plugin uses a **location-based tracking system** to prevent duplicate task imports:

### How It Works

Each task is tracked by its **file path and line number**, not by its content. This means:

- **Editing a task** - Updates the existing task in your planner (no duplicate created)
- **Moving a task** - Creates a new task at the new location (intentional - different context)
- **Copying a task** - Creates a new task (different line number = different task)

### Examples

**✅ No Duplicate - Editing Content:**

```markdown
<!-- Before -->

- [ ] Write documentation #planner

<!-- After editing (same line) -->

- [ ] Write documentation for new feature #planner
```

Result: Task title updates to "Write documentation for new feature"

**✅ No Duplicate - Changing Status:**

```markdown
<!-- Before -->

- [ ] Review code #planner

<!-- After completing -->

- [x] Review code #planner
```

Result: Task marked as completed in planner

**✅ New Task - Different Location:**

```markdown
<!-- Original task on line 5 -->

- [ ] Buy groceries #planner

<!-- Same text on line 20 -->

- [ ] Buy groceries #planner
```

Result: Two separate tasks (different contexts/locations)

### Task Identity

- **Task ID** - Generated once per file location, persists through edits
- **Location Key** - `filePath:lineNumber` used to track task position
- **Updates** - Any changes to the task text update the existing task
- **Cleanup** - If you delete a task from your note, the location tracking is removed

This approach ensures you can freely edit your tasks without creating duplicates!

## Limitations

### Current Limitations

1. **Task updates** - Changing a task in the source note will update the planner task, but changing it in the planner doesn't update the source note
2. **Task deletion** - Deleting a task from the source note doesn't remove it from the planner (prevents accidental deletion)
3. **Subtasks** - Nested subtasks in daily notes are not currently supported
4. **Dependencies** - Task dependencies must be set in the planner views

### Future Enhancements

Planned improvements:

- Bidirectional sync (update source notes when tasks change in planner)
- Task deletion sync
- Support for nested subtasks
- Inline task editing with live preview

## Troubleshooting

### Tasks Not Being Imported

**First, check the basics:**

1. **Feature enabled?** - Settings → Project Planner → Daily Note Task Tagging → Enable Daily Note Sync must be ON
2. **Default project set?** - **This is required!** Select a project in the "Default Project" dropdown
3. **Correct tag?** - Make sure tasks use the correct tag (default: `#planner`)
4. **File location?** - If you specified scan folders, your note must be in one of them

**Open the Developer Console** (Ctrl+Shift+I on Windows, Cmd+Option+I on Mac):

When the scanner initializes, you'll see:

```
[DailyNoteScanner] Initializing daily note scanner...
[DailyNoteScanner] Tag pattern: #planner
[DailyNoteScanner] Scan folders: []
[DailyNoteScanner] Default project: <project-id>
[DailyNoteScanner] Available projects: Personal (<id>), Work (<id>)
```

When scanning files, you'll see:

```
[DailyNoteScanner] Starting scan of all notes...
[DailyNoteScanner] Adding task: Buy groceries to project: <project-id>
[DailyNoteScanner] Scan complete. Found 1 tasks.
```

**Common error messages:**

If you see:

```
[DailyNoteScanner] No project found for task: Buy groceries
```

This means:

- No default project is set (for `#planner` tags), OR
- Project name doesn't match any existing project (for `#planner/ProjectName` tags)

The console will also show which project name was extracted and list all available projects to help you debug.

**Still not working?**

- Try clicking "Scan Now" in settings to force a manual scan
- Check the console for any error messages
- Verify your task format: `- [ ] Task text #planner`

### Wrong Project Assignment

1. **Check project names** - Project names in tags must match exactly (case-insensitive)
   - You have a project called "Personal" → Use `#planner/Personal`
   - Console will show: "Available projects: Personal (<id>), Work (<id>)"
2. **Use spaces or hyphens** - For "Project Planner", use either:
   - `#planner/Project Planner` (direct with spaces)
   - `#planner/Project-Planner` (hyphens converted to spaces)
3. **Verify default project** - Tasks with just `#planner` (no `/ProjectName`) use the default project

### Tasks Not Updating

1. **Save the file** - Changes are only detected when the file is saved
2. **Wait a moment** - File watcher triggers after metadata cache updates (usually < 1 second)
3. **Check console** - Look for scan messages showing the task was detected
4. **Re-enable if needed** - Toggle the feature off and on in settings to restart watchers

### Debugging Tips

**Enable verbose logging:**

1. Open Developer Console (Ctrl+Shift+I / Cmd+Option+I)
2. Keep it open while creating/editing tasks
3. Look for `[DailyNoteScanner]` messages

**Test with a simple example:**

```markdown
- [ ] Test task #planner
```

Save the file and check console for:

```
[DailyNoteScanner] Adding task: Test task to project: <id>
```

**Verify settings:**

- Settings → Project Planner → Daily Note Task Tagging
- Ensure "Enable Daily Note Sync" is toggled ON
- Ensure "Default Project" has a project selected (not "Select a project...")

## Examples

### Complete Daily Note Template

```markdown
---
tags: daily-note
date: { { date } }
---

# {{date:YYYY-MM-DD}}

## 🎯 Goals for Today

- [ ] Complete feature implementation !! #planner/Work due: {{date:YYYY-MM-DD}}
- [ ] Code review session #planner/Work
- [ ] Update documentation #planner/Work

## 📝 Notes

Morning standup notes go here...

## ✅ Completed

- [x] Email responses #planner/Work
- [x] Bug fix #planner/Work #bug

## 🏠 Personal

- [ ] Workout #planner/Personal
- [ ] Read for 30 minutes #planner/Personal

## 📅 Tomorrow

- [ ] Prepare presentation !!! #planner/Work @{{date+1d:YYYY-MM-DD}}
```

---

**Happy Task Planning! 🚀**
