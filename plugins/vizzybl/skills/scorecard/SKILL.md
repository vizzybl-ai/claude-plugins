---
name: scorecard
description: Per-engine AI-visibility scorecard from Vizzybl. Use when the user asks which AI engines mention their brand most or least, how they compare across ChatGPT, Claude, Gemini, Perplexity, Grok, Copilot, Google AI Overviews and Google AI Mode, or where to focus by engine.
argument-hint: "[days]"
---

# Per-engine scorecard

Call `engine_scorecard`. The window is 30 days unless the user asked for another length (7 to 90 days; in Claude Code it arrives as `$ARGUMENTS`).

Present one row per engine, best to worst: latest share of voice, average share of voice over the window, and the trend direction. Then name the weakest engine and the gap to the best one.

State two limits rather than hiding them:

- Per-engine figures are best-effort. Days with no per-engine rollup are skipped, so an engine with few days of data should be flagged.
- Sentiment and position are blended across engines. Never attribute a blended figure to a single engine.

If the user asks about products rather than the brand, use `product_scorecard` instead.
