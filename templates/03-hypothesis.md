---
mtd_hx_version: "2.0"
phase: 03
phase_name: "Technical Hypothesis / Hipótesis Técnica"
case_id: "CD-2025-001"
author: "hoxtxnDev"
date: "2026-05-03"
status: final
mitre_tactics:
  - "TA0042 — Resource Development"
  - "TA0009 — Collection"
cvss_version: "N/A"
legal_framework: ["Ley 19.628", "Ley 21.663"]
---

# Fase 3 — Hipótesis Técnica / Technical Hypothesis

> Formula el modelo de ataque hipotético basado en los hechos verificados. Usa lenguaje condicional ("podría", "es técnicamente viable que") y documenta los supuestos de cada paso. El pseudocódigo y diagramas son herramientas analíticas, no instrucciones operativas.
> *Formulate the hypothetical attack model based on verified facts. Use conditional language ("could", "it is technically feasible that") and document the assumptions of each step. Pseudocode and diagrams are analytical tools, not operational instructions.*

---

## 3.1 Enunciado de la hipótesis / Hypothesis Statement

```
HYPOTHESIS: An actor with access to the Clínica Dávila leaked dataset
(500,000+ records containing RUT, names, DOB, addresses, phones, emails)
could programmatically query public Chilean RUT lookup platforms
(SII, Registro Civil) using the RUT as a pivot key to enrich each record
with verified identity data, producing a consolidated, cross-validated
personal profile per individual with higher confidence than the raw
leaked data alone.

HIPÓTESIS: Un actor con acceso al dataset filtrado de Clínica Dávila
(500,000+ registros con RUT, nombres, FDN, direcciones, teléfonos,
correos) podría consultar programáticamente plataformas públicas chilenas
de consulta de RUT (SII, Registro Civil) usando el RUT como llave pivot
para enriquecer cada registro con datos de identidad verificados,
produciendo un perfil personal consolidado y cruzado por individuo con
mayor confianza que los datos filtrados crudos.
```

---

## 3.2 Supuestos de la hipótesis / Hypothesis Assumptions

| # | Supuesto / Assumption | Probabilidad / Probability | Justificación / Justification |
|---|---|---|---|
| 1 | El atacante tiene acceso completo al dataset filtrado | Alta — los datos fueron publicados en foros de acceso restringido | Reportado por múltiples fuentes de prensa |
| 2 | Las plataformas públicas de consulta de RUT no tienen rate limiting efectivo | Media — SII implementa CAPTCHA básico que puede ser evadido | Pruebas de concepto documentadas públicamente |
| 3 | El RUT es suficiente como campo pivot para la correlación | Alta — RUT es único por persona y está presente en ambos datasets | Especificaciones técnicas de ambas plataformas |

---

## 3.3 Flujo del ataque / Attack Flow

```
PASO 1: Extraer RUTs del dataset filtrado
        Entrada: Dataset filtrado (CSV, 500k+ registros)
        Acción:  Parsear columna RUT de cada registro
        Salida:  Lista única de RUTs (500k+)

PASO 2: Consultar plataforma pública A (SII)
        Entrada: Lista de RUTs
        Acción:  Enviar solicitud HTTP GET a https://www.sii.cl/consulta-rut?rut=XXXX
        Salida:  Nombre completo verificado por el SII

PASO 3: Consultar plataforma pública B (Registro Civil)
        Entrada: Lista de RUTs
        Acción:  Enviar solicitud a API de validación de identidad
        Salida:  Datos de identidad adicionales

PASO 4: Correlacionar y consolidar
        Entrada: Datos del paso 1 + paso 2 + paso 3
        Acción:  JOIN por RUT, cruzar campos, validar consistencia
        Salida:  Perfil consolidado por individuo

        Resultado final: Dataset enriquecido con datos verificados vs. datos filtrados
```

---

## 3.4 Pseudocódigo analítico / Analytical Pseudocode

