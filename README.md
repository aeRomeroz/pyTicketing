<h1 align="center">pyTicketing - Sistema de Gestión de Tickets</h1>

<h4 align="center">Control integral para parques itinerantes: desde la taquilla hasta la atracción.
</h2>

<div align="center">

[![](https://img.shields.io/badge/-Inicio-111827?style=for-the-badge&logo=github&logoColor=white)](/README.md)
[![](https://img.shields.io/badge/-Modelo_del_Dominio-B03B00?style=for-the-badge&logo=drawio&logoColor=white)](/documents/00-requisitos/00-modeloDelDominio/README.md)
[![](https://img.shields.io/badge/-Actores_Y_Casos_de_Uso-B03B00?style=for-the-badge&logo=use-case&logoColor=white)](/documents/00-requisitos/01-actores-casosDeUso/00-actores/README.md)
[![](https://img.shields.io/badge/-Diagramas_de_Contexto-B03B00?style=for-the-badge&logo=flowchart&logoColor=white)](/documents/00-requisitos/01-actores-casosDeUso/02-diagramaDeContexto/README.md)
[![](https://img.shields.io/badge/-Detalle_de_Casos_de_Uso-B03B00?style=for-the-badge&logo=notepad&logoColor=white)](/documents/00-requisitos/01-actores-casosDeUso/04-detalladoCasosDeUso/README.md)
[![](https://img.shields.io/badge/-Análisis-B03B00?style=for-the-badge&logo=uml&logoColor=white)](/documents/01-analisis/casosDeUso/README.md)
[![](https://img.shields.io/badge/-Diseño-B03B00?style=for-the-badge&logo=uml&logoColor=white)](/documents/02-diseño/README.md)
[![](https://img.shields.io/badge/-Desarrollo-B03B00?style=for-the-badge&logo=code&logoColor=white)](/documents/03-desarrollo/README.md)

[![Methodology](https://img.shields.io/badge/Methodology-RUP-0A3B64?style=for-the-badge)](https://en.wikipedia.org/wiki/Rational_Unified_Process)
[![Stage](https://img.shields.io/badge/Stage-Requirements-success?style=for-the-badge)](./documents/00-requisitos/)
[![UML](https://img.shields.io/badge/Diagrams-PlantUML-orange?style=for-the-badge)](http://plantuml.com)

</div>


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

### [➔ Ver Detalle Completo de Casos de Uso](./documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/README.md)

| Área / Actor | Casos de Uso | Documentación |
| :--- | :---: | :---: |
| **Administración de Usuarios** | 5 | [📂 Ver](./documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Administrador/README.md) |
| **Gestión de Plazas (Supervisor)** | 9 | [📂 Ver](./documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Supervisor/Plaza/README.md) |
| **Gestión de Máquinas (Supervisor)** | 6 | [📂 Ver](./documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Supervisor/Maquina/README.md) |
| **Gestión de Ventas (Supervisor)** | 3 | [📂 Ver](./documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Supervisor/Venta/README.md) |
| **Operaciones de Taquilla** | 3 | [📂 Ver](./documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Taquillero/README.md) |
| **Reportes de Atracción (Motorario)** | 1 | [📂 Ver](./documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Motorario/README.md) |

---

## 🛠️ Estructura de Documentación

El repositorio está organizado siguiendo el flujo de trabajo de RUP:

```bash
pyTicketing/
├── 📄 README.md                # Presentación del proyecto
├── 📂 documents/
│   └── 📂 00-requisitos/       # Artefactos de la fase de requisitos
│       ├── 📂 00-modeloDelDominio/
│       └── 📂 01-actores-casosDeUso/
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
- [📊 Diagramas de Contexto](./documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/README.md#diagramas-de-contexto)
- [📐 Casos de Uso Detallados](./documents/00-requisitos/01-actores-casosDeUso/04-detalladoCasosDeUso/README.md)

---
<p align="center">
  Desarrollado con rigor técnico bajo los estándares de Ingeniería del Software.
</p>
