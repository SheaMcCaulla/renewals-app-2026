# 2026 Renewals App

A renewal tracking dashboard with Gmail draft integration.

## Deploy to Vercel (2 minutes)

### Option A — Drag & drop (easiest, no account needed)
1. Go to [vercel.com](https://vercel.com) and sign up with your Google or GitHub account
2. From the dashboard click **"Add New Project"** → **"Deploy from template"** — or just drag the project folder onto the Vercel dashboard
3. Done — you'll get a URL like `https://renewals-yourname.vercel.app`

### Option B — Vercel CLI
```bash
npm i -g vercel
cd renewals-app
vercel
```
Follow the prompts — takes about 60 seconds. You'll get a live URL.

### Option C — GitHub (best for future updates)
1. Push this folder to a GitHub repo
2. Connect the repo to Vercel — it auto-deploys on every push
3. When you get CRM integration set up, push the update and it redeploys automatically

## Updating data
Until CRM integration is live, open `index.html` and edit the `DATA` array at the top of the `<script>` block. Each account has:
- `co` — display name
- `close` — CRM target close date (M/D/YYYY)
- `amt` — contract value (0 for TBD)
- `stage` — "Renewal Notice Sent" | "In Contract" | "Closed Won" | "Closed Lost"
- `ar` — true/false for auto-renewal clause

## Gmail integration
The app calls the Anthropic API to create Gmail drafts. This works when accessed through Claude.ai. For standalone use outside Claude, you'd swap the API call for a direct Gmail OAuth integration — flag this when ready and it can be wired up.

## Coming: HubSpot integration
HubSpot MCP is available in your Claude connectors. Once connected, the DATA array can be replaced with a live query pulling stage, close date, and contract value directly from your CRM.
