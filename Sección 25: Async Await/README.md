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
