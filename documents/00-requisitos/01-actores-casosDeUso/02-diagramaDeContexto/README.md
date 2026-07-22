<div align="center">

[![](https://img.shields.io/badge/-Inicio-111827?style=for-the-badge&logo=github&logoColor=white)](/README.md)
[![](https://img.shields.io/badge/-Modelo_del_Dominio-B03B00?style=for-the-badge&logo=drawio&logoColor=white)](/documents/00-requisitos/00-modeloDelDominio/README.md)
[![](https://img.shields.io/badge/-Actores_Y_Casos_de_Uso-B03B00?style=for-the-badge&logo=use-case&logoColor=white)](/documents/00-requisitos/01-actores-casosDeUso/00-actores/README.md)
[![](https://img.shields.io/badge/-Diagramas_de_Contexto-B03B00?style=for-the-badge&logo=flowchart&logoColor=white)](/documents/00-requisitos/01-actores-casosDeUso/02-diagramaDeContexto/README.md)
[![](https://img.shields.io/badge/-Detalle_de_Casos_de_Uso-B03B00?style=for-the-badge&logo=notepad&logoColor=white)](/documents/00-requisitos/01-actores-casosDeUso/04-detalladoCasosDeUso/README.md)
[![](https://img.shields.io/badge/-Análisis-B03B00?style=for-the-badge&logo=uml&logoColor=white)](/documents/01-analisis/casosDeUso/README.md)
[![](https://img.shields.io/badge/-Diseño-B03B00?style=for-the-badge&logo=uml&logoColor=white)](/documents/02-diseño/README.md)
[![](https://img.shields.io/badge/-Desarrollo-B03B00?style=for-the-badge&logo=code&logoColor=white)](/documents/03-desarrollo/README.md)

</div>

# Sistema de Gestión de Tickets > Requisitos > Diagrama de Contexto Global

## Información del artefacto

- **Proyecto**: Sistema de Control y Gestión Operativa de Tickets y Plazas
- **Fase RUP**: Inception (Inicio)
- **Versión**: 1.0
- **Fecha**: 2026-07-22
- **Autor**: Equipo de desarrollo
- **Cambios principales**: Estructuración del ciclo de vida global del sistema como máquina de estados finitos, estandarización de contenedores plurales (`-ABIERTO`) para listados y operativas in situ, y contenedores singulares (`-ABIERTA`/`-ABIERTO`) para la gestión individualizada.

## Introducción

Este documento presenta el **Diagrama de Contexto Global** del sistema. En él se modela el comportamiento dinámico del sistema como una máquina de estados finitos, detallando la secuencialidad de navegación entre módulos, las precondiciones operativas y el mapa de transiciones activadas por cada Caso de Uso.

## Propósito

- Presentar la perspectiva holística del comportamiento del sistema.
- Especificar la navegación mediante un flujo de estados declarativo e inequívoco.
- Hacer explícita la secuencia requerida para acceder a los distintos módulos operativos.
- Validar la consistencia conceptual entre los Casos de Uso y sus estados de destino.
- Garantizar la separación de responsabilidades entre el Menú Principal y los subdiagramas contenedores.

## Diagrama

<div align="center">

![Diagrama de Contexto Global](/images/00-requisitos/01-actores-casosDeUso/02-diagramaDeContexto/diagrama-de-contexto-global.svg)

*Código fuente: [diagrama-contexto-global.puml](/UML/00-requisitos/01-actores-casosDeUso/02-diagramaDeContexto/diagrama-de-contexto-global.puml)*

</div>

---

## Estados del sistema

| Estado | Descripción | Función principal |
| :--- | :--- | :--- |
| **`SESION_CERRADA`** | Estado inicial y final por defecto. | Punto de entrada antes de la autenticación de usuarios. |
| **`SISTEMA_DISPONIBLE`** | Hub/Menú principal de navegación. | Distribuye el flujo del sistema tras validar credenciales. |
| **`MAQUINAS_ABIERTO`** | Listado y catálogo general de máquinas. | Permite filtrar, dar de baja/reactivar y gestionar asignaciones de motorarios. |
| **`MAQUINA_ABIERTA`** | Ficha o formulario individual de máquina. | Permite consultar, registrar y editar la información específica de una máquina. |
| **`PLAZAS_ABIERTO`** | Listado y catálogo general de plazas. | Permite filtrar, dar de baja/reactivar y asignar/desasignar máquinas y taquilleros. |
| **`PLAZA_ABIERTA`** | Ficha o formulario individual de plaza. | Permite consultar, registrar y editar datos puntuales de una plaza. |
| **`USUARIOS_ABIERTO`** | Listado general de cuentas de usuario. | Permite filtrar, desactivar y reactivar cuentas activas/inactivas. |
| **`USUARIO_ABIERTO`** | Ficha de gestión de usuario. | Permite consultar, crear o editar perfiles e información de usuarios. |
| **`REPORTES_ABIERTO`** | Panel principal de reporte de boletaje. | Permite seleccionar u originar ciclos de reporte de tickets recibidos. |
| **`REPORTE_ABIERTO`** | Bucle operativo de carga de tickets. | Permite registrar tickets recibidos de motorarios hasta la finalización. |
| **`CAJA_ABIERTA`** | Panel de control de flujo de caja. | Permite revisar arqueos, diferencias y consolidar cierres contables. |
| **`VENTAS_ABIERTO`** | Módulo de terminal e historial de ventas. | Permite solicitar anulaciones, ejecutar anulaciones o autorizar reembolsos. |
| **`VENTA_ABIERTA`** | Formulario/Terminal de emisión. | Permite procesar y expedir nuevas ventas de tickets. |

---

## Transiciones principales

### Autenticación y Navegación Menú Central
- `iniciarSesion()`: **`SESION_CERRADA`** $\rightarrow$ **`SISTEMA_DISPONIBLE`**
- `cerrarSesion()`: **`SISTEMA_DISPONIBLE`** $\rightarrow$ **`SESION_CERRADA`**

### Acceso a Contenedores Módulos (`abrirX`)
- `abrirMaquinas()`: **`SISTEMA_DISPONIBLE`** $\rightarrow$ **`MAQUINAS_ABIERTO`**
- `abrirPlazas()`: **`SISTEMA_DISPONIBLE`** $\rightarrow$ **`PLAZAS_ABIERTO`**
- `abrirUsuarios()`: **`SISTEMA_DISPONIBLE`** $\rightarrow$ **`USUARIOS_ABIERTO`**
- `abrirReportes()`: **`SISTEMA_DISPONIBLE`** $\rightarrow$ **`REPORTES_ABIERTO`**
- `abrirCaja()`: **`SISTEMA_DISPONIBLE`** $\rightarrow$ **`CAJA_ABIERTA`**
- `abrirVentas()`: **`SISTEMA_DISPONIBLE`** $\rightarrow$ **`VENTAS_ABIERTO`**

### Transiciones Internas de Módulo

#### Módulo Máquinas
- **Acceso a Ficha**: `consultarMaquina()`, `editarMaquina()`, `registrarMaquina()` ($\rightarrow$ **`MAQUINA_ABIERTA`**)
- **Operaciones In Situ / Retorno**: `darDeBajaMaquina()`, `reactivarMaquina()`, `asignarMotorarioAMaquina()`, `desasignarMotorarioDeMaquina()` ($\rightarrow$ **`MAQUINAS_ABIERTO`**)

#### Módulo Plazas
- **Acceso a Ficha**: `consultarPlaza()`, `editarPlaza()`, `registrarPlaza()` ($\rightarrow$ **`PLAZA_ABIERTA`**)
- **Operaciones In Situ / Retorno**: `darDeBajaPlaza()`, `reactivarPlaza()`, `asignarMaquinaAPlaza()`, `desasignarMaquinaDePlaza()`, `asignarTaquilleroAPlaza()`, `desasignarTaquilleroDePlaza()` ($\rightarrow$ **`PLAZAS_ABIERTO`**)

#### Módulo Usuarios
- **Acceso a Ficha**: `consultarUsuario()`, `editarUsuario()`, `crearUsuario()` ($\rightarrow$ **`USUARIO_ABIERTO`**)
- **Operaciones In Situ**: `desactivarUsuario()`, `reactivarUsuario()` ($\rightarrow$ **`USUARIOS_ABIERTO`**)

#### Módulo Reportes
- **Inicio de proceso**: `iniciarReporte()` ($\rightarrow$ **`REPORTE_ABIERTO`**)
- **Cierre de ciclo**: `finalizarReporte()` ($\rightarrow$ **`REPORTES_ABIERTO`**)

#### Módulo Caja
- **Gestión / Auditoría**: `revisarCierreDeCaja()`, `consolidarCierreDeCaja()` ($\rightarrow$ **`CAJA_ABIERTA`**)

#### Módulo Ventas
- **Emisión**: `registrarVenta()` ($\rightarrow$ **`VENTA_ABIERTA`**)
- **Aprobaciones / Solicitudes**: `solicitarAnulacionVenta()`, `anularVenta()`, `autorizarReembolso()` ($\rightarrow$ **`VENTAS_ABIERTO`**)

### Retorno Unificado al Menú Principal
El retorno desde cualquiera de los contenedores hacia el Hub principal se completa mediante un único caso de uso unificado:
- `completarGestion()`: **`[MODULO]_ABIERTO`** $\rightarrow$ **`SISTEMA_DISPONIBLE`**

---

## Precondiciones visuales

1. **Autenticación Obligatoria**: Ningún actor puede acceder a los contenedores operacionales sin transitar previamente por el proceso `iniciarSesion()`.
2. **Navegación Centralizada**: Todos los accesos principales a los módulos del dominio derivan directamente de **`SISTEMA_DISPONIBLE`**.
3. **Consistencia de Retorno**: Todo ciclo de trabajo finalizado dentro de un módulo devuelve el control al catálogo general o, mediante `completarGestion()`, al Menú Principal.

---

## Características del diseño

- **Patrón Hub & Spoke Centralizado**: El estado **`SISTEMA_DISPONIBLE`** actúa como el núcleo orquestador que garantiza el aislamiento entre las distintas áreas operativas.
- **Diferenciación Semántica de Estados**:
  - **Plural (`-ABIERTO`)**: Representa estados contenedores de conjunto, diseñados para acciones sobre listados o tablas.
  - **Singular (`-ABIERTA` / `-ABIERTO`)**: Representa la apertura formal de la entidad para modificación o consulta detallada.
- **Desacoplamiento Tecnológico**: El diagrama abstrae completamente detalles de implementación web o bases de datos, centrándose de forma estricta en la semántica del negocio.

---

## Referencias

- [Modelo del dominio](/documents/00-requisitos/00-modeloDelDominio/README.md) — Entidades del negocio.
- [Actores y Casos de Uso](/documents/00-requisitos/01-actores-casosDeUso/00-actores/README.md) — Identificación de perfiles operacionales.