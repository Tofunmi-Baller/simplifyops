Send the prototype link to a lead who has replied asking to see it. This is the hand-off, and the only email that carries the prototype link.

Run this only after the lead has actually asked. If they haven't, stop.

1. **Read the outreach file** from `outreach/[company-name].md` to get the hand-off reply draft and the prototype artifact URL.

2. **Confirm they asked.** Find the lead's reply in Gmail (search the thread from admin@simplifyops.dev to their address). Read it. If it is a yes — or anything close, "sure", "go ahead", "send it" — continue. If it's a no, a stop request, or you can't find a reply at all, do not send: report what you found and let the user decide.

3. **Check the prototype is still live** — open the artifact URL. A dead link here loses the lead.

4. **Confirm with the user** — show them the hand-off email and the thread it will reply to. Ask: "Ready to send the prototype to [contact email]?"

5. **Send as a reply on the existing thread** — not a new email. Use the Gmail reply tool with the thread ID from step 2. The quoted history is what makes the link safe to click.
   - Send from admin@simplifyops.dev
   - Body from `outreach/template-reply.html`, filled: `{{BUILT}}`, `{{DEMO_URL}}`, `{{TRY_THIS}}`, `{{SENDER}}`
   - Includes the booking link again: https://calendar.app.google/aYy6MJaq9zJAm7nQ9

6. **Update the lead file** — set status to "Prototype Sent" and record the date.

7. **Update Notion** — same status and date.

8. **Report** — confirm it was sent, and flag that the next move is theirs (a booked call, or a nudge in 3-5 days).

Always confirm before sending. Never send without user approval, and never send this to a lead who has not asked for it.
