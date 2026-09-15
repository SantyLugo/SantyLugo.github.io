# SavIA Admin

> **Plataforma de Control e Infraestructura Unificada para SavIA Lab**

SavIA Admin es el software de gestión interna desarrollado por **SavIA Control** para centralizar la administración de la infraestructura tecnológica de **SavIA Lab**. Actúa como una capa de orquestación y gobierno sobre el ecosistema físico y lógico, unificando cómputo, almacenamiento, datos y permisos en una sola plataforma coordinada, trazable y escalable.

---

## 📋 Descripción General

La infraestructura de SavIA Lab requiere evolucionar desde un entorno actualmente distribuido en múltiples equipos y servicios hacia un modelo coordinado e institucional. **SavIA Admin** no busca reemplazar tecnologías maduras, sino integrarlas mediante una capa de control propia que simplifique la administración y maximice el aprovechamiento del hardware de inteligencia artificial.

## ✨ Capacidades Principales

* **Gestión de Recursos de Cómputo:** Administración unificada de GPUs, servidores, workstations y nodos de procesamiento.
* **Control de Proyectos y Jobs:** Asignación de cargas de trabajo, seguimiento del ciclo de vida de *jobs* y vinculación por proyecto.
* **Gobernanza de Datos:** Gestión centralizada de almacenamiento, catálogos de metadatos y acceso a *datasets*.
* **Identidad y Seguridad:** Control granular de permisos, autenticación centralizada y políticas de acceso.
* **Observabilidad y Auditoría:** Visibilidad en tiempo real del estado de la infraestructura, métricas de rendimiento y trazabilidad operativa.

## 🛠️ Arquitectura e Integraciones

SavIA Admin opera como una capa superior que conecta herramientas especializadas y consolidadas del ecosistema:

| Dominio | Tecnología / Protocolo | Rol dentro de SavIA Admin |
| :--- | :--- | :--- |
| **Scheduling** | Slurm | Planificación y orquestación de cargas de cómputo de alto rendimiento. |
| **Identidad (IAM)** | Keycloak | Gestión unificada de usuarios, autenticación y autorización por roles. |
| **Observabilidad** | Prometheus / Grafana | Recolección de métricas, alertas y paneles de monitoreo. |
| **Almacenamiento** | NFS / S3 | Abstracción y gestión de volúmenes de almacenamiento en bloque y objetos. |
| **Gobernanza** | Catálogos de Metadatos | Registro, trazabilidad y control de acceso a conjuntos de datos. |

## 🚀 Hoja de Ruta y Desarrollo Incremental

El proyecto se aborda mediante una estrategia modular dividida en cuatro etapas continuas:

1. **Levantamiento y Validación:** Diagnóstico detallado y validación técnica del estado actual del laboratorio.
2. **Definición de Arquitectura:** Diseño de la capa de control, requerimientos de integración y especificación de modelos de datos.
3. **Despliegue de MVPs:** Desarrollo iterativo por módulos, ejecuciones de prueba y validación con usuarios clave.
4. **Operación en Producción:** Despliegue definitivo, migración de componentes y gobernanza activa de la infraestructura.

## 🎯 Objetivo Institucional

Convertir los recursos físicos fragmentados de **SavIA Lab** en un entorno de infraestructura institucional único, donde cada recurso de hardware, usuario, proyecto, dataset y ejecución pueda ser identificado, gobernado, monitoreado y auditado desde un único sistema central.
