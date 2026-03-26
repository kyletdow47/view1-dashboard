# CLAUDE.md — View1 Dashboard Agent Handbook

You are working on the **View1 Ops Dashboard** — a static HTML dashboard that tracks the progress of building the View1 Sort product.

## What This Repo Is

This is a collection of static HTML pages deployed to Vercel. It is NOT a Next.js app. It is NOT the product. It is the **monitoring and operations dashboard** that shows:
- Build progress of the View1 Sort product
- Agent status (which AI agents are running, idle, errored)
- Strategy reports, competitive analysis, roadmaps
- Live agent control panel (polls the Telegram bot API)

## Tech Stack

- **Static HTML** with inline CSS and JavaScript
- **Vercel** for hosting (auto-deploys from this repo)
- **Vercel Serverless Functions** in `api/` (Node.js)
- **No frameworks** — no React, no Next.js, no build step

## File Structure

```
index.html            — Main project dashboard
strategy.html         — Strategy report
competitive.html      — Competitive analysis
agents.html           — Agent team playbook
flowchart.html        — Plan flowchart
agent-control.html    — Live agent monitoring (polls bot API on :3847)
api/
  telegram.js         — Telegram webhook handler
  data.js             — Data endpoint
  setup-webhook.js    — Webhook setup
vercel.json           — Vercel routing and deploy config
```

## Design System

- **Background:** #0C0C0E (dark)
- **Surface:** #161619, #1E1E22, #26262B
- **Text:** #E8E6E3 (primary), #8A8A95 (dim), #5A5A65 (muted)
- **Accent green:** #4ADE80
- **Blue:** #60A5FA
- **Purple:** #A78BFA
- **Fonts:** DM Sans (headings), JetBrains Mono (code), system-ui (body)

All pages follow this dark theme. Keep it consistent.

## Rules

1. **ONLY create static HTML files.** Do not create src/ directories, React components, or Next.js pages.
2. **Never create package.json with Next.js dependencies.** This repo has no build step.
3. **Keep the dark theme consistent** across all pages.
4. **API functions in api/ use Vercel serverless format** (export default function handler).
5. **All secrets are in Vercel env vars** — never hardcode API keys.
6. **Commit directly to main** — these are static pages, no PR workflow needed.
7. **Test by opening the HTML file in a browser** before committing.

## What This Repo Is NOT

- NOT the product (that is `view1-sort` repo)
- NOT the Telegram bot (that is `~/view1-studio/agents/telegram-bot/`)
- NOT documentation (that is `~/view1-studio/docs/`)

Do not create product code here. Do not create bot scripts here.
