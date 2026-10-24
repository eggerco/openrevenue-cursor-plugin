# OpenRevenue for Cursor

Privacy-friendly web analytics in Cursor. This plugin connects Cursor to the
hosted [OpenRevenue MCP](https://mcp.openrevenue.com/mcp) so you can ask about
traffic, sources, funnels, and visitors for sites you can access.

## Install

1. Open **Cursor Settings → Plugins** (or browse the [Cursor Marketplace](https://cursor.com/marketplace)).
2. Install **OpenRevenue**.
3. Enable the MCP server and complete the OAuth connect flow when prompted.

Docs: [openrevenue.com/docs/api/mcp#cursor](https://www.openrevenue.com/docs/api/mcp#cursor)

### Optional: API key

Prefer a key instead of OAuth? Create one under **Account → API** in OpenRevenue,
then add a **separate** manual MCP server entry (plugin-managed MCP config is
read-only) with:

```http
Authorization: Bearer openrevenue_…
```

## What’s included

| Component | Purpose |
| --- | --- |
| MCP | Hosted HTTP MCP at `https://mcp.openrevenue.com/mcp` |
| Skills | `traffic-overview`, `traffic-sources`, `funnel-health` |
| Commands | `ask-traffic`, `top-referrers`, `list-sites` |

Skills and commands only use numbers returned by MCP tools — they never invent metrics.

## Try these prompts

- How did my top site do this week?
- What are the top referrers for my project in the last 30 days?
- Show funnel conversion for my signup funnel this month.
- List my OpenRevenue projects.

## Local development

```bash
mkdir -p ~/.cursor/plugins/local/openrevenue
rsync -a --delete ./ ~/.cursor/plugins/local/openrevenue/ \
  --exclude .git --exclude scripts
```

Then **Developer: Reload Window** → Customize, and confirm skills / MCP appear.

```bash
node scripts/validate-template.mjs
```

## License

MIT. The OpenRevenue product and hosted MCP remain separate (proprietary SaaS);
this repository only packages Cursor plugin metadata, skills, and commands.
