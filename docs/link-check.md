# Link Check Report — Developer Onboarding Guide "Further Reading" Box

**Date checked:** 2026-11-12 (UTC)
**Checked by:** Automated live verification (MCP fetch tools)
**Repository:** `mcpmark-eval-liuhezi/web-audit-notes`
**File path:** `docs/link-check.md` (default branch: `main`)

## Summary

Two claims in the onboarding guide's "further reading" box were verified against the live pages on **2026-11-12**. Both pages loaded successfully. Claim 1 **holds** (matches). Claim 2 **does not hold as worded** — the IANA reserved-domains page does not enumerate `.test`, `.example`, `.invalid`, and `.localhost` as "the four special-use top-level domains"; it instead points to a separate **Special-Use Domain Names registry** and describes example domains, test IDN top-level domains, and policy-reserved domains.

## Entry 1 — https://example.com

- **URL:** https://example.com
- **Loader status:** OK — page loaded successfully (HTTP fetch succeeded; content rendered as Markdown/HTML).
- **Captured main heading (verbatim):** `Example Domain`
- **Quoted line from body text:** "This domain is for use in documentation examples without needing permission. This is not a service; avoid relying on it for testing and monitoring purposes."
- **Date checked:** 2026-11-12
- **Status:** OK
- **Verdict vs. guide's claim:** **Matches.** The page opens with the heading `Example Domain`, exactly as the guide states.

## Entry 2 — https://www.iana.org/domains/reserved

- **URL:** https://www.iana.org/domains/reserved
- **Loader status:** OK — page loaded successfully (HTTP fetch succeeded; content rendered as Markdown/HTML).
- **Captured main heading (verbatim):** `IANA-managed Reserved Domains`
- **Quoted line from body text:** "Certain domains are set aside, and nominally registered to "IANA", for specific policy or technical purposes."
- **Date checked:** 2026-11-12
- **Status:** OK (page loaded fine)
- **Verdict vs. guide's claim:** **Does not match (as worded).** The page does **not** list `.test`, `.example`, `.invalid`, and `.localhost` as "the four special-use top-level domains." Instead, it explains that example domains (per RFC 2606 and RFC 6761) such as `example.com` and `example.org` are maintained for documentation purposes, covers **Test IDN top-level domains** (Arabic, Persian, Chinese, Russian, Hindi, Greek, Korean, Yiddish, Japanese, Tamil), and **policy-reserved domains**. It also notes a separately maintained **Special-Use Domain Names registry** (`/assignments/special-use-domain-names`) that documents special-use domains designated by technical standards. Recommendation: reword the guide's claim to reference the Special-Use Domain Names registry, or cite RFC 2606/6761 directly for the `.test`, `.example`, `.invalid`, and `.localhost` TLDs.

## Notes for the guide authors

1. **example.com heading:** Verified live on 2026-11-12. The `<h1>` reads `Example Domain`. The body text has been updated from the older "This domain is for use in illustrative examples in documents. You may use this domain in literature without prior coordination or asking for permission." wording to: "This domain is for use in documentation examples without needing permission. This is not a service; avoid relying on it for testing and monitoring purposes." The claim still holds, but consider adding a footnote that the page now explicitly discourages relying on it for testing/monitoring.
2. **Special-use TLDs:** The IANA reserved-domains page is not the right source to cite for the list `.test`, `.example`, `.invalid`, `.localhost`. Cite the **Special-Use Domain Names registry** at `https://www.iana.org/assignments/special-use-domain-names` or **RFC 2606** / **RFC 6761** instead.
3. All checks were performed live on 2026-11-12 (UTC); re-verify before the guide ships if any delay beyond today is expected.
