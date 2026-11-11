# Link Check Report — Developer Onboarding Guide ("Further Reading" Box)

- **Date checked (live):** 2026-11-11 (UTC; checks run ~21:14 UTC)
- **Method:** Fresh live fetch of both URLs on 2026-11-11 (not from memory or cache).
- **Scope:** The two claims currently in the guide's "further reading" box.
- **Repo:** `mcpmark-eval-liuhezi/web-audit-notes` (default branch: `main`)

---

## Claim 1 — https://example.com

- **URL:** https://example.com
- **Page loaded:** OK (page returned successfully, HTTP fetch succeeded)
- **Main heading (verbatim):** `Example Domain`
- **Quoted line from body:** "This domain is for use in documentation examples without needing permission."
- **Date checked:** 2026-11-11
- **Status:** OK
- **Verdict vs. guide's claim:** **Matches — keep as written.** The page still opens with the heading "Example Domain", exactly as the guide states. (Caveat for the guide: example.com has been redesigned — the heading now renders as a page title with a short paragraph beneath it rather than traditional `<h1>` markup, but the visible text "Example Domain" is still correct.)

---

## Claim 2 — https://www.iana.org/domains/reserved

- **URL:** https://www.iana.org/domains/reserved
- **Page loaded:** OK (page returned successfully)
- **Main heading (verbatim):** `IANA-managed Reserved Domains`
- **Quoted line from body:** "Certain domains are set aside, and nominally registered to "IANA", for specific policy or technical purposes."
- **Date checked:** 2026-11-11
- **Status:** FAIL (content mismatch vs. guide's claim)
- **Verdict vs. guide's claim:** **Does not match.** This page no longer presents `.test`, `.example`, `.invalid`, and `.localhost` as an enumerated set of special-use top-level domains. What it actually shows is:
  - An **"Example domains"** section covering `example.com` and `example.org` (per RFC 2606 / RFC 6761) — these are second-level documentation domains, not TLDs.
  - A **"Test IDN top-level domains"** table of non-Latin IDN variants (إختبار / xn--kgbechtv, آزمایشی / xn--hgbk6aj7f53bba, 测试 / xn--0zwm56d, 測試 / xn--g6w251d, испытание, परीक्षा, δοκιμή, 테스트, טעסט, テスト, பரிட்சை, etc.) — not the ASCII `.test` TLD.
  - A **"Policy-reserved domains"** section on domains reserved under policy grounds.
  - A **"Other Special-Use Domains"** pointer to a separate registry at `/assignments/special-use-domain-names` (RFC 6761).

  The four root TLDs live in that separate registry, not on the reserved page. Cross-reference checked live: IANA's **Special-Use Domain Names** registry (https://www.iana.org/assignments/special-use-domain-names) does list `test.` (RFC 6761), `example.` (RFC 6761), `invalid.` (RFC 6761), and `localhost.` (RFC 6761) — along with many others (alt., home.arpa., example.com./net./org., onion., etc.).

  **Recommended fix for the guide:** link to IANA's Special-Use Domain Names registry (https://www.iana.org/assignments/special-use-domain-names) or cite RFC 2606 / RFC 6761 directly, instead of claiming the reserved page lists the four TLDs.

---

## Summary

| # | Claim | URL | Page loaded | Status | Verdict |
| --- | --- | --- | --- | --- | --- |
| 1 | https://example.com opens with heading "Example Domain" | https://example.com | OK | OK | **Matches** — keep as written |
| 2 | IANA page lists .test, .example, .invalid, .localhost | https://www.iana.org/domains/reserved | OK | FAIL | **Does not match** — page restructured; re-point the guide to IANA's Special-Use Domain Names registry (https://www.iana.org/assignments/special-use-domain-names) or RFC 2606/6761 |

---

*Report committed 2026-11-11 (UTC) as part of the onboarding-guide audit. Re-run before publish if either page changes.*
