---
title: Dashboard View
date:
  created: 2026-01-14
readtime: 6
---

# Dashboard View Guide

The Dashboard View provides a high-level overview of all your projects and tasks, presenting key performance indicators (KPIs) and project summaries in an easy-to-digest visual format.

## Overview

Dashboard View serves as your command center for project monitoring:

- **Project Cards** - Visual cards for each project with metadata
- **KPI Metrics** - Task completion rates and statistics
- **Quick Navigation** - Click project cards to jump to Grid view
- **At-a-Glance Status** - See all projects in one view
- **Real-Time Updates** - Metrics update as tasks change

## Opening Dashboard View

**From Ribbon:**

- Click the layout-dashboard icon in the left sidebar

**From Command Palette:**

- Press `Ctrl/Cmd + P`
- Type "Open Dashboard"
- Press Enter

**From Settings:**

- Set as default view in Settings → Project Planner → Default View

**From Other Views:**

- Click "Dashboard" button in header bar

## Interface Elements

### Header Bar

Located at the top of the dashboard:

- **View Buttons** - Quick access to Grid, Board, Timeline, and Graph views
- **Refresh Button** - Manually refresh metrics (auto-updates on changes)
- **Settings Link** - Quick access to plugin settings

### Project Cards Section

Main area displaying project cards:

- **Card Grid** - Responsive layout adapts to window size
- **Project Headers** - Show project name prominently
- **Metadata Display** - Created date, last updated, task counts
- **Click to Navigate** - Cards are clickable to open project

### Metrics Section

Overview statistics across all projects:

- **Total Tasks** - Count of all tasks across projects
- **Completed Tasks** - Number of finished tasks
- **In Progress** - Tasks currently being worked on
- **Completion Rate** - Percentage of tasks completed
- **Overdue Tasks** - Tasks past their due date (if applicable)

## Project Cards

### Card Layout

Each project card displays:

**Header:**

- Project name (large, prominent text)
- Project icon or color indicator (if configured)

**Metadata:**

- **Created**: Date project was created
- **Last Updated**: Most recent task modification
- **Task Count**: Total number of tasks in project

**Statistics:**

- **Completed**: Number of completed tasks
- **In Progress**: Tasks currently being worked on
- **Not Started**: Tasks waiting to begin
- **Blocked**: Tasks that are blocked (if applicable)

**Visual Indicators:**

- Progress bar showing completion percentage
- Color-coded status indicators
- Badge showing task count

### Card Actions

**Click Anywhere on Card:**

- Opens the project in Grid view
- Switches active project automatically
- Maintains your current workspace tab settings

**Hover Effects:**

- Card highlights to indicate clickability
- Shows additional metadata (future feature)
- Displays quick actions (future feature)

## Metrics and KPIs

### Task Completion Metrics

**Completion Rate:**

- Percentage of all tasks marked as completed
- Calculated across all projects
- Updates in real-time as tasks change

**Task Distribution:**

- Breakdown by status (Not Started, In Progress, etc.)
- Shows workflow balance
- Helps identify bottlenecks

**Time-Based Metrics:**

- Tasks created this week/month (future)
- Tasks completed this week/month (future)
- Average task completion time (future)

### Project Health Indicators

**Activity Level:**

- Last updated timestamp shows recent activity
- Stale projects easily identified
- Encourages regular task updates

**Workload Balance:**

- See which projects have most tasks
- Identify overloaded projects
- Plan capacity accordingly

**Completion Trends:**

- Compare completion rates across projects
- Identify high/low performers
- Adjust priorities based on progress

## Navigation

### From Dashboard to Projects

**Open Project in Grid View:**

1. Click any project card
2. Grid view opens with that project active
3. Start managing tasks immediately

**Quick Switching:**

- Use project card clicks for fast navigation
- No need to use project dropdown
- Maintains context between views

### From Dashboard to Other Views

**Access via Header:**

- Click "Grid" to see all tasks in table format
- Click "Board" for Kanban-style view
- Click "Timeline" for Gantt chart
- Click "Graph" for dependency visualization

**View Persistence:**

- Selected project carries to other views
- Dashboard remembers scroll position
- Returns to same state when reopening

## Settings

### Dashboard Configuration

Access in Settings → Project Planner:

**Default View:**

- Set Dashboard as the startup view
- Opens automatically when plugin loads

**Open Views in New Tab:**

- Controls whether dashboard opens in new tab
- Applies when clicking project cards

