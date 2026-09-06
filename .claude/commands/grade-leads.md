Grade all ungraded leads in the SimplifyOps pipeline.

1. **Read the grading criteria** from `context/grading-criteria.md`
2. **Scan all lead files** in `leads/` directory
3. **Identify ungraded leads** — any lead file without a grade or with status "New" or "Researched"
4. **For each ungraded lead:**
   - Review all research data in the lead file
   - Apply the grading criteria
   - Assign Hot / Warm / Keep with a one-sentence reason
   - Update the lead file with the grade
   - Update the status to "Graded"

5. **Update Notion** with all new grades

6. **Report:**
   ```
   GRADING COMPLETE — [date]
   ──────────────────
   [Company] → Hot — [reason]
   [Company] → Warm — [reason]
   [Company] → Keep — [reason]
   
   Next: Run /generate-outreach [company] for Hot leads
   ```

If a lead doesn't have enough research data to grade properly, flag it and suggest running /process-lead on it first.