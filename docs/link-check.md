# Link Check Report — Developer Onboarding Guide "Further Reading" Box

- **Date checked:** 2026-07-15
- **Checked by:** Automated live verification (MCP fetch tools)
- **Repository:** mcpmark-eval-liuhezi/web-audit-notes
- **File:** `docs/link-check.md`

---

## Entry 1: https://example.com

- **URL:** https://example.com
- **Captured heading (verbatim):** `Example Domain`
- **Quoted body line:** "This domain is for use in documentation examples without needing permission. This is not a service; avoid relying on it for testing and monitoring purposes."
- **Page loaded:** OK (loaded successfully)
- **Status:** OK
- **Verdict vs. guide's claim:** ✅ **Matches** — The page opens with the heading "Example Domain", exactly as the guide states.

## Entry 2: https://www.iana.org/domains/reserved

- **URL:** https://www.iana.org/domains/reserved
- **Captured heading (verbatim):** `IANA-managed Reserved Domains`
- **Quoted body line:** "As described in RFC 2606 and RFC 6761, a number of domains such as example.com and example.org are maintained for documentation purposes. These domains may be used as illustrative examples in documents without prior coordination with us."
- **Page loaded:** OK (loaded successfully)
- **Status:** OK (page loads fine), but ⚠️ **Claim partially does not match** — The page discusses IANA-managed reserved domains and references RFC 2606 and RFC 6761 (which define the special-use TLDs .test, .example, .invalid, and .localhost), but it does not present an explicit list of those four TLDs. It instead points to a separate Special-Use Domain Names registry (`/assignments/special-use-domain-names`) for the full list. Recommend updating the guide's wording to say the page references RFC 2606/6761 and IANA's Special-Use Domain Names registry rather than claiming it "lists" the four TLDs.

---

## Summary

| URL | Heading (verbatim) | Loaded | Status | Guide claim |
|---|---|---|---|---|
| https://example.com | Example Domain | Yes | OK | ✅ Matches |
| https://www.iana.org/domains/reserved | IANA-managed Reserved Domains | Yes | OK (content nuance) | ⚠️ Partially does not match |

## Recommendation

1. The example.com claim is accurate and can ship as-is.
2. For the IANA page, consider rewording the guide to: "The IANA page at https://www.iana.org/domains/reserved explains IANA-managed reserved domains and references RFC 2606 and RFC 6761, which define the special-use top-level domains .test, .example, .invalid, and .localhost."
