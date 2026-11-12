# Link Check Report — Developer Onboarding Guide "Further Reading"

**Date checked:** 2026-07-15
**Checked via:** Live fetch of both URLs (not from memory or cached knowledge)
**Purpose:** Fresh verification of two claims in the onboarding guide further-reading box before tomorrow release.

## Entry 1: https://example.com

- **URL:** https://example.com
- **Captured heading (verbatim):** Example Domain
- **Quoted body line:** This domain is for use in documentation examples without needing permission. This is not a service; avoid relying on it for testing and monitoring purposes.
- **Page loaded fine:** Yes — page retrieved successfully and content rendered.
- **Status:** OK
- **Verdict vs. guide claim:** Matches — The page opens with the heading "Example Domain", exactly as the guide states.

## Entry 2: https://www.iana.org/domains/reserved

- **URL:** https://www.iana.org/domains/reserved
- **Captured heading (verbatim):** IANA-managed Reserved Domains
- **Quoted body line:** Certain domains are set aside, and nominally registered to IANA, for specific policy or technical purposes.
- **Page loaded fine:** Yes — page retrieved successfully and content rendered.
- **Status:** OK (with a caveat)
- **Verdict vs. guide claim:** Partial match — does-not-match as worded. The page loaded fine and is about reserved and special-use domains, citing RFC 2606 and RFC 6761 (which define .test, .example, .invalid, and .localhost). However, the page does not explicitly list those four TLDs by name as "the four special-use top-level domains." It covers Example domains (example.com, example.org), Test IDN top-level domains, Policy-reserved domains, and a link to the separate Special-Use Domain Names registry.

  **Recommendation:** Update the guide wording to say the IANA page references RFC 2606/6761, where those four TLDs are defined, rather than claiming the page lists them verbatim.

## Summary

| URL | Heading (verbatim) | Loaded | Status | Matches guide claim? |
|-----|-------------------|--------|--------|---------------------|
| https://example.com | Example Domain | Yes | OK | Yes — exact match |
| https://www.iana.org/domains/reserved | IANA-managed Reserved Domains | Yes | OK (caveat) | Partial — page loads, but it does not enumerate .test/.example/.invalid/.localhost verbatim; it cites the RFCs that define them |

**Action for the guide:** Claim 1 is accurate as-is and can ship unchanged. Claim 2 holds in spirit (the IANA reserved-domains page is the authoritative source and cites RFC 2606/6761, which define those four TLDs), but the wording should be adjusted to reflect that the page references those domains via RFC 2606/6761 rather than listing them directly.
