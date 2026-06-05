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

| Caso de uso | Documentación |
|---|---|
| Gestión de Usuarios | [ver](documents/00-requisitos/01-actores_casosDeUso/01-casosDeUso/Administrador/README.md) |

---

### 📍 Supervisor — Plazas

| Caso de uso | Documentación |
|---|---|
| Gestión de Plazas | [ver](documents/00-requisitos/01-actores_casosDeUso/01-casosDeUso/Supervisor/Plaza/README.md) |

---

### 🎡 Supervisor — Máquinas

| Caso de uso | Documentación |
|---|---|
| Gestión de Máquinas | [ver](documents/00-requisitos/01-actores_casosDeUso/01-casosDeUso/Supervisor/Maquina/README.md) |

---

### 💰 Supervisor — Ventas

| Caso de uso | Documentación |
|---|---|
| Gestión de Ventas | [ver](documents/00-requisitos/01-actores_casosDeUso/01-casosDeUso/Supervisor/Venta/README.md) |

---

### 🎟️ Taquillero

| Caso de uso | Documentación |
|---|---|
| Operaciones de Taquilla | [ver](documents/00-requisitos/01-actores_casosDeUso/01-casosDeUso/Taquillero/README.md) |

---

### 🎠 Motorario

| Caso de uso | Documentación |
|---|---|
| Reportes de Motorario | [ver](documents/00-requisitos/01-actores_casosDeUso/01-casosDeUso/Motorario/README.md) |

---

## Convención de diagramas

Los diagramas de casos de uso están elaborados como **diagramas de estados** siguiendo esta convención de colores:

| Color | Significado |
|---|---|
| 🟢 Verde | Flujo principal / éxito |
| 🔴 Rojo | Cancelación / salida sin completar el objetivo |
| 🔵 Azul | Fin del diagrama |

---
