Re-check and re-verify a SimplifyOps lead against its live site before any outreach is written, then correct Notion. The user may name a lead, an owner, or say "all" — default to every lead the current owner has that is not already SKIP/Dead.

Read `context/verification-process.md` first. It has the exact checks, the fetch flags that matter, and the failure modes that produced false findings before. Do the following:

1. **Pull current data from Notion** — query the Lead Pipeline data source for the leads in scope. Take Company, Contact, Role, Hook, Tier, Status, Website, LinkedIn, Email, Staff, Revenue. Treat every field as a claim to be tested, not a fact.

2. **Fetch each live site properly:**
   - `curl -sSL --compressed -A '<browser User-Agent>'` — the `--compressed` flag is not optional; without it a gzipped page greps as empty and every check returns a false negative
   - Record the final URL after redirects. A redirect off the expected domain is itself a finding
   - A 403 or WAF block is **unverifiable**, never "broken"

3. **Test the specific claimed defect** using the mapping table in `context/verification-process.md`. Check the actual thing the hook asserts — viewport tag for mobile claims, analytics scripts for analytics claims, `<form>` count for form claims. A "no CRM" claim cannot be verified from outside; do not assert it.

4. **Read the page content, not just the markup.** The strongest hooks are usually ones the automated scan never produced. Note anything better than what is on file.

5. **Sanity-check company and contact** — parent company or acquisition, staff count against our profile, whether the contact is a real decision-maker, whether the contact name matches the site and LinkedIn, whether the email domain matches the website domain.

6. **Update Notion immediately**, before writing anything:
   - `Hook` — the verified finding, dated, stating explicitly where the old hook was false
   - `Tier` — HOT / WARM / SKIP per the rules in the verification doc
   - `Status` — `Dead` only for structural disqualification
   - Correct any Contact or Company field the research disproved

7. **Write the result** to `leads/[company-slug].md`: date checked, what was checked, what held up, what did not, and the recommended next step.

8. **Report back** a table of every lead checked: claimed hook, verdict (TRUE / FALSE / UNVERIFIABLE), the real finding, and the new tier. State plainly how many hooks survived.

Never soften a false hook into a usable one. If a lead has no honest angle, say so and mark it SKIP — a wasted send costs more than a dropped lead, and a checkably wrong claim from a new sending domain costs more than both.
