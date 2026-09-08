# SimplifyOps — Lead Process

## Pipeline Stages
1. **New** — lead received, not yet researched
2. **Researched** — all info gathered (LinkedIn, website, online presence)
3. **Graded** — classified as Hot / Warm / Keep
4. **Outreach Sent** — personalized email sent, offering the prototype (booking link only, no prototype link)
5. **Prototype Sent** — lead replied asking to see it; prototype link sent as a reply on the thread
6. **Follow-up** — no response, follow-up email queued or sent
7. **Booked** — call booked via calendar link
8. **In Progress** — project started
9. **Completed** — project delivered
10. **Lost** — lead went cold or declined

## Lead Data Structure
Each lead record contains:
- **Company**: name, website, LinkedIn page, industry, size estimate
- **Contact**: name, title/role, LinkedIn profile, email
- **Assessment**: current digital presence rating (1-10), identified needs, gaps spotted
- **Grade**: Hot / Warm / Keep (with reason)
- **Status**: current pipeline stage
- **Outreach**: email draft, prototype artifact link (held until they ask), date sent, date prototype sent
- **Follow-up**: follow-up dates, notes
- **Dates**: date added, last updated

## Research Process
When processing a new lead:
1. Visit their website — assess design quality, mobile responsiveness, speed, UX
2. Check LinkedIn company page — size, industry, recent posts, growth signals
3. Check contact's LinkedIn — role, tenure, recent activity
4. Look for pain points — outdated site, no mobile, slow load, missing features
5. Identify what they actually need (might not be what they think)
6. Note any competitors with better digital presence
7. Record everything in the lead file

## Notion Database
Leads are tracked in a Notion database called "SimplifyOps Leads" with:
- Kanban view by Status
- Table view for all data
- Filtered views: Hot Leads, This Week's Outreach, Follow-ups Due

## Gmail Integration
- Outreach emails sent from admin@simplifyops.dev
- When an email is sent, update the lead's status in Notion to "Outreach Sent"
- Track replies — if a reply comes in, update status. A reply asking to see the prototype is the trigger for `/send-prototype`: reply on that same thread with the link, then set status to "Prototype Sent"
- Sync command pulls latest Gmail activity and updates Notion