**Metrics Display:**

- Future: Toggle specific metrics on/off
- Future: Customize KPI calculations
- Future: Set metric thresholds

### Project Display

**Project Order:**

- Currently: Alphabetical by name
- Future: Sort by last updated, creation date, task count
- Future: Pin favorite projects to top

**Card Styling:**

- Future: Choose compact or expanded card view
- Future: Show/hide specific metadata fields
- Future: Custom color themes per project

## Integration with Other Views

### Grid View

- **Navigation**: Click project card to open Grid
- **Sync**: Task changes in Grid update Dashboard metrics
- **Active Project**: Dashboard selection becomes active in Grid

### Board View

- **Metrics**: Board task counts contribute to Dashboard stats
- **Navigation**: Access Board for project from Grid after clicking card
- **Buckets**: Board bucket assignments don't affect Dashboard display

### Timeline (Gantt) View

- **Date Metrics**: Timeline tasks with dates affect metrics
- **Dependencies**: Dependency chains visible via Graph link
- **Scheduling**: Overdue calculations use Timeline dates

### Task Detail Panel

- **Editing**: Task changes update Dashboard in real-time
- **Status Changes**: Completion rate updates immediately
- **Metadata**: Updated timestamps reflect on cards

## Use Cases

### Morning Standup

**Quick Overview:**

1. Open Dashboard view
2. Scan project cards for activity
3. Identify stale projects needing attention
4. Click project to dive into details

**Status Check:**

- See completion progress at a glance
- Identify blocked tasks across projects
- Plan daily priorities based on metrics

### Weekly Review

**Progress Assessment:**

1. Review each project card
2. Compare completion rates
3. Identify lagging projects
4. Update stale projects

**Planning:**

- See workload distribution
- Balance task assignments
- Set priorities for next week

### Project Handoffs

**Share Status:**

- Dashboard provides snapshot for stakeholders
- Quick visual summary of all projects
- No need to explain individual tasks

**Documentation:**

- Screenshot dashboard for reports
- Show progress over time
- Demonstrate activity levels

### Multi-Project Management

**Portfolio View:**

- See all projects simultaneously
- Identify resource constraints
- Balance competing priorities
- Track overall team capacity

**Quick Switching:**

- Jump between projects rapidly
- No dropdown navigation needed
- Maintain context with visual cards

## Tips and Best Practices

### Organization

**Keep Projects Active:**

- Regular updates show on "Last Updated"
- Stale projects indicate need for review
- Archive or delete unused projects

**Meaningful Names:**

- Project names display prominently on cards
- Use clear, descriptive names
- Keep names concise for better layout

**Task Distribution:**

- Avoid massive projects (hundreds of tasks)
- Split large initiatives into sub-projects
- Better metrics with focused projects

### Workflow

**Start Your Day:**

1. Open Dashboard first
2. Quick scan of all projects
3. Click project needing attention
4. Work in Grid/Board/Timeline

**End Your Day:**

1. Return to Dashboard
2. Verify all projects updated
3. Check completion progress
4. Plan tomorrow's priorities

**Weekly Cadence:**

- Monday: Review Dashboard, set weekly goals
- Mid-week: Check progress via Dashboard
- Friday: Final Dashboard review, update metrics

### Performance

**Optimize Load Time:**

- Fewer projects load faster
- Archive completed projects
- Keep active project count reasonable (< 20)

**Metric Accuracy:**

- Regularly update task statuses
- Mark completed tasks promptly
- Keep due dates current

## Troubleshooting

### Dashboard Not Loading

**Blank Dashboard:**

1. Check if any projects exist
2. Create project in settings if needed
3. Refresh view (close and reopen)
4. Check console for errors

**Partial Data:**

- Some project cards missing
- Check data.json for corruption
- Verify all projects have valid IDs
- Restore from backup if needed

### Metrics Not Updating

**Stale Metrics:**

1. Click refresh button in header
2. Make task change to trigger update
3. Close and reopen Dashboard view
4. Check taskStore emit() is working

**Incorrect Counts:**

- Verify task statuses are set correctly
- Check for orphaned tasks in data.json
- Ensure completed flag syncs with status
- Validate tasksByProject structure

### Navigation Issues

**Can't Open Project:**

- Click directly on card area
- Ensure project has valid ID
- Check if project exists in settings
- Verify Grid view is available

**Wrong Project Opens:**

