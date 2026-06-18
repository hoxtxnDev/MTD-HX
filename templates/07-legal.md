---
mtd_hx_version: "2.0"
phase: 07
phase_name: "Legal Framework / Marco Legal"
case_id: "CD-2025-001"
author: "hoxtxnDev"
date: "2026-05-03"
status: final
mitre_tactics: []
cvss_version: "N/A"
legal_framework:
  - "Ley 19.628 — Protección de Datos Personales"
  - "Ley 21.663 — Marco de Ciberseguridad"
  - "Código Penal Chileno"
---

# Fase 7 — Marco Legal Aplicable / Applicable Legal Framework

> Mapea cada elemento del análisis a la legislación correspondiente. Esto no es asesoría legal — es contextualización normativa. Si el caso es de otro país, reemplaza con la legislación local.
> *Map each element of the analysis to the corresponding legislation. This is not legal advice — it is regulatory contextualization. If the case is in another country, replace with local legislation.*

---

## 7.1 Legislación chilena / Chilean Legislation

| Norma / Norm | Artículo / Article | Descripción / Description | Relevancia para el caso / Relevance to Case |
|---|---|---|---|
| Ley 19.628 | Art. 2 letra d) | Define dato personal como cualquier información relativa a una persona identificada o identificable | El RUT, nombre, FDN, dirección, teléfono y correo son datos personales protegidos |
| Ley 19.628 | Art. 4 | Los datos personales deben recogerse y tratarse con finalidades lícitas | La recolección de datos vía scraping sin autorización puede violar este artículo |
| Ley 19.628 | Art. 7 | El consentimiento del titular debe ser expreso, informado e inequívoco | Los titulares de RUT no consintieron la correlación de sus datos con fuentes públicas |
| Ley 19.628 | Art. 23 | El responsable del registro debe notificar a los titulares cualquier violación de seguridad que ponga en riesgo los datos | Clínica Dávila debe notificar a cada paciente afectado por la brecha |
| Ley 21.663 | Art. 1 | Establece el marco institucional para la ciberseguridad en Chile | La correlación de datos post-brecha califica como incidente de ciberseguridad |
| Ley 21.663 | Art. 8 | Los servicios esenciales deben reportar incidentes al CSIRT en un plazo máximo de 72 horas desde su detección | Clínica Dávila como servicio de salud esencial debe cumplir este plazo |
| Ley 21.663 | Art. 14 | El CSIRT Nacional recibe y coordina la respuesta a incidentes de ciberseguridad | CSIRT es el canal oficial para reportar análisis y hallazgos |
| Ley 21.663 | Art. 23 | Las infracciones pueden ser sancionadas con multas de hasta 20,000 UTM (~$1.3M USD) | La falta de notificación oportuna puede resultar en sanciones económicas |
| Código Penal | Art. 196 | Delitos informáticos: acceso ilícito a sistemas | Si el actor accedió sin autorización para extraer los datos |
| Código Penal | Art. 197 | Violación de secreto o privacidad de comunicaciones | La publicación de datos personales filtrados puede constituir este delito |

---

## 7.2 Organismos competentes / Competent Authorities

| Organismo / Agency | Rol / Role | Acción recomendada / Recommended Action |
|---|---|---|
| **CSIRT Nacional** | Recepción de reportes de incidentes críticos de servicios esenciales | Reportar hallazgos de la investigación dentro de 72h |
| **SERNAC** | Protección al consumidor en brechas de datos | Notificar si los afectados son consumidores de Clínica Dávila |
| **PDI — BRICET** | Brigada de Cibercrimen — investigación penal | Derivar si se identifica evidencia de delito |

---

## 7.3 Obligaciones de reporte / Reporting Obligations

| Obligación / Obligation | Plazo / Deadline | Destinatario / Recipient | Fundamento Legal / Legal Basis |
|---|---|---|---|
| Notificar brecha a titulares de datos | "Sin dilación" | Titulares de datos afectados | Ley 19.628 Art. 23 |
| Reportar incidente a CSIRT | 72 horas desde confirmación | CSIRT Nacional | Ley 21.663 Art. 8 |
| Notificar a SERNAC si hay consumo masivo afectado | 5 días hábiles | SERNAC | Ley 19.628 + Ley 21.663 |
| Derivar a PDI si hay indicios de delito | A la brevedad | PDI — BRICET | Código Procesal Penal |

---

## 7.4 Registro de divulgación responsable / Responsible Disclosure Log

| Destinatario / Recipient | Canal / Channel | Fecha / Date | Estado / Status | Respuesta / Response |
|---|---|---|---|---|
| CSIRT Nacional | Formulario web csirt.gob.cl | 2026-05-03 | Enviado | Acuse de recibo recibido |
| PDI — BRICET | Correo certificado | 2026-05-03 | Pendiente | Sin respuesta a la fecha |

---

*Template MTD-HX v2.0 — Cybersecurity Research Framework by hoxtxnDev*
