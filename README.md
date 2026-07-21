<div align="center">

# pyTicketing - Sistema de Gestión de Tickets

#### Control integral para parques itinerantes: desde la taquilla hasta la atracción.

</div>

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

---

**pyTicketing** es una solución de ingeniería de software diseñada para la gestión operativa y financiera de parques de atracciones itinerantes. El sistema cubre todo el ciclo de vida del ticket: desde su emisión en taquilla hasta su validación en la atracción y el posterior cierre de caja.

---

## 🏗️ Metodología y Estado del Proyecto

Este proyecto se desarrolla siguiendo la metodología **RUP (Rational Unified Process)**, garantizando un enfoque riguroso en la definición de requisitos, análisis, diseño e implementación.

Actualmente, el proyecto se encuentra en la fase de **Requisitos**, enfocado en la identificación de actores, estructuración de casos de uso y definición conceptual del modelo del dominio.

---

## 👥 Actores del Sistema

El sistema define cuatro roles clave para cubrir el flujo operativo y contable:

| Actor | Responsabilidad Principal |
| :--- | :--- |
| **Administrador** | Gestión de identidades y accesos (usuarios del sistema). |
| **Supervisor** | Coordinación operativa de plazas, máquinas y control financiero. |
| **Taquillero** | Punto de venta: registro de transacciones y atención al público. |
| **Motorario** | Validación de tickets y control de aforo en las atracciones. |

---

## 📋 Resumen de Casos de Uso (27 Identificados)

Los requisitos funcionales están estructurados por módulo operativo:

| Área / Actor | Cantidad | Documentación |
| :--- | :---: | :---: |
| **Administración de Usuarios** | 5 | [📂 Ver Casos de Uso](./documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Administrador/README.md) |
| **Gestión de Plazas** *(Supervisor)* | 9 | [📂 Ver Casos de Uso](./documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Supervisor/Plaza/README.md) |
| **Gestión de Máquinas** *(Supervisor)* | 6 | [📂 Ver Casos de Uso](./documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Supervisor/Maquina/README.md) |
| **Gestión de Ventas** *(Supervisor)* | 3 | [📂 Ver Casos de Uso](./documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Supervisor/Venta/README.md) |
| **Operaciones de Taquilla** *(Taquillero)* | 3 | [📂 Ver Casos de Uso](./documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Taquillero/README.md) |
| **Reportes de Atracción** *(Motorario)* | 1 | [📂 Ver Casos de Uso](./documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Motorario/README.md) |

> ➔ [**Ver detalle completo de Casos de Uso**](./documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/README.md)

---

## 🛠️ Estructura de Documentación

El repositorio organiza sus artefactos garantizando la separación entre documentación, diagramas exportados y código fuente PlantUML:

```bash
pyTicketing/
├── 📄 README.md                 # Presentación principal del proyecto
├── 📂 documents/                 # Artefactos de las fases RUP
│   ├── 📂 00-requisitos/        # Requisitos, Modelo del Dominio y Casos de Uso
│   ├── 📂 01-analisis/          # Modelo de análisis
│   ├── 📂 02-diseño/            # Diseño de software y arquitectura
│   └── 📂 03-desarrollo/        # Código fuente e implementación
├── 📂 images/                   # Diagramas exportados en SVG
└── 📂 UML/                      # Código fuente de diagramas (PlantUML)