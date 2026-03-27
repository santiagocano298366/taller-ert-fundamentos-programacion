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
   [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/santiagocano298366/taller-ert-fundamentos-programacion/blob/main/notebook/taller_ert_completo.ipynb)

2. Montar Google Drive cuando se solicite
3. Ejecutar las celdas en orden (Shift + Enter)

---

*Taller elaborado por Miguel A. Becerra Ph.D. — Semana 5*
