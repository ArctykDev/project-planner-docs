---
title: Dependency Graph View
date:
  created: 2026-01-14
readtime: 7
---

# Dependency Graph View Guide

The Dependency Graph View provides a visual network diagram of task relationships and dependencies, helping you understand task sequences, identify critical paths, and manage complex project workflows.

## Overview

Dependency Graph View visualizes task relationships as an interactive network:

- **Node-Based Layout** - Each task is a node in the graph
- **Dependency Links** - Lines show relationships between tasks
- **Dependency Types** - FS, SS, FF, SF relationships visualized
- **Interactive Navigation** - Click nodes to view/edit tasks
- **Zoom and Pan** - Navigate large dependency networks
- **Real-Time Updates** - Graph updates as dependencies change

## Opening Dependency Graph View

**From Ribbon:**

- Click the network/graph icon in the left sidebar

**From Command Palette:**

- Press `Ctrl/Cmd + P`
- Type "Open Dependency Graph"
- Press Enter

**From Settings:**

- Set as default view in Settings → Project Planner → Default View

**From Other Views:**

- Click "Graph" button in header bar (if available)

## Interface Elements

### Header Bar

Located at the top of the graph view:

- **View Buttons** - Quick access to Grid, Board, Timeline, Dashboard views
- **Project Selector** - Switch between projects
- **Zoom Controls** - Zoom in/out of graph
- **Fit View** - Auto-zoom to fit all nodes
- **Settings Link** - Quick access to plugin settings

### Graph Canvas

Main visualization area:

- **Task Nodes** - Circular or rectangular nodes representing tasks
- **Dependency Edges** - Lines connecting dependent tasks
- **Node Labels** - Task titles displayed on/near nodes
- **Color Coding** - Status-based node colors
- **Arrows** - Direction indicators showing dependency flow

### Legend Panel

Shows graph element meanings:

- **Node Colors** - Status color indicators (Not Started, In Progress, Completed)
- **Edge Types** - Different line styles for dependency types
- **Icons** - Special indicators (blocked, critical path, etc.)

### Details Panel (Optional)

Side panel for selected node:

- **Task Information** - Title, description, status, priority
- **Dependencies** - List of predecessors and successors
- **Quick Actions** - Edit, add dependency, remove
- **Metadata** - Dates, tags, assignees

## Graph Visualization

### Task Nodes

**Node Appearance:**

- **Shape**: Circular or rectangular based on settings
- **Color**: Matches task status color from settings
- **Size**: Can vary by priority or task complexity (future)
- **Border**: Highlighted when selected or hovered
- **Label**: Task title (truncated if too long)

**Node States:**

- **Not Started**: Gray or default color
- **In Progress**: Blue or yellow
- **Completed**: Green with checkmark
- **Blocked**: Red border or special indicator
- **Selected**: Bold border, highlighted

**Visual Indicators:**

- **Priority**: Icon or badge on node (High/Medium/Low)
- **Due Date**: Calendar icon if date set
- **Subtasks**: Smaller connected nodes (future)
- **Critical Path**: Special highlighting (future)

### Dependency Edges

**Edge Appearance:**

- **Line Style**: Solid, dashed, or dotted based on type
- **Color**: Can match predecessor or successor status
- **Thickness**: Indicates dependency strength (future)
- **Arrow**: Shows direction of dependency
- **Label**: Shows dependency type (FS, SS, FF, SF)

**Edge Types Visualization:**

- **FS (Finish-to-Start)**: Standard arrow from finish to start
- **SS (Start-to-Start)**: Arrow from start to start
- **FF (Finish-to-Finish)**: Arrow from finish to finish
- **SF (Start-to-Finish)**: Arrow from start to finish

### Layout Algorithms

**Hierarchical Layout:**

- Tasks arranged in levels based on dependency depth
- Top-down or left-right orientation
- Clear visual hierarchy
- Good for waterfall-style projects

**Force-Directed Layout:**

- Nodes repel each other, edges attract connected nodes
- Organic, balanced appearance
- Good for complex interconnected tasks
- Can be harder to follow specific paths

**Manual Layout:**

- Drag nodes to custom positions (future)
- Save layout preferences
- Override automatic positioning

## Task Relationships

### Dependency Types

**Finish-to-Start (FS):**

- Most common dependency type
- Task B starts when Task A finishes
- Example: "Design wireframes" → "Develop UI"
- Visualization: Arrow from A's end to B's start

**Start-to-Start (SS):**

- Tasks start at the same time
- Task B starts when Task A starts
- Example: "Develop backend" ↔ "Develop frontend"
- Visualization: Arrow from A's start to B's start

