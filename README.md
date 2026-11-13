# aliasmail-site

Static site for **aliasmail.app** — landing page, privacy policy, terms and the
account-deletion page (WEB-01). Served by a Cloudflare Workers assets-only
project; the API itself lives in the [`aliasmail`](https://github.com/michael-whelan/aliasmail)
repo on **api.aliasmail.app**, so nothing here proxies or shadows it.

## Pages

| Path | Purpose |
|---|---|
| `/` | Landing: what Alias Mail is, how it works, plans |
| `/privacy` | Privacy policy (matches the app's trust line: no email storage, 30-day metadata) |
| `/terms` | Terms of service |
| `/delete-account` | How to delete your account in-app + email fallback for Play compliance |

The pages use the app's dark/blue brand (APP-25 tokens: `#0F1115` bg, `#3B82F6`
primary). The Play Store link is a placeholder until APP-12.

## Deploy

```
npx wrangler deploy
```

Requires the `aliasmail.app` custom domain to be attached to the account. The
first deploy claims the domain; Cloudflare manages DNS.

## Editing

Everything is hand-written static HTML at the repo root — no build step, no
dependencies. Keep the shared `<style>` block in sync across pages. The same files are also served by GitHub Pages at michaelwhelan.dev/aliasmail-site/.
