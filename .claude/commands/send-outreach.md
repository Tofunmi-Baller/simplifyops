Send an outreach email for a SimplifyOps lead. The user will specify which lead (by company name).

This sends the **ask** email — the one that offers the prototype without linking it. The prototype link is never sent cold; it goes out only after the lead replies asking for it, via `/send-prototype`.

1. **Read the outreach file** from `outreach/[company-name].md` to get the email draft, subject, and contact email.

2. **Check the draft before anything else** — the only link allowed in this email is the booking link (https://calendar.app.google/aYy6MJaq9zJAm7nQ9). No prototype/artifact URL, no tracking links. If the artifact URL is in there, strip it and say so. The hand-off reply in that file is marked DO NOT SEND UNTIL THEY ASK — do not send it here.

3. **Confirm with the user** — show them the email one more time before sending. Ask: "Ready to send this to [contact email]?"

4. **Send via Gmail** using the Gmail tools:
   - Send from admin@simplifyops.dev
   - Use the subject line and body from the outreach file
   - The ask is "would you like to see it?" and the action is a reply; booking is the secondary out

5. **Update the lead file** — set status to "Outreach Sent" and record the send date.

6. **Update Notion** — update the lead record status to "Outreach Sent" with today's date. Keep the prototype link on the record; it just hasn't been sent yet.

7. **Report** — confirm the email was sent, when the follow-up should go out (3-5 days), and that the prototype link is held back until they ask.

Always confirm before sending. Never send without user approval.
