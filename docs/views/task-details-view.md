---
title: Task Details Panel
date:
  created: 2026-01-14
readtime: 7
---

# Task Details Panel

## Overview

The Task Details panel is a dedicated sidebar view that displays all properties and metadata for a single task. It provides comprehensive editing capabilities in a focused interface, eliminating the need to switch between views or use inline editors.

## Features

### **Comprehensive Task Editor**

Edit all task properties in one place:

- **Title**: Task name with inline editing
- **Status**: Dropdown selector for workflow states
- **Priority**: Dropdown for importance level
- **Tags**: Multi-select with color-coded badges
- **Bucket**: Dropdown for Board view bucket assignment
- **Start Date**: Date/time picker
- **Due Date**: Date/time picker
- **Description**: Rich text editor with Markdown preview
- **Dependencies**: Task relationship manager
- **Links & Attachments**: Wiki links and external URLs
- **Checklist**: Subtask items with drag-to-reorder

### **Quick Actions**

Header buttons for common operations:

- **Complete Button**: Toggle task completion status
  - Shows ✓ icon when completed
  - Click to mark complete or revert to "Not Started"
  - Button style changes based on completion state
- **Copy Link Button**: Copy deep link to clipboard
  - Generates `obsidian://open-planner-task?id=...` URI
  - Shows "Copied!" confirmation feedback
  - Paste link anywhere (notes, chat, documentation)
- **Close Button**: Close the Task Details panel (× icon)

### **Tag Management**

Interactive tag selector with visual badges:

- **Add Tags**: Click tags from dropdown to add
- **Remove Tags**: Click × on tag badge to remove
- **Color Coded**: Each tag displays with configured color
- **Multi-Select**: Add multiple tags to single task
- Tags sync across all views (Grid, Board, Timeline)

### **Bucket Assignment**

Dropdown selector for Board view organization:

- **Unassigned**: Default option (no bucket)
- **Project Buckets**: List of buckets from active project
- Changes immediately update Board view column placement
- Independent from task status field

### **Date & Time Editing**

Dedicated pickers for temporal properties:

- **Date Input**: HTML5 date picker with calendar
- **Clear Button**: Remove date entirely (leaves field empty)
- **Format**: ISO 8601 (YYYY-MM-DD)
- Changes immediately update Timeline view visualization

### **Markdown Description**

Rich text editing with preview toggle:

- **Edit Mode**: Plain text editor with Markdown syntax
- **Preview Mode**: Rendered Markdown with Obsidian parsing
- **Toggle Button**: Switch between edit and preview
- Supports all Markdown features:
  - Headers, lists, emphasis
  - Links (wiki and external)
  - Code blocks, quotes
  - Embedded images

### **Dependency Manager**

Visual dependency editor with type selection:

- **Dependency Types**:
  - **FS** (Finish-to-Start): Predecessor must finish before this task starts
  - **SS** (Start-to-Start): Tasks start simultaneously
  - **FF** (Finish-to-Finish): Tasks finish simultaneously
  - **SF** (Start-to-Finish): This task finishes when predecessor starts
- **Add Dependency**: Select type and target task from dropdown
- **Remove Dependency**: Click × button on dependency item
- **Task Selector**: Filtered list excludes current task and descendants
- Dependencies visualized in Dependency Graph View

### **Links & Attachments**

Manage task-related resources:

- **Link Types**:
  - **Obsidian Links**: Wiki-style `[[Note Name]]` links to vault notes
  - **External Links**: Full URLs to websites, docs, repositories
- **Add Link**: Type or paste link, optional title
- **Remove Link**: Click × button on link item
- **Click to Open**: Links open in default application
- Link IDs regenerated during markdown sync (titles/URLs preserved)

### **Checklist (Subtasks)**

Task breakdown with interactive list:

- **Checkbox**: Toggle completion state inline
- **Inline Edit**: Click title to edit text
- **Drag to Reorder**: Grab ⋮⋮ handle and drag up/down
- **Add Item**: Button at bottom to create new checklist item
- **Delete Item**: × button on each item
- **Visual Feedback**: Drop indicator shows where item will land during drag
- Progress shown on task cards in other views (e.g., "✓ 2/5")

## Usage

### **Opening Task Details**

Task Details panel opens automatically when you:

