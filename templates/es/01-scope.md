---
mtd_hx_version: "2.0"
phase: 01
phase_name: "Definición de Alcance"
case_id: "CD-2025-001"
author: "hoxtxnDev"
date: "2026-05-03"
status: final
mitre_tactics: []
cvss_version: "N/A"
legal_framework: ["Ley 19.628 (Chile)", "Ley 21.663 (Chile)"]
---

# Fase 1 — Definición de Alcance

> Completa esta plantilla **antes** de iniciar cualquier investigación. Define con precisión qué está dentro y fuera del análisis. Un alcance mal definido invalida el resto del trabajo.

---

## 1.1 Identificación del Caso

| Campo | Valor |
|---|---|
| Nombre del caso | Análisis de Enriquecimiento de Datos — Clínica Dávila |
| Fecha de inicio | 2026-05-03 |
| Investigador | hoxtxnDev |
| Institución | Investigación Independiente |
| Folio | CD-2025-001 |

---

## 1.2 Objetivo de la Investigación

> ¿Qué pregunta técnica intenta responder esta investigación?

```
Determinar si es técnicamente viable que un actor malicioso haya correlacionado
los datos filtrados de Clínica Dávila (diciembre 2025) con plataformas públicas
de consulta de RUT chileno (SII, Registro Civil) usando el RUT como llave de
enlace para enriquecer cada registro con datos de identidad verificados y
consolidar perfiles individuales completos.
```

---

## 1.3 Límites del Análisis

### En Alcance
- Notificaciones públicas de la brecha y reportes de prensa verificables
- Plataformas públicas de consulta de RUT (SII, Registro Civil, sitios .gob.cl)
- Análisis de viabilidad técnica de ataques de enriquecimiento/re-identificación
- Ecosistema de datos abiertos en Chile
- Mapeo legal aplicable (Ley 19.628, Ley 21.663)

### Fuera de Alcance
- Acceso, descarga o reproducción del dataset filtrado real de Clínica Dávila
- Verificación activa de vulnerabilidades en sistemas en producción
- Publicación de datos personales de individuos específicos
- Identificación o exposición de víctimas concretas
- Pruebas de penetración contra cualquier plataforma pública

---

## 1.4 Declaración Ética

> Sección obligatoria. Debe firmarse antes de continuar.

- [x] Esta investigación tiene fines exclusivamente académicos e investigativos
- [x] No se accederá, descargará ni reproducirá información proveniente de filtraciones
- [x] Toda fuente utilizada es de acceso público y legal
- [x] Los hallazgos serán reportados a las autoridades competentes si corresponde
- [x] Se cumplirá con la legislación aplicable en privacidad y ciberseguridad

**Firma:** `hoxtxnDev`
**Fecha:** `2026-05-03`

---

## 1.5 Fuentes Autorizadas

| Fuente | Tipo | URL / Referencia |
|---|---|---|
| Clínica Dávila — Comunicado oficial | Comunicado de prensa | `https://www.clinicadavila.cl/comunicado-oficial-diciembre-2025` |
| SII — Consulta de RUT | Plataforma pública | `https://www.sii.cl/consulta-rut` |
| Registro Civil — Validación | Plataforma pública | `https://www.registrocivil.cl/validacion` |
| CSIRT Chile — Reportes | Informes oficiales | `https://www.csirt.gob.cl/reportes/2025` |
| Ley 19.628 — Protección de Datos | Legislación | `https://www.bcn.cl/leychile/navegar?idNorma=241331` |
| Ley 21.663 — Ciberseguridad | Legislación | `https://www.bcn.cl/leychile/navegar?idNorma=1182861` |

---

## 1.6 Marco Legal Aplicable

| Ley / Norma | Relevancia |
|---|---|
| Ley 19.628 — Protección de Datos Personales | Regula el tratamiento de datos; Art. 23 exige notificación de brechas |
| Ley 21.663 — Marco de Ciberseguridad | Obligaciones para servicios esenciales; Art. 8 exige reporte a CSIRT en 72h |
| ISO 27001:2022 — A.5.24 | Gestión de incidentes de seguridad |

---

*Template MTD-HX v2.0 — Cybersecurity Research Framework by hoxtxnDev*
