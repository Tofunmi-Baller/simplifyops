# SimplifyOps — Email Outreach Structure

## Principles
- Short. Nobody reads long cold emails. 5-7 sentences max.
- Personal. Reference something specific about THEIR business. Never generic.
- Value first. Show you already understand their problem before pitching.
- Prototype tease. We already built something for them — link it.
- Two links: "View the demo" (bold link, own line) + "grab fifteen minutes" (inline link to booking).
- Plain design — white background, dark text, no branding. Should look like a real person typed it in Gmail, not a marketing campaign.

## HTML Template
The canonical email template lives at `outreach/template.html`. Always use it when sending outreach — never send plain-text-only.

### Email Palette (deliberately plain)
| Token     | Hex       | Usage                              |
|-----------|-----------|------------------------------------|
| ground    | `#FFFFFF` | White background                   |
| text      | `#222222` | Body copy                          |
| link      | `#1155CC` | Links (Gmail's native blue)        |
| muted     | `#666666` | Sign-off "SimplifyOps" line        |

The old dark-branded template is archived at `outreach/template-v3-dark.html` if ever needed.

### Placeholders
Fill these when generating outreach for a lead:

| Placeholder        | What it is                                                    | Example                                                        |
|--------------------|---------------------------------------------------------------|----------------------------------------------------------------|
| `{{FIRST_NAME}}`   | Lead's first name                                             | Chuck                                                          |
| `{{PREHEADER}}`    | ~50 chars, extends the subject line, never repeats it         | We rebuilt your portfolio from scratch                         |
| `{{OBSERVATION}}`  | The specific broken thing you noticed (the hook)              | Your site takes 8 seconds to load and the portfolio page 404s  |
| `{{PROOF}}`        | One line of their real credentials — proves you did research  | You've shipped 3 major projects this year                      |
| `{{DEMO_URL}}`     | The published artifact link (the prototype)                   | https://claude.ai/artifacts/...                                |
| `{{SENDER}}`       | Whoever is sending                                            | SimplifyOps Team                                               |

### Template Structure
1. **Greeting** — `{{FIRST_NAME}},`
2. **Observation** — bold text, the only bold line (proves it's not a mail merge)
3. **Proof line** — `{{PROOF}} — so that gap seemed worth closing.`
4. **Transition** — "I rebuilt it. Working version, using your real projects and details:"
5. **Demo link** — bold underlined link on its own line
6. **Nudge** — "The contact form on it works, so send yourself one and see."
7. **Booking** — inline link: "grab fifteen minutes here"
8. **Opt-out** — "If it's not for you, keep the build — no strings."
9. **Sign-off** — sender name + "SimplifyOps" in gray

### Email Client Compatibility
- **Outlook**: MSO conditional wrapper for max-width (Outlook ignores `max-width`)
- **Dark mode**: plain white email inverts naturally — nothing to fight
- **No images**: text-only, no tracking pixels — helps deliverability on a new domain
- **No web fonts**: system sans-serif everywhere
- **Left-aligned**: not centered — centered narrow columns look like a template

## Subject Lines
Personalized, curiosity-driving. Examples:
- "Quick question about [Company]'s website"
- "[Company] — noticed something on your site"
- "Built something for [Company]"
- "Re: [Company]'s [specific thing]"

Never: "Partnership opportunity", "Our services", "Let's connect"

## Follow-ups

### Follow-up 1 (3-5 days after first email, if no response)
Use the same HTML template structure but adjust the body:
- Reference the prototype again
- Add one new observation or value angle
- Keep the same button pair (demo + booking)

### Follow-up 2 (5-7 days after follow-up 1, final)
Shorter version — just the prototype link and a soft close:
- "Last one from me"
- Prototype link still live
- "If the timing isn't right, no worries"

## Rules
- Never send more than 3 emails total (initial + 2 follow-ups)
- Always personalize — never send the same email to two leads
- Always include the prototype link in at least the first email
- Always include the booking link: https://calendar.app.google/aYy6MJaq9zJAm7nQ9
- Sign off as "SimplifyOps Team" (no individual names) unless specified
- Send from admin@simplifyops.dev
- Always use the HTML template at `outreach/template.html` — fill the placeholders