**Finish-to-Finish (FF):**

- Tasks finish at the same time
- Task B finishes when Task A finishes
- Example: "Testing" → "Documentation" (both complete together)
- Visualization: Arrow from A's end to B's end

**Start-to-Finish (SF):**

- Rare dependency type
- Task B finishes when Task A starts
- Example: "Night shift" → "Day shift" handoff
- Visualization: Arrow from A's start to B's end

### Managing Dependencies

**Add Dependency:**

1. Click source task node
2. Click "Add Dependency" button
3. Select target task
4. Choose dependency type (FS/SS/FF/SF)
5. Graph updates automatically

**Remove Dependency:**

1. Click dependency edge (line)
2. Press Delete or click "Remove" button
3. Confirm removal if prompted
4. Graph updates automatically

**Edit Dependency:**

1. Click dependency edge
2. Change type in details panel
3. Update lag time if applicable (future)
4. Changes reflect immediately

## Navigation

### Zoom and Pan

**Mouse/Trackpad:**

- **Scroll wheel**: Zoom in/out
- **Click and drag**: Pan around graph
- **Pinch gesture**: Zoom on trackpad
- **Double-click node**: Center on node

**Keyboard:**

- **+/-**: Zoom in/out
- **Arrow keys**: Pan in direction
- **Space + drag**: Pan mode
- **Ctrl/Cmd + 0**: Reset zoom to 100%

**Toolbar Controls:**

- **Zoom In button**: Increase zoom level
- **Zoom Out button**: Decrease zoom level
- **Fit View button**: Auto-zoom to show all nodes
- **Reset button**: Return to default view

### Node Interaction

**Click Node:**

- Selects node (highlights)
- Shows task details in panel
- Highlights connected dependencies

**Double-Click Node:**

- Opens Task Detail view
- Edit task properties
- Manage dependencies in detail

**Right-Click Node (future):**

- Context menu with quick actions
- Add dependency, edit, delete
- Mark complete, change status

**Hover Node:**

- Shows tooltip with task info
- Highlights immediate dependencies
- Preview without selecting

### Path Tracing

**Follow Dependencies:**

1. Click starting task node
2. Connected dependencies highlight
3. Follow arrows to see sequence
4. Click next node to continue

**Critical Path (future):**

- Automatically highlights longest path
- Shows tasks that can't be delayed
- Useful for timeline planning
- Color-coded differently

## Settings

### Graph Display Settings

Access in Settings → Project Planner:

**Layout Algorithm:**

- Hierarchical (top-down or left-right)
- Force-directed (organic layout)
- Manual (drag to position)
- Circular (future)

**Node Appearance:**

- Shape: Circle, Rectangle, Rounded Rectangle
- Size: Small, Medium, Large
- Label position: Inside, Below, Above
- Show icons: Priority, Due Date, Status

**Edge Appearance:**

- Show dependency type labels
- Edge color: By status, by type, neutral
- Line style: Solid, Dashed, Dotted
- Arrow size: Small, Medium, Large

**Colors:**

- Use status colors from main settings
- Custom critical path color (future)
- Highlight color for selection
- Background color/theme

### Graph Behavior

**Interaction:**

- Auto-center on selection
- Animate transitions
- Smooth zoom/pan
- Tooltip delay time

**Performance:**

- Max nodes to display (for large projects)
- Simplify edges beyond threshold
- Render quality (high/medium/low)
- Hardware acceleration (future)

## Integration with Other Views

### Grid View

- **Dependency Column**: Shows predecessors/successors
- **Edit Dependencies**: Use Grid to add/remove
- **Graph Navigation**: Click "Graph" to visualize
- **Sync**: Changes in Grid update Graph immediately

### Board View

- **Workflow Visualization**: See how buckets relate
- **Sequential Tasks**: FS dependencies common in Board
- **Status Updates**: Moving cards updates node colors
- **Limited View**: Board doesn't show all dependencies

### Timeline (Gantt) View

- **Date Scheduling**: Dependencies affect Timeline dates
- **Critical Path**: Timeline shows impact on schedule
- **Lag Time**: Timeline accounts for dependency lag
- **Complementary**: Use Graph for structure, Timeline for dates

### Task Detail Panel

- **Dependency Management**: Add/remove via detail panel
- **Type Selection**: Choose FS/SS/FF/SF in dropdown
- **Preview**: See dependency list before viewing graph
- **Quick Edit**: Modify without opening full Graph view

## Use Cases

### Project Planning

**Map Workflow:**

