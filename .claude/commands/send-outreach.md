Send an outreach email for a SimplifyOps lead. The user will specify which lead (by company name).

This sends the **ask** email — the one that offers the prototype without linking it. The prototype link is never sent cold; it goes out only after the lead replies asking for it, via `/send-prototype`.

1. **Read the outreach file** from `outreach/[company-name].md` to get the email draft, subject, and contact email.

2. **Check the draft before anything else** — the only link allowed in this email is the booking link (https://calendar.app.google/aYy6MJaq9zJAm7nQ9). No prototype/artifact URL, no tracking links. If the artifact URL is in there, strip it and say so. The hand-off reply in that file is marked DO NOT SEND UNTIL THEY ASK — do not send it here.

3. **Check the subject line** — it is the one thing every recipient sees, and it has shipped
   broken before. Reject the send if any of these are true:
   - The subject contains `@`, a bare domain, or a URL. A subject like `kristen@zettavp.com`
     means the merge dropped the name and fell back to the address.
   - The name in the subject is not the recipient's first name, or does not match the name in
     the "Hi ..." greeting. A mismatch means a previous lead's name leaked through.
   - The first name is not capitalised (`jerry` instead of `Jerry`).
   - The subject still contains an unresolved `{{...}}` placeholder.

   Fix the subject and re-check before continuing. Never send a subject you have not read
   against the recipient's actual name.

4. **Confirm with the user** — show them the email one more time before sending. Ask: "Ready to send this to [contact email]?"

5. **Send via Gmail** using the Gmail tools:
   - Send from admin@simplifyops.dev
   - Use the subject line and body from the outreach file
   - The ask is "would you like to see it?" and the action is a reply; booking is the secondary out

6. **Update the lead file** — set status to "Outreach Sent" and record the send date.

7. **Update Notion** — update the lead record status to "Outreach Sent" with today's date. Keep the prototype link on the record; it just hasn't been sent yet.

8. **Report** — confirm the email was sent, when the follow-up should go out (3-5 days), and that the prototype link is held back until they ask.

Always confirm before sending. Never send without user approval.
