# Sección 25: **Async Await**

## 25.1 ¿Que es Try Catch?

### Try catch

En programación, **try-catch** es una estructura de control que se utiliza para manejar errores en tiempo de ejecución. Básicamente, permite que el programa intente ejecutar un bloque de código y, si se produce un error, captura ese error y ejecuta un bloque de código alternativo en su lugar.

El bloque **`try`** contiene el código que puede generar una excepción, mientras que el bloque **`catch`** se utiliza para capturar y manejar esa excepción en caso de que ocurra.

Cuando se ejecuta un código dentro del bloque **`try`**, el programa monitorea si ocurre alguna excepción. Si no hay excepciones, el código se ejecuta normalmente y se salta el bloque **`catch`**. Sin embargo, si se produce una excepción dentro del bloque **`try, el programa salta a la sección`** catch` correspondiente y se ejecuta el código dentro de dicho bloque.

El uso del bloque **`try`** y **`catch`** es beneficioso porque permite que el programa continúe ejecutándose incluso si se produce un error, evitando que se detenga abruptamente. Además, brinda la oportunidad de manejar el error de manera adecuada, ya sea mostrando un mensaje de error al usuario o tomando medidas correctivas.

Aquí tienes un ejemplo sencillo en JavaScript que muestra cómo se utiliza **`try`** y **`catch`**:

```jsx
try {
  // Código que puede generar una excepción
  const num = 10 / 0; // Intentamos dividir entre cero
  console.log(num); // Esta línea no se ejecutará si se genera una excepción
} catch (error) {
  // Manejo de la excepción
  console.log("Se produjo un error:", error.message);
}
```

En este ejemplo, estamos intentando dividir el número 10 entre cero, lo cual generará una excepción porque la división por cero no está definida. En el bloque **`catch`**, capturamos la excepción y mostramos un mensaje de error que incluye el mensaje asociado al error. En este caso, imprimirá "Se produjo un error: Division by zero" en la consola.

El uso de **`try`** y **`catch`** permite que el programa controle el flujo de ejecución incluso cuando ocurren errores, lo que es especialmente útil al tratar con operaciones potencialmente problemáticas o dependientes de factores externos.

## 25.2 Que es Async Await y que es lo que hace

**`async`** y **`await`** son características de JavaScript que se utilizan para trabajar con código asíncrono de manera más fácil y legible.

En el mundo de JavaScript, muchas operaciones son asíncronas, lo que significa que su resultado no se conoce inmediatamente. En lugar de esperar a que se complete una operación antes de continuar con el resto del código, JavaScript permite que el programa continúe ejecutándose mientras espera a que se complete la operación asincrónica.

Para trabajar con código asíncrono de manera efectiva, se utilizan las funciones **`async`** y **`await`**. Cuando se define una función como **`async`**, se convierte en una función asíncrona que devuelve una promesa. Significa que la función se ejecutará en segundo plano mientras el programa continúa su ejecución, sin bloquear el hilo principal. Además, las funciones asíncronas siempre devuelven una promesa. Las promesas son objetos que representan un valor que puede estar disponible ahora, en el futuro, o nunca.

La palabra clave **`await`** solo puede ser utilizada dentro de una función definida como **`async`**. Cuando se llama a una función que devuelve una promesa con la palabra clave **`await`**, el programa espera hasta que la promesa se resuelva o rechace antes de continuar con el código. Básicamente, **`await`** pausa la ejecución de la función hasta que la promesa se resuelva, y luego devuelve el resultado de la promesa.

Aquí tienes unos ejemplos sencillos que ilustra el uso de **`async`** y **`await`**:

En este ejemplo, tenemos una función **`ejemploAsync`** que se declara como **`async`**. Dentro de esta función, utilizamos **`await`** para esperar 2 segundos utilizando la función **`delay`**. Después de esperar, se imprime un mensaje en la consola y se devuelve la cadena "Fin de la función".

```jsx
function delay(ms) {
  return new Promise((resolve) => setTimeout(resolve, ms));
}