- Card click may have missed target
- Try clicking center of card
- Check activeProjectId in console
- Reload plugin if persists

### Display Problems

**Cards Overlapping:**

- Resize Obsidian window
- Zoom out (Ctrl/Cmd + -)
- Future: Responsive layout improvements

**Missing Metadata:**

- Project may lack timestamps
- Migration adds timestamps automatically
- Check data.json for created/lastUpdated fields

## Advanced Features

### Project Metadata

**Timestamps:**

```json
{
  "id": "project-id",
  "name": "Project Name",
  "createdDate": "2026-01-14T10:00:00Z",
  "lastUpdatedDate": "2026-01-14T15:30:00Z"
}
```

**Auto-Update:**

- `createdDate` set when project created
- `lastUpdatedDate` updates on task changes
- Displayed on Dashboard cards

### Custom Metrics

**Future Enhancements:**

- Custom KPI formulas
- Project-specific metrics
- Time-based trending
- Burndown charts
- Velocity tracking

### Data Export

**Current:**

- Screenshot Dashboard for reports
- Access data.json for raw metrics

**Future:**

- Export Dashboard to PDF
- Generate metric reports
- CSV export of project summaries
- Integration with external tools

## Keyboard Shortcuts

### Navigation

- **Arrow Keys**: Navigate between project cards (future)
- **Enter**: Open selected project (future)
- **Escape**: Close Dashboard and return to previous view

### Quick Actions

- **Ctrl/Cmd + R**: Refresh Dashboard metrics
- **Number Keys**: Quick-open project by position (future)
- **Tab**: Cycle through interactive elements

_Note: Enhanced keyboard navigation planned for future versions_

## Future Enhancements

### Planned Features

**v0.7.0 - KPI Expansion:**

- Custom metric definitions
- Trend charts and graphs
- Historical data tracking
- Comparison views

**v0.8.0 - Customization:**

- Drag-to-reorder project cards
- Custom card layouts
- Pin favorite projects
- Hide/show specific projects

**v0.9.0 - Advanced Analytics:**

- Task completion trends
- Velocity calculations
- Burndown/burnup charts
- Team capacity planning

**v1.0.0 - Polish:**

- Export to PDF/CSV
- Custom themes per project
- Widget system for custom metrics
- Integration with external analytics

## Frequently Asked Questions

**Q: How do I create a new project?**
A: Go to Settings → Project Planner → Click "Add project" button.

**Q: Can I reorder project cards?**
A: Not yet - currently alphabetical. Drag-to-reorder planned for v0.8.0.

**Q: How is completion rate calculated?**
A: (Completed tasks / Total tasks) × 100 across all projects.

**Q: Why isn't my project showing on Dashboard?**
A: Check that project exists in settings and has a valid ID and name.

**Q: Can I hide certain projects from Dashboard?**
A: Not currently - all projects display. Hide/show feature planned for v0.8.0.

**Q: How often do metrics update?**
A: Automatically whenever tasks change. Manual refresh also available.

**Q: Can I export Dashboard data?**
A: Currently only via screenshot. Export features planned for v1.0.0.

**Q: What's the max number of projects Dashboard can handle?**
A: No hard limit, but 20-30 projects recommended for best UX.

**Q: Do archived projects show on Dashboard?**
A: Yes, if project exists in settings it appears. Delete to remove from Dashboard.

**Q: Can I customize which metrics show?**
A: Not yet - metric customization planned for v0.7.0.

## Best Practices Summary

### ✅ Do This:

- Open Dashboard first each day for overview
- Click project cards for quick navigation
- Keep project names clear and concise
- Update tasks regularly to keep metrics accurate
- Use Dashboard for stakeholder updates
- Review weekly for project health checks

### ❌ Avoid This:

- Don't create too many projects (reduces clarity)
- Don't ignore stale projects (clutter Dashboard)
- Don't rely on Dashboard for detailed task work
- Don't skip updating task statuses (skews metrics)
- Don't screenshot with sensitive data visible

---

**Need Help?**

- Check [README.md](README.md) for plugin overview
- Read [TROUBLESHOOTING.md](troubleshooting.md) for common issues
- Report bugs on GitHub Issues

**Related Documentation:**

- [Grid View Guide](grid-view.md) - Detailed task management
- [Board View Guide](board-view.md) - Kanban workflows
- [Timeline View Guide](timeline-view.md) - Gantt charts
- [Dependency Graph Guide](dependency-view.md) - Task relationships
