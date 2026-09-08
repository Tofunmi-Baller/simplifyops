# SimplifyOps — Lead Verification

## Why this exists

On 2026-09-08 all 8 leads owned by Solo were checked against their live sites
before any email went out. **Only 1 of the 8 hooks in Notion was true.** Four
were provably false, three were unverifiable from outside.

Two were structurally dead: Linear Roofing had been acquired and its domain
redirected to the parent brand, and Reeves turned out to be a subsidiary of
Colas USA — 58,000 employees. One lead had the wrong contact name stored.

Every one of those emails would have opened with a confident, checkable, wrong
statement about someone's own business, sent from a brand-new domain. The hooks
come from an automated scan; the scan is a starting point, never evidence.

**No email is written from Notion data alone. Verify first, update Notion, then write.**

## The rule

Verification is a gate on `/generate-outreach`, not an optional extra. If a
hook cannot be confirmed against the live site, the email does not get written.

Re-verify any lead whose last check is more than **14 days** old. Sites change,
companies get acquired, and a stale hook is the same liability as a false one.

## What to check

### 1. Fetch the site correctly
Most failed checks are fetch bugs, not real findings.

- **Always decompress.** `curl -sSL --compressed -A '<browser UA>'`. Without
  `--compressed` a gzipped page reads as binary and every grep returns nothing,
  which looks exactly like "no analytics, no forms, empty title". This produced
  two false findings before it was caught.
- **Follow redirects and read the final URL.** `%{url_effective}`. A redirect
  off the expected domain is itself the story — that is how the Linear Roofing
  acquisition surfaced.
- **Send a real User-Agent.** Bare curl gets blocked or served a stub.
- **A 403 or WAF block means UNVERIFIABLE, not broken.** Record it that way.
  Never convert "I couldn't load it" into "their site is bad."

### 2. Confirm the specific claimed defect
Check the actual thing the hook asserts, not a proxy for it:

| Claimed hook | What actually proves or disproves it |
|---|---|
| not mobile-friendly | presence of `<meta name="viewport">` |
| no analytics | `googletagmanager`, `gtag(`, `google-analytics`, Site Kit |
| no website stack | `wp-content`, Squarespace/Wix/Shopify/Duda/GoDaddy markers |
| no contact form | count of `<form` tags across the main pages |
| no CRM | **not visible from outside — never assert this from a scan** |

If the claimed defect is absent, the hook is false. Say so plainly in Notion
and either find a real one or drop the lead.

### 3. Look for a better hook than the one on file
The strongest hooks found were ones the scan never produced: a site still
serving from a GoDaddy staging domain with template copy describing an entirely
different industry; a commercial GC with no bid form anywhere. Read the actual
page content, not just the markup.

### 4. Sanity-check the company and the contact
A true hook on the wrong company or wrong person is still a wasted send.

- **Parent company or acquisition?** Search the company name. If it is a
  subsidiary, web decisions usually sit with the parent — that is a SKIP.
- **Size vs. our profile.** Hundreds of staff means enterprise procurement.
  `grading-criteria.md` calls that a KEEP regardless of how broken the site is.
- **Is the contact the decision-maker?** A CFO does not sign off a website.
  Owner, founder, partner or marketing lead is who we want.
- **Does the contact name match the site and LinkedIn?** One lead was stored as
  "Mark Catania" when the site said "Founded in 1998 by Mark Middleman".
- **Does the email domain match the website domain?** A mismatch means the
  record is broken — flag it, do not email it.

## Update Notion before writing

Write findings back **before** generating any email, so the database stops
being wrong the moment the truth is known.

- **Hook** — replace with the verified finding, dated. State explicitly where
  the previous hook was false, so nobody re-runs the same bad angle.
- **Tier** — HOT only for a verified hook on a reachable decision-maker at a
  company that fits. WARM if real gaps exist but the contact or record needs
  fixing. SKIP if there is no honest pitch.
- **Status** — `Dead` only for structural disqualification (acquired, enterprise
  parent). A healthy site today is SKIP with status unchanged; they may need us
  later.
- **Contact / Company** — correct any field the research disproved.

## Writing the email

Only after the above:

- `{{OBSERVATION}}` must be the **verified** finding, specific enough that the
  reader can check it in ten seconds on their own phone.
- `{{PROOF}}` must come from their real site content — a named project, a
  founding year, the services they actually list.
- If a fact cannot be verified, leave a clearly marked placeholder rather than
  guessing. Never put an unverified claim about someone's own business into a
  cold email to them.

## Record the outcome

Write the verification into `leads/[company-slug].md` with the date, what was
checked, what held up, and what did not — so the next person does not repeat it.