async function ejemploAsync() {
  console.log("Inicio de la función");

  await delay(2000); // Esperamos 2 segundos

  console.log("Después de esperar");

  return "Fin de la función";
}

//La función ejecutar se declara como async tambien. Dentro de esta función, utilizamos await para esperar a que la función ejemploAsync se complete.

async function ejecutar() {
  //El resultado se almacena en la variable resultado y se imprime en la consola.
  try {
    const resultado = await ejemploAsync();
    console.log(resultado);

    //Si ocurre algún error durante la ejecución de ejemploAsync, se captura en el bloque catch y se muestra un mensaje de error.
  } catch (error) {
    console.log("Se produjo un error:", error);
  }
}

//Al ejecutar la funcion ejecutar(), verás que el programa espera 2 segundos antes de imprimir "Después de esperar" y "Fin de la función" en la consola.
ejecutar();
```

Aquí veremos otro ejemplo:

El código muestra cómo usar **`async`** y **`await`** para esperar la resolución de una promesa antes de continuar con la ejecución del código. Esto permite un flujo de ejecución más controlado y legible, y evita el anidamiento excesivo de funciones de devolución de llamada (callbacks).

```jsx
// Async Await
//Definimos una función llamada descargarClientes que devuelve una promesa.
// Esta promesa se resuelve después de 3 segundos (3000 milisegundos) y devuelve un mensaje de éxito o un mensaje de error dependiendo del valor de la variable error.
function descargarClientes() {
  return new Promise((resolve, reject) => {
    const error = true;

    setTimeout(() => {
      if (!error) {
        resolve("El Listado de Clientes se descargo correctamente");
      } else {
        reject("No se pudo aplicar el descuento");
      }
    }, 3000);
  });
}

// Async await
// Definimos una función llamada ejecutar con la palabra clave async, lo que indica que es una función asíncrona.
// Dentro de la función ejecutar, utilizamos try y catch para manejar los errores.
async function ejecutar() {
  try {
    console.log("Me ejecuto antes del await");
    //Utilizamos la palabra clave await para esperar a que la función descargarClientes se resuelva. Esto detiene la ejecución del código hasta que se resuelva la promesa.
    //Una vez que la promesa se resuelve, continuamos con la ejecución y almacenamos el resultado en la variable respuesta.
    const respuesta = await descargarClientes();
    console.log(
      "Me ejecuto luego de esperar una respuesta del promise y ahi recien puedo ejecutarme"
    );
    console.log(respuesta);
    //Si se produce algún error durante la ejecución de la promesa, se captura en el bloque catch y se muestra en la consola.
  } catch (error) {
    console.log(error);
  }
}
ejecutar();

