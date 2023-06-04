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
  `jsx
    <script defer src="script.js"></script>
  `

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

## 30.3. Como utilizar debugger

En JavaScript, el término "debugger" se refiere tanto a una palabra clave específica (**`debugger`**) como a las herramientas de depuración disponibles en los navegadores web y en entornos de desarrollo.

### **Palabra clave "debugger"**:

- La palabra clave **`debugger`** es utilizada en JavaScript para detener la ejecución del código en un punto específico y permitir la depuración paso a paso. Cuando se encuentra la palabra clave **`debugger`** en el código, el intérprete de JavaScript pausa la ejecución y permite al desarrollador examinar y manipular el estado actual del programa utilizando las herramientas de depuración del entorno, ya sea en un navegador web o en un entorno de desarrollo.

#### Aquí hay algunos aspectos clave sobre la palabra clave **`debugger`**:

1. **Activación del depurador**: Cuando se alcanza una instrucción **`debugger`** durante la ejecución del código, se activa el depurador en el entorno correspondiente. Esto puede ser en el navegador web si estás depurando en un entorno de cliente, o en la consola si estás utilizando Node.js para ejecutar tu código.
2. **Pausa en el punto de interrupción**: Una vez que se encuentra la instrucción **`debugger`**, la ejecución se detiene en ese punto, lo que permite al desarrollador examinar el estado actual del programa. Esto significa que puedes inspeccionar el valor de las variables, examinar la pila de llamadas, evaluar expresiones y realizar un seguimiento de la ejecución paso a paso desde ese punto en adelante.
3. **Utilización del depurador**: Una vez que el depurador se ha activado, generalmente se tienen varias opciones para interactuar con él. Estas opciones pueden incluir avanzar a la siguiente instrucción, avanzar hasta el próximo punto de interrupción, retroceder en la ejecución, inspeccionar variables, modificar valores en tiempo real y ejecutar comandos específicos para obtener información adicional.
4. **Herramientas de depuración en navegadores**: Al utilizar la palabra clave **`debugger`** en un navegador web, se abrirán las herramientas de desarrollo específicas del navegador, como Chrome DevTools o Firefox Developer Tools. Estas herramientas proporcionan una interfaz gráfica de usuario para depurar el código, y ofrecen características avanzadas como puntos de interrupción condicionales, seguimiento de eventos, perfiles de rendimiento y más.
5. **Entorno de desarrollo y Node.js**: En un entorno de desarrollo o en Node.js, la palabra clave **`debugger`** activará un depurador en la consola o en una herramienta de línea de comandos específica para Node.js. Esto permite inspeccionar y depurar el código JavaScript en tiempo real desde la terminal.

Ejemplo de uso:

```jsx
function miFuncion() {
  // Código a depurar
  debugger; // Pausa la ejecución aquí
  // Más código a depurar
}
```

En este ejemplo, la ejecución se detendrá en la línea donde se encuentra **`debugger`**, permitiendo al desarrollador examinar las variables, ejecutar instrucciones paso a paso y analizar el estado del programa.

### **Herramientas de depuración en navegadores web**:

- Los navegadores modernos, como Google Chrome, Mozilla Firefox y Microsoft Edge, proporcionan herramientas de desarrollo que incluyen capacidades de depuración. Estas herramientas permiten al desarrollador inspeccionar y depurar código JavaScript en tiempo real mientras se ejecuta en el navegador. Las herramientas de depuración generalmente incluyen características como puntos de interrupción, seguimiento de la ejecución, inspección de variables y análisis de la pila de llamadas.
- Para acceder a las herramientas de depuración en un navegador web, generalmente se debe abrir el panel de herramientas de desarrollo (presionando F12 o haciendo clic derecho y seleccionando "Inspeccionar elemento"). Luego, se debe navegar a la pestaña "Sources" o "Fuentes" (puede variar según el navegador) y allí se podrán colocar puntos de interrupción y utilizar las funcionalidades de depuración.
- Aquí tenemos una vista previa de la herramienta de depuración en chrome

<img src="./img/section-30-1.png"/>

