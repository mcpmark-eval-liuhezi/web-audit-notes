# Link Check Report — Developer Onboarding Guide, "Further Reading" Box

- **Date checked:** 2026-07-15
- **Method:** Live HTTP fetch of both URLs; headings captured verbatim from the rendered page (not from memory).
- **Repository:** `mcpmark-eval-liuhezi/web-audit-notes`
- **Committed file path:** `docs/link-check.md` (default branch: `main`)
- **Link to report:** https://github.com/mcpmark-eval-liuhezi/web-audit-notes/blob/main/docs/link-check.md

---

## Entry 1 — https://example.com

- **URL:** https://example.com
- **Page loaded:** OK (fetch succeeded, content rendered)
- **Captured main heading (verbatim):** `Example Domain`
- **Quoted line from body:** "This domain is for use in documentation examples without needing permission. This is not a service; avoid relying on it for testing and monitoring purposes."
- **Status:** OK
- **Verdict vs. guide's claim:** ✅ **MATCHES** — the page's main heading is exactly "Example Domain", so the guide's claim holds. (Note for the guide: the page now warns it is not a service and should not be relied on for testing/monitoring, so frame it as a documentation example domain only.)

## Entry 2 — https://www.iana.org/domains/reserved

- **URL:** https://www.iana.org/domains/reserved
- **Page loaded:** OK (fetch succeeded, content rendered)
- **Captured main heading (verbatim):** `IANA-managed Reserved Domains`
- **Quoted line from body:** "As described in RFC 2606 and RFC 6761, a number of domains such as example.com and example.org are maintained for documentation purposes."
- **Status:** OK
- **Verdict vs. guide's claim:** ⚠️ **PARTIAL MATCH — does not fully match as written** — the page loads fine and does cover reserved/example domains per RFC 2606 and RFC 6761, but it does **not** explicitly enumerate ".test, .example, .invalid and .localhost" as "the four special-use top-level domains" on this page. Those names are documented under RFC 2606/6761 and IANA's separate Special-Use Domain Names registry (`/assignments/special-use-domain-names`). Recommended guide rewording: "For documentation examples, use example.com/example.org (RFC 2606/6761); IANA's Special-Use Domain Names registry lists .test, .example, .invalid and .localhost."

---

## Summary

| URL | Loaded | Heading (verbatim) | Claim holds? |
| --- | --- | --- | --- |
| https://example.com | OK | Example Domain | ✅ Yes — matches |
| https://www.iana.org/domains/reserved | OK | IANA-managed Reserved Domains | ⚠️ Partial — page does not explicitly list the four TLDs; reword the claim |
