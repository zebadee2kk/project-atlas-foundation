# Create foundation GitHub Project board

## Context

`docs/launch-checklist.md` lists **Create GitHub Project board** as an
unresolved founding task. The operational model in
`docs/operating-model.md` expects GitHub Projects for roadmap and status
tracking.

## Work required

1. At [zebadee2kk/project-atlas-foundation](https://github.com/zebadee2kk/project-atlas-foundation), create a new **Projects** board linked to the repository.
2. Create the nine columns in the exact order and with the exact names defined in [`docs/project-board-plan.md`](../../docs/project-board-plan.md):


   1. Inbox
   2. Shaping
   3. Review
   4. Approved
   5. Active
   6. Blocked
   7. Needs verification
   8. Done
   9. Won't do / Archived

3. Enable the automations specified in `docs/project-board-plan.md`:
   - Auto-add new issues to Inbox
   - Map proposal/status labels (`needs-shaping`, `needs-review`,
     `accepted`, `in-progress`, `blocked`, `needs-verification`,
     `delivered`, `wont-do`) to their corresponding columns
   - Weekly stale-blocked check (14-day threshold)
   - Weekly verification reminder (7-day threshold)
   - Auto-reopen issues moved back to **Review**

4. Link any active issues from `backlog/seed-ideas.md` as proposal issues
   into the board and route them through **Inbox → Shaping**.

## Definition of done

- The board exists with all nine columns in the correct order.
- All automations are active and confirmed working.
- Existing backlog proposal issues are loaded into the board.
- `docs/launch-checklist.md` item "Create GitHub Project board" is checked.
