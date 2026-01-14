# Timeline View (Gantt Chart)

## Overview

The Timeline View (also known as Gantt View) provides a visual timeline representation of tasks with their start and due dates. It displays tasks chronologically across a horizontal timeline, allowing you to see task durations, overlaps, and schedule gaps at a glance.

## Features

### **Visual Timeline Layout**

- Hierarchical task display with parent/child indentation
- Horizontal bars representing task duration
- Resizable split-pane layout (task list + timeline chart)
- Collapsible parent tasks to hide/show children
- Today indicator line for temporal context

### **Zoom Levels**

Three zoom modes for different planning horizons:

- **Day View**: Each cell represents one day (fine-grained scheduling)
- **Week View**: Each cell represents one week (sprint/milestone planning)
- **Month View**: Each cell represents one month (long-term roadmap)

Toggle between zoom levels using buttons in the toolbar.

### **Interactive Timeline Bars**

Each task bar supports:

- **Move**: Drag the bar body to shift start and due dates together
- **Resize Left**: Drag left handle to adjust start date
- **Resize Right**: Drag right handle to adjust due date
- **Click**: Click bar to open Task Details panel
- **Visual Feedback**: Bars highlight on drag, show handles on hover

### **Task List Panel**

Left side shows hierarchical task information:

- **Drag Handle**: ⋮⋮ icon for reordering tasks
- **Collapse/Expand**: ▼/▶ icons for parent tasks
- **Inline Title Edit**: Click title to edit task name
- **Context Menu**: Right-click for task operations
- **Color Coding**: Status colors and priority indicators

### **Smart Filtering**

Filter toolbar with multiple criteria:

- **Status Filter**: Dropdown to filter by task status
- **Priority Filter**: Dropdown to filter by priority level
- **Search Filter**: Text search across task titles
- Filters apply across both task list and timeline

### **Task Operations**

Right-click context menu provides:

- **Open Details**: Open Task Details panel for full editing
- **Add Task Above**: Insert new task before current task
- **Make Subtask**: Convert task to child of previous task
- **Promote to Parent**: Move subtask up one hierarchy level
- **Delete Task**: Remove task from project

## Usage

### **Opening Timeline View**

**Via Ribbon:**

- Click the 📅 calendar icon in the left sidebar

**Via Command Palette:**

- Press `Ctrl/Cmd + P`
- Type "Open Timeline View" or "Open Gantt View"
- Press Enter

**Via Keyboard:**

- Assign a hotkey in Settings → Hotkeys → "Open Timeline View"

### **Adjusting Task Dates**

**Move Task:**

1. Hover over a task bar
2. Click and drag the bar body (avoid handles)
3. Release to set new date range
4. Both start and due dates shift by the same amount

**Change Start Date:**

1. Hover over left edge of task bar
2. Click and drag the left handle (◀)
3. Release to set new start date
4. Due date remains unchanged

**Change Due Date:**

1. Hover over right edge of task bar
2. Click and drag the right handle (▶)
3. Release to set new due date
4. Start date remains unchanged

**Note:** Bars cannot be resized to less than one day duration.

### **Managing Hierarchy**

**Create Subtask:**

1. Right-click a task in the list
2. Select "Make subtask"
3. Task becomes child of the previous task in the list

**Promote Subtask:**

1. Right-click a child task
2. Select "Promote to parent"
3. Task moves up one level in hierarchy

**Collapse/Expand:**

- Click ▼ icon on parent task to collapse children
- Click ▶ icon to expand and show children
- Useful for focusing on high-level milestones

### **Reordering Tasks**

**Drag and Drop:**

1. Click the ⋮⋮ drag handle on any task row
2. Drag up or down to new position
3. Drop between other tasks
4. Parent tasks move with all their children as a block
5. Subtasks can change parents when dropped

**Hierarchy Rules:**

- Dropping a subtask changes its parent based on position
- Dropping before a subtask makes it share the same parent
- Dropping after a parent makes it a root task
- Cannot drop parent onto its own descendants

### **Resizing Panels**

**Adjust Split:**

1. Hover over the divider between task list and timeline
2. Cursor changes to resize indicator
3. Click and drag left/right to adjust widths
4. Width preference saves to browser localStorage

### **Filtering Tasks**

**By Status:**

- Click status dropdown in toolbar
- Select specific status or "All"
- Only matching tasks appear

**By Priority:**

- Click priority dropdown in toolbar
- Select priority level or "All"
- Filters combine with other active filters

**By Search:**

- Type in search box
- Filters as you type
- Searches task titles (case-insensitive)
- Clear search to show all tasks

### **Zoom Control**

**Change Zoom Level:**

1. Click "Day", "Week", or "Month" buttons in toolbar
2. Timeline rescales to show selected time unit
3. Task bars adjust proportionally
4. Useful for switching between tactical and strategic views

## Task Display Rules

### **Date Handling**

- **No Dates**: Task appears at "today" with 1-day duration
- **Start Only**: Task spans from start date to start date
- **Due Only**: Task appears at due date
- **Both Dates**: Task spans from start to due date
- **Invalid Range**: If due < start, due date adjusts to match start

### **Bar Colors**

Task bars are colored based on status:

