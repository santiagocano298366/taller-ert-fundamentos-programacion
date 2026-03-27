# 🌍 Taller Integrador — Fundamentos de Programación Científica
## Monitoreo ERT — East River Watershed, Colorado (2016–2018)

**Maestría en Automatización**
**Autor:** Santiago Cano
**Dataset:** [ESS-DIVE doi:10.15485/1969563](https://data.ess-dive.lbl.gov/view/doi:10.15485/1969563)
**Herramienta:** Google Colab + Python 3

---

## 📌 Descripción del proyecto

Este repositorio contiene el desarrollo completo del taller integrador de
Fundamentos de Programación Científica. El caso de estudio es el sistema de
**Tomografía de Resistividad Eléctrica (ERT)** del sitio Pumphouse en el
upper East River Watershed, Colorado, USA, que monitorea condiciones del
subsuelo (humedad, congelamiento, saturación) mediante 128 electrodos durante
el período 2016–2018.

---

## 🗂️ Estructura del repositorio

taller-ert-fundamentos-programacion/ │ ├── README.md │ ├── notebook/ │ └── taller_ert_completo.ipynb ← Notebook principal en Colab │ ├── resultados/ │ ├── tablas/ │ │ ├── p1_registros_validos.csv ← Punto 1: registros válidos │ │ ├── p1_alertas.txt ← Punto 1: log de alertas │ │ ├── p2_registros_30dias.csv ← Punto 2: 30 días con categoría │ │ ├── p2_gradiente_diario.csv ← Punto 2: cambios consecutivos │ │ ├── p2_estadisticas.csv ← Punto 2: lista vs NumPy │ │ ├── p3_kpis_por_periodo.csv ← Punto 3: KPIs y semáforos │ │ ├── p4_muestra_simulaciones.csv ← Punto 4: muestra Montecarlo │ │ └── p4_resumen_montecarlo.csv ← Punto 4: estadísticas finales │ └── graficos/ │ └── p4_montecarlo_cobertura_ert.png ← Punto 4: histograma │ └── documentacion/ └── p3_hallazgos_acciones.txt ← Punto 3: hallazgos y acciones

---

## 🧪 Puntos del taller desarrollados

### ✅ Punto 1 — Programación básica en Python
Programa de validación y clasificación de 10 registros de resistividad
eléctrica del suelo. Implementa `if/elif/else`, ciclo `for` para recorrer
los registros y ciclo `while` para emitir alertas. Detecta 3 tipos de
condición: suelo saturado, suelo helado y datos inválidos por falla de sensor.

### ✅ Punto 2 — Manejo de listas y arreglos
Análisis de 30 días consecutivos de resistividad. Trabajo con **listas
nativas** (máximo, mínimo, promedio manuales) y **arreglos NumPy** con
3 operaciones: estadísticas descriptivas, normalización Min-Max y gradiente
temporal con `np.diff()`. Comparación explícita Lista vs. NumPy.

### ✅ Punto 3 — Indicadores con semáforo
Sistema de **4 KPIs** evaluados sobre 3 períodos estacionales (Otoño 2016,
Invierno 2017, Primavera-Verano 2017):
| KPI | Descripción | Dirección |
|-----|-------------|-----------|
| KPI1 | Cobertura de Datos | Mayor es mejor |
| KPI2 | Estabilidad de Señal | Mayor es mejor |
| KPI3 | Tasa de Anomalías | Menor es mejor |
| KPI4 | Índice de Cambio Brusco | Menor es mejor |

Semáforo 🟢/🟡/🔴 con diagnóstico general por período y 4 hallazgos
documentados con acciones sugeridas.

### ✅ Punto 4 — Simulación de Montecarlo
**10,000 simulaciones** para estimar la probabilidad de que el sistema ERT
alcance una cobertura de datos ≥ 85% en un período de invierno (90 días).

- Variable aleatoria: días perdidos ~ **Poisson(λ=3.2)** energía solar
  + **Poisson(λ=1.5)** falla MPT
- Resultado: **P(cobertura ≥ 85%) = 44.92%** → Riesgo ALTO
- Incluye histograma de coberturas + distribución de días perdidos

---

## 📊 Resultados principales

| Período | KPI1 Cobertura | KPI2 Estabilidad | KPI3 Anomalías | KPI4 Cambios | Estado |
|---------|---------------|-----------------|---------------|-------------|--------|
| Otoño 2016 | 93.4% 🟢 | 40.0% 🔴 | 6.6% 🟡 | 13.3% 🟡 | 🟡 En Riesgo |
| Invierno 2017 | 79.8% 🟡 | 46.7% 🔴 | 20.2% 🔴 | 15.9% 🟡 | 🔴 Crítico |
| Primavera 2017 | 96.7% 🟢 | 100.0% 🟢 | 3.3% 🟢 | 2.5% 🟢 | 🟢 Operativo |

---

## 🛠️ Tecnologías utilizadas

- **Python 3** — lenguaje principal
- **NumPy** — operaciones sobre arreglos
- **Matplotlib** — visualización de resultados
- **Google Colab** — entorno de desarrollo
- **Google Drive** — almacenamiento de archivos

---

## 📚 Fuente del dataset

> Dafflon, B., Leger, E., & Peterson, J. (2025).
> *Electrical Resistivity Tomography data from 2016 to 2018 at the
> Lower Montane site in the East River Watershed, Colorado.*
> ESS-DIVE. https://doi.org/10.15485/1969563

---

## ▶️ Cómo ejecutar

1. Abrir el notebook en Google Colab:
   [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)]([https://colab.research.google.com/github/santiagocano298366/taller-ert-fundamentos-programacion/blob/main/notebook/taller_ert_completo.ipynb](https://colab.research.google.com/drive/13QTFUv7h3UkCPF9IErb7otvd4Obfa060?usp=sharing))

2. Montar Google Drive cuando se solicite
3. Ejecutar las celdas en orden (Shift + Enter)

---

*Taller elaborado por Miguel A. Becerra Ph.D. — Semana 5*

---

## 🖥️ Punto 6 — Prototipo Funcional en Lovable

### 🔗 Acceso al prototipo

> **[▶️ Abrir ERT Monitor Dashboard]([https://id-preview--23e1851e-5ac6-4613-95ce-12411e316184.lovable.app/?__lovable_token=eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyX2lkIjoiNGJ3dXE4UGdqRFNGRG1XajZTY1gxWkhQZkJlMiIsInByb2plY3RfaWQiOiIyM2UxODUxZS01YWM2LTQ2MTMtOTVjZS0xMjQxMWUzMTYxODQiLCJhY2Nlc3NfdHlwZSI6InByb2plY3QiLCJpc3MiOiJsb3ZhYmxlLWFwaSIsInN1YiI6IjIzZTE4NTFlLTVhYzYtNDYxMy05NWNlLTEyNDExZTMxNjE4NCIsImF1ZCI6WyJsb3ZhYmxlLWFwcCJdLCJleHAiOjE3NzUyNDk3NzMsIm5iZiI6MTc3NDY0NDk3MywiaWF0IjoxNzc0NjQ0OTczfQ.pqa0Zkcl6GfBk7p9PVjZ_xm4LMDty08srQ56YcvyyP0v2Xj7VsubkwQfbFFckowgMhyat5hRyGtW8P_LxEWbjt9l2sADgK3JprLlgvsjE-Pge5dB8Oyt5be5RcjT_1AHvV3Oi1g3u8UemZU_tJnMwpkUpU5f0Mp5I-VAwUEx6cO7Mo9wBCLVoXXG9XPFwcSFcV2IsEO9lsaYOeVcMG8Fw2g0LD-0S-9zknqRodwsnSFb7X124IPtNh1KHBRGLABNmg4MFn0Ksv0hQ04PbZekSryR-0mXdgo3Av0yiDi2Ta4G8H-Bt3zCa0AYWOjbQt4xRocJos2lxGCmf_bvYuquKMtX-opyAmuIR_n0BYXM6FYGjPMFBFD7Odrtph-hsyv0yKPx8H0YaVa-0sqNHOm8p7xbq2a3DFPE7o1Cq6zH3M-420I1MRFR1qcNMkcHG6qKBEb91RdOzTVKNBdLpUf-thILoI7GajTu9O976xWtPf6sKIfIF6Oni6XrXcv2e_QW1vz__QYywmuJivnemyxGXJejxVm6c0zuAhrStgVdDNfVrOH5Wyc17Ka_281q9qJWlVeFxQBTSphsWblkfppkqRkiNYP88vLvSycQHMMrGAxoVbj2GB7TirIe_3Pe44b9URsJ4utFyAZyQWZDp5SHPLblX9AVLc2vGrLHquZOlXk](https://lovable.dev/projects/23e1851e-5ac6-4613-95ce-12411e316184)**

[![Prototipo ERT Monitor](https://img.shields.io/badge/Lovable-ERT%20Monitor%20Dashboard-blueviolet?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI+PHBhdGggZmlsbD0id2hpdGUiIGQ9Ik0xMiAyQzYuNDggMiAyIDYuNDggMiAxMnM0LjQ4IDEwIDEwIDEwIDEwLTQuNDggMTAtMTBTMTcuNTIgMiAxMiAyem0tMiAxNWwtNS01IDEuNDEtMS40MUwxMCAxNC4xN2w3LjU5LTcuNTlMMTkgOGwtOSA5eiIvPjwvc3ZnPg==)](https://id-preview--23e1851e-5ac6-4613-95ce-12411e316184.lovable.app/?__lovable_token=eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyX2lkIjoiNGJ3dXE4UGdqRFNGRG1XajZTY1gxWkhQZkJlMiIsInByb2plY3RfaWQiOiIyM2UxODUxZS01YWM2LTQ2MTMtOTVjZS0xMjQxMWUzMTYxODQiLCJhY2Nlc3NfdHlwZSI6InByb2plY3QiLCJpc3MiOiJsb3ZhYmxlLWFwaSIsInN1YiI6IjIzZTE4NTFlLTVhYzYtNDYxMy05NWNlLTEyNDExZTMxNjE4NCIsImF1ZCI6WyJsb3ZhYmxlLWFwcCJdLCJleHAiOjE3NzUyNDk3NzMsIm5iZiI6MTc3NDY0NDk3MywiaWF0IjoxNzc0NjQ0OTczfQ.pqa0Zkcl6GfBk7p9PVjZ_xm4LMDty08srQ56YcvyyP0v2Xj7VsubkwQfbFFckowgMhyat5hRyGtW8P_LxEWbjt9l2sADgK3JprLlgvsjE-Pge5dB8Oyt5be5RcjT_1AHvV3Oi1g3u8UemZU_tJnMwpkUpU5f0Mp5I-VAwUEx6cO7Mo9wBCLVoXXG9XPFwcSFcV2IsEO9lsaYOeVcMG8Fw2g0LD-0S-9zknqRodwsnSFb7X124IPtNh1KHBRGLABNmg4MFn0Ksv0hQ04PbZekSryR-0mXdgo3Av0yiDi2Ta4G8H-Bt3zCa0AYWOjbQt4xRocJos2lxGCmf_bvYuquKMtX-opyAmuIR_n0BYXM6FYGjPMFBFD7Odrtph-hsyv0yKPx8H0YaVa-0sqNHOm8p7xbq2a3DFPE7o1Cq6zH3M-420I1MRFR1qcNMkcHG6qKBEb91RdOzTVKNBdLpUf-thILoI7GajTu9O976xWtPf6sKIfIF6Oni6XrXcv2e_QW1vz__QYywmuJivnemyxGXJejxVm6c0zuAhrStgVdDNfVrOH5Wyc17Ka_281q9qJWlVeFxQBTSphsWblkfppkqRkiNYP88vLvSycQHMMrGAxoVbj2GB7TirIe_3Pe44b9URsJ4utFyAZyQWZDp5SHPLblX9AVLc2vGrLHquZOlXk)

---

### 📋 Propósito del prototipo

El prototipo **ERT Monitor** es un dashboard de monitoreo geofísico en tiempo
real construido en Lovable (React + TypeScript + Recharts + Tailwind CSS).
Traduce los resultados computacionales del taller (Puntos 1–4) en una interfaz
visual interactiva orientada a operadores de campo y gestores de proyectos de
monitoreo ambiental.

**Problema que resuelve:** Los datos brutos de Tomografía de Resistividad
Eléctrica (ERT) son difíciles de interpretar sin herramientas visuales.
Este prototipo convierte los valores numéricos de resistividad en indicadores
operativos con semáforos, gráficos interactivos y alertas accionables.

---

### 🗂️ Estructura del prototipo (4 módulos)

| Módulo | Descripción | Requisito cubierto |
|--------|-------------|-------------------|
| **📊 Dashboard** | KPIs con semáforo + serie temporal de resistividad + distribución de condiciones del suelo | Visualización de resultados |
| **📋 Tabla de Datos** | 30 registros filtrables y ordenables con badges de categoría | Formulario/tabla de captura |
| **⚡ Alertas y KPIs** | Comparativa de 3 períodos estacionales + alertas activas del sistema | Indicadores operativos |
| **🎲 Monte Carlo** | Histograma de 10,000 simulaciones + distribución de días perdidos + recomendaciones | Resultados de simulación |

---

### 🔍 Caso de uso

Un operador del sistema ERT en el sitio East River Watershed, Colorado,
accede al dashboard desde una tablet en campo. En la pestaña **Dashboard**
verifica de un vistazo el estado actual del sistema mediante los 4 KPIs
con semáforo verde/amarillo/rojo. Si detecta una alerta roja, navega a
**Alertas y KPIs** para revisar el período problemático y consultar la
acción sugerida. Antes de cada invierno, revisa la pestaña **Monte Carlo**
para conocer la probabilidad de mantener cobertura ≥ 85% y planificar el
mantenimiento preventivo.

---

### 💡 Valor del prototipo

- **Reduce el tiempo de interpretación** de datos ERT de horas a segundos
- **Democratiza el acceso** a análisis geofísico para operadores no expertos
- **Base funcional** para evolucionar hacia una aplicación web desplegada
  en AWS (ver Punto 7) con datos en tiempo real via API
- **Evidencia de trazabilidad** completa: los mismos datos del dataset
  ESS-DIVE (doi:10.15485/1969563) usados en Python aparecen en el dashboard

---

### 🛠️ Tecnologías del prototipo

| Tecnología | Uso |
|------------|-----|
| React + TypeScript | Framework principal |
| Tailwind CSS | Diseño dark-theme responsive |
| Recharts | Gráficos interactivos (línea, barras, torta, histograma) |
| shadcn/ui | Componentes (tablas, badges, cards, tabs) |
| Lovable.dev | Plataforma de generación y despliegue |

---
