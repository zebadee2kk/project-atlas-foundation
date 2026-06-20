# Proposal Lifecycle

A proposal is the bridge between a problem and an active project. This lifecycle aligns with the GitHub-native label set used on the project board.

## Status flow

```text
Draft -> needs-review -> needs-shaping -> accepted -> in-progress -+-> needs-verification -> delivered
                                                                      |
                                                                      +-> blocked -> delivered or wont-do
```

### 1. Draft

Use the Proposal template in `.github/ISSUE_TEMPLATE/proposal.yml`. Keep the initial issue concise; add detail in linked docs or pinned comments as needed.

### 2. needs-review

The proposal has been opened and is awaiting initial triage. A maintainer or reviewer confirms scope and assigns `needs-shaping` when the proposal needs more research, scope definition, or risk analysis before full review.

### 3. needs-shaping

Active research: collect existing solutions, constraints, risks, likely maintainers, and any safety concerns. Expected artefacts: short scoping note, maintainer volunteer, safety review snapshot.

### 4. accepted

Score and safety review are complete (see `docs/impact-scoring.md` and `docs/scoring-example.md`). A maintainer promotes the proposal and assigns a project lead.

### 5. in-progress

Delivery has started. The assigned lead breaks the proposal into tasks, opens implementation work, and keeps the issue updated.

### 6. blocked

Active work is paused due to a missing dependency, skill, decision, or external requirement. Unblock and resume `in-progress` when the blocker is cleared.

### 7. needs-verification

Implementation or document delivery is complete. The lead requests final review, testing, or community sign-off.

### 8. delivered

The proposal has been accepted, reviewed, and moved to Done on the project board.

### 9. wont-do / Archived

The proposal is declined, duplicated, out of scope, or no longer relevant. Close the issue with a brief rationale so future proposers can learn from it.

## Promotion check

Before promoting from `accepted` to `in-progress`, confirm:
- Problem, beneficiaries, and proposed outcome are each stated plainly.
- No unresolved high-severity safety or legal concern.
- At least one maintainer or project lead has accepted ownership.
- At least one first task is listed.

## Escalation

If after 14 days a proposal has no review comment, add a reminder as a pinned comment during weekly triage.
