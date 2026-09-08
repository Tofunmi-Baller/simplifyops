# Session — 08-09-26

## Covered
Switched outreach from "here's the prototype link" to "we built a prototype — want to see it?"
An unfamiliar artifact URL in a cold email from an unknown sender reads as a scam, to the
recipient and to the spam filter. So the cold email no longer links the prototype — the
primary action is a reply.

### Rule
- **Email 1 + both follow-ups**: no prototype link. The email states the observation, proves
  the research, says we already built it, and asks "would you like to see it?" The booking
  link stays — calendar.app.google is a known Google domain and the ordinary business ask,
  and it gives the reader a second way in if they'd rather talk than look at a demo.
- **Hand-off reply**: sent on the existing thread only after the lead says yes. This is the
  one email carrying the prototype link.

### Files changed
- `outreach/template.html` — rewritten as v5, ask-first. Booking link only. Old version
  archived at `outreach/template-v4-link-in-email.html`
- `outreach/template-reply.html` — new. The hand-off email. Placeholders: `{{BUILT}}`,
  `{{DEMO_URL}}`, `{{TRY_THIS}}`
- `context/email-templates.md` — rewritten around the ask-first rule; new `{{BUILT}}` and
  `{{TRY_THIS}}` placeholders, per-template placeholder table, rewritten follow-ups
- `.claude/commands/send-prototype.md` — new skill. Confirms the lead actually asked, checks
  the artifact is live, replies on the thread, sets status to Prototype Sent
- `.claude/commands/generate-outreach.md` — now writes 4 emails (ask, 2 follow-ups, hand-off);
  hand-off marked DO NOT SEND UNTIL THEY ASK
- `.claude/commands/send-outreach.md` — checks the draft is link-free before sending
- `.claude/commands/sync.md` — a reply asking to see the prototype becomes an action item
- `.claude/commands/pipeline.md` — flags any lead who asked but hasn't been sent it
- `context/lead-process.md` — new pipeline stage 5: **Prototype Sent**
- `context/prototype-process.md`, `context/business-overview.md`, `CLAUDE.md` — propagated

### Notion
- Added **Prototype Sent** (pink) as a Status option on the SimplifyOps Leads database,
  between "Outreach Sent" and "Follow-up". All existing options and values untouched.

## Next Steps
- Regenerate any outreach drafts written under the old link-in-email template
- Connect GitHub auth so changes can be pushed, not just committed locally
