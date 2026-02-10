---
title: FAQ
date:
  created: 2026-01-14
  updated: 2026-02-10
readtime: 4
---

# Frequently Asked Questions

## Data Structure

??? question "Where are Tasks stored?"
    Tasks are stored in `.obsidian/plugins/obsidian-project-planner/data.json`. See the [Data Structure Reference](../features/data-structure.md) for complete details on data organization, schema, and storage formats.

---

## Markdown Sync

??? question "What is Markdown Sync and how does it work?"
    Markdown Sync enables bidirectional synchronization between the plugin's JSON data and markdown files in your vault. When enabled, tasks are automatically created/updated as markdown files at `{ProjectName}/Tasks/{TaskTitle}.md`, and changes to those markdown files sync back to the plugin.

??? question "What settings control Markdown Sync?"
    **Enable Markdown Sync** - Watches markdown files for changes and syncs to plugin. **Auto-Create Task Notes** - Automatically creates/updates markdown files when you modify tasks in the UI. **Sync on Startup** - Imports existing task markdown files when plugin loads (disable if using Obsidian Sync to prevent duplicates).

??? question "Can I manually create tasks by writing markdown files?"
    Yes! Create a markdown file in `{ProjectName}/Tasks/` with YAML frontmatter containing required fields: `id` (UUID), `title`, `status`, and `completed`. The plugin will detect and import it automatically. Generate UUIDs using `[guid]::NewGuid().ToString()` in PowerShell.

??? question "What fields can I use in task frontmatter?"
    Required: `id`, `title`, `status`, `completed`. Optional: `parentId`, `priority`, `bucketId`, `startDate`, `dueDate`, `tags`, `collapsed`, `dependencies` (array of `{TYPE}:{TASK_ID}` like `FS:task-abc123`).

??? question "How does the plugin handle simultaneous edits?"
    The sync system uses a 200ms timeout to prevent infinite loops. If you edit markdown and plugin data simultaneously, the last save wins. Task IDs are tracked in a `syncInProgress` Set during operations to avoid conflicts.

??? question "Can I use Markdown Sync with Obsidian Sync?"
    Yes, but **disable Sync on Startup** in plugin settings. This prevents tasks from being duplicated each time Obsidian starts after syncing across devices.

??? question "What happens to subtasks when syncing from markdown?"
    Subtask IDs are regenerated when syncing from markdown, but titles and completion states are preserved. The hierarchical structure is maintained.

??? question "Can I bulk update tasks using markdown files?"
    Yes! Use find-and-replace across multiple task files, scripts, or text editors to update tags, priorities, dates, or other fields. Changes sync automatically back to the plugin.

??? question "How can I use markdown tasks with version control?"
    Commit task markdown files to git for team collaboration and change tracking. Markdown format makes diffs readable and merge conflicts easier to resolve than JSON.

??? question "Can I use other Obsidian plugins with synced tasks?"
    Yes! Use plugins like Dataview, Templater, or Breadcrumbs to query and manipulate task data. Create task templates as markdown files and copy/modify them for new tasks.

---

## Dashboard View

??? question "How do I create a new project?"
    Go to Settings → Project Planner → Click "Add project" button.

??? question "Can I reorder project cards?"
    Not yet - currently alphabetical. Drag-to-reorder planned for v0.8.0.

??? question "How is completion rate calculated?"
    (Completed tasks / Total tasks) × 100 across all projects.

??? question "Why isn't my project showing on Dashboard?"
    Check that project exists in settings and has a valid ID and name.

??? question "Can I hide certain projects from Dashboard?"
    Not currently - if **Show All Projects** is checked, all projects display. Hide/show feature planned for future release.

??? question "How often do metrics update?"
    Automatically whenever tasks change. Manual refresh also available.

??? question "Can I export Dashboard data?"
    Currently only via screenshot. Export features planned for v1.0.0.

??? question "What's the max number of projects Dashboard can handle?"
    No hard limit, but 20-30 projects recommended for best UX.

??? question "Do archived projects show on Dashboard?"
    Yes, if project exists in settings it appears. Delete to remove from Dashboard.

??? question "Can I customize which metrics show?"
    Not yet - metric customization planned for future release.

---

## Grid View

??? question "Can I reorder columns?"
    Yes. Click on the column header to drag it to a new location.

??? question "How do I export grid data?"
    Use markdown sync to create individual task files, or access data.json directly.

??? question "Can I have multiple parents for one task?"
    No - each task has 0 or 1 parent only.

??? question "What happens to children when I delete a parent?"
    Children are promoted to top-level tasks (not deleted).

??? question "Can I move tasks between projects?"
    Not directly in UI - requires manual data.json editing.

??? question "How many tasks can grid view handle?"
    Hundreds comfortably, thousands with performance considerations.

??? question "Do subtasks count toward parent completion?"
    Not automatically - parent status is independent.

??? question "Can I print the grid view?"
    Use browser print (Ctrl+P) or export to markdown first.

---

## Board View

??? question "What are buckets and how are they different from status?"
    **Buckets** are visual columns that organize tasks (like "To Do", "In Progress", "Done"). **Status** is a task property that tracks lifecycle state. Tasks can have any status in any bucket - buckets control column placement, while status is shown on the card. Change buckets by dragging cards; change status in Task Details panel.

