# GitHub Discussions Setup

Enable GitHub Discussions at the repository level to separate broad debate from
structured proposals and tasks. This document covers exact setup steps and the
proposed category mapping for `zebadee2kk/project-atlas-foundation`.

---

## Prerequisites

- Repository admin access for `zebadee2kk/project-atlas-foundation`.
- `docs/project-lifecycle.md` already published (defines project stages).
- `docs/impact-scoring.md` already published (used in review discussions).

If either document is missing, add it before enabling Discussions so community
members have relevant references available from day one.

---

## 1. Enable the feature

1. Open <https://github.com/zebadee2kk/project-atlas-foundation/settings> while
   signed in as an admin.
2. Scroll to **Features**.
3. Under **Discussions**, select **Set up discussions**.
4. Optionally enable the **Discussions** entry in the main repository navigation
   tab by toggling it visible under **Repository features**.

No repository content is modified by this step. Issues, PRs, and existing files
are untouched.

---

## 2. Create categories

Create the following categories. Use the exact names below so labels and links
elsewhere in documentation remain consistent.

| Category | Description | Emoji | Allowed? |
|---|---|---|---|
| **Announcements** | Maintainer updates, scoring results, naming decisions, council notices | `📣` | Comments only |
| **Ideas** | Early-stage problems and rough proposals before formal review | `💡` | Comments and answers |
| **General Q&A** | Process questions, contribution guidance, onboarding | `❓` | Comments and answers |
| **Proposals** | Formal review of proposals per `docs/proposal-lifecycle.md` | `📝` | Comments and answers |

To create a category:

1. In **Settings > General > Features > Discussions**, click **Categories >
   New category**.
2. Enter the name and description exactly as listed above.
3. Select the emoji and comment/answer restriction as shown.
4. Click **Create**.

---

## 3. Draft an inaugural post

After enabling Discussions, pin the following post to **Proposals** to establish
the expected format:

Title: **Welcome to Project Atlas Discussions**

Body:

```text
Welcome.

Use this space to discuss problems, proposals, and process. Before creating
a formal proposal, consider starting in **Ideas** to gauge interest.

Review:

- docs/impact-scoring.md for how proposals are evaluated
- docs/proposal-lifecycle.md for the review stages
- docs/project-lifecycle.md for what happens after a proposal is accepted

Rules:

- Stay on topic and keep comments relevant to the discussion.
- Disclose conflicts of interest per GOVERNANCE.md.
- Do not use Discussions to report harmful content that needs urgent removal;
  use the moderation contacts defined in GOVERNANCE.md or open a private
  maintainer issue instead.
```

Set the post format to **Announcement** and pin it.

---

## 4. Configure moderation settings

1. In **Settings > General > Features > Discussions**, click **Moderation
   settings**.
2. Enable **Require approval for new comments** if the project anticipates
   spam; otherwise leave disabled for low friction during founding.
3. Leave **Flagged content auto-resolution** off during founding (manual review
   supports transparency).
4. Confirm at least one maintainer has admin-level moderation rights.
5. Document the moderation contact in `GOVERNANCE.md` if not already present.

---

## 5. Link from existing documents

Update the following files to reference the new Discussions location:

- `README.md` — add a bullet under **Get involved** linking to the
  **Proposals** category.
- `CONTRIBUTING.md` — mention that process questions go to **General Q&A**
  before opening issues.
- `docs/launch-checklist.md` — keep the **Enable GitHub Discussions** item
  checked only after categories are created and the inaugural post is pinned.

---

## 6. Category mapping reference

Use this table when triaging or migrating content.

| Source location | Target category | Label to apply |
|---|---|---|
| New rough problem statement | Ideas | `needs-shaping` |
| Formal proposal (proposal.yml) | Proposals | `needs-review` |
| Scaling review discussion | Proposals | `reviewing` |
| Accepted project | Proposals | `accepted` |
| Community announcement | Announcements | `announcement` |
| Onboarding / contribution help | General Q&A | `question` |

---

## Related documents

- `docs/proposal-lifecycle.md`
- `docs/impact-scoring.md`
- `GOVERNANCE.md`
- `docs/launch-checklist.md`
