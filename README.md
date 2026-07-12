# 🛡️ ÉGIDA — Maqueta de Demostración

<div align="center">

![Demo](https://img.shields.io/badge/Demo-Live-30d158?style=for-the-badge)
![Autocontenida](https://img.shields.io/badge/Sin_Backend-Autocontenida-0a84ff?style=for-the-badge)
![NTSIC](https://img.shields.io/badge/DS_N°7/2023-NTSIC-5e5ce6?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

**Portal de Autogestión de Madurez y Cumplimiento Normativo en Ciberseguridad para órganos de la Administración del Estado de Chile**

[🌐 **Ver demo en vivo →**](https://jarayaa.github.io/egida-demo/)

*ACIF3003 — Proyecto de Innovación | UNAB — Jaime Araya Aros*

</div>

---

## 📖 ¿Qué es esta maqueta?

Una **vitrina funcional** del portal ÉGIDA que corre directamente en el navegador, sin backend ni base de datos. Demuestra las capacidades núcleo del sistema:

- 🎯 Autodiagnóstico de los 20 controles críticos del DS N°7/2023 con cálculo real del IMI
- 📊 Panel de indicadores con promedios por función NTSIC
- 🤖 Asistente normativo RAG con citación obligatoria (conectado al chatbot del MVP validado)
- 🔐 Simulación de roles (Directivo, Técnico, Operativo) asignados por correo

> **Nota:** La versión funcional completa (autenticación JWT, persistencia, informes PDF, auditoría) se ejecuta con `docker compose` desde el [repositorio privado](https://github.com/jarayaa/EGIDA) y está desplegada en **https://egida.uk**.

---

## 📊 Módulos del Portal

### 1. Autodiagnóstico de Madurez

<div align="center">

![Autodiagnóstico](assets/modulo-autodiagnostico.svg)

</div>

Evalúe los **20 controles críticos** del Anexo A NCh-ISO 27001.Of2009, organizados por las 5 funciones del DS N°7/2023 (Identificar, Proteger, Detectar, Responder, Recuperar). El **Índice de Madurez Institucional (IMI)** se calcula en tiempo real con la fórmula determinística:

```
IMI = (Σ niveles / 60) × 100    [escala 0–100, 1 decimal]
```

---

### 2. Panel de Indicadores por Rol

<div align="center">

![Panel](assets/modulo-panel.svg)

</div>

Visualice el estado de madurez de su organismo con indicadores diferenciados por perfil:

| Rol | Vista |
|-----|-------|
| **Directivo** | IMI agregado, tendencia, total de brechas |
| **Técnico (RIS/RAI)** | Detalle completo: controles, niveles, recomendaciones |
| **Operativo** | Solo lectura de evaluaciones completadas |

---

### 3. Asistente Normativo con Citación Obligatoria

<div align="center">

![Asistente](assets/modulo-asistente.svg)

</div>

Consulte la normativa chilena en **lenguaje natural**. El asistente responde exclusivamente desde el corpus indexado, con:

- ✅ **Citas verificables**: tipo de instrumento correcto (DS, Resolución, Norma, Ley) + artículo exacto
- ✅ **Condiciones habilitantes**: plazos del DS N°295/2024 con sus condiciones (ej.: 24 h solo si OIV con servicios esenciales afectados)
- ✅ **Verificación OIV**: búsqueda difusa contra la nómina de la Res. Ex. N°87/2025 ANCI
- ✅ **Rechazo fuera de dominio**: frase exacta si la consulta no está cubierta por el corpus
- ✅ **Advertencia asistiva**: toda respuesta requiere validación humana

---

## 🔐 Roles disponibles en la maqueta

El perfil se asigna automáticamente por el correo ingresado:

| Correo | Rol asignado |
|--------|:---:|
| `ris@organismo.gob.cl` | Técnico (RIS/RAI) |
| `jefe@organismo.gob.cl` | Directivo |
| `operador@organismo.gob.cl` | Operativo |
| Cualquier otro | Técnico (default) |

---

## 🏗️ Tecnología

| Aspecto | Detalle |
|---------|---------|
| Archivo | `index.html` único, autocontenido (~50 KB) |
| Backend | No requiere — todo corre en el navegador |
| Cálculos | IMI determinístico en JavaScript (replica backend) |
| Asistente | iframe del chatbot Chatbase del MVP validado + modo offline |
| Tema visual | macOS dark, translúcidos, acento #0a84ff |
| Accesibilidad | WCAG AA (contraste, labels, foco) |

---

## 🔗 Enlaces

| | |
|---|---|
| 🌐 **Demo en vivo** | [jarayaa.github.io/egida-demo](https://jarayaa.github.io/egida-demo/) |
| 🔒 **Producción** | [egida.uk](https://egida.uk) |
| 📁 **Repositorio principal** | [github.com/jarayaa/EGIDA](https://github.com/jarayaa/EGIDA) (privado) |
| 🏫 **MVP no-code** | [portal-ntsic-mvp.softr.app](https://portal-ntsic-mvp.softr.app) |

---

## 📜 Normativa implementada

- **DS N°7/2023** — Norma Técnica de Seguridad de la Información y Ciberseguridad (NTSIC)
- **DS N°295/2024** — Reporte obligatorio de incidentes de ciberseguridad
- **Res. Ex. N°7/2025 ANCI** — Taxonomía de incidentes
- **Res. Ex. N°87/2025 ANCI** — Nómina de Operadores de Importancia Vital (OIV)
- **NCh-ISO 27001.Of2009** — Controles del Anexo A

---

<div align="center">

**ACIF3003 — Proyecto de Innovación en Ingeniería Civil Informática**

Universidad Andrés Bello | 2026

🛡️ *Bajo la égida de la ciberseguridad* 🛡️

</div>
