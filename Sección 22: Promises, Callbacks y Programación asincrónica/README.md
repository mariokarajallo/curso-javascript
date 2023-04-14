# Sección 22: **Promises, Callbacks y Programación asincrónica**

## 22.1 Código Sincrónico, código asíncrono y Callbacks

En programación, el código síncrono y el código asíncrono son dos estilos diferentes de ejecución de código.

### Código sincrónico

El código síncrono es aquel que se ejecuta en secuencia, una línea de código a la vez. Esto significa que una instrucción debe ser completada antes de que la siguiente se ejecute. En otras palabras, el código síncrono bloquea la ejecución de todo el programa hasta que una tarea se completa. Si una tarea tarda mucho en completarse, puede ralentizar todo el programa.

### Código Asíncrono

el código asíncrono es aquel que se ejecuta en segundo plano, en paralelo con otros procesos. En lugar de esperar a que una tarea se complete, el programa puede continuar ejecutando otras tareas mientras espera la finalización de una tarea asincrónica. Esto significa que el código asíncrono no bloquea la ejecución del programa, lo que permite que el programa siga siendo sensible y reactivo incluso cuando se están realizando tareas de larga duración.

En JavaScript, una función asíncrona se ejecuta en segundo plano y no bloquea la ejecución de otras tareas. En su lugar, se utiliza una función callback para notificar al programa cuando la tarea asíncrona se ha completado. Esto permite al programa continuar ejecutando otras tareas mientras espera la finalización de la tarea asíncrona.

### Callbacks

Los callbacks en JavaScript son funciones que se pasan como argumentos a otras funciones y que se invocan dentro de esas funciones en un momento determinado. El objetivo principal de los callbacks es permitir que el código asíncrono (código asíncrono se ejecuta en segundo plano) se comunique con el código sincrónico (código síncrono se ejecuta en secuencia).

En otras palabras, los callbacks se utilizan para controlar el flujo de ejecución de las funciones asíncronas. Cuando se invoca una función asíncrona, esta no bloquea la ejecución del resto del código, sino que continúa su ejecución mientras la función asíncrona se procesa en segundo plano. Cuando la función asíncrona ha terminado su procesamiento, se llama al callback para notificar que el resultado está disponible.

Un ejemplo común de un callback en JavaScript es la función **`setTimeout()`**. Esta función toma dos argumentos: una función de retorno de llamada y un tiempo en milisegundos. La función de retorno de llamada se ejecutará después del tiempo especificado en milisegundos.

```jsx
// Se crea un arreglo llamado paises que contiene algunos países.
const paises = ['Francia', 'España', 'Portugal', 'Australia', 'Inglaterra', 'Irlanda'];

// Se define la función nuevoPais, que acepta dos argumentos: 
// pais (el nombre del nuevo país que se va a agregar) y callback (la función que se va a llamar una vez que se haya agregado el nuevo país). 
// Dentro de nuevoPais, se utiliza setTimeout para simular un retraso de 2 segundos.
// Después del retraso, se agrega el nuevo país al arreglo paises y se llama al callback que se pasó como argumento.
function nuevoPais(pais, callback) {
    setTimeout( () =>  {
        paises.push(pais);
        callback();
    }, 2000  ); // Pero el segundo ya paso, y se agrega uno nuevo, ejecutamos el callback para que se vuelva a llamar la función
}

// Se define la función mostrarPaises, que utiliza setTimeout para simular un retraso de 1 segundo.
// Después del retraso, se recorre el arreglo paises y se muestra cada país por consola.
function mostrarPaises() {
    setTimeout(  () =>  {
        paises.forEach( pais =>  {
            console.log(pais)
        });
    }, 1000 ); // Después de un segundo obtenemos los paises...
}

// Se llama a mostrarPaises de forma opcional, lo que significa que se mostrarán los países actuales en el arreglo paises.
mostrarPaises();

// Se llama a nuevoPais para agregar un nuevo país llamado "Alemania". Se pasa mostrarPaises como argumento, lo que significa que se llamará a mostrarPaises (es el callback) una vez que se haya agregado el nuevo país.
nuevoPais('Alemania', mostrarPaises);
```

En resumen, este ejemplo utiliza un callback para asegurarse de que la función **`mostrarPaises`**  se ejecute después de que se haya agregado un nuevo país al arreglo **`paises`**. El **`setTimeout`**  se utiliza para simular una tarea asíncrona, lo que significa que el programa no se bloquea mientras espera que el retraso termine. El callback se llama una vez que se ha completado la tarea asíncrona para notificar al programa que puede continuar con la siguiente tarea.

## 22.2 Callback Hell

### Que es Callback Hell

Callback Hell es un término que se refiere a la situación en la que un programa JavaScript tiene varias funciones anidadas que utilizan callbacks, lo que hace que el código sea difícil de leer y mantener.

Cuando se tienen muchas tareas asíncronas que se deben realizar en orden, puede ser necesario utilizar callbacks para manejar la secuencia de eventos. Sin embargo, si no se manejan adecuadamente, los callbacks pueden resultar en una estructura de código anidada y compleja que se hace difícil de leer y entender.

Para evitar Callback Hell, existen varias técnicas alternativas que permiten manejar tareas asíncronas de manera más elegante y fácil de leer, como las Promesas o Async/Await.

Este código es un ejemplo de "Callback Hell", que se produce cuando se utilizan varios callbacks anidados para realizar tareas secuenciales. En este caso, el objetivo es agregar varios países al array "paises" y luego mostrarlos.

```jsx
// Listado de paises
const paises = [];

//se define la función "nuevoPais", que agrega un país al array, imprime un mensaje en la consola y llama al callback proporcionado.
function nuevoPais(pais, callback) {
    paises.push(pais);
    console.log(`Agregado: ${pais}`)
    callback();
}

//Se define una función llamada "mostrarPaises" simplemente imprime el contenido del array "paises" en la consola.
function mostrarPaises() {
    console.log(paises);
}
// Se define una función llamada "iniciarCallbackHell" que contiene múltiples funciones anidadas que utilizan callbacks para realizar tareas asíncronas. Esta función es la que representa el Callback Hell.
// Primero, se utiliza setTimeout para esperar 3 segundos antes de comenzar el proceso. 
// Luego, se llama a la función "nuevoPais" con el país "Alemania" y el callback "mostrarPaises".
// Después de agregar Alemania, se llama a otro setTimeout que espera 3 segundos antes de agregar Francia utilizando "nuevoPais" y "mostrarPaises" como callbacks
// A continuación, se utiliza otro setTimeout anidado para esperar otros 3 segundos antes de agregar Inglaterra.
// Finalmente, después de agregar todos los países, se llamará a la función "mostrarPaises" para imprimir el array completo en la consola.
function iniciarCallbackHell() {
    setTimeout(() => {
        // Agregar nuevo pais
        nuevoPais('Alemania', mostrarPaises); 
        setTimeout(  () =>  {
            nuevoPais('Francia', mostrarPaises);
            setTimeout(() => { 
                nuevoPais('Inglaterra', mostrarPaises);
            }, 3000);
        }, 3000 );
    }, 3000);
}

iniciarCallbackHell();
```

Este ejemplo de Callback Hell representa una situación en la que se deben realizar múltiples tareas asíncronas en un orden específico utilizando callbacks anidados. Si no se manejan adecuadamente, los callbacks pueden resultar en una estructura de código compleja y difícil de entender. Por esta razón, es recomendable utilizar otras técnicas como Promesas o Async/Await para manejar tareas asíncronas de manera más elegante y fácil de leer.