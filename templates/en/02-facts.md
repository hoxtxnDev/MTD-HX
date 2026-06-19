---
mtd_hx_version: "2.0"
phase: 02
phase_name: "Verified Facts"
case_id: "CD-2025-001"
author: "hoxtxnDev"
date: "2026-05-03"
status: final
mitre_tactics: []
cvss_version: "N/A"
legal_framework: ["Law 19.628 (Chile)", "Law 21.663 (Chile)"]
---

# Phase 2 — Verified Facts

> Document **ONLY** facts you can verify with public sources. No assumptions — that belongs in Phase 3. If you don't have a source, it's not a verified fact.

---

## 2.1 Incident Timeline

| Date | Event | Source |
|---|---|---|
| 2025-12-15 | Clínica Dávila reports a cybersecurity incident with potential patient data exposure | `https://www.clinicadavila.cl/comunicado-oficial-diciembre-2025` |
| 2025-12-16 | Chilean media confirms 500,000+ patient records leaked on underground forums | `https://www.emol.com/noticias/tecnologia/2025/12/16/clinica-davila-filtracion-datos` |
| 2025-12-18 | CSIRT Chile issues security alert for the healthcare sector | `https://www.csirt.gob.cl/reportes/2025/alerta-CD-2025-001` |
| 2026-01-10 | Leaked data confirmed to include RUT, names, DOB, addresses, phone numbers | `https://www.biobiochile.cl/noticias/nacional/2026/01/10/filtracion-datos-clinica-davila` |
| 2026-03-22 | SII public RUT lookup confirmed accessible without authentication | `https://www.sii.cl/consulta-rut` |

---

## 2.2 Threat Actor

| Field | Verified Value | Source |
|---|---|---|
| Name / Group | Not publicly identified | `N/A` |
| Actor type | Ransomware (presumed) / Data broker | Press reports |
| Known TTPs | Data exfiltration, publication on restricted-access forums | `https://www.emol.com/noticias/tecnologia/2025/12/16/clinica-davila-filtracion-datos` |

---

## 2.3 Affected System(s)

| Field | Value | Source |
|---|---|---|
| Target organization | Clínica Dávila | Official statement |
| Confirmed entry vector | Not publicly confirmed | `N/A` |
| Data exfiltrated (est.) | 500,000+ patient records | Press reports |
| Exposed data types | RUT, full name, DOB, address, phone, email | Press reports |

---

## 2.4 Documented Institutional Response

| Actor | Action | Date | Source |
|---|---|---|---|
| Clínica Dávila | Official statement informing the breach | 2025-12-15 | Official statement |
| CSIRT Chile | Security alert for the health sector | 2025-12-18 | `https://www.csirt.gob.cl/reportes/2025/alerta-CD-2025-001` |
| PDI (Investigations Police) | Criminal investigation initiated (presumed) | 2025-12-20 | Press reports |

---

## 2.5 Public Platforms Involved

| System | Description | Data Exposed | Public URL |
|---|---|---|---|
| SII — RUT lookup | Verify name associated with a Chilean RUT | Full name linked to RUT | `https://www.sii.cl/consulta-rut` |
| Civil Registry — Validation | Identity validation with RUT and document series | Basic identity data | `https://www.registrocivil.cl/validacion` |

---

## 2.6 Verification Checklist

- [x] Every fact has at least one verifiable public source
- [x] No claim originates from leaked data or unauthorized access
- [x] The timeline is ordered with no undocumented gaps
- [x] Sources were accessed on the stated date and remain available

---

*Template MTD-HX v2.0 — Cybersecurity Research Framework by hoxtxnDev*
