# MTD-HX v2.0 — Metodología de Investigación en Ciberseguridad

## Guía completa de uso del framework

---

## ¿Por qué un framework estructurado?

La investigación en ciberseguridad sin metodología produce dos tipos de problemas:

1. **Técnicamente débil** — Hipótesis sin supuestos explícitos, sin análisis de viabilidad, sin reconocimiento de limitaciones. Fácilmente descartable.
2. **Éticamente comprometida** — Sin declaración de alcance y límites claros, cualquier análisis puede ser cuestionado como facilitador de daño.

Este framework resuelve ambos problemas obligando al investigador a documentar cada decisión antes de tomarla.

---

## Integración con Estándares de la Industria

MTD-HX v2.0 se alinea con:

| Estándar | Cómo Integra MTD-HX |
|---|---|
| **MITRE ATT&CK v15** | Tácticas (TAXXXX), Técnicas (TXXXX), Sub-técnicas (TXXXX.XXX) y Fuentes de Datos de Detección (DSXXXX) mapeadas en Fases 3 y 4 |
| **CVSS 4.0** | Desglose completo de Puntaje Base (AV/AC/AT/PR/UI/VC/VI/VA/SC/SI/SA) con etiquetas cuantitativas + cualitativas en Fase 5 |
| **OWASP Testing Guide v5** | Taxonomía de ataques con referencias cruzadas en Fase 4 |
| **ISO 27001:2022** | Mapeo de controles para recomendaciones en Fase 6 |
| **NIST SP 800-61 Rev 2** | Alineación del ciclo de vida de respuesta a incidentes a través de Fase 2 (hechos) y Fase 7 (reporte legal) |

---

## Las 8 Fases — Guía de Uso

### Fase 1 — Definición de Alcance

- **Cuándo usarla:** Antes de cualquier otra cosa.
- **Para qué sirve:** Definir qué está dentro y fuera del análisis, y comprometerse éticamente con esos límites.
- **Producto:** Documento de alcance firmado con ID de caso, objetivos y fuentes autorizadas.
- **Error común:** Empezar desde la hipótesis y definir el alcance después. Esto contamina el análisis con confirmation bias.

### Fase 2 — Hechos Verificados

- **Cuándo usarla:** Antes de formular hipótesis.
- **Para qué sirve:** Construir la base factual del análisis usando solo fuentes públicas verificables.
- **Producto:** Tabla de hechos cronológica con URLs de fuente para cada afirmación.
- **Error común:** Mezclar hechos con inferencias. Si no tienes fuente, no es un hecho.

### Fase 3 — Hipótesis Técnica

- **Cuándo usarla:** Después de documentar los hechos.
- **Para qué sirve:** Formular el modelo de ataque con supuestos explícitos y limitaciones reconocidas. Ahora incluye mapeo a técnica MITRE ATT&CK.
- **Producto:** Enunciado de hipótesis + flujo de ataque + referencia MITRE.
- **Error común:** Presentar la hipótesis como hecho confirmado. Usa siempre lenguaje condicional.

**Integración MITRE ATT&CK:**
- Mapea cada paso del ataque a un ID de técnica específico (ej., T1566.001 — Spearphishing Attachment)
- Identifica la táctica (ej., TA0001 — Initial Access)
- Documenta la fuente de datos de detección (ej., DS0015 — Application Log)
- Referencia el componente de la fuente de datos (ej., `Application Log: Network Traffic`)

### Fase 4 — Taxonomía

- **Cuándo usarla:** Después de formular la hipótesis.
- **Para qué sirve:** Clasificar el ataque usando frameworks estándar de la industria (MITRE ATT&CK, STRIDE, OWASP). Conecta tu análisis con el lenguaje de la industria.
- **Producto:** Tabla de clasificación multi-framework.
- **Por qué importa:** Permite que otros investigadores y profesionales entiendan tu trabajo sin necesidad de leer todo el informe.

### Fase 5 — Análisis de Riesgo

- **Cuándo usarla:** Después de taxonomía.
- **Para qué sirve:** Evaluar probabilidad e impacto por vector usando puntuación CVSS 4.0.
- **Producto:** Vector CVSS 4.0 + puntaje numérico + etiqueta cualitativa.
- **Error común:** Clasificar todo como "crítico". La matriz de riesgo pierde valor si no hay diferenciación.

**Métricas CVSS 4.0:**
- Attack Vector (AV): Network / Adjacent / Local / Physical
- Attack Complexity (AC): Low / High
- Attack Requirements (AT): None / Present
- Privileges Required (PR): None / Low / High
- User Interaction (UI): None / Passive / Active
- VC/VI/VA: Impacto en Confidencialidad / Integridad / Disponibilidad del Sistema Vulnerable
- SC/SI/SA: Impacto en Confidencialidad / Integridad / Disponibilidad del Sistema Subsecuente

### Fase 6 — Recomendaciones

- **Cuándo usarla:** Después de análisis de riesgo.
- **Para qué sirve:** Producir valor accionable para cada stakeholder afectado.
- **Producto:** Matriz de recomendaciones por stakeholder.
- **Error común:** Recomendaciones genéricas ("mejorar la seguridad"). Cada recomendación debe ser específica, técnica y dirigida al actor correcto.

### Fase 7 — Marco Legal

- **Cuándo usarla:** En paralelo con las demás, pero documentar al final.
- **Para qué sirve:** Mapear el análisis a la legislación aplicable y documentar la divulgación responsable.
- **Producto:** Artículos legales referenciados + timeline de divulgación.
- **Por qué importa:** Sin fundamentación legal, el informe puede ser cuestionado o ignorado por autoridades.

### Fase 8 — Informe Final

- **Cuándo usarla:** Al completar las fases anteriores.
- **Para qué sirve:** Consolidar todo en un entregable estructurado para autoridades, instituciones o publicación.
- **Producto:** Resumen ejecutivo + cuerpo técnico + anexos.
- **Clave:** El informe debe poder leerse de forma independiente. El resumen ejecutivo es lo más importante.

---

## Principios Éticos del Framework

1. **Datos filtrados = fuera de alcance siempre** — El acceso, descarga o reproducción de datos obtenidos ilegalmente contamina toda la investigación y expone al investigador a responsabilidad legal.
2. **Hipótesis ≠ hecho confirmado** — Una hipótesis bien fundamentada tiene valor técnico incluso sin confirmación. Presentarla como hecho confirmado la destruye.
3. **Divulgación responsable es parte del proceso** — Reportar hallazgos a autoridades competentes no es opcional en una investigación ética.
4. **Reconocer limitaciones fortalece el análisis** — Un investigador que identifica los límites de su propia hipótesis es más creíble que uno que los oculta.

---

## Cómo Usar las Plantillas

1. Copia la plantilla de la fase correspondiente
2. Completa todos los campos — marca los no aplicables como `N/A` con justificación
3. No saltes fases — cada una depende de la anterior
4. Usa el frontmatter YAML para rastrear versión, ID de caso y estado en todas las plantillas
5. Mantén encabezados bilingües (español primario, inglés secundario)

---

*MTD-HX v2.0 — hoxtxnDev | 2026*
