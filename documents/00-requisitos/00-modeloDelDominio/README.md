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

# Modelo del Dominio y Glosario de Términos

Este documento describe el modelo conceptual del dominio para el Sistema Gestionador de Tickets (pyTicketing). El modelo establece el vocabulario común y las relaciones fundamentales entre las entidades del negocio de ferias e instalaciones itinerantes, enfocándose en los conceptos esenciales de la generación, validación, recolección y trazabilidad financiera/operativa de tickets.

## Propósito
- Establecer un vocabulario común entre desarrolladores, supervisores y personal operativo.
- Definir las reglas de negocio para la emisión, validación, rendición de boletos y consolidación de ingresos.
- Servir como base conceptual para el diseño de la base de datos y la especificación de casos de uso.

## Diagrama del Modelo del Dominio

![Modelo del Dominio](../../../images/00-requisitos/00-modeloDelDominio/modelo-del-dominio.svg)

> [Ver código fuente (PlantUML)](../../../UML/00-requisitos/00-modeloDelDominio/modelo-del-dominio.puml)

## Problema que resuelve
El sistema garantiza la **trazabilidad financiera y operativa** asegurando que:
1. **Venta válida:** Todo ticket emitido por un Taquillero pertenezca a una Venta registrada.
2. **Acceso único y trazable:** Cada ticket autorice el acceso a una Máquina (atracción) específica y quede registrado en el turno operativo correspondiente.
3. **Control de recolección:** Los boletos físicos recibidos por el Motorario durante la jornada queden consolidados y auditados mediante su correspondiente Reporte de Tickets.
4. **Cuadre de caja:** La suma de Ventas individuales coincida exactamente con el Cierre de Caja del turno.

---

## 📖 Glosario de Términos

### Entidades y Roles

| Entidad / Rol | Tipo | Descripción |
| :--- | :--- | :--- |
| **Plaza** | Entidad | Ubicación geográfica temporal donde se instala el parque e itineran máquinas y personal. |
| **Máquina** | Entidad | Atracción física (ej. Noria, Coches de choque) con aforo y estado operativo. |
| **Venta** | Entidad | Registro de la transacción comercial realizada en caja que agrupa uno o varios tickets emitidos. |
| **Ticket** | Entidad | Comprobante que otorga el derecho de acceso a una atracción específica. |
| **ReporteDeTickets** | Entidad | Documento/registro transaccional auditable generado por el Motorario que agrupa y contabiliza el lote de tickets recolectados durante su turno. |
| **CierreDeCaja** | Entidad | Consolidación diaria o por turno de todas las ventas realizadas por el Taquillero. |
| **Taquillero** | Rol | Personal responsable de la emisión de tickets, atención en caja y arqueo de su turno. |
| **Motorario** | Rol | Operador de máquina encargado del control de acceso, recolección de boletos y rendición del Reporte de Tickets. |
| **Supervisor** | Rol | Encargado de la logística, asignaciones de personal/maquinaria y auditoría/aprobación de cierres financieros. |

### Procesos Financieros y Operaciones

| Proceso / Operación | Tipo | Descripción |
| :--- | :--- | :--- |
| **Solicitud / Anulación de Venta** | Operación | Cancelación de una transacción realizada por el Taquillero durante su turno. Invalida los tickets asociados y revierte el importe en caja. |
| **Autorización de Reembolso** | Proceso | Devolución del importe de un ticket al cliente tras su emisión, autorizada formalmente por el Supervisor. |
| **Cierre de Caja** | Proceso | Consolidación por turno de las ventas y montos recaudados, efectuada por el Taquillero. |
| **Revisión / Consolidación de Caja** | Proceso | Auditoría y confirmación del Cierre de Caja ejecutada por el Supervisor contra registros del sistema y dinero físico. |
| **Rendición de Reporte de Tickets** | Proceso | Ciclo mediante el cual el Motorario declara el lote de tickets físicos recibidos en la atracción para cerrar su turno. |
| **Asignación** | Operación | Vinculación temporal de un recurso humano (Taquillero, Motorario) o material (Máquina) a una entidad operativa (Plaza / Máquina). |

