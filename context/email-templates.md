# SimplifyOps — Email Outreach Structure

## Core Rule: Ask First, Link Later
Never put any links in a cold email. No demo links, no booking links, no URLs of any kind. The first email introduces who we are, states what we noticed, and offers to share what we built. Links only go out after the lead replies.

## 2-Part Email Process (everyone uses this)

### Email 1 — Opener (no links, no URLs)
1. "Hi {{FIRST_NAME}},"
2. "I'm {{SENDER}} from SimplifyOps. We help businesses build and fix their digital presence."
3. Observation in bold — "I came across [website] and noticed [specific problem]."
4. Proof line — connect their credentials/reputation to why this matters for them
5. "We [went ahead and rebuilt it / put together a working system] using your real [services/details]. Happy to share it if you'd like to take a look."
6. "Best," + "SimplifyOps Team"

### Email 2 — After they reply (links included)
Sent as a reply on the same thread, never as a new email.
1. "Hi {{FIRST_NAME}},"
2. "Here it is." + brief description of what was built
3. Demo link on its own line
4. Nudge to interact with the prototype
5. "If you'd like to talk through it, here's a link to book a time with us:" + booking link
6. "Best," + "SimplifyOps Team"

## Sender Mapping
Each owner uses their own name in the intro line:

| Owner  | Sender name |
|--------|-------------|
| Baller | Samuel      |
| Momoh  | Momoh       |
| Zeph   | Zeph        |
| Lumi   | Lumi        |
| Solo   | Solomon     |
| Osas   | Osas        |
| Caleb  | Caleb       |

## Principles
- Short. 5 sentences max per email.
- Personal. Reference something specific about THEIR business. Never generic.
- Value first. Show you already understand their problem before offering anything.
- No links in Email 1. None. Zero. Not even a booking link.
- Always introduce yourself. They need to know who is emailing them.
- Use "we" when talking about SimplifyOps work, not "I" (except "I came across" and "I'm [name]").
- No em dashes. They look AI-generated. Use periods or commas instead.
- Natural tone. This is a human reaching out, not a template. Make it conversational.
- Always use "Hi {{FIRST_NAME}}," greeting and sign off with "Best," followed by "SimplifyOps Team".

## HTML Template
The canonical email template lives at `outreach/template.html`. Use it when sending via Gmail.

### Email Palette (deliberately plain)
| Token     | Hex       | Usage                              |
|-----------|-----------|------------------------------------|
| ground    | `#FFFFFF` | White background                   |
| text      | `#222222` | Body copy                          |
| link      | `#1155CC` | Links (Gmail's native blue)        |
| muted     | `#666666` | Sign-off "SimplifyOps" line        |

### Placeholders
| Placeholder        | What it is                                                    | Example                                                        |
|--------------------|---------------------------------------------------------------|----------------------------------------------------------------|
| `{{FIRST_NAME}}`   | Lead's first name                                             | Larry                                                          |
| `{{SENDER}}`       | Sender's first name (from sender mapping above)               | Samuel                                                         |
| `{{PREHEADER}}`    | ~50 chars, extends the subject line, never repeats it         | We noticed something on texastileroofing.com                   |
| `{{OBSERVATION}}`  | The specific broken thing you noticed (the hook)              | Your site doesn't display properly on mobile                   |
| `{{PROOF}}`        | One line connecting their credentials to the problem          | You've been in business for 30 years across DFW                |
| `{{DEMO_URL}}`     | The published artifact link (Email 2 only)                    | https://claude.ai/artifacts/...                                |

### Email Client Compatibility
- **Outlook**: MSO conditional wrapper for max-width
- **Dark mode**: plain white email inverts naturally
- **No images**: text-only, no tracking pixels
- **No web fonts**: system sans-serif everywhere
- **Left-aligned**: not centered

## Subject Lines
Simple and direct with their first name. No catchy hooks or curiosity bait.

Format: "{{FIRST_NAME}}, please check this out"

Examples:
- "Larry, please check this out"
- "Susan, please check this out"

Never: "Quick question about...", "Partnership opportunity", "Our services", "Let's connect", "Built something for..."

### Subject line checks (all four have failed in live sends)
The subject is the only thing every recipient is guaranteed to read, so check it against the
recipient before the email goes out:
- **Never an email address or domain.** If `{{FIRST_NAME}}` is empty the merge must fail loudly,
  not fall back to the address. `kristen@zettavp.com` went out as a live subject line.
- **The name must be this lead's name.** It must match the "Hi ..." greeting in the body. A
  subject reading "Kindly check this out, David" on an email opening "Hi Leo" went out because a
  previous lead's name was left in place.
- **Capitalise it.** "Please take a look at this, jerry" went out lowercase.
- **No unresolved `{{...}}` placeholders.**

`/send-outreach` enforces these before sending, but generation should not produce them in the
first place.

## Follow-ups (if no response to Email 1)
Still no links. Same 2-part rule applies.

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
After generating emails for a lead, populate the lead's Notion page with the email in markdown format:
- H2: "Outreach Email (2-part process)"
- H3: "Email 1 — Opener (no links)" with subject and preheader
- Full email body ready to copy and paste
- Note: "Email 2 sent only after they reply"

## Rules
- Never send any links in Email 1. No demo, no booking, no URLs
- Always introduce yourself in the first email
- Always personalize. Never send the same email to two leads
- Booking link (Email 2 only): https://calendar.app.google/aYy6MJaq9zJAm7nQ9
- Sign off as "SimplifyOps Team"
- Send from admin@simplifyops.dev
- Always populate the lead's Notion page with the email drafts after generating
- Never send more than 3 cold emails total (initial + 2 follow-ups) before they reply
- SKIP leads get deleted from Notion immediately
