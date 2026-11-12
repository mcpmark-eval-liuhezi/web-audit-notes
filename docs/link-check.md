# Link-Check Report: Developer Onboarding Guide — "Further Reading" Box

**Date checked:** 2026-11-12
**Auditor:** Automated live verification (MCP fetch tools)
**Purpose:** Fresh, live verification of the two claims in the onboarding guide's "further reading" box before tomorrow's ship.

---

## Entry 1: https://example.com

- **URL:** https://example.com
- **Captured heading (verbatim):** `Example Domain`
- **Quoted line from body:** “This domain is for use in documentation examples without needing permission. This is not a service; avoid relying on it for testing and monitoring purposes.”
- **Page loaded fine:** Yes — HTTP fetch succeeded; heading and body text rendered as expected.
- **Status:** OK
- **Verdict vs. guide's claim:** **Matches.** The page opens with the heading "Example Domain", exactly as the guide states.
- **Editor's note:** The page now also warns that it is “not a service; avoid relying on it for testing and monitoring purposes.” Consider adding this caveat to the guide.

## Entry 2: https://www.iana.org/domains/reserved

- **URL:** https://www.iana.org/domains/reserved
- **Captured heading (verbatim):** `IANA-managed Reserved Domains`
- **Quoted line from body:** “As described in RFC 2606 and RFC 6761, a number of domains such as example.com and example.org are maintained for documentation purposes.”
- **Page loaded fine:** Yes — HTTP fetch succeeded; the page rendered with full navigation and content.
- **Status:** OK (page loads), but **claim accuracy is partial** — see verdict below.
- **Verdict vs. guide's claim:** **Does-not-match (partially).** The page does discuss IANA-managed reserved domains and special-use domains, and it references RFC 2606 and RFC 6761 (which define .test, .example, .invalid, and .localhost), but this specific page does **not** explicitly list the four special-use top-level domains .test, .example, .invalid, and .localhost. Those are documented in RFC 2606 / RFC 6761 and in IANA's separate Special-Use Domain Names registry (/assignments/special-use-domain-names), which this page only links to.
- **Recommendation:** Update the guide's claim to say the IANA reserved-domains page (per RFC 2606/6761) covers special-use domains like .test, .example, .invalid, and .localhost, and link to the Special-Use Domain Names registry for the authoritative list.

---

## Summary

| URL | Heading (verbatim) | Loaded | Status | Matches guide's claim? |
| --- | --- | --- | --- | --- |
| https://example.com | Example Domain | Yes | OK | Yes — matches exactly |
| https://www.iana.org/domains/reserved | IANA-managed Reserved Domains | Yes | OK | Partially — page loads, but doesn't explicitly enumerate .test/.example/.invalid/.localhost |

**Action items before shipping:**
1. The example.com claim is still accurate and can ship as-is.
2. Revisit the IANA page claim: either reword it to reference RFC 2606/6761 and the Special-Use Domain Names registry, or link those resources directly from the guide.
