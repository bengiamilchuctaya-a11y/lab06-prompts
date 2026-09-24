# Tarea: Mi prompt profesional

## Funcionalidad elegida

Sistema CRUD (Crear, Leer, Actualizar, Eliminar) de Productos para una tienda de abarrotes utilizando Java Swing para la interfaz de escritorio.

## Version 1: prompt basico

```text
Hazme un CRUD de productos.
```

- **Qué cambié:** Es la versión inicial sin especificidad.
- **Por qué:** Representa la consulta genérica de un usuario sin experiencia en ingeniería de prompts.
- **Qué mejoró en la respuesta:** La respuesta fue vaga; la IA generó un script simple en consola usando Python y arreglos en memoria, sin interfaz gráfica ni estructura orientada a objetos.

## Version 2

```text
Crea un CRUD de productos en Java usando Swing para escritorio. Debe permitir agregar, listar, editar y eliminar productos con nombre, precio y stock.
```

- **Qué cambié:** Especificué el lenguaje de programación (Java), la tecnología de interfaz (Swing), el entorno (escritorio) y los campos requeridos (nombre, precio, stock).
- **Por qué:** Para evitar que la IA asuma un lenguaje aleatorio o genere campos que no necesito.
- **Qué mejoró en la respuesta:** La IA entregó un código en Java funcional con ventanas de Swing, pero puso todo el código dentro de una sola clase gigante y no manejó restricciones de diseño ni librerías.

## Version 3: prompt final

```text
Actúa como un desarrollador Java Senior especializado en arquitecturas de escritorio.

Necesito un sistema CRUD (Crear, Leer, Actualizar, Eliminar) de productos para una tienda de abarrotes. La aplicación debe contar con una interfaz gráfica Swing intuitiva.

Cada producto debe incluir: id (generado automáticamente), nombre, precio (double) y cantidad de stock (int).

Requisitos estrictos / Restricciones:
- NO uses librerías externas ni frameworks de persistencia (como Hibernate o Maven dependencies). Usa únicamente componentes nativos de Java SE (Swing, AWT y colecciones como ArrayList).
- Organiza el código siguiendo una arquitectura limpia dividida en 3 clases: Producto (Modelo), ProductoRepository (Lógica de almacenamiento) y ProductoFrame (Interfaz gráfica).

Ejemplo de estructura de respuesta esperada:
1. Explicación breve de la arquitectura planteada.
2. Código estructurado clase por clase en bloques de código separados.
3. Instrucciones claras sobre cómo ejecutar la aplicación desde la clase Main.
```

- **Qué cambié:** Añadí un rol profesional, contexto del dominio de negocio, estructura deseada de respuesta, ejemplos de salida y restricciones estrictas (sin librerías externas y división en 3 clases).
- **Por qué:** Para garantizar código modular, mantenible, fácil de probar y sin dependencias difíciles de configurar.
- **Qué mejoró en la respuesta:** Generó un proyecto limpio con arquitectura en capas (Modelo, Repositorio y Vista), con validación de tipos de datos e instrucciones paso a paso para ejecutarlo en cualquier IDE.

## Componentes del prompt final

| Componente            | Ejemplo exacto en el Prompt Final                                                                                    |
| :-------------------- | :------------------------------------------------------------------------------------------------------------------- |
| **Rol**               | `Actúa como un desarrollador Java Senior especializado en arquitecturas de escritorio.`                              |
| **Instrucción**       | `Necesito un sistema CRUD (Crear, Leer, Actualizar, Eliminar) de productos...`                                       |
| **Contexto**          | `...para una tienda de abarrotes. Cada producto debe incluir: id, nombre, precio y cantidad de stock.`               |
| **Restricción**       | `NO uses librerías externas ni frameworks... Usa únicamente componentes nativos de Java SE.`                         |
| **Ejemplo / Formato** | `Ejemplo de estructura de respuesta esperada: 1. Explicación breve... 2. Código estructurado... 3. Instrucciones...` |

## Evaluacion del resultado

| Criterio de Evaluación                                                         | Cumple (Sí / No) |
| :----------------------------------------------------------------------------- | :--------------- |
| ¿Está escrito en Java y utiliza Swing de manera nativa sin librerías externas? | **Sí**           |
| ¿Permite realizar las 4 operaciones CRUD sobre los campos indicados?           | **Sí**           |
| ¿El código se entregó organizado y separado en las clases requeridas?          | **Sí**           |
| ¿Incluye la explicación de la arquitectura e instrucciones de ejecución?       | **Sí**           |

## Errores que evite

1. **Ser demasiado general:**
   - En la `v1` solo pedí "un CRUD". En la `v3` especifiqué detalladamente el lenguaje (Java), la tecnología gráfica (Swing), el tipo de aplicación (escritorio) y los atributos exactos de la entidad `Producto`.
2. **No dar contexto ni restricciones:**
   - Al no dar restricciones, la IA solía incluir dependencias de bases de datos o frameworks como Hibernate/Spring. Lo evité agregando una sección explícita de "Requisitos estrictos / Restricciones" prohibiendo librerías externas y exigiendo el uso de colecciones nativas (`ArrayList`).

- [Tarea: mi prompt profesional](prompts/TAREA.md)
