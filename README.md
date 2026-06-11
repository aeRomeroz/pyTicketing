# 🎟️ pyTicketing — Sistema de Gestión de Tickets

> **Control integral para parques itinerantes: desde la taquilla hasta la atracción.**

[![Methodology](https://img.shields.io/badge/Methodology-RUP-0A3B64?style=for-the-badge)](https://en.wikipedia.org/wiki/Rational_Unified_Process)
[![Stage](https://img.shields.io/badge/Stage-Requirements-success?style=for-the-badge)](./documents/00-requisitos/)
[![UML](https://img.shields.io/badge/Diagrams-PlantUML-orange?style=for-the-badge)](http://plantuml.com)

**pyTicketing** es una solución técnica diseñada para la gestión operativa y financiera de parques de atracciones itinerantes. El sistema cubre todo el ciclo de vida del ticket, desde su emisión en taquilla hasta su validación en la atracción y el posterior cierre de caja.

---

## 🏗️ Metodología y Estado del Proyecto

Este proyecto se desarrolla siguiendo la metodología **RUP (Rational Unified Process)**, garantizando una aproximación disciplinada a la asignación de tareas y responsabilidades.

Actualmente, el proyecto se encuentra en la fase de **Requisitos**, con un enfoque exhaustivo en la identificación de actores y la definición detallada de casos de uso mediante diagramas de estados.

---

## 👥 Actores del Sistema

El sistema interactúa con cuatro roles principales, cada uno con responsabilidades claramente definidas:

| Actor | Responsabilidad Principal |
| :--- | :--- |
| **🔑 Administrador** | Gestión de identidades y accesos (Usuarios del sistema). |
| **👮 Supervisor** | Coordinación operativa de plazas, máquinas y control financiero. |
| **🎫 Taquillero** | Punto de venta: registro de transacciones y atención al público. |
| **🎡 Motorario** | Validación y control de aforo en las atracciones. |

---

## 📋 Resumen de Casos de Uso

Se han identificado un total de **27 casos de uso**, organizados para cubrir todas las necesidades operativas:

### [➔ Ver Detalle Completo de Casos de Uso](./documents/00-requisitos/01-actores_casosDeUso/01-casosDeUso/README.md)

| Área / Actor | Casos de Uso | Documentación |
| :--- | :---: | :---: |
| **Administración de Usuarios** | 5 | [📂 Ver](./documents/00-requisitos/01-actores_casosDeUso/01-casosDeUso/Administrador/README.md) |
| **Gestión de Plazas (Supervisor)** | 9 | [📂 Ver](./documents/00-requisitos/01-actores_casosDeUso/01-casosDeUso/Supervisor/Plaza/README.md) |
| **Gestión de Máquinas (Supervisor)** | 6 | [📂 Ver](./documents/00-requisitos/01-actores_casosDeUso/01-casosDeUso/Supervisor/Maquina/README.md) |
| **Gestión de Ventas (Supervisor)** | 3 | [📂 Ver](./documents/00-requisitos/01-actores_casosDeUso/01-casosDeUso/Supervisor/Venta/README.md) |
| **Operaciones de Taquilla** | 3 | [📂 Ver](./documents/00-requisitos/01-actores_casosDeUso/01-casosDeUso/Taquillero/README.md) |
| **Reportes de Atracción (Motorario)** | 1 | [📂 Ver](./documents/00-requisitos/01-actores_casosDeUso/01-casosDeUso/Motorario/README.md) |

---

## 🛠️ Estructura de Documentación

El repositorio está organizado siguiendo el flujo de trabajo de RUP:

```bash
pyTicketing/
├── 📄 README.md                # Presentación del proyecto
├── 📂 documents/
│   └── 📂 00-requisitos/       # Artefactos de la fase de requisitos
│       ├── 📂 00-modeloDelDominio/
│       └── 📂 01-actores_casosDeUso/
├── 📂 images/                  # Diagramas exportados (SVG)
└── 📂 UML/                     # Código fuente de diagramas (PlantUML)
```

### 🎨 Convención de Diagramas
Los diagramas detallados utilizan una convención de colores para facilitar su lectura:
- **🟢 Verde:** Flujo principal / Éxito.
- **🔴 Rojo:** Flujo alternativo / Cancelación.
- **🔵 Azul:** Punto de finalización.

---

## 🔗 Enlaces Rápidos

- [📖 Glosario de Términos](./documents/00-requisitos/00-modeloDelDominio/Glosario/README.md)
- [🗺️ Modelo del Dominio](./documents/00-requisitos/00-modeloDelDominio/README.md)
- [📊 Diagramas de Contexto](./documents/00-requisitos/01-actores_casosDeUso/01-casosDeUso/README.md#diagramas-de-contexto)
- [📐 Casos de Uso Detallados](./documents/00-requisitos/01-actores_casosDeUso/04-detalladoCasosDeUso/README.md)

---
<p align="center">
  Desarrollado con rigor técnico bajo los estándares de Ingeniería del Software.
</p>
