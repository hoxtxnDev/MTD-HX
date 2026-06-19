---
mtd_hx_version: "2.0"
phase: 05
phase_name: "Análisis de Riesgo"
case_id: "CD-2025-001"
author: "hoxtxnDev"
date: "2026-05-03"
status: final
mitre_tactics:
  - "TA0042 — Desarrollo de Recursos"
  - "TA0009 — Recolección"
cvss_version: "4.0"
legal_framework: ["Ley 19.628 (Chile)", "Ley 21.663 (Chile)"]
---

# Fase 5 — Análisis de Riesgo

> Evalúa cada vector de ataque usando CVSS 4.0. Sé conservador — sobreestimar el riesgo es más útil que subestimarlo en contexto investigativo.

---

## 5.1 Problema Estructural Identificado

```
El uso del RUT como identificador transversal en múltiples dominios públicos
y privados en Chile crea un escenario donde un solo dato (RUT) expuesto en
una brecha puede usarse como llave maestra para acceder a información personal
adicional a través de APIs públicas sin control de acceso granular.
```

---

## 5.2 Matriz de Riesgo

| Vector de Ataque | Probabilidad | Impacto | Nivel |
|---|---|---|---|
| Enriquecimiento masivo vía scraping de APIs públicas | Alta | Alto | CRÍTICO |
| Re-identificación mediante datos cruzados | Alta | Alto | CRÍTICO |
| Venta de datos enriquecidos en mercados subterráneos | Media | Alto | ALTO |

---

## 5.3 CVSS 4.0 — Puntaje Base

### Vector 1: Enriquecimiento Masivo de Datos

**Vector CVSS 4.0:**
```
CVSS:4.0/AV:N/AC:L/AT:N/PR:N/UI:N/VC:H/VI:L/VA:N/SC:H/SI:N/SA:N
```

| Métrica | Valor | Descripción |
|---|---|---|
| **AV** — Attack Vector | **N** (Network) | Ataque remoto por red |
| **AC** — Attack Complexity | **L** (Low) | Sin condiciones especiales |
| **AT** — Attack Requirements | **N** (None) | Sin configuraciones que eludir |
| **PR** — Privileges Required | **N** (None) | Sin autenticación requerida |
| **UI** — User Interaction | **N** (None) | Sin interacción de la víctima |
| **VC** — Vuln Confidentiality | **H** (High) | Exposición completa de datos correlacionados |
| **VI** — Vuln Integrity | **L** (Low) | Datos factuales pero la correlación genera nuevo valor |
| **VA** — Vuln Availability | **N** (None) | Sin impacto en disponibilidad |
| **SC** — Sub Confidentiality | **H** (High) | Perfiles consolidados exponen datos de terceros |
| **SI** — Sub Integrity | **N** (None) | Sin impacto en integridad subsecuente |
| **SA** — Sub Availability | **N** (None) | Sin impacto en disponibilidad subsecuente |

**Resultado:**
| Campo | Valor |
|---|---|
| **CVSS 4.0 Base Score** | **9.3** |
| **Severidad** | **CRÍTICO** |

---

### Vector 2: Ataque de Re-identificación

**Vector CVSS 4.0:**
```
CVSS:4.0/AV:N/AC:L/AT:N/PR:N/UI:N/VC:H/VI:H/VA:N/SC:H/SI:N/SA:N
```

| Métrica | Valor | Descripción |
|---|---|---|
| AV | N (Network) | Remoto |
| AC | L (Low) | Sin precondiciones |
| AT | N (None) | Sin requisitos |
| PR | N (None) | Sin autenticación |
| UI | N (None) | Sin interacción |
| VC | H (High) | Exposición completa de identidad |
| VI | H (High) | Datos correlacionados difícilmente refutables |
| VA | N (None) | Sin impacto |
| SC | H (High) | Riesgo para sistemas que usan estos datos |
| SI | N (None) | Sin impacto |
| SA | N (None) | Sin impacto |

**Resultado:**
| Campo | Valor |
|---|---|
| **CVSS 4.0 Base Score** | **10.0** |
| **Severidad** | **CRÍTICO** |

---

## 5.4 Población Afectada Estimada

| Segmento | Estimado | Base |
|---|---|---|
| Pacientes de Clínica Dávila con datos filtrados | 500,000+ | Reportes de prensa |
| Población chilena con RUT consultable | 18,000,000+ | Cobertura del sistema |
| Individuos en riesgo de re-identificación | 500,000+ | Intersección dataset + APIs |

---

## 5.5 Criterios de Clasificación

### Probabilidad

| Nivel | Criterio |
|---|---|
| Alta | Atacante tiene acceso, motivo y capacidad documentada |
| Media | Atacante tiene acceso pero requiere recursos adicionales |
| Baja | Requiere capacidades avanzadas o condiciones improbables |

### Impacto

| Nivel | Criterio |
|---|---|
| Crítico | Daño irreversible a personas o infraestructura crítica |
| Alto | Daño significativo, reversible con esfuerzo considerable |
| Medio | Daño moderado, mitigable con respuesta rápida |
| Bajo | Impacto menor, fácilmente reversible |

---

*Template MTD-HX v2.0 — Cybersecurity Research Framework by hoxtxnDev*
