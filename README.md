# Vizzybl Claude plugins

Claude Code plugins for [Vizzybl](https://vizzybl.ai) — measure how your brand
appears inside AI answer engines (ChatGPT, Claude, Gemini, Perplexity, Grok,
Google AI Overviews, Copilot).

## Install

```
/plugin marketplace add vizzybl-ai/claude-plugins
/plugin install vizzybl-geo@vizzybl
```

## Plugins

### `vizzybl-geo`

Query the Vizzybl public API from Claude in plain language — share of voice over
time, the verbatim AI answers for your monitored prompts, which domains get
cited, product visibility, and AI-crawler traffic. With a write-scoped key it can
also run a GEO audit or start tracking new prompts, confirming with you before it
spends credits.

Needs a Vizzybl API key in `VIZZYBL_API_KEY` (format `vzbl_live_…`), created under
**Settings → API Keys** on an Ultra or Enterprise plan.

Full setup guide: <https://vizzybl.ai/docs/claude-skill>

---

This repo is generated. The plugin source lives in the Vizzybl product repo and is
mirrored here by `scripts/sync-plugin-repo.sh` — edit it there, not here.
