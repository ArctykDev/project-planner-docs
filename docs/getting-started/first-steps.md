---
title: First Steps
date:
  created: 2026-01-15
  updated: 2026-01-15
---

# First Steps

Welcome to Project Planner! This guide will walk you through the essential steps to get started with managing your projects in Obsidian.

## Opening Project Planner

After [installing the plugin](installation.md), you can access Project Planner in several ways:

- **Ribbon Icon**: Click the Project Planner icon in the left sidebar
- **Command Palette**: Press `Ctrl/Cmd + P` and search for "Project Planner"
- **View Menu**: Navigate to the view you want from the command palette

!!! tip
You can customize which ribbon icons appear in **Settings** → **Project Planner** → **Interface**.

## Understanding the Interface

Project Planner provides multiple specialized views to help you visualize and manage your tasks:

- **[Dashboard View](../views/dashboard-view.md)**: Analytics and KPIs for tracking project progress
- **[Grid View](../views/grid-view.md)**: Hierarchical task tables for detailed project organization
- **[Board View](../views/board-view.md)**: Kanban-style workflow for visual task management
- **[Timeline View](../views/timeline-view.md)**: Gantt chart visualization for time-based planning
- **[Dependency Graph View](../views/dependency-graph-view.md)**: Visual representation of task relationships
- **[Task Details View](../views/task-details-view.md)**: Detailed information and editing for individual tasks

Each view offers unique ways to interact with your projects. You can switch between views at any time to find the perspective that works best for your current task.

## Creating Your First Project

1. Open Project Planner using one of the methods above
2. Click the **New Project** button or use the command palette
3. Enter a project name (e.g., "Website Redesign" or "Blog Content Calendar")
4. Choose a location in your vault to store the project file
5. Click **Create**

!!! note
Projects are stored as markdown files in your vault, making them fully compatible with version control and other Obsidian plugins.

## Adding Your First Tasks

Once you have a project created:

1. Click the **Add Task** button in your preferred view
2. Enter a task name (e.g., "Design homepage mockup")
3. (Optional) Add additional details:
   - **Due Date**: Click the date field to set a deadline
   - **Priority**: Set task priority (High, Medium, Low)
   - **Status**: Choose from To Do, In Progress, Done, etc.
   - **Tags**: Add tags for organization and filtering
4. Press **Enter** or click **Save** to create the task

!!! tip
Use keyboard shortcuts to quickly add tasks: `Ctrl/Cmd + Enter` to create a new task in most views.

## Exploring Different Views

### Grid View

The Grid View displays tasks in a hierarchical table format, perfect for:

- Breaking down large projects into subtasks
- Viewing all task details at once
- Quickly editing multiple tasks

[Learn more about Grid View →](../views/grid-view.md)

### Board View

The Board View uses a Kanban-style layout, ideal for:

- Visualizing workflow stages
- Drag-and-drop task management
- Tracking task status at a glance

[Learn more about Board View →](../views/board-view.md)

### Timeline View

The Timeline View shows tasks on a Gantt chart, useful for:

- Planning time-based projects
- Identifying scheduling conflicts
- Visualizing project duration

[Learn more about Timeline View →](../views/timeline-view.md)

## Basic Task Management

### Updating Task Status

- **Grid View**: Click directly on the status cell
- **Board View**: Drag tasks between columns
- **Task Details**: Use the status dropdown

### Setting Due Dates

Click on any date field to open the date picker. You can:

- Select a specific date from the calendar
- Type a date in natural language (e.g., "tomorrow", "next Monday")
- Clear the date by clicking the clear button

### Adding Dependencies

Create task relationships to ensure proper sequencing:

1. Open the Task Details view for a task
2. Click **Add Dependency**
3. Select the task that must be completed first
4. Choose the dependency type (Finish-to-Start, Start-to-Start, etc.)

[Learn more about task dependencies →](../views/dependency-graph-view.md)

## Working with Markdown Sync

One of Project Planner's most powerful features is bidirectional markdown synchronization. This means:

- Tasks you create in Project Planner are automatically saved to markdown files
- Changes made to markdown files are reflected in Project Planner
- You can use YAML frontmatter to define task properties
- Works seamlessly with other Obsidian plugins and workflows

!!! example "Example Task in Markdown"

```markdown
---
status: in-progress
priority: high
due: 2026-01-20
tags: [development, urgent]
---

# Implement user authentication

Create a secure login system with OAuth support.
```

[Learn more about Markdown Sync →](../features/markdown-sync.md)

## Next Steps

Now that you understand the basics, explore more advanced features:

- **[Task Tagging](../features/daily-notes-tagging.md)**: Organize tasks with tags and integrate with Daily Notes
- **[URI Linking](../features/uri-linking.md)**: Create deep links to specific tasks and views
- **[Dashboard Analytics](../views/dashboard-view.md)**: Track project metrics and KPIs

!!! question "Need Help?"
If you encounter any issues or have questions, visit our [Troubleshooting guide](../troubleshooting.md) or join the discussion on [GitHub](https://github.com/ArctykDev/obsidian-project-planner/discussions).
