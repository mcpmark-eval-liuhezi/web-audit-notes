# Link Verification Report — Developer Onboarding Guide ("Further Reading")

- **Checked:** 2026-11-10
- **Method:** Live fetch of each URL over HTTPS today; headings captured verbatim from the served page markup (page `<title>` for example.com, primary `<h1>` for IANA). Both pages loaded with no error.
- **Purpose:** Fresh, live verification of the two claims in the onboarding guide's "further reading" box, ahead of the ship date.

---

## Entry 1 — https://example.com

| Field | Value |
|---|---|
| URL | https://example.com |
| Page loaded | OK |
| Main heading (verbatim) | **None — the page contains no heading element.** "Example Domain" survives only as the <code>&lt;title&gt;</code> of the served document: <code>&lt;title>Example Domain&lt;/title&gt;</code> |
| Quoted line from body | "This domain is for use in documentation examples without needing permission. This is not a service; avoid relying on it for testing and monitoring purposes." |
| Guide's claim | https://example.com opens with the heading 'Example Domain'. |
| **Verdict** | **❌ Does not match (as literally stated)** |

**Reading:** The URL is still live and still the canonical documentation-domain page, but the literal claim no longer holds: today's page has no `<h1>`/visible heading — "Example Domain" is only the browser-tab title, and the body now asks readers not to rely on it for testing and monitoring. Reword if the literal claim must stay.

## Entry 2 — https://www.iana.org/domains/reserved

| Field | Value |
|---|---|
| URL | https://www.iana.org/domains/reserved |
| Page loaded | OK |
| Main heading (verbatim) | `IANA-managed Reserved Domains` (the page's `<h1>`) |
| Quoted line from body | "Certain domains are set aside, and nominally registered to “IANA”, for specific policy or technical purposes." |
| Guide's claim | The IANA page at this URL lists the four special-use top-level domains .test, .example, .invalid and .localhost. |
| **Verdict** | **❌ Does not match** |

**Reading:** The page's actual sections are "Example domains" (example.com/example.org, per RFC 2606/6761), "Test IDN top-level domains" (eleven internationalized entries such as <code>xn--kgbechtv</code> Arabic test and <code>xn--0zwm56d</code> Chinese simplified), "Policy-reserved domains", and "Other Special-Use Domains". It does **not** enumerate .test, .example, .invalid or .localhost — those live in IANA's separate **Special-Use Domain Names** registry (RFC 6761), which this page links out to.

---

## Summary

| # | URL | Page loaded | Main heading (verbatim) | Claim | Verdict |
|---|---|---|---|---|---|
| 1 | https://example.com | OK | None (title only: `Example Domain`) | Opens with heading 'Example Domain' | ❌ Does not match |
| 2 | https://www.iana.org/domains/reserved | OK | `IANA-managed Reserved Domains` | Lists .test, .example, .invalid, .localhost | ❌ Does not match |