1. El panel del Navegador de archivos. Aquí se muestra una lista de todos los archivos que la página solicita.
2. El panel del Editor de código. Después de seleccionar un archivo en el Navegador de archivos, se muestra aquí el contenido de ese archivo.
3. El panel de Depuración de JavaScript. Contiene varias herramientas para inspeccionar el JavaScript de la página. Si la ventana de las herramientas de desarrollo es ancha, este panel se muestra a la derecha del panel del Editor de código.

Las herramientas de depuración, tanto la palabra clave **`debugger`** como las disponibles en los navegadores web, son fundamentales para detectar y solucionar problemas en el código JavaScript, ya que permiten examinar el estado de las variables, seguir la ejecución del programa y analizar posibles errores o comportamientos inesperados.

## 30.4 Ofuscar el código

La ofuscación de código en JavaScript se refiere al proceso de modificar el código fuente de un programa de manera que sea más difícil de entender y leer para los humanos, sin cambiar su funcionalidad. El objetivo principal de la ofuscación es dificultar la comprensión y el análisis del código por parte de terceros, como los desarrolladores malintencionados que intentan realizar ingeniería inversa, robar propiedad intelectual o encontrar vulnerabilidades.

### La ofuscación se logra mediante técnicas como:

1. **Minificación**: Consiste en eliminar espacios en blanco, comentarios y reducir el tamaño de los nombres de variables y funciones, utilizando nombres más cortos y crípticos. Esto no altera la funcionalidad del código, pero dificulta su lectura y comprensión.
2. **Ofuscación de nombres**: Implica cambiar los nombres de variables y funciones por nombres aleatorios o sin sentido. Esto hace que el código sea más difícil de entender, ya que los nombres no proporcionan ninguna pista sobre su propósito o uso.
3. **Transformación de estructuras**: Se modifican estructuras de código, como reemplazar condicionales claros por estructuras más complejas, cambiar el orden de las declaraciones, utilizar operaciones matemáticas en lugar de literales, entre otros cambios. Estas transformaciones dificultan la lectura y el análisis del código.
4. **Encriptación**: Se utiliza en algunos casos para proteger partes sensibles del código, como claves o algoritmos, mediante técnicas de encriptación. Esto dificulta el acceso directo a la información sensible y la comprensión de su lógica interna.

### Características de la ofuscación de código JavaScript:

1. Protección de propiedad intelectual: La ofuscación ayuda a proteger el código fuente de ser copiado o reutilizado fácilmente por terceros.
2. Dificultar la ingeniería inversa: La ofuscación hace que el proceso de ingeniería inversa sea más complicado y requiera más tiempo y esfuerzo.
3. Reducción del tamaño del archivo: Al eliminar espacios en blanco y comentarios, y cambiar nombres de variables y funciones, la ofuscación puede reducir el tamaño del archivo JavaScript, lo que puede mejorar el tiempo de carga de la página.
4. Personalización: Las herramientas de ofuscación suelen ofrecer opciones de configuración para adaptarse a las necesidades específicas del proyecto.

Ejemplo de código JavaScript antes de la ofuscación:

```jsx
function suma(a, b) {
  return a + b;
}

const resultado = suma(5, 3);
console.log("El resultado es:", resultado);
```

Ejemplo de código JavaScript después de la ofuscación:

```jsx
var _0x4b22=["\x45\x6C\x20\x72\x65\x73\x75\x6C\x74\x61\x64\x6F\x20\x65\x73\x3A"];function_0x2a3c(_0x4b22,_0x2a3c){return _0x4b22[_0x2a3c]}(function(_0x4b22,_0x2a3c){var _0x5a8e=function(_0x4b22){while(--_0x4b22){_0x2a3c["\x70\x75\x73\x68"](_0x2a3c["\x73\x68\x69\x66\x74"]())}};_0x5a8e(++_0x2a3c)}(_0x4b22,0x1b3));var _0x5a8e=function(_0x4b22,_0x2a3c){_0x4b22=_0x4b22-0x0;var _0x5a8e=_0x4b22[_0x2a3c];return _0x5a8e};functionsuma(_0x2a3c,_0x5a8e){return _0x2a3c+_0x5a8e}var resultado=suma(0x5,0x3);console[_0x5a8e(0x0)](_0x5a8e(0x0),resultado);
```

### Herramientas y bibliotecas para ofuscar código JavaScript:

