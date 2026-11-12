---
name: gaps
description: Find citation gaps with Vizzybl, the websites AI engines cite for the user's topics where the user's own site is not cited. Use when the user asks who gets cited instead of them, which sources AI engines trust in their category, or what content to create to earn AI citations.
argument-hint: "[domain]"
---

# Citation gaps

Call `citation_gap`. It returns the brand's own domain, whether that domain is cited at all, and the other domains AI engines cite, most-cited first.

Present the top domains as a table: domain, citation count, and whether it is a competitor. These are the sources AI engines rely on where the brand is absent.

If the user named a domain (in Claude Code it arrives as `$ARGUMENTS`), call `find_prompts_citing` with that `domain` to list the monitored prompts where it is cited and which engines cite it. Those prompts are the shortlist to target.

For how well the brand's own pages earn citations, use `source_authority`.

Close with two or three specific pages worth creating or improving, each tied to named prompts and the domains currently cited for them.
