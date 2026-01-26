---
title: FAQ
date:
  created: 2026-01-14
  updated: 2026-01-26
readtime: 1
---

# Frequently Asked Questions

## Data Structure

??? question "Where are Tasks stored?"
    Tasks are stored in `.obsidian/plugins/obsidian-project-planner/data.json`. See the [Data Structure Reference](../features/data-structure.md) for complete details on data organization, schema, and storage formats.

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
    Not currently - all projects display. Hide/show feature planned for v0.8.0.

??? question "How often do metrics update?"
    Automatically whenever tasks change. Manual refresh also available.

??? question "Can I export Dashboard data?"
    Currently only via screenshot. Export features planned for v1.0.0.

??? question "What's the max number of projects Dashboard can handle?"
    No hard limit, but 20-30 projects recommended for best UX.

??? question "Do archived projects show on Dashboard?"
    Yes, if project exists in settings it appears. Delete to remove from Dashboard.

??? question "Can I customize which metrics show?"
    Not yet - metric customization planned for v0.7.0.

---

## Grid View

??? question "Can I reorder columns?"
    Not currently - column order is fixed.

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

!!! info "Coming Soon"
    Board view FAQs will be added in a future update.

---

## Dependency Graph

??? question "What's the difference between FS, SS, FF, and SF?"
    FS = finish-to-start (most common), SS = start together, FF = finish together, SF = rare handoff scenario.

??? question "Can I create a dependency to a task in another project?"
    Not currently - dependencies are project-scoped. Future versions may support cross-project links.

??? question "How do I find the critical path?"
    Not yet automated. Manually trace longest dependency chain. Auto-detection coming in v0.7.0.

??? question "What happens if I create a circular dependency?"
    Plugin should prevent this (A → B → A). If one exists, remove via Task Detail panel.

??? question "Can I print the dependency graph?"
    Currently only via screenshot. Export/print features planned for v1.0.0.

??? question "Why are some dependencies not showing?"
    Check dependency types are defined correctly in task data. Refresh view or check console for errors.

??? question "How many tasks can the graph handle?"
    Tested up to 200 tasks. Performance degrades beyond that. Use filters (future) for larger projects.

??? question "Can I change the graph layout?"
    Yes, in Settings → Project Planner → Graph Layout Algorithm. Choose hierarchical or force-directed.

??? question "Do subtasks show in the graph?"
    Not currently - only top-level tasks. Subtask visualization planned for future release.

??? question "Can I export the graph as an image?"
    Not yet - currently screenshot only. PNG/SVG export planned for v1.0.0.

---

## Timeline View

!!! info "Coming Soon"
    Timeline view FAQs will be added in a future update.