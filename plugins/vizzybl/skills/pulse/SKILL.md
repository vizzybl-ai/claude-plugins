---
name: pulse
description: Weekly AI-visibility pulse from Vizzybl. Use when the user asks how their brand did in AI answers this week, what changed since last week, or for a quick status update on share of voice, rank and sentiment.
argument-hint: "[days]"
---

# Weekly pulse

Call `weekly_pulse`. It returns the last 7 days and the 7 days before, side by side, with the exact dates of each window.

If the user asked for a different window (in Claude Code, a number of days arrives as `$ARGUMENTS`), call `get_visibility_stats` twice instead: once for the current window and once for the window of the same length just before it. Work out today's date first.

Report a short table with one row each for share of voice, rank and sentiment: this period, the previous period, and the change. Then add one sentence on what moved most and, if the order of `topCompetitors` changed, who overtook whom.

Call a metric unchanged only when both periods have data. If either period is empty, say that period has no data; it is not a zero.