> **AVISO / WARNING:** Solo con fines académicos. No representa código ejecutable ni instrucciones operativas.
> *For academic purposes only. Does not represent executable code or operational instructions.*

```python
# HIPOTÉTICO — Fines exclusivamente analíticos
# HYPOTHETICAL — Exclusively for analytical purposes

leaked_data = load_csv("davila_leak_sample.csv")        # 500k+ records from breach
rut_list = extract_unique(leaked_data, column="rut")     # Extract unique RUTs

# Phase A: Verify identity via SII public endpoint
def query_sii(rut: str) -> dict:
    # HTTP GET to public endpoint — no auth required
    response = http_get(f"https://www.sii.cl/consulta-rut?rut={rut}")
    return {"name": parse_name(response), "rut": rut}

# Phase B: Cross-reference via Civil Registry
def query_registro_civil(rut: str) -> dict:
    response = http_get(f"https://www.registrocivil.cl/validacion?rut={rut}")
    return parse_identity(response)

# Phase C: Consolidate profiles
for rut in rut_list[:100]:  # Analytical sample only
    profile_a = query_sii(rut)
    profile_b = query_registro_civil(rut)
    consolidated = merge(profile_a, profile_b, leaked_data[leaked_data.rut == rut])
    save_profile(consolidated)
```

---

## 3.5 Campo pivot / llave de enlace / Pivot Field

| Propiedad / Property | Valor / Value |
|---|---|
| Campo / Field | RUT (Rol Único Tributario / National ID) |
| Presente en dataset A (filtración) | Sí — columna presente en el dataset filtrado |
| Presente en dataset B (SII) | Sí — llave de consulta primaria |
| Presente en dataset C (Registro Civil) | Sí — llave de consulta primaria |
| Unicidad | Único por persona (99.9%+ cobertura poblacional) |
| Carácter público | Sí — RUT es de acceso público en Chile |
| Revocable | No — RUT es permanente |

---

## 3.6 Mapeo MITRE ATT&CK / MITRE ATT&CK Mapping

| Táctica / Tactic | ID | Técnica / Technique | ID | Sub-técnica / Sub-technique | ID | Fuente de Datos / Data Source | ID |
|---|---|---|---|---|---|---|---|
| Resource Development | TA0042 | Gather Victim Identity Information | T1589 | Email Addresses | T1589.002 | Application Log: Network Traffic | DS0015 |
| Collection | TA0009 | Data from Information Repositories | T1213 | Code Repositories | T1213.003 | Application Log: User Activity | DS0015 |
| Reconnaissance | TA0043 | Active Scanning | T1595 | Scanning IP Blocks | T1595.001 | Network Traffic: DNS | DS0029 |

---

## 3.7 Perfil resultante / Resulting Profile

| Dato obtenido / Data Obtained | Fuente original / Source | Sensibilidad / Sensitivity |
|---|---|---|
| RUT | Leaked dataset / SII / RC | Alta — identificador único |
| Nombre completo verificado | SII + Registro Civil | Alta — identidad confirmada |
| Fecha de nacimiento | Leaked dataset | Alta — PII |
| Dirección | Leaked dataset + Registro Civil | Alta — PII |
| Teléfono / correo | Leaked dataset | Alta — PII |
| Validez cruzada | Correlación 2+ fuentes | Alta — incrementa confianza del perfil |

---

## 3.8 Limitaciones de la hipótesis / Hypothesis Limitations

- Limitación 1: Rate limiting en plataformas públicas puede reducir la velocidad de extracción a niveles no prácticos para 500k+ registros
- Limitación 2: No hay confirmación pública de que el actor ejecutó este proceso específico
- Limitación 3: Algunos RUTs pueden haber sido inválidos o de personas fallecidas, reduciendo la tasa de éxito
- Limitación 4: CAPTCHA o WAF en plataformas .gob.cl puede bloquear solicitudes automatizadas

---

*Template MTD-HX v2.0 — Cybersecurity Research Framework by hoxtxnDev*
