---
name: connect-a-source
description: Use when the user says connect my health source, wants to connect a wearable, ring, CGM, training platform, gym log, Apple Health, or Health Connect to freddy, or asks why a newly connected source shows no data yet. Not for disconnecting or an ordinary data query.
---

# Connect my health source

This skill uses the freddy app's MCP tools (get_profile, list_metrics, query_metrics, connect_source, sync_source). Follow the workflow below.

Connect my health source to freddy.

1. Call get_profile to see what is already connected.
2. If I haven't named a source, ask which app or device I use. Once I answer, immediately call connect_source with that provider; do not guess.
3. If this connection interrupted another health-data question, pass that exact question as original_question. Never add provider credentials, health data, or anything else to that field.
4. Use the interactive card when available. OAuth approval and credentials happen on freddy or the provider; Apple Health and Health Connect finish in the freddy phone app. Keep the tool's text instructions as the fallback, and never ask me to paste credentials into chat.
5. After authorization, the first sync/backfill may take a few minutes. The card checks for real synced data and offers one action to continue the original question. If no card is available, re-check with get_profile or query_metrics after 30-60 seconds; call sync_source only if the source is connected but still stale.
