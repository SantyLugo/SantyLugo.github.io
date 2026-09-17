# 🔀 Flujo de Trabajo GitFlow en SavIA Lab

Para mantener la estabilidad del código, organizar las entregas y coordinar los desarrollos de **SavIA Admin**, el equipo utiliza el modelo de ramificación **GitFlow**.

---

## 📊 Diagrama General del Flujo

![Diagrama GitFlow](./assets/gitflow_diagram.png)

---

## 🌿 Ramas Principales (Larga Duración)

Son las dos ramas permanentes del repositorio:

* **`main` (Azul claro):** Refleja el estado de producción. Código 100% estable, probado y empaquetado bajo versiones semánticas (ej. `v0.1`, `v0.2`, `v1.0`).
* **`develop` (Púrpura):** Rama de integración continua. Contiene los últimos cambios aprobados que se incluirán en la siguiente versión oficial.

---

## 🚀 Ramas Auxiliares (Temporales)

Nacen para un propósito específico y se eliminan tras ser integradas:

### 🟢 `feature/*` (Verde) — Funcionalidades
* **Origen:** `develop` | **Destino:** `develop`
* **Uso:** Desarrollo de nuevos módulos, tareas o componentes (ej. integrador de Slurm, nuevo dashboard).
* **Convención:** `feature/nombre-de-la-tarea`

### 🔵 `release/*` (Cian) — Preparación de Versión
* **Origen:** `develop` | **Destino:** `main` y `develop`
* **Uso:** Estabilización previa al despliegue a producción (pruebas finales, corrección de detalles menores y actualización de documentación).
* **Convención:** `release/vX.Y.Z`

### 🟠 `hotfix/*` (Naranja) — Parches de Emergencia
* **Origen:** `main` | **Destino:** `main` y `develop`
* **Uso:** Solución rápida para errores críticos detectados en producción que no pueden esperar al siguiente ciclo de desarrollo.
* **Convención:** `hotfix/descripcion-error`

---

## 🔄 Flujo de Trabajo Paso a Paso

1. **Iniciar un desarrollo:**
   Crea tu rama desde `develop`:
   `git checkout -b feature/modulo-auth develop`

2. **Finalizar y solicitar revisión:**
   Al terminar tu trabajo, abre un **Pull Request (PR)** con destino a `develop` para revisión de código (*Code Review*).

3. **Consolidar una versión:**
   Cuando `develop` tenga suficientes avances, el administrador crea la rama `release/v1.0`. Al validar las pruebas, esta se fusiona a `main` (agregando la etiqueta `v1.0`) y se actualiza de vuelta en `develop`.

4. **Atender emergencias:**
   Si surge un fallo crítico en producción, se crea un `hotfix` desde el Tag actual de `main`, se corrige el error y se fusiona de inmediato tanto en `main` (generando una nueva versión como `v0.2`) como en `develop`.

---

## ⚠️ Reglas de Oro

* **Cero Commits Directos:** Prohibido hacer `git push` directo sobre `main` o `develop`. Todo cambio entra por Pull Request.
* **Commits Limpios:** Haz cambios atómicos con mensajes claros. Usa `Amend` en local antes de subir tu rama si necesitas corregir tu último commit.
* **Tags obligatorios:** Cada merge a `main` debe llevar su correspondiente etiqueta de versión (`v0.1`, `v0.2`, `v1.0`).
