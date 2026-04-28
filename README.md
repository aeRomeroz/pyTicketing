# pyTicketing — Documentación del Sistema

<!--
>> Documentación técnica del sistema de ticketing para parque itinerante.  
> Elaborada siguiendo la metodología **RUP (Rational Unified Process)**.
-->
---

## 📁 Estructura del repositorio

```
documentos/
└── casosDeUso/
    ├── Administrador/
    ├── Motorario/
    ├── Supervisor/
    │   ├── Maquina/
    │   ├── Plaza/
    │   └── Venta/
    └── Taquillero/
```

---

## 👥 Actores del sistema

| Actor | Responsabilidad |
|---|---|
| **Administrador** | Gestión de usuarios del sistema (crear, consultar, editar, desactivar, reactivar) |
| **Supervisor** | Gestión operativa de plazas, máquinas, asignaciones, cierre de caja y reembolsos |
| **Taquillero** | Registro de ventas, anulaciones y consolidación del cierre de caja |
| **Motorario** | Reporte de tickets recibidos en su máquina |

---

## 📋 Casos de uso

### 🔑 Administrador

| Caso de uso | Diagrama |
|---|---|
| Crear usuario | [ver](documentos/casosDeUso/Administrador/crearUsuario.svg) |
| Consultar usuario | [ver](documentos/casosDeUso/Administrador/consultarUsuario.svg) |
| Editar usuario | [ver](documentos/casosDeUso/Administrador/editarUsuario.svg) |
| Desactivar usuario | [ver](documentos/casosDeUso/Administrador/desactivarUsuario.svg) |
| Reactivar usuario | [ver](documentos/casosDeUso/Administrador/reactivarUsuario.svg) |

---

### 📍 Supervisor — Plazas

| Caso de uso | Diagrama |
|---|---|
| Registrar plaza | [ver](documentos/casosDeUso/Supervisor/Plaza/registrarPlaza.svg) |
| Consultar plaza | [ver](documentos/casosDeUso/Supervisor/Plaza/consultarPlaza.svg) |
| Editar plaza | [ver](documentos/casosDeUso/Supervisor/Plaza/editarPlaza.svg) |
| Dar de baja plaza | [ver](documentos/casosDeUso/Supervisor/Plaza/darDeBajaPlaza.svg) |
| Reactivar plaza | [ver](documentos/casosDeUso/Supervisor/Plaza/reactivarPlaza.svg) |
| Asignar máquina a plaza | [ver](documentos/casosDeUso/Supervisor/Plaza/asignarMaquinaAPLaza.svg) |
| Desasignar máquina de plaza | [ver](documentos/casosDeUso/Supervisor/Plaza/desasignarMaquinaDePlaza.svg) |
| Asignar taquillero a plaza | [ver](documentos/casosDeUso/Supervisor/Plaza/asignarTaquilleroAPlaza.svg) |
| Desasignar taquillero de plaza | [ver](documentos/casosDeUso/Supervisor/Plaza/desasignarTaquilleroDePlaza.svg) |

---

### 🎡 Supervisor — Máquinas

| Caso de uso | Diagrama |
|---|---|
| Registrar máquina | [ver](documentos/casosDeUso/Supervisor/Maquina/registrarMaquina.svg) |
| Consultar máquina | [ver](documentos/casosDeUso/Supervisor/Maquina/consultarMaquina.svg) |
| Editar máquina | [ver](documentos/casosDeUso/Supervisor/Maquina/editarMaquina.svg) |
| Dar de baja máquina | [ver](documentos/casosDeUso/Supervisor/Maquina/darDeBajaMaquina.svg) |
| Reactivar máquina | [ver](documentos/casosDeUso/Supervisor/Maquina/reactivarMaquina.svg) |
| Asignar motorario a máquina | [ver](documentos/casosDeUso/Supervisor/Maquina/asignarMotorarioAMaquina.svg) |
| Desasignar motorario de máquina | [ver](documentos/casosDeUso/Supervisor/Maquina/desasignarMotorarioDeMaquina.svg) |

---

### 💰 Supervisor — Ventas

| Caso de uso | Diagrama |
|---|---|
| Anular venta | [ver](documentos/casosDeUso/Supervisor/Venta/anularVenta.svg) |
| Autorizar reembolso | [ver](documentos/casosDeUso/Supervisor/Venta/autorizarReembolso.svg) |
| Revisar cierre de caja | [ver](documentos/casosDeUso/Supervisor/Venta/revisarCierreDeCaja.svg) |

---

### 🎟️ Taquillero

| Caso de uso | Diagrama |
|---|---|
| Registrar venta | [ver](documentos/casosDeUso/Taquillero/registrarVenta.svg) |
| Anular venta | [ver](documentos/casosDeUso/Taquillero/anularVenta.svg) |
| Consolidar cierre de caja | [ver](documentos/casosDeUso/Taquillero/consolidarCierreDeCaja.svg) |

---

### 🎠 Motorario

| Caso de uso | Diagrama |
|---|---|
| Reportar tickets recibidos | [ver](documentos/casosDeUso/Motorario/reportarTicketsRecibidos.svg) |

---

## Convención de diagramas

Los diagramas de casos de uso están elaborados como **diagramas de estados** siguiendo esta convención de colores:

| Color | Significado |
|---|---|
| 🟢 Verde | Flujo principal / éxito |
| 🔴 Rojo | Cancelación / salida sin completar el objetivo |
| 🔵 Azul | Fin del diagrama |

---
