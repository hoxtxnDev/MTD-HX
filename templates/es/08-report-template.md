---
mtd_hx_version: "2.0"
phase: 08
phase_name: "Informe Final"
case_id: "CD-2025-001"
classification: "TLP:CLEAR"
author: "hoxtxnDev"
date: "2026-05-03"
status: final
mitre_tactics:
  - "TA0042 — Desarrollo de Recursos"
  - "TA0009 — Recolección"
  - "TA0043 — Reconocimiento"
  - "TA0010 — Exfiltración"
cvss_version: "4.0"
legal_framework:
  - "Ley 19.628"
  - "Ley 21.663"
  - "Código Penal Chileno"
nist_csf_functions:
  - "IDENTIFICAR"
  - "PROTEGER"
  - "DETECTAR"
  - "RESPONDER"
---

# Análisis de Viabilidad de Ataque de Enriquecimiento de Datos — Clínica Dávila

## Informe de Hipótesis Técnica de Ciberseguridad

| Campo | Valor |
|---|---|
| **Elaborado por** | hoxtxnDev |
| **Institución** | Investigación Independiente |
| **Fecha** | 2026-05-03 |
| **Versión** | 2.0 |
| **Clasificación** | TLP:CLEAR — Público Investigativo |
| **Caso ID** | CD-2025-001 |

---

## 1. Resumen Ejecutivo

> Debe poder leerse de forma independiente. Un CISO con 5 minutos debe entender la amenaza, el riesgo y las acciones requeridas.

### Declaración de Apetición de Riesgo

Este informe asume una **postura de riesgo conservadora**: cualquier vector de ataque factible con CVSS 4.0 superior a 7.0 (ALTO) requiere atención de los stakeholders.

### Panorama de la Situación

El 15 de diciembre de 2025, Clínica Dávila sufrió una brecha de datos que expuso información personal de más de **500,000 pacientes** (RUT, nombres, fechas de nacimiento, direcciones, teléfonos, correos). Este informe analiza la viabilidad técnica de que un actor malicioso haya correlacionado estos datos filtrados con plataformas públicas de consulta de RUT chileno (SII, Registro Civil) para enriquecer y consolidar perfiles personales completos para fraude, robo de identidad o corretaje de datos.

### Hallazgos Clave

| # | Hallazgo | Severidad | Estado |
|---|---|---|---|
| 1 | Enriquecimiento masivo vía scraping de APIs públicas es técnicamente viable | CVSS 4.0: 9.3 (CRÍTICO) | Confirmado |
| 2 | Re-identificación permite consolidación completa de perfiles | CVSS 4.0: 10.0 (CRÍTICO) | Confirmado |
| 3 | RUT como llave pivot transversal crea vulnerabilidad sistémica | Estructural | Endémico |
| 4 | APIs públicas carecen de rate limiting y controles de acceso adecuados | ALTO | Accionable |

### Acciones Prioritarias

1. **CISO (30 días):** Rate limiting + CAPTCHA en APIs públicas con PII
2. **Desarrollo (45 días):** Migrar de consulta directa por RUT a identificadores temporales
3. **Legal (7 días):** Notificar a titulares de datos por Ley 19.628 Art. 23
4. **Dirección (15 días):** Aprobar presupuesto de mitigaciones y canal CSIRT

---

## 2. Línea de Tiempo del Incidente (NIST SP 800-61)

| Fecha | Evento | Categoría | Fuente |
|---|---|---|---|
| 2025-12-15 09:00 | Brecha detectada por TI de Clínica Dávila | Detección | Comunicado interno |
| 2025-12-15 14:00 | Comunicado oficial publicado | Divulgación | `clinicadavila.cl` |
| 2025-12-16 08:00 | Datos confirmados en foros subterráneos | Contención | Reportes de prensa |
| 2025-12-18 10:00 | Alerta CSIRT Chile emitida | Erradicación | `csirt.gob.cl` |
| 2026-01-10 | Alcance de la filtración confirmado | Recuperación | Reportes de prensa |
| 2026-05-03 | Este análisis realizado | Post-mortem | Informe actual |

---

## 3. Hechos Verificados

> Síntesis de la Fase 2. Solo hechos con fuente.

| # | Hecho | Fuente |
|---|---|---|
| 1 | Clínica Dávila reportó incidente de ciberseguridad el 15/12/2025 | Comunicado oficial |
| 2 | 500,000+ registros expuestos en foros subterráneos | Emol, BioBioChile |
| 3 | CSIRT Chile emitió alerta al sector salud el 18/12/2025 | csirt.gob.cl |
| 4 | Datos expuestos: RUT, nombre, FDN, dirección, teléfono, correo | Reportes de prensa |
| 5 | SII permite consulta de RUT sin autenticación | sii.cl (verificado) |
| 6 | Registro Civil permite validación con RUT | registrocivil.cl (verificado) |

---

## 4. Hipótesis Técnica

> Síntesis de la Fase 3. Incluye mapeo MITRE ATT&CK.

### Enunciado

```
Un actor con acceso al dataset filtrado de Clínica Dávila (500,000+ registros)
podría consultar programáticamente plataformas públicas chilenas usando el RUT
como llave pivot para enriquecer cada registro con datos verificados.
```

### Flujo del Ataque

```
[Dataset Filtrado] → Extraer RUTs → Consultar API SII → Consultar API Registro Civil
                                          ↓
                             Correlacionar & Consolidar
                                          ↓
                              Perfiles Personales Enriquecidos
```

---

## 5. Mapa de Calor MITRE ATT&CK

