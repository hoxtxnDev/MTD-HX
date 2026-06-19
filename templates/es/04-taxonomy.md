---
mtd_hx_version: "2.0"
phase: 04
phase_name: "Taxonomía del Ataque"
case_id: "CD-2025-001"
author: "hoxtxnDev"
date: "2026-05-03"
status: final
mitre_tactics:
  - "TA0042 — Desarrollo de Recursos"
  - "TA0009 — Recolección"
  - "TA0043 — Reconocimiento"
  - "TA0010 — Exfiltración"
owasp_category: "A01:2021 — Broken Access Control"
cvss_version: "4.0"
legal_framework: ["Ley 19.628 (Chile)", "Ley 21.663 (Chile)"]
---

# Fase 4 — Taxonomía del Ataque

> Clasifica el ataque usando frameworks estándar (MITRE ATT&CK, STRIDE, OWASP). Permite que otros investigadores entiendan rápidamente el tipo de amenaza.

---

## 4.1 Clasificación por Concepto

| Concepto | Definición Aplicada |
|---|---|
| Ataque de Enriquecimiento de Datos | Uso de datos parcialmente filtrados para aumentar su valor mediante fuentes públicas |
| Ataque de Re-identificación | Correlación de datos seudónimos (RUT) con fuentes públicas para reconstruir identidades |
| Scraping Automatizado | Consulta programática masiva a APIs públicas |
| Correlación / Fusión de Datos | Cruce de múltiples datasets para consolidar perfiles |

---

## 4.2 Mapeo MITRE ATT&CK

| Táctica | ID | Técnica | ID | Sub-técnica | ID | Fuente de Datos | ID | Componente |
|---|---|---|---|---|---|---|---|---|
| Reconocimiento | TA0043 | Escaneo Activo | T1595 | Escaneo de IPs | T1595.001 | Flujo de Tráfico | DS0029 | Contenido de Red |
| Desarrollo de Recursos | TA0042 | Obtener Información de Identidad | T1589 | Correos Electrónicos | T1589.002 | Log de Aplicación | DS0015 | Actividad de Usuario |
| Recolección | TA0009 | Datos de Repositorios | T1213 | Apps Públicas | T1213.003 | Log de Aplicación | DS0015 | Acceso Web |
| Exfiltración | TA0010 | Exfiltración vía Web | T1567 | Almacenamiento Cloud | T1567.002 | Flujo de Tráfico | DS0029 | Conexiones Salientes |

---

## 4.3 Clasificación STRIDE

| Categoría | ¿Aplica? | Descripción |
|---|---|---|
| Spoofing (Suplantación) | Sí | Suplantación con datos verificados para engañar a terceros |
| Tampering (Alteración) | No | No se modifican datos en fuentes originales |
| Repudiation (Repudio) | Sí | El actor puede negar razonablemente la correlación |
| Information Disclosure | Sí | Exposición de datos más allá de la filtración original |
| Denial of Service | No | No es objetivo del ataque |
| Elevation of Privilege | No | No se escalan privilegios |

---

## 4.4 Clasificación OWASP

| Categoría | ¿Aplica? | Descripción |
|---|---|---|
| A01:2021 — Broken Access Control | Sí | APIs públicas sin control de acceso para consultas masivas |
| A08:2021 — Data Integrity Failures | Sí | Datos filtrados usados sin verificación de integridad |

---

## 4.5 Tipos de Ataque Extendidos

| Categoría | ¿Aplica? | Descripción |
|---|---|---|
| Ransomware | No | Sin evidencia en este vector |
| Data Brokerage / Enriquecimiento | Sí | Objetivo: enriquecer datos para reventa o explotación |
| Man-in-the-Middle | No | Consultas directas a APIs públicas |
| Cadena de Suministro | Parcial | Datos enriquecidos podrían usarse en ataques secundarios |

---

*Template MTD-HX v2.0 — Cybersecurity Research Framework by hoxtxnDev*
