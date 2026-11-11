# Link Check Report — Developer Onboarding Guide "Further Reading" Box

- **Checked:** 2026-07-15 (live HTTP fetch of each URL; no cached or requirements.io data)
- **Method:** Each URL was loaded fresh at check time. Verdicts compare the live page content against the claims currently published in the onboarding guide.
- **Repo:** `mcpmark-eval-liuhezi/web-audit-notes` → `docs/link-check.md`

## Entry 1: https://example.com

- **Load status:** OK — page fetched successfully and rendered.
- **Main heading (verbatim):** `Example Domain`
- **Quoted from body:** "This domain is for use in documentation examples without needing permission. This is not a service; avoid relying on it for testing and monitoring purposes."
- **Claim in guide:** https://example.com opens with the heading *'Example Domain'*.
- **Verdict:** ✅ **Matches.** The live page's main heading is exactly **Example Domain**, so this claim still holds.
- **Editor's note:** The body copy has changed from the older "This domain is for use in illustrative examples in documents…" wording. The page now also carries a caution: *"This is not a service; avoid relying on it for testing and monitoring purposes."* Consider adding this note to the guide.

## Entry 2: https://www.iana.org/domains/reserved

- **Load status:** OK — page fetched successfully and rendered.
- **Main heading (verbatim):** `IANA-managed Reserved Domains`
- **Quoted from body:** "Certain domains are set aside, and nominally registered to 'IANA', for specific policy or technical purposes."
- **Claim in guide:** The IANA page at this URL lists the four special-use top-level domains **.test, .example, .invalid** and **.localhost**.
- **Verdict:** ⚠️ **Does-not-match (partial).** The page's own heading is *"IANA-managed Reserved Domains"*, and the page does **not** present an enumeration of .test, .example, .invalid and .localhost as "the four special-use TLDs." Instead it describes *example domains* (per RFC 2606 / RFC 6761, e.g. example.com, example.org), *test IDN top-level domains*, and *policy-reserved domains*, and points readers to the separate **Special-Use Domain Names** registry (https://www.iana.org/assignments/special-use-domain-names) for the full list of special-use domains. those four TLDs are covered under RFC 2606, but that list is not displayed on this page.
- **Recommended fix for the guide:** reword to: *"IANA's reserved-domains page (https://www.iana.org/domains/reserved), which references RFC 2606/6761 for the special-use TLDs .test, .example, .invalid and .localhost; the authoritative registry is https://www.iana.org/assignments/special-use-domain-names."*

## Summary

| # | URL | Main heading (verbatim) | Load | Claim verdict |
|---|-----|--------------------------|------|---------------|
| 1 | https://example.com | Example Domain | OK | ✅ Matches — claim still holds |
| 2 | https://www.iana.org/domains/reserved | IANA-managed Reserved Domains | OK | ⚠️ Does-not-match as written — page does not list the four TLDs; cite the Special-Use Domain Names registry instead |

## Action items before go-live

1. Keep the https://example.com claim as-is (heading confirmed).
2. Update the IANA claim to reference RFC 2606/6761 and the Special-Use Domain Names registry (https://www.iana.org/assignments/special-use-domain-names).
3. Optionally add the note that example.com should not be used for testing/monitoring per the page's own guidance.
