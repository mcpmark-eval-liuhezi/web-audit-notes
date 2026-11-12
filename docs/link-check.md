# Link Check Report — Developer Onboarding Guide "Further Reading" Box

**Repository:** `mcpmark-eval-liuhezi/web-audit-notes`
**File:** `docs/link-check.md`
**Date checked:** 2026-07-15
**Method:** Live fetch of each URL at time of writing (verified fresh via HTTP fetch tools, not from memory or cached documentation).

---

## Summary

| # | URL | Captured heading (verbatim) | Page loaded? | Verdict vs. guide claim |
|---|-----|---------------------------|--------------|--------------------------|
| 1 | https://example.com | `Example Domain` | Yes — OK | **Matches** |
| 2 | https://www.iana.org/domains/reserved | `IANA-managed Reserved Domains` | Yes — OK | **Matches (with a precision note)** |

## Entry 1: https://example.com

- **URL:** https://example.com
- **Loader status:** OK — page loaded successfully (`ok: true`), content retrieved.
- **Captured main heading (verbatim):** `Example Domain`
- **Quoted line from body text:** "This domain is for use in documentation examples without needing permission. This is not a service; avoid relying on it for testing and monitoring purposes."
- **Date checked:** 2026-07-15
- **Status:** OK
- **Verdict vs. guide's claim:** **Matches.** The page opens with the heading `Example Domain`, exactly as the guide states. The claim still holds.
- **Notes:** The body copy has been updated relative to older versions of the page; it now includes a caveat: "This is not a service; avoid relying on it for testing and monitoring purposes." If the onboarding guide suggests using example.com for live tests, flag that it should not be relied on for testing/monitoring.

## Entry 2: https://www.iana.org/domains/reserved

- **URL:** https://www.iana.org/domains/reserved
- **Loader status:** OK — page loaded successfully (`ok: true`), content rendered.
- **Captured main heading (verbatim):** `IANA-managed Reserved Domains`
- **Quoted line from body text:** "Certain domains are set aside, and nominally registered to "IANA", for specific policy or technical purposes."
- **Date checked:** 2026-07-15
- **Status:** OK (page loaded fine)
- **Verdict vs. guide's claim:** **Matches (with a precision note).** The page is on-topic and does reference these special-use domains via RFC 2606 / RFC 6761 links under "Example domains" and "Other Special-Use Domains", and points readers to the separate **Special-Use Domain Names** registry at `/assignments/special-use-domain-names`, where `example.`, `invalid.`, `localhost.`, and `test.` are all listed (each referenced to RFC 6761, except `localhost.` which is referenced to RFC 6762). For the authoritative four-item list, cite that registry directly.

## Notes for the guide authors

1. **example.com heading:** Verified live on 2026-07-15. The main heading reads `Example Domain`, exactly as the guide states. The claim still holds. The body text has been updated from the older "This domain is for use in illustrative examples in documents. You may use this domain in literature without prior coordination or asking for permission." wording to: "This domain is for use in documentation examples without needing permission. This is not a service; avoid relying on it for testing and monitoring purposes." Consider adding a footnote that the page now explicitly discourages relying on it for testing/monitoring.
2. **Special-use TLDs:** The IANA reserved-domains page is a valid reference for policy context, but the authoritative list of `.test`, `.example`, `.invalid`, and `.localhost` lives in the **Special-Use Domain Names registry** (`https://www.iana.org/assignments/special-use-domain-names`, last updated 2026-05-22 per the page) or in **RFC 2606** / **RFC 6761**. Recommend citing that registry directly for the list.
3. All checks were performed live on 2026-07-15; no Broken Resource errors were returned for either URL.

## File location

- **Path:** `docs/link-check.md`
- **Branch:** `link-check-update` (also present on `main`)
- **GitHub link:** https://github.com/mcpmark-eval-liuhezi/web-audit-notes/blob/link-check-update/docs/link-check.md
