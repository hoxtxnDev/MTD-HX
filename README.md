# 🔍 MTD-HX v1 — Cybersecurity Research Framework

> A structured methodology for conducting ethical cybersecurity hypothesis research — from threat identification to formal reporting.

**Author:** Horacio N.

---

## About the name

**MTD-HX** stands for **Methodology for Threat Documentation — Hypothesis** (Metodología de Documentación de Amenazas — Hipótesis). It is a structured, ethics-first framework for producing technically rigorous cybersecurity research reports based on public sources only.

---

## What is this?

This repository contains a **reusable framework** for structuring cybersecurity research and threat hypotheses in an academic and investigative context. It is not a hacking toolkit — it is a **documentation and analysis methodology** designed to produce technically rigorous, legally grounded, and ethically responsible reports.

The framework was developed and validated through a real applied case: the analysis of the **Clínica Dávila data breach (December 2025)** and its potential correlation with public Chilean RUT.

---

## Framework Phases

```
[1. SCOPE]→ [2. FACTS]→ [3. HYPOTHESIS]→ [4. TAXONOMY]→ [5. RISK]→ [6. RECOMMENDATIONS]→ [7. LEGAL]→ [8. REPORT]
```

| Phase | Description | Template |
|---|---|---|
| 1. Scope Definition | Define objectives, boundaries, and ethical constraints | [scope.md](./templates/01-scope.md) |
| 2. Verified Facts | Document only publicly verifiable information | [facts.md](./templates/02-facts.md) |
| 3. Technical Hypothesis | Formulate the attack vector or threat model | [hypothesis.md](./templates/03-hypothesis.md) |
| 4. Attack Taxonomy | Classify the attack using standard frameworks | [taxonomy.md](./templates/04-taxonomy.md) |
| 5. Risk Analysis | Assess probability, impact, and risk level per vector | [risk.md](./templates/05-risk.md) |
| 6. Recommendations | Produce actionable mitigations per stakeholder | [recommendations.md](./templates/06-recommendations.md) |
| 7. Legal Framework | Map applicable laws and regulatory obligations | [legal.md](./templates/07-legal.md) |
| 8. Final Report | Compile into a structured deliverable | [report-template.md](./templates/08-report-template.md) |

---

## Repository Structure

```
MTD-HX-v1/
├── README.md                        ← You are here
├── README.es.md                     ← Versión en español
├── docs/
│   ├── en/
│   │   └── methodology.md           ← Full methodology explanation (EN)
│   └── es/
│       └── metodologia.md           ← Explicación completa (ES)
├── templates/                       ← Reusable markdown templates per phase
│   ├── 01-scope.md
│   ├── 02-facts.md
│   ├── 03-hypothesis.md
│   ├── 04-taxonomy.md
│   ├── 05-risk.md
│   ├── 06-recommendations.md
│   ├── 07-legal.md
│   └── 08-report-template.md
├── cases/
│   └── example-davila-rutificador/  ← Applied case study
│       ├── README.md
│       ├── 01-scope.md
│       ├── 03-hypothesis.md
│       └── 05-risk.md
└── assets/
    └── framework-diagram.png        ← Visual diagram (coming soon)
```

---

## Key Principles

- ✅ **Ethics first** — No actual breach data accessed, downloaded, or reproduced
- ✅ **Source transparency** — Only publicly verifiable facts are documented
- ✅ **Legal grounding** — Every analysis maps to applicable legislation
- ✅ **Reproducibility** — Templates allow any researcher to follow the same process
- ✅ **Responsible disclosure** — Findings reported to competent authorities (PDI, CSIRT)

---

## Applied Case Study

| Field | Detail |
|---|---|
| Case | Clínica Dávila Breach + Rutificador Correlation Hypothesis |
| Attack type | Data Enrichment Attack / Re-identification Attack |
| Pivot field | Chilean RUT (national ID number) |
| Reported to | PDI Cibercrimen, CIPER Chile |
| Date | May 3, 2026 |

→ Full case: [`/cases/example-davila-rutificador/`](./cases/example-davila-rutificador/)

---

## Legal Notice

This framework and all associated case studies are produced for **academic and investigative purposes only**. No breach data was accessed, downloaded, or reproduced. All analysis is based exclusively on publicly available information.

Applicable Chilean law: Ley 19.628 (Data Privacy), Ley 21.663 (Cybersecurity Framework).

---

## License

MIT — Free to use, adapt, and build upon with attribution.
