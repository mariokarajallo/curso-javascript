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

## 26.4 Separar los Datos de las funciones & Higher Order Functions

En la programación funcional, separar los datos de las funciones se refiere a mantener una clara distinción entre los datos y las operaciones que se realizan sobre esos datos. Se busca evitar la mutación o modificación directa de los datos y, en su lugar, trabajar con copias inmutables de los datos y utilizar funciones puras que no tengan efectos secundarios.

La separación de los datos de las funciones en la programación funcional se basa en los siguientes principios:

1. Inmutabilidad de los datos: En lugar de modificar directamente los datos existentes, se crean nuevas estructuras de datos inmutables que representan los cambios necesarios. Esto asegura que los datos originales no se alteren y facilita el razonamiento sobre el flujo de datos.
2. Funciones puras: Las funciones puras son aquellas que no tienen efectos secundarios y siempre producen el mismo resultado dado el mismo conjunto de argumentos. No modifican los datos de entrada y no dependen de variables globales. Las funciones puras toman datos como entrada y generan nuevos datos como salida sin alterar los datos originales.
3. Composición de funciones: En lugar de realizar operaciones directamente sobre los datos, se combinan funciones más pequeñas y modulares para construir operaciones más complejas. La composición de funciones permite una mayor reutilización del código y facilita el mantenimiento y la comprensión del programa.
4. Datos como argumentos de funciones: Los datos se pasan como argumentos a las funciones, lo que permite que las funciones sean independientes de los datos específicos. Esto promueve la reutilización de las funciones con diferentes conjuntos de datos y facilita las pruebas y el razonamiento sobre el comportamiento de las funciones.

La separación de datos y funciones en la programación funcional ayuda a crear programas más modulares, legibles y mantenibles. Al seguir estos principios, se puede lograr un código más limpio, menos propenso a errores y más fácil de razonar sobre el flujo de datos y las transformaciones que ocurren en el programa.

```jsx
// Función pura para duplicar un número
function duplicar(numero) {
  return numero * 2;
}

// Datos
const numeroOriginal = 5;

// Llamada a la función con los datos como argumento
const numeroDuplicado = duplicar(numeroOriginal);

console.log(numeroDuplicado); // Output: 10
```

En este ejemplo, la función **`duplicar`** es una función pura que toma un número como argumento y devuelve el doble del número. La función no modifica directamente el número original, sino que crea un nuevo valor basado en él y lo devuelve como resultado.

Los datos se mantienen separados de la función y se pasan como argumento al llamar a la función. La función **`duplicar`** opera solo en el dato que se le pasa, sin afectar los datos originales.

Este ejemplo muestra cómo la función **`duplicar`** es independiente de los datos específicos y puede ser reutilizada con diferentes números de entrada. La separación de datos y funciones permite un código más modular y fácilmente comprensible, ya que las operaciones sobre los datos se realizan a través de funciones puras sin efectos secundarios.

### Funciones de orden Superior

Las funciones de orden superior (Higher Order Functions) son funciones que pueden recibir otras funciones como argumentos y/o devolver funciones como resultado. En JavaScript, las funciones son ciudadanos de primera clase, lo que significa que se pueden tratar como cualquier otro valor, como cadenas de texto o números. Esto permite utilizar funciones como argumentos de otras funciones y devolver funciones desde una función.

Hay varias formas de utilizar las funciones de orden superior en JavaScript:

1. Pasar una función como argumento: Se puede pasar una función como argumento a otra función. Esto permite que la función receptora utilice la función pasada como argumento dentro de su implementación.
2. Devolver una función como resultado: Una función puede devolver otra función como resultado. Esto permite la creación de funciones especializadas o funciones que generan otras funciones.
3. Almacenar una función en una variable: Una función se puede asignar a una variable y, luego, esa variable se puede usar para invocar la función como si fuera cualquier otra función.

Las funciones de orden superior son fundamentales en la programación funcional, ya que permiten abstracciones y permiten escribir código más modular y reutilizable. Al usar funciones de orden superior, se pueden crear abstracciones más poderosas y expresivas, ya que se pueden componer funciones y pasar comportamientos personalizados a través de funciones como argumentos.

```jsx
// Higher Order functions es un termino muy común con la programación funcional.

// Ya los hemos visto, un Higher order function es una función que toma o retorna una función como argumento. y basicamente la mayoria de Array Methods son HOF

const carrito = [
  { nombre: "Monitor 20 Pulgadas", precio: 500 },
  { nombre: "Televisión 50 Pulgadas", precio: 700 },
  { nombre: "Tablet", precio: 300 },
  { nombre: "Audifonos", precio: 200 },
  { nombre: "Teclado", precio: 50 },
  { nombre: "Celular", precio: 500 },
  { nombre: "Bocinas", precio: 300 },
  { nombre: "Laptop", precio: 800 },
];

// Si quisieramos obtener todos los productos que tienen un precio mayor a 400 tendriamos que hacer lo siguiente..

// const resultado = carrito.filter( producto => {
//     return producto.precio > 400
// } )

// console.log(resultado);

// Este ejemplo es un HOF porque .filter esta tomando una función como argumento, ese producto es un Arrow Function, pero puedes dejarlo de la sig forma,..

const mayor400 = (producto) => {
  return producto.precio > 400;
};

const resultado = carrito.filter(mayor400);
console.log(resultado);
```

