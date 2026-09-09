Enrich leads assigned to a specific owner (or all owners if not specified). This is the full pipeline: research, email collection, and outreach email generation.

The user may say "enrich lead", "enrich leads", "enrich Baller's leads", etc.

1. **Identify the leads** — Query the Notion Lead Pipeline database for leads belonging to the specified owner (or all owners). Pull the first 10 by score unless the user specifies otherwise.

2. **Deep research each lead:**
   - Fetch their website with WebFetch
   - Look at what they do, what services they offer, what projects they showcase
   - Note real details (years in business, service areas, specialties, team size)
   - Verify the hook is still accurate against the live site
   - Flag any issues (domain down, website mismatch, bad contact info)

3. **Collect all email addresses** — Present a clean list of all lead emails for easy CC/copy.

4. **Generate Email 1 (opener) for each lead** using the 2-part process:
   - Every email follows the same structure, no exceptions
   - **No links of any kind in Email 1.** No demo links, no booking links, no URLs. Nothing clickable.
   - Use the `{{SENDER}}` name from the lead's owner (check `context/email-templates.md` for the sender mapping)
   - **Subject:** "{{FIRST_NAME}}, please check this out". Before writing it, confirm the first
     name is the one on this lead's record, capitalised. If the record has no usable first name,
     flag the lead in step 6 and write no subject for it. Never fall back to the email address or
     the domain, and never carry the previous lead's name forward. When generating a batch, the
     subject name and the "Hi ..." greeting must be the same word on every single lead.
   - Structure:
     1. "Hi {{FIRST_NAME}},"
     2. "I'm {{SENDER}} from SimplifyOps. We help businesses build and fix their digital presence."
     3. Observation in bold — "I came across [website] and noticed [specific problem]."
     4. Proof line — connect their credentials/reputation to why this matters
     5. "We [went ahead and rebuilt it / put together a working system] using your real [services/details/content]. Happy to share it if you'd like to take a look."
     6. "Best," + "SimplifyOps Team"
   - Keep it natural and conversational. Not robotic.
   - No em dashes. Use periods or commas.
   - Use "we" when talking about SimplifyOps work, not "I"

5. **Populate each lead's Notion page** with the email in markdown format:
   - H2: "Outreach Email (2-part process)"
   - H3: "Email 1 — Opener (no links)" with subject and preheader
   - Full email body ready to copy and paste
   - Note: "Email 2 sent only after they reply — contains demo link and booking link"

6. **Present everything** to the user:
   - CC-ready email list
   - All emails for review
   - Any flags (domain issues, contact mismatches, leads that should be SKIP)

Read `context/email-templates.md` before starting.
