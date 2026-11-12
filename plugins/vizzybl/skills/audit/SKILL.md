---
name: audit
description: Run a Vizzybl GEO audit on a public web page and report its AI-visibility and readiness scores. Spends credits. Use only when the user asks to audit a specific URL, or to show results of past Vizzybl audits.
argument-hint: "[url]"
---

# GEO audit

An audit spends workspace credits. Run one only when the user asked for an audit of a specific URL in this conversation. For past results, `list_audits` and `get_audit` are free.

1. Get the URL. In Claude Code it arrives as `$ARGUMENTS`. If none was given, ask for one; never guess.
2. Call `get_quota` and tell the user their credit balance.
3. Call `run_audit` with the URL. Claude asks the user to approve it. Add `keywords` only if the user gave some.
4. It returns an `auditId` straight away. Call `get_audit` with it until `status` is `completed` or `error`. Never call `run_audit` again to check progress.
5. Report the AI Visibility Index and GEO readiness, the technical, content and authority pillar scores, and how many AI crawlers the site's robots.txt blocks.

If the result is `BLOCKED`, the URL is internal or not allowed: ask for a public URL. If it is `INSUFFICIENT_CREDITS`, report the balance and stop.
