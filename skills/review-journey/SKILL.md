---
name: review-journey
description: Check an Orchetta journey for gaps and mess, such as missing descriptions, empty stages, steps without needs or pain points, unscored or unlinked records, duplicates and a missing goal or metric, then offer fixes. Use when asked how good, complete or ready a journey is, or to tidy one up.
---

# Review a journey

## Instructions

1. `get_journey`, `list_resource_kinds`, and `list_resources` for the needs and pain points on it (for their scores and status).
2. Check the journey against this list and note each result as pass or fail, with the stages, steps or records involved:
   - The journey has a description.
   - It has at least two stages, and no stage is empty.
   - Nearly every step (80% or more) carries at least one need or pain point.
   - Needs and pain points are scored or prioritised.
   - Pain points are linked to an opportunity or solution where one exists.
   - No two records on the same step say the same thing.
   - Names fit the board: short phrases, and descriptions on one line.
   - The journey has a goal and a metric attached somewhere.
   - Persona: a profile is applied, if the workspace uses profiles.
3. Report the failures first, the worst gap first, in a short list. Give a one-line tally (for example, "7 of 9 pass").
4. Offer fixes grouped by effort. Do nothing until the person picks:
   - **Quick fixes you can make now:** a missing description, shortened names, links between existing records.
   - **Fixes that need input:** scores, merging duplicates, new needs for bare steps.
   Then use `add-insights` or `restructure-journey` as each fix calls for.
5. Don't invent findings to fill bare steps. A step with nothing on it is a research gap to report, not something to make up.
