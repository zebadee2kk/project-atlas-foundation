# Seed Proposal Scores — Generated 2026-06-21

Scored by the Architect agent (deepseek-r1:8b) using the impact scoring model from `docs/impact-scoring.md`.

## Scoring Summary

| Proposal | Human Benefit | Urgency | Feasibility | Reusability | Neglectedness | Contributor Fit | Safety | Total | Recommendation |
|----------|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|---|
| AI Accessibility Toolkit (#11) | 5 | 4 | 3 | 5 | 2 | 2 | 0 | **21** | Accept |
| Open Civic Form Automation (#12) | 4 | 3 | 4 | 4 | 2 | 3 | 0 | **20** | Accept |
| Open-Source Issue Triage Assistant (#7) | 4 | 3 | 4 | 4 | 3 | 4 | 0 | **22** | Accept |
| Public Project Research Packs (#10) | 3 | 2 | 4 | 5 | 1 | 4 | 0 | **19** | Accept |
| Community Cyber Hygiene Scanner (#9) | 4 | 5 | 3 | 3 | 1 | 2 | 0 | **18** | Needs shaping |
| Open Privacy Redaction Gateway (#3) | 4 | 4 | 3 | 4 | 3 | 2 | -1 | **19** | Needs shaping |
| Public-Good Agent Template Library (#4) | 4 | 3 | 4 | 5 | 3 | 3 | 0 | **22** | Accept |
| Small Charity Automation Kit (#5) | 4 | 3 | 3 | 3 | 4 | 2 | 0 | **19** | Needs shaping |
| Elder Digital-Access Assistant (#6) | 5 | 4 | 2 | 2 | 4 | 1 | 0 | **18** | Needs shaping |
| Climate Action Project Map (#8) | 5 | 4 | 2 | 3 | 1 | 1 | 0 | **16** | Reject |

## Notes
- **AI Accessibility Toolkit** scores highest due to high human benefit and reusability
- **Community Cyber Hygiene Scanner** has high urgency but needs scope shaping
- **Climate Action Project Map** has high impact but low feasibility and contributor fit for a small community
- All proposals have zero safety risk penalty unless noted
- Scores should be validated by human reviewers before promotion

## New scores (Team B, 2026-06-21)

### #7 — Open-Source Issue Triage Assistant (Score: 22/30 — Accept)
- **Human Benefit (4):** Directly helps open-source maintainers (large community), saves time on triage
- **Urgency (3):** Problem is ongoing but not rapidly worsening
- **Feasibility (4):** GitHub Action + embeddings approach is well-understood tech
- **Reusability (4):** MIT-licensed template, works across any OSS project via opt-in
- **Neglectedness (3):** Some bots exist (stale-bot, Copilot) but no open-source AI triage assistant
- **Contributor Fit (4):** Community has strong GitHub/GitHub Actions experience
- **Safety (0):** Low risk; auto-responses labeled as AI-assisted

### #4 — Public-Good Agent Template Library (Score: 22/30 — Accept)
- **Human Benefit (4):** Reduces duplicated effort for nonprofits and agent builders
- **Urgency (3):** Useful now but not time-critical
- **Feasibility (4):** Markdown + JSON schema templates, low technical complexity
- **Reusability (5):** Pure templates — maximally reusable, forkable, translatable
- **Neglectedness (3):** LangGraph templates exist but are generic; no public-good focus
- **Contributor Fit (3):** Requires prompt engineering skill; some contributors have this
- **Safety (0):** Templates are advisory; misuse risk is low

### #3 — Open Privacy Redaction Gateway (Score: 19/30 — Notes shaping)
- **Human Benefit (4):** Protects sensitive data for AI builders, small businesses, consultants
- **Urgency (4):** AI adoption accelerating; data exposure incidents increasing
- **Feasibility (3):** Proxy + regex + NER is proven but NER accuracy is challenging
- **Reusability (4):** Open-source proxy applicable across domains
- **Neglectedness (3):** Commercial solutions exist but no open-source local-first tool
- **Contributor Fit (2):** Requires NLP/security skills not yet confirmed in community
- **Safety (-1):** Over/under-redaction risk; penalty applied — must include clear limitations documentation

### #5 — Small Charity Automation Kit (Score: 19/30 — Needs shaping)
- **Human Benefit (4):** Frees charity workers from repetitive tasks; direct social impact
- **Urgency (3):** Persistent problem but not worsening rapidly
- **Feasibility (3):** n8n workflows are straightforward but charity partnerships slow deployment
- **Reusability (3):** Workflows are reusable but tailored to charity sector
- **Neglectedness (4):** Salesforce Nonprofit is expensive; no free sector-specific automation kit exists
- **Contributor Fit (2):** Requires domain knowledge of charity operations
- **Safety (0):** GDPR concerns manageable with proper data handling guide

### #6 — Elder Digital-Access Assistant (Score: 18/30 — Needs shaping)
- **Human Benefit (5):** Directly addresses digital exclusion for vulnerable elderly population
- **Urgency (4):** Digital-only services accelerating; exclusion worsening
- **Feasibility (2):** Browser extension + user testing with elderly is complex; accessibility is hard
- **Reusability (2):** Guides are task-specific; extension is Chrome/Firefox only
- **Neglectedness (4):** No open-source tool specifically for digital form navigation by elderly
- **Contributor Fit (1):** Requires UX research with elderly; unlikely skill in current community
- **Safety (0):** No data storage by design; phishing risk manageable with audited extension
