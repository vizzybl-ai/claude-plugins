---
name: scorecard
description: Per-engine visibility scorecard — share of voice and trend broken down by ChatGPT, Claude, Gemini, Perplexity, Grok, Copilot, Google AI Overviews and Google AI Mode.
argument-hint: "[days]"
allowed-tools: Bash(curl *)
---

# Per-engine scorecard

Which AI engines does the brand win on, and which is it losing? Default window 30
days, or `$ARGUMENTS` days if given.

```bash
curl -s -H "Authorization: Bearer $VIZZYBL_API_KEY" \
  "https://vizzybl.ai/api/v1/visibility?byEngine=true&startDate=<start>&endDate=<end>&limit=200"
curl -s -H "Authorization: Bearer $VIZZYBL_API_KEY" \
  "https://vizzybl.ai/api/v1/stats?startDate=<start>&endDate=<end>"
```

Fold each day's `byEngine` map into per-engine latest and average share of voice
plus a trend direction. Present one row per engine, best to worst.

Two caveats to state rather than paper over: `byEngine` is best-effort and is
`null` on days with no rollup, and sentiment and position are blended across
engines — they are not available per engine. Do not attribute a blended figure to
a single engine.
