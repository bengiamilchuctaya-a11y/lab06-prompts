# Bitacora de prompts

Laboratorio 06: Fundamentos de Ingenieria de Prompts.

Herramienta de IA usada: (escribe aqui cual usaste)

## Ejercicio 2: Tokens y ventana de contexto

| Texto                              | Caracteres | Tokens |
| ---------------------------------- | ---------- | ------ |
| Los estudiantes programan en Java. | 34         | 7      |
| The students program in Java.      | 29         | 6      |
| desafortunadamente                 | 18         | 4      |

**explicando qué pasó en los pasos 4 y 5:**
Cuando la ia si tiene contexto de lo que le estamos pidiendo esta no se confunde y nos da datos correctos, pero cuando no, nos pide mas informacion(contexto).

## Ejercicio 3: Temperatura

| Temperatura | % de BiblioTec | Nombres en los 5 intentos                               |
| ----------- | -------------- | ------------------------------------------------------- |
| 0           | 100.0%         | BiblioTec, BiblioTec, BiblioTec, BiblioTec, BiblioTec   |
| 0.5         | 65.3%          | LibroYa, BiblioTec, LibroYa, LibroYa, LibroYa           |
| 1           | 44.5%          | PrestaLibro, BiblioTec, LibroYa, BiblioTec, BiblioTec   |
| 1.8         | 32.2%          | BiblioTec, PrestaLibro, PaginaLibre, LibroYa, BiblioTec |

**¿Que pasa con los nombres al subir la temperatura?**
Al aumentar la temperatura, el porcentaje de la opcion principal (BiblioTec) disminuye y los porcentajes se distribuyen entre las demas opciones.

**¿Por que el simulador nunca inventa un nombre nuevo?**
La temperatura solo cambia la probabilidad de elección entre las opciones que ya existen enlas opciones del modelo, no le agrega conocimiento.

## Ejercicio 4: Prompt vago vs estructurado

| Criterio                            | Prompt vago | Prompt estructurado |
| :---------------------------------- | :---------: | :-----------------: |
| Menciona el objetivo del sistema    |     Sí      |         Sí          |
| Menciona a los usuarios principales |     No      |         Sí          |
| Tiene exactamente 3 funcionalidades |     No      |         Sí          |
| Esta en 3 parrafos                  |     No      |         Sí          |
| Lo usaria en un informe real        |     No      |         Sí          |

## Ejercicio 5: Anatomia de un prompt

| Componente      | Texto de mi prompt                                                                                         |
| :-------------- | :--------------------------------------------------------------------------------------------------------- |
| **Rol**         | `Actua como desarrollador Java.`                                                                           |
| **Instrucción** | `Crea un programa en Java ... usando una clase Producto con los atributos codigo, nombre, precio y stock.` |
| **Contexto**    | `para gestionar los productos de una tienda.`                                                              |
| **Ejemplo**     | `Usa este estilo para los metodos: getPrecio(), setPrecio(double precio).`                                 |
| **Formato**     | `Explica primero la estructura de la clase y luego presenta el codigo Java.`                               |

**Cambios en la respuesta por cada nivel**

- **Nivel 1:** Como el prompt era muy general, la IA eligió el tema al azar y creó un sistema de biblioteca muy básico.
- **Nivel 2 (+Rol):** Al pedirle que actúe como desarrollador Java, mejoró la calidad del código ordenándolo en métodos y usando `ArrayList`.
- **Nivel 3 (+Contexto):** Al darle el contexto de una tienda, cambió la temática de la biblioteca por un programa para gestionar productos.
- **Nivel 4 (+Instrucción):** Al especificar la clase `Producto` con sus atributos, cambió `id` por `codigo`, puso las variables en privado y creó el constructor con sus _getters_.
- **Nivel 5 (+Formato):** Al pedirle un formato claro, organizó la respuesta poniendo la explicación teórica arriba, justo antes del código Java.
- **Nivel 6 (+Ejemplo):** Al darle un ejemplo de sintaxis, agregó los métodos _setters_ y mostró cómo usarlos en el `main` para cambiar el precio de un producto.

## Ejercicio 6: Del prompt basico al profesional

| Qué revisar                                            | Cumple (Sí / No) |
| :----------------------------------------------------- | :--------------: |
| ¿Está escrito en Java y usa Swing?                     |      **Sí**      |
| ¿Pide correo y contraseña?                             |      **Sí**      |
| ¿Explica el funcionamiento antes o después del código? |      **Sí**      |
| ¿El código está organizado en clases?                  |      **Sí**      |
| ¿Valida los datos que ingresa el usuario?              |      **Sí**      |

**PROMT FINAL (profesional)**

```text
Actua como desarrollador Java. Crea un ejemplo de login para una
aplicacion de escritorio utilizando Swing. El usuario debe ingresar
correo y contrasena. Explica brevemente el funcionamiento y presenta
el codigo organizado por clases. No uses librerias
externas, valida que el correo contenga @ y que la contrasena tenga
al menos 8 caracteres, y muestra los mensajes con JOptionPane.
```

[Bitacora de prompts](prompts/BITACORA.md)

- [Tarea: mi prompt profesional](prompts/TAREA.md)
