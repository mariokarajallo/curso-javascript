# Sección 27: **Dominando Javascript**

## 27.1 Scope

El término "scope" se refiere al alcance o ámbito de visibilidad de las variables, funciones y objetos en un programa. Define las partes de un programa en las que una variable, función u objeto puede ser referenciado y accedido.

JavaScript utiliza dos tipos principales de scope: el scope global y el scope local.

### Scope Global

Es el alcance más amplio en JavaScript y se refiere al contexto global del programa. Las variables y funciones declaradas en el ámbito global están disponibles en todo el programa, es decir, se pueden acceder desde cualquier parte del código. Las variables globales pueden ser útiles para almacenar información que necesita ser compartida entre diferentes partes de un programa, pero su uso excesivo puede llevar a problemas de mantenimiento y posibles conflictos entre variables.

```jsx
let variableGlobal = "Soy una variable global";

function mostrarVariable() {
  console.log(variableGlobal);
}

mostrarVariable(); // Muestra "Soy una variable global"
```

```jsx
var nombre = "Juan"; // Variable global

function saludar() {
  console.log("Hola, " + nombre); // Accede a la variable global 'nombre'
}

saludar(); // Salida: "Hola, Juan"
```

En este ejemplo, la variable**`nombre`** se declara en el ámbito global y se puede acceder tanto dentro como fuera de la función **`saludar()`**.

### Scope Local

También conocido como scope de función o scope bloque, se refiere a los ámbitos que se crean dentro de las funciones o bloques de código (como un bucle o una condición if). Las variables y funciones declaradas dentro de un ámbito local solo son accesibles dentro de ese ámbito y no pueden ser referenciadas desde fuera. Las variables locales ayudan a evitar conflictos entre variables y facilitan la comprensión del flujo de datos en un programa.

```jsx
function mostrarVariableLocal() {
  let variableLocal = "Soy una variable local";
  console.log(variableLocal);
}

mostrarVariableLocal(); // Muestra "Soy una variable local"
console.log(variableLocal); // Error: variableLocal no está definida
```

```jsx
function saludar() {
  var mensaje = "Hola"; // Variable local dentro de la función

  console.log(mensaje); // Accede a la variable local 'mensaje'
}

saludar(); // Salida: "Hola"
console.log(mensaje); // Error: 'mensaje' no está definido fuera de la función
```

En este caso, la variable mensaje se declara dentro de la función saludar(), lo que significa que solo es accesible dentro de esa función. Si intentas acceder a la variable fuera de la función, se producirá un error.

#### Scope Local "lexical" o "estático"

El scope local también puede tener un ámbito "lexical" o "estático", lo que significa que un ámbito interno tiene acceso a las variables de su ámbito externo, pero el ámbito externo no puede acceder a las variables del ámbito interno.

```jsx
function crearContador() {
  var contador = 0; // Variable local en el ámbito de crearContador()

  function incrementar() {
    contador++; // Accede a la variable del ámbito externo
    console.log(contador);
  }

  return incrementar;
}

var contadorA = crearContador();
contadorA(); // Salida: 1
contadorA(); // Salida: 2

var contadorB = crearContador();
contadorB(); // Salida: 1
```

En este ejemplo, la función **`crearContador()`** devuelve otra función **`incrementar()`**. La variable **`contador`** se declara en el ámbito de **`crearContador()`**, pero la función **`incrementar()`** tiene acceso a ella incluso después de que **`crearContador()`** haya finalizado su ejecución. Cada vez que se llama a la función devuelta (**`contadorA()`** y **`contadorB()`**), se incrementa y se conserva el valor de **`contador`**.

#### Block Scope

Además, con la introducción de las palabras clave **let** y **const** en ECMAScript 6 (ES6), JavaScript también admite el "block scope". Esto significa que las variables declaradas con **let** y **const** tienen un alcance limitado al bloque de código en el que se encuentran, como bucles y bloques condicionales.

