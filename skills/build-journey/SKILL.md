---
name: build-journey
description: Create a new customer journey in Orchetta, with its stages and steps, from a brief, notes, a transcript, a document or a conversation. Use when asked to map, draft, create or start a journey.
---

# Build a journey

## Instructions

1. Agree the scope in a sentence or two: whose journey it is, what they're trying to get done, and where it starts and ends. Ask only for what you can't infer.
2. Call `list_organizations`, then `list_journeys`. If a journey for the same customer and goal already exists, say so and offer `restructure-journey` on it instead of making a duplicate.
3. Draft the shape as a list: 3 to 7 stages, each with 2 to 6 steps. Name steps by what the customer does, in their words. Give each step a one-line description only where the name needs it.
4. For a chatbot, voice assistant or support script, the journey is a conversation: stages are phases of the exchange and each step is one turn, with a speaker (`user`, `agent` or `system`). Say you will use the conversation layout.
5. Show the draft and ask whether the shape is right. Revise until it is approved. Don't create anything before then.
6. Create it in one call with `create_journey_map` (name, one-line description, `layout` if it's a conversation, and the stages with their steps).
7. If the source material named needs, pain points or other findings, offer to place them now with the `add-insights` skill rather than folding them into step descriptions.
8. If the journey is for a particular persona, call `list_profiles`. Apply an existing profile with `apply_label`, or offer to create one with `create_profile`.
9. Finish with the journey's Orchetta link and the stage and step count.