En este caso, la función **`filter`** es una Higher Order Function porque toma una función como argumento.

La función **`filter`** recibe una función de retorno (callback) como argumento, en este caso la función **`mayor400`**, que determina si un producto cumple con cierta condición. La función **`mayor400`** devuelve **`true`** si el precio del producto es mayor a 400, y **`false`** en caso contrario.

Al llamar a **`carrito.filter(mayor400)`**, se está utilizando **`filter`** como una Higher Order Function para filtrar los elementos del arreglo **`carrito`** y obtener solo aquellos productos que cumplen con la condición definida en la función **`mayor400`**. El resultado se almacena en la variable **`resultado`**, que contendrá un nuevo arreglo con los productos cuyo precio es mayor a 400.

Este es un ejemplo práctico del uso de una Higher Order Function en la programación funcional, donde se utiliza una función como argumento para aplicar un comportamiento personalizado a un proceso de filtrado.

## 26.5 Funciones de Orden Superior (Higher Order Functions) más Comunes

En JavaScript, hay varias funciones de orden superior integradas en el lenguaje y en la API de JavaScript. Son funciones que cumplen al menos uno de los siguientes criterios:

1. Aceptan una o más funciones como argumentos.
2. Devuelven una función como resultado.

Estas funciones son fundamentales en la programación funcional, ya que permiten una mayor abstracción, modularidad y reutilización del código. Al trabajar con funciones de orden superior, los desarrolladores pueden crear funciones más genéricas y componibles que pueden ser aplicadas a diferentes tipos de datos y operaciones.

#### Algunas de las funciones de orden superior más comunes son las siguientes:

1. **`map`**: Recorre un arreglo y aplica una función a cada elemento, devolviendo un nuevo arreglo con los resultados de aplicar la función a cada elemento, sin duda es uno de las funciones mas utilizadas.
2. **`filter`**: Recorre un arreglo y devuelve un nuevo arreglo con los elementos que cumplen con una determinada condición especificada en una función.
3. **`reduce`**: Aplica una función a un acumulador y a cada elemento de un arreglo, reduciendo el arreglo a un único valor. Puede utilizarse para realizar operaciones como sumas, promedios, concatenaciones, entre otras.
4. **`forEach`**: Recorre un arreglo y ejecuta una función en cada elemento, sin devolver un nuevo arreglo. Se utiliza principalmente para efectuar acciones en cada elemento, como realizar operaciones de lado o modificar el arreglo original.
5. **`sort`**: Ordena los elementos de un arreglo en función de una función de comparación especificada. La función de comparación define el criterio de ordenamiento.
6. **`find`** y **`findIndex`**: Recorren un arreglo y devuelven el primer elemento que cumple con una condición especificada en una función. **`find`** devuelve el elemento encontrado y **`findIndex`** devuelve el índice del elemento encontrado.
7. **`some()`**: Verifica si al menos un elemento de un arreglo cumple con una condición dada por una función de prueba.
8. **`every()`**: Verifica si todos los elementos de un arreglo cumplen con una condición dada por una función de prueba.

Estas son solo algunas de las funciones de orden superior más utilizadas en JavaScript. Sin embargo, hay muchas más disponibles en el lenguaje y también es posible crear funciones de orden superior personalizadas para adaptarse a necesidades específicas.

Las funciones de orden superior permiten a los desarrolladores de software escribir código más genérico y reutilizable, ya que pueden ser aplicadas a diferentes tipos de datos y operaciones. Además, al utilizar funciones de orden superior, se fomenta la inmutabilidad y la ausencia de efectos secundarios, lo que puede mejorar la legibilidad y mantenibilidad del código.

#### ejemplo utilizando la función **`map()`**

Este ejemplo utiliza la función **`map()`** como una función de orden superior para transformar un arreglo de objetos en un arreglo de nombres de productos.

```jsx
// Utilizando MAP
const carrito = [
  { nombre: "Monitor 20 Pulgadas", precio: 500 },
  { nombre: "Televisión 50 Pulgadas", precio: 700 },
  { nombre: "Tablet", precio: 300 },
  { nombre: "Audifonos", precio: 200 },
  { nombre: "Teclado", precio: 50 },
  { nombre: "Celular", precio: 500 },
  { nombre: "Bocinas", precio: 300 },
  { nombre: "Laptop", precio: 800 },
];

const obtenerNombres = (producto) => {
  return producto.nombre;
};

const resultado = carrito.map(obtenerNombres);
console.log(resultado);
```

La función **`map()`** recibe como argumento una función de transformación, en este caso, la función **`obtenerNombres`**. La función **`obtenerNombres`** toma un objeto **`producto`** y devuelve el valor de su propiedad **`nombre`**.

Al llamar a **`carrito.map(obtenerNombres)`**, se aplica la función **`obtenerNombres`** a cada elemento del arreglo **`carrito`** y se obtiene un nuevo arreglo que contiene solo los nombres de los productos.

El resultado se almacena en la variable **`resultado`** y se muestra en la consola con **`console.log(resultado)`**. El resultado será un arreglo que contiene los nombres de los productos del carrito.

Este ejemplo ilustra cómo la función **`map()`** es una función de orden superior que permite transformar un arreglo aplicando una función de transformación a cada elemento. Esto proporciona una forma concisa de obtener una nueva colección de datos basada en una propiedad específica de los objetos en el arreglo original.
