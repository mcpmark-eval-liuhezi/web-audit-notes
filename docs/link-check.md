# Link Check Report — Developer Onboarding Guide ("Further Reading" Box)

- **Date checked:** 2026-07-15
- **Method:** Live fetch of each URL at report time (no reliance on cached memory of prior content).
- **Overall result:** Both URLs loaded successfully (status OK). Claim 1 still holds; Claim 2 does **not** hold as written and should be reworded before shipping.

---

## Entry 1 — https://example.com

- **URL:** https://example.com
- **Page loaded:** OK (fetched live; content retrieved without error)
- **Main heading (verbatim):** `Example Domain`
- **Quoted line from body:** "This domain is for use in documentation examples without needing permission. This is not a service; avoid relying on it for testing and monitoring purposes."
- **Guide's claim:** The page opens with the heading "Example Domain".
- **Verdict:** **Matches.** The captured heading is exactly "Example Domain", so this claim still holds. No change needed.

---

## Entry 2 — https://www.iana.org/domains/reserved

- **URL:** https://www.iana.org/domains/reserved
- **Page loaded:** OK (fetched live; content retrieved without error)
- **Main heading (verbatim):** `IANA-managed Reserved Domains`
- **Quoted line from body:** "As described in RFC 2606 and RFC 6761, a number of domains such as example.com and example.org are maintained for documentation purposes."
- **Guide's claim:** The IANA page at this URL lists the four special-use top-level domains .test, .example, .invalid and .localhost.
- **Verdict:** **Does-not-match.** The page loads fine and its heading is "IANA-managed Reserved Domains", but the page body does **not** enumerate .test, .example, .invalid, and .localhost as a list of four special-use TLDs. Instead, it covers: Example domains (example.com, example.org, per RFC 2606/6761), Test IDN top-level domains (e.g. إختبار / xn--kgbechtv, 测试 / xn--0zwm56d, испытание / xn--80akhbyknj4f, etc.), Policy-reserved domains, and points readers to a separate **Special-Use Domain Names registry** (/assignments/special-use-domain-names) for the full list of special-use domains per RFC 6761. The names .test/.example/.invalid/.localhost are referenced indirectly via RFC 2606/6761, but they are not listed on this page. Recommend rewording the guide's claim to: "The IANA Reserved Domains page (iana.org/domains/reserved) explains IANA-managed reserved domains per RFC 2606/6761 and links to the Special-Use Domain Names registry for the full list of special-use TLDs such as .test, .example, .invalid and .localhost."

---

## Summary Table

| # | URL | Heading (verbatim) | Loaded | Status | Claim verdict |
|---|-----|--------------------|--------|--------|---------------|
| 1 | https://example.com | Example Domain | Yes | OK | Matches |
| 2 | https://www.iana.org/domains/reserved | IANA-managed Reserved Domains | Yes | OK | Does-not-match (page does not list .test/.example/.invalid/.localhost; see separate registry) |

## Recommended Action Before Ship

1. Keep Claim 1 as-is: https://example.com does open with the heading "Example Domain".
2. Update Claim 2: reword to reference the IANA-managed Reserved Domains page and its linked Special-Use Domain Names registry (RFC 6761) rather than stating the page lists the four TLDs.
