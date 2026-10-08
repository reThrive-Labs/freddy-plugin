# freddy plugin for Cursor and Grok Bot

freddy connects the health apps and devices you already use to your AI assistant.
This plugin adds the hosted freddy MCP server (`https://freddy.coach/mcp`) and
three skills: connect a source, weekly health review, and long-term trends.

## Setup

1. Install the freddy plugin from the marketplace.
2. Open the freddy MCP server and choose Connect (Cursor) or Authorize (Grok Bot).
   Sign in with your email and the 6-digit code freddy sends you, then approve access.
   If you don't have a freddy account yet, one is created when you sign in.
3. Optional: connect a wearable or app. You can do this from chat ("connect my Garmin")
   or on https://freddy.coach.

No API key is needed. freddy uses OAuth 2.1 with PKCE and Dynamic Client Registration.

### Manual install (until the marketplace listing is live)

Add freddy to `~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "freddy": {
      "url": "https://freddy.coach/mcp"
    }
  }
}
```

Then open Cursor Settings, find freddy under MCP, and choose Connect to sign in.

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

freddy shows your own recorded data back to you. It is not medical advice.

- Privacy policy: https://freddy.coach/privacy
- Consumer health data notice: https://freddy.coach/consumer-health-data
- Terms of service: https://freddy.coach/terms
- Support: tom@freddy.coach
- Publisher: reThrive Labs LLC, 30 N Gould St, Ste R, Sheridan, WY 82801, USA
