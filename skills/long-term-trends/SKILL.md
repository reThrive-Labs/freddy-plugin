---
name: long-term-trends
description: Use when the user asks how a metric recorded in their freddy account changed over months or years — history charts, progress since a date, seasonal patterns, year-over-year comparisons. Not for a single week (use weekly-health-review).
---

# Long-term trends

This skill uses the freddy app's MCP tools (get_profile, list_metrics, query_metrics, connect_source, sync_source) to chart the user's own recorded wellness data over time. It is a factual presentation of historical numbers, not medical advice, diagnosis, or a clinical assessment.

Show how my freddy data changed over time.

1. Call list_metrics to find the exact metric names — never guess generic English names. Prefer daily-summary variants (names containing avg/min/max) over per-reading metrics.
2. For multi-month or multi-year windows, call query_metrics with granularity: "month" (or "week" for finer detail) and explicit start / end dates (YYYY-MM-DD). This returns avg/min/max/count buckets so years of data fit in one response.
3. If a response reports truncation or omitted buckets, follow its continuation hint — it names the exact start and end to pass next.
4. Present the numbers factually: the overall direction, notable changes with their dates, seasonal patterns if visible, and — when enough history exists — the most recent 3 months side by side with the same period a year earlier. State which aggregation level the numbers come from. Do not characterize the data as a health status and do not draw medical conclusions from it.
