---
mtd_hx_version: "2.0"
phase: 05
phase_name: "Risk Analysis / Análisis de Riesgo"
case_id: "CD-2025-001"
author: "hoxtxnDev"
date: "2026-05-03"
status: final
mitre_tactics:
  - "TA0042 — Resource Development"
  - "TA0009 — Collection"
cvss_version: "4.0"
legal_framework: ["Ley 19.628", "Ley 21.663"]
---

# Fase 5 — Análisis de Riesgo / Risk Analysis

> Evalúa cada vector de ataque derivado de la hipótesis usando CVSS 4.0. Sé conservador — sobreestimar el riesgo es más útil que subestimarlo en un contexto investigativo.
> *Evaluate each attack vector derived from the hypothesis using CVSS 4.0. Be conservative — overestimating risk is more useful than underestimating in an investigative context.*

---

## 5.1 Problema estructural identificado / Structural Problem Identified

```
El uso del RUT (Rol Único Tributario) como identificador transversal en
múltiples dominios públicos y privados en Chile crea un escenario donde
un solo dato (RUT) expuesto en una brecha puede usarse como llave maestra
para acceder a información personal adicional a través de APIs públicas
sin control de acceso granular.

EN: The use of the RUT (Chilean national ID) as a cross-domain identifier
across multiple public and private domains in Chile creates a scenario
where a single data point (RUT) exposed in a breach can be used as a
master key to access additional personal information through public APIs
without granular access control.
```

---

## 5.2 Matriz de riesgo / Risk Matrix

| Vector de ataque / Attack Vector | Probabilidad / Probability | Impacto / Impact | Nivel / Level |
|---|---|---|---|
| Enriquecimiento masivo de datos vía scraping de APIs públicas | Alta — herramientas disponibles, CAPTCHA evitable | Alto — consolidación de perfiles personales completos | CRÍTICO |
| Re-identificación de individuos mediante datos cruzados | Alta — RUT permite correlación directa | Alto — pérdida de privacidad y riesgo de fraude | CRÍTICO |
| Venta de datos enriquecidos en mercados subterráneos | Media — demanda existente | Alto — monetización del daño | ALTO |

---

## 5.3 CVSS 4.0 — Puntuación Base / Base Score

### Vector 1: Enriquecimiento masivo de datos / Mass Data Enrichment

**Vector CVSS 4.0:**
```
CVSS:4.0/AV:N/AC:L/AT:N/PR:N/UI:N/VC:H/VI:L/VA:N/SC:H/SI:N/SA:N
```

| Métrica / Metric | Valor / Value | Descripción / Description |
|---|---|---|
| **AV** — Attack Vector | **N** (Network) | El ataque se ejecuta remotamente a través de la red |
| **AC** — Attack Complexity | **L** (Low) | No se requieren condiciones especiales para el ataque |
| **AT** — Attack Requirements | **N** (None) | No hay configuraciones específicas que eludir |
| **PR** — Privileges Required | **N** (None) | No se requiere autenticación para consultar las APIs |
| **UI** — User Interaction | **N** (None) | Las víctimas no interactúan con el atacante |
| **VC** — Vuln Confidentiality | **H** (High) | Exposición completa de datos personales correlacionados |
| **VI** — Vuln Integrity | **L** (Low) | Los datos recuperados son factuales pero su correlación genera nuevo valor informacional |
| **VA** — Vuln Availability | **N** (None) | No hay impacto en disponibilidad de sistemas |
| **SC** — Sub Confidentiality | **H** (High) | Los perfiles consolidados pueden exponer datos de terceros |
| **SI** — Sub Integrity | **N** (None) | Sin impacto en integridad de sistemas subsecuentes |
| **SA** — Sub Availability | **N** (None) | Sin impacto en disponibilidad de sistemas subsecuentes |

**Resultado / Result:**
| Campo / Field | Valor / Value |
|---|---|
| **CVSS 4.0 Base Score** | **9.3** |
| **Severidad / Severity** | **CRITICAL** |

---

### Vector 2: Ataque de re-identificación / Re-identification Attack

**Vector CVSS 4.0:**
```
CVSS:4.0/AV:N/AC:L/AT:N/PR:N/UI:N/VC:H/VI:H/VA:N/SC:H/SI:N/SA:N
```

| Métrica / Metric | Valor / Value | Descripción / Description |
|---|---|---|
| AV | N (Network) | Remoto vía red |
| AC | L (Low) | Sin condiciones previas |
| AT | N (None) | Sin requisitos especiales |
| PR | N (None) | Sin autenticación |
| UI | N (None) | Sin interacción del usuario |
| VC | H (High) | Exposición de identidad completa |
| VI | H (High) | Los datos correlacionados son difícilmente refutables |
| VA | N (None) | Sin impacto de disponibilidad |
| SC | H (High) | Riesgo para sistemas que usan estos datos como verificación |
| SI | N (None) | Sin impacto en integridad subsecuente |
| SA | N (None) | Sin impacto en disponibilidad subsecuente |

**Resultado / Result:**
| Campo / Field | Valor / Value |
|---|---|
| **CVSS 4.0 Base Score** | **10.0** |
| **Severidad / Severity** | **CRITICAL** |

---

## 5.4 Población afectada estimada / Estimated Affected Population

| Segmento / Segment | Estimado / Estimate | Base del estimado / Basis |
|---|---|---|
| Pacientes de Clínica Dávila con datos filtrados | 500,000+ | Reportes de prensa verificados |
| Población chilena con RUT consultable en plataformas públicas | 18,000,000+ | Cobertura del sistema de RUT en Chile |
| Individuos en riesgo de re-identificación completa | 500,000+ | Intersección del dataset filtrado con APIs públicas |

---

## 5.5 Criterios de clasificación / Classification Criteria

### Probabilidad / Probability
| Nivel / Level | Criterio / Criterion |
|---|---|
| Alta | El atacante tiene acceso, motivo y capacidad técnica documentada |
| Media | El atacante tiene acceso pero la ejecución requiere recursos adicionales |
| Baja | Requiere capacidades técnicas avanzadas o condiciones poco probables |

### Impacto / Impact
| Nivel / Level | Criterio / Criterion |
|---|---|
| Crítico | Daño irreversible a personas, infraestructura crítica o pérdida masiva de datos sensibles |
| Alto | Daño significativo reversible con esfuerzo considerable |
| Medio | Daño moderado, mitigable con respuesta rápida |
| Bajo | Impacto menor, fácilmente reversible |

---

*Template MTD-HX v2.0 — Cybersecurity Research Framework by hoxtxnDev*
