# MTD-HX v1 — Metodología de Investigación en Ciberseguridad
## Guía completa de uso del framework

---

## ¿Por qué un framework estructurado?

La investigación en ciberseguridad sin metodología produce dos tipos de problemas:

1. **Técnicamente débil** — Hipótesis sin supuestos explícitos, sin análisis de viabilidad, sin reconocimiento de limitaciones. Fácilmente descartable.
2. **Éticamente comprometida** — Sin declaración de alcance y límites claros, cualquier análisis puede ser cuestionado como facilitador de daño.

Este framework resuelve ambos problemas obligando al investigador a documentar cada decisión antes de tomarla.

---

## Las 8 Fases — Guía de uso

### Fase 1 — Definición de Alcance
**Cuándo usarla:** Antes de cualquier otra cosa.  
**Para qué sirve:** Definir qué está dentro y fuera del análisis, y comprometerse éticamente con esos límites.  
**Error común:** Empezar desde la hipótesis y definir el alcance después. Esto contamina el análisis con confirmation bias.

### Fase 2 — Hechos Verificados
**Cuándo usarla:** Antes de formular hipótesis.  
**Para qué sirve:** Construir la base factual del análisis usando solo fuentes públicas verificables.  
**Error común:** Mezclar hechos con inferencias. Si no tienes fuente, no es un hecho.

### Fase 3 — Hipótesis Técnica
**Cuándo usarla:** Después de documentar los hechos.  
**Para qué sirve:** Formular el modelo de ataque con sus supuestos explícitos y sus limitaciones reconocidas.  
**Error común:** Presentar la hipótesis como hecho confirmado. Usa siempre lenguaje condicional.

### Fase 4 — Taxonomía
**Cuándo usarla:** Después de formular la hipótesis.  
**Para qué sirve:** Clasificar el ataque usando frameworks estándar (MITRE ATT&CK, STRIDE). Esto conecta tu análisis con el lenguaje de la industria.  
**Por qué importa:** Permite que otros investigadores y profesionales entiendan tu trabajo sin necesidad de leer todo el informe.

### Fase 5 — Análisis de Riesgo
**Cuándo usarla:** Después de taxonomía.  
**Para qué sirve:** Evaluar probabilidad × impacto por vector. Eleva el análisis de lo técnico a lo estratégico.  
**Error común:** Clasificar todo como "crítico". La matriz de riesgo pierde valor si no hay diferenciación.

### Fase 6 — Recomendaciones
**Cuándo usarla:** Después de análisis de riesgo.  
**Para qué sirve:** Producir valor accionable para cada stakeholder afectado.  
**Error común:** Recomendaciones genéricas ("mejorar la seguridad"). Cada recomendación debe ser específica, técnica y dirigida al actor correcto.

### Fase 7 — Marco Legal
**Cuándo usarla:** En paralelo con las demás, pero documentar al final.  
**Para qué sirve:** Mapear el análisis a la legislación aplicable y documentar la divulgación responsable.  
**Por qué importa:** Sin fundamentación legal, el informe puede ser cuestionado o ignorado por autoridades.

### Fase 8 — Informe Final
**Cuándo usarla:** Al completar las fases anteriores.  
**Para qué sirve:** Consolidar todo en un entregable estructurado para autoridades, instituciones o publicación.  
**Clave:** El informe debe poder leerse de forma independiente. El resumen ejecutivo es lo más importante.

---

## Principios éticos del framework

### 1. Datos filtrados = fuera de alcance siempre
El acceso, descarga o reproducción de datos obtenidos ilegalmente contamina toda la investigación y expone al investigador a responsabilidad legal.

### 2. Hipótesis ≠ hecho
Una hipótesis bien fundamentada tiene valor técnico incluso sin confirmación. Presentarla como hecho confirmado la destruye.

### 3. Divulgación responsable es parte del proceso
Reportar hallazgos a autoridades competentes no es opcional en una investigación ética. Documenta quién, cuándo y por qué canal.

### 4. Reconocer limitaciones fortalece el análisis
Un investigador que identifica los límites de su propia hipótesis es más creíble que uno que los oculta.

---

## Cómo usar los templates

1. Copia el template de la fase correspondiente
2. Completa todos los campos — los que no aplican márcalos como `N/A` con justificación
3. No saltes fases — cada una depende de la anterior

---

*MTD-HX v1 — Horacio Navarrete Muñoz | Duoc UC, Concepción | 2026*
