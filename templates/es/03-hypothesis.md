---
mtd_hx_version: "2.0"
phase: 03
phase_name: "Hipótesis Técnica"
case_id: "CD-2025-001"
author: "hoxtxnDev"
date: "2026-05-03"
status: final
mitre_tactics:
  - "TA0042 — Desarrollo de Recursos"
  - "TA0009 — Recolección"
cvss_version: "N/A"
legal_framework: ["Ley 19.628 (Chile)", "Ley 21.663 (Chile)"]
---

# Fase 3 — Hipótesis Técnica

> Formula el modelo de ataque hipotético basado en hechos verificados. Usa lenguaje condicional ("podría", "es técnicamente viable que"). Pseudocódigo y diagramas son herramientas analíticas, no instrucciones operativas.

---

## 3.1 Enunciado de la Hipótesis

```
HIPÓTESIS: Un actor con acceso al dataset filtrado de Clínica Dávila
(500,000+ registros con RUT, nombres, FDN, direcciones, teléfonos, correos)
podría consultar programáticamente plataformas públicas chilenas de consulta
de RUT (SII, Registro Civil) usando el RUT como llave pivot para enriquecer
cada registro con datos de identidad verificados, produciendo un perfil
personal consolidado y validado por individuo.
```

---

## 3.2 Supuestos de la Hipótesis

| # | Supuesto | Probabilidad | Justificación |
|---|---|---|---|
| 1 | El atacante tiene acceso completo al dataset filtrado | Alta — datos publicados en foros de acceso restringido | Reportado por múltiples fuentes |
| 2 | Las plataformas públicas no tienen rate limiting efectivo | Media — SII implementa CAPTCHA básico evitable | POCs documentados públicamente |
| 3 | RUT es suficiente como campo pivot | Alta — único por persona y presente en ambos datasets | Especificaciones técnicas |

---

## 3.3 Flujo del Ataque

```
PASO 1: Extraer RUTs del dataset filtrado
        Entrada: Dataset filtrado (CSV, 500k+ registros)
        Acción:  Parsear columna RUT
        Salida:  Lista única de RUTs

PASO 2: Consultar plataforma pública A (SII)
        Entrada: Lista de RUTs
        Acción:  HTTP GET a https://www.sii.cl/consulta-rut?rut=XXXX
        Salida:  Nombre verificado por SII

PASO 3: Consultar plataforma pública B (Registro Civil)
        Entrada: Lista de RUTs
        Acción:  Solicitud a API de validación de identidad
        Salida:  Datos de identidad adicionales

PASO 4: Correlacionar y consolidar
        Entrada: Datos pasos 1+2+3
        Acción:  JOIN por RUT, cruzar campos
        Salida:  Perfil consolidado por individuo
```

---

## 3.4 Pseudocódigo Analítico

> **AVISO:** Solo fines académicos. No es código ejecutable ni instrucciones operativas.

```python
# HIPOTÉTICO — Fines exclusivamente analíticos

leaked_data = load_csv("davila_leak_sample.csv")
rut_list = extract_unique(leaked_data, column="rut")

def query_sii(rut: str) -> dict:
    response = http_get(f"https://www.sii.cl/consulta-rut?rut={rut}")
    return {"name": parse_name(response), "rut": rut}

def query_registro_civil(rut: str) -> dict:
    response = http_get(f"https://www.registrocivil.cl/validacion?rut={rut}")
    return parse_identity(response)

for rut in rut_list[:100]:  # Muestra analítica solamente
    profile_a = query_sii(rut)
    profile_b = query_registro_civil(rut)
    consolidated = merge(profile_a, profile_b, leaked_data[leaked_data.rut == rut])
    save_profile(consolidated)
```

---

## 3.5 Campo Pivot

| Propiedad | Valor |
|---|---|
| Campo | RUT (Rol Único Tributario) |
| Presente en dataset A (filtración) | Sí |
| Presente en dataset B (SII) | Sí — llave primaria |
| Presente en dataset C (Registro Civil) | Sí — llave primaria |
| Unicidad | Único por persona (99.9%+ cobertura) |
| Carácter público | Sí |
| Revocable | No |

---

## 3.6 Mapeo MITRE ATT&CK

| Táctica | ID | Técnica | ID | Sub-técnica | ID | Fuente de Datos | ID |
|---|---|---|---|---|---|---|---|
| Desarrollo de Recursos | TA0042 | Obtener Información de Identidad | T1589 | Correos Electrónicos | T1589.002 | Log de Aplicación | DS0015 |
| Recolección | TA0009 | Datos de Repositorios | T1213 | Repositorios de Código | T1213.003 | Log de Aplicación | DS0015 |
| Reconocimiento | TA0043 | Escaneo Activo | T1595 | Escaneo de IPs | T1595.001 | Tráfico de Red | DS0029 |

---

## 3.7 Perfil Resultante

| Dato Obtenido | Fuente | Sensibilidad |
|---|---|---|
| RUT | Dataset filtrado / SII / RC | Alta |
| Nombre completo verificado | SII + Registro Civil | Alta |
| Fecha de nacimiento | Dataset filtrado | Alta |
| Dirección | Dataset filtrado + RC | Alta |
| Teléfono / correo | Dataset filtrado | Alta |
| Validación cruzada | Correlación 2+ fuentes | Alta |

---

## 3.8 Limitaciones

- Los límites de tasa en plataformas públicas pueden reducir la velocidad de extracción
- No hay confirmación pública de que el actor ejecutó este proceso
- Algunos RUTs pueden pertenecer a fallecidos, reduciendo la tasa de éxito
- CAPTCHA o WAF en plataformas .gob.cl puede bloquear solicitudes automatizadas

---

*Template MTD-HX v2.0 — Cybersecurity Research Framework by hoxtxnDev*
