---
title: Grid View
date:
  created: 2026-01-14
  updated: 2026-02-02
readtime: 9
---

# Grid View Guide

The Grid View is the primary task management interface in Project Planner, providing a powerful hierarchical table for organizing and managing your tasks.

![Hierarchical spreadsheet interface displaying tasks in rows with columns for Title, Status, Priority, Bucket, Tags, Deps, Start Date, Due Date, Created, and Modified. Tasks are organized with parent-child relationships shown through expandable tree structure with arrow icons](../assets/version-0-6-7-grid-view.png)

## Overview

Grid View presents your tasks in a spreadsheet-like interface with support for:

- **Hierarchical organization** - Create parent tasks with nested subtasks
- **Multiple columns** - View and edit all task properties at once
- **Inline editing** - Quick updates without opening detail panels
- **Filtering and sorting** - Focus on what matters
- **Drag-and-drop reordering** - Organize tasks your way


## How to navigate the Grid view

### Using the top header bar

Located at the top of the grid view:

![Navigation bar containing project selector dropdown on the left, four view toggle buttons for Board, Timeline, Dashboard, and Graph in the center, plus Add Task button and settings icon on the right](../assets/0-6-10-grid-view-header-bar.png){ width="400" .center}

- **Project Selector** - Dropdown to switch between projects
- **View Buttons** - Quick access to Board, Timeline, Dashboard, and Graph views
- **Add Task Button** - Create new top-level tasks
- **Filter Indicators** - Shows active filters (status, priority, tags)

### How to customize columns

- Click the column headers to sort acending/decending order (▲/▼)
- Hover over the column header edge to adjust the width of the column (↔)
- Hover/click on the colum header to drag the column 

To show or hide columns, click on the "Columns" button:

    ![Columns button highlighted in purple with dropdown menu showing checkboxes for Title, Status, Priority, Bucket, Tags, Deps, Start Date, Due Date, Created, and Modified columns, all currently checked](../assets/0-6-10-columns.png)

### Task Rows

Each row represents a task with:

- **Expand/Collapse Icon** - For tasks with children (►/▼)
- **Checkbox** - Mark tasks as complete
- **Editable Cells** - Click to edit values inline
- **Action Buttons** - Delete, add child, open details


## How to create a task

### To add a new Top-Level task

1. Click the **"+ Add Task"** button in the header

    ![Purple button labeled Add Task with plus icon located in the header toolbar between view switcher buttons and settings icon](../assets/0-6-10-add-new-button.png){ width="200" .center}

2. Enter task title
3. Press Enter or click outside to save

**Or:**

- Right-click anywhere the task row, or click on the "..." button
- Select "Add new task above"

    ![Context menu displaying options including Add new task above option at the top, followed by other task management options in a white dropdown menu](../assets/0-6-10-add-new-task-above.png){ width="300" .center}

### How to add a new subtask

**Method 1 - Inline:**

1. Hover over a task
2. Click the **"..."** icon (appears on hover)
3. Select "Make subtask" from the context menu

![Context menu opened from three-dot button showing Make subtask option among other task actions in a vertical list format](../assets/0-6-12-make-subtask-menu.png){ width="300" .center}

**Method 2 - Drag and Drop:**

1. Create a new task
2. Drag it onto the parent task
3. It becomes a child automatically

![Task being dragged with mouse cursor showing the task moving toward another task to create parent-child relationship, with visual indicator showing drop zone](../assets/0-6-12-drag-subtask.png){ width="350" .center}

## How do I edit tasks?

You can edit tasks in-line or through the Task Details panel. 

### To edit in-line:

- Click any cell to edit its value

    ![Task cell in edit mode showing text input field with cursor active, allowing direct editing of task properties within the grid without opening separate panel](../assets/0-6-10-inline-edit.png){ width="300" .center}

- Make changes
- Click outside or press Enter to save
- Press Escape to cancel

### To edit using the Task Details panel

The Task Details panel provides a way to update all task options in one view.

1. Right-click task row or click the task menu button
2. Select "Open details"

    ![Context menu showing Open details option among other task actions, accessed by right-clicking on a task row or clicking the menu button](../assets/0-6-10-open-task-details.png){ width="350" .center}

3. Detail panel opens on the right
4. Edit description, subtasks, links, dependencies
5. Changes save automatically


## How are tasks stored?

For detailed information about how tasks and projects are stored, see the [Data Structure Reference](../features/data-structure.md).


---

## Support 

**Need Help?**

- Read the [FAQ](../getting-started/faq.md)
- Check [Home](../index.md) for plugin overview
- Report bugs on [GitHub Issues](https://github.com/ArctykDev/project-planner-docs/issues)
