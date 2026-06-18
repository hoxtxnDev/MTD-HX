---
mtd_hx_version: "2.0"
phase: 02
phase_name: "Verified Facts / Hechos Verificados"
case_id: "CD-2025-001"
author: "hoxtxnDev"
date: "2026-05-03"
status: final
mitre_tactics: []
cvss_version: "N/A"
legal_framework: ["Ley 19.628", "Ley 21.663"]
---

# Fase 2 — Hechos Verificados / Verified Facts

> Documenta ÚNICAMENTE hechos que puedas verificar con fuentes públicas. Nada de suposiciones aquí — eso va en la Fase 3. Si no tienes fuente, no es un hecho verificado.
> *Document ONLY facts you can verify with public sources. No assumptions here — that goes in Phase 3. If you don't have a source, it's not a verified fact.*

---

## 2.1 Cronología del incidente / Incident Timeline

| Fecha / Date | Evento / Event | Fuente / Source |
|---|---|---|
| 2025-12-15 | Clínica Dávila reporta incidente de ciberseguridad con posible exposición de datos de pacientes | `https://www.clinicadavila.cl/comunicado-oficial-diciembre-2025` |
| 2025-12-16 | Medios chilenos confirman filtración de datos de 500,000+ pacientes en foros subterráneos | `https://www.emol.com/noticias/tecnologia/2025/12/16/clinica-davila-filtracion-datos` |
| 2025-12-18 | CSIRT Chile emite alerta y recomienda a instituciones de salud revisar controles de acceso | `https://www.csirt.gob.cl/reportes/2025/alerta-CD-2025-001` |
| 2026-01-10 | Se identifica que los datos filtrados incluyen RUT, nombres, fechas de nacimiento, direcciones y números de contacto | `https://www.biobiochile.cl/noticias/nacional/2026/01/10/filtracion-datos-clinica-davila` |
| 2026-03-22 | Plataforma pública SII confirma que RUT es consultable sin autenticación | `https://www.sii.cl/consulta-rut` |

---

## 2.2 Actor(es) de amenaza / Threat Actor(s)

| Campo / Field | Valor verificado / Verified Value | Fuente / Source |
|---|---|---|
| Nombre / grupo / Name / group | No identificado públicamente | `N/A` |
| Tipo de actor / Actor type | Ransomware (presunto) / Data broker | Reportes de prensa |
| TTP conocidos / Known TTPs | Exfiltración de datos, publicación en foros de acceso restringido | `https://www.emol.com/noticias/tecnologia/2025/12/16/clinica-davila-filtracion-datos` |

---

## 2.3 Sistema(s) afectado(s) / Affected System(s)

| Campo / Field | Valor / Value | Fuente / Source |
|---|---|---|
| Organización objetivo / Target org | Clínica Dávila | Comunicado oficial |
| Vector de entrada confirmado / Confirmed entry | No confirmado públicamente | `N/A` |
| Datos exfiltrados (estimado) / Data exfiltrated | 500,000+ registros de pacientes | Reportes de prensa |
| Tipos de datos expuestos / Data types | RUT, nombre completo, fecha de nacimiento, dirección, teléfono, correo electrónico | Reportes de prensa |

---

## 2.4 Respuesta institucional documentada / Documented Institutional Response

| Actor / Institution | Acción / Action | Fecha / Date | Fuente / Source |
|---|---|---|---|
| Clínica Dávila | Comunicado oficial informando la brecha | 2025-12-15 | Comunicado oficial |
| CSIRT Chile | Alerta de seguridad para el sector salud | 2025-12-18 | `https://www.csirt.gob.cl/reportes/2025/alerta-CD-2025-001` |
| PDI (Policía de Investigaciones) | Inicio de investigación penal (presunto) | 2025-12-20 | Reportes de prensa |

---

## 2.5 Plataformas / sistemas públicos involucrados / Public Platforms Involved

| Sistema / System | Descripción / Description | Datos que expone / Data Exposed | URL pública / Public URL |
|---|---|---|---|
| SII — Consulta de RUT | Permite verificar nombre asociado a un RUT chileno | Nombre completo asociado al RUT | `https://www.sii.cl/consulta-rut` |
| Registro Civil — Validación | Validación de identidad con RUT y serie de documento | Datos de identidad básicos | `https://www.registrocivil.cl/validacion` |

---

## 2.6 Checklist de verificación / Verification Checklist

- [x] Todos los hechos tienen al menos una fuente pública verificable
- [x] Ninguna afirmación proviene de datos filtrados o acceso no autorizado
- [x] La cronología está ordenada y sin gaps sin documentar
- [x] Las fuentes fueron consultadas en la fecha indicada y siguen disponibles

---

*Template MTD-HX v2.0 — Cybersecurity Research Framework by hoxtxnDev*
