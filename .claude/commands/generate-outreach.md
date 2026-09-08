Generate a complete outreach package for a SimplifyOps lead. The user will specify which lead (by company name). Do the following:

1. **Verify the lead first — this is a gate, not a formality.** Run the `/verify-lead` workflow for this lead, or follow `context/verification-process.md` directly. Re-check the hook against the live site, sanity-check the company and contact, and write the corrected findings back to Notion before anything else. If the hook on file turns out to be false and no honest replacement is found, stop and report — do not write the email. If the lead was verified within the last 14 days, note the date and continue.

2. **Read the lead file** from `leads/[company-name].md` to get all research data. If no lead file exists, run the process-lead workflow first.

3. **Build a prototype** for this lead:
   - Read `context/prototype-process.md` for the process
   - Based on the identified needs, build a tailored artifact
   - Use their brand colors (check their website), business name, and real content
   - Make it polished — this is the pitch. It must look like a finished product
   - Publish the artifact and save the URL

4. **Write the outreach email** using the ask-first templates in `outreach/`:
   - Read `context/email-templates.md` first — the governing rule is **ask first, link later**
   - **Email 1 and both follow-ups use `outreach/template.html` and carry NO prototype link.** The email says we already built the thing and asks whether they want to see it. An unfamiliar artifact URL in a cold email reads as a scam, to the person and to the spam filter. The booking link stays in — it's a known Google domain and the ordinary ask
   - Fill: `{{FIRST_NAME}}`, `{{PREHEADER}}`, `{{OBSERVATION}}`, `{{PROOF}}`, `{{BUILT}}`, `{{SENDER}}`
   - `{{OBSERVATION}}` is the hook — the specific broken thing you found in research
   - `{{PROOF}}` is one line of their real credentials — proves you actually looked
   - `{{BUILT}}` is what you actually built, in their words — the thing they'd be saying yes to
   - **Also write the hand-off reply** using `outreach/template-reply.html`. This is the only email carrying `{{DEMO_URL}}`, and it only goes out after the lead replies asking to see it. Fill `{{BUILT}}` (same wording as email 1), `{{DEMO_URL}}`, `{{TRY_THIS}}`
   - Write the filled HTML for: email 1, follow-up 1, follow-up 2, and the hand-off reply
   - Keep it short — the template structure handles the design

5. **Save the outreach** to `outreach/[company-name-slug].md` with:
   - Email subject line
   - Preheader text
   - Filled placeholder values (observation, proof, built, etc.)
   - The complete filled HTML for each email version, with the hand-off reply clearly marked **DO NOT SEND UNTIL THEY ASK**
   - Prototype artifact URL (held back from email 1 — it lives here and in the hand-off reply only)
   - Note that the cold emails carry the booking link and nothing else clickable
   - Contact email address
   - Send date (leave blank for user to fill)

6. **Update the lead file** with the prototype link and outreach status.

7. **Update Notion** with the prototype link and outreach draft.

8. **Present everything** to the user for review before anything is sent.

Read all context docs in `context/` before starting — `context/verification-process.md` included.