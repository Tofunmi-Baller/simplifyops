Show the current SimplifyOps lead pipeline status. Quick overview, no changes.

1. **Read all lead files** in `leads/` directory
2. **Group by grade** (Hot / Warm / Keep) and **by status** (New → Completed)
3. **Check for action items:**
   - Any Hot leads without outreach sent?
   - Any outreach sent more than 3 days ago without follow-up?
   - Any follow-ups due today?
   - Any booked calls coming up?

4. **Display a clean summary:**
   ```
   PIPELINE — [date]
   ──────────────────
   
   HOT LEADS
   [Company] — [Status] — [Last action date]
   
   WARM LEADS
   [Company] — [Status] — [Last action date]
   
   KEEP
   [Company] — [Status] — [Last action date]
   
   ACTION ITEMS
   - [what needs attention right now]
   ```

No changes, no syncing — just a snapshot. Run /sync for a full update.