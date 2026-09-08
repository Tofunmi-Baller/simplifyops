Sync all SimplifyOps data across Gmail, Notion, and local files. This is the master sync command.

Run these steps in order:

1. **Check Gmail** for recent activity:
   - Search for emails sent from admin@simplifyops.dev in the last 7 days
   - Search for replies to any outreach emails
   - Note any new threads or responses

2. **Check local lead files** in `leads/` directory:
   - List all leads and their current status
   - Identify any that are out of sync (e.g., email sent but status not updated)

3. **Check Notion** — search the SimplifyOps Leads database:
   - Pull current status of all leads
   - Compare with local files and Gmail data

4. **Sync discrepancies:**
   - If Gmail shows an email was sent but lead status is still "Graded" → update to "Outreach Sent"
   - If Gmail shows a reply received → read it. If they asked to see the prototype, flag it as an action item to run `/send-prototype` today. Otherwise update lead to "Follow-up" or "Booked" depending on content
   - If Notion has updates not in local files → update local files
   - If local files have updates not in Notion → update Notion

5. **Report a sync summary:**
   ```
   SYNC REPORT — [date]
   ──────────────────
   Total leads: X
   Hot: X | Warm: X | Keep: X
   
   Pipeline:
   - New: X
   - Researched: X
   - Graded: X
   - Outreach Sent: X
   - Prototype Sent: X
   - Follow-up: X
   - Booked: X
   - In Progress: X
   
   Updates made:
   - [list any changes made during sync]
   
   Action items:
   - [any follow-ups due, leads to process, etc.]
   ```

6. **Commit changes** to git if any files were updated (ask user first).

This command should be run daily or whenever someone wants the full picture.