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
