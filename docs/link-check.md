# Link Check Report — Developer Onboarding Guide (Further Reading Box)

**Purpose:** Fresh, live verification of the two claims in the onboarding guide's "further reading" box before ship.

**Date checked:** July 15, 2026 (determined from the GitHub account's latest activity timestamp, as other date services blocked access)

**Method:** Both URLs were loaded live at check time using an HTTP fetch tool. Status, headings, and body text captured verbatim from the returned page content.

---

## Entry 1: https://example.com

- **URL:** https://example.com
- **Page loaded:** OK (loaded successfully)
- **Main heading (verbatim):** `Example Domain`
- **Quoted line from body:** "This domain is for use in documentation examples without needing permission. This is not a service; avoid relying on it for testing and monitoring purposes."
- **Status:** OK
- **Verdict vs. guide's claim:** **Matches.** The page does open with the heading "Example Domain", exactly as the guide states.

## Entry 2: https://www.iana.org/domains/reserved

- **URL:** https://www.iana.org/domains/reserved
- **Page loaded:** OK (loaded successfully)
- **Main heading (verbatim):** `IANA-managed Reserved Domains`
- **Quoted line from body:** "As described in RFC 2606 and RFC 6761, a number of domains such as example.com and example.org are maintained for documentation purposes. These domains may be used as illustrative examples in documents without prior coordination with us. They are not available for registration or transfer."
- **Status:** OK
- **Verdict vs. guide's claim:** **Partial match — claim needs a small update.** The page loads fine and is directly on-topic (reserved/special-use domains), and it cites RFC 2606 and RFC 6761, which are the standards that define the four special-use TLDs .test, .example, .invalid, and .localhost. However, this specific page does not explicitly enumerate those four TLDs as a list; instead it discusses example domains, test IDN top-level domains, policy-reserved domains, and links out to a separate **Special-Use Domain Names registry** (/assignments/special-use-domain-names) where those names are documented.

  **Recommendation:** Update the guide's claim to say the IANA Reserved Domains page references RFC 2606/RFC 6761 and links to the Special-Use Domain Names registry, rather than claiming the page itself lists .test, .example, .invalid, and .localhost.

---

## Summary

| URL | Loaded | Heading (verbatim) | Status | Verdict |
| --- | --- | --- | --- | --- |
| https://example.com | Yes | Example Domain | OK | Matches guide's claim |
| https://www.iana.org/domains/reserved | Yes | IANA-managed Reserved Domains | OK | Partial match — page is related but does not explicitly list the four TLDs; it cites the governing RFCs and links to the Special-Use Domain Names registry |

Both pages loaded successfully at check time. No broken links in the further reading box.
