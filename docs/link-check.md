# Link Check — Developer Onboarding Guide "Further Reading" Box

**Date checked:** 2026-09-22 (UTC)
**Method:** live fetches of each page on 2026-09-22; headings and quotes captured verbatim from the fetched content.
**Purpose:** verify the two claims in the guide's "further reading" box before publication.

---

## Entry 1 — https://example.com

| Field | Value |
|---|---|
| URL | https://example.com |
| Page loaded | OK |
| Main heading (verbatim) | Example Domain |
| Quoted line from body | "This domain is for use in documentation examples without needing permission." |
| Guide's claim | https://example.com opens with the heading 'Example Domain' |
| Verdict | **MATCHES** — the page does open with the heading "Example Domain". |

---

## Entry 2 — https://www.iana.org/domains/reserved

| Field | Value |
|---|---|
| URL | https://www.iana.org/domains/reserved |
| Page loaded | OK |
| Main heading (verbatim) | IANA-managed Reserved Domains |
| Quoted line from body | "Certain domains are set aside, and nominally registered to “IANA”, for specific policy or technical purposes." |
| Guide's claim | this page lists the four special-use top-level domains .test, .example, .invalid and .localhost |
| Verdict | **DOES NOT MATCH** — the page contains no list of .test, .example, .invalid or .localhost. Those four names (and many more) appear in IANA's separate Special-Use Domain Names registry at https://www.iana.org/assignments/special-use-domain-names (registry last updated 2026-05-22, per RFC 6761), which this page only links to. |

---

## Notes for the guide's editor

- Claim 1 is still accurate and can ship as-is.
- Claim 2 should be corrected: point the guide to https://www.iana.org/assignments/special-use-domain-names for the .test / .example / .invalid / .localhost list, or reword the claim to say the reserved-domains page covers example.com/.net/.org, Test IDN TLDs, and policy-reserved domains.
