# ☁️ Punto 7 — Consulta Metodológica AWS

## Sistema ERT Monitor — Despliegue en Amazon Web Services
**Maestría en Automatización | Fundamentos de Programación Científica**
**Autor:** Santiago Cano | **Fecha:** Marzo 2026

---

## 1. Tipo de Aplicación

La solución tiene **3 componentes** a desplegar de forma integrada:

| Componente | Descripción | Tecnología |
|------------|-------------|------------|
| **Backend científico** | Módulos Python del taller (validación, KPIs, Montecarlo, ML) | FastAPI + Python 3.11 |
| **Frontend dashboard** | Interfaz React del prototipo Lovable | React + TypeScript (SPA estática) |
| **Pipeline de datos** | Ingesta y almacenamiento de archivos ERT CSV | S3 + DynamoDB |

---

## 2. Arquitectura de Despliegue

Usuario/Navegador │ HTTPS ▼ S3 Static Website + CloudFront (CDN) │ Dashboard React │ API calls JSON ▼ API Gateway REST │ Rutas: /validar /kpis /montecarlo /prediccion ▼ AWS Lambda (Python 3.11) × 4 funciones │ │ ▼ ▼ Amazon S3 Amazon DynamoDB (CSV + modelos ML) (KPIs + alertas + simulaciones) │ ▼ CloudWatch + CodePipeline (monitoreo + CI/CD)


---

## 3. Servicios AWS Seleccionados

| Servicio | Uso | Capa gratuita |
|----------|-----|---------------|
| **Amazon S3** | Datos ERT CSV, frontend React, modelos ML | 5 GB / mes |
| **Amazon CloudFront** | CDN + HTTPS para el dashboard | 1 TB transferencia |
| **AWS Lambda** | Ejecutar los 4 módulos Python del taller | 1M requests / mes |
| **Amazon API Gateway** | Endpoints REST para el frontend | 1M calls / mes |
| **Amazon DynamoDB** | Resultados KPIs, alertas, simulaciones | 25 GB storage |
| **AWS CloudWatch** | Logs, métricas, alarmas de errores | 5 GB logs |
| **AWS CodePipeline** | CI/CD automático desde GitHub | 1 pipeline gratuito |
| **AWS IAM** | Roles y permisos mínimos por servicio | Sin costo |

**Costo estimado para perfil académico: USD 0/mes (dentro de capa gratuita)**

---

## 4. Secuencia de Despliegue

FASE 1: DESARROLLO → Código Python en Colab / VS Code + GitHub ↓ FASE 2: PRUEBAS → pytest (unitarias) + npm run build (frontend) ↓ FASE 3: EMPAQUETADO → zip Lambda package + requirements.txt npm run build → /dist estático ↓ FASE 4: DESPLIEGUE → Lambda upload + API Gateway config S3 sync frontend + CloudFront distribution DynamoDB tables creation ↓ FASE 5: MONITOREO → CloudWatch Logs + Alarmas SNS por email Dashboard métricas: invocaciones, latencia, errores ↓ FASE 6: ITERACIÓN → CodePipeline: push GitHub → build → test → deploy


---

## 5. Ventajas, Riesgos y Limitaciones

### ✅ Ventajas
- **Costo cero** en capa gratuita para volumen académico
- **Escalabilidad automática** de Lambda sin gestión de servidores
- **Reproducibilidad científica** con datos versionados en S3
- **CI/CD automático** desde GitHub vía CodePipeline

### ⚠️ Riesgos
- **Cold start Lambda** (~300–500 ms en primera invocación)
  → Mitigación: Provisioned Concurrency para funciones críticas
- **Timeout 15 min Lambda** si el modelo ML crece en complejidad
  → Mitigación: AWS Step Functions para simulaciones largas
- **Vendor lock-in** a servicios propietarios AWS
  → Mitigación: containerización Docker para portabilidad

### 🚧 Limitaciones
- **Límite 250 MB** en paquete Lambda (NumPy+pandas+sklearn ≈ 180 MB)
  → Solución: Lambda Layers o migrar a Amazon ECS con Docker
- **No es tiempo real** — arquitectura request-response
  → Evolución futura: AWS IoT Core + Kinesis para datos continuos
- **Curva de aprendizaje** de 2–4 semanas para configuración inicial
  → Alternativa simple: AWS Elastic Beanstalk o AWS Amplify

---

## 6. Costo Estimado (Perfil Académico)

| Servicio | Uso/mes | Capa gratuita | Costo |
|----------|---------|---------------|-------|
| AWS Lambda | 15,000 req | 1M GRATIS | **$0.00** |
| API Gateway | 15,000 calls | 1M GRATIS | **$0.00** |
| S3 (datos + frontend) | 2 GB | 5 GB GRATIS | **$0.00** |
| CloudFront | 15 GB | 1 TB GRATIS | **$0.00** |
| DynamoDB | 1 GB | 25 GB GRATIS | **$0.00** |
| CloudWatch | 1 GB logs | 5 GB GRATIS | **$0.00** |
| **TOTAL** | | | **USD 0.00/mes** |

> AWS ofrece 12 meses de capa gratuita para nuevas cuentas.

---
*Generado: 2026-03-27 21:05:26*
