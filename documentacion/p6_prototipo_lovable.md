# Punto 6 — Prototipo Lovable
**URL:** https://ert-monitor-east-river.lovable.app


---

## 🖥️ Punto 6 — Prototipo Funcional en Lovable

### 🔗 Acceso al prototipo

> **[▶️ Abrir ERT Monitor Dashboard](https://ert-monitor-east-river.lovable.app)**

[![Prototipo ERT Monitor](https://img.shields.io/badge/Lovable-ERT%20Monitor%20Dashboard-blueviolet?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI+PHBhdGggZmlsbD0id2hpdGUiIGQ9Ik0xMiAyQzYuNDggMiAyIDYuNDggMiAxMnM0LjQ4IDEwIDEwIDEwIDEwLTQuNDggMTAtMTBTMTcuNTIgMiAxMiAyem0tMiAxNWwtNS01IDEuNDEtMS40MUwxMCAxNC4xN2w3LjU5LTcuNTlMMTkgOGwtOSA5eiIvPjwvc3ZnPg==)](https://ert-monitor-east-river.lovable.app)

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
