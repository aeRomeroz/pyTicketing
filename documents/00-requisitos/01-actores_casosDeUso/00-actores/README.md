<div align="right">

[![](https://img.shields.io/badge/-Inicio-0A3B64?style=for-the-badge&logo=github&logoColor=white)](/README.md)
[![](https://img.shields.io/badge/-Modelo_del_Dominio-0A3B64?style=for-the-badge&logo=drawio&logoColor=white)](/documents/00-requisitos/00-modeloDelDominio/README.md)
[![](https://img.shields.io/badge/-Actores_Y_Casos_de_Uso-0A3B64?style=for-the-badge&logo=use-case&logoColor=white)](/documents/00-requisitos/01-actores_casosDeUso/00-actores/README.md)
[![](https://img.shields.io/badge/-Diagramas_de_Contexto-0A3B64?style=for-the-badge&logo=flowchart&logoColor=white)](/documents/00-requisitos/01-actores_casosDeUso/02-diagramaDeContexto/README.md)
[![](https://img.shields.io/badge/-Detalle_de_Casos_de_Uso-0A3B64?style=for-the-badge&logo=notepad&logoColor=white)](/documents/00-requisitos/01-actores_casosDeUso/04-detalladoCasosDeUso/README.md)
[![](https://img.shields.io/badge/-Prototipos-0A3B64?style=for-the-badge&logo=figma&logoColor=white)](/documents/00-requisitos/01-actores_casosDeUso/05-prototipadoCasosDeUso/README.md)
[![](https://img.shields.io/badge/-Priorización-0A3B64?style=for-the-badge&logo=priority&logoColor=white)](/documents/00-requisitos/01-actores_casosDeUso/03-priorizaciónCasosDeUso/README.md)

</div>

# Casos de Uso

## Actores y casos de uso identificados

Los actores identificados para el sistema **pyTicketing** son:

- **Administrador**: responsable de la gestión de usuarios del sistema (crear, consultar, editar, desactivar, reactivar).
- **Supervisor**: encargado de la gestión operativa de plazas, máquinas, asignaciones, cierre de caja y reembolsos.
- **Taquillero**: responsable del registro de ventas, anulaciones y consolidación del cierre de caja.
- **Motorario**: encargado del reporte de tickets recibidos en su máquina para el control de aforo y uso.

<div align=center>

| **Administrador** | **Supervisor** | **Taquillero** | **Motorario** |
| :---: | :---: | :---: | :---: |
| ![](/images/00-requisitos/01-actores_casosDeUso/01-casosDeUso/Administrador/CdUAdministrador.svg) | [Ver Diagrama General de Casos de Uso del Supervisor](/images/00-requisitos/01-actores_casosDeUso/00-actores/Supervisor/DdCdU-supervisor-general.svg) | ![](/images/00-requisitos/01-actores_casosDeUso/00-actores/Taquillero/DdCdU-taquillero.svg) | ![](/images/00-requisitos/01-actores_casosDeUso/00-actores/Motorario/DdCdU-motorario.svg) |
| [Código fuente](/UML/00-requisitos/01-actores_casosDeUso/00-actores/Administrador/DdCdU-administrador.puml) | [Código fuente](/UML/00-requisitos/01-actores_casosDeUso/00-actores/Supervisor/DdCdU-supervisor.puml) | [Código fuente](/UML/00-requisitos/01-actores_casosDeUso/00-actores/Taquillero/DdCdU-taquillero.puml) | [Código fuente](/UML/00-requisitos/01-actores_casosDeUso/00-actores/Motorario/DdCdU-motorario.puml) |

> Debido a la amplitud de responsabilidades operativas, el actor **Supervisor** se ha estructurado en **tres diagramas independientes** según su área funcional.

| Área funcional | Diagrama | Código (.puml) |
| :--- | :---: | :--- |
| **Gestión de Plazas** | <div align="center">![](/images/00-requisitos/01-actores_casosDeUso/00-actores/Supervisor/Plaza/DdCdU-supervisor-gestionDePlazas.svg)</div> | [Ver código](/UML/00-requisitos/01-actores_casosDeUso/00-actores/Supervisor/Plaza/DdCdU-supervisor-gestionDePlaza.puml) |
| **Gestión de Máquinas** | <div align="center">![](/images/00-requisitos/01-actores_casosDeUso/00-actores/Supervisor/Maquina/DdCdU-supervisor-gestionDeMaquinas.svg)</div> | [Ver código](/UML/00-requisitos/01-actores_casosDeUso/00-actores/Supervisor/Maquina/DdCdU-supervisor-gestionDeMaquinas.puml) |
| **Gestión de Ventas** | <div align="center">![](/images/00-requisitos/01-actores_casosDeUso/00-actores/Supervisor/Venta/DdCdU-supervisor-gestionDeVentas.svg)</div> | [Ver código](/UML/00-requisitos/01-actores_casosDeUso/00-actores/Supervisor/Venta/DdCdU-supervisor-gestionDeVentas.puml) |

</div>

---

## Diagramas de contexto

El diagrama de contexto representa el entorno operativo y la navegación entre estados en el sistema, consolidando los flujos permitidos y las transiciones de estado de todos los actores en un único diseño global.

<div align=center>

| **Diagrama de Contexto Global del Sistema** |
| :---: |
| ![](/images/00-requisitos/01-actores_casosDeUso/02-diagramaDeContexto/diagrama-de-contexto-global.svg) |
| [Ver código](/UML/00-requisitos/01-actores_casosDeUso/02-diagramaDeContexto/diagrama-de-contexto-global.puml) |

</div>

---

## Detalle de Casos de Uso

A continuación se presentan los diagramas detallados (máquinas de estados) para los casos de uso identificados, organizados por actor y área funcional.

### Supervisor — Gestión de Plazas

| CRUD de Plazas | Asignaciones |
| :--- | :--- |
| [registrarPlaza()](/documents/00-requisitos/01-actores_casosDeUso/01-casosDeUso/Supervisor/Plaza/README.md#registrar-plaza) | [asignarMaquinaAPlaza()](/documents/00-requisitos/01-actores_casosDeUso/01-casosDeUso/Supervisor/Plaza/README.md#asignar-máquina-a-plaza) |
| [consultarPlaza()](/documents/00-requisitos/01-actores_casosDeUso/01-casosDeUso/Supervisor/Plaza/README.md#consultar-plaza) | [desasignarMaquinaDePlaza()](/documents/00-requisitos/01-actores_casosDeUso/01-casosDeUso/Supervisor/Plaza/README.md#desasignar-máquina-de-plaza) |
| [editarPlaza()](/documents/00-requisitos/01-actores_casosDeUso/01-casosDeUso/Supervisor/Plaza/README.md#editar-plaza) | [asignarTaquilleroAPlaza()](/documents/00-requisitos/01-actores_casosDeUso/01-casosDeUso/Supervisor/Plaza/README.md#asignar-taquillero-a-plaza) |
| [darDeBajaPlaza()](/documents/00-requisitos/01-actores_casosDeUso/01-casosDeUso/Supervisor/Plaza/README.md#dar-de-baja-plaza) | [desasignarTaquilleroDePlaza()](/documents/00-requisitos/01-actores_casosDeUso/01-casosDeUso/Supervisor/Plaza/README.md#desasignar-taquillero-de-plaza) |
| [reactivarPlaza()](/documents/00-requisitos/01-actores_casosDeUso/01-casosDeUso/Supervisor/Plaza/README.md#reactivar-plaza) | |

---

## Totales por actor:

- **Administrador:** 5 casos de uso
- **Supervisor:** 18 casos de uso (Plazas: 9, Máquinas: 6, Ventas: 3)
- **Taquillero:** 3 casos de uso
- **Motorario:** 1 caso de uso
- **TOTAL:** 27 casos de uso identificados
