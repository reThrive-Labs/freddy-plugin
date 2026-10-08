---
name: weekly-health-review
description: Use when the user asks for a weekly summary or check-in of the sleep, heart, training, or body data recorded in their freddy account. Not for multi-month or multi-year questions (use long-term-trends) or single-metric lookups.
---

# Weekly health review

This skill uses the freddy app's MCP tools (get_profile, list_metrics, query_metrics, connect_source, sync_source) to present the user's own recorded wellness data back to them. It is a factual data summary, not medical advice, diagnosis, or a clinical assessment.

Summarize my week from my freddy data.

1. Call get_profile to see which sources are connected and whether a sync is running, then list_metrics once to learn the exact metric names available for my account.
2. Fetch the most recent 7 full days with explicit start / end dates (YYYY-MM-DD; end = yesterday, start = 6 days before that) for the areas that exist in my data: sleep (duration, stages), heart data (HRV, resting heart rate), training (workouts, load), and body measurements (weight) if present.
3. Fetch the 7 full days immediately before that window, again with explicit start / end dates, as the comparison baseline — two equal-length, non-overlapping weeks.
4. Present a factual side-by-side summary: how this week's numbers compare with the previous week, with the actual values. Call out gaps — days without data or a source that stopped syncing. Do not assess health status, offer diagnoses, or prescribe changes; if the user wants guidance beyond what their numbers show, suggest they consult a qualified professional.

Stay grounded in the data returned — no invented values, and no conclusions from metrics that were not fetched.
