# kevin-jassiel-sanchez-ramos-lenguajedeinterfaz-unidad-3
# Prácticas de la Unidad 3 - Lenguajes de Interfaz

**Alumno:** Kevin Jassiel Sánchez Ramos[cite: 4]  
**Horario:** 8:00 AM - 9:00 AM  
**Institución:** Instituto Tecnológico de Culiacán  
**Materia:** Lenguajes de Interfaz[cite: 4]  

---

## Descripción General
Este repositorio contiene un conjunto de 5 prácticas desarrolladas en lenguaje ensamblador utilizando la librería `Irvine32`[cite: 1, 2, 3, 4, 5] para la arquitectura x86 (modo protegido de 32 bits), enfocadas en el manejo de procedimientos, el uso de la pila (stack), validación de cadenas y programación con macros.

---

## Contenido de las Prácticas

### Práctica 1: Uso básico de Procedimientos (`CALL` y `RET`)
* **Archivo:** `practica1/main.asm`[cite: 1]
* **Qué hace el programa:** Demuestra el flujo de ejecución mediante saltos a subrutinas utilizando las instrucciones `CALL` y `RET`. Imprime mensajes de inicio, entra a un procedimiento llamado `mensajeAviso` de forma repetida, modifica registros y finaliza[cite: 1].
* **Qué comprobé al ejecutarlo:** Se comprobó cómo el registro `EIP` maneja la dirección de retorno de forma automática al invocar un procedimiento, permitiendo regresar exactamente a la instrucción posterior al `CALL`.

### Práctica 2: Inspección del Puntero de Pila (`ESP`) en Procedimientos Anidados
* **Archivo:** `practica2/main.asm`[cite: 2]
* **Qué hace el programa:** Imprime en formato hexadecimal el valor actual del puntero de pila (`ESP`) en diferentes niveles de llamadas a procedimientos anidados (`main` -> `procUno` -> `procDos`)[cite: 2].
* **Qué comprobé al ejecutarlo:** Verifiqué cómo la dirección de la pila cambia (decrece debido al almacenamiento de las direcciones de retorno por cada `CALL`) conforme se entra a niveles más profundos de subrutinas.

### Práctica 3: Manejo de la Pila y Paso de Parámetros (`EBP` y `RET n`)
* **Archivo:** `practica3/main.asm`[cite: 3]
* **Qué hace el programa:** Realiza el paso de parámetros a través de la pila (`push`), establece un marco de pila usando el puntero base (`EBP`), efectúa una multiplicación con signo (`imul`) de los valores recibidos y limpia los parámetros de la pila al retornar mediante `RET 8`[cite: 3].
* **Qué comprobé al ejecutarlo:** Comprobé la forma correcta de acceder a argumentos apilados mediante desplazamientos positivos (`[ebp+8]`, `[ebp+12]`) y la importancia de limpiar correctamente la pila para evitar desbordamientos o fallas de retorno[cite: 3].

### Práctica 4: Validación de Cadenas Vacías
* **Archivo:** `practica4/main.asm`[cite: 4]
* **Qué hace el programa:** Solicita al usuario una cadena de caracteres por consola mediante `ReadString`, valida el primer byte de la variable para comprobar si contiene un terminador nulo (`0`) y muestra en pantalla si la cadena está vacía o contiene texto[cite: 4].
* **Qué comprobé al ejecutarlo:** Comprobé el uso de comparaciones condicionales (`cmp`) y saltos condicionales (`je`, `jmp`) para evaluar entradas de usuario a nivel de byte en memoria.

### Práctica 5: Implementación y Uso de Macros
* **Archivo:** `practica5/main.asm`[cite: 5]
* **Qué hace el programa:** Define y utiliza macros personalizadas (`MostrarMensaje` y `Multi`) para automatizar tareas repetitivas como la impresión de cadenas en consola mediante `WriteString` y la multiplicación de valores numéricos[cite: 5].
* **Qué comprobé al ejecutarlo:** Comprobé que las macros se expanden directamente en el código fuente durante el tiempo de ensamblado, facilitando la modularidad sin el overhead de rendimiento que implican las llamadas a procedimientos convencionales.