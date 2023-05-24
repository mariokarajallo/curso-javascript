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

## 26.6 Menos cantidad de código en tus Funciones

En la programación funcional, uno de los objetivos principales es escribir código más conciso y expresivo. Esto se debe a varios principios y técnicas utilizados en la programación funcional, como el uso de funciones puras, composición de funciones y abstracciones de alto nivel. A continuación, te mencionaré algunas razones por las cuales la programación funcional puede ayudar a reducir la cantidad de código necesario:

1. Funciones puras: Las funciones puras en la programación funcional no tienen efectos secundarios y siempre producen el mismo resultado dado el mismo conjunto de argumentos. Al evitar efectos secundarios y cambios en el estado, se reduce la necesidad de escribir código adicional para manejar y rastrear el estado mutable.
2. Composición de funciones: En la programación funcional, se fomenta la composición de funciones pequeñas y modulares para construir operaciones más complejas. Esto permite reutilizar funciones existentes y evitar la repetición de código. Al componer funciones, se puede lograr la misma funcionalidad con menos líneas de código.
3. Abstracciones de alto nivel: La programación funcional promueve el uso de abstracciones de alto nivel, como funciones de orden superior y funciones de transformación de datos (como **`map`**, **`filter`** y **`reduce`**). Estas abstracciones encapsulan lógica compleja en funciones reutilizables y declarativas, lo que reduce la cantidad de código necesario para lograr una tarea específica.
4. Eliminación de bucles: En lugar de utilizar bucles tradicionales (como **`for`** o **`while`**), la programación funcional enfatiza el uso de funciones de orden superior, como **`map`**, **`filter`** y **`reduce`**, para operar sobre colecciones de datos. Estas funciones permiten expresar operaciones de manera más concisa y declarativa, eliminando la necesidad de escribir bucles explícitos.
5. Programación declarativa: La programación funcional se centra en el "qué" se debe hacer en lugar del "cómo" se debe hacer. Esto significa que te puedes concentrar en describir la lógica y las transformaciones de datos en lugar de los detalles de implementación. Esto conduce a un código más claro y conciso.

#### Ejemplo

Este ejemplo se muestran algunas formas de reducir aún más el código en la programación funcional. Al utilizar funciones flecha y nombres de parámetros más cortos, se puede lograr un código más conciso sin comprometer la legibilidad.

```jsx
// En la programación funcional también se busca tener código más corto que lo que seria una función más larga...

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

// const obtenerNombres = producto =>  producto.nombre;
// const resultado = carrito.map(obtenerNombres);

// const mayor400 = producto => producto.precio > 400
// const resultado2 = carrito.filter(mayor400);

// console.log(resultado)
// console.log(resultado2)

// Aún lo podemos recortar más cambiando la variable producto...
// En lugar de utilizar la sintaxis completa producto => producto.nombre en la función obtenerNombres
// se utiliza la sintaxis abreviada p => p.nombre, donde p es el nombre abreviado del parámetro.
// Esto reduce la cantidad de código necesario para definir la función y sigue siendo claro y comprensible.
const obtenerNombres = (p) => p.nombre;
const resultado = carrito.map(obtenerNombres);

//en la función mayor400, se utilizó p => p.precio > 400 en lugar de la versión más larga producto => producto.precio > 400.
// Esto simplifica la escritura de la función y mantiene el código más limpio y legible.
const mayor400 = (p) => p.precio > 400;
const resultado2 = carrito.filter(mayor400);

console.log(resultado);
console.log(resultado2);
```

Recuerda en la programación funcional, las funciones son valores. Se busca escribir código conciso y expresivo, utilizando funciones de orden superior, composición de funciones y abstracciones de datos. La reducción del código se logra a través de la eliminación de código redundante, la simplificación de la sintaxis y la reutilización de funciones existentes.

En resumen, la programación funcional fomenta el uso de funciones puras, composición de funciones y abstracciones de alto nivel, lo que puede ayudar a reducir la cantidad de código necesario. Al escribir código más conciso, se mejora la legibilidad, mantenibilidad y reutilización del código.

## 26.7 Pure Functions

Una función pura es una función en la programación funcional que cumple con dos características principales: no tiene efectos secundarios observables y siempre produce el mismo resultado para los mismos argumentos de entrada. Estas características hacen que las funciones puras sean predecibles, fáciles de razonar y menos propensas a errores.

#### Las características de las funciones puras son las siguientes:

