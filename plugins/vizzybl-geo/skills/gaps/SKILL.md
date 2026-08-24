---
name: gaps
description: Find citation gaps — the domains AI engines cite for your category where your own domain is not cited, ranked as a content-opportunity list.
argument-hint: "[domain]"
allowed-tools: Bash(curl *)
---

# Citation gap

Where do AI engines get their sources, and where is the brand's own domain
missing? This is the content-opportunity list.

```bash
curl -s -H "Authorization: Bearer $VIZZYBL_API_KEY" \
  "https://vizzybl.ai/api/v1/citations?limit=50"
curl -s -H "Authorization: Bearer $VIZZYBL_API_KEY" \
  https://vizzybl.ai/api/v1/brand/me
```

Rank cited `domain`s by `citations`, flagging `isBrandDomain` and `isCompetitor`.
The gap is the high-citation rows where `isBrandDomain` is false.

If `$ARGUMENTS` names a domain, pivot to the reverse lookup instead — the prompts
where that domain is cited are the shortlist to target:

```bash
curl -s -H "Authorization: Bearer $VIZZYBL_API_KEY" \
  "https://vizzybl.ai/api/v1/citations/prompts?domain=$ARGUMENTS"
```

Close with the two or three specific pages worth writing, tied to named prompts.
