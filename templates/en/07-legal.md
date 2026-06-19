---
mtd_hx_version: "2.0"
phase: 07
phase_name: "Legal Framework"
case_id: "CD-2025-001"
author: "hoxtxnDev"
date: "2026-05-03"
status: final
mitre_tactics: []
cvss_version: "N/A"
legal_framework:
  - "Law 19.628 — Personal Data Protection (Chile)"
  - "Law 21.663 — Cybersecurity Framework (Chile)"
  - "Chilean Penal Code"
---

# Phase 7 — Legal Framework

> Map each element of the analysis to the corresponding legislation. This is not legal advice — it is regulatory contextualization. If the case is in another country, replace with local legislation.

---

## 7.1 Chilean Legislation

| Law | Article | Description | Relevance to Case |
|---|---|---|---|
| Law 19.628 | Art. 2(d) | Defines personal data as any information relating to an identified or identifiable person | RUT, name, DOB, address, phone, email are protected personal data |
| Law 19.628 | Art. 4 | Personal data must be collected and processed for lawful purposes | Data collection via scraping without authorization may violate this article |
| Law 19.628 | Art. 7 | Data subject consent must be express, informed, and unequivocal | RUT holders did not consent to correlation of their data with public sources |
| Law 19.628 | Art. 23 | Data controller must notify data subjects of any security breach that puts data at risk | Clínica Dávila must notify each affected patient |
| Law 21.663 | Art. 1 | Establishes the institutional framework for cybersecurity in Chile | Post-breach data correlation qualifies as a cybersecurity incident |
| Law 21.663 | Art. 8 | Essential services must report incidents to CSIRT within 72 hours of detection | Clínica Dávila as an essential health service must meet this deadline |
| Law 21.663 | Art. 14 | CSIRT Nacional receives and coordinates incident response | CSIRT is the official channel for reporting findings |
| Law 21.663 | Art. 23 | Violations may result in fines up to 20,000 UTM (~$1.3M USD) | Failure to notify in time may result in financial penalties |
| Penal Code | Art. 196 | Computer crimes: unauthorized access to systems | If the actor accessed systems without authorization to extract data |
| Penal Code | Art. 197 | Violation of secrecy or privacy of communications | Publishing leaked personal data may constitute this crime |

---

## 7.2 Competent Authorities

| Agency | Role | Recommended Action |
|---|---|---|
| **CSIRT Nacional** | Receives critical incident reports from essential services | Report research findings within 72h |
| **SERNAC** | Consumer protection in data breaches | Notify if affected individuals are Clínica Dávila consumers |
| **PDI — BRICET** | Cybercrime investigation unit | Refer if evidence of criminal offense is identified |

---

## 7.3 Reporting Obligations

| Obligation | Deadline | Recipient | Legal Basis |
|---|---|---|---|
| Notify breach to data subjects | "Without delay" | Affected data subjects | Law 19.628 Art. 23 |
| Report incident to CSIRT | 72 hours from confirmation | CSIRT Nacional | Law 21.663 Art. 8 |
| Notify SERNAC if mass consumer impact | 5 business days | SERNAC | Law 19.628 + Law 21.663 |
| Refer to PDI if criminal evidence | As soon as practicable | PDI — BRICET | Criminal Procedure Code |

---

## 7.4 Responsible Disclosure Log

| Recipient | Channel | Date | Status | Response |
|---|---|---|---|---|
| CSIRT Nacional | Web form csirt.gob.cl | 2026-05-03 | Submitted | Acknowledgment received |
| PDI — BRICET | Certified mail | 2026-05-03 | Pending | No response to date |

---

*Template MTD-HX v2.0 — Cybersecurity Research Framework by hoxtxnDev*
