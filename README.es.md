# 🔍 MTD-HX v1 — Framework de Investigación en Ciberseguridad

> Metodología estructurada para conducir hipótesis de investigación en ciberseguridad de forma ética — desde la identificación de amenazas hasta el reporte formal.

**Autor:** Horacio N.


---

## Sobre el nombre

**MTD-HX** significa **Methodology for Threat Documentation — Hypothesis** (Metodología de Documentación de Amenazas — Hipótesis). Es un framework estructurado, con enfoque ético prioritario, para producir informes de investigación en ciberseguridad técnicamente rigurosos basados exclusivamente en fuentes públicas.

---

## ¿Qué es esto?

Este repositorio contiene un **framework reutilizable** para estructurar investigaciones y hipótesis técnicas en ciberseguridad, en un contexto académico e investigativo. No es un toolkit de hacking — es una **metodología de documentación y análisis** diseñada para producir informes técnicamente rigurosos, legalmente fundamentados y éticamente responsables.

El framework fue desarrollado y validado a través de un caso aplicado real: el análisis de la **filtración de datos de Clínica Dávila (diciembre 2025)** y su posible correlación con plataformas públicas de consulta de RUT en Chile.

---

## Fases del Framework

```
[1. ALCANCE]→ [2. HECHOS]→ [3. HIPÓTESIS]→ [4. TAXONOMÍA]→ [5. RIESGO]→ [6. RECOMENDACIONES]→ [7. LEGAL]→ [8. INFORME]
```

| Fase | Descripción | Template |
|---|---|---|
| 1. Definición de alcance | Objetivos, límites y restricciones éticas | [scope.md](./templates/01-scope.md) |
| 2. Hechos verificados | Solo información públicamente verificable | [facts.md](./templates/02-facts.md) |
| 3. Hipótesis técnica | Vector de ataque o modelo de amenaza | [hypothesis.md](./templates/03-hypothesis.md) |
| 4. Taxonomía del ataque | Clasificación usando frameworks estándar | [taxonomy.md](./templates/04-taxonomy.md) |
| 5. Análisis de riesgo | Probabilidad, impacto y nivel por vector | [risk.md](./templates/05-risk.md) |
| 6. Recomendaciones | Mitigaciones accionables por stakeholder | [recommendations.md](./templates/06-recommendations.md) |
| 7. Marco legal | Leyes y obligaciones regulatorias aplicables | [legal.md](./templates/07-legal.md) |
| 8. Informe final | Compilación en entregable estructurado | [report-template.md](./templates/08-report-template.md) |

---

## Principios Fundamentales

- ✅ **Ética primero** — Ningún dato de filtración fue accedido, descargado ni reproducido
- ✅ **Transparencia de fuentes** — Solo se documentan hechos públicamente verificables
- ✅ **Fundamentación legal** — Cada análisis se mapea a la legislación aplicable
- ✅ **Reproducibilidad** — Los templates permiten seguir el mismo proceso
- ✅ **Divulgación responsable** — Hallazgos reportados a autoridades competentes

---

## Aviso Legal

Este framework y todos los casos asociados son producidos con **fines exclusivamente académicos e investigativos**. No se accedió, descargó ni reprodujo ningún dato de filtraciones. Todo el análisis se basa en información públicamente disponible.

Legislación chilena aplicable: Ley 19.628 (Protección de Datos), Ley 21.663 (Marco de Ciberseguridad).
