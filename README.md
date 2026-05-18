# 📋 GitHub Templates

Repositorio de templates reutilizables para proyectos GitHub del equipo: issues, pull requests y automatizaciones con GitHub Actions.

> Diseñados para ahorrar tiempo, estandarizar la comunicación y mantener el tablero Kanban siempre actualizado.

---

## 📁 Contenido

```
.
├── ISSUE_TEMPLATE/
│   ├── config.yml              # Configuración del selector de templates
│   ├── bug_report.md           # 🐛 Reporte de bug con severidad y entorno
│   ├── feature_request.md      # 🚀 Solicitud de funcionalidad con criterios de aceptación
│   ├── tarea_general.md        # 📝 Tarea con tipo y estimación de esfuerzo
│   ├── question.md             # ❓ Pregunta o duda técnica
│   └── security.md             # 🔒 Vulnerabilidad de seguridad
├── workflow/
│   └── auto-fechas.yml         # ⚙️ GitHub Action: fecha automática en issues
└── pull_request_template.md    # Template para Pull Requests
```

---

## 🚀 Cómo usar este repositorio

### Opción A — Copiar los archivos a tu repositorio

1. Clona o descarga este repositorio.
2. Copia la carpeta `ISSUE_TEMPLATE/` y el archivo `pull_request_template.md` a la raíz de tu repositorio (o dentro de `.github/`).
3. Copia `workflow/auto-fechas.yml` dentro de `.github/workflows/` de tu repositorio.
4. Haz commit y push. GitHub detectará los templates automáticamente.

### Opción B — Usar `.github` como repositorio central (recomendado para organizaciones)

Si tu organización tiene un repositorio especial llamado `.github`, puedes añadir estos templates ahí y estarán disponibles para todos los repositorios de la organización que no tengan sus propios templates.

```
organización/.github/
├── ISSUE_TEMPLATE/
│   └── ...
└── pull_request_template.md
```

> 📖 Más info: [Creating a default community health file](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file)

---

## 📌 Templates de Issues

### 🐛 Bug Report
Para reportar errores. Incluye:
- Pasos para reproducir y comportamiento esperado vs actual
- Tabla de entorno (OS, versión, navegador, JDK)
- Selector de **severidad** (Crítica / Alta / Media / Baja)

### 🚀 Feature Request
Para proponer nuevas funcionalidades. Incluye:
- Problema que resuelve + solución propuesta
- Alternativas consideradas
- Criterios de aceptación
- Selector de **prioridad**

### 📝 Tarea General
Para refactorizaciones, documentación, tests, configuración, etc. Incluye:
- Tipo de tarea (refactor, docs, tests, config, seguridad...)
- **Estimación de esfuerzo** (XS / S / M / L / XL)
- Dependencias entre issues

### ❓ Pregunta / Duda
Para dudas técnicas o de proceso que no encajan como bug ni feature. Evita que se abran bugs incorrectos solo para preguntar.

### 🔒 Vulnerabilidad de Seguridad
Para reportar problemas de seguridad de forma responsable. Incluye aviso para no publicar detalles sensibles y campo de severidad CVSS aproximada.

---

## 🔀 Template de Pull Request

El PR template incluye:
- Referencia al issue con palabras clave para automatizar el Kanban (`Closes #ID`)
- Tipo de cambio
- Sección de pruebas realizadas
- Checklist generalizado (sin referencias a proyectos concretos)

---

## ⚙️ Workflow: Fechas Automáticas

El workflow `auto-fechas.yml` añade automáticamente una marca de tiempo a cada issue al **abrirse** o **cerrarse**, usando la zona horaria `Atlantic/Canary`.

**Requisitos:**
- Copiar el archivo en `.github/workflows/auto-fechas.yml` de tu repositorio.
- El workflow usa `GITHUB_TOKEN` por defecto (no requiere configuración adicional).

**Resultado en el issue:**
```
🕒 Fecha de creación: 15/05/2025, 10:32

[resto del contenido del issue...]
```

---

## 🗂️ Integración con GitHub Projects (Kanban)

Para que el tablero Kanban se actualice automáticamente:

1. **Crea un proyecto** en GitHub Projects (vista tipo tablero).
2. **Añade los issues** al proyecto desde la barra lateral del issue.
3. **Vincula el PR al issue** usando `Closes #ID` en la descripción del PR.
4. **Activa reglas automáticas** en el proyecto:
   - Issue abierto → columna *Todo* o *In Progress*
   - PR fusionado → issue cerrado → columna *Done*

> Con este flujo, cerrar un PR mueve automáticamente el issue en el tablero sin intervención manual.

---

## 🤝 Contribuir

¿Quieres mejorar algún template o añadir uno nuevo?

1. Abre un issue usando el template **🚀 Solicitud de Funcionalidad** o **📝 Tarea General**.
2. Crea una rama descriptiva: `feat/template-release-notes` o `fix/bug-report-entorno`.
3. Abre un PR usando el template de PR y referencia el issue.

---

## 📄 Licencia

Este repositorio es de uso interno del equipo. Siéntete libre de adaptarlo a tus proyectos.
