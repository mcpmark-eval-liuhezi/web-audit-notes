# Link Check Report — Developer Onboarding Guide: "Further Reading" Box

**Date checked:** November 12, 2026
**Source of truth:** Live fetch of both URLs on the date above (not from memory or cached copies).
**Repository:** [`mcpmark-eval-liuhezi/web-audit-notes`](https://github.com/mcpmark-eval-liuhezi/web-audit-notes)

---

## Entry 1: https://example.com

- **URL checked:** https://example.com
- **Page loaded:** OK (HTTP fetch succeeded; page rendered normally)
- **Main heading (verbatim):** `Example Domain`
- **Quoted line from body:** "This domain is for use in documentation examples without needing permission. This is not a service; avoid relying on it for testing and monitoring purposes."
- **Status:** OK
- **Verdict vs. guide's claim:** ✅ **Matches.** The page still opens with the heading **"Example Domain"**, exactly as the guide states. (Note: the body copy has been refreshed wording-wise — it now includes a note that the domain is not a service and shouldn't be relied on for testing/monitoring — but the heading itself is unchanged.)

## Entry 2: https://www.iana.org/domains/reserved

- **URL checked:** https://www.iana.org/domains/reserved
- **Page loaded:** OK (HTTP fetch succeeded; page rendered normally)
- **Main heading (verbatim):** `IANA-managed Reserved Domains`
- **Quoted line from body:** "As described in RFC 2606 and RFC 6761, a number of domains such as example.com and example.org are maintained for documentation purposes. These domains may be used as illustrative examples in documents without prior coordination with us. They are not available for registration or transfer."
- **Status:** OK
- **Verdict vs. guide's claim:** ⚠️ **Partially matches.** The page loaded fine and is directly relevant, but it does **not** explicitly list the four special-use top-level domains `.test`, `.example`, `.invalid`, and `.localhost` on this page. Instead, it refers readers to the separate **Special-Use Domain Names registry** (`/assignments/special-use-domain-names`) and to RFC 6761 for the full list of special-use domains. The page does discuss reserved/example domains (including example.com and example.org) and IDN test top-level domains, but the specific claim that this page "lists the four special-use top-level domains" is not准确 as written — the authoritative list lives in the linked Special-Use Domain Names registry and RFC 2606/6761, not on this reserved-domains page itself. **Recommendation:** update the guide's wording to point at the Special-Use Domain Names registry (or RFC 2606) for the definitive list of `.test`, `.example`, `.invalid`, and `.localhost`.

---

## Summary Table

| # | URL | Heading (verbatim) | Status | Guide's claim | Verdict |
|---|-----|--------------------|--------|---------------|---------|
| 1 | https://example.com | Example Domain | OK | Page opens with heading "Example Domain" | ✅ Matches |
| 2 | https://www.iana.org/domains/reserved | IANA-managed Reserved Domains | OK | Page lists .test, .example, .invalid, .localhost | ⚠️ Partially matches (see note above) |

## Notes for the Guide Authors

1. The example.com heading claim is still accurate and can stay as-is.
2. For the IANA claim, consider rewording to: *"The IANA page at https://www.iana.org/domains/reserved explains reserved and example domains; the definitive list of special-use top-level domains (.test, .example, .invalid, .localhost) is maintained in IANA's Special-Use Domain Names registry and RFC 2606."*
3. Both links were verified live on November 12, 2026 and are safe to include in the guide as of that date.