console.log(2 + 2); // Este código se continua ejecutando mientras que el await sigue esperando por su respuesta
```

Los **`async`** y **`await`** son herramientas poderosas que simplifican la escritura de código asíncrono en JavaScript, permitiendo una sintaxis más clara y fácil de entender cuando se trabaja con promesas y tareas asíncronas.

## 25.3 Async Await en function express y Declaration

### Antes hablemos del `Hoisting`

El hoisting es un comportamiento en JavaScript donde las declaraciones de variables y funciones se mueven al principio del ámbito en el que se encuentran, antes de que se ejecute el código.

En otras palabras, cuando se declara una variable o función en JavaScript, el intérprete de JavaScript mueve esa declaración al principio del ámbito en el que se encuentra, antes de que se ejecute cualquier otra línea de código en ese ámbito. Esto significa que se puede utilizar una variable o función antes de que se declare explícitamente en el código.

Sin embargo, es importante tener en cuenta que solo la declaración se mueve al principio del ámbito, no la asignación. Por lo tanto, si se utiliza una variable antes de asignarle un valor, su valor será "undefined".

Por ejemplo, considera el siguiente código:

```jsx
console.log(miVariable); // undefined
var miVariable = 10;
```

En este caso, la declaración de la variable "miVariable" se mueve al principio del ámbito, pero la asignación no. Por lo tanto, cuando se intenta imprimir el valor de "miVariable" antes de asignarle un valor, se imprime "undefined".

Es importante tener en cuenta que el hoisting puede ser confuso y puede llevar a errores sutiles en el código. Pues, es una buena práctica declarar todas las variables y funciones al principio del ámbito para evitar problemas.

La diferencia principal entre una función de expresión y una función de declaración en relación con el uso de `async` y `await` radica en cómo se definen y se accede a ellas.

### Asyn Await en Función de expresión:

Una función de expresión se define asignando una función anónima a una variable o constante, en este caso, la variable se convierte en un nombre de referencia para la función. Estas funciones no pueden ser llamadas antes de su definición en el código y, por lo tanto, no están sujetas al hoisting. Son adecuadas para casos en los que solo necesitas llamar la función después de definirla.
Puede utilizar `async` y `await` dentro de una función de expresión sin problemas. Aquí tienes un ejemplo:

```jsx
const miFuncion = async function () {
  // Código usando async y await
};
```

En este caso, la función se asigna a la variable `miFuncion`, y puede ser invocada llamando a `miFuncion()`. Puedes usar `async` y `await` dentro de la función sin ninguna restricción.

### Async Await en funciones de declaración:

Una declaración de función se define utilizando la palabra clave `function` seguida de un nombre de función, los parámetros de entrada entre paréntesis y luego el cuerpo de la función entre llaves. Estas funciones pueden ser llamadas antes de su declaración en el código debido al concepto de "hoisting”. Por lo tanto, son adecuadas para casos en los que necesitas llamar la función antes de que se defina.
No puedes utilizar `async` y `await` directamente en una declaración de función, ya que se espera que una declaración de función devuelva un valor de función, no una promesa. Sin embargo, puedes utilizar `async` y `await` dentro de una función definida dentro de la declaración de función. Aquí tienes un ejemplo:

```jsx
function miFuncion() {
  async function otraFuncion() {
    // Código usando async y await
  }

  // Llamada a otraFuncion()
  otraFuncion();
}
```

En este caso, `miFuncion` es una declaración de función y dentro de ella se define `otraFuncion` como una función interna. Puedes usar `async` y `await` dentro de `otraFuncion`, pero no directamente en `miFuncion`.

En resumen, puedes utilizar `async` y `await` tanto en funciones de expresión como en funciones definidas dentro de declaraciones de función. Sin embargo, en una declaración de función directa, debes definir una función interna si deseas utilizar `async` y `await`. En ambos casos, las funciones asíncronas con `async` y `await` te permiten trabajar de manera más conveniente con código asincrónico y promesas.

## 25.4 ¿Como manejar múltiples awaits?

Hay algunas formas de manejar múltiples **`await`** de manera más eficiente y evitar esperar innecesariamente. Aquí te presento algunas sugerencias:

### Utilizando `await` encadenado:

Para manejar múltiples `await` de manera secuencial, puedes utilizar la sintaxis de `await` encadenado

```jsx
async function ejemplo() {
  try {
    const resultado1 = await promesa1();
    console.log(resultado1);

    const resultado2 = await promesa2();
    console.log(resultado2);

    const resultado3 = await promesa3();
    console.log(resultado3);

    // ...continuar con más await si es necesario
  } catch (error) {
    console.log(error);
  }
}
```

En este enfoque, cada `await` espera a que la promesa anterior se resuelva antes de ejecutarse. Esto garantiza una ejecución secuencial y ordenada de las promesas.

### Utilizando una estructura de bucle:

También puedes utilizar una estructura de bucle para esperar por cada promesa individualmente:

```jsx
async function ejemplo() {
  try {
    const promesas = [promesa1(), promesa2(), promesa3()];
    for (const promesa of promesas) {
      const resultado = await promesa;
      console.log(resultado);
    }
  } catch (error) {
    console.log(error);
  }
}
```

En este caso, creamos un array de promesas y luego utilizamos un bucle `for...of` para iterar sobre ellas. En cada iteración, se utiliza `await` para esperar a que la promesa se resuelva y luego se muestra el resultado.

### Paralelizar las operaciones asincrónicas con Promise.all():

Si tienes varias operaciones asincrónicas que no dependen entre sí, puedes ejecutarlas en paralelo utilizando **`Promise.all()`**. Esto permite que se ejecuten al mismo tiempo y no tengas que esperar por una para iniciar la siguiente. El método **`Promise.all()`** recibe un array de promesas y devuelve una promesa que se resuelve cuando todas las promesas del array se han resuelto.

Ejemplo:

```jsx
async function obtenerDatos() {
  try {
    const respuesta = await Promise.all([promesa1(), promesa2()]);
    console.log(respuesta[0]);
    console.log(respuesta[1]);
  } catch (error) {
    console.log(error);
  }
}
```

#### otro ejemplo:

En este ejemplo vemos que la primera versión utiliza múltiples **`await`** para esperar las promesas de forma secuencial, mientras que la segunda versión utiliza **`Promise.all()`** para realizar múltiples operaciones asincrónicas en paralelo y esperar a que todas se completen antes de continuar.

```jsx
// 2 O mas Async await...

