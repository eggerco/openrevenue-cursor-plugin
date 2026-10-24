---
name: top-referrers
description: List top referrers for an OpenRevenue site
---

# Top referrers

Use the OpenRevenue MCP tools (and the `traffic-sources` skill when available).

1. Resolve `domain` via the user or `list_projects`.
2. Call `get_referrers` with period `30d` unless they named another period.
3. Summarize top sources with counts from the tool only.
