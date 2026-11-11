# Link Check Report — Developer Onboarding Guide ("Further Reading" Box)

**Check date:** 2026-07-15 (UTC)
**Method:** Live HTTP fetch of both URLs performed 2026-07-15 (no reliance on prior memory or cached content).
**Repo:** `mcpmark-eval-liuhezi/web-audit-notes` (default branch: `main`)
**Pages verified:** 2

---

## Entry 1 — https://example.com

| Field | Value |
| --- | --- |
| **URL** | https://example.com |
| **Loaded OK?** | Yes — page retrieved successfully, no errors |
| **Main heading (verbatim)** | `Example Domain` |
| **Quoted line from body** | "This domain is for use in documentation examples without needing permission. This is not a service; avoid relying on it for testing and monitoring purposes." |
| **Date checked** | 2026-07-15 |
| **Status** | OK |
| **Guide's claim** | The page opens with the heading "Example Domain". |
| **Verdict** | **Matches** — the live page's main heading is exactly `Example Domain`, so this claim still holds. |

> Note for guide authors: the page body now adds a caveat — "This is not a service; avoid relying on it for testing and monitoring purposes." Worth a one-line note in the onboarding doc so readers don't build health checks against it.

## Entry 2 — https://www.iana.org/domains/reserved

| Field | Value |
| --- | --- |
| **URL** | https://www.iana.org/domains/reserved |
| **Loaded OK?** | Yes — page retrieved successfully, no errors |
| **Main heading (verbatim)** | `IANA-managed Reserved Domains` |
| **Quoted line from body** | "Certain domains are set aside, and nominally registered to “IANA”, for specific policy or technical purposes." |
| **Date checked** | 2026-07-15 |
| **Status** | OK (page loads), but claim does not hold |
| **Guide's claim** | The IANA page lists the four special-use top-level domains `.test`, `.example`, `.invalid` and `.localhost`. |
| **Verdict** | **Does-not-match** — this page does **not** enumerate `.test`, `.example`, `.invalid` and `.localhost` as "the four special-use TLDs". What it actually says:
  - It covers **example domains** (`example.com`, `example.org`) maintained for documentation purposes per **RFC 2606** and **RFC 6761**.
  - It documents **Test IDN top-level domains** (Arabic `إختبار`, Persian `آزمایشی`, Chinese `测试`, Russian `испытание`, Hindi `परीक्षा`, Greek `δοκιмή`, Korean `테스트`, Yiddish `טעסט`, Japanese `テスト`, Tamil `பரிட்சை`).
  - It describes **policy-reserved domains** registered to IANA/ICANN on policy grounds (e.g. `_country-name_.info`).
  - It points readers to a separate **[Special-Use Domain Names registry](https://www.iana.org/assignments/special-use-domain-names)** (per RFC 6761) as the authoritative list of special-use domains.

  The four names `.test`, `.example`, `.invalid`, `.localhost` are reserved by **RFC 2606**, but this specific IANA page does not present them as "the four special-use TLDs" — it instead references the dedicated special-use registry. **Recommendation:** reword the guide entry to say the IANA page describes IANA-managed reserved domains (including example domains per RFC 2606 / RFC 6761) and that the full special-use list lives in IANA's [Special-Use Domain Names registry](https://www.iana.org/assignments/special-use-domain-names).

## Summary

| # | URL | Heading (verbatim) | Status | Claim verdict |
| --- | --- | --- | --- | --- |
| 1 | https://example.com | `Example Domain` | OK | **Matches** — keep as-is. |
| 2 | https://www.iana.org/domains/reserved | `IANA-managed Reserved Domains` | OK (loads) | **Does-not-match** — reword to reference RFC 2606 / the Special-Use Domain Names registry instead of claiming it lists the four special-use TLDs. |

---

*Generated 2026-07-15 for review ahead of the onboarding guide shipping tomorrow morning.*