1. No tiene efectos secundarios observables: Una función pura no realiza ninguna acción que afecte el estado externo o genere cambios no locales. Esto significa que no modifica variables fuera de su alcance, no altera estructuras de datos compartidas, no realiza operaciones de entrada/salida y no produce efectos colaterales. La única salida de una función pura es su valor de retorno.
2. Resultado determinista: Dada la misma entrada, una función pura siempre produce el mismo resultado. Esto significa que no hay dependencias ocultas en el estado o en el entorno externo que puedan afectar el resultado de la función. El resultado de una función pura depende únicamente de los valores de sus argumentos.

#### Beneficios de las funciones puras:

- Facilitan la comprensión y el razonamiento del código, ya que su comportamiento es predecible y no depende de factores externos.
- Favorecen la reutilización, porque al no tener efectos secundarios, pueden ser utilizadas en diferentes contextos sin generar impactos inesperados.
- Mejoran la testabilidad, pues al no depender de estado externo, las pruebas unitarias se vuelven más simples y confiables.
- Promueven la modularidad, ya que las funciones puras se pueden combinar fácilmente mediante composición para construir lógica más compleja.

#### Ejemplo

```jsx
function sumar(a, b) {
  return a + b;
}

console.log(sumar(2, 3)); //5
```

La función **`sumar`** es pura porque no realiza ningún efecto secundario y siempre devuelve la suma de sus dos argumentos. No depende de ningún estado externo y el resultado es determinista para los mismos argumentos de entrada.

Es importante destacar que no todas las funciones en un programa deben ser puras, ya que a menudo se necesitan efectos secundarios y operaciones no puras para interactuar con el mundo exterior. Sin embargo, la programación funcional fomenta el uso de funciones puras siempre que sea posible, puesto que ofrecen numerosos beneficios en términos de comprensión, modularidad y confiabilidad del código.

## 26.8 Funciones que Retornan funciones

Una característica interesante de la programación funcional es la capacidad de que una función retorne otra función como resultado.

Estas funciones se conocen como funciones que retornan una función o funciones de orden superior. Algunas de las características de estas funciones son:

1. Retorno de funciones: Una función que retorna una función devuelve una nueva función como resultado en lugar de un valor directo. Esto permite la creación de funciones más especializadas o configurables.
2. Cierre (closure): La función retornada mantiene acceso al entorno léxico de la función que la envuelve. Esto significa que puede acceder y utilizar las variables y parámetros de la función padre incluso después de que la función padre haya finalizado su ejecución.
3. Configurabilidad: Al retornar una función, se pueden configurar y personalizar comportamientos específicos mediante la aplicación parcial de argumentos o la definición de valores predeterminados.

A continuación, se presenta un ejemplo sencillo de una función que retorna una función en JavaScript:

```jsx
function saludarFamilia(apellido) {
  return function (nombre) {
    console.log(`Hola ${nombre} ${apellido}`);
  };
}

const saludarApellidoKarajallo = saludarFamilia("Karajallo");
saludarApellidoKarajallo("Mario"); // Output: Hola Mario Karajallo
saludarApellidoKarajallo("Javier"); // Output: Hola Javier Karajallo
```

En este ejemplo, la función **`saludarFamilia`** recibe un apellido como parámetro y retorna una nueva función que toma un nombre como parámetro. La función retornada puede acceder al valor del apellido a través del cierre (closure) y combinarlo con el nombre proporcionado para imprimir un saludo personalizado.

Al llamar a **`saludarFamilia('Karajallo')`**, se obtiene una función específica que saluda a las personas con el apellido "Karajallo". Luego, se pueden invocar esa función retornada pasando diferentes nombres para obtener saludos personalizados.

Este ejemplo ilustra cómo una función puede retornar una función más especializada, permitiendo configurar comportamientos específicos y lograr una mayor flexibilidad y reutilización de código.

## 26.9 Closures

En programación funcional, los closures (cierres o clausuras) son una característica que permite a una función acceder y recordar el `ámbito léxico` (se refiere al alcance de visibilidad de variables y funciones) en el que fue creada, incluso después de que esa función haya finalizado su ejecución.

Un closure combina una función y su `Entorno léxico` (se refiere al conjunto de variables y funciones disponibles en un determinado ámbito), lo que significa que la función retiene acceso a las variables, parámetros y funciones definidas en el ámbito en el que fue creada.

El concepto de closure es importante en la programación funcional porque permite crear funciones que mantienen estado y comportamiento persistente, incluso cuando están fuera de su ámbito original. Esto facilita la creación de funciones de orden superior, funciones que retornan funciones y la implementación de patrones como el curry, la memorización y el encapsulamiento de datos.

