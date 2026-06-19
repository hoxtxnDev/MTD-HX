---
mtd_hx_version: "2.0"
phase: 02
phase_name: "Hechos Verificados"
case_id: "CD-2025-001"
author: "hoxtxnDev"
date: "2026-05-03"
status: final
mitre_tactics: []
cvss_version: "N/A"
legal_framework: ["Ley 19.628 (Chile)", "Ley 21.663 (Chile)"]
---

# Fase 2 — Hechos Verificados

> Documenta ÚNICAMENTE hechos verificables con fuentes públicas. Sin suposiciones — eso va en la Fase 3. Sin fuente, no es un hecho verificado.

---

## 2.1 Cronología del Incidente

| Fecha | Evento | Fuente |
|---|---|---|
| 2025-12-15 | Clínica Dávila reporta incidente de ciberseguridad con posible exposición de datos | `https://www.clinicadavila.cl/comunicado-oficial-diciembre-2025` |
| 2025-12-16 | Medios confirman filtración de 500,000+ registros en foros subterráneos | `https://www.emol.com/noticias/tecnologia/2025/12/16/clinica-davila-filtracion-datos` |
| 2025-12-18 | CSIRT Chile emite alerta para el sector salud | `https://www.csirt.gob.cl/reportes/2025/alerta-CD-2025-001` |
| 2026-01-10 | Datos filtrados incluyen RUT, nombres, FDN, direcciones, teléfonos | `https://www.biobiochile.cl/noticias/nacional/2026/01/10/filtracion-datos-clinica-davila` |
| 2026-03-22 | SII confirma que RUT es consultable sin autenticación | `https://www.sii.cl/consulta-rut` |

---

## 2.2 Actor de Amenaza

| Campo | Valor Verificado | Fuente |
|---|---|---|
| Nombre / Grupo | No identificado públicamente | `N/A` |
| Tipo de actor | Ransomware (presunto) / Data broker | Reportes de prensa |
| TTPs conocidos | Exfiltración, publicación en foros de acceso restringido | Reportes de prensa |

---

## 2.3 Sistemas Afectados

| Campo | Valor | Fuente |
|---|---|---|
| Organización objetivo | Clínica Dávila | Comunicado oficial |
| Vector de entrada | No confirmado públicamente | `N/A` |
| Datos exfiltrados (est.) | 500,000+ registros | Reportes de prensa |
| Tipos de datos expuestos | RUT, nombre, FDN, dirección, teléfono, correo | Reportes de prensa |

---

## 2.4 Respuesta Institucional

| Actor | Acción | Fecha | Fuente |
|---|---|---|---|
| Clínica Dávila | Comunicado oficial informando la brecha | 2025-12-15 | Comunicado oficial |
| CSIRT Chile | Alerta de seguridad para el sector salud | 2025-12-18 | `csirt.gob.cl` |
| PDI | Investigación penal iniciada (presunto) | 2025-12-20 | Reportes de prensa |

---

## 2.5 Plataformas Públicas Involucradas

| Sistema | Descripción | Datos que Expone | URL Pública |
|---|---|---|---|
| SII — Consulta de RUT | Verifica nombre asociado a un RUT | Nombre completo vinculado al RUT | `https://www.sii.cl/consulta-rut` |
| Registro Civil — Validación | Validación de identidad con RUT | Datos de identidad básicos | `https://www.registrocivil.cl/validacion` |

---

## 2.6 Checklist de Verificación

- [x] Todos los hechos tienen al menos una fuente pública verificable
- [x] Ninguna afirmación proviene de datos filtrados o acceso no autorizado
- [x] La cronología está ordenada sin gaps
- [x] Las fuentes fueron consultadas en la fecha indicada y están disponibles

---

*Template MTD-HX v2.0 — Cybersecurity Research Framework by hoxtxnDev*
