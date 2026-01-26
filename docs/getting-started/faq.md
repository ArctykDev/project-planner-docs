---
title: FAQ
date:
  created: 2026-01-14
  updated: 2026-01-26
readtime: 1
---

# Frequently Asked Questions

This section is a work-in-progress.

## Data Structure¶

**Q: Where are Tasks stored?** 
A: Tasks are stored in `.obsidian/plugins/obsidian-project-planner/data.json`. See the [Data Structure Reference](../features/data-structure.md) for complete details on data organization, schema, and storage formats.

---

## Dashboard view

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


---

## Grid view

**Q: Can I reorder columns?**
A: Not currently - column order is fixed.
**Q: How do I export grid data?**
A: Use markdown sync to create individual task files, or access data.json directly.
**Q: Can I have multiple parents for one task?**
A: No - each task has 0 or 1 parent only.
**Q: What happens to children when I delete a parent?**
A: Children are promoted to top-level tasks (not deleted).
**Q: Can I move tasks between projects?**
A: Not directly in UI - requires manual data.json editing.
**Q: How many tasks can grid view handle?**
A: Hundreds comfortably, thousands with performance considerations.
**Q: Do subtasks count toward parent completion?**
A: Not automatically - parent status is independent.
**Q: Can I print the grid view?**
A: Use browser print (Ctrl+P) or export to markdown first.

---

## Board view

Coming soon.

## Dependency graph

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

---

## Timeline view

Coming soon.