??? question "Can I customize buckets for each project?"
    Yes! Each project has its own bucket configuration. You can add, rename, delete, reorder, and color buckets per project. Default buckets ("To Do", "In Progress", "Done") are just placeholders you can customize.

??? question "How do I move a task to a different bucket?"
    Click and drag the task card to the target bucket and release. The task's bucketId updates automatically. Alternatively, open Task Details panel and select the bucket from the dropdown.

??? question "Can I rename or delete the 'Unassigned' bucket?"
    You can rename it, but you cannot move it, delete it, or color it. The Unassigned bucket is a special bucket for tasks without a bucket assignment.

??? question "What information shows on task cards?"
    Cards display: title (clickable), priority badges (🔥 Critical / ⚡ High), colored tags, status with color coding, due date (red if overdue, blue if today), subtask progress (✓ 2/5), dependency indicator (🔗), attachment indicator (📎), and a completion checkbox.

??? question "Where do completed tasks go?"
    When you click the checkbox on a task card, it moves to the completed section of the same bucket. Each bucket has collapsible active and completed sections.

??? question "Can I reorder buckets?"
    Yes. Select a bucket header and drag it left or right to reorder. The bucket order is saved per project.

??? question "What happens to tasks when I delete a bucket?"
    Tasks remain in the project but their bucketId is cleared. They'll move to the Unassigned bucket.

??? question "How do I create a new task in a specific bucket?"
    Click the "+ Add task" button at the top of any bucket. The task will be created with that bucket assigned. Or click "Add Task" in the toolbar for default bucket assignment.

??? question "Can I use Board View for different workflows?"
    Yes! Common patterns include organizing by phase ("Planning", "Development", "Testing"), by team ("Backend", "Frontend", "Design"), by sprint ("Backlog", "Sprint 1", "Sprint 2"), or by priority ("Critical", "This Week", "Someday").

---

## Dependency Graph

??? question "What's the difference between FS, SS, FF, and SF?"
    FS = finish-to-start (most common), SS = start together, FF = finish together, SF = rare handoff scenario.

??? question "Can I create a dependency to a task in another project?"
    Not currently - dependencies are project-scoped. Future versions may support cross-project links.

??? question "How do I find the critical path?"
    Not yet automated. Manually trace longest dependency chain. Auto-detection coming in future release.

??? question "What happens if I create a circular dependency?"
    Plugin should prevent this (A → B → A). If one exists, remove via Task Detail panel.

??? question "Can I print the dependency graph?"
    Currently only via screenshot. Export/print features planned for v1.0.0.

??? question "Why are some dependencies not showing?"
    Check dependency types are defined correctly in task data. Refresh view or check console for errors.

??? question "How many tasks can the graph handle?"
    Tested up to 200 tasks. Performance degrades beyond that. Use filters (future) for larger projects.

??? question "Can I change the graph layout?"
    Not currently. Layouts planned for future release.

??? question "Do subtasks show in the graph?"
    Not currently - only top-level tasks. Subtask visualization planned for future release.

??? question "Can I export the graph as an image?"
    Not yet - currently screenshot only. PNG/SVG export planned for v1.0.0.

---

## Timeline View

??? question "How do I change a task's start or due date?"
    Hover over the task bar. To move both dates together, drag the bar body. To change start date only, drag the left handle (◀). To change due date only, drag the right handle (▶). Release to save changes.

??? question "What are the different zoom levels?"
    Timeline has three zoom modes: **Day View** (each cell = 1 day) for fine-grained scheduling, **Week View** (each cell = 1 week) for sprint planning, and **Month View** (each cell = 1 month) for long-term roadmaps. Toggle using toolbar buttons.

??? question "Can I reorder tasks in Timeline View?"
    Yes. Click the ⋮⋮ drag handle on any task row and drag up or down. Parent tasks move with all their children. Dropping a subtask in a new position can change its parent based on placement.

??? question "How do I create or manage subtasks?"
    Right-click a task and select "Make subtask" to convert it to a child of the previous task. To promote a subtask to top-level, right-click and select "Promote to parent". Click ▼/▶ icons to collapse/expand parent tasks.

??? question "What does the task list panel show?"
    The left panel displays hierarchical tasks with drag handles (⋮⋮), collapse/expand icons (▼/▶), inline editable titles, status colors, and priority indicators. Right-click for context menu operations.

??? question "How do I filter tasks in Timeline View?"
    Use the filter toolbar to filter by status (dropdown), priority (dropdown), or search text across task titles. Filters apply to both the task list and timeline bars.

??? question "Can I resize task bars to be less than one day?"
    No. Task bars have a minimum duration of one day. If you need sub-day tracking, use subtasks or notes.

??? question "What does the 'Today' indicator show?"
    A vertical line marks the current date on the timeline, helping you see which tasks are current, upcoming, or overdue at a glance.

??? question "Can I edit task titles directly in Timeline View?"
    Yes. Click the task title in the left task list panel to edit inline. Press Enter to save or Escape to cancel.

??? question "What happens when I move a parent task bar?"
    Only the parent task's dates change. Child tasks remain at their original dates independently. To move all children together, you'll need to adjust each child individually or plan a batch date update.