```jsx
if (true) {
  let variableDeBloque = "Soy una variable de bloque";
  console.log(variableDeBloque); // Muestra "Soy una variable de bloque"
}

console.log(variableDeBloque); // Error: variableDeBloque no está definida
```

El entendimiento y manejo adecuado del scope es importante para evitar colisiones de nombres de variables, proteger los datos y modularizar el código de manera eficiente en programas JavaScript.

## 27.2 Hoisting

El hoisting en JavaScript es un comportamiento especial que ocurre durante la fase de compilación del código. Consiste en el movimiento automático de las declaraciones de variables y funciones al inicio de su ámbito, sin importar dónde se haya realizado la declaración en el código.

En otras palabras, JavaScript "eleva" las declaraciones de variables y funciones al principio de su ámbito, lo que permite utilizarlas antes de que se declaren explícitamente en el código. Sin embargo, es importante tener en cuenta que solo las declaraciones se elevan, no las inicializaciones o asignaciones.

### Hoisting Variables

Cuando se utilizan las palabras clave **var**, las declaraciones de variables se elevan al inicio de su ámbito, pero se inicializan con **undefined**.

Si se utilizan **let** y **const**, las declaraciones también se elevan, pero no se inicializan, lo que da como resultado un error si se intenta acceder a ellas antes de su declaración.

Ejemplo con **var**:

```jsx
console.log(miVariable); // Muestra "undefined"
var miVariable = 10;
console.log(miVariable); // Muestra "10"
```

```jsx
console.log(nombre); // Salida: undefined
var nombre = "Juan";
```

En este ejemplo, aunque la variable **`nombre`** se utiliza antes de ser declarada, no se produce un error. Esto se debe a que durante la fase de compilación, la declaración de la variable se "eleva" al principio del ámbito. Sin embargo, en ese momento, la variable no tiene un valor asignado, por lo que su valor es **`undefined`**.

Ejemplo con **let**:

```jsx
console.log(miVariable); // Error: miVariable no está definida
let miVariable = 10;
console.log(miVariable); // Muestra "10"
```

### Hoisting con Funciones:

Las declaraciones de funciones se elevan al inicio de su ámbito junto con su cuerpo, lo que permite llamar a una función antes de que sea declarada en el código.

```jsx
saludar(); // Salida: "Hola"

function saludar() {
  console.log("Hola");
}
```

En este caso, la función **`saludar()`** se llama antes de su declaración en el código. Gracias al hoisting, la declaración de la función se mueve al principio del ámbito, lo que permite su invocación antes de la declaración real.

### Diferencia entre function Declarations & Expressions

El hoisting en JavaScript se aplica tanto a las funciones declarativas como a las expresivas, pero hay diferencias sutiles en su comportamiento.

Veamos ejemplos de hoisting con ambos tipos de funciones:

#### Hoisting con funciones declarativas:

```jsx
saludar(); // Salida: "Hola"

function saludar() {
  console.log("Hola");
}
```

En este caso, la función **`saludar()`** se declara utilizando la sintaxis de función declarativa. Aunque se llama a la función antes de su declaración en el código, el hoisting mueve la declaración de la función al principio del ámbito y luego lo ejecuta, lo que permite su invocación exitosa.

#### Hoisting con funciones expresivas:

```jsx
saludar(); // Error: saludar is not a function

var saludar = function () {
  console.log("Hola");
};
```

En este ejemplo, la función **`saludar`** se declara utilizando la sintaxis de función expresiva asignada a una variable. Al intentar llamar a la función antes de su declaración, se produce un error. A diferencia de las funciones declarativas, solo la declaración de la variable **`saludar`** se eleva al principio del ámbito, no la asignación de la función en sí. Por lo tanto, al intentar llamar a **`saludar()`** antes de asignar la función, se produce un error, ya que en ese momento, **`saludar`** es **`undefined`**.

Es importante destacar que, aunque las declaraciones de funciones se "elevan" durante la fase de compilación, el hoisting no se aplica a las asignaciones de variables u objetos. Solo las declaraciones de variables y funciones se ven afectadas por el hoisting. Por eso, en el caso de las funciones expresivas, es importante asegurarse de que la asignación se realice antes de intentar llamar a la función.

