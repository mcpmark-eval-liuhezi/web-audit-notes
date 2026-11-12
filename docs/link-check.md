# Link Check Report — Developer Onboarding Guide "Further Reading" Box

**Date checked:** 2026-07-15
**Method:** Live verification by fetching both URLs today (not from memory).
**Purpose:** Verify two claims in the onboarding guide's "further reading" box before it ships tomorrow.

## Page 1: https://example.com

- **URL:** https://example.com
- **Loaded OK:** Yes — the page loaded successfully.
- **Main heading (verbatim):** `Example Domain`
- **Quoted line from body:** "This domain is for use in documentation examples without needing permission. This is not a service; avoid relying on it for testing and monitoring purposes."
- **Guide's claim:** The page opens with the heading 'Example Domain'.
- **Verdict:** ✅ **Matches.** The live page's main heading is exactly "Example Domain", so this claim still holds.
- **Editorial note:** The page now also cautions that it is not a service and should not be relied on for testing or monitoring. Consider adding a caveat in the guide that example.com is for documentation examples only.

## Page 2: https://www.iana.org/domains/reserved

- **URL:** https://www.iana.org/domains/reserved
- **Loaded OK:** Yes — the page loaded successfully.
- **Main heading (verbatim):** `IANA-managed Reserved Domains`
- **Quoted line from body:** "Certain domains are set aside, and nominally registered to \"IANA\", for specific policy or technical purposes."
- **Guide's claim:** The IANA page at this URL lists the four special-use top-level domains .test, .example, .invalid and .localhost.
- **Verdict:** ⚠️ **Partially matches (needs refinement).** The page loads fine and covers reserved and special-use domains, citing RFC 2606 and RFC 6761, and points to the separate IANA Special-Use Domain Names registry. That registry (https://www.iana.org/assignments/special-use-domain-names) does explicitly list `example.`, `invalid.`, `localhost.`, and `test.` (along with many other names). However, the reserved domains page itself does not enumerate those four TLDs as a list; it discusses example domains, test IDN top-level domains, and policy-reserved domains, and defers the full special-use list to the Special-Use Domain Names registry. Recommend the guide either link to the special-use registry directly or rephrase to say IANA's reserved domains page (citing RFC 2606/6761) covers .test, .example, .invalid, and .localhost.

## Supporting reference checked

- IANA Special-Use Domain Names registry: https://www.iana.org/assignments/special-use-domain-names/special-use-domain-names.xml — confirms `example.`, `invalid.`, `localhost.`, and `test.` are listed there.

## Summary table

| URL | Loaded | Heading (verbatim) | Status | Claim verdict |
|-----|--------|--------------------|--------|---------------|
| https://example.com | OK | Example Domain | OK | Matches |
| https://www.iana.org/domains/reserved | OK | IANA-managed Reserved Domains | OK | Partially matches — page loads and covers the topic, but the four TLDs are listed in IANA's separate Special-Use Domain Names registry rather than enumerated on this page |

## Recommended guide edits

1. Keep the example.com claim as-is; optionally add a note that the page advises not to rely on it for testing or monitoring.
2. Update the IANA reference to point to https://www.iana.org/assignments/special-use-domain-names for the explicit list of .test, .example, .invalid, and .localhost, or rephrase to attribute the list to RFC 2606/6761 as documented on the reserved domains page.