| Táctica | ID | Técnica | ID | Fuente de Datos | ID | Prioridad |
|---|---|---|---|---|---|---|
| Reconocimiento | TA0043 | Escaneo Activo | T1595 | Tráfico de Red | DS0029 | Media |
| Desarrollo de Recursos | TA0042 | Obtener Identidad | T1589 | Log de Aplicación | DS0015 | Alta |
| Recolección | TA0009 | Datos de Repositorios | T1213 | Log de Aplicación | DS0015 | Crítica |
| Exfiltración | TA0010 | Exfiltración vía Web | T1567 | Tráfico de Red | DS0029 | Alta |

---

## 6. Puntuación CVSS 4.0

### Vector Principal: Enriquecimiento Masivo

| Métrica | Valor |
|---|---|
| Vector | `CVSS:4.0/AV:N/AC:L/AT:N/PR:N/UI:N/VC:H/VI:L/VA:N/SC:H/SI:N/SA:N` |
| **Puntaje Base** | **9.3 (CRÍTICO)** |

### Vector Secundario: Re-identificación

| Métrica | Valor |
|---|---|
| Vector | `CVSS:4.0/AV:N/AC:L/AT:N/PR:N/UI:N/VC:H/VI:H/VA:N/SC:H/SI:N/SA:N` |
| **Puntaje Base** | **10.0 (CRÍTICO)** |

---

## 7. Registro de Riesgos (ISO 27005)

| ID | Riesgo | Probabilidad | Impacto | CVSS 4.0 | Dueño | Tratamiento |
|---|---|---|---|---|---|---|
| R-001 | Enriquecimiento masivo vía scraping APIs públicas | Alta | Alto | 9.3 | CISO | Mitigar |
| R-002 | Re-identificación por correlación cruzada | Alta | Alto | 10.0 | CISO | Mitigar |
| R-003 | Venta de datos enriquecidos en mercados | Media | Alto | 8.5 | Legal | Aceptar |
| R-004 | Ataques secundarios contra individuos | Baja | Crítico | 9.0 | Direc. | Mitigar |

---

## 8. Mapeo NIST CSF

| Función | Categoría | Control | Estado Actual | Estado Objetivo |
|---|---|---|---|---|
| **IDENTIFICAR** | Gestión de Activos | Inventario de PII vía APIs | Parcial | Completo |
| **PROTEGER** | Control de Acceso | MFA para APIs de datos | Ninguno | Implementado |
| **PROTEGER** | Seguridad de Datos | Rate limiting en APIs PII | Ninguno | Implementado |
| **DETECTAR** | Anomalías | Detección de scraping | Ninguno | Alertas automáticas |
| **RESPONDER** | Comunicaciones | Procedimiento CSIRT | Ad-hoc | Formalizado |
| **RECUPERAR** | Mejoras | Lecciones aprendidas | Parcial | Mandatorio |

---

## 9. Recomendaciones por Stakeholder

| Stakeholder | Acción Prioritaria | Plazo |
|---|---|---|
| CISO | Rate limiting + CAPTCHA en APIs públicas con PII | 30 días |
| Desarrollo | Migrar de RUT a identificadores temporales | 45 días |
| Legal | Notificar brecha a SERNAC + titulares Art. 23 | 7 días |
| Dirección | Aprobar presupuesto de mitigaciones | 15 días |

---

## 10. Marco Legal

| Ley | Artículo | Obligación |
|---|---|---|
| Ley 19.628 | Art. 23 | Notificar brecha a titulares |
| Ley 21.663 | Art. 8 | Reportar a CSIRT en 72h |
| Código Penal | Arts. 196-197 | Delitos informáticos aplicables |

**Divulgación Realizada:**
- CSIRT Nacional — Enviado 2026-05-03
- PDI — BRICET — Enviado 2026-05-03

---

## Apéndices

### Anexo A: Fuentes Consultadas

| Fuente | URL | Fecha de Consulta |
|---|---|---|
| Clínica Dávila — Comunicado oficial | `https://www.clinicadavila.cl/comunicado-oficial-diciembre-2025` | 2026-05-03 |
| SII — Consulta de RUT | `https://www.sii.cl/consulta-rut` | 2026-05-03 |
| CSIRT Chile | `https://www.csirt.gob.cl/reportes/2025/alerta-CD-2025-001` | 2026-05-03 |

### Anexo B: Acrónimos

| Acrónimo | Significado |
|---|---|
| RUT | Rol Único Tributario |
| SII | Servicio de Impuestos Internos |
| PDI | Policía de Investigaciones |
| CSIRT | Computer Security Incident Response Team |
| CVSS | Common Vulnerability Scoring System |
| NIST CSF | National Institute of Standards and Technology — CSF |

### Anexo C: Metodología

Este informe fue elaborado siguiendo la metodología **MTD-HX v2.0** (Methodology for Threat Documentation — Hypothesis). Las 8 fases del framework fueron completadas secuencialmente. Framework disponible en `https://github.com/hoxtxnDev/MTD-HX`.

### Anexo D: Clasificación TLP

Este informe está clasificado como **TLP:CLEAR** — sin restricciones de distribución.

---

## Declaración de Integridad

Este informe fue elaborado con fines exclusivamente académicos e investigativos. No se accedió, descargó ni reprodujo ningún dato de filtraciones. Todo el análisis se basa en fuentes públicamente disponibles.

**Firma:** `hoxtxnDev`
**Fecha:** `2026-05-03`

---

*Template MTD-HX v2.0 — Cybersecurity Research Framework by hoxtxnDev*
