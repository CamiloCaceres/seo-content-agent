# SEO & Content Agent

A standalone Houston agent that runs the inbound content engine for a
founder or small team — site audits, keyword research, blog drafts,
case studies, content repurposing, content-gap analysis, backlinks,
and AI-search (GEO) visibility. Drafts only. Never publishes without
your sign-off.

## Install

In Houston: **Add from GitHub** → paste this repo's URL. Houston
installs the agent into its own workspace and seeds the empty index
so the Overview opens clean.

On first open, the Activity tab shows an **"Onboard me"** card in the
"Needs you" column — click it and send any message to start the
3-question setup (domain, existing content, SEO tooling). After that
the agent is ready to work. Positioning and voice are asked
just-in-time the first time a skill needs them — no upfront load.

## First prompts

- "Run an SEO audit of my site"
- "Find the keyword clusters we should own for {topic}"
- "Draft a blog post on {topic} targeting {keyword}"
- "Draft a customer case study for {customer}"
- "Turn this YouTube video into a blog post draft"
- "Where's our content gap vs {competitor}?"
- "Who should we try to get backlinks from, and what's the pitch?"
- "Audit our visibility in AI search (ChatGPT, Perplexity, Gemini)"

## Skills

- `onboard-me` — 3-question setup (domain, existing content, tooling).
- `audit-site-seo` — on-page + technical + content audit via Composio.
- `research-keywords` — cluster keywords (volume / difficulty / intent).
- `write-blog-post` — 2000–3000 word draft with meta, slug, CTA.
- `write-case-study` — customer story (challenge → approach → results).
- `repurpose-content` — blog / YouTube / article → any target format.
- `analyze-content-gap` — competitor crawl vs your content, ranked.
- `find-backlinks` — link targets + per-target pitch drafts.
- `audit-ai-search` — GEO visibility in ChatGPT / Perplexity / Gemini.

## What I need to know about your business

Two local config files the agent builds up on its own, just-in-time
the first time a skill needs them:

- `config/positioning.md` — product in one line, ICP,
  differentiators, category. Captured by whichever substantive skill
  runs first (best: drop a pitch deck / about page as file or URL;
  fallback: paste 3–5 sentences).
- `config/voice.md` — how you write. Needed only for drafting skills
  (blog posts, case studies, repurposed content, backlink pitches).
  Best modality: connect your inbox via Composio and I'll sample
  20–30 sent messages. Fallback: paste 2–3 things you've written.

Neither is asked upfront — `onboard-me` stays to 3 questions. The
agent asks for positioning / voice the first time a skill needs it.

## Composio is the only external transport

Every external tool — SEO platforms (Semrush / Ahrefs / Firecrawl),
content CMS (WordPress / Webflow / Ghost / Notion), search + scrape,
YouTube — is reached through Composio. The agent discovers tool
slugs at runtime with `composio search <category>`. If a connection
is missing, it names the category you should link from the
Integrations tab and stops. No hardcoded tool names.

## Outputs

Every skill writes a markdown artifact to a topic subfolder at the
agent root and appends a record to `outputs.json`. The Overview tab
is a click-to-copy menu of prompts you can run — all artifacts live
as markdown files you can edit, version, or paste into your tools.

Subfolders: `seo-audits/` · `keyword-clusters/` · `blog-posts/` ·
`case-studies/` · `repurposed/` · `content-gap-analyses/` ·
`backlink-plans/` · `ai-search-audits/`. A single living
`keyword-map.md` at the root accumulates per-cluster entries.

## Lineage

This agent was originally built as part of
[`founder-marketing-workspace`](https://github.com/CamiloCaceres/founder-marketing-workspace)
(a 5-agent workspace for solo founders) and extracted as a standalone
install. In the workspace version, positioning is read from a shared
doc owned by a Head of Marketing agent; this standalone version
captures its own `config/positioning.md` just-in-time.

## License

MIT — see `LICENSE`.
