# Scoring example: Open-source school air quality monitor

Proposal: deploy low-cost, open-source air quality monitors in schools located in industrial corridors, delivering real-time data to parents, teachers, and local health services.

---

## Score walkthrough

| Category | Score (1–5) | Rationale | Evidence |
|---|---|---|---|
| Human benefit | 4 | Protects children's respiratory health and cognitive performance by giving schools actionable pollution data. | WHO links long-term particulate exposure to asthma and reduced lung development in children; 2024 local air quality reports in three candidate cities show frequent exceedances near primary schools. |
| Urgency | 4 | Industrial-grade pollution in residential districts is worsening in several mid-income cities where new schools continue to be built. | 2025 WHO global update notes 99% of the world's population breathes air above recommended limits; two of the three target cities recorded record PM2.5 levels in Q1 2026. |
| Feasibility | 3 | Hardware assembly and firmware are straightforward using existing open designs, but procurement approval and sustained maintenance in school environments require more effort than a typical software-only proposal. | Luftdaten and PurpleAir open hardware show clear proof-of-concept; school administrators in two districts require minimum 6-month procurement cycles and confirmed maintenance plans. |
| Reusability | 5 | All hardware design files, firmware, data ingestion pipelines, and dashboard front-ends can be released under permissive licences for other cities or communities to fork. | Prior open-source sensor projects have been reused across 15+ countries; standard LoRa/WiFi data formats are already interoperable with city-wide air quality networks. |
| Neglectedness | 4 | Commercial calibrated monitors are expensive ($300–$800/unit) and rarely deployed at school-granularity; no existing open project focuses specifically on school environments in industrial zones. | Existing open projects (Luftdaten, AirQo) focus on general neighbourhood coverage; no maintained package addresses the school-specific installation and child-privacy requirements. |
| Contributor fit | 3 | Requires electronics, embedded firmware, and education-sector outreach skills—not all available in the current community roster. | Community contributors have strong WebAssembly and dashboard expertise, but only two members list embedded hardware experience and none have school-district partnerships. |
| Safety | 4 | Low physical and digital risk. Standard IoT security practices apply; community notes a minor concern around children's location metadata if GPS-enabled sensors are used indoors. | A privacy-by-default design (no GPS, hashed school IDs) eliminates the main concern; physical installation presents only standard electrical safety requirements. |

---

## Total and interpretation

Using the draft formula:

```
Priority = Human benefit + Urgency + Feasibility + Reusability + Neglectedness + Contributor fit − Safety risk penalty
```

The Safety risk penalty is derived from the Safety score, where a score of 5 represents no safety concern. With a Safety score of **4**, the risk penalty is **1**.

```
Priority = 4 + 4 + 3 + 5 + 4 + 3 − 1 = 22
```

**Result: 22 out of 30**

**Interpretation: moderate-to-high priority.**

This proposal justifies forward movement. Its strengths are clear public benefit, strong reusability, and genuine market/project neglectedness. The main constraints are moderate feasibility (mostly institutional, not technical) and limited contributor fit in hardware and education-sector outreach. 

A next step would be to recruit or partner with two contributors who have embedded electronics experience, and to map the procurement consent process in at least one target district before requesting a formal resource commitment.
