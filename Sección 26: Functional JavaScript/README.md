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

## 26.2 First Class Functions

En programación, el concepto de "funciones de primera clase" (o "first-class functions" en inglés) se refiere a que las funciones son tratadas como cualquier otro valor o dato en el lenguaje de programación (como números, cadenas o listas). Esto significa que en un lenguaje con soporte para funciones de primera clase, las funciones pueden ser:

1. Asignadas a variables: Puedes asignar una función a una variable, de modo que la variable se convierte en una referencia a esa función.

```jsx
// Asignar una función a una variable
const greet = function (name) {
  console.log(`¡Hola, ${name}!`);
};

// Llamar a la función a través de la variable
greet("Mario"); // Output: ¡Hola, Juan!
```

1. Pasadas como argumentos: Las funciones pueden ser pasadas como argumentos a otras funciones. Esto permite la posibilidad de pasar funciones como parámetros y utilizarlas dentro de otras funciones.

```jsx
// Función que recibe una función como argumento
function applyOperation(a, b, operation) {
  return operation(a, b);
}

// Definir funciones para realizar diferentes operaciones
function add(a, b) {
  return a + b;
}

function multiply(a, b) {
  return a * b;
}

// Llamar a la función 'applyOperation' con diferentes operaciones
console.log(applyOperation(5, 3, add)); // Output: 8
console.log(applyOperation(5, 3, multiply)); // Output: 15
```

1. Retornadas como resultados: Una función puede devolver otra función como resultado. Esto es útil para crear y retornar funciones dinámicamente, en función de ciertas condiciones o cálculos.

```jsx
// Función que devuelve otra función basada en un parámetro
function createMultiplier(factor) {
  return function (number) {
    return number * factor;
  };
}

// Crear funciones multiplicadoras para diferentes factores
const double = createMultiplier(2);
const triple = createMultiplier(3);

console.log(double(5)); // Output: 10
console.log(triple(5)); // Output: 15
```

1. Almacenadas en estructuras de datos: Las funciones pueden ser almacenadas en estructuras de datos como arreglos, objetos o incluso otras funciones.

```jsx
// Almacenar funciones en un arreglo
const operations = [
  function (a, b) {
    return a + b;
  },
  function (a, b) {
    return a - b;
  },
  function (a, b) {
    return a * b;
  },
];

// Llamar a las funciones del arreglo
console.log(operations[0](3, 2)); // Output: 5
console.log(operations[1](3, 2)); // Output: 1
console.log(operations[2](3, 2)); // Output: 6
```

La capacidad de tratar las funciones como valores de primera clase proporciona una mayor flexibilidad y expresividad en la programación. Permite escribir código más modular, reutilizable y poderoso, ya que puedes manipular y trabajar con funciones de la misma manera que lo harías con otros tipos de datos.

El soporte para funciones de primera clase es una característica común en muchos lenguajes de programación modernos, incluyendo JavaScript, Python, Ruby y otros.

## 26.3 Funciones como Argumentos

En la programación funcional, las funciones como argumento se refieren al concepto de pasar una función como argumento a otra función.

Esto permite que una función reciba una función como uno de sus parámetros, lo que brinda flexibilidad y capacidad de abstracción en el diseño de programas.

Cuando se utilizan funciones como argumentos en la programación funcional, se pueden lograr varias cosas, incluyendo:

1. #### Mayor modularidad:
   Al pasar una función como argumento, se puede separar la lógica específica de una función en particular y reutilizarla en diferentes contextos. Esto promueve la modularidad y facilita la composición de funciones más complejas.
2. #### Abstracción de comportamiento:
   Al permitir que las funciones sean pasadas como argumentos, se puede generalizar el comportamiento de una función y hacerla más genérica. Esto permite que la función que recibe la función como argumento pueda adaptar su comportamiento en función de la función pasada.
3. #### Implementación de patrones de diseño:
   Algunos patrones de diseño, como el patrón "Strategy" o el patrón "Callback", se basan en el uso de funciones como argumentos. Estos patrones permiten cambiar el comportamiento de una función en tiempo de ejecución al pasar diferentes funciones como argumentos.
   ##### Patrón Strategy:
   - El patrón de diseño "Strategy" (o "estrategia") es un patrón de diseño de software que permite intercambiar algoritmos o estrategias en tiempo de ejecución. Se utiliza cuando se desea tener diferentes formas de resolver un problema y poder cambiar la estrategia utilizada sin modificar la estructura principal del código.
   - En este patrón, se define una interfaz común para todas las estrategias y se implementan clases que representan cada una de las posibles estrategias. Estas clases implementan la misma interfaz, lo que permite que se puedan intercambiar fácilmente en tiempo de ejecución.
   - El patrón "Strategy" se beneficia del concepto de funciones como argumentos, ya que permite que una función se pase como argumento a otra función o se almacene como propiedad en un objeto, lo que proporciona una forma flexible de implementar diferentes estrategias.
   - Ejemplo sencillo: Supongamos que tenemos una aplicación de navegación que puede calcular rutas utilizando diferentes algoritmos (ruta más corta, ruta más rápida, ruta más escénica). En lugar de codificar cada algoritmo directamente en la aplicación, se crea una interfaz común (Estrategia) y se implementan los algoritmos como clases separadas. La aplicación puede cambiar fácilmente entre algoritmos en tiempo de ejecución.
   ##### Patrón Callback:
   - El concepto de "callback" se refiere a una función que se pasa como argumento a otra función y que se invoca en un momento posterior dentro de esa función. Es una forma común de lograr la programación asíncrona y la manipulación de eventos en muchos lenguajes de programación.
   - En JavaScript, los callbacks son ampliamente utilizados en operaciones asíncronas, como solicitudes de red, lectura y escritura de archivos, y manejo de eventos. Cuando se realiza una operación asíncrona, se proporciona una función de callback que se ejecuta una vez que la operación se completa o cuando se produce un evento específico.
   - El uso de callbacks permite que el código siga ejecutándose mientras se espera la finalización de una operación asíncrona, evitando bloqueos y permitiendo una programación más eficiente y no bloqueante.
   - Ejemplo sencillo: Imagina que estás creando una aplicación que realiza una solicitud a una API y procesa los datos recibidos. En lugar de codificar directamente la lógica de procesamiento en la función que realiza la solicitud, puedes pasar una función de callback que se encargue de procesar los datos. De esta manera, puedes reutilizar la función de solicitud para diferentes tipos de procesamiento, simplemente cambiando el callback que se pasa como argumento.

Aquí tienes un ejemplo simple que ilustra el uso de funciones como argumentos en la programación funcional en JavaScript:

```jsx
// Función que toma una función como argumento
function executeOperation(a, b, operation) {
  return operation(a, b);
}

// Funciones de operación
function add(a, b) {
  return a + b;
}

function multiply(a, b) {
  return a * b;
}

// Llamadas a la función 'executeOperation' con diferentes operaciones
console.log(executeOperation(5, 3, add)); // Output: 8
console.log(executeOperation(5, 3, multiply)); // Output: 15
```

En este ejemplo, la función **`executeOperation`** toma tres argumentos: **`a`**, **`b`** y **`operation`**, donde **`operation`** es una función. La función **`executeOperation`** luego ejecuta la función **`operation`** pasando **`a`** y **`b`** como argumentos.

Al llamar a **`executeOperation`** con diferentes funciones de operación, podemos realizar diferentes cálculos utilizando la misma estructura de función. Esto demuestra cómo las funciones como argumentos pueden permitir la flexibilidad y la capacidad de adaptar el comportamiento de una función en tiempo de ejecución.