1. UglifyJS (https://github.com/mishoo/UglifyJS): Es una herramienta de línea de comandos y una biblioteca de JavaScript que permite minificar y ofuscar el código JavaScript.
2. Terser (https://github.com/terser/terser): Es una herramienta de línea de comandos y una biblioteca de JavaScript que permite minificar y ofuscar el código JavaScript. Terser es compatible con ECMAScript 2015 (ES6) y versiones posteriores.
3. javascript-obfuscator (https://github.com/javascript-obfuscator/javascript-obfuscator): Es una biblioteca de JavaScript que ofrece una amplia gama de opciones de ofuscación, incluyendo cifrado de strings, transformaciones de código y protección de dominio.

Es importante destacar que la ofuscación de código no proporciona una seguridad completa. Aunque dificulta el análisis y la comprensión del código, aún es posible desofuscar y entender el funcionamiento subyacente. La ofuscación se utiliza principalmente como una medida adicional de seguridad y para proteger la propiedad intelectual, pero no debe considerarse como una solución definitiva para proteger secretos o información confidencial en una aplicación.

## 30.5. Otras Medidas de seguridad en JS

Existen varias medidas de seguridad que se pueden aplicar al desarrollar aplicaciones en JavaScript (JS) para proteger contra vulnerabilidades y ataques. Algunas de las medidas de seguridad más comunes incluyen:

1. **Validación de datos**: Siempre se debe validar y filtrar cualquier entrada de datos recibida desde fuentes externas, como formularios web o solicitudes HTTP. Esto ayuda a prevenir ataques de inyección, como ataques de SQL o XSS (Cross-Site Scripting), al garantizar que los datos ingresados cumplan con los requisitos esperados.
2. **Escapado de caracteres**: Al mostrar datos de usuario en la interfaz de la aplicación, se debe escapar correctamente los caracteres especiales para evitar la ejecución de scripts maliciosos. Usar métodos de escape adecuados, como la función **`encodeURIComponent()`** o **`innerHTML`** seguro, ayuda a prevenir ataques de XSS.
3. **Prevención de clickjacking**: Se deben implementar medidas para prevenir ataques de clickjacking, donde un atacante superpone un contenido malicioso sobre un sitio web legítimo y engaña a los usuarios para que hagan clic en él involuntariamente. El encabezado HTTP **`X-Frame-Options`** o la política de seguridad de contenido **`Content-Security-Policy`** pueden ayudar a mitigar este tipo de ataques.
4. **Seguridad en las comunicaciones**: Siempre se debe utilizar HTTPS en lugar de HTTP para asegurar las comunicaciones entre el cliente y el servidor. Esto garantiza que los datos estén cifrados durante el transporte y ayuda a prevenir ataques de interceptación de datos.
5. **Protección contra CSRF**: Se deben implementar mecanismos de protección contra CSRF (Cross-Site Request Forgery), como el uso de tokens CSRF y comprobaciones de referencias de origen (Origin Headers), para evitar que los ataques manipulen las solicitudes realizadas por los usuarios autenticados.
6. **Autenticación y autorización seguras**: Al implementar autenticación y autorización en una aplicación, se deben seguir buenas prácticas, como almacenar contraseñas de manera segura utilizando técnicas como el hash y salt, utilizar tokens de acceso seguro y aplicar adecuados controles de permisos y roles.
7. **Actualización y parcheo**: Mantener todas las bibliotecas, frameworks y dependencias actualizadas con las últimas versiones que contengan correcciones de seguridad. Además, asegurarse de aplicar parches de seguridad y actualizaciones en el servidor y en la infraestructura subyacente.
8. **Pruebas de seguridad**: Realizar pruebas de seguridad regular, como pruebas de penetración (pentesting) y análisis estático de código, para identificar posibles vulnerabilidades en la aplicación y abordarlas antes de que sean explotadas.

Estas son solo algunas de las medidas de seguridad que se pueden implementar en JavaScript. Es importante seguir las mejores prácticas de seguridad en todas las capas de una aplicación, incluyendo el código en el lado del cliente (JavaScript) y en el lado del servidor. Además, estar actualizado con las últimas amenazas y vulnerabilidades de seguridad, y seguir las recomendaciones de seguridad proporcionadas por la comunidad de desarrollo y las organizaciones de seguridad.
