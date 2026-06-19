---
mtd_hx_version: "2.0"
phase: 07
phase_name: "Marco Legal"
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

# Fase 7 — Marco Legal Aplicable

> Mapea cada elemento del análisis a la legislación correspondiente. Esto no es asesoría legal — es contextualización normativa.

---

## 7.1 Legislación Chilena

| Ley | Artículo | Descripción | Relevancia al Caso |
|---|---|---|---|
| Ley 19.628 | Art. 2 letra d) | Define dato personal como información relativa a persona identificada o identificable | RUT, nombre, FDN, dirección son datos personales protegidos |
| Ley 19.628 | Art. 4 | Los datos deben recogerse con finalidades lícitas | Scraping sin autorización puede violar este artículo |
| Ley 19.628 | Art. 7 | Consentimiento expreso, informado e inequívoco del titular | Titulares no consintieron la correlación con fuentes públicas |
| Ley 19.628 | Art. 23 | El responsable debe notificar violaciones de seguridad | Clínica Dávila debe notificar a cada paciente afectado |
| Ley 21.663 | Art. 1 | Marco institucional para la ciberseguridad en Chile | La correlación post-brecha es incidente de ciberseguridad |
| Ley 21.663 | Art. 8 | Servicios esenciales deben reportar a CSIRT en 72h | Clínica Dávila como servicio de salud esencial |
| Ley 21.663 | Art. 14 | CSIRT Nacional recibe y coordina respuesta a incidentes | CSIRT es el canal oficial para reportar hallazgos |
| Ley 21.663 | Art. 23 | Infracciones sancionables con multas hasta 20,000 UTM (~$1.3M USD) | Falta de notificación puede resultar en sanciones |
| Código Penal | Art. 196 | Delitos informáticos: acceso ilícito a sistemas | Si el actor accedió sin autorización |
| Código Penal | Art. 197 | Violación de secreto o privacidad | Publicación de datos filtrados puede constituir delito |

---

## 7.2 Organismos Competentes

| Organismo | Rol | Acción Recomendada |
|---|---|---|
| **CSIRT Nacional** | Recepción de reportes de incidentes críticos | Reportar hallazgos dentro de 72h |
| **SERNAC** | Protección al consumidor en brechas de datos | Notificar si hay consumidores afectados |
| **PDI — BRICET** | Brigada de Cibercrimen | Derivar si hay evidencia de delito |

---

## 7.3 Obligaciones de Reporte

| Obligación | Plazo | Destinatario | Fundamento Legal |
|---|---|---|---|
| Notificar brecha a titulares | "Sin dilación" | Titulares afectados | Ley 19.628 Art. 23 |
| Reportar incidente a CSIRT | 72h desde confirmación | CSIRT Nacional | Ley 21.663 Art. 8 |
| Notificar a SERNAC | 5 días hábiles | SERNAC | Ley 19.628 + Ley 21.663 |
| Derivar a PDI | A la brevedad | PDI — BRICET | Código Procesal Penal |

---

## 7.4 Registro de Divulgación Responsable

| Destinatario | Canal | Fecha | Estado | Respuesta |
|---|---|---|---|---|
| CSIRT Nacional | Formulario web csirt.gob.cl | 2026-05-03 | Enviado | Acuse de recibo |
| PDI — BRICET | Correo certificado | 2026-05-03 | Pendiente | Sin respuesta |

---

*Template MTD-HX v2.0 — Cybersecurity Research Framework by hoxtxnDev*
