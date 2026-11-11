# Link Check Report — Developer Onboarding Guide ("Further Reading" Box)

- **Date checked:** 2026-11-11 (live fetch performed just now, not from cached memory)
- **Method:** Both URLs were loaded live via HTTP fetch on the check date above.
- **Scope:** The two claims currently in the guide's "further reading" box.
- **Repository:** `mcpmark-eval-liuhezi/web-audit-notes`, path `docs/link-check.md` (default branch: `main`).

---

## Claim 1 — https://example.com

- **URL:** https://example.com
- **Page loaded:** OK (page returned successfully)
- **Main heading (verbatim):** `Example Domain`
- **Quoted line from body:** "This domain is for use in documentation examples without needing permission. This is not a service; avoid relying on it for testing and monitoring purposes."
- **Date checked:** 2026-11-11
- **Status:** OK
- **Verdict vs. guide's claim:** **Matches — keep as written.** The page still opens with the heading "Example Domain", exactly as the guide states. (Note: the page has been redesigned — it is now a title-only layout with a short paragraph instead of the older multi-paragraph body — but "Example Domain" is still exactly right.)

---

## Claim 2 — https://www.iana.org/domains/reserved

- **URL:** https://www.iana.org/domains/reserved
- **Page loaded:** OK (page returned successfully)
- **Main heading (verbatim):** `IANA-managed Reserved Domains`
- **Quoted line from body:** "Certain domains are set aside, and nominally registered to "IANA", for specific policy or technical purposes."
- **Date checked:** 2026-11-11
- **Status:** OK (page loads fine), but **content does not match** the guide's claim as phrased.
- **Verdict vs. guide's claim:** **Does not match as written.** This page no longer presents `.test`, `.example`, `.invalid`, and `.localhost` as an enumerated set. What it actually shows is:
  - An **"Example domains"** section (example.com, example.org per RFC 2606 / RFC 6761) — these are second-level documentation domains, not the root TLDs `.example`.
  - A **"Test IDN top-level domains"** table of non-Latin IDN variants (إختبار / آزمایشی / テスト, etc.) — not `.test`.
  - A **"Policy-reserved domains"** section on domains reserved under policy grounds (RFC documents / contractual limitations).
  - A pointer to a separate **"Other Special-Use Domains"** registry at `/assignments/special-use-domain-names` (RFC 6761).

  The four root TLDs live in that separate registry, not on the reserved page. I also verified cross-references live: IANA's Special-Use Domain Names registry (https://www.iana.org/assignments/special-use-domain-names, last updated 2026-05-22) does list `example.` (RFC 6761), `invalid.` (RFC 6761), `localhost.` (RFC 6761), and `test.` (RFC 6761) — along with many others (alt., home.arpa., example.com./net./org., onion., ipv4only.arpa., resolver.arpa., service.arpa., etc.).

  **Recommended fix for the guide:** link to IANA's Special-Use Domain Names registry (https://www.iana.org/assignments/special-use-domain-names) or cite RFC 2606 / RFC 6761 directly, instead of claiming the reserved page lists the four TLDs.

---

## Summary

| # | Claim | URL | Page load | Status | Verdict |
| --- | --- | --- | --- | --- | --- |
| 1 | https://example.com opens with heading "Example Domain" | https://example.com | OK | OK | **Matches** — keep as written |
| 2 | IANA page lists .test, .example, .invalid, .localhost | https://www.iana.org/domains/reserved | OK | OK | **Does not match as written** — page has been redesigned. Re-point the guide to IANA's Special-Use Domain Names registry (https://www.iana.org/assignments/special-use-domain-names) or RFC 2606/6761. |

---

*Report generated as part of the onboarding-guide audit on 2026-11-11 (UTC). Re-run before publish if either page changes.*