Un ejemplo sencillo de closure en JavaScript sería el siguiente:

```jsx
function contador() {
  let count = 0;

  return function () {
    count++;
    console.log(count);
  };
}

const incrementar = contador();
incrementar(); // Output: 1
incrementar(); // Output: 2
incrementar(); // Output: 3
```

En este ejemplo, la función **`contador`** retorna una función interna que incrementa un contador cada vez que se invoca. La función interna (**`incrementar`**) mantiene acceso al ámbito léxico de la función **`contador`**, lo que le permite recordar el valor de la variable **`count`** incluso después de que la función **`contador`** haya finalizado su ejecución.

Al llamar a **`incrementar()`** varias veces, el contador se incrementa y se muestra por consola. Cada llamada a **`incrementar()`** accede y modifica el valor de **`count`** gracias al closure, lo que permite que el estado de la variable **`count`** se mantenga persistente entre las invocaciones.

```jsx
// Closure

// En JavaScript los Closures son son creados cada que una función se crea...

// Pero un closure es una forma de acceder a una función o valor, desde el exterior...

const obtenerCliente = () => {
  const nombre = "Juan";
  function muestraNombre() {
    console.log(nombre);
  }
  return muestraNombre;
};

const cliente = obtenerCliente();
cliente();
```

Este ejemplo proporcionado se ilustra la idea de closure en JavaScript. La función **`obtenerCliente`** crea una función interna llamada **`muestraNombre`** que tiene acceso al ámbito léxico de **`obtenerCliente`**, incluyendo la variable **`nombre`**. La función **`obtenerCliente`** devuelve la función **`muestraNombre`** como resultado.

Luego, al invocar **`obtenerCliente()`** y asignar su resultado a la variable **`cliente`**, se está capturando la función interna **`muestraNombre`** en el closure. Finalmente, al llamar a **`cliente()`**, se accede al valor de la variable `nombre` que se encuentra en el ámbito léxico de **`obtenerCliente`** y se muestra por consola.

El closure permite que la función interna **`muestraNombre`** acceda y recuerde el valor de **`nombre`** incluso después de que **`obtenerCliente`** haya finalizado su ejecución. Esto es posible gracias al cierre del ámbito léxico en el que se creó la función.

En resumen, el closure en este ejemplo permite que la función **`cliente`** acceda al valor de **`nombre`** que está fuera de su ámbito léxico original, lo que permite recordar y utilizar variables que ya no están en el ámbito actual.

Los closures son una poderosa herramienta en la programación funcional que permite crear funciones más flexibles, encapsular datos y mantener estado persistente. Su capacidad para mantener el contexto léxico de una función proporciona una forma eficiente y elegante de trabajar con datos y comportamientos en un entorno funcional.

## 26.10 Partials y Currying

El currying y los partials son técnicas utilizadas en programación funcional para transformar funciones y lograr una mayor flexibilidad en la aplicación de argumentos.

### Currying:

El currying es una técnica que consiste en transformar una función que toma múltiples argumentos en una secuencia de funciones que toman un solo argumento. En otras palabras, se trata de dividir una función con varios parámetros en una serie de funciones más pequeñas y especializadas, donde cada una toma un solo argumento.

#### Características del currying:

- Crea funciones más específicas y reutilizables.
- Permite aplicar parcialmente los argumentos, es decir, fijar algunos argumentos de antemano y generar una nueva función con los argumentos restantes.
- Facilita la composición de funciones.

Ejemplo de currying en JavaScript:

```jsx
function sum(a) {
  return function (b) {
    return a + b;
  };
}

const sumTwo = sum(2);
console.log(sumTwo(3)); // Output: 5
```

En este ejemplo, la función **`sum`** toma un argumento **`a`** y retorna una función interna que toma otro argumento **`b`** y realiza la suma de **`a`** y **`b`**. Al llamar a **`sum(2)`**, se genera una nueva función **`sumTwo`** que suma **`2`** al argumento que se le pase. Al invocar **`sumTwo(3)`**, se suma **`2`** y **`3`** para obtener el resultado **`5`**.

### Partials:

Los partials son una técnica relacionada con el currying que permite fijar algunos argumentos de una función y generar una nueva función con esos argumentos predefinidos. La nueva función puede luego ser utilizada con los argumentos restantes en un momento posterior.

#### Características de los partials:

