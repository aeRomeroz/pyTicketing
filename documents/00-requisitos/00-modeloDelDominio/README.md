# Modelo del Dominio y Glosario de Términos

Este documento constituye la **fuente de verdad** para el lenguaje y la estructura del negocio del sistema **pyTicketing**. Aquí se definen tanto las entidades y sus relaciones como el significado de cada término técnico y operativo.

---

## 📊 Diagrama del Modelo del Dominio

El siguiente diagrama representa las entidades clave del sistema y cómo interactúan entre sí según las reglas de negocio identificadas.

![Modelo del Dominio](../../../images/00-requisitos/00-modeloDelDominio/modelo-del-dominio.svg)

> [Ver código fuente (PlantUML)](../../../UML/00-requisitos/00-modeloDelDominio/modelo-del-dominio.puml)

---

## 📖 Glosario de Términos

### 🏗️ Entidades de Negocio

#### Plaza
Espacio físico o ubicación geográfica donde se instala el parque itinerante. Una plaza agrupa un conjunto de máquinas y taquilleros durante un periodo de tiempo determinado.

#### Máquina (Atracción)
Unidad operativa del parque (ej. montaña rusa, carrusel). Cada máquina tiene un aforo, un estado (activa/baja) y requiere de un motorario para su validación.

#### Ticket
Documento (físico o digital) que representa el derecho de acceso a una atracción. Contiene información sobre la venta y su estado de validez.

---

### 👥 Roles y Actores

#### Administrador
Usuario con permisos de nivel de sistema encargado de gestionar las cuentas de usuario, perfiles y permisos. No interviene directamente en la operación diaria del parque.

#### Supervisor
Responsable de la logística y supervisión financiera. Gestiona la creación de plazas, máquinas y las asignaciones de personal. Valida los procesos críticos como reembolsos y revisiones de caja.

#### Taquillero
Personal encargado del punto de venta. Sus funciones principales son la emisión de tickets, la gestión de anulaciones inmediatas y la preparación del cierre de caja al finalizar su turno.

#### Motorario
Operador asignado a una máquina específica. Su responsabilidad es validar los tickets recibidos y reportar la actividad de la máquina para el control de aforo y estadísticas de uso.

---

### 💰 Procesos Financieros

#### Cierre de Caja (Consolidación)
Proceso realizado por el Taquillero al finalizar su jornada, donde se suma el total de ventas realizadas y se prepara el reporte para su posterior validación.

#### Revisión de Caja
Acción ejecutada por el Supervisor para validar que la consolidación realizada por el Taquillero coincide con los registros del sistema y el dinero físico recaudado.

#### Anulación de Venta
Cancelación de una transacción de venta. Puede ser realizada por el Taquillero (en condiciones normales) o requerir intervención del Supervisor si existen discrepancias.

#### Reembolso
Proceso mediante el cual se devuelve el importe de un ticket al cliente. Debido a su impacto financiero, requiere de una **Autorización de Reembolso** explita por parte del Supervisor.

---

### ⚙️ Estados y Operaciones

#### Asignación
Acto de vincular un recurso humano (Taquillero, Motorario) o material (Máquina) a una entidad organizativa (Plaza) para un periodo de tiempo.

#### Dar de Baja / Reactivar
Cambio de estado de una entidad (Usuario, Plaza o Máquina) que impide o permite su uso en el sistema sin eliminar sus registros históricos.

---
<p align="center">
  <i>Este documento es un artefacto vivo y debe actualizarse ante cualquier cambio en las definiciones de negocio.</i>
</p>
