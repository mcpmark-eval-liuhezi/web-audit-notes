# Link Check Report — Developer Onboarding Guide "Further Reading" Box

**Repository:** `mcpmark-eval-liuhezi/web-audit-notes`  
**File:** `docs/link-check.md`  
**Date checked:** 2026-07-15  
**Method:** Live fetch of each URL at time of writing (verified fresh, not from memory or cached documentation).

## Summary

| # | URL | Captured heading (verbatim) | Page loaded? | Verdict vs. guide claim |
|---|-----|---------------------------|--------------|--------------------------|
| 1 | https://example.com | `Example Domain` | Yes — OK | **Matches** |
| 2 | https://www.iana.org/domains/reserved | `IANA-managed Reserved Domains` | Yes — OK | **Does not match** (as worded) |

## Entry 1: https://example.com

- **Captured main heading (verbatim):** `Example Domain`
- **Quoted line from body:** "This domain is for use in documentation examples without needing permission. This is not a service; avoid relying on it for testing and monitoring purposes."
- **Page loaded:** Yes — fetch succeeded (`ok: true`), content retrieved.
- **Guide's claim:** The page opens with the heading '$(Example Domain)'.
- **Verdict:** **Matches.** The main heading on https://example.com is exactly `Example Domain`, so this part of the guide's claim still holds.
- **Notes:** The body copy has been updated relative to older versions of the page; it now includes a caveat: "This is not a service; avoid relying on it for testing and monitoring purposes." If the onboarding guide suggests using example.com for live tests, consider flagging that it should not be relied on for testing/monitoring.

## Entry 2: https://www.iana.org/domains/reserved

- **Captured main heading (verbatim):** `IANA-managed Reserved Domains`
- **Quoted line from body:** "As described in RFC 2606 and RFC 6761, a number of domains such as example.com and example.org are maintained for documentation purposes."
- **Page loaded:** Yes — fetch succeeded (`ok: true`), content retrieved.
- **Guide's claim:** The IANA page lists the four special-use top-level domains `.test`, `.example`, `.invalid` and `.localhost`.
- **Verdict:** **Does not match (as stated).** The page does **not** enumerate `.test`, `.example`, `.invalid` and `.localhost` as a four-item list. Instead, it explains that such domains are covered by **RFC 2606** and **RFC 6761**, and points readers to a separate **Special-Use Domain Names** registry at `/assignments/special-use-domain-names`. The page's own sections cover: *Example domains*, *Test IDN top-level domains*, *Policy-reserved domains*, and *Other Special-Use Domains*. The four names `.test`, `.example`, `.invalid` and `.localhost` are not explicitly listed anywhere on this page.
- **Recommendation:** Update the guide's wording to say the IANA Reserved Domains page (per RFC 2606 / RFC 6761) documents example domains and points to the Special-Use Domain Names registry for the full list of special-use domains, rather than claiming the page lists .test, .example, .invalid and .localhost.

## Action items before shipping

1. Keep the https://example.com heading claim — it verified live and still matches.
2. Revise the https://www.iana.org/domains/reserved description to reference RFC 2606 / RFC 6761 and the Special-Use Domain Names registry (`/assignments/special-use-domain-names`) instead of a four-item list.
3. Optionally add a note that example.com now carries a disclaimer against relying on it for testing and monitoring purposes.
