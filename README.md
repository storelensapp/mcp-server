# Ecommerce competitor research by Storelens

Ecommerce competitor research as an MCP server: store spy reports, a theme detector and app detector, competitor product tracking, price tracking, best sellers and store leads. Connect Claude, ChatGPT, Cursor or any MCP client to [Storelens](https://storelensapp.com): detect a store's Shopify theme, apps and tech stack, open store spy reports (catalog, prices, launches, best sellers), see the Meta ads a store runs, track competitors for daily price and launch alerts, and search an index of live Shopify stores by theme, app, country and niche, with owner contacts.

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
| `get_account` | Plan, limits and usage | nothing |
| `detect_store` | Theme, apps, stack, country, product count of any store | nothing on paid plans; 1 of 5 free scans on Free |
| `get_store_report` | Catalog, launches, best sellers, price and stock changes | 1 store spy report |
| `get_store_ads` | Live Meta ads with creative, copy and start date | 1 ad lookup |
| `search_leads` / `get_lead_filters` | Shopify stores by theme, app, country, niche, size | nothing on paid plans (plan rows); 10 rows in total on Free |
| `reveal_store_contacts` | Owners and executives of a store | 1 reveal, refunded on a miss |
| `track_store` / `untrack_store` / `list_tracked_stores` / `get_alerts` | Daily price, launch and stock alerts | tracked-store slots; 7 alert days on Free |

Every tool runs on your Storelens account. A free account is a one-time allowance to try Storelens with no card: 5 store scans, 3 store spy reports, 10 lead rows and 1 tracked store with 7 alert days. Subscribe for more: Starter and Pro have monthly allowances.

## Contact data: sources, legal basis and opt-out

Owner contacts come from a business-contact data provider, reached through the treg API gateway, that compiles what professionals publish about their work (company websites, professional profiles, public business registries); store facts come from each store's public pages. Storelens holds them for business-to-business contact with the people who run a store, on the basis of legitimate interests (Article 6(1)(f) GDPR). Anyone listed can be removed at https://storelensapp.com/opt-out/ with a work email or a store domain: no account is needed and it takes effect immediately on the website, the API, the MCP server and exports.

Plans and allowances: https://storelensapp.com/pricing/ · Docs: https://storelensapp.com/developers/ · Privacy: https://storelensapp.com/privacy/ · Opt out: https://storelensapp.com/opt-out/

## License

MIT
