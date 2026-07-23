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

# Actores y Casos de Uso

## Actores e Identificación del Sistema

El sistema **pyTicketing** organiza sus funcionalidades en torno a cuatro actores operativos principales, cada uno con responsabilidades y niveles de acceso claramente acotados:

- **Administrador**: Responsable de la gestión de la seguridad del sistema y de las cuentas de usuario (alta, edición, consulta, desactivación y reactivación).
- **Supervisor**: Encargado de la supervisión operacional y logística. Gestiona plazas, máquinas, asignaciones de personal/equipos, auditoría de cierres de caja y autorización de excepciones (anulaciones/reembolsos).
- **Taquillero**: Operador de terminal de venta en plaza, responsable del cobro/expedición de tickets, solicitud de anulaciones y declaración de cierre de caja de su turno.
- **Motorario**: Operador de máquina/atracción responsable de la validación de boletos recibidos y del reporte de conteo al finalizar su turno.

---

## Diagramas de Casos de Uso por Actor

<div align="center">

| **Administrador** | **Supervisor** | **Taquillero** | **Motorario** |
| :---: | :---: | :---: | :---: |
| ![](/images/00-requisitos/01-actores-casosDeUso/00-actores/Administrador/DdCdU-administrador.svg) | [Ver Diagrama General Supervisor](/images/00-requisitos/01-actores-casosDeUso/00-actores/Supervisor/DdCdU-supervisor-general.svg) | ![](/images/00-requisitos/01-actores-casosDeUso/00-actores/Taquillero/DdCdU-taquillero.svg) | ![](/images/00-requisitos/01-actores-casosDeUso/00-actores/Motorario/DdCdU-motorario.svg) |
| [Código fuente](/UML/00-requisitos/01-actores-casosDeUso/00-actores/Administrador/DdCdU-administrador.puml) | [Código fuente](/UML/00-requisitos/01-actores-casosDeUso/00-actores/Supervisor/DdCdU-supervisor.puml) | [Código fuente](/UML/00-requisitos/01-actores-casosDeUso/00-actores/Taquillero/DdCdU-taquillero.puml) | [Código fuente](/UML/00-requisitos/01-actores-casosDeUso/00-actores/Motorario/DdCdU-motorario.puml) |

</div>

> Debido a la amplitud de responsabilidades operativas, las funciones del **Supervisor** se han desglosado en diagramas especializados por módulo operativo:

<div align="center">

| Área funcional | Diagrama | Código (.puml) |
| :--- | :---: | :--- |
| **Gestión de Plazas** | ![](/images/00-requisitos/01-actores-casosDeUso/00-actores/Supervisor/Plaza/DdCdU-supervisor-gestionDePlazas.svg) | [Ver código](/UML/00-requisitos/01-actores-casosDeUso/00-actores/Supervisor/Plaza/DdCdU-supervisor-gestionDePlazas.puml) |
| **Gestión de Máquinas** | ![](/images/00-requisitos/01-actores-casosDeUso/00-actores/Supervisor/Maquina/DdCdU-supervisor-gestionDeMaquinas.svg) | [Ver código](/UML/00-requisitos/01-actores-casosDeUso/00-actores/Supervisor/Maquina/DdCdU-supervisor-gestionDeMaquinas.puml) |
| **Gestión de Ventas y Caja** | ![](/images/00-requisitos/01-actores-casosDeUso/00-actores/Supervisor/Venta/DdCdU-supervisor-gestionDeVentas.svg) | [Ver código](/UML/00-requisitos/01-actores-casosDeUso/00-actores/Supervisor/Venta/DdCdU-supervisor-gestionDeVentas.puml) |

</div>

---

## Diagrama de Contexto Global

El **Diagrama de Contexto Global** orquesta el ciclo de vida completo del sistema como una máquina de estados finitos, definiendo la navegación centralizada desde `SISTEMA_DISPONIBLE` hacia cada uno de los contenedores operativos (`abrirX`).

<div align="center">

| **Diagrama de Contexto Global del Sistema** |
| :---: |
| ![](/images/00-requisitos/01-actores-casosDeUso/02-diagramaDeContexto/diagrama-de-contexto-global.svg) |
| [Ver código PlantUML](/UML/00-requisitos/01-actores-casosDeUso/02-diagramaDeContexto/diagrama-de-contexto-global.puml) |

</div>

---

## Índice Detallado de Casos de Uso

A continuación se listan las especificaciones y máquinas de estado individuales agrupadas por módulo operativo y responsabilidad:

### 1. Módulo Administrador (Usuarios)
- [`crearUsuario()`](/documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Administrador/README.md#crear-usuario)
- [`consultarUsuario()`](/documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Administrador/README.md#consultar-usuario)
- [`editarUsuario()`](/documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Administrador/README.md#editar-usuario)
- [`desactivarUsuario()`](/documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Administrador/README.md#desactivar-usuario)
- [`reactivarUsuario()`](/documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Administrador/README.md#reactivar-usuario)

### 2. Módulo Supervisor — Gestión de Plazas
| Operaciones CRUD de Plaza | Asignaciones de Recursos |
| :--- | :--- |
| [`registrarPlaza()`](/documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Supervisor/Plaza/README.md#registrar-plaza) | [`asignarMaquinaAPlaza()`](/documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Supervisor/Plaza/README.md#asignar-máquina-a-plaza) |
| [`consultarPlaza()`](/documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Supervisor/Plaza/README.md#consultar-plaza) | [`desasignarMaquinaDePlaza()`](/documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Supervisor/Plaza/README.md#desasignar-máquina-de-plaza) |
| [`editarPlaza()`](/documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Supervisor/Plaza/README.md#editar-plaza) | [`asignarTaquilleroAPlaza()`](/documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Supervisor/Plaza/README.md#asignar-taquillero-a-plaza) |
| [`darDeBajaPlaza()`](/documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Supervisor/Plaza/README.md#dar-de-baja-plaza) | [`desasignarTaquilleroDePlaza()`](/documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Supervisor/Plaza/README.md#desasignar-taquillero-de-plaza) |
| [`reactivarPlaza()`](/documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Supervisor/Plaza/README.md#reactivar-plaza) | |

### 3. Módulo Supervisor — Gestión de Máquinas
| Operaciones CRUD de Máquina | Asignación de Operadores |
| :--- | :--- |
| [`registrarMaquina()`](/documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Supervisor/Maquina/README.md#registrar-máquina) | [`asignarMotorarioAMaquina()`](/documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Supervisor/Maquina/README.md#asignar-motorario-a-máquina) |
| [`consultarMaquina()`](/documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Supervisor/Maquina/README.md#consultar-máquina) | [`desasignarMotorarioDeMaquina()`](/documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Supervisor/Maquina/README.md#desasignar-motorario-de-máquina) |
| [`editarMaquina()`](/documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Supervisor/Maquina/README.md#editar-máquina) | |
| [`darDeBajaMaquina()`](/documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Supervisor/Maquina/README.md#dar-de-baja-máquina) | |
| [`reactivarMaquina()`](/documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Supervisor/Maquina/README.md#reactivar-máquina) | |

### 4. Módulo Operativo de Ventas y Excepciones (Taquillero / Supervisor)
- [`registrarVenta()`](/documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Taquillero/README.md#registrar-venta) *(Taquillero)*
- [`solicitarAnulacionVenta()`](/documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Taquillero/README.md#solicitar-anulación-de-venta) *(Taquillero)*
- [`anularVenta()`](/documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Supervisor/Venta/README.md#anular-venta) *(Supervisor)*
- [`autorizarReembolso()`](/documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Supervisor/Venta/README.md#autorizar-reembolso) *(Supervisor)*

### 5. Módulo Cierre de Caja y Auditoría
- [`revisarCierreDeCaja()`](/documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Supervisor/Caja/README.md#revisar-cierre-de-caja) *(Supervisor)*
- [`consolidarCierreDeCaja()`](/documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Supervisor/Caja/README.md#consolidar-cierre-de-caja) *(Supervisor)*

### 6. Módulo Reportes de Motorario
- [`iniciarReporte()`](/documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Motorario/README.md#iniciar-reporte) *(Motorario)*
- [`reportarTicketsRecibidos()`](/documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Motorario/README.md#reportar-tickets-recibidos) *(Motorario)*
- [`finalizarReporte()`](/documents/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Motorario/README.md#finalizar-reporte) *(Motorario)*

---

## Totales por Actor y Resumen del Dominio

| Actor | Áreas Funcionales | N° Casos de Uso |
| :--- | :--- | :---: |
| **Administrador** | Gestión de Usuarios y Accesos | **5** |
| **Supervisor** | Plazas (9), Máquinas (7), Excepciones/Caja (4) | **20** |
| **Taquillero** | Ventas y Solicitudes | **2** |
| **Motorario** | Rendición y Conteo de Boletos | **3** |
| **TOTAL** | **4 Actores Principales** | **30 Casos de Uso** |