# Link Check — Developer Onboarding Guide "Further Reading" Box

Live verification of the two claims in the guide's "further reading" box.
Both pages were loaded directly and checked on **2026-11-10 (UTC)** — not from
prior knowledge. Each entry includes the URL, the captured heading verbatim,
a quoted line from the body, the load status, and the matches/does-not-match
verdict against the guide's claim.

| Item | Loads? | Verdict |
|---|---|---|
| https://example.com | ✅ OK | ❌ Does not match as literally stated |
| https://www.iana.org/domains/reserved | ✅ OK | ❌ Does not match |

---

## Entry 1 — https://example.com

- **Page loaded:** Yes, without error
- **Main heading (verbatim):** none on the page — the rendered HTML contains only a `<title>` and one paragraph. "Example Domain" appears only as the browser/tab title, not as a heading.
- **Quoted line from the body:** "This domain is for use in documentation examples without needing permission. This is not a service; avoid relying on it for testing and monitoring purposes."
- **Guide's claim:** that https://example.com opens with the heading 'Example Domain'.
- **Verdict:** ❌ **Does not match (as literally stated).** The page loads fine and its title is "Example Domain", but the body carries no heading element — only a `<p>` plus a `<script src=/s.js>`. If the guide intends "the page is titled 'Example Domain'", that holds only in the loose/tab-title sense. Suggested rewording: *"https://example.com is a reserved domain maintained for use in documentation examples without needing permission."*

---

## Entry 2 — https://www.iana.org/domains/reserved

- **Page loaded:** Yes, without error
- **Main heading (verbatim):** `IANA-managed Reserved Domains`
- **Quoted line from the body:** "Certain domains are set aside, and nominally registered to “IANA”, for specific policy or technical purposes."
- **Guide's claim:** the page lists the four special-use top-level domains `.test`, `.example`, `.invalid` and `.localhost`.
- **Verdict:** ❌ **Does not match.** The page explains that example domains (like example.com and example.org) are reserved under RFC 2606 / RFC 6761, but it does **not** enumerate the four special-use TLDs — `.test`, `.example`, `.invalid` and `.localhost` appear nowhere on the page. Related content: a "Test IDN top-level domains" table of internationalised TLDs, "Policy-reserved domains", and a final "Other Special-Use Domains" section that points to a **separate** registry at `https://www.iana.org/assignments/special-use-domain-names`. The correct pointer for the claim's intent is that registry.

---

## What to change in the guide

1. Reword claim 1 (or rephrase to the title-only sense) — the URL remains a valid, live link for documentation-example use.
2. Replace claim 2's source with the IANA **Special-Use Domain Names** registry:
   `https://www.iana.org/assignments/special-use-domain-names` (RFC 6761),
   where `.test`, `.example`, `.invalid` and `.localhost` are listed.