- Click a task row in Grid View
- Click a task card in Board View
- Click a task bar in Timeline View
- Click a task node in Dependency Graph View
- Use URI protocol link: `obsidian://open-planner-task?id={taskId}&project={projectId}`

**Via Command Palette:**

- Press `Ctrl/Cmd + P`
- Type "Open Task Details"
- Enter task ID when prompted (for manual opening)

**Panel Location:**

- Opens in right sidebar by default
- Can be moved to any Obsidian pane
- Supports split view (details + grid/board/timeline)

### **Editing Task Properties**

**Title:**

1. Click the title input field
2. Type new task name
3. Click outside field or press Enter to save

**Status:**

1. Click status dropdown
2. Select new status from list
3. Saves immediately on selection
4. "Completed" status syncs `completed` boolean flag

**Priority:**

1. Click priority dropdown
2. Select priority level
3. Saves immediately

**Tags:**

1. Click tags dropdown
2. Click tag name to add
3. Click × on badge to remove
4. Tags appear as colored badges

**Bucket:**

1. Click bucket dropdown
2. Select bucket or "Unassigned"
3. Changes Board view column placement

**Dates:**

1. Click date input to open calendar picker
2. Select date from calendar
3. Or type date in YYYY-MM-DD format
4. Click "Clear" button to remove date

**Description:**

1. Click in description text area
2. Type Markdown-formatted text
3. Click "Preview" to see rendered output
4. Click "Edit" to return to editing mode
5. Saves on blur (clicking outside)

### **Managing Dependencies**

**Add Dependency:**

1. Click "+ Add Dependency" button
2. Select dependency type (FS, SS, FF, SF)
3. Select predecessor task from dropdown
4. Dependency appears in list
5. Updates Dependency Graph View

**Remove Dependency:**

1. Find dependency in list
2. Click × button
3. Dependency removed immediately

**Understanding Types:**

- **FS (Finish-to-Start)**: Most common - task B starts after task A finishes
- **SS (Start-to-Start)**: Tasks start together (parallel work)
- **FF (Finish-to-Finish)**: Tasks finish together (synchronized delivery)
- **SF (Start-to-Finish)**: Rare - task B finishes when task A starts

### **Managing Links**

**Add Obsidian Link:**

1. Click "+ Add Link" button
2. Select "Obsidian" type
3. Type note name (autocomplete helps)
4. Link appears in list with 📄 icon

**Add External Link:**

1. Click "+ Add Link" button
2. Select "External" type
3. Paste or type full URL
4. Optionally add display title
5. Link appears in list with 🔗 icon

**Open Link:**

- Click link title to open in default app
- Obsidian links open in vault
- External links open in browser

**Remove Link:**

- Click × button on link item

### **Managing Checklist**

**Add Item:**

1. Click "Add checklist item" button
2. New item appears at bottom
3. Click title to edit text

**Complete Item:**

1. Click checkbox to toggle completion
2. Completed items show ✓
3. Progress updates on task cards

**Reorder Items:**

1. Click ⋮⋮ drag handle
2. Drag item up or down
3. Drop indicator shows placement
4. Release to reorder

**Edit Item:**

1. Click item title
2. Type new text
3. Click outside or press Enter

**Delete Item:**

1. Click × button on item
2. Item removed immediately

### **Completing Tasks**

**Mark as Complete:**

1. Click "Mark as Complete" button in header
2. Status changes to "Completed"
3. `completed` flag sets to `true`
4. Button changes to "Completed" with ✓ icon
5. Task moves to completed section in Board view

**Mark as Incomplete:**

1. Click "Completed" button
2. Status reverts to "Not Started"
3. `completed` flag sets to `false`
4. Task returns to active section

### **Copying Task Link**

**Get Shareable Link:**

1. Click "Copy Link" button in header
2. URI copied to clipboard: `obsidian://open-planner-task?id={taskId}&project={projectId}`
3. Button shows "Copied!" confirmation (2 seconds)
4. Paste link in notes, chat, or documentation
5. Anyone with the plugin can click link to open this task

**Using URI Links:**

- Paste in Obsidian notes: Creates clickable link
- Share in team chat: Direct task access
- Embed in documentation: Cross-reference tasks
- Bookmark in browser: Quick task access

## Integration

### **Grid View**

- Select task row in Grid to open Task Details
- Details panel shows canonical task data
- Changes sync back to Grid row immediately
- Close details to return focus to Grid

### **Board View**