### Ciclo de Vida y Estados del Dominio

| Entidad | Estado | Descripción |
| :--- | :--- | :--- |
| **Máquina / Plaza** | **Alta / Activa** | La entidad está disponible e integrada en la operativa del parque para recibir o vender tickets. |
| **Máquina / Plaza** | **Baja / Inactiva** | Inactivación de la entidad (mantenimiento o final de temporada) sin eliminar su historial contable o de uso. |
| **Ticket** | **Válido / Consumido / Anulado** | Estado del acceso: listo para usar, recibido/validado en máquina, o cancelado comercialmente. |
| **Venta** | **Completada / Anulada / Reembolsada** | Refleja el estado contable final de la transacción económica en el sistema. |
| **ReporteDeTickets** | **En Proceso / Finalizado / Auditado** | Estado del ciclo de rendición de tickets del motorario desde la apertura hasta la entrega contable. |

---

## Relaciones del Modelo

### Relaciones Operativas e Infraestructura
- **Plaza agrupa Máquinas (`Plaza o-- Maquina`):** Una plaza física alberga las atracciones disponibles en esa ubicación.
- **Asignación de Personal:**
  - `Taquillero --> Plaza`: Asignación temporal del personal de caja a una ubicación.
  - `Maquina --> Motorario`: Asignación del operador a cargo de una atracción específica.
- **Supervisión de Entidades:** El Supervisor supervisa directamente las infraestructuras de Plazas y Máquinas.

### Relaciones Comerciales y de Control de Tickets
- **Venta contiene Tickets (`Venta *-- Ticket`):** Una transacción comercial genera uno o varios tickets individuales.
- **Ticket corresponde a Máquina (`Ticket --> Maquina`):** El ticket vincula la compra con el derecho de uso en una atracción concreta.
- **Motorario rinde Reporte (`Motorario --> ReporteDeTickets`):** El operador genera el informe de boletos recaudados al concluir su jornada/turno.
- **Reporte agrupa Tickets (`ReporteDeTickets o-- Ticket`):** El reporte consolida el lote de boletos recibidos físicamente para la auditoría contable.

### Relaciones Contables y Cierre
- **Cierre de Caja consolida Ventas (`CierreDeCaja --> Venta`):** El resumen financiero agrupa y audita todas las ventas del turno.
- **Intervención en Cierre de Caja:**
  - `Taquillero --> CierreDeCaja`: Efectúa y realiza la declaración inicial del cierre.
  - `Supervisor --> CierreDeCaja`: Revisa y consolida formalmente el resultado financiero del turno.

---

## Decisiones de Diseño y Semántica del Modelo

- **Agregación en lugar de Composición en Entidades Operativas e Históricas:**
  * *Decisión:* Se utilizan asociaciones simples / agregaciones (`o--` o `-->`) entre usuarios (`Taquillero`, `Motorario`, `Supervisor`) y sus artefactos transaccionales (`CierreDeCaja`, `ReporteDeTickets`).
  * *Justificación:* Garantiza la integridad contable e histórica. Si un usuario o cuenta es desactivado o cambiado de rol, sus registros históricos de ventas, cierres de caja y reportes de tickets permanecen intactos para auditorías contables posteriores.
- **Justificación de la Entidad `ReporteDeTickets`:**
  * *Decisión:* Se modela como una entidad explicita y no como un simple evento/acción.
  * *Justificación:* Proporciona evidencia auditable y trazabilidad temporal por lotes. Posee identificador, fechas, totalización de boletos recolectados y estados de rendición, permitiendo contrastar la recaudación física del motorario contra las ventas emitidas en caja.
- **Independencia del Ticket respecto a la Máquina:**
  * *Decisión:* El `Ticket` nace de una `Venta` y referencia a una `Maquina`.
  * *Justificación:* Desacopla el evento financiero (cobro en caja) de la prestación del servicio (uso/validación en la atracción).