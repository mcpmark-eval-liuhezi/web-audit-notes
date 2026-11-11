# Link Check Report — Developer Onboarding Guide ("Further Reading" Box)

**Date checked:** 2026-11-11 (UTC)
**Source of truth:** Live fetch of both URLs on the date above (not from cached memory).
**Scope:** Two claims currently in the guide's "further reading" box.

---

## Claim 1 — https://example.com

- **URL:** https://example.com
- **Status:** OK (page loaded fine)
- **Captured heading (verbatim):** `Example Domain`
- **Quoted line from body:** "This domain is for use in documentation examples without needing permission." (Note: the page has been redesigned; it now also warns: "This is not a service; avoid relying on it for testing and monitoring purposes.")
- **Verdict vs. guide's claim:** **Matches.** The page still opens with the heading **"Example Domain"**, exactly as the guide states.

## Claim 2 — https://www.iana.org/domains/reserved

- **URL:** https://www.iana.org/domains/reserved
- **Status:** OK (page loaded fine)
- **Captured heading (verbatim):** `IANA-managed Reserved Domains`
- **Quoted line from body:** "Certain domains are set aside, and nominally registered to IANA, for specific policy or technical purposes." (The page also references the Special-Use Domain Names registry at `/assignments/special-use-domain-names`, rather than listing the four TLDs directly.)
- **Verdict vs. guide's claim:** **Does not match.** The page no longer lists `.test`, `.example`, `.invalid`, and `.localhost` as an enumerated set. What it actually shows is: an "Example domains" section (example.com, example.org per RFC 2606 / RFC 6761), a "Test IDN top-level domains" table of non-Latin IDN variants (إختبار, آزمایشی, テスト, etc.), a "Policy-reserved domains" section, and a pointer to a separate "Other Special-Use Domains" registry (`/assignments/special-use-domain-names`). The four root TLDs live in that separate registry, not on this page. **Recommendation:** update the guide to link to the Special-Use Domain Names registry (or cite RFC 2606 / RFC 6761) instead of claiming this page lists the four TLDs.

---

## Summary

| Claim | URL | Status | Verdict |
| --- | --- | --- | --- |
| example.com opens with heading "Example Domain" | https://example.com | OK | **Matches** — keep as written |
| IANA page lists .test, .example, .invalid, .localhost | https://www.iana.org/domains/reserved | OK | **Does not match** — page redDuring a redesign. Re-point the guide to IANA's Special-Use Domain Names registry (https://www.iana.org/assignments/special-use-domain-names) or RFC 2606/6761. |

*Report generated automatically as part of the onboarding-guide audit. Re-run before publish if pages change.*
