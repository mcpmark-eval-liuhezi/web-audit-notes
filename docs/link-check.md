# Link Check Report — Developer Onboarding Guide "Further Reading" Box

**Checked:** 2026-11-11 (UTC) — live fetch performed immediately before this report was committed.
**Method:** Both URLs were loaded live at check time (not from memory); verdicts reflect exactly what each page served.
**Repo:** `mcpmark-eval-liuhezi/web-audit-notes` (default branch: `main`)
**Pages verified:** 2

---

## Entry 1 — https://example.com

| Field | Value |
| --- | --- |
| **URL** | https://example.com |
| **Page loaded** | ✅ OK — page retrieved successfully |
| **Main heading (verbatim)** | `Example Domain` |
| **Quoted body line** | "This domain is for use in documentation examples without needing permission. This is not a service; avoid relying on it for testing and monitoring purposes." |
| **Date checked** | 2026-11-11 |
| **Status** | ✅ OK |
| **Guide's claim** | The page opens with the heading "Example Domain". |
| **Verdict** | ✅ **Matches** — the live page's main heading is exactly `Example Domain`, so this claim still holds. |

> Note for guide authors: the page body now adds a caveat — "This is not a service; avoid relying on it for testing and monitoring purposes." Worth a one-line note in the onboarding doc so readers don't build health checks against it.

---

## Entry 2 — https://www.iana.org/domains/reserved

| Field | Value |
| --- | --- |
| **URL** | https://www.iana.org/domains/reserved |
| **Page loaded** | ✅ OK — page retrieved successfully |
| **Main heading (verbatim)** | `IANA-managed Reserved Domains` |
| **Quoted body line** | "Certain domains are set aside, and nominally registered to “IANA”, for specific policy or technical purposes." |
| **Date checked** | 2026-11-11 |
| **Status** | ✅ OK (page loads), but the claim does not hold as written |
| **Guide's claim** | The IANA page lists the four special-use top-level domains `.test`, `.example`, `.invalid` and `.localhost`. |
| **Verdict** | ⚠️ **Does-not-match as written** — this page does **not** enumerate `.test`, `.example`, `.invalid` and `.localhost` as "the four special-use TLDs". What it actually says: it covers **example domains** (`example.com`, `example.org`) maintained for documentation purposes per **RFC 2606** and **RFC 6761**; it documents **Test IDN top-level domains** (Arabic `إختبار`, Persian `آزمایشی`, Chinese `测试`, Russian `испытание`, Hindi `परीक्षा`, Greek `δοκιмή`, Korean `테스트`, Yiddish `טעסט`, Japanese `テスト`, Tamil `பரிட்சை`); it describes **policy-reserved domains** registered to IANA/ICANN on policy grounds (e.g. `_country-name_.info`); and it points readers to a separate **[Special-Use Domain Names registry](https://www.iana.org/assignments/special-use-domain-names)** (per RFC 6761) as the authoritative list of special-use domains. The four names `.test`, `.example`, `.invalid`, `.localhost` are reserved by **RFC 2606**, but this specific IANA page does not present them as "the four special-use TLDs" — it instead references the dedicated special-use registry. **Recommendation:** reword the guide entry to say the IANA page describes IANA-managed reserved domains (including example domains per RFC 2606 / RFC 6761) and that the full special-use list lives in IANA's [Special-Use Domain Names registry](https://www.iana.org/assignments/special-use-domain-names). |

---

## Summary

| # | URL | Heading (verbatim) | Status | Claim verdict |
| --- | --- | --- | --- | --- |
| 1 | https://example.com | `Example Domain` | ✅ OK | ✅ **Matches** — keep as-is. |
| 2 | https://www.iana.org/domains/reserved | `IANA-managed Reserved Domains` | ✅ OK (loads) | ⚠️ **Does-not-match** — reword to reference RFC 2606 / the Special-Use Domain Names registry instead of claiming it lists the four special-use TLDs. |

---

*Generated 2026-11-11 for review ahead of the onboarding guide shipping.*