Sin embargo, aunque el hoisting puede resultar útil en algunos casos, se recomienda mantener un código claro y legible, evitando depender demasiado de este comportamiento. Es una buena práctica declarar las variables y funciones en su posición adecuada antes de utilizarlas, para evitar confusiones y errores.

## 27.3 Coercion

La `coerción` en JavaScript es el proceso mediante el cual los valores de un tipo de datos se convierten automáticamente a otro tipo de datos durante una operación.

JavaScript realiza la `coerción` de manera implícita para adaptar los valores y permitir realizar operaciones entre diferentes tipos de datos.

Existen dos tipos de coerción en JavaScript: coerción implícita (o automática) y coerción explícita (o manual).

### Coerción implícita:

La coerción implícita ocurre cuando JavaScript convierte automáticamente un valor de un tipo de datos a otro tipo de datos sin que se realice una conversión explícita en el código.

Esto puede suceder en situaciones como la concatenación de cadenas de texto y números, operaciones aritméticas, comparaciones o evaluaciones lógicas.

Ejemplo de coerción implícita:

```jsx
var numero = 10;
var texto = "El número es: " + numero;

console.log(texto); // Salida: "El número es: 10"

const num1 = 1;
const num2 = "2";

console.log(num1 + num2); // "3"
```

En este caso, se realiza una concatenación de una cadena de texto y un número. JavaScript realiza automáticamente la coerción del número a una cadena de texto para poder concatenarlos.

### Coerción explícita:

La coerción explícita ocurre cuando se realiza una conversión manual de un tipo de dato a otro mediante el uso de funciones o métodos específicos. Esto permite controlar y forzar la conversión de un tipo de dato a otro según nuestras necesidades.

Ejemplo de coerción explícita:

```jsx
var numero = "5";
var numeroEntero = parseInt(numero);

console.log(numeroEntero); // Salida: 5
```

En este caso, se utiliza la función **`parseInt()`** para convertir explícitamente la cadena de texto **`"5"`** a un número entero. La coerción explícita nos permite especificar el tipo de conversión que deseamos realizar.

Es importante tener en cuenta que la coerción puede tener implicaciones en la precisión y el comportamiento de las operaciones, por lo que es fundamental comprender cómo se realizan las conversiones automáticas en JavaScript y tener cuidado al utilizar la coerción en nuestros programas.

## 27.4 Implicit Binding

El "implicit binding" (enlace implícito) es un concepto que se refiere a la forma en que JavaScript determina automáticamente el valor de **`this`** dentro de un objeto en función del contexto de ejecución.

En JavaScript, la palabra clave **`this`** se refiere al objeto en el que se está ejecutando actualmente un fragmento de código. El "implicit binding" establece que, cuando se llama a un método en un objeto, el valor de **`this`** dentro de ese método se establecerá automáticamente como el objeto en sí mismo.

Veamos un ejemplo para entenderlo mejor:

```jsx
var persona = {
  nombre: "Juan",
  edad: 30,
  saludar: function () {
    console.log("Hola, mi nombre es " + this.nombre);
  },
};

persona.saludar(); // Salida: "Hola, mi nombre es Juan"
```

En este caso, **`persona`** es un objeto que tiene una propiedad **`nombre`** y un método **`saludar`**. Cuando se llama al método **`saludar()`** en el objeto **`persona`**, el valor de **`this`** dentro de ese método se establecerá automáticamente como **`persona`**. Por lo tanto, podemos acceder a la propiedad **`nombre`** del objeto utilizando **`this.nombre`**.

El enlace implícito es útil para acceder a las propiedades y métodos de un objeto desde su propio contexto. Sin embargo, es importante tener en cuenta que el valor de **`this`** en JavaScript puede cambiar dependiendo del contexto de ejecución y la forma en que se llama a una función. Por lo tanto, es importante comprender cómo se establece **`this`** en diferentes situaciones, como el enlace implícito, explícito o mediante el uso de arrow functions.
