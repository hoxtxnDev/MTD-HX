# Fase 3 — Hipótesis Técnica

> **Instrucciones:** Aquí formulas el modelo de ataque hipotético basado en los hechos verificados. Usa lenguaje condicional ("podría", "es técnicamente viable que") y documenta los supuestos de cada paso. El pseudocódigo y diagramas son herramientas analíticas, no instrucciones operativas.

---

## 3.1 Enunciado de la hipótesis

> Una sola frase que describa el ataque hipotético con precisión técnica.

```
HIPÓTESIS: [Actor] pudo haber utilizado [Dataset A] en combinación con [Sistema/Fuente B],
usando [campo X] como llave de enlace, para ejecutar un [tipo de ataque], 
con el resultado de [impacto concreto].
```

---

## 3.2 Supuestos de la hipótesis

> Lista los supuestos que deben ser verdaderos para que la hipótesis sea viable. Sé honesto con las limitaciones.

| # | Supuesto | Probabilidad estimada | Justificación |
|---|---|---|---|
| 1 | `[Supuesto 1]` | `[Alta / Media / Baja]` | `[Por qué]` |
| 2 | `[Supuesto 2]` | `[Alta / Media / Baja]` | `[Por qué]` |
| 3 | `[Supuesto 3]` | `[Alta / Media / Baja]` | `[Por qué]` |

---

## 3.3 Flujo del ataque

> Describe el ataque paso a paso. Usa el formato: Entrada → Proceso → Salida.

```
PASO 1: [Descripción del primer paso]
        Entrada: [Qué tiene el atacante]
        Acción:  [Qué hace]
        Salida:  [Qué obtiene - Beneficios]

PASO 2: [Descripción del segundo paso]
        Entrada: [Output del paso anterior]
        Acción:  [Qué hace]
        Salida:  [Qué obtiene - Beneficios]

PASO N: [...]
        Resultado final: [Impacto concreto]
```

---

## 3.4 Pseudocódigo analítico

> **AVISO: Solo con fines académicos. No representa código ejecutable ni instrucciones operativas.**

```python
# HIPOTÉTICO — Fines exclusivamente analíticos
# [Descripción de lo que modela este pseudocódigo]

db_a = cargar('[fuente_a]')         # [Descripción del dataset]
db_b = obtener('[fuente_publica]')  # [Descripción de la fuente pública]

# [Operación principal — ej: JOIN, correlación, enriquecimiento]
resultado = dataset_a.operacion(dataset_b, on='[campo_comun]')

# Resultado: [descripción del output hipotético]
```

---

## 3.5 Campo pivot / llave de enlace

> Si el ataque depende de un campo de correlación, documenta sus propiedades.

| Propiedad | Valor |
|---|---|
| Campo | `[Nombre del campo]` |
| Presente en dataset A | `[Sí / No / Parcialmente]` |
| Presente en dataset B | `[Sí / No / Parcialmente]` |
| Unicidad | `[Único por persona / reutilizable / etc.]` |
| Carácter público | `[Sí / No]` |
| Revocable | `[Sí / No]` |

---

## 3.6 Perfil resultante (si aplica)

> Qué información tendría el atacante al completar el ataque hipotético.

| Dato obtenido | Fuente original | Sensibilidad |
|---|---|---|
| `[Dato 1]` | `[Dataset A / B / Correlación]` | `[Alta / Media / Baja]` |
| `[Dato 2]` | `[Dataset A / B / Correlación]` | `[Alta / Media / Baja]` |

---

## 3.7 Limitaciones de la hipótesis

> Sé honesto. ¿Qué factores podrían invalidar o reducir la viabilidad de esta hipótesis?

- `[Limitación 1 — ej: rate limiting en la fuente pública]`
- `[Limitación 2 — ej: no hay confirmación pública de que el actor ejecutó este paso]`
- `[Limitación 3]`

---

*Template MTD - HX 1 — Cybersecurity Research Framework by hoxtxnDev*
