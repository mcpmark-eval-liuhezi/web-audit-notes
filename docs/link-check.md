# Link Check — Developer Onboarding Guide "Further Reading" Box

**Date checked:** 2026-11-10 (UTC)
**Method:** Live fetch of each URL; headings and quotes captured verbatim from the fetched content. Both pages loaded without error.
**Purpose:** Fresh, live verification of the two claims in the guide's "further reading" box before the ship date.

---

## Entry 1 — https://example.com

| Field | Value |
|---|---|
| URL | https://example.com |
| Page loaded | OK (no error) |
| Main heading (verbatim) | **None.** The live page contains **no heading element at all**. "Example Domain" survives only as the HTML document title (`<title>Example Domain</title>`). |
| Quoted line from body | "This domain is for use in documentation examples without needing permission." |
| Guide's claim | https://example.com opens with the heading 'Example Domain'. |
| Verdict | **DOES NOT MATCH (as literally stated)** |

**Reading:** the current live page still carries the same message as the old one ("This domain is for use in documentation examples without needing permission…"), but the step the claim relies on — the `<h1>` — is gone; "Example Domain" remains only the browser-tab title. If the guide's intent is simply "point readers at a reserved domain for documentation examples," the URL is still fine and should be reworded, not deleted. If the intent is literally "the page opens with the heading 'Example Domain'", that wording is now false.

## Entry 2 — https://www.iana.org/domains/reserved

| Field | Value |
|---|---|
| URL | https://www.iana.org/domains/reserved |
| Page loaded | OK (no error) |
| Main heading (verbatim) | "IANA-managed Reserved Domains" |
| Quoted line from body | "As described in RFC 2606 and RFC 6761, a number of domains such as example.com and example.org are maintained for documentation purposes." |
| Guide's claim | this page lists the four special-use top-level domains .test, .example, .invalid and .localhost |
| Verdict | **DOES NOT MATCH** |

**Reading:** the live page does **not** contain the four names named in the claim. Its sections are "Example domains", "Test IDN top-level domains", "Policy-reserved domains", and "Other Special-Use Domains". Those four names appear in IANA's separate **Special-Use Domain Names** registry (RFC 6761), referenced from this page rather than listed there — the registry at https://www.iana.org/assignments/special-use-domain-names is the authoritative pointer for claim 2.

---

## Notes for the guide's editor

- **Claim 1 is out of date as written.** Reword it — e.g. *"https://example.com is a reserved domain maintained for use in documentation examples without needing permission."* The URL itself is still a good live link.
- **Claim 2 is materially out of date.** Change the pointer to the registry you actually mean: *"the special-use top-level domains in IANA's Special-Use Domain Names registry (RFC 6761), at https://www.iana.org/assignments/special-use-domain-names"*, or reword to describe what this page does cover (the example.com/.net/.org set, the Test IDN table, and policy-reserved domains).
