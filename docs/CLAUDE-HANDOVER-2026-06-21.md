# Claude Code Handover — 2026-06-21

**From:** OWL (Hermes Agent, orchestrator session)
**To:** Claude Code (next operator session in this repo)
**Context:** Multi-agent team setup + repo sync + issue triage

---

## What happened this session

OWL (running on Hermes Agent) spent the day setting up a multi-agent coding team on the Mac AI Server (M1 Pro, 16GB RAM, Ollama) and using it to advance the project-atlas-foundation repo. This handover captures everything Claude Code needs to pick up where we left off.

### Key accomplishments

1. **Ollama infrastructure on Mac AI Server** — Brew install, launchd service, 9 models pulled, management scripts at `~/.ollama/scripts/`
2. **Memory system fixed** — Ollama bound to `0.0.0.0:11434` (was `127.0.0.1`), Letta provider updated, dual_memory.py writes verified to both Mem0 and Letta
3. **Multi-agent team deployed** — 6 agents (orchestrator, architect, implementer, researcher, reviewer, utility) with shift-based concurrency (max 2 models in 16GB RAM)
4. **Team produced deliverables:**
   - `docs/candidate-names.md` — 10 naming candidates (mistral:7b)
   - `docs/seed-proposal-scores.md` — 5 proposal scores (deepseek-r1:8b)
5. **Repo sync** — Merged 27 commits from `/home/richardham/hermes-mgmt` (feat branch) into canonical `~/Documents/Github/hermes-mgmt`, pushed to origin
6. **Issue triage** — Closed #23 (names) and #18 (seed proposals), commented on all remaining issues with status updates and next steps

---

## Repo state

### project-atlas-foundation (`/home/richardham/project-atlas-foundation`)

| Branch | Status |
|---|---|
| `main` | ✅ In sync with origin/main, all work pushed |

**Open issues:** #3, #4, #5, #6, #7, #8, #9, #10, #11, #12, #15, #16, #22, #31, #32
**Closed this session:** #23, #18

**Issue status summary:**

| Issue | Title | Status | Score |
|---|---|---|---|
| #3 | Open Privacy Redaction Gateway | needs-review | Not scored |
| #4 | Public-Good Agent Template Library | needs-shaping | Not scored |
| #5 | Small Charity Automation Kit | needs-shaping | Not scored |
| #6 | Elder Digital-Access Assistant | needs-shaping | Not scored |
| #7 | Open-Source Issue Triage Assistant | needs-shaping | Not scored |
| #8 | Climate Action Project Map | needs-shaping | 16/25 — Reject |
| #9 | Community Cyber Hygiene Scanner | needs-shaping | 18/25 — Needs shaping |
| #10 | Public Project Research Packs | needs-shaping | 19/25 — Accept |
| #11 | AI Accessibility Toolkit | needs-shaping | 21/25 — Accept |
| #12 | Open Civic Form Automation | needs-shaping | 20/25 — Accept |
| #15 | Enable Discussions | Open (owner) | — |
| #16 | Project board | Blocked by #32 | — |
| #22 | Recruit contributors | Open | — |
| #31 | Launch readiness | Open (owner) | — |
| #32 | Create Projects board | Open (owner) | — |

### hermes-mgmt

| Branch | Status |
|---|---|
| `main` (canonical: `~/Documents/Github/hermes-mgmt`) | ✅ Pushed to origin, up to date |
| `park/multi-agent-team-arch` | ✅ Merged into main |
| `feat/mac-ai-ollama-dashboard` (in `/home/richardham/hermes-mgmt`) | ✅ Merged into canonical main |
| `feature/hermes-secrets-vault-architecture` (in `/home/richardham/hermes-mgmt`) | ✅ Merged into canonical main |

---

## Mac AI Server access

- **SSH:** `rham-admin@mac-ai-server` (key auth, no password)
- **Tailscale IP:** `100.120.253.20`
- **Ollama:** `http://100.120.253.20:11434` (bound to `0.0.0.0`)
- **Models (9):** hermes3:8b, qwen2.5-coder:7b, deepseek-r1:8b, mistral:7b, qwen2.5:7b, llama3.2:3b, codellama:7b, starcoder2:7b, nomic-embed-text
- **Constraint:** Max 2 loaded simultaneously (16GB RAM, ~1GB free after system)
- **Management scripts:** `~/.ollama/scripts/` (ollama-team-swap.sh, ollama-model-manager.sh, ollama-resource-monitor.sh, ollama-benchmark.sh, ollama-team-coord.sh)
- **Response normalizer:** `~/Hermes/scripts/ollama_response_normalizer.py`

