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

# Caso de Uso: [nombreCasoDeUso()]

## Resumen Ejecutivo

| Propiedad | Detalle |
| :--- | :--- |
| **Actor Principal** | [Nombre del Actor: Administrador / Supervisor / Taquillero / Motorario] |
| **Módulo Operativo** | [Módulo al que pertenece] |
| **Descripción** | Breve descripción sintética del objetivo de negocio que cumple este caso de uso. |
| **Precondición** | Estado o condición necesaria del sistema antes de iniciar. |
| **Postcondición** | Estado garantizado del sistema tras la ejecución exitosa. |

---

## 1. Diagrama de Especificación (Máquina de Estados)

Representa el ciclo de vida dinámico del caso de uso, las transiciones permitidas y el manejo de excepciones.

<div align="center">

| **Máquina de Estados Finita — `[nombreCasoDeUso()]`** |
| :---: |
| ![](/images/00-requisitos/01-actores-casosDeUso/01-casosDeUso/[Modulo]/[nombreCasoDeUso]/especificacion.svg) |
| [Ver código fuente PlantUML](especificacion.puml) |

</div>

---

## 2. Prototipo de Interfaz de Usuario (Wireframe)

Diseño conceptual de la interfaz de usuario en Salt para guiarnos en las etapas futuras de prototipado y desarrollo.

<div align="center">

| **Diseño de Interfaz / Wireframe — `[nombreCasoDeUso()]`** |
| :---: |
| ![](/images/00-requisitos/01-actores-casosDeUso/01-casosDeUso/[Modulo]/[nombreCasoDeUso]/prototipo.svg) |
| [Ver código fuente Salt](prototipo.puml) |

</div>

---

## 3. Especificación del Flujo de Eventos

### Flujo Principal (Camino Feliz)
1. **[Estado Inicial]**: El actor invoca la acción `[nombreCasoDeUso()]`.
2. **[Validación]**: El sistema verifica permisos, precondiciones y datos requeridos.
3. **[Procesamiento]**: El sistema aplica la regla de negocio y actualiza las entidades del dominio.
4. **[Consolidación]**: El sistema confirma la operación, emite la notificación correspondiente y transiciona al estado final.

### Flujos Alternativos y Excepciones
* **[E1. Datos Inválidos / Incompletos]**: El sistema alerta sobre los campos erróneos y retiene al actor en el formulario hasta corregir.
* **[E2. Cancelación por el Usuario]**: El actor aborta la operación y el sistema retorna al estado anterior sin alterar el dominio.