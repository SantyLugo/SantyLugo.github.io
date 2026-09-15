# Guía de Ejecución: MVP 0, Baseline y Gap Analysis

Para ejecutar el **MVP 0**, levantar la **Línea Base (Baseline)** y realizar el **Gap Analysis** de SavIA Admin, debes estructurar un proceso técnico ordenado en tres etapas operativas:

## 1. Levantamiento de la Línea Base (Baseline)

Consiste en auditar la infraestructura física y lógica actual para mapear la capacidad real del laboratorio sin suposiciones:

* **Inventario de Cómputo y GPUs:** Registrar nodos, modelos de GPUs, VRAM disponible, CPU, RAM y estado operativo actual (servidores, workstations y clústeres).
* **Mapeo de Almacenamiento y Datos:** Catalogar volúmenes NFS, buckets S3, tamaño de *datasets* y la estructura actual de permisos en disco.
* **Identidad y Acceso:** Documentar la cantidad de usuarios activos, métodos de autenticación actuales (cuentas locales, SSH keys, LDAP/Keycloak) y privilegios asignados.
* **Orquestación y Observabilidad:** Identificar la versión/configuración existente de Slurm, scripts de *scheduling* informales y agentes activos de Prometheus.

## 2. Matriz de Gap Analysis (Análisis de Brecha)

Compara el diagnóstico del Baseline contra los requerimientos de la plataforma final para identificar qué falta construir o integrar:

| Dimensión | Estado Actual (Baseline) | Estado Deseado (SavIA Admin) | Brecha a Resolver (Gap) |
| :--- | :--- | :--- | :--- |
| **Gestión de Cómputo** | Equipos aislados, asignación manual de GPUs. | Clúster unificado bajo Slurm con trazabilidad por proyecto. | Crear la capa de control (API) que orqueste y consulte Slurm. |
| **Identidad (IAM)** | Usuarios locales y accesos desarticulados. | Autenticación centralizada y RBAC con Keycloak. | Diseñar el esquema de roles y conectar el backend de SavIA a Keycloak. |
| **Observabilidad** | Métricas locales o inexistentes de consumo de GPUs. | Telemetría en tiempo real con Prometheus y Grafana. | Desplegar exporters (ej. `nvidia_gpu_exporter`) en todos los nodos. |
| **Gobernanza de Datos** | Datasets duplicados en discos locales y NFS. | Catálogo de metadatos centralizado con control de acceso. | Implementar el servicio de indexación y registro de datasets. |

## 3. Consolidación de Resultados del MVP 0

El MVP 0 no es el software completo, sino la validación técnica y el marco de trabajo sobre el cual se construirá la plataforma. Los entregables clave son:

* **Matriz de Inventario Unificada:** Base de datos o JSON estructurado con el hardware y recursos reales mapeados.
* **Documento de Arquitectura de Integración (v1.0):** Diagrama detallado de las API y protocolos de comunicación entre SavIA Admin, Slurm, Keycloak y Prometheus.
* **PoC de Integración Mínima:** Prueba de concepto donde un usuario autenticado por Keycloak pueda enviar un *job* de prueba a Slurm y ver su consumo en un panel básico.
* **Informe de Hallazgos y Riesgos:** Lista priorizada de barreras técnicas identificadas para abordar en el desarrollo del MVP 1.
