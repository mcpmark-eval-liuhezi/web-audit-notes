# Link Check Report — Developer Onboarding Guide ("Further Reading" Box)

**Date checked:** 2026-07-15
**Method:** Live fetch of each URL on the day of checking (not from memory or cached documentation).
**Repository:** `mcpmark-eval-liuhezi/web-audit-notes` (default branch: `main`)
**File:** `docs/link-check.md`

---

## Entry 1: https://example.com

- **URL:** https://example.com
- **Load status:** OK — page loaded successfully.
- **Captured main heading (verbatim):** `Example Domain`
- **Quoted line from body:** "This domain is for use in documentation examples without needing permission. This is not a service; avoid relying on it for testing and monitoring purposes."
- **Guide's claim:** https://example.com opens with the heading 'Example Domain'.
- **Verdict:** **Matches.** The claim held at time of check. The page's `<h1>` reads exactly `Example Domain`, so this part of the guide is still accurate.

---

## Entry 2: https://www.iana.org/domains/reserved

- **URL:** https://www.iana.org/domains/reserved
- **Load status:** OK — page loaded successfully.
- **Captured main heading (verbatim):** `IANA-managed Reserved Domains`
- **Quoted line from body:** "Certain domains are set aside, and nominally registered to “IANA”, for specific policy or technical purposes."
- **Guide's claim:** The IANA page at https://www.iana.org/domains/reserved lists the four special-use top-level domains .test, .example, .invalid and .localhost.
- **Verdict:** **Does not match as stated.** The page loaded fine and its heading is "IANA-managed Reserved Domains," but it does not enumerate .test, .example, .invalid, and .localhost as "four special-use top-level domains." Instead, it covers: example domains (example.com, example.org) maintained for documentation purposes per RFC 2606 and RFC 6761; Test IDN top-level domains (xn--kgbechtv, xn--hgbk6aj7f53bba, xn--0zwm56d, xn--g6w251d, xn--80akhbyknj4f, xn--11b5bs3a9aj6g, xn--jxalpdlp, xn--9t4b11yi5a, xn--deba0ad, xn--zckzah, xn--hlcj6aya9esc7a); and policy-reserved domains. The page explicitly points to a separate **Special-Use Domain Names registry** (`/assignments/special-use-domain-names`) and RFC 6761 for the full list of special-use domains. Recommendation: reword the guide to say the IANA Special-Use Domain Names registry (referenced from the reserved domains page) documents .test, .example, .invalid, and .localhost, rather than claiming this page lists them.

---

## Summary

| # | URL | Loaded | Heading (verbatim) | Claim verdict |
|---|-----|--------|--------------------|---------------|
| 1 | https://example.com | OK | `Example Domain` | Matches |
| 2 | https://www.iana.org/domains/reserved | OK | `IANA-managed Reserved Domains` | Does not match as stated (page discusses example domains, Test IDN TLDs, and policy-reserved domains; points to the separate Special-Use Domain Names registry for .test/.example/.invalid/.localhost) |

**Action for onboarding guide update:** Claim 1 is still accurate. Claim 2 should be rephrased to reference IANA's Special-Use Domain Names registry (linked from the reserved domains page) or RFC 6761, which is where .test, .example, .invalid, and .localhost are formally documented.
