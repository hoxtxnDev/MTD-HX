# MTD-HX v2.0 — Cybersecurity Research Methodology

## Full Framework Usage Guide

---

## Why a Structured Framework?

Unstructured cybersecurity research produces two types of problems:

1. **Technically weak** — Hypotheses without explicit assumptions, no viability analysis, no acknowledgment of limitations. Easy to dismiss.
2. **Ethically compromised** — Without a clear scope and boundary declaration, any analysis can be challenged as facilitating harm.

This framework solves both problems by forcing the researcher to document every decision before making it.

---

## Integration with Industry Standards

MTD-HX v2.0 aligns with:

| Standard | How MTD-HX Integrates |
|---|---|
| **MITRE ATT&CK v15** | Tactics (TAXXXX), Techniques (TXXXX), Sub-techniques (TXXXX.XXX), and Detection Data Sources (DSXXXX) mapped in Phases 3 and 4 |
| **CVSS 4.0** | Full Base Score breakdown (AV/AC/AT/PR/UI/VC/VI/VA/SC/SI/SA) with quantitative + qualitative labels in Phase 5 |
| **OWASP Testing Guide v5** | Attack taxonomy cross-reference methodology in Phase 4 |
| **ISO 27001:2022** | Control mapping for recommendations in Phase 6 |
| **NIST SP 800-61 Rev 2** | Incident response lifecycle alignment through Phase 2 (facts) and Phase 7 (legal reporting) |

---

## The 8 Phases — Usage Guide

### Phase 1 — Scope Definition

- **When:** Before anything else.
- **Purpose:** Define what is in and out of scope, and make an ethical commitment to those boundaries.
- **Output:** Signed scope document with case ID, objectives, and authorized sources.
- **Common mistake:** Starting from the hypothesis and defining scope afterward. This contaminates analysis with confirmation bias.

### Phase 2 — Verified Facts

- **When:** Before formulating hypotheses.
- **Purpose:** Build the factual foundation of the analysis using only publicly verifiable sources.
- **Output:** Timelined fact table with source URLs for every claim.
- **Common mistake:** Mixing facts with inferences. If you don't have a source, it's not a verified fact.

### Phase 3 — Technical Hypothesis

- **When:** After documenting facts.
- **Purpose:** Formulate the attack model with explicit assumptions and acknowledged limitations. Now includes MITRE ATT&CK technique mapping.
- **Output:** Hypothesis statement + attack flow + MITRE technique reference.
- **Common mistake:** Presenting the hypothesis as confirmed fact. Always use conditional language.

**MITRE ATT&CK Integration:**
- Map each attack step to a specific technique ID (e.g., T1566.001 — Spearphishing Attachment)
- Identify the tactic (e.g., TA0001 — Initial Access)
- Document the detection data source (e.g., DS0015 — Application Log)
- Reference the data source component (e.g., `Application Log: Network Traffic`)

### Phase 4 — Taxonomy

- **When:** After formulating the hypothesis.
- **Purpose:** Classify the attack using industry-standard frameworks (MITRE ATT&CK, STRIDE, OWASP). Connects your analysis to industry language.
- **Output:** Multi-framework classification table.
- **Why it matters:** Allows other researchers and professionals to understand your work without reading the full report.

### Phase 5 — Risk Analysis

- **When:** After taxonomy.
- **Purpose:** Evaluate probability and impact per vector using CVSS 4.0 scoring.
- **Output:** CVSS 4.0 vector string + numeric score + qualitative label.
- **Common mistake:** Classifying everything as "critical." The risk matrix loses value without differentiation.

**CVSS 4.0 Metrics:**
- Attack Vector (AV): Network / Adjacent / Local / Physical
- Attack Complexity (AC): Low / High
- Attack Requirements (AT): None / Present
- Privileges Required (PR): None / Low / High
- User Interaction (UI): None / Passive / Active
- VC/VI/VA: Confidentiality / Integrity / Availability impact on Vulnerable System
- SC/SI/SA: Confidentiality / Integrity / Availability impact on Subsequent System

### Phase 6 — Recommendations

- **When:** After risk analysis.
- **Purpose:** Produce actionable value for each affected stakeholder.
- **Output:** Stakeholder-targeted recommendation matrix.
- **Common mistake:** Generic recommendations ("improve security"). Each recommendation must be specific, technical, and directed at the right actor.

### Phase 7 — Legal Framework

- **When:** In parallel with others, but document at the end.
- **Purpose:** Map the analysis to applicable legislation and document responsible disclosure.
- **Output:** Legal articles referenced + disclosure timeline.
- **Why it matters:** Without legal grounding, the report may be questioned or ignored by authorities.

### Phase 8 — Final Report

- **When:** After completing all previous phases.
- **Purpose:** Consolidate everything into a structured deliverable for authorities, institutions, or publication.
- **Output:** Executive summary + technical body + appendices.
- **Key:** The report must be readable independently. The executive summary is the most important part.

---

## Ethical Principles

1. **Leaked data = always out of scope** — Accessing, downloading, or reproducing illegally obtained data contaminates the entire research and exposes the researcher to legal liability.
2. **Hypothesis ≠ confirmed fact** — A well-supported hypothesis has technical value even without confirmation. Presenting it as confirmed fact destroys it.
3. **Responsible disclosure is part of the process** — Reporting findings to competent authorities is not optional in ethical research.
4. **Acknowledging limitations strengthens the analysis** — A researcher who identifies the limits of their own hypothesis is more credible than one who hides them.

---

## How to Use the Templates

1. Copy the template for the corresponding phase
2. Complete all fields — mark non-applicable ones as `N/A` with justification
3. Do not skip phases — each one depends on the previous
4. Use the YAML frontmatter to track version, case ID, and status across all templates
5. Maintain bilingual headers (Spanish primary, English secondary)

---

*MTD-HX v2.0 — hoxtxnDev | 2026*
