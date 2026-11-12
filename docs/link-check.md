# Link Check Report — Developer Onboarding Guide "Further Reading"

**Date checked:** 2026-07-15
**Purpose:** Live verification of the two claims in the onboarding guide's further reading box before shipped release.
**Method:** Both pages were loaded live at check time (not from memory or cached documentation). Status OK = page loaded successfully and content was captured.

---

## Entry 1: https://example.com

- **URL:** https://example.com
- **Captured heading (verbatim):** `Example Domain`
- **Quoted line from body:** "This domain is for use in documentation examples without needing permission."
- **Page loaded fine:** Yes (OK)
- **Guide's claim:** The page opens with the heading 'Example Domain'.
- **Verdict:** ✅ **Matches** — The main heading on https://example.com is exactly `Example Domain`, word for word. The claim holds.
- **Notes:** The page body now also includes a caution: "This is not a service; avoid relying on it for testing and monitoring purposes." The heading itself is unchanged, so the guide's claim remains accurate.

---

## Entry 2: https://www.iana.org/domains/reserved

- **URL:** https://www.iana.org/domains/reserved
- **Captured heading (verbatim):** `IANA-managed Reserved Domains`
- **Quoted line from body:** "As described in RFC 2606 and RFC 6761, a number of domains such as example.com and example.org are maintained for documentation purposes."
- **Page loaded fine:** Yes (OK)
- **Guide's claim:** The IANA page at this URL lists the four special-use top-level domains .test, .example, .invalid and .localhost.
- **Verdict:** ⚠️ **Partial match / does not fully match as stated** — The page loaded fine and is titled "IANA-managed Reserved Domains," and it does reference RFC 2606 and RFC 6761 (which define .test, .example, .invalid, and .localhost) and discusses example domains, test IDN top-level domains, and policy-reserved domains. However, this page does not explicitly enumerate or list the four special-use TLDs .test, .example, .invalid, and .localhost as its content. Instead, it points readers to the separate **Special-Use Domain Names registry** (/assignments/special-use-domain-names) for the full list of special-use domains designated by technical standards. **Recommendation:** Update the guide's claim to say the IANA reserved domains page references RFC 2606/6761 and links to the Special-Use Domain Names registry, where .test, .example, .invalid, and .localhost are listed, rather than saying the page itself lists them.
- **Notes:** The page also covers example.com/example.org (documentation purposes), Test IDN top-level domains (Arabic, Persian, Chinese, Russian, Hindi, Greek, Korean, Yiddish, Japanese, Tamil), and policy-reserved domains. The four special-use TLDs are covered under RFC 6761, which the page cites.

---

## Summary Table

| # | URL | Heading (verbatim) | Status | Claim verdict |
|---|-----|--------------------|--------|---------------|
| 1 | https://example.com | Example Domain | OK | ✅ Matches |
| 2 | https://www.iana.org/domains/reserved | IANA-managed Reserved Domains | OK | ⚠️ Partial match — page references the relevant RFCs and links to the Special-Use Domain Names registry, but does not explicitly list .test, .example, .invalid, .localhost |

## Action Items Before Shipping

1. **example.com claim:** No change needed — heading is still "Example Domain" exactly.
2. **IANA reserved domains claim:** Consider rewording to reflect that the page cites RFC 2606/6761 and directs readers to the Special-Use Domain Names registry for the explicit list of .test, .example, .invalid, and .localhost.
3. This report is committed at `docs/link-check.md` in this repository for review.
