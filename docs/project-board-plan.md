# Project Board Plan

This document defines the columns, automations, and lifecycle mapping for the
foundation-level GitHub Project board used in
`zebadee2kk/project-atlas-foundation`.

The board tracks two item types: **Proposals** and **Tasks**. Both start as
issues using `.github/ISSUE_TEMPLATE/proposal.yml` or
`.github/ISSUE_TEMPLATE/task.yml` and flow through the board via label-driven
automation.

---

## Columns

Use these exact column names. Order matters: items progress left to right.

| Order | Column | Purpose |
|---|---|---|
| 1 | **Inbox** | New issues and PRs awaiting triage or initial response. |
| 2 | **Shaping** | Proposals or tasks that need domain research, scope, or risk analysis before review. |
| 3 | **Review** | Ready for community or maintainer review per the impact scoring framework. |
| 4 | **Approved** | Accepted and ready for execution; awaiting maintainer assignment. |
| 5 | **Active** | Work in progress with an assigned maintainer or contributor. |
| 6 | **Blocked** | Active work paused due to missing dependency, skill, or decision. |
| 7 | **Needs verification** | Implementation complete; awaiting final review or testing. |
| 8 | **Done** | Fully delivered outcome. Optionally archived after retention window. |
| 9 | **Won't do / Archived** | Explicitly declined, duplicated, or no longer relevant. |

---

## Labels and column mapping

Apply labels consistently so automation remains predictable.

| Label | Column | Auto-action triggered |
|---|---|---|
| `needs-triage` | Inbox | — |
| `needs-shaping` | Shaping | — |
| `needs-review` | Review | — |
| `accepted` | Approved | Move to **Approved** |
| `in-progress` | Active | Move to **Active** |
| `blocked` | Blocked | Move to **Blocked** |
| `needs-verification` | Needs verification | Move to **Needs verification** |
| `delivered` | Done | Move to **Done** |
| `wont-do` | Won't do / Archived | Move to **Won't do / Archived** |

Automation will ignore labels that do not map to a unique column. If an item
carries multiple mapping labels (e.g., `blocked` and `needs-verification`),
use the label that reflects the current blocking state; automation picks the
highest-priority match.

---

## Automation rules

Configure the following in **Settings > Automation** of the linked project board.

> If the GitHub UI does not expose the exact wording below, choose the closest
> native equivalent and note the deviation in `docs/decision-log/`.

### 1. Auto-add new issues to Inbox

- **Trigger:** Issue opened
- **Condition:** Always true
- **Action:** Add the issue to the board; apply `needs-triage` if no other
  mapping label is present at creation time.

### 2. Map proposal status labels to columns

- **Trigger:** Issue labeled or unlabeled
- **Condition:** Label is one of `needs-shaping`, `needs-review`, `accepted`,
  `in-progress`, `blocked`, `needs-verification`, `delivered`, `wont-do`
- **Action:** Move the card to the corresponding column listed above.

### 3. Auto-close archived items

- **Trigger:** Issue closed
- **Condition:** Label `wont-do` is present
- **Action:** Leave the card visible in **Won't do / Archived** for 90 days,
  then archive.

### 4. Blocked stale check

- **Trigger:** On a schedule (weekly)
- **Condition:** Card is in **Blocked**; last comment older than 14 days
- **Action:** Add `stale-blocked` label and notify the assignee.

### 5. Verification reminder

- **Trigger:** On a schedule (weekly)
- **Condition:** Card is in **Needs verification**; last activity older than 7
  days
- **Action:** @-mention the assignee requesting verification.

### 6. Re-open item moved back to Review

- **Trigger:** Card moved to **Review**
- **Condition:** Issue state is closed
- **Action:** Re-open the issue automatically, applying `reopened-by-board`
  and leaving a note linking to `docs/proposal-lifecycle.md`.

---

## Lifecycle mapping

The board mirrors the project lifecycle defined in `docs/project-lifecycle.md`
and the proposal lifecycle in `docs/proposal-lifecycle.md`.

```text
Inbox
  └─ needs-shape ─────────► Shaping
                              └─ needs-review ──────► Review
                                                       └─ accepted ──────────► Approved
                                                                              └─ in-progress ──────► Active
                                                                                                     └─ blocked ──────────► Blocked
                                                                                                   (unblock) ──────────► Active
                                                                                                     └─ needs-verification ► Needs verification
                                                                                                                           └─ delivered ──────► Done
                                                                                                                       (fail) ──────► Won't do / Archived
```

### Workflow summary

1. **Inbox → Shaping:** A maintainer triages and confirms the issue is valid.
   Apply `needs-shaping`. Research and scope occur here.
2. **Shaping → Review:** Proposals passing initial feasibility screening
   receive `needs-review`. Community review and impact scoring begin.
3. **Review → Approved:** Maintainers apply `accepted` once scoring, safety,
   and scope are clear.
4. **Approved → Active:** Assignee starts work; `in-progress` is applied.
5. **Active ↔ Blocked:** `blocked` halts active work. Remove `blocked` to
   resume. Stale blockers should be escalated weekly.
6. **Active → Needs verification:** Work is complete; `needs-verification`
   triggers a final review pass.
7. **Needs verification → Done:** After approval, apply `delivered`.
8. **Any column → Won't do / Archived:** Explicit decision to decline,
   duplicate, or close. Apply `wont-do` and a closing comment explaining the
   outcome.

---

## Governance compliance

- **Transparency:** All columns and automation rules are public within the
  repository settings.
- **Capture resistance:** No sponsor paywall or private control of workflow can
  affect board status (see GOVERNANCE.md).
- **Decision log:** Major board changes (new columns, altered automation,
  lifecycle changes) are recorded in `docs/decision-log/` once that directory
  is created.

---

## Related documents

- `docs/project-lifecycle.md`
- `docs/proposal-lifecycle.md`
- `GOVERNANCE.md`
- `docs/impact-scoring.md`
