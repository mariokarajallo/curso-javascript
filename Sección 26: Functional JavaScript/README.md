# Sección 26: **Functional JavaScript**

## 26.1 Qué es Functional JS?

La programación funcional en JavaScript es un paradigma de programación que se centra en el uso de funciones y la aplicación de conceptos matemáticos para resolver problemas de programación. Se basa en el principio de que un programa puede verse como una serie de transformaciones de datos mediante la composición de funciones.

En la programación funcional, se considera que las funciones son ciudadanos de primera clase, lo que significa que pueden ser asignadas a variables, pasadas como argumentos a otras funciones y devueltas como resultados de otras funciones. También se enfatiza la inmutabilidad de los datos, lo que implica que los datos no deben modificarse una vez que se crean, en su lugar, se crean nuevas versiones modificadas de los datos existentes.

### Algunos conceptos clave en la programación funcional en JavaScript incluyen:

1. Funciones puras: Son funciones que producen el mismo resultado cuando se les proporciona el mismo conjunto de entradas, sin causar efectos secundarios en el programa como modificar variables globales o realizar operaciones de E/S. Esto facilita la comprensión y el razonamiento sobre el código.
2. Inmutabilidad: Los datos se consideran inmutables, lo que significa que no se pueden modificar una vez que se crean. Evitar la modificación de datos. En lugar de cambiar un objeto o una variable existente, se crea una nueva copia con las modificaciones necesarias.
3. Composición de funciones: Se fomenta la composición de funciones, es decir, la combinación de varias funciones más pequeñas para crear funciones más complejas. Esto permite construir programas de manera modular y reutilizable.
4. Funciones de orden superior: JavaScript permite el uso de funciones de orden superior, que son funciones que pueden aceptar otras funciones como argumentos o devolver funciones como resultado. Ejemplos comunes en JavaScript incluyen **map**, **filter** y **reduce**.
   Esto permite construir abstracciones poderosas y expresivas.
5. Recursión: En lugar de utilizar bucles, la programación funcional favorece el uso de la recursión para iterar sobre estructuras de datos y realizar operaciones repetitivas. Evitar el uso de bucles, en lugar de utilizar bucles **for** o **while**, se utilizan funciones de alto orden como **map**, **filter** y **reduce** para iterar sobre colecciones de datos y aplicar transformaciones.
6. Funciones de primera clase: JavaScript permite el uso de funciones como valores, lo que significa que se pueden asignar a variables, pasar como argumentos a otras funciones y retornar como valores de otras funciones.

La programación funcional en JavaScript puede ayudar a escribir código más conciso, legible y mantenible, y puede ser especialmente útil en el manejo de datos y en el desarrollo de aplicaciones web.

### Ejemplos practicos

Un ejemplo simple de programación funcional en JavaScript sería:

```jsx
const suma = (a, b) => a + b;
const cuadrado = (x) => x * x;

const numeros = [1, 2, 3, 4, 5];

// Aplicar la función cuadrado a cada elemento del array y luego sumar todos los resultados
const sumaDeCuadrados = numeros.map(cuadrado).reduce(suma,
```

Este ejemplo ilustra cómo la programación funcional se enfoca en el uso de funciones y la transformación de datos mediante la composición de funciones.

```jsx
// Función pura: suma dos números
function sum(a, b) {
  return a + b;
}

// Función de orden superior: aplica una función a cada elemento de un arreglo
function map(arr, fn) {
  const result = [];
  for (let i = 0; i < arr.length; i++) {
    result.push(fn(arr[i]));
  }
  return result;
}

// Datos de entrada
const numbers = [1, 2, 3, 4, 5];

// Aplicar la función 'sum' a cada elemento del arreglo usando 'map' funcion de orden superior
const result = map(numbers, (num) => sum(num, 1));

console.log(result); // Output: [2, 3, 4, 5, 6]
```
