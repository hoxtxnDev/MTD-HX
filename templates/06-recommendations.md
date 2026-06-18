---
mtd_hx_version: "2.0"
phase: 06
phase_name: "Recommendations / Recomendaciones"
case_id: "CD-2025-001"
author: "hoxtxnDev"
date: "2026-05-03"
status: final
mitre_tactics:
  - "TA0042 — Resource Development"
  - "TA0009 — Collection"
cvss_version: "4.0"
legal_framework: ["Ley 19.628", "Ley 21.663", "ISO 27001:2022"]
---

# Fase 6 — Recomendaciones / Recommendations

> Las recomendaciones deben ser específicas, accionables y dirigidas al stakeholder correcto. Evita generalidades. Una buena recomendación dice QUÉ hacer, CÓMO hacerlo y POR QUÉ reduce el riesgo identificado.
> *Recommendations must be specific, actionable, and directed at the right stakeholder. Avoid generalities. A good recommendation says WHAT to do, HOW to do it, and WHY it reduces the identified risk.*

---

## Matriz de recomendaciones por stakeholder / Stakeholder Recommendation Matrix

### → CISO / Chief Information Security Officer

| Prioridad | Recomendación / Recommendation | Referencia / Reference | Plazo / Timeline |
|---|---|---|---|
| P1 | Implementar rate limiting y CAPTCHA avanzado en todas las APIs públicas que expongan datos personales (RUT, nombre, etc.) | OWASP ASVS v4.0 V3 — Session Management | 30 días |
| P1 | Establecer monitoreo de scraping anómalo: alertar cuando una misma IP realice +100 consultas de RUT por hora | DS0015 — Application Log: Network Traffic | 15 días |
| P2 | Segmentar las APIs de consulta de datos personales detrás de autenticación multifactor (MFA) | ISO 27001:2022 A.9.4.2 | 60 días |
| P3 | Realizar un Privacy Impact Assessment (PIA) sobre todas las APIs públicas que exponen PII | Ley 19.628 Art. 23 | 90 días |

### → Developer / Equipo de Desarrollo / Development Team

| Prioridad | Recomendación / Recommendation | Referencia / Reference | Plazo / Timeline |
|---|---|---|---|
| P1 | Migrar de consulta directa por RUT a un identificador temporal con expiración (nonce + hash) | OWASP Top 10 A01:2021 — Broken Access Control | 45 días |
| P1 | Implementar Web Application Firewall (WAF) con reglas anti-scraping (ModSecurity + OWASP CRS) | NIST SP 800-41 Rev 2 | 30 días |
| P2 | Agregar headers `X-RateLimit-Limit`, `X-RateLimit-Remaining`, `Retry-After` a todas las respuestas API | RFC 6585 — Additional HTTP Status Codes | 15 días |
| P3 | Desarrollar dashboard de monitoreo de consultas anómalas con umbrales configurables | DS0015 — Application Log | 60 días |

### → Legal Counsel / Asesoría Legal

| Prioridad | Recomendación / Recommendation | Referencia / Reference | Plazo / Timeline |
|---|---|---|---|
| P1 | Evaluar obligación de notificar la brecha a SERNAC y a cada titular de datos afectado | Ley 19.628 Art. 23 | 7 días |
| P1 | Reportar el incidente a CSIRT Chile dentro del plazo legal de 72 horas desde la confirmación | Ley 21.663 Art. 8 | 72h |
| P2 | Preparar documentación para eventual derivación a PDI si se identifica infracción penal | Código Penal Chileno Arts. 196-199 | 30 días |
| P3 | Revisar contratos con proveedores de plataformas de consulta de datos para asegurar cláusulas de protección de datos | Ley 19.628 Art. 7 | 90 días |

### → Executive / Dirección Ejecutiva / Board

| Prioridad | Recomendación / Recommendation | Referencia / Reference | Plazo / Timeline |
|---|---|---|---|
| P1 | Aprobar presupuesto para implementar las mitigaciones técnicas priorizadas (P1 del CISO + Developer) | ISO 27001:2022 A.5.1 — Information Security Policy | 15 días |
| P1 | Establecer un canal de comunicación con CSIRT Chile y coordinar la respuesta institucional | Ley 21.663 Art. 8 | 7 días |
| P2 | Comisionar un audit externo de seguridad sobre APIs públicas que exponen datos personales | ISO 27001:2022 A.9.1 — Access Control Policy | 60 días |
| P2 | Evaluar la necesidad de un seguro cibernético que cubra brechas de datos y re-identificación | — | 90 días |

### → Reforma estructural / Policy Reform (si aplica)

| Prioridad | Recomendación / Recommendation | Referencia / Reference | Plazo / Timeline |
|---|---|---|---|
| P1 | Evaluar la creación de una capa de abstracción de identidad digital que evite el uso del RUT como identificador transversal público | Ley 21.663 — Marco de Ciberseguridad | 12 meses |
| P2 | Proponer modificación normativa para exigir autenticación en consultas masivas de datos personales en plataformas públicas | Ley 19.628 — Nuevo Artículo | 18 meses |

---

## Resumen de carga por stakeholder / Stakeholder Effort Summary

| Stakeholder | Acciones P1 | Acciones P2 | Acciones P3 | Plazo máximo / Max timeline |
|---|---|---|---|---|
| CISO | 3 | 1 | 1 | 90 días |
| Developer | 2 | 1 | 1 | 60 días |
| Legal Counsel | 2 | 1 | 1 | 90 días |
| Executive / Board | 2 | 2 | 0 | 90 días |

---

*Template MTD-HX v2.0 — Cybersecurity Research Framework by hoxtxnDev*