- Click task card to open Task Details
- Edit bucket assignment via dropdown
- Completion toggle moves card between sections
- Card updates instantly when details change

### **Timeline View**

- Click task bar to open Task Details
- Date changes update bar position/width
- Hierarchy changes reflect in task list
- Details panel allows precise date/time entry

### **Dependency Graph View**

- Click node to open Task Details
- Add/remove dependencies to update graph
- Graph re-renders when relationships change
- Visual and detail views stay synchronized

### **Markdown Sync** (v0.6.2+)

- All changes in Task Details write to markdown files
- Markdown edits sync back to Task Details panel
- Description, subtasks, links preserved bidirectionally
- See MARKDOWN_SYNC.md for details

## Visual Design

The Task Details panel follows Obsidian's design system:

### **Layout**

- Clean vertical scrollable layout
- Section headers (h3) separate property groups
- Consistent spacing between fields
- Responsive to sidebar width

### **Input Styling**

- Native Obsidian input components
- Focus states with accent color
- Hover effects on interactive elements
- Disabled states for unavailable options

### **Color Indicators**

- Tag badges use configured tag colors
- Status colors from Settings → Statuses
- Priority indicators match Grid/Board views
- Completion button green when active

### **Buttons**

- Primary actions in header (complete, copy link, close)
- Secondary actions inline (add dependency, add link)
- Icon + text labels for clarity
- Success states with visual feedback

## Keyboard Shortcuts

While Task Details doesn't have specific keyboard shortcuts, you can:

- Use `Tab` to navigate between fields
- Press `Enter` in input fields to save
- Use standard text editing shortcuts in description
- Press `Escape` to close panel (if configured in Obsidian settings)

## Tips & Best Practices

1. **Keep Panel Open**: Pin Task Details in right sidebar for quick task editing
2. **Split View**: Open Grid or Board on left, Details on right for seamless workflow
3. **Use Descriptions**: Add context in Markdown description for future reference
4. **Link Liberally**: Connect tasks to relevant notes and resources
5. **Break Down Tasks**: Use checklist for subtask tracking without creating separate tasks
6. **Set Dependencies**: Define task relationships for better project planning
7. **Copy Links**: Share task links in team communication for direct access
8. **Preview Markdown**: Toggle preview to ensure descriptions render correctly
9. **Drag Checklist**: Reorder checklist items to match workflow sequence
10. **Complete Button**: Use header button instead of changing status dropdown (faster)

## Troubleshooting

**Panel not opening when clicking tasks?**

- Check that right sidebar is visible (toggle with sidebar icon)
- Try clicking task again or use Command Palette
- Restart Obsidian if panel view registration failed
- Check Developer Console (Ctrl+Shift+I) for errors

**Changes not saving?**

- Ensure you click outside input fields to trigger save
- Dropdown selections save immediately
- Check markdown sync isn't creating conflicts
- Verify TaskStore is loaded (try reloading plugin)

**Tags/buckets not showing in dropdowns?**

- Verify tags/buckets are configured in Settings
- Ensure active project has buckets defined
- Try switching projects and back
- Reload plugin (Ctrl+R)

**Markdown preview not rendering?**

- Check Markdown syntax is valid
- Toggle preview off and on
- Preview uses Obsidian's Markdown renderer
- Complex plugins may not render in preview

**Dependencies not appearing in dropdown?**

- Dropdown excludes current task (can't depend on self)
- Dropdown excludes descendant tasks (prevents cycles)
- Ensure other tasks exist in project
- Check filters aren't hiding tasks

**Checklist drag not working?**

- Grab ⋮⋮ handle (not checkbox or title)
- Ensure you're dragging within checklist area
- Drop indicator shows valid placement
- Release mouse to complete drop

**Copy link button not working?**

- Browser must support Clipboard API
- Check for clipboard permission errors in console
- Try using Ctrl+C after selecting URI text
- URI format: `obsidian://open-planner-task?id={id}&project={projectId}`

**Panel shows "No task selected"?**

- Click a task in Grid, Board, Timeline, or Graph view
- Use URI protocol link to open specific task
- Task may have been deleted - check Grid view
- Try selecting different task

**Changes not syncing to markdown?**

- Check "Enable Markdown Sync" in settings
- Verify "Auto-Create Task Notes" is enabled
- See MARKDOWN_SYNC.md troubleshooting section
- Check Developer Console for `[TaskSync]` messages