- Each status has a configurable color (see Settings → Statuses)
- Completed tasks typically show in muted/green tones
- In Progress tasks might show in blue
- Not Started tasks might show in gray

### **Visual Indicators**

- **Priority Badges**: 🔥 Critical, ⚡ High (displayed in task list)
- **Today Line**: Vertical line marking current date on timeline
- **Hover Effects**: Bars and handles highlight on mouse over
- **Drag Feedback**: Bars become semi-transparent during drag

## Global Navigation

The timeline view includes the shared global header:

- **Project Dropdown**: Switch between projects
- **Add Task**: Quick task creation (opens at today's date)
- **📋 Hub**: Open project hub documentation
- **⚙️ Settings**: Open plugin settings

## Integration

### **Task Details Panel**

- Click any task bar to open Task Details (right sidebar)
- Edit all properties without leaving timeline view
- Changes sync instantly to timeline visualization

### **Grid View**

- Same hierarchical structure appears in both views
- Timeline shows only tasks with dates
- Grid View shows all tasks with full metadata columns
- Switch between views seamlessly

### **Board View**

- Timeline and Board share the same tasks
- Board shows leaf tasks only (no hierarchy)
- Timeline shows full hierarchy
- Use timeline for scheduling, board for workflow status

### **Markdown Sync** (v0.6.2+)

- Date changes in timeline update corresponding markdown files
- Markdown edits to start/due dates sync back to timeline
- Hierarchy changes (parent/child) sync bidirectionally
- See MARKDOWN_SYNC.md for details

## Keyboard Shortcuts

While the timeline doesn't have specific keyboard shortcuts, you can:

- Use standard Obsidian navigation (`Ctrl/Cmd + Tab`, etc.)
- Click task titles or bars to open details and use keyboard editing
- Assign custom hotkeys in Settings for opening timeline view

## Performance

The timeline is optimized for smooth interaction:

- Efficient rendering with HTML5 Canvas for timeline grid
- Drag and drop uses pointer capture for responsiveness
- Hierarchical collapse reduces visual complexity
- Handles hundreds of tasks smoothly

## Tips & Best Practices

1. **Set Realistic Dates**: Always set both start and due dates for accurate scheduling
2. **Use Zoom Levels**: Switch to Week/Month view for long-term planning
3. **Collapse Parents**: Hide completed or future work to focus on current tasks
4. **Drag to Schedule**: Quickly adjust schedules by dragging bars instead of editing dates manually
5. **Filter for Focus**: Use filters to isolate specific workstreams or priority levels
6. **Resize Panel**: Adjust split to show more task details or more timeline context
7. **Check Today Line**: Use the today indicator to identify overdue tasks at a glance
8. **Combine with Dependencies**: Timeline makes dependency relationships visual (see GRAPH_FEATURES.md)

## Comparison to Other Views

| Feature             | Timeline View          | Grid View              | Board View           |
| ------------------- | ---------------------- | ---------------------- | -------------------- |
| Layout              | Horizontal timeline    | Hierarchical table     | Kanban buckets       |
| Best For            | Date-based scheduling  | Detailed editing       | Visual workflow      |
| Task Representation | Duration bars          | Table rows             | Cards                |
| Hierarchy           | Full (collapsible)     | Full (expandable)      | Leaf tasks only      |
| Date Editing        | Visual drag/resize     | Input fields           | Via details panel    |
| Filtering           | Status/priority/search | Multi-field filter bar | Priority/search      |
| Reordering          | Drag handle            | Drag handle            | Drag between buckets |
| Zoom/Scale          | Day/Week/Month         | N/A                    | N/A                  |

Use **Timeline View** for visual scheduling and date-based planning.
Use **Grid View** for hierarchical task management and bulk editing.
Use **Board View** for workflow status and quick bucket reassignment.

## Troubleshooting

**Tasks not showing on timeline?**

- Verify tasks have start date or due date set
- Check if filters are hiding the tasks
- Ensure correct project is selected in dropdown
- Try expanding collapsed parent tasks

**Can't drag task bars?**

- Ensure you're clicking on the bar body (not empty space)
- Check that you're not clicking on text labels
- For resizing, hover over left/right edges until handles appear
- Try clicking the bar to open details, then manually edit dates

**Timeline looks empty?**

- Most tasks may be outside the visible date range
- Use scroll bar at bottom to navigate to different time periods
- Try Month zoom level to see wider date range
- Check that tasks have dates assigned (no dates = appear at today)

**Hierarchy not updating after drag?**

- Drop must occur between valid task positions
- Cannot drop parent onto own descendants
- Subtask parent updates based on drop position relative to other tasks
- Try using context menu "Make subtask" or "Promote to parent" instead

**Date changes not saving?**

- Ensure you release mouse button to complete drag operation
- Check Developer Console (Ctrl+Shift+I) for errors
- Try editing dates via Task Details panel instead
- Verify markdown sync isn't creating conflicts (see MARKDOWN_SYNC.md)

**Panel split not saving?**

- Split width saves to browser localStorage
- If using Obsidian on multiple devices, each has separate preference
- Try clearing localStorage if preference gets stuck
- Default is 300px for task list panel

**Performance issues with large projects?**

- Use filters to reduce visible tasks
- Collapse completed parent tasks
- Switch to Week or Month zoom for fewer timeline cells
- Consider archiving old completed tasks
