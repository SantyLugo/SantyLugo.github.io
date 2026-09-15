# 🛠️ Software Interno

Este directorio alberga los módulos centralizados, microservicios, APIs, interfaces y herramientas administrativas desarrolladas a medida para dar vida a la capa de control de **SavIA Admin** y la operación técnica de **SavIA Lab**.

---

## 🎯 Alcance

Centralizar el código fuente de los sistemas de producción interna que componen la plataforma SavIA Admin, garantizando su mantenibilidad, arquitectura modular y capacidad de integración con los servicios del laboratorio.

## 📂 Estructura Sugerida

Cada componente o microservicio debe alojarse en su propio subdirectorio siguiendo la convención `[modulo_o_servicio]` (ej. `core_api`, `slurm_adapter`, `admin_dashboard`):

```text
software_interno/
└── [nombre_modulo_o_servicio]/
    ├── docs/         # Especificaciones de la API (OpenAPI/Swagger) y arquitectura
    ├── src/          # Código fuente principal de la aplicación/servicio
    ├── tests/        # Pruebas unitarias, de integración y cobertura
    ├── deploy/       # Dockerfiles, manifestos de despliegue o scripts de inicio
    └── README.md     # Descripción del servicio, variables de entorno y guía de ejecución
