# Link Check — Developer Onboarding Guide "Further Reading" Box

**Date checked:** 2026-11-10 (UTC)
**Method:** live fetch of each URL used today; headings and quotes captured verbatim from the fetched content.
**Purpose:** fresh, live verification of the two claims in the guide's "further reading" box before the ship date.

> **Headline:** claim 1 still holds (page shows "Example Domain"); claim 2 does not — the IANA reserved-domains page no longer enumerates .test, .example, .invalid and .localhost.

---

## Entry 1 — https://example.com

| Field | Value |
|---|---|
| URL | https://example.com |
| Page loaded | OK (no error) |
| Main heading (verbatim) | `Example Domain` |
| Quoted line from body | "This domain is for use in documentation examples without needing permission. This is not a service; avoid relying on it for testing and monitoring purposes." |
| Guide's claim | https://example.com opens with the heading 'Example Domain'. |
| Status | OK |
| Verdict | **Matches** |

**Reading:** the live page still opens with the "Example Domain" title, followed by the IANA-style notice that the domain is for documentation examples without needing permission, and that it is not a service. The guide's claim as written is accurate.

---

## Entry 2 — https://www.iana.org/domains/reserved

| Field | Value |
|---|---|
| URL | https://www.iana.org/domains/reserved |
| Page loaded | OK (no error) |
| Main heading (verbatim) | `IANA-managed Reserved Domains` |
| Quoted line from body | "As described in RFC 2606 and RFC 6761, a number of domains such as example.com and example.org are maintained for documentation purposes." |
| Guide's claim | this page lists the four special-use top-level domains .test, .example, .invalid and .localhost. |
| Status | OK (page loaded fine) |
| Verdict | **Does not match** |

**Reading:** the live page does **not** contain the four names from the claim. Its actual sections are "Example domains", "Test IDN top-level domains", "Policy-reserved domains", and "Other Special-Use Domains". The special-use names are covered in IANA's separate Special-Use Domain Names registry (referenced from this page under RFC 6761), not listed on the reserved-domains page itself. Recommend rewording the guide's pointer to the registry at https://www.iana.org/assignments/special-use-domain-names.

---

## Notes for the guide's editor

- **Claim 1 is fine** — keep the example.com link and its "Example Domain" heading text.
- **Claim 2 needs rewording.** Either point at the registry you actually mean — "the special-use top-level domains listed in IANA's Special-Use Domain Names registry (RFC 6761), at https://www.iana.org/assignments/special-use-domain-names" — or describe what the reserved-domains page covers (example.com/.net/.org, the Test IDN table, policy-reserved domains).
