# freddy plugin for Cursor and Grok Bot

freddy connects the health apps and devices you already use to your AI assistant.
This plugin adds the hosted freddy MCP server (`https://freddy.coach/mcp`) and
three skills: connect a source, weekly health review, and long-term trends.

## Setup

1. Create a free account at https://freddy.coach and connect at least one source.
2. Install the freddy plugin from the marketplace.
3. Open the freddy MCP server and choose Connect (Cursor) or Authorize (Grok Bot).
   Sign in with your email and the 6-digit code freddy sends you, then approve access.

No API key is needed. freddy uses OAuth 2.1 with PKCE and Dynamic Client Registration.

## Tools

| Tool | What it does |
|---|---|
| get_profile | Your account, plan, accepted policies, and connected sources |
| list_metrics | Which metrics you have, with units, ranges, and sources |
| query_metrics | Values for chosen metrics, daily or weekly/monthly, with optional raw detail |
| connect_source | Starts connecting a source; credentials are entered on freddy or the provider, never in chat |
| sync_source | Fetches the latest data from a connected source now |
| disconnect_source | Disconnects a source and deletes its synced data (destructive, asks first) |
| accept_terms | Records your acceptance of updated terms, only after you say you agree |
| connection_status, resume_question | Internal helpers for the in-chat connection card; not called by the model |

## Privacy and support

- Privacy policy: https://freddy.coach/privacy
- Consumer health data notice: https://freddy.coach/consumer-health-data
- Terms of service: https://freddy.coach/terms
- Support: tom@freddy.coach
- Publisher: reThrive Labs LLC, 30 N Gould St, Ste R, Sheridan, WY 82801, USA
