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

## Propósito

Especificación detallada del caso de uso `crearUsuario()` mediante diagrama de estados finitos, mostrando la conversación completa entre el **Administrador** y el **Sistema** para el registro de nuevos usuarios en la plataforma.

## Información del Caso de Uso

|Atributo|Valor|
|-|-|
|**Nombre**|crearUsuario()|
|**Actor primario**|Administrador|
|**Objetivo**|Registrar una nueva cuenta de usuario asignando sus datos personales, credenciales y rol operativo|
|**Tipo**|Primario, esencial|
|**Nivel**|Objetivo de usuario|
|**Precondición**|El Administrador se encuentra autenticado y en la pantalla de gestión de usuarios|
|**Postcondición exitosa**|Se crea una nueva entidad Usuario con estado `ACTIVO` en el sistema|
|**Postcondición de fallo**|No se registra el usuario y el sistema permanece en el estado de gestión|

## diagrama de especificación

<div align=center>

|![Caso de uso: crearUsuario()](/images/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Administrador/crearUsuario.svg)|
|-|
|Código fuente: [crearUsuario.puml](/UML/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Administrador/crearUsuario.puml)|

</div>

## prototipo de interfaz

### propósito del prototipo
**Objetivo:** Validar la especificación y los campos requeridos para la creación de cuentas antes de realizar la implementación.

### wireframes

#### pantalla 1: formulario de creación de usuario
<div align=center>

|![Wireframe: Formulario crear usuario](/images/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Administrador/crearUsuario/crearUsuario-wireframe.svg)|
|-|
|**Estado**: SolicitandoCreacion → IntroduciendoDatos|

</div>

**Correspondencia con especificación:**
- Actor "solicita crear usuario"
- Sistema "permite introducir datos personales, rol y credenciales"

#### pantalla 2: error en formulario (datos inválidos / duplicados)
<div align=center>

|![Wireframe: Error en formulario](/images/00-requisitos/01-actores-casosDeUso/01-casosDeUso/Administrador/crearUsuario/crearUsuario-error-wireframe.svg)|
|-|
|**Estado**: Choice point → regreso a IntroduciendoDatos|

</div>

**Correspondencia con especificación:**
- Choice point evalúa: "datos incompletos / usuario ya existe"
- Sistema presenta el formulario resaltando los campos erróneos

**Código fuente:** [prototipo.puml](prototipo.puml)

## conversación detallada

### flujo principal (éxito)

|Actor|Acción|Sistema|Respuesta|
|-|-|-|-|
|**Administrador**|solicita crear nuevo usuario|||
||**Sistema**|permite introducir|• nombre y apellido<br>• correo electrónico<br>• nombre de usuario<br>• contraseña<br>• rol (Administrador, Supervisor, Taquillero, Motorario)|
|**Administrador**|introduce|• datos requeridos<br>• rol seleccionado||
||**Sistema**|registra usuario|• confirma creación exitosa<br>• asigna estado ACTIVO|

### flujo alternativo (error)

|Actor|Acción|Sistema|Respuesta|
|-|-|-|-|
|**Administrador**|solicita crear nuevo usuario|||
||**Sistema**|permite introducir|• datos requeridos|
|**Administrador**|introduce|• datos incompletos o nombre de usuario en uso||
||**Sistema**|informa error|• muestra mensaje explicativo<br>• conserva datos para corrección|

## estados internos del caso de uso

|Estado|Descripción|Responsabilidad|
|-|-|-|
|**SolicitandoCreacion**|Estado inicial tras pulsar el botón de creación|Sistema debe desplegar el formulario limpio|
|**IntroduciendoDatos**|Administrador completa la información|Sistema recibe entrada de datos en tiempo real|
|**Punto de decisión**|Evaluación de validez y unicidad del usuario|Sistema valida campos contra reglas del dominio|

## validaciones del sistema

|Validación|Criterio|Resultado|
|-|-|-|
|**Datos válidos y únicos**|Campos completos y username/email no registrado|Transicionar a `UsuarioCreado` y guardar registro|
|**Datos inválidos o duplicados**|Campo obligatorio vacío o username ya existente|Regresar a `IntroduciendoDatos` con alerta|

## conexión con diagrama de contexto

Este caso de uso corresponde a la transición dentro del contenedor:
- **GESTION_USUARIOS_ABIERTA** → `crearUsuario()` → **GESTION_USUARIOS_ABIERTA**

La especificación detalla la sub-máquina interna al seleccionar la opción de creación dentro de la gestión de usuarios del Administrador.

## vocabulario utilizado

### actor (Administrador)
- **solicita**: inicia la interacción pidiendo el formulario de alta
- **introduce**: proporciona los datos del usuario a registrar

### sistema
- **permite**: habilita los campos de captura de datos
- **registra**: persiste la entidad en el dominio y confirma la operación

## características metodológicas

### separación de responsabilidades
- **Actor**: Solo solicita y completa la información.
- **Sistema**: Habilita la interfaz, evalúa las reglas y persiste la entidad.

### ausencia de detalles de implementación
- No especifica base de datos (SQL/NoSQL).
- No define algoritmos de cifrado de contraseña (se trata a nivel conceptual).
- Agnóstico del framework de interfaz gráfica.

### conversación atómica
- Representa el ciclo completo de alta de un usuario en el sistema.

### referencias

- [Diagrama de contexto - Administrador](../../../02-diagramaDeContexto/README.md)
- [Modelo del dominio](../../../../00-modeloDelDominio/README.md)
- [conversation-log.md](../../../../../../conversation-log.md)