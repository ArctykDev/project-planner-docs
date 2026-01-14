---
title: ProjectPlanner.md
date:
  created: 2026-01-07
  updated: 2026-01-14
---

# ProjectPlanner.md

**Project Planner** is a comprehensive project management plugin for [Obsidian](https://obsidian.md) inspired by Microsoft Planner, designed to help you organize and track tasks directly within your vault.

It offers multiple specialized views including [Grid](views/grid-view.md) (hierarchical task tables), [Board](views/board-view.md) (Kanban-style workflow), [Gantt](views/timeline-view.md) (timeline visualization), [Dashboard](views/dashboard-view.md) (analytics and KPIs), and [Dependency Graph](views/dependency-graph-view.md) (task relationships), giving you flexibility to visualize your projects in the way that works best for you.

With bidirectional [markdown sync](features/markdown-sync.md), tasks can be managed both through the plugin's rich UI and as standard markdown files with YAML frontmatter, enabling seamless integration with your existing notes, version control workflows, and other Obsidian plugins like Dataview or Templater.

Whether you're managing software development sprints, planning content calendars, or organizing personal projects, Project Planner brings enterprise-grade task management to your local-first knowledge base.

---

# Features

## Views

<div class="grid cards" markdown>

- :material-view-dashboard: **Dashboard** <hr> <p>Analytics overview displaying KPI cards (total tasks, completion rates, blocked items, overdue tasks) with clickable metrics to filter and view specific task subsets, plus project metadata.</p><p>[:octicons-arrow-right-24: View](views/dashboard-view.md)</p>
- :material-view-grid: **Grid View** <hr> <p>Hierarchical table displaying all tasks with columns for status, priority, dates, and dependencies, supporting parent-child relationships and drag-and-drop reordering.</p><p>[:octicons-arrow-right-24: View](views/grid-view.md)</p>
- :material-card-multiple: **Board View** <hr> <p>Kanban-style board organizing tasks into customizable buckets (columns) with drag-and-drop functionality for visual workflow management.</p><p>[:octicons-arrow-right-24: View](views/board-view.md)</p>
- :material-chart-gantt: **Timeline** <hr> <p>Timeline visualization showing tasks plotted across a calendar with start/due dates, providing a chronological overview of project schedules.</p><p>[:octicons-arrow-right-24: View](views/timeline-view.md)</p>

</div>

## Integration

<div class="grid cards" markdown>

- :material-language-markdown: **Markdown Sync** <hr> <p>Bidirectional synchronization between Project Planner internal JSON data storage and markdown notes in your vault.</p><p>[:octicons-arrow-right-24: View](features/markdown-sync.md)</p>
- :material-vector-link: **URI Linking** <hr> <p>Create deep links to specific tasks in your Project Planner from anywhere in Obsidian. Reference tasks from meeting notes, daily logs, or any other page in your vault.</p><p>[:octicons-arrow-right-24: View](features/uri-linking.md)</p>

</div>
