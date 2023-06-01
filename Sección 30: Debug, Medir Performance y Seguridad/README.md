# Sección 30: **Debug, Medir Performance y Seguridad**

## 30.1 Performance.now()

En JavaScript, la función **`performance.now()`** se utiliza para medir el rendimiento y la precisión temporal de tu código. Proporciona un valor de tiempo de alta resolución y se utiliza comúnmente para medir el tiempo transcurrido entre dos puntos en el código, lo que permite evaluar el rendimiento de una función o sección específica.

La función **`performance.now()`** devuelve un valor de tipo **`DOMHighResTimeStamp`**, que representa el número de milisegundos transcurridos desde que se cargó la página o la aplicación. La precisión de este valor depende de la implementación del navegador y el sistema operativo, pero generalmente se mide con una resolución de microsegundos (1/1000 de milisegundo). A diferencia de otras funciones de tiempo en JavaScript, como **`Date.now()`** que tiene una precisión en milisegundos, **`performance.now()`** ofrece una mayor precisión temporal.

Aquí hay un ejemplo sencillo de cómo puedes utilizar **`performance.now()`** para medir el rendimiento de una porción de código en JavaScript:

```jsx
// Inicio de la medición
const startTime = performance.now();

// Código que deseas medir
for (let i = 0; i < 1000000; i++) {
  // Realizar operaciones aquí
}

// Fin de la medición
const endTime = performance.now();

// Calcular la duración en milisegundos
const duration = endTime - startTime;

console.log(`El código tardó ${duration} milisegundos en ejecutarse.`);
```

- En este ejemplo, se utiliza **`performance.now()`** para capturar la marca de tiempo antes y después de ejecutar un bucle que realiza alguna tarea repetitiva. Al restar **`startTime`** de **`endTime`**, obtendrás la duración en milisegundos que tardó en ejecutarse ese código específico.

Esta función es especialmente útil cuando deseas medir el rendimiento de diferentes algoritmos, funciones o enfoques para encontrar el más eficiente.

Recuerda que **`performance.now()`** puede variar ligeramente en su valor cada vez que se llama, puede variar en diferentes entornos y navegadores, y su precisión depende de la capacidad del hardware y la implementación del navegador en sí. Por lo que se recomienda realizar múltiples mediciones y calcular promedios para obtener resultados más precisos. Sin embargo, en general, se considera una forma confiable de medir el rendimiento dentro del navegador para optimizar y mejorar la eficiencia de tu código JavaScript.

## 30.2 Async o Defer?

**async** y **defer** son atributos que se pueden agregar a la etiqueta **<script>** en HTML para controlar cómo se carga y se ejecuta un archivo JavaScript externo en relación con la carga de la página.

### Async

- Cuando se agrega el atributo **async** a una etiqueta **<script>**, el archivo JavaScript se carga de forma asíncrona. Esto significa que el navegador no bloqueará la carga y el procesamiento del contenido HTML mientras descarga y ejecuta el archivo JavaScript. En su lugar, el archivo se descargará en paralelo y se ejecutará tan pronto como esté disponible. Esto puede mejorar el rendimiento de la página, pero también puede causar problemas si el script depende de elementos del DOM que aún no se han cargado.
- Es importante tener en cuenta que el orden de ejecución de múltiples scripts con **`async`** no está garantizado. Si hay varios scripts con el atributo **`async`**, pueden ejecutarse en cualquier orden según su disponibilidad, lo que puede afectar la lógica de tu código si dependes del orden de ejecución.
  Ejemplo:
  ```jsx
  <script async src="script.js"></script>
  ```

### Defer

- El atributo **defer** también permite la carga asíncrona de un archivo JavaScript, pero con una diferencia clave: el script se ejecutará solo después de que se haya cargado y analizado todo el contenido HTML. Esto garantiza que el script se ejecute en el orden correcto y que todos los elementos del DOM estén disponibles antes de que se ejecute el script. El atributo **defer** es útil cuando se tienen scripts que dependen de elementos del DOM o cuando se necesita mantener el orden de ejecución de varios scripts.
- A diferencia de **`async`**, el uso de **`defer`** garantiza que el script se ejecute después de que el documento HTML haya sido analizado, lo que permite que el script manipule elementos HTML existentes sin bloquear la carga de la página.
  Ejemplo:
      ```jsx
      <script defer src="script.js"></script>
      ```

### Aquí hay un ejemplo para ilustrar cómo se utilizan **`async`** y **`defer`** en las etiquetas **`<script>`**:

```jsx
<!DOCTYPE html>
<html>
<head>
  <title>Ejemplo de async y defer</title>
  <script src="script1.js" async></script>
  <script src="script2.js" defer></script>
</head>
<body>
  <!-- Contenido de la página -->
</body>
</html>
```

- En este ejemplo, el archivo "script1.js" se descargará de manera asíncrona y se ejecutará tan pronto como esté disponible, sin bloquear la carga de la página.
- Por otro lado, el archivo "script2.js" se descargará de manera asíncrona, pero se ejecutará después de que el documento HTML haya sido analizado, asegurando el orden de ejecución.

En resumen, **`async`** y **`defer`** son atributos que se utilizan para controlar la forma en que los archivos de script se descargan y ejecutan en una página web, brindando opciones para optimizar la carga y ejecución de los scripts. La elección entre **`async`** y **`defer`** depende de las necesidades específicas de tu código y del orden en el que se deben ejecutar los scripts.

La principal diferencia entre ellos es el momento en que se ejecutan los scripts: **async** ejecuta el script tan pronto como esté disponible, mientras que **defer** espera hasta que se haya cargado y analizado todo el contenido HTML.
