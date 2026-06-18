---
mtd_hx_version: "2.0"
phase: 04
phase_name: "Attack Taxonomy / Taxonomía del Ataque"
case_id: "CD-2025-001"
author: "hoxtxnDev"
date: "2026-05-03"
status: final
mitre_tactics:
  - "TA0042 — Resource Development"
  - "TA0009 — Collection"
  - "TA0043 — Reconnaissance"
  - "TA0010 — Exfiltration"
owasp_category: "A01:2021 — Broken Access Control"
cvss_version: "4.0"
legal_framework: ["Ley 19.628", "Ley 21.663"]
---

# Fase 4 — Taxonomía del Ataque / Attack Taxonomy

> Clasifica el ataque usando frameworks estándar de la industria (MITRE ATT&CK, STRIDE, OWASP). Esto permite que otros investigadores y profesionales entiendan rápidamente el tipo de amenaza.
> *Classify the attack using industry-standard frameworks (MITRE ATT&CK, STRIDE, OWASP). This allows other researchers and professionals to quickly understand the threat type.*

---

## 4.1 Clasificación por concepto / Concept Classification

| Concepto / Concept | Definición aplicada al caso / Definition Applied |
|---|---|
| Data Enrichment Attack | Uso de datos parcialmente filtrados como entrada para aumentar su valor mediante fuentes públicas adicionales |
| Re-identification Attack | Correlación de datos seudónimos (RUT) con fuentes públicas para reconstruir identidades completas |
| Automated Scraping / Crawling | Consulta programática masiva a APIs públicas para extraer datos a escala |
| Data Correlation / Fusion | Cruce de múltiples datasets (filtrado + público) para consolidar perfiles |

---

## 4.2 Mapeo MITRE ATT&CK / MITRE ATT&CK Mapping

| Táctica / Tactic | ID | Técnica / Technique | ID | Sub-técnica / Sub-technique | ID | Fuente de Datos / Data Source | ID | Componente / Component |
|---|---|---|---|---|---|---|---|---|
| Reconnaissance | TA0043 | Active Scanning | T1595 | Scanning IP Blocks | T1595.001 | Network Traffic Flow | DS0029 | Network Traffic Content |
| Resource Development | TA0042 | Gather Victim Identity Information | T1589 | Email Addresses | T1589.002 | Application Log | DS0015 | User Activity |
| Collection | TA0009 | Data from Information Repositories | T1213 | Public-facing Applications | T1213.003 | Application Log | DS0015 | Web Application Access |
| Exfiltration | TA0010 | Exfiltration Over Web Service | T1567 | Exfiltration to Cloud Storage | T1567.002 | Network Traffic Flow | DS0029 | Outbound Connections |

---

## 4.3 Clasificación STRIDE / STRIDE Classification

| Categoría STRIDE | ¿Aplica? / Applies? | Descripción / Description |
|---|---|---|
| Spoofing | Sí | Suplantación de identidad mediante datos verificados para engañar a terceros |
| Tampering | No | No se modifican datos en las fuentes originales |
| Repudiation | Sí | El actor puede negar razonablemente la correlación de datos públicos |
| Information Disclosure | Sí | Exposición de datos personales consolidados más allá de la filtración original |
| Denial of Service | No | No es un objetivo del ataque descrito |
| Elevation of Privilege | No | No se escalan privilegios en sistemas |

---

## 4.4 OWASP Clasificación / OWASP Classification

| Categoría OWASP | ¿Aplica? / Applies? | Descripción / Description |
|---|---|---|
| A01:2021 — Broken Access Control | Sí | APIs públicas de consulta de RUT sin control de acceso adecuado para consultas masivas |
| A08:2021 — Software and Data Integrity Failures | Sí | Los datos filtrados se usan sin verificación de integridad en el proceso de enriquecimiento |

---

## 4.5 Tipo de ataque STRIDE extendido / Extended STRIDE Attack Types

| Categoría / Category | ¿Aplica? / Applies? | Descripción / Description |
|---|---|---|
| Ransomware | No | Sin evidencia de ransomware en este vector |
| Data Brokerage / Enrichment | Sí | El objetivo del ataque es enriquecer datos para reventa o explotación |
| Man-in-the-Middle | No | No aplica — todas las consultas son directas a APIs públicas |
| Ataques a la Cadena de Suministro | Parcial | Los datos enriquecidos podrían usarse en ataques secundarios contra los individuos |

---

*Template MTD-HX v2.0 — Cybersecurity Research Framework by hoxtxnDev*
