Generate a complete outreach package for a SimplifyOps lead. The user will specify which lead (by company name). Do the following:

1. **Verify the lead first. This is a gate, not a formality.** Run the `/verify-lead` workflow for this lead, or follow `context/verification-process.md` directly. Re-check the hook against the live site, sanity-check the company and contact, and write the corrected findings back to Notion before anything else. If the hook on file turns out to be false and no honest replacement is found, stop and report. Do not write the email. If the lead was verified within the last 14 days, note the date and continue.

2. **Read the lead file** from `leads/[company-name].md` to get all research data. If no lead file exists, run the process-lead workflow first.

3. **Check the lead's owner** in the Notion Lead Pipeline database. Look up which email version the owner is assigned to in `context/email-templates.md` (Version A = 2-part, Version B = 1-part).

4. **Build a prototype** for this lead:
   - Read `context/prototype-process.md` for the process
   - Based on the identified needs, build a tailored artifact
   - Use their brand colors (check their website), business name, and real content
   - Make it polished. This is the pitch. It must look like a finished product
   - Publish the artifact and save the URL

5. **Write the outreach emails** based on the owner's assigned version:
   - Read `context/email-templates.md` for the full structure and rules
   - Use "Hi {{FIRST_NAME}}," greeting, sign off with "Best," + "SimplifyOps Team"
   - Use "we" not "I" throughout
   - No em dashes. Use periods or commas instead
   - Keep each email to 5 sentences max

   **If Version A (2-part):**
   - Email 1: Observation (bold) + proof + "We went ahead and rebuilt it... Happy to share it if you'd like to take a look." No links at all.
   - Email 2: Demo link + nudge to interact + booking link. Only sent after lead replies.

   **If Version B (1-part):**
   - Single email: Observation (bold) + proof + demo link + nudge + booking link, all in one.

6. **Save the outreach** to `outreach/[company-name-slug].md` with:
   - Email version (A or B)
   - Email subject line and preheader
   - Full email body for each email in markdown
   - Prototype artifact URL
   - Contact email address
   - Send date (leave blank for user to fill)

7. **Update the lead file** with the prototype link and outreach status.

8. **Populate the lead's Notion page** with the full email drafts in markdown format:
   - H2: "Outreach Emails (Version [A/B])"
   - H3 per email with subject line and preheader
   - Full email body ready to copy and paste

9. **Update Notion properties**: set Prototype to "Generated" and add the prototype link.

10. **Present everything** to the user for review before anything is sent.

Read all context docs in `context/` before starting, including `context/verification-process.md`.
