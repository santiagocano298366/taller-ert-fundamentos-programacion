# 📋 Avance del Proyecto Final

## Maestría en Automatización — Fundamentos de Programación Científica
**Autor:** Santiago Cano | **Fecha:** Marzo 2026

---

## 1. Título del Proyecto

> **"Diseño y desarrollo de un sistema portátil de bajo costo basado en
> mediciones de resistividad eléctrica para la estimación espacial y en
> tiempo real del potencial mátrico del suelo mediante modelos de
> aprendizaje automático."**

---

## 2. Problema y Contexto

El potencial mátrico del suelo (ψ, kPa) determina la disponibilidad
de agua para plantas y recarga de acuíferos. Su medición directa con
tensiómetros comerciales cuesta entre USD 500 y USD 2,000 por nodo.
La resistividad eléctrica del suelo (ρ, Ohm·m) está físicamente
relacionada con el contenido de agua, pero los equipos ERT comerciales
cuestan entre USD 20,000 y USD 80,000. Este proyecto propone un sistema
portátil de bajo costo (< USD 150) que integra medición de resistividad
con modelos de ML para estimar ψ en tiempo real.

---

## 3. Objetivo General

Desarrollar un sistema portátil de bajo costo para estimar espacialmente
el potencial mátrico del suelo mediante resistividad eléctrica y
aprendizaje automático, validado con el dataset ERT del East River
Watershed (ESS-DIVE, doi:10.15485/1969563).

## Objetivos Específicos

| # | Objetivo |
|---|----------|
| OE1 | Caracterizar la relación cuantitativa ρ → θ con el dataset ESS-DIVE |
| OE2 | Comparar modelos ML: Random Forest, XGBoost y Red Neuronal MLP |
| OE3 | Diseñar prototipo electrónico con ESP32 y 4 electrodos |
| OE4 | Validar el prototipo con tensiómetros de referencia en campo |
| OE5 | Implementar interfaz de visualización en tiempo real con alertas |

---

## 4. Variables Disponibles

| Variable | Unidad | Fuente |
|----------|--------|--------|
| Resistividad aparente (ρ) | Ohm·m | Dataset ESS-DIVE |
| Temperatura del suelo (T) | °C | Dataset ESS-DIVE |
| Profundidad del electrodo (z) | m | Dataset ESS-DIVE |
| Posición en el transecto | m | Dataset ESS-DIVE |
| Potencial mátrico (ψ) — objetivo | kPa | Estimado vía van Genuchten |

---

## 5. Metodología Preliminar

Fase 1 (Sem. 1–3) → Adquisición y preprocesamiento de datos ERT Fase 2 (Sem. 4–5) → Análisis exploratorio e ingeniería de características
Fase 3 (Sem. 6–8) → Modelado ML: RF, XGBoost, MLP Fase 4 (Sem. 9–11) → Diseño del prototipo hardware ESP32 Fase 5 (Sem. 12–14)→ Validación, incertidumbre y publicación

---

## 6. Revisión de Literatura (8 referencias)

| # | Autores | Año | Problema abordado | Técnica | Relación con el proyecto |
|---|---------|-----|-------------------|---------|--------------------------|
| R1 | Meng et al. | 2024 | Cuantificación ρ→θ con ML y ERT de alta resolución | XGBoost, RF, ERT | Referencia central para OE2 |
| R2 | Zeng et al. | 2025 | Modelo teórico ρ→θ en loess no saturado | ERT + Archie mod. | Fundamenta conversión ρ→ψ |
| R3 | Dafflon et al. | 2025 | Dataset ERT time-lapse East River Watershed | MPT ERT, 128 elec. | Dataset principal del proyecto |
| R4 | Ciampi et al. | 2024 | Clustering ERT para heterogeneidad litológica | ERT + clustering | Ingeniería de características |
| R5 | Amabile et al. | 2023 | ERT para monitoreo de contenido hídrico en diques | ERT time-lapse | Protocolo de validación OE4 |
| R6 | Tso et al. | 2023 | Estimación humedad con ERT+FDEM y Random Forest | RF + ERT + FDEM | Justifica uso de RF en OE2 |
| R7 | Blanchy et al. | 2023 | Evaluación multiscala ERT-VWC | ERT + análisis escala | Análisis de incertidumbre Fase 5 |
| R8 | Navarro-Hellín et al. | 2024 | Sistema IoT bajo costo para humedad del suelo | ESP32, LoRa, sensores | Arquitectura hardware OE3 |

### Referencias APA Completas

- Meng, F., Wang, J., Zhao, Y., & Chen, Z. (2024). Journal of Hydrology, 645, 131908. https://doi.org/10.1016/j.jhydrol.2024.131908
- Zeng, H. et al. (2025). Geosciences, 15(8), 302. https://doi.org/10.3390/geosciences15080302
- Dafflon, B., Leger, E., & Peterson, J. (2025). ESS-DIVE. https://doi.org/10.15485/1969563
- Ciampi, P. et al. (2024). Engineering Geology, 337, 107589. https://doi.org/10.1016/j.enggeo.2024.107589
- Amabile, A. et al. (2023). Vadose Zone Journal, 22(6), e20290. https://doi.org/10.1002/vzj2.20290
- Tso, C. H. M. et al. (2023). Vadose Zone Journal, 22(1), e20246. https://doi.org/10.1002/vzj2.20246
- Blanchy, G. et al. (2023). Scientific Reports, 13, 20927. https://doi.org/10.1038/s41598-023-48100-w
- Navarro-Hellín, H. et al. (2024). Sensors, 24(24), 7952. https://www.ncbi.nlm.nih.gov/pmc/articles/PMC11679594/

---

## 7. Resultados Esperados y Aporte

| Resultado | Descripción |
|-----------|-------------|
| RE1 | Modelo ML con R² > 0.80 para estimación de ψ desde ρ |
| RE2 | Prototipo funcional < USD 150 con transmisión inalámbrica |
| RE3 | Dataset de calibración en 2 tipos de suelo |
| RE4 | Interfaz de visualización en tiempo real con alertas |
| RE5 | Análisis costo-efectividad vs. tensiómetros comerciales |

**Aporte principal:** Reducir el costo de monitoreo hídrico del suelo
de USD 500–2,000 a < USD 150 por nodo, integrando hardware de bajo
costo, ML y visualización en tiempo real en un único sistema abierto
y reproducible.

---
*Generado: 2026-03-27 20:52:22*
