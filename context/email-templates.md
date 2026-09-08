# SimplifyOps — Email Outreach Structure

## Core Rule: Ask First, Link Later
A cold email from an unknown sender with an unfamiliar link reads as spam, to the person and to the spam filter. So we never put the prototype link in a cold email. The first email says we already built the thing and asks whether they want to see it. The prototype link goes out only after they reply asking for it.

Never send the prototype link to a lead who has not asked for it.

## Principles
- Short. Nobody reads long cold emails. 5 sentences max per email.
- Personal. Reference something specific about THEIR business. Never generic.
- Value first. Show you already understand their problem before pitching.
- No links in the first email. Tease the prototype, don't link it.
- Use "we" not "I". Sounds like an organized team, not a solo operator.
- No em dashes. They look AI-generated. Use periods or commas instead.
- Plain design. White background, dark text, no branding. Should look like a real person typed it in Gmail.
- Always use "Hi {{FIRST_NAME}}," greeting and sign off with "Best," followed by "SimplifyOps Team".

## Two Email Versions

Teams are split into two groups. Each owner is assigned a version.

### Version A — 2-part email (reply-gated links)

**Email 1 (opener, no links):**
1. "Hi {{FIRST_NAME}},"
2. Observation in bold (the hook, the specific broken thing)
3. Proof line (their credentials, why this matters for them specifically)
4. "We went ahead and rebuilt it using your real [projects/content/business] details. Happy to share it if you'd like to take a look."
5. "Best," + "SimplifyOps Team"

**Email 2 (sent only after they reply, includes links):**
1. "Hi {{FIRST_NAME}},"
2. "Here it is." + brief description of what was built
3. Demo link on its own line
4. Nudge to interact with the prototype
5. "If you'd like to talk through it, here's a link to book a time with us:" + booking link
6. "Best," + "SimplifyOps Team"

### Version B — 1-part email (everything at once)

**Single email with all links:**
1. "Hi {{FIRST_NAME}},"
2. Observation in bold (the hook)
3. Proof line
4. "We went ahead and rebuilt it using your real [projects/content/business] details:"
5. Demo link on its own line
6. Nudge to interact + booking link in same paragraph
7. "Best," + "SimplifyOps Team"

## Owner Assignments

| Version A (2-part) | Version B (1-part) |
|---------------------|--------------------|
| Osas                | Lumi               |
| Momoh               | Solo               |
| Zeph                | Baller             |
| Caleb               |                    |

## HTML Template
The canonical email template lives at `outreach/template.html`. Always use it when sending outreach.

### Email Palette (deliberately plain)
| Token     | Hex       | Usage                              |
|-----------|-----------|------------------------------------|
| ground    | `#FFFFFF` | White background                   |
| text      | `#222222` | Body copy                          |
| link      | `#1155CC` | Links (Gmail's native blue)        |
| muted     | `#666666` | Sign-off "SimplifyOps" line        |

Archived templates: `outreach/template-v3-dark.html` (dark branded version).

### Placeholders
Fill these when generating outreach for a lead:

| Placeholder        | What it is                                                    | Example                                                        |
|--------------------|---------------------------------------------------------------|----------------------------------------------------------------|
| `{{FIRST_NAME}}`   | Lead's first name                                             | Bill                                                           |
| `{{PREHEADER}}`    | ~50 chars, extends the subject line, never repeats it         | We noticed something on advconc.com                            |
| `{{OBSERVATION}}`  | The specific broken thing you noticed (the hook)              | Your site at advconc.com doesn't resize on mobile              |
| `{{PROOF}}`        | One line connecting their credentials to the problem          | You're running a $10M operation with 50 people across Dallas   |
| `{{DEMO_URL}}`     | The published artifact link (the prototype)                   | https://claude.ai/artifacts/...                                |
| `{{SENDER}}`       | Always "SimplifyOps Team" unless specified                    | SimplifyOps Team                                               |

### Email Client Compatibility
- **Outlook**: MSO conditional wrapper for max-width (Outlook ignores `max-width`)
- **Dark mode**: plain white email inverts naturally
- **No images**: text-only, no tracking pixels
- **No web fonts**: system sans-serif everywhere
- **Left-aligned**: not centered

## Subject Lines
Personalized, curiosity-driving. Examples:
- "Quick question about [Company]'s website"
- "Quick question about [Company]'s [specific thing]"

Never: "Partnership opportunity", "Our services", "Let's connect", "Built something for [Company]"

## Follow-ups (Version A only)
If no response to Email 1, follow up before they reply. Still no prototype link.

### Follow-up 1 (3-5 days after first email)
- Re-offer the prototype in one line. "Still happy to send it over"
- Add one new observation or value angle
- Same ask: reply and it's theirs

### Follow-up 2 (5-7 days after follow-up 1, final)
Shorter, just the offer and a soft close:
- "Last one from us"
- "The build is still sitting here if you want it, just say the word"
- "If the timing isn't right, no worries"

## Notion Integration
After generating emails for a lead, populate the lead's Notion page with the full email drafts in markdown format. Structure as:
- H2: "Outreach Emails (Version [A/B])"
- H3 per email with subject line and preheader
- Full email body in markdown, ready to copy and paste

## Rules
- Never send links in the first cold email or to unresponsive leads
- Always personalize. Never send the same email to two leads
- Check the owner's assigned version before generating emails
- Always include the booking link in the email that contains the demo link
- Booking link: https://calendar.app.google/aYy6MJaq9zJAm7nQ9
- Sign off as "SimplifyOps Team" (no individual names) unless specified
- Send from admin@simplifyops.dev
- Always populate the lead's Notion page with the email drafts after generating
- Never send more than 3 cold emails total (initial + 2 follow-ups) before they reply
