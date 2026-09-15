# 📦 Software Externo

Este directorio centraliza las configuraciones, adaptadores, scripts de instalación, parches y componentes de terceros integrados dentro del ecosistema de **SavIA Admin** y **SavIA Lab**.

---

## 🎯 Alcance

Gestionar de forma trazable y versionada el software de código abierto o comercial que no es desarrollado internamente, pero que resulta esencial para la operación, observabilidad y orquestación de la infraestructura.

## 📂 Estructura Sugerida

Cada software o herramienta externa debe organizarse en una carpeta propia siguiendo la convención `[nombre_herramienta]`:

```text
software_externo/
└── [nombre_herramienta]/
    ├── config/       # Archivos de configuración (ej. slurm.conf, prometheus.yml)
    ├── patches/      # Modificaciones locales, parches o scripts de extensión
    ├── deploy/       # Manifestos de despliegue, Dockerfiles o Compose
    └── README.md     # Versión utilizada, licencias, propósito y guía de instalación
