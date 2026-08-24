---
name: audit
description: Run a GEO audit on a URL and report its AI-visibility and readiness scores. Spends credits.
argument-hint: "[url]"
disable-model-invocation: true
allowed-tools: Bash(curl *)
---

# Run a GEO audit

**This spends credits.** It is user-invoked only — `disable-model-invocation`
keeps it from ever firing on its own.

Audit `$ARGUMENTS`. If no URL was given, ask for one; do not guess a URL.

Before submitting, check the balance and confirm the action with the user:

```bash
curl -s -H "Authorization: Bearer $VIZZYBL_API_KEY" https://vizzybl.ai/api/v1/quota
```

Then submit and poll — never re-POST to check progress:

```bash
curl -s -X POST -H "Authorization: Bearer $VIZZYBL_API_KEY" \
  -H "Content-Type: application/json" -d '{"url":"$ARGUMENTS"}' \
  https://vizzybl.ai/api/v1/audits
curl -s -H "Authorization: Bearer $VIZZYBL_API_KEY" \
  https://vizzybl.ai/api/v1/audits/AUDIT_ID
```

Poll `GET /audits/{auditId}` until `status` is `completed` or `error`. Report
`scores.aiVisibilityIndex`, `scores.geoReadiness`, the technical/content/authority
pillars, and how many AI bots `robots` blocks.

Needs the `write:audits` scope. A `403 INSUFFICIENT_SCOPE` means the key was
created read-only — say so rather than retrying. `400 BLOCKED` means the URL is
internal or disallowed; ask for a public one. `402` means insufficient credits:
report the balance, do not retry.