### Ollama API quirks

- **deepseek-r1** only works via `/api/generate` (NOT `/v1/chat/completions`)
- Use `format:"json"` for structured output
- Use `think:false` for deepseek-r1
- Use `options.num_predict` (not `max_tokens`)
- Use `shlex.quote` for JSON in SSH+curl commands
- RAM guard: check ≥3GB free before loading a new model

---

## Memory system architecture

```
Ollama on Mac (0.0.0.0:11434)
    ↓
Mem0 plugin (embed + LLM) → Qdrant (127.0.0.1:6333)
    ↓
Letta (localhost:8283) → Provider DB base_url → Ollama (100.120.253.20:11434/v1)
    ↓
Postgres + Redis
```

**Failure docs:** `hermes-mgmt/docs/memory-system-failure-modes.md`

**If memory breaks:**
1. Check Ollama is running on Mac: `ssh rham-admin@mac-ai-server "ollama ps"`
2. Check Ollama binds `0.0.0.0`: `curl http://100.120.253.20:11434/api/tags`
3. Check Letta provider: `curl http://localhost:8283/v1/health`
4. Check Letta can reach Ollama: `docker exec docker-letta-1 curl http://100.120.253.20:11434/api/tags`

---

## Durable facts stored to Mem0 + Letta

1. Ollama team roles + bind fix
2. Ollama routing quirks (`/api/generate`, `shlex.quote`, `num_predict`, `format:json`, `think:false`)
3. `project-atlas-foundation` repo state (candidate names, proposal scores, closed/remaining issues)

---

## Recommended next tasks for Claude Code

### Priority 1 — Score remaining proposals (#3-#7)

The Architect agent (deepseek-r1:8b) scored 5 proposals as a calibration batch. The remaining 5 unscored proposals (#3-#7) need scoring using the same impact scoring model.

**Prompt to use:**
```
Read docs/impact-scoring.md and docs/seed-proposal-scores.md to understand the scoring model and calibration. Then score the following proposals using the same criteria:

- Issue #3: Open Privacy Redaction Gateway
- Issue #4: Public-Good Agent Template Library
- Issue #5: Small Charity Automation Kit
- Issue #6: Elder Digital-Access Assistant
- Issue #7: Open-Source Issue Triage Assistant

For each proposal, read the issue description, score it on all 7 criteria (Human Benefit, Urgency, Feasibility, Reusability, Neglectedness, Contributor Fit, Safety), and add the results to docs/seed-proposal-scores.md. Then comment on each issue with its score.
```

### Priority 2 — Shape top-scored proposals

The 3 "Accept" proposals (#11 AI Accessibility Toolkit, #12 Open Civic Form Automation, #10 Public Project Research Packs) are ready for the research workflow. Move them from `needs-shaping` to `ready-for-research` and begin the research phase defined in `docs/research-agent-worklist.md`.

### Priority 3 — Set up Project board (#32)

Create a GitHub Projects board from `docs/project-board-plan.md`. This unblocks #16 and gives the community a visual workflow.

### Priority 4 — Landing page content review

The landing page was designed by the team but hasn't been reviewed for accuracy. Check the deployed page against the current repo state and update any stale content.

---

## Files to read first

1. `docs/vision.md` — project vision and goals
2. `docs/operating-model.md` — how the platform works
3. `docs/research-agent-workflow.md` — research phase process
4. `docs/safety-agent-checklist.md` — safety review checklist
5. `docs/impact-scoring.md` — scoring model
6. `docs/seed-proposal-scores.md` — scored proposals (reference)
7. `docs/candidate-names.md` — generated names
8. `docs/project-board-plan.md` — board structure
9. `hermes-mgmt/docs/memory-system-failure-modes.md` — if memory acts up
10. `hermes-mgmt/docs/multi-agent-team-architecture.md` — team roster and shift model
