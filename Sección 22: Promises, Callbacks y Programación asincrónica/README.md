# Sección 22: **Promises, Callbacks y Programación asincrónica**

## Código Sincrónico, código asíncrono y Callbacks

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