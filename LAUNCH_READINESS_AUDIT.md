# Launch Readiness Audit — repo-atlas-foundation

**Repo:** `zebadee2kk/project-atlas-foundation`
**Audited:** 2026-06-20
**Source of truth:** `docs/launch-checklist.md`, operation model, labels, templates, Pages/Discussions/Projects API.

---

## Summary

A solid governance and docs foundation is in place, but this repository **is not yet ready for public launch**. The repository is missing 5 GitHub-native integrations (Discussions, Pages, a populated Project board, missing status labels, CI), 2 broken internal links, and several standard launch artifacts (LICENSE, SECURITY.md, PR template).

---

## Findings (priority order)

### P0 — Blocker for public launch

1. **GitHub Discussions: disabled**
   - `gh repo view` → `hasDiscussionsEnabled: false`
   - `docs/launch-checklist.md` explicitly lists this unchecked
   - `docs/discussions-setup.md` is ready (categories, inaugural post, moderation)
   - **Action:** Enable Discussions and create 4 categories (Announcements, Ideas, General Q&A, Proposals).

2. **GitHub Pages: not configured**
   - Pages API → 404 Not Found
   - Landing page (`website/index.html`, `index.html`) exists but is not served
   - `docs/launch-checklist.md` decision (GitHub Pages vs Cloudflare Pages) remains open
   - **Action:** Decide hosting (GitHub Pages is the simplest first step given the static starter), then configure source branch and set `homepageUrl` in repo settings.

3. **GitHub Project board: not created**
   - `hasProjectsEnabled: true` but `gh project list` is empty
   - Required 9-column blueprint is defined in `docs/project-board-plan.md` (Inbox → Won't do / Archived) with 6 automations
   - **Action:** Create the board, add columns in order, configure automations, seed backlog issues.

4. **Missing proposal-status labels required for board automation**
   - `gh label list` shows defaults + `community, setup, task, governance, proposal, needs-review, naming, website, agentic, research, good-first-issue`
   - Labels required by `docs/project-board-plan.md` and missing:
     - `needs-triage`
     - `needs-shaping`
     - `accepted`
     - `in-progress`
     - `blocked`
     - `needs-verification`
     - `delivered`
     - `wont-do`
   - Without these, column automations will not work and the board cannot be used.
   - **Action:** Create all 8 labels with intuitive colors (e.g., grey/blue/green/yellow/red/purple/teal).

5. **No `.github/workflows`**
   - CI/CD is standard for public launches even on doc-only repos (links, markdown lint, issue template validation).
   - Docs refer to automations, but nothing materializes without at least a workflow skeleton.
   - **Action:** Add a minimal workflow: `markdownlint`, `link-check` on PR, and a template for CODEOWNERS/review assignments.

### P1 — High priority

6. **Broken internal markdown links: 2**
   - `.github/ISSUE_TEMPLATE/issue-1-body.md` → `docs/discussions-setup.md` (relative path broken from the templates folder)
   - `.github/ISSUE_TEMPLATE/issue-2-body.md` → `docs/project-board-plan.md`
   - Both resolve to nonexistent paths under `.github/ISSUE_TEMPLATE/`, which is confusing for triagers.
   - **Action:** Change to `../docs/...` or restore context block once PR lands.

7. **Missing `LICENSE`**
   - Public launch without an open license is a major trust and reusability issue.
   - `docs/operating-model.md` mentions public repositories; future projects will depend on licensing clarity.

8. **Missing `SECURITY.md`**
   - Expected in almost all public repos; required for `isSecurityPolicyEnabled`.
   - Needed before accepting PRs and community attachments.

9. **Missing pull request template**
   - `.github/PULL_REQUEST_TEMPLATE/` does not exist.
   - Without it, PRs lack scope, risks, and AI-assistance disclosure fields referenced in `docs/ai-assistant-policy.md`.

### P2 — Should complete within first public week

10. **Missing bug and feature issue templates**
    - `docs/new-project-checklist.md` expects `bug.yml` and `feature.yml` for promoted projects; the foundation repo currently uses only `proposal.yml` and `task.yml`.
    - Not strictly a launch blocker for the foundation itself, but creates an inconsistent experience.

11. **No `dependabot.yml` or `renovate.json`**
    - Not strictly required for a doc-first launch, but expected for any public open-source repo.

12. **`homepageUrl` empty**
    - Related to #2; once Pages is configured, set it on the repo.

---

## Recommended priority order for next steps

1. Enable Discussions + create categories + inaugural post.
2. Decide Pages host and configure deployment; fix landing page CTA/subsection placeholders.
3. Create the GitHub Project board (9 columns, automations).
4. Add missing proposal-status labels.
5. Add `LICENSE`, `SECURITY.md`, and a PR template.
6. Add a basic CI workflow (link-check + markdownlint).
7. Fix broken links in `.github/ISSUE_TEMPLATE/issue-{1,2}-body.md`.
8. Add bug/feature issue templates and Dependabot config.
