---
name: add-insights
description: Turn research notes, interview transcripts, support tickets, survey answers or feedback into needs, pain points, gains, opportunities and solutions on the right steps of an Orchetta journey, without duplicates, and link them together. Use when given material to add to a journey, or asked to log a need, pain point, idea or fix.
---

# Add insights to a journey

## Instructions

1. `get_journey` for the target journey and `list_resource_kinds` for the kinds and fields this workspace uses (names, select options, score scales).
2. Read the material and pull out findings. Classify each finding as one kind:
   - **need**: what the customer is trying to get or feel
   - **pain point**: what goes wrong or gets in the way
   - **gain**: what goes well
   - **opportunity**: a chance to do better
   - **solution**: something built or planned in answer
   Keep the kinds straight: a complaint is a pain point, not a need.
3. Place each finding on the step where it happens. If no step fits, list it separately rather than forcing it onto one.
4. Check for duplicates. Compare against records already on that step (from `get_journey`) and `list_resources` for the kind. Where one already says the same thing, propose attaching or updating it instead.
5. Show the plan as a table: kind · name · one-line description · step · new or existing · source quote. Wait for a yes, or edits.
6. Create new records with `create_resource`, passing `step_ids` to place them in the same call. Put an existing record on another step with `attach_resource_to_step`.
7. Set priority, severity or scores with `update_resource` only where the material or the person gave a basis. Say which you left blank.
8. Link what belongs together with `link_resources`: a pain point to the solution or opportunity that answers it, a need to the opportunity it raises.
9. If the findings came from a particular persona, `apply_label` that profile to the new records.
10. Report counts by kind and by step, any findings left unplaced, and the journey's link.
