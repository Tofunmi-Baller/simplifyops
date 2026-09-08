Generate a complete outreach package for a SimplifyOps lead. The user will specify which lead (by company name). Do the following:

1. **Read the lead file** from `leads/[company-name].md` to get all research data. If no lead file exists, run the process-lead workflow first.

2. **Build a prototype** for this lead:
   - Read `context/prototype-process.md` for the process
   - Based on the identified needs, build a tailored artifact
   - Use their brand colors (check their website), business name, and real content
   - Make it polished — this is the pitch. It must look like a finished product
   - Publish the artifact and save the URL

3. **Write the outreach email** using the HTML template at `outreach/template.html`:
   - Read `context/email-templates.md` for the full placeholder reference
   - Fill all placeholders: `{{FIRST_NAME}}`, `{{PREHEADER}}`, `{{OBSERVATION}}`, `{{PROOF}}`, `{{DEMO_URL}}`, `{{SENDER}}`
   - `{{OBSERVATION}}` is the hook — the specific broken thing you found in research
   - `{{PROOF}}` is one line of their real credentials — proves you actually looked
   - Write the filled HTML for the first email AND both follow-ups
   - Keep it short — the template structure handles the design

4. **Save the outreach** to `outreach/[company-name-slug].md` with:
   - Email subject line
   - Preheader text
   - Filled placeholder values (observation, proof, etc.)
   - The complete filled HTML for each email version
   - Prototype artifact URL
   - Contact email address
   - Send date (leave blank for user to fill)

5. **Update the lead file** with the prototype link and outreach status.

6. **Update Notion** with the prototype link and outreach draft.

7. **Present everything** to the user for review before anything is sent.

Read all context docs in `context/` before starting.