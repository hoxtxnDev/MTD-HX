---
mtd_hx_version: "2.0"
phase: 06
phase_name: "Recomendaciones"
case_id: "CD-2025-001"
author: "hoxtxnDev"
date: "2026-05-03"
status: final
mitre_tactics:
  - "TA0042 — Desarrollo de Recursos"
  - "TA0009 — Recolección"
cvss_version: "4.0"
legal_framework: ["Ley 19.628 (Chile)", "Ley 21.663 (Chile)", "ISO 27001:2022"]
---

# Fase 6 — Recomendaciones

> Las recomendaciones deben ser específicas, accionables y dirigidas al stakeholder correcto. Evita generalidades.

---

## Matriz de Recomendaciones por Stakeholder

### → CISO / Chief Information Security Officer

| Prioridad | Recomendación | Referencia | Plazo |
|---|---|---|---|
| P1 | Implementar rate limiting y CAPTCHA avanzado en APIs públicas con datos personales | OWASP ASVS v4.0 V3 | 30 días |
| P1 | Monitoreo de scraping anómalo: alertar cuando una IP supere 100 consultas de RUT/hora | DS0015 — Application Log | 15 días |
| P2 | Segmentar APIs de consulta con autenticación multifactor (MFA) | ISO 27001:2022 A.9.4.2 | 60 días |
| P3 | Realizar PIA sobre APIs públicas que exponen PII | Ley 19.628 Art. 23 | 90 días |

### → Equipo de Desarrollo / Engineering

| Prioridad | Recomendación | Referencia | Plazo |
|---|---|---|---|
| P1 | Migrar de consulta directa por RUT a identificadores temporales con expiración | OWASP A01:2021 | 45 días |
| P1 | Implementar WAF con reglas anti-scraping (ModSecurity + OWASP CRS) | NIST SP 800-41 | 30 días |
| P2 | Agregar headers `X-RateLimit-Limit`, `Retry-After` a respuestas API | RFC 6585 | 15 días |
| P3 | Dashboard de monitoreo de consultas anómalas | DS0015 | 60 días |

### → Asesoría Legal / Legal Counsel

| Prioridad | Recomendación | Referencia | Plazo |
|---|---|---|---|
| P1 | Notificar brecha a SERNAC y titulares de datos | Ley 19.628 Art. 23 | 7 días |
| P1 | Reportar incidente a CSIRT Chile (72h desde confirmación) | Ley 21.663 Art. 8 | 72h |
| P2 | Preparar documentación para eventual derivación a PDI | CP Arts. 196-199 | 30 días |
| P3 | Revisar contratos con proveedores de consulta de datos | Ley 19.628 Art. 7 | 90 días |

### → Dirección Ejecutiva / Board

| Prioridad | Recomendación | Referencia | Plazo |
|---|---|---|---|
| P1 | Aprobar presupuesto para mitigaciones técnicas prioritarias | ISO 27001:2022 A.5.1 | 15 días |
| P1 | Establecer canal con CSIRT y coordinar respuesta institucional | Ley 21.663 Art. 8 | 7 días |
| P2 | Audit externo de seguridad sobre APIs públicas con datos personales | ISO 27001:2022 A.9.1 | 60 días |
| P3 | Evaluar seguro cibernético para brechas de datos | — | 90 días |

### → Reforma Estructural

| Prioridad | Recomendación | Referencia | Plazo |
|---|---|---|---|
| P1 | Crear capa de abstracción de identidad digital (evitar RUT como identificador transversal público) | Ley 21.663 | 12 meses |
| P2 | Proponer modificación normativa para exigir autenticación en consultas masivas | Ley 19.628 | 18 meses |

---

## Resumen de Carga por Stakeholder

| Stakeholder | Acciones P1 | Acciones P2 | Acciones P3 | Plazo Máximo |
|---|---|---|---|---|
| CISO | 3 | 1 | 1 | 90 días |
| Desarrollo | 2 | 1 | 1 | 60 días |
| Legal | 2 | 1 | 1 | 90 días |
| Dirección | 2 | 2 | 0 | 90 días |

---

*Template MTD-HX v2.0 — Cybersecurity Research Framework by hoxtxnDev*
