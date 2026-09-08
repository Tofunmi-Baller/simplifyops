# SimplifyOps

## What This Is
SimplifyOps is a code and digital services agency. This folder contains all business operations: context docs, lead management, session logs, outreach templates, and website assets.

## Business Model
We are a prototype-first, speed-focused agency. We don't sell a rigid menu — we diagnose what the client actually needs and build it fast (2-3 weeks).

### Core Process
1. **Lead intake** — receive leads from various sources
2. **Lead research** — pull info from LinkedIn, website, online presence; fill gaps with research
3. **Lead grading** — classify as hot / warm / keep-nurture
4. **Outreach** — send a personalized email saying we already built a prototype for them and asking if they want to see it. The cold email carries the booking link only; the prototype link goes out as a reply once they ask (an unfamiliar artifact URL in a cold email reads as a scam)
5. **Delivery** — ship within 2-3 weeks

### Services (flexible umbrella)
- Website development
- Web app development
- Mobile apps
- Automation and integrations
- Dashboards and internal tools
- Any digital service the client needs — we adapt

### Key Selling Points
- **Speed**: 2-3 week delivery on work that typically takes months
- **Prototype-first**: leads see a working preview before signing anything
- **Flexible**: we build what the client needs, not what's on a menu
- **Quality**: creative, polished, professional output

## Brand Identity
- **Vibe**: Bold and dark — dark backgrounds, high contrast, neon/vibrant accent colors, modern aggressive energy
- **No faces**: never show people or faces on the website or materials
- **Language**: simple, clear, no jargon — anyone should understand what we do
- **Identity**: brand-focused, no founder names or personal spotlights
- **Pricing**: never shown publicly — all custom, "book a call" approach

## Folder Structure
- `context/` — business context docs (overview, brand, processes, decisions)
- `leads/` — lead files, research, grading
- `sessions/` — session logs (one per conversation)
- `website/` — website source files
- `outreach/` — outreach drafts per lead (ask email, follow-ups, hand-off reply + prototype link)
- `.claude/commands/` — team skills (slash commands)

## Skills (Slash Commands)
Team members run these instead of writing long prompts:

| Command | What it does |
|---------|-------------|
| `/process-lead` | Research a new lead — gathers all info, assesses digital presence, creates lead file |
| `/grade-leads` | Grade all ungraded leads as Hot / Warm / Keep |
| `/verify-lead` | Re-check a lead's hook against its live site and correct Notion — required before outreach |
| `/generate-outreach` | Build prototype artifact + write personalized email for a specific lead (verifies first) |
| `/send-outreach` | Send the "want to see it?" email via Gmail — booking link, no prototype link (confirms before sending) |
| `/send-prototype` | After the lead says yes — reply on the thread with the prototype link |
| `/sync` | Sync everything — Gmail, Notion, local files. Shows full pipeline report |
| `/pipeline` | Quick pipeline snapshot — no changes, just status |

## Key Links
- **Booking**: https://calendar.app.google/aYy6MJaq9zJAm7nQ9
- **Email**: admin@simplifyops.dev
- **Domain**: simplifyops.dev
- **GitHub**: https://github.com/Tofunmi-Baller/simplifyops

## Context Docs (read these for full detail)
- `context/business-overview.md` — what we are and how we work
- `context/brand-identity.md` — visual direction, tone, content rules
- `context/contacts-and-links.md` — domain, email, booking, socials
- `context/lead-process.md` — full lead pipeline and data structure
- `context/grading-criteria.md` — how to classify leads (Hot/Warm/Keep)
- `context/verification-process.md` — how to re-verify a lead before outreach (mandatory gate)
- `context/email-templates.md` — outreach email structure and rules
- `context/prototype-process.md` — how to build lead prototypes

## Session Protocol
After every session, update:
1. The session log in `sessions/` with what was covered
2. Any context docs that gained new information
3. Keep everything current so the next session starts with full context

## For New Team Members
1. Clone the repo: `git clone https://github.com/Tofunmi-Baller/simplifyops.git ~/simplified-ops`
2. Open Claude Code from the `simplified-ops/` folder
3. This CLAUDE.md gives Claude all the context. Use the slash commands above — they handle the prompting for you.
4. Run `/sync` first to see the current state of everything.
