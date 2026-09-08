# SimplifyOps — Email Outreach Structure

## The Rule That Shapes Everything: Ask First, Link Later
A cold email from an unknown sender that leads with "click this unfamiliar link" reads
as a scam — to the person and to the spam filter. So we never put the prototype link in
a cold email. The first email says we already built the thing and **asks whether they
want to see it**. The prototype link goes out only after they reply asking for it.

- **Email 1 and both follow-ups**: no prototype link. The only link is the booking link.
- **The hand-off reply**: carries the prototype link. Sent on the existing thread once
  they've said yes. A link they asked for, in a thread they started, gets clicked.

The booking link stays in every email. `calendar.app.google` is a recognisable Google
domain, it's the ordinary thing a business email asks for, and it gives the reader a
second way in if they'd rather talk than look at a demo. The artifact URL is the one
that has to be earned.

Never send the prototype link to a lead who has not asked for it.

## Principles
- Short. Nobody reads long cold emails. 5-7 sentences max.
- Personal. Reference something specific about THEIR business. Never generic.
- Value first. Show you already understand their problem before pitching.
- Prototype tease — not prototype drop. "We built it, want to see it?" is the ask.
- One primary action: reply. Booking is the secondary out, not the headline.
- Plain design — white background, dark text, no branding. Should look like a real person typed it in Gmail, not a marketing campaign.

## Templates
| File | When |
|------|------|
| `outreach/template.html` | Email 1 and follow-ups — the ask. Booking link only, no prototype link. |
| `outreach/template-reply.html` | The hand-off — sent as a reply after they say yes. Carries the prototype link. |

Always use these when sending outreach — never send plain-text-only.

### Email Palette (deliberately plain)
| Token     | Hex       | Usage                              |
|-----------|-----------|------------------------------------|
| ground    | `#FFFFFF` | White background                   |
| text      | `#222222` | Body copy                          |
| link      | `#1155CC` | Links (Gmail's native blue)         |
| muted     | `#666666` | Sign-off "SimplifyOps" line        |

Archived: `outreach/template-v4-link-in-email.html` (link-in-cold-email version, retired
because the link read as spam) and `outreach/template-v3-dark.html` (dark branded version).

### Placeholders
Fill these when generating outreach for a lead:

| Placeholder        | Used in        | What it is                                                    | Example                                                        |
|--------------------|----------------|---------------------------------------------------------------|----------------------------------------------------------------|
| `{{FIRST_NAME}}`   | both           | Lead's first name                                             | Chuck                                                          |
| `{{PREHEADER}}`    | ask            | ~50 chars, extends the subject line, never repeats it         | We rebuilt your portfolio from scratch                         |
| `{{OBSERVATION}}`  | ask            | The specific broken thing you noticed (the hook)              | Your site takes 8 seconds to load and the portfolio page 404s  |
| `{{PROOF}}`        | ask            | One line of their real credentials — proves you did research  | You've shipped 3 major projects this year                      |
| `{{BUILT}}`        | both           | What we built, in their words — same wording in both emails   | a new portfolio page with your three real projects on it       |
| `{{DEMO_URL}}`     | hand-off reply | The published artifact link (the prototype)                   | https://claude.ai/artifacts/...                                |
| `{{TRY_THIS}}`     | hand-off reply | One concrete thing to poke at                                 | The contact form works, so send yourself one and see.          |
| `{{SENDER}}`       | both           | Whoever is sending                                            | SimplifyOps Team                                               |

### Email 1 Structure (`outreach/template.html`)
1. **Greeting** — `{{FIRST_NAME}},`
2. **Observation** — bold text, the only bold line (proves it's not a mail merge)
3. **Proof line** — `{{PROOF}} — so that gap seemed worth closing.`
4. **The build** — "Rather than describe it, we built it: `{{BUILT}}`. Working version, using your real details — not a mockup."
5. **The ask** — "Would you like to see it? Reply \"yes\" and I'll send it over."
6. **Booking** — "Or if you'd rather just talk it through, grab fifteen minutes here."
7. **Opt-out** — "If it's not for you, just say so and I won't write again."
8. **Sign-off** — sender name + "SimplifyOps" in gray

No prototype link anywhere in this email — the booking link is the only link.

### Hand-off Reply Structure (`outreach/template-reply.html`)
Sent as a **reply on the existing thread**, never as a new email.
1. **Greeting** — `{{FIRST_NAME}},`
2. **Delivery** — "Here it is — `{{BUILT}}`:"
3. **Demo link** — bold underlined link on its own line
4. **Nudge** — `{{TRY_THIS}}`
5. **Booking** — inline link: "grab fifteen minutes here"
6. **No-strings** — "Either way, keep the build — no strings."
7. **Sign-off**

### Email Client Compatibility
- **Outlook**: MSO conditional wrapper for max-width (Outlook ignores `max-width`)
- **Dark mode**: plain white email inverts naturally — nothing to fight
- **No images**: text-only, no tracking pixels — helps deliverability on a new domain
- **One link, on a known domain**: a single google.com-family booking link, no unfamiliar URLs — much easier on deliverability from a new domain than an artifact link
- **No web fonts**: system sans-serif everywhere
- **Left-aligned**: not centered — centered narrow columns look like a template

## Subject Lines
Personalized, curiosity-driving. Examples:
- "Quick question about [Company]'s website"
- "[Company] — noticed something on your site"
- "Built something for [Company] — want to see it?"
- "Re: [Company]'s [specific thing]"

Never: "Partnership opportunity", "Our services", "Let's connect"

## Follow-ups
Both follow-ups use `outreach/template.html` — still no prototype link, still the same ask,
booking link still there.

### Follow-up 1 (3-5 days after first email, if no response)
- Re-offer the prototype in one line — "still happy to send it over"
- Add one new observation or value angle
- Same ask: reply and it's theirs

### Follow-up 2 (5-7 days after follow-up 1, final)
Shorter — just the offer and a soft close:
- "Last one from me"
- "The build is still sitting here if you want it — just say the word"
- "If the timing isn't right, no worries"

## Rules
- Never put the prototype link in a cold email — the lead asks first, always
- Send the prototype link as a **reply on the existing thread**, not a new email
- The booking link goes in every email, cold ones included
- Never send more than 3 emails total (initial + 2 follow-ups) before they reply
- Always personalize — never send the same email to two leads
- Booking link: https://calendar.app.google/aYy6MJaq9zJAm7nQ9
- Sign off as "SimplifyOps Team" (no individual names) unless specified
- Send from admin@simplifyops.dev
- Always use the templates in `outreach/` — fill the placeholders
