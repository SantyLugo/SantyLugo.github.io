# 🚀 Proyectos SavIA Lab

Este directorio centraliza los proyectos de investigación aplicada, desarrollo de infraestructura e iniciativas de Inteligencia Artificial ejecutados por el equipo interno de **SavIA Lab** e integrados con la plataforma **SavIA Admin**.

---

## 🎯 Alcance

Albergar el código fuente, la documentación técnica y las configuraciones de despliegue de los proyectos institucionales, herramientas internas y servicios de IA desarrollados en el laboratorio.

## 📂 Estructura Sugerida

Cada proyecto debe alojarse en su propia carpeta siguiendo la convención `[Tipo]_[Nombre_Proyecto]` (ej. `infra_monitoring_cluster` o `ia_llm_finetuning`):

```text
proyectos_savIA_lab/
└── [Nombre_Proyecto]/
    ├── docs/         # Arquitectura, diagramas y especificaciones
    ├── src/          # Código fuente, microservicios o pipelines de IA
    ├── deploy/       # Dockerfiles, manfiestos o scripts de Slurm (.sbatch)
    └── README.md     # Objetivos del proyecto, responsables y guía de uso