- Permite fijar argumentos de una función y generar una nueva función más específica.
- Facilita la reutilización de funciones al aplicar parcialmente los argumentos.
- Puede utilizarse en combinación con el currying para lograr una mayor flexibilidad en la aplicación de argumentos.

Ejemplo de partials en JavaScript:

```jsx
function greet(greeting, name) {
  console.log(`${greeting}, ${name}!`);
}

const greetHello = (name) => greet("Hello", name);
greetHello("John"); // Output: Hello, John!
```

En este ejemplo, la función **`greet`** recibe dos argumentos: **`greeting`** y **`name`**, y muestra un saludo combinando ambos. La función **`greetHello`** es una nueva función que toma un solo argumento **`name`**. Esta función se crea utilizando una función de flecha (arrow function) y hace uso de la función **`greet`** aplicando parcialmente el argumento **`'Hello'`**.

Al llamar a **`greetHello('John')`**, se invoca la función **`greet`** con el argumento **`'Hello'`** predefinido y el argumento **`'John'`** que se pasa en la llamada a **`greetHello`**. Como resultado, se muestra el saludo **`'Hello, John!'`**.

En este caso, el partial se logra mediante el uso de una función de flecha y la aplicación parcial del argumento **`'Hello'`** en la función **`greet`**. Esto permite generar una nueva función más específica (**`greetHello`**) que solo requiere el argumento **`name`**.

#### Ejemplos

En el ejemplo, la función **`suma`** toma tres argumentos **`a`**, **`b`** y **`c`**, y devuelve la suma de los tres. Luego, se utiliza la técnica de currying para dividir la función **`suma`** en múltiples funciones más pequeñas.

```jsx
// const suma = (a, b, c ) => { // Esto podría quedar como a + b + c
//     return a + b + c;
// }

// console.log(suma(1,2,3));

// Curring es dividir  una función que toma más de un parametro, en argumentos de forma parcial...

// Podriamos agregar un Currying de la siguiente forma...

const suma = (a, b, c) => a + b + c;
```

Aquí, en ejemplo comentado, se utiliza una función **`parcial`** que toma el argumento **`a`** y devuelve una nueva función que toma los argumentos **`b`** y **`c`**. Al aplicar esta técnica, se pueden generar funciones más específicas y reutilizables. Por ejemplo, al crear la función **`primerNumero`** utilizando **`parcial(5)`**, se obtiene una función que suma **`5`** a los argumentos **`b`** y **`c`**. Luego, al invocar **`primerNumero(4, 3)`**, se obtiene el resultado de la suma: **`12`**.

Luego en el siguiente ejemplo se utiliza una estructura anidada de funciones de flecha para lograr el currying. La función **`parcial`** toma el argumento **`a`** y devuelve una función que toma el argumento **`b`** y devuelve otra función que toma el argumento **`c`**. Esto permite invocar las funciones de forma encadenada. Al crear las funciones **`primerNumero`** y **`segundoNumero`** de esta manera, se puede lograr la aplicación parcial de argumentos de forma más modular. Luego, al invocar **`segundoNumero(3)`**, se obtiene el resultado de la suma: **`12`**.

En el último ejemplo, se utiliza la función **`parcial`** para generar una función más específica directamente en una sola línea. Al utilizar **`parcial(5)(5)(3)`**, se fijan los argumentos **`5`**, **`5`** y **`3`** en la función **`suma`**. Esto genera una nueva función que toma los argumentos restantes y devuelve el resultado de la suma. Al invocar **`resultadoParcial`**, se obtiene el resultado: **`13`**.

```jsx
// const parcial = a =>
//     (b,c) =>  suma(a, b, c);

// const primerNumero = parcial(5);
// const resultado = primerNumero(4,3);
// console.log(resultado);

// Podriamos dividir más esta función suma... a que sea un argumento en cada ocasion...

const parcial = (a) => (b) => (c) => suma(a, b, c);

const primerNumero = parcial(5);
const segundoNumero = primerNumero(4);
const resultado = segundoNumero(3);

console.log(resultado);

// Otra opción seria...
const resultadoParcial = parcial(5)(5)(3);
console.log(resultadoParcial);
```

En resumen, tanto el currying como los partials son técnicas que permiten una mayor flexibilidad y reutilización de funciones en la programación funcional. El currying divide una función con múltiples argumentos en funciones más pequeñas y especializadas, mientras que los partials fijan algunos argumentos de una función para generar una nueva función más específica. Ambas técnicas son útiles para lograr una composición de funciones más modular y flexible.
