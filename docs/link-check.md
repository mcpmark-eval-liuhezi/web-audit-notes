# Link Check Report — Developer Onboarding Guide ("Further Reading" Box)

- **Date checked:** 2026-11-11 (UTC)
- **Method:** Live fetch of both URLs on 2026-11-11 (not from cached memory).
- **Scope:** Two claims currently in the guide's "further reading" box.

---

## Claim 1 — https://example.com

- **URL:** https://example.com
- **Page loaded:** OK (page returned successfully)
- **Main heading (verbatim):** `Example Domain`
- **Quoted line from body:** "This domain is for use in documentation examples without needing permission."
- **Date checked:** 2026-11-11
- **Status:** OK
- **Verdict vs. guide's claim:** **Matches — keep as written.** The page still opens with the heading "Example Domain", exactly as the guide states. (Note: the page has been redesigned — it is now a title-only layout with a short paragraph instead of an `<h1>`, but "Example Domain" is still exactly right.)

---

## Claim 2 — https://www.iana.org/domains/reserved

- **URL:** https://www.iana.org/domains/reserved
- **Page loaded:** OK (page returned successfully)
- **Main heading (verbatim):** `IANA-managed Reserved Domains`
- **Quoted line from body:** "Certain domains are set aside, and nominally registered to "IANA", for specific policy or technical purposes."
- **Date checked:** 2026-11-11
- **Status:** FAIL (content mismatch)
- **Verdict vs. guide's claim:** **Does not match.** This page no longer lists `.test`, `.example`, `.invalid`, and `.localhost` as an enumerated set. What it actually shows is:
  - An **"Example domains"** section (example.com, example.org per RFC 2606 / RFC 6761) — these are second-level documentation domains, not TLDs.
  - A **"Test IDN top-level domains"** table of non-Latin IDN variants (إختبار, آزمایشی, テスト, etc.) — not `.test`.
  - A **"Policy-reserved domains"** section on domains reserved under policy grounds.
  - A pointer to a separate **"Other Special-Use Domains"** registry at `/assignments/special-use-domain-names` (RFC 6761).

  The four root TLDs live in that separate registry, not on the reserved page. I also verified cross-references live: IANA's Special-Use Domain Names registry (https://www.iana.org/assignments/special-use-domain-names) does list `test.` (RFC 6761), `example.` (RFC 6761), `invalid.` (RFC 6761), and `localhost.` (RFC 6761) — along with many others (alt., home.arpa., example.com./net./org., onion., etc.).

  **Recommended fix for the guide:** link to IANA's Special-Use Domain Names registry (https://www.iana.org/assignments/special-use-domain-names) or cite RFC 2606 / RFC 6761 directly, instead of claiming the reserved page lists the four TLDs.

---

## Summary

| # | Claim | URL | Status | Verdict |
| --- | --- | --- | --- | --- |
| 1 | https://example.com opens with heading "Example Domain" | https://example.com | OK | **Matches** — keep as written |
| 2 | IANA page lists .test, .example, .invalid, .localhost | https://www.iana.org/domains/reserved | OK | **Does not match** — page has been redesigned. Re-point the guide to IANA's Special-Use Domain Names registry (https://www.iana.org/assignments/special-use-domain-names) or RFC 2606/6761. |

---

*Report generated as part of the onboarding-guide audit on 2026-11-11 (UTC). Re-run before publish if either page changes.
