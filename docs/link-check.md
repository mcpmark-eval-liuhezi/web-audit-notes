# Link Check Report — Onboarding Guide "Further Reading" Box

**Checked:** 2026-11-11 (UTC)
**Method:** Live fetch of both URLs on 2026-11-11; verdicts based on what the pages actually served at check time, not on prior memory.
**Repository:** `mcpmark-eval-liuhezi/web-audit-notes` (default branch: `main`)

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
| **Verdict vs. guide claim** | ✅ **Matches** — The page still opens with the heading **"Example Domain"**, exactly as the guide states. Claim holds. |

**Notes:** The heading is unchanged and still reads `Example Domain`. The body copy now reads: *"This domain is for use in documentation examples without needing permission. This is not a service; avoid relying on it for testing and monitoring purposes."* (The second sentence is a newer caveat worth noting in the guide if we ever suggest using example.com for automated link checks.)

---

## Entry 2 — https://www.iana.org/domains/reserved

| Field | Value |
| --- | --- |
| **URL** | https://www.iana.org/domains/reserved |
| **Page loaded** | ✅ OK — page retrieved successfully |
| **Main heading (verbatim)** | `IANA-managed Reserved Domains` |
| **Quoted body line** | "As described in RFC 2606 and RFC 6761, a number of domains such as example.com and example.org are maintained for documentation purposes. These domains may be used as illustrative examples in documents without prior coordination with us. They are not available for registration or transfer." |
| **Date checked** | 2026-11-11 |
| **Status** | ✅ OK (page loads fine) |
| **Verdict vs. guide claim** | ⚠️ **Does not match as written** — The page does load, but it does **not** enumerate the four special-use TLDs `.test`, `.example`, `.invalid` and `.localhost` on this page. Instead it points readers to a separate **Special-Use Domain Names** registry: *"There is additionally a Special-Use Domain Names registry documenting special-use domains designated by technical standards. For further information, see Special-Use Domain Names (RFC 6761)."* The four TLDs `.test`, `.example`, `.invalid`, `.localhost` are defined in **RFC 2606**, which this page references. |

**Recommended fix for the guide:** Reword the claim to something like: *"The IANA page at https://www.iana.org/domains/reserved explains IANA-managed reserved domains and points to the Special-Use Domain Names registry (https://www.iana.org/assignments/special-use-domain-names) and RFC 2606 / RFC 6761 for the four special-use top-level domains: `.test`, `.example`, `.invalid`, and `.localhost`."* The `.example` TLD is indeed mentioned implicitly via the "Example domains" section (example.com, example.org), and `.test`/`.invalid`/`.localhost` are covered under RFC 2606 as referenced by the page, but they are not *listed* on this page itself.

---

## Summary

| URL | Loaded? | Heading (verbatim) | Claim holds? |
| --- | --- | --- | --- |
| https://example.com | ✅ Yes | `Example Domain` | ✅ **Yes — matches** |
| https://www.iana.org/domains/reserved | ✅ Yes | `IANA-managed Reserved Domains` | ⚠️ **Partially — reword needed** (page references RFC 2606/6761 and a separate Special-Use Domain Names registry rather than listing the four TLDs inline) |

**Action for onboarding guide edit:** Claim 1 is still accurate and can ship as-is. Claim 2 should be updated to reference RFC 2606 / RFC 6761 and the Special-Use Domain Names registry at https://www.iana.org/assignments/special-use-domain-names so readers can find the actual list of `.test`, `.example`, `.invalid`, and `.localhost`.
