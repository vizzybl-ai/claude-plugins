---
name: pulse
description: Weekly AI-visibility pulse — share of voice, rank, and sentiment for the last 7 days versus the prior 7, across every tracked AI answer engine.
argument-hint: "[days]"
allowed-tools: Bash(curl *)
---

# Vizzybl weekly pulse

Week-over-week movement in the brand's AI-search visibility. Window defaults to 7
days; if `$ARGUMENTS` is a number, use that many days per period instead.

Call `/stats` twice — the current window and the one immediately before it:

```bash
curl -s -H "Authorization: Bearer $VIZZYBL_API_KEY" \
  "https://vizzybl.ai/api/v1/stats?startDate=<curStart>&endDate=<curEnd>"
curl -s -H "Authorization: Bearer $VIZZYBL_API_KEY" \
  "https://vizzybl.ai/api/v1/stats?startDate=<prevStart>&endDate=<prevEnd>"
```

Compute today's date first — never assume a year. Report as a short table:
`shareOfVoice`, `rank`, and `sentimentScore` for each period plus the delta, then
one sentence on what moved and `topCompetitors[]` if the ordering changed.

Report a metric as unchanged only when both periods returned data. If either
window is empty, say so — a missing period is not a zero.

See the bundled `references/api-reference.md` for full response fields.