// Es muy común tener 2 Async Await,  es probable que quieras en una misma función descargar los últimos 100 clientes y también los últimos 50 pedidos..

// Las primeras dos funciones, descargarNuevosClientes() y descargarUltimosPedidos(), son funciones que devuelven promesas simulando la descarga de clientes y pedidos respectivamente.
// Estas funciones tienen un temporizador setTimeout de 5 segundos antes de resolver la promesa para simular una operación asincrónica.
function descargarNuevosClientes() {
  return new Promise((resolve) => {
    console.log("Descargando Clientes....");
    setTimeout(() => {
      resolve("Los clientes fueron descargados");
    }, 5000);
  });
}

function descargarUltimosPedidos() {
  return new Promise((resolve) => {
    console.log("Descargando Pedidos....");
    setTimeout(() => {
      resolve("Los pedidos fueron descargados");
    }, 5000);
  });
}

// Async await secuencial
// se muestra una forma de manejar las operaciones asincrónicas utilizando múltiples await en una secuencia.
// const app = async () => {
//     try {
//         const clientes = await descargarNuevosClientes();
//         console.log(clientes);

//         const pedidos = await descargarUltimosPedidos();
//         console.log(pedidos);
//     } catch (error) {
//         console.log(error)
//     }
// }

// La solución optima para ejecutar varios async await, Promise.all();
// La función app() ahora utiliza await Promise.all([descargarNuevosClientes(), descargarUltimosPedidos() ])
// Recibe un array de promesas y devuelve una promesa que se resuelve cuando todas las promesas en el array se han resuelto. Esto significa que ambas descargas se realizan al mismo tiempo, en paralelo.
const app = async () => {
  try {
    ////Después de esperar a que Promise.all() se resuelva, se almacena la respuesta en la variable respuesta.
    const respuesta = await Promise.all([
      descargarNuevosClientes(),
      descargarUltimosPedidos(),
    ]);
    // Luego se imprimen los resultados en la consola, accediendo a los elementos del array respuesta utilizando respuesta[0] y respuesta[1].
    console.log(respuesta);
    console.log(respuesta[0]);
    console.log(respuesta[1]);
  } catch (error) {
    console.log(error);
  }
};
app();
```

Los tres enfoques presentados son válidos y pueden adaptarse según los requisitos específicos de tu código. Recuerda que utilizar `await` bloquea la ejecución de la función hasta que la promesa se resuelva, por lo que ten en cuenta que el tiempo de espera total aumentará si tienes múltiples `await` secuenciales.
