---
name: ask-traffic
description: Summarize traffic for an OpenRevenue site (stats + optional timeseries)
---

# Ask traffic

Use the OpenRevenue MCP tools (and the `traffic-overview` skill when available).

1. If the user did not name a domain, call `list_projects` and pick or ask.
2. Call `get_project_stats` with period `7d` unless they named another period.
3. Optionally call `get_timeseries` for the same domain and period.
4. Answer only with tool results — never invent metrics.
