---
name: restructure-journey
description: Reshape an existing Orchetta journey by renaming, reordering, adding, moving, merging, splitting or removing stages and steps, while keeping what is attached to them. Use when asked to tidy, reorganise, simplify or correct a journey's structure.
---

# Restructure a journey

## Instructions

1. `get_journey` and lay out the current structure as a numbered list of stages and steps, with how many records sit on each step.
2. Propose the new structure as a before → after list. Mark every operation: rename, move, add, merge or remove.
3. Explain what happens to attached records:
   - Moving a stage (`update_stage` with `position`) or a step (`update_step` with `position` or `stage_id`) keeps everything attached.
   - Merging two steps means re-attaching the records of the one going away to the one staying (`attach_resource_to_step`), then removing the empty step.
   - Removing a step or stage takes its records off this journey; the records themselves stay in the workspace.
4. Get a yes on the whole plan. Then get a separate yes for each `remove_step` or `remove_stage`, naming it.
5. Apply in an order that never strands a record: add new stages and steps first (`add_stage`, `add_step`), then move (`update_stage`, `update_step`), then re-attach, and remove last.
6. `get_journey` again and confirm the result matches the agreed plan. Report any difference.
7. Journey-level fields (name, description, status, priority, scores, assignee) change with `update_journey`. Only touch the fields that were asked about.
