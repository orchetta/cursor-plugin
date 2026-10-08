# Orchetta for Cursor

Manage your customer journeys from Cursor's agent. [Orchetta](https://orchetta.com) is where a team maps what customers go through: journeys, their stages and steps, and the needs, pain points, opportunities, solutions, goals and metrics on each step. With this plugin, Cursor's agent can look after a journey on any model you choose. It can build the journey, reshape it, fill it with findings, and keep it tidy.

## What's included

| Component | What it does |
| --- | --- |
| `mcp.json` | Connects the Orchetta MCP server at `https://orchetta.com/mcp`. |
| `agents/journey-manager` | An agent that looks after a journey end to end: it reads before it writes, announces each change, asks before removing anything, and doesn't make things up. |
| `skills/build-journey` | Drafts a new journey's stages and steps from a brief, notes or a transcript, confirms the shape, then creates it in one call. |
| `skills/restructure-journey` | Renames, reorders, moves, merges, splits and removes stages and steps without losing what's attached. |
| `skills/add-insights` | Turns interviews, tickets, surveys or feedback into needs, pain points, gains, opportunities and solutions on the right steps. It checks for duplicates and links each pain point to its answer. |
| `skills/review-journey` | Checks a journey for gaps and mess, such as empty stages, bare steps, unscored or unlinked records, and duplicates, then offers fixes. |
| `rules/orchetta.mdc` | The ground rules for any task that touches Orchetta. |
| `/journey-status` | Walks one journey stage by stage, with what sits on each step and where the gaps are. |
| `/orchetta-overview` | Summarises a workspace's journeys and records. |
| `/orchetta-pain-points` | Lists the highest-priority pain points and where they sit. |

## Setup

1. Install the plugin from the Cursor Marketplace.
2. The first time the agent uses an Orchetta tool, Cursor opens Orchetta's sign-in in your browser. Approve it.

That is the whole setup. There is no API key to paste: the server uses OAuth with dynamic client registration. You need an Orchetta account; [sign up](https://orchetta.com) if you don't have one.

The connection acts as you, with your role in each workspace you belong to. A viewer can read but not write. A workspace admin can turn MCP access off for a workspace under **Settings → MCP**. You can disconnect Cursor at any time under **Settings → API tokens**.

### Cloud agents and CI

Cursor's cloud agents sign in the same way: the first Orchetta call opens the sign-in in your browser, and approving it hands the connection back to the agent.

Where no one can approve a sign-in, such as CI or a scheduled job, create an API token under **Settings → API tokens** in Orchetta and add the server to `.cursor/mcp.json` with the token as a bearer header:

```json
{
  "mcpServers": {
    "orchetta": {
      "url": "https://orchetta.com/mcp",
      "headers": { "Authorization": "Bearer ${env:ORCHETTA_TOKEN}" }
    }
  }
}
```

## Try it

- "Build a journey for a first-time buyer, from discovering us to their first repeat order."
- "Here are five interview transcripts. Add what they say to the onboarding journey."
- "Merge the two payment steps in checkout and move delivery into its own stage."
- "Review the onboarding journey and fix what you can."
- `/journey-status`

## Cost

Nothing the server exposes calls a model, so managing journeys from Cursor never spends your Orchetta AI credits.

## Links

- [Connecting an AI client over MCP](https://orchetta.com/help/connect-mcp)
- [Privacy](https://orchetta.com/privacy) · [Terms](https://orchetta.com/terms)
- Support: support@orchetta.com

## License

MIT