1. Create all tasks in Grid view
2. Open Dependency Graph
3. Add dependencies to establish sequence
4. Verify no circular dependencies
5. Identify critical path

**Parallel Workflows:**

- Use SS dependencies for parallel work
- Visualize concurrent tasks
- Plan resource allocation
- Optimize timeline

### Risk Management

**Identify Bottlenecks:**

- Tasks with many dependencies are risks
- Single points of failure visible
- Plan mitigation strategies
- Create alternative paths

**Critical Path Analysis:**

- Longest dependency chain is critical
- Delays on critical path affect timeline
- Focus resources on critical tasks
- Monitor closely for issues

### Team Communication

**Visual Handoffs:**

- Show dependencies to team members
- Clarify who waits on whom
- Reduce coordination overhead
- Document workflow visually

**Stakeholder Updates:**

- Screenshot graph for presentations
- Show project complexity visually
- Explain task relationships
- Justify timeline estimates

### Workflow Optimization

**Reduce Dependencies:**

- Identify unnecessary dependencies
- Simplify workflow where possible
- Enable more parallelization
- Speed up project completion

**Reorder Tasks:**

- Find tasks that can start earlier
- Reduce critical path length
- Optimize resource utilization
- Improve project efficiency

## Tips and Best Practices

### Graph Organization

**Keep It Simple:**

- Don't create unnecessary dependencies
- Only link truly dependent tasks
- Avoid circular dependencies (will cause errors)
- Use subtasks instead of over-linking

**Logical Grouping:**

- Group related tasks in Grid view
- Dependencies will cluster naturally
- Use parent tasks to organize
- Clear project phases visible

**Use Appropriate Types:**

- FS (Finish-to-Start) for sequential work
- SS (Start-to-Start) for parallel kickoffs
- FF (Finish-to-Finish) for synchronized endings
- SF (Start-to-Finish) rarely needed

### Performance

**Large Projects:**

- Limit dependencies to essential relationships
- Use filters to show subset of tasks (future)
- Split into sub-projects if too complex
- Consider performance settings

**Graph Rendering:**

- Close graph when not actively using
- Reduce node/edge details for many tasks
- Lower render quality if slow
- Avoid constant zooming (caches layout)

### Workflow

**Start with Grid:**

1. Create all tasks in Grid view first
2. Organize into logical structure
3. Then open Graph to add dependencies
4. Verify graph makes sense
5. Return to Grid for detailed work

**Regular Review:**

- Weekly graph review to verify dependencies
- Remove outdated relationships
- Add new dependencies as project evolves
- Keep graph current with reality

## Troubleshooting

### Graph Not Displaying

**Blank Graph View:**

1. Check if project has tasks
2. Verify tasks have valid IDs
3. Refresh view (close and reopen)
4. Check browser console for errors

**No Nodes Visible:**

- Use "Fit View" button to auto-zoom
- Check if accidentally zoomed out too far
- Verify project selector shows correct project
- Ensure tasks aren't filtered out

### Dependency Issues

**Can't Add Dependency:**

- Check for circular dependency (A → B → A)
- Verify both tasks exist in same project
- Ensure task IDs are valid
- Try adding via Task Detail panel instead

**Dependency Not Showing:**

1. Refresh graph view
2. Check dependency exists in task data
3. Verify edge color isn't matching background
4. Look in Task Detail panel to confirm

**Wrong Dependency Type:**

- Click edge to select
- Edit type in details panel
- Verify type label shows correctly
- Re-add if needed

### Performance Problems

**Slow Rendering:**

- Reduce number of visible tasks (filter)
- Lower render quality in settings
- Use simpler layout algorithm
- Close other resource-intensive views

**Graph Freezes:**

- Too many nodes (>200) may slow down
- Circular dependencies can cause issues
- Reload plugin if unresponsive
- Check for infinite loops in dependencies

### Layout Issues

**Overlapping Nodes:**

- Switch layout algorithm
- Manually adjust node positions (future)
- Increase canvas size (zoom out)
- Reduce node size in settings

**Edges Crossing:**

- Use hierarchical layout for cleaner lines
- Reorder tasks in Grid to improve graph
- Accept some crossing (complex graphs)
- Focus on specific subgraph

## Advanced Features

### Data Export

**Current:**

- Screenshot graph for documentation
- Export task dependencies via Grid view
- Access data.json for raw dependency data

**Future:**

- Export as image (PNG, SVG)
- Export as DOT file (Graphviz)
- Print-optimized layouts
- Share interactive graph (HTML)

### Filtering and Search

**Future Enhancements:**

- Filter by status, priority, tags
- Show only critical path
- Highlight specific dependency types
- Search for task by name
- Show only neighbors of selected node

