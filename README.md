# Storelens MCP server

Connect Claude, ChatGPT, Cursor or any MCP client to [Storelens](https://storelensapp.com): detect a store's Shopify theme, apps and tech stack, open store spy reports (catalog, prices, launches, best sellers), see the Meta ads a store runs, track competitors for daily price and launch alerts, and search an index of live Shopify stores by theme, app, country and niche, with owner contacts.

## Remote (recommended)

Add `https://storelensapp.com/mcp` as a custom connector. You sign in to Storelens and approve access (OAuth 2.1 with PKCE).

```bash
claude mcp add --transport http storelens https://storelensapp.com/mcp
```

Clients without OAuth can send an API key from Settings in the Storelens dashboard:

```json
{ "mcpServers": { "storelens": { "url": "https://storelensapp.com/mcp", "headers": { "Authorization": "Bearer sl_live_…" } } } }
```

## Desktop / npm

```bash
npx -y storelens-mcp
```

The package is a small bridge to the remote endpoint; your browser opens for sign-in and consent. A `.mcpb` desktop extension is attached to each release.

## Tools

| Tool | What it does | Uses |
|---|---|---|
| `get_account` | Plan, monthly limits and usage | nothing |
| `detect_store` | Theme, apps, stack, country, product count of any store | nothing |
| `get_store_report` | Catalog, launches, best sellers, price and stock changes | 1 store spy report |
| `get_store_ads` | Live Meta ads with creative, copy and start date | 1 ad lookup |
| `search_leads` / `get_lead_filters` | Shopify stores by theme, app, country, niche, size | nothing (plan rows) |
| `reveal_store_contacts` | Owners and executives of a store | 1 reveal, refunded on a miss |
| `track_store` / `untrack_store` / `list_tracked_stores` / `get_alerts` | Daily price, launch and stock alerts | tracked-store slots |

Plans and allowances: https://storelensapp.com/pricing/ · Docs: https://storelensapp.com/developers/ · Privacy: https://storelensapp.com/privacy/

## License

MIT
