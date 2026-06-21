# Shaping Document: Open-Source Issue Triage Assistant (#7)

**Created:** 2026-06-21
**Score:** 22/30 — Accept
**Shaping Agent:** Team B (Hermes Agent)

---

## Refined Scope

### In Scope
Build an opt-in GitHub Action that helps open-source maintainers triage incoming issues using semantic similarity and templated AI responses. The MVP focuses on three high-value features:

1. **Duplicate issue grouping** — When a new issue is opened, compute semantic embeddings against existing open issues and suggest potential duplicates with a similarity score.
2. **High-impact bug flagging** — Identify issues mentioning security, data loss, crashes, or critical functionality and apply a `high-impact` label.
3. **Weekly triage report** — Generate a markdown summary of open issues grouped by category, highlighting stale items and unlabeled issues.

### Explicitly Out of Scope (v1)
- Auto-closing issues
- Auto-responses to users (too high risk for v1; deferred to v2)
- Integration with non-GitHub platforms
- Suggest assignees (requires contributor activity data not reliably available)

### Success Metrics
- Reduce average triage time per issue by ≥50% for pilot projects
- Achieve ≥80% precision on duplicate detection in pilot
- Used by ≥3 open-source projects within first month

---

## Key Research Questions

1. **What is the current baseline for open-source triage practices?** How long do maintainers spend on triage weekly? What tools do they currently use?
2. **Which embedding models work best for GitHub issue similarity?** Evaluate `nomic-embed-text`, `text-embedding-ada-002`, and `all-MiniLM-L6-v2` on a labeled dataset of duplicate issues.
3. **What makes a triage report actionable?** Survey 10+ maintainers on format, frequency, and content preferences.
4. **What are the false-positive rates for keyword-based vs. semantic duplicate detection?** A keyword baseline is simpler and may be "good enough."

---

## Suggested Approach

### Phase 1 — Research (Week 1-2)
- Survey 10-15 open-source maintainers on triage pain points (use GitHub Discussions, Reddit r/opensource, Mastodon)
- Collect a ground-truth dataset of 50+ duplicate issue pairs from popular repos (e.g., microsoft/vscode, python/cpython)
- Benchmark 3 embedding models on the dataset for similarity recall

### Phase 2 — PoC (Week 3-4)
- Build a GitHub Action that:
  - Triggers on `issues.opened` and `issues.edited`
  - Computes embedding for new issue title + body
  - Compares against embeddings of open issues (stored in a JSON file or GitHub repository variable)
  - Comments with "Possible duplicates" list if similarity > 0.85
- Test on 2-3 pilot repositories

### Phase 3 — Iterate (Week 5-6)
- Add keyword-based baseline for comparison
- Add high-impact classifier (regex + lightweight ML)
- Generate weekly triage report as a GitHub issue
- Gather feedback from pilot maintainers

### Phase 4 — Harden & Publish (Week 7-8)
- Add comprehensive README and configuration guide
- Add GitHub Marketplace listing
- Write blog post for announcement
- Define contribution guidelines

---

## Dependencies & Open Questions

- **Dependency:** Requires a free embedding API or local model. `nomic-embed-text` via Ollama is free but requires self-hosting. GitHub Actions has free compute for public repos.
- **Open Question:** Should the action store embeddings in the repo itself or use an external store? Repo storage is simpler but adds noise.
- **Open Question:** What similarity threshold minimizes false positives while catching real duplicates? Needs empirical testing.

---

## Risks
| Risk | Mitigation |
|------|------------|
| AI misclassifies critical issues as duplicates | Threshold-based with manual override; never auto-close |
| Low maintainer adoption | Start with friendly pilot projects; iterate on feedback |
| Embedding costs at scale | Use local model (nomic-embed-text) via Ollama for self-hosters |
| Maintainers feel replaced by AI | Position as assistant, not replacement; all actions are suggestions |

---

## Related Documents
- `docs/research-agent-workflow.md` — research phase process
- `docs/seed-proposal-scores.md` — scoring details
- `docs/safety-agent-checklist.md` — safety review checklist