### Collaboration

**Current:**

- Share screenshots with team
- Document dependencies in task notes
- Use Graph for planning meetings

**Future:**

- Real-time collaborative editing
- Comment on dependencies
- Assign tasks from graph view
- Integration with team tools

### Analytics

**Future Metrics:**

- Dependency density (avg deps per task)
- Graph complexity score
- Critical path length
- Bottleneck identification
- Circular dependency detection

## Keyboard Shortcuts

### Navigation

- **Arrow Keys**: Pan graph in direction
- **+/-**: Zoom in/out
- **Ctrl/Cmd + 0**: Reset zoom
- **Space + Drag**: Pan mode
- **Escape**: Deselect node

### Node Selection

- **Click**: Select node
- **Shift + Click**: Multi-select (future)
- **Ctrl/Cmd + A**: Select all (future)
- **Tab**: Cycle through nodes (future)

### Actions

- **Delete**: Remove selected dependency (when edge selected)
- **Enter**: Edit selected task (when node selected)
- **Ctrl/Cmd + F**: Find task (future)
- **Ctrl/Cmd + Z**: Undo layout change (future)

_Note: Enhanced keyboard navigation planned for future versions_

## Future Enhancements

### Planned Features

**v0.7.0 - Enhanced Visualization:**

- Critical path highlighting
- Dependency lag time visualization
- Task grouping/clustering
- Mini-map for large graphs

**v0.8.0 - Interactivity:**

- Drag to create dependencies
- Manual node positioning with save
- Context menus on nodes/edges
- Inline task editing

**v0.9.0 - Advanced Features:**

- Multiple dependency paths visualization
- What-if scenario planning
- Resource allocation view
- Gantt integration (click node → show in timeline)

**v1.0.0 - Professional Tools:**

- Export to Graphviz, Mermaid, PlantUML
- Import dependencies from MS Project, Jira
- Critical path method (CPM) calculations
- PERT chart generation

### Community Requests

- Swimlanes for team members
- Milestone nodes (different shape)
- Progress indicators on nodes
- Burndown from dependency completion
- Integration with external PM tools

## Frequently Asked Questions

**Q: What's the difference between FS, SS, FF, and SF?**
A: FS = finish-to-start (most common), SS = start together, FF = finish together, SF = rare handoff scenario.

**Q: Can I create a dependency to a task in another project?**
A: Not currently - dependencies are project-scoped. Future versions may support cross-project links.

**Q: How do I find the critical path?**
A: Not yet automated. Manually trace longest dependency chain. Auto-detection coming in v0.7.0.

**Q: What happens if I create a circular dependency?**
A: Plugin should prevent this (A → B → A). If one exists, remove via Task Detail panel.

**Q: Can I print the dependency graph?**
A: Currently only via screenshot. Export/print features planned for v1.0.0.

**Q: Why are some dependencies not showing?**
A: Check dependency types are defined correctly in task data. Refresh view or check console for errors.

**Q: How many tasks can the graph handle?**
A: Tested up to 200 tasks. Performance degrades beyond that. Use filters (future) for larger projects.

**Q: Can I change the graph layout?**
A: Yes, in Settings → Project Planner → Graph Layout Algorithm. Choose hierarchical or force-directed.

**Q: Do subtasks show in the graph?**
A: Not currently - only top-level tasks. Subtask visualization planned for future release.

**Q: Can I export the graph as an image?**
A: Not yet - currently screenshot only. PNG/SVG export planned for v1.0.0.

## Best Practices Summary

### ✅ Do This:

- Use Graph for planning and understanding structure
- Keep dependencies to essential relationships only
- Use FS (Finish-to-Start) for most dependencies
- Regularly review and clean up outdated dependencies
- Use Grid view for detailed dependency management
- Take screenshots for documentation/presentations

### ❌ Avoid This:

- Don't create circular dependencies (A → B → A)
- Don't over-link every task (creates clutter)
- Don't use SF (Start-to-Finish) unless truly needed
- Don't rely solely on Graph for task work (use Grid)
- Don't create dependencies across projects
- Don't ignore performance issues with large graphs

---

**Need Help?**

- Check [Home](../index.md) for plugin overview
- Report bugs on [GitHub Issues](https://github.com/ArctykDev/project-planner-docs/issues)

**Related Documentation:**

- [Grid View Guide](grid-view.md) - Detailed task management
- [Board View Guide](board-view.md) - Kanban workflows
- [Timeline View Guide](timeline-view.md) - Gantt charts
- [Grid View Guide](task-details-view.md) - Detailed task management
