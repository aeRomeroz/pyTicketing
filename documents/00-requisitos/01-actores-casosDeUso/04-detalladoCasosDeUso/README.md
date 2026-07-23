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

# Detalle y Prototipo de Casos de Uso

Esta carpeta contiene la especificación detallada y el prototipado para cada caso de uso identificado en el sistema **pyTicketing**.

---

## Casos de Uso Específicos por Módulo

### 1. Módulo Administrador (Gestión de Usuarios y Accesos)
- [crearUsuario](Administrador/crearUsuario/) — Registro de nuevas cuentas de usuario en el sistema.
- [consultarUsuario](Administrador/consultarUsuario/) — Búsqueda, visualización y filtrado de usuarios.
- [editarUsuario](Administrador/editarUsuario/) — Modificación de perfil, credenciales y rol asignado.
- [desactivarUsuario](Administrador/desactivarUsuario/) — Inhabilitación de acceso para usuarios activos.
- [reactivarUsuario](Administrador/reactivarUsuario/) — Restablecimiento de acceso para cuentas inactivas.

### 2. Módulo Supervisor — Gestión de Plazas
- [registrarPlaza](Supervisor/Plaza/registrarPlaza/) — Alta de plazas operativas o sedes.
- [consultarPlaza](Supervisor/Plaza/consultarPlaza/) — Auditoría y consulta del estado de plazas.
- [editarPlaza](Supervisor/Plaza/editarPlaza/) — Actualización de datos generales y límites operacionales de la plaza.
- [darDeBajaPlaza](Supervisor/Plaza/darDeBajaPlaza/) — Cierre temporal o desactivación de plaza.
- [reactivarPlaza](Supervisor/Plaza/reactivarPlaza/) — Reapertura operativa de una plaza previamente dada de baja.
- [asignarMaquinaAPlaza](Supervisor/Plaza/asignarMaquinaAPlaza/) — Vinculación de máquinas/molinetes a una plaza.
- [desasignarMaquinaDePlaza](Supervisor/Plaza/desasignarMaquinaDePlaza/) — Desvinculación de máquinas para mantenimiento o reubicación.
- [asignarTaquilleroAPlaza](Supervisor/Plaza/asignarTaquilleroAPlaza/) — Asignación de personal de ventas a una plaza específica.
- [desasignarTaquilleroDePlaza](Supervisor/Plaza/desasignarTaquilleroDePlaza/) — Remoción de personal de ventas de una plaza.

### 3. Módulo Supervisor — Gestión de Máquinas
- [registrarMaquina](Supervisor/Maquina/registrarMaquina/) — Alta física y lógica de terminales/máquinas.
- [consultarMaquina](Supervisor/Maquina/consultarMaquina/) — Monitoreo e inspección de estado de máquinas.
- [editarMaquina](Supervisor/Maquina/editarMaquina/) — Modificación de configuración técnica de la máquina.
- [darDeBajaMaquina](Supervisor/Maquina/darDeBajaMaquina/) — Desactivación de máquinas por avería o mantenimiento.
- [reactivarMaquina](Supervisor/Maquina/reactivarMaquina/) — Restablecimiento de máquinas al parque activo.
- [asignarMotorarioAMaquina](Supervisor/Maquina/asignarMotorarioAMaquina/) — Asignación de operador a máquina/atracción.
- [desasignarMotorarioDeMaquina](Supervisor/Maquina/desasignarMotorarioDeMaquina/) — Desvinculación de operador de máquina.

### 4. Módulo Operativo de Ventas y Excepciones (Taquillero / Supervisor)
- [registrarVenta](Taquillero/registrarVenta/) — Expedición y cobro directo de boletos en taquilla.
- [solicitarAnulacionVenta](Taquillero/solicitarAnulacionVenta/) — Solicitud de anulación enviada por el taquillero ante imprevisto.
- [anularVenta](Supervisor/Venta/anularVenta/) — Autorización y ejecución de anulación por parte del supervisor.
- [autorizarReembolso](Supervisor/Venta/autorizarReembolso/) — Aprobación y registro de la devolución monetaria.

### 5. Módulo Cierre de Caja y Auditoría
- [declararCierreDeCaja](Taquillero/declararCierreDeCaja/) — Arqueo y rendición inicial de valores por el taquillero.
- [revisarCierreDeCaja](Supervisor/Caja/revisarCierreDeCaja/) — Auditoría y cotejo de arqueo por parte del supervisor.
- [consolidarCierreDeCaja](Supervisor/Caja/consolidarCierreDeCaja/) — Cierre definitivo y aprobación contable del turno.

### 6. Módulo Motorario (Conteo y Rendición de Boletos)
- [iniciarReporte](Motorario/iniciarReporte/) — Apertura del ciclo de recepción y conteo de boletos en atracción.
- [reportarTicketsRecibidos](Motorario/reportarTicketsRecibidos/) — Registro cuantitativo de boletos recolectados.
- [finalizarReporte](Motorario/finalizarReporte/) — Cierre y envío de la rendición física para auditoría.

---

## Principios y Buenas Prácticas Aplicadas

> **Filosofía del Modelo Dinámico:** Cada caso de uso representa un contenedor de estado explícito que garantiza la consistencia del dominio desde el inicio de la transacción hasta su consolidación final.

- **Diseño Agnóstico de Tecnología:** Especificaciones e interfaces centradas en las reglas de negocio sin acoplamiento a frameworks específicos.
- **Trazabilidad de Entidades:** Garantía de auditoría sobre transacciones, arqueos de caja y rendiciones de boletos.
- **Simetría Operacional:** Homologación en operaciones CRUD y ciclos de vida (Altas/Bajas, Asignaciones/Desasignaciones, Declaraciones/Consolidaciones).