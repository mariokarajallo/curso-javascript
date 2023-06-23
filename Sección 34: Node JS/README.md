# Sección 34: **Introducción NodeJS**

## 34.1. ¿Qué es Node.js?

Node.js es un entorno de tiempo de ejecución de código abierto y multiplataforma que permite ejecutar código JavaScript fuera de un navegador web. Fue creado por Ryan Dahl en 2009 y se basa en el motor de JavaScript V8 de Google Chrome. Node.js proporciona una arquitectura orientada a eventos y no bloqueante, lo que significa que puede manejar un gran número de solicitudes simultáneas sin bloquear la ejecución de otras operaciones.

Una de las principales características de Node.js es su capacidad para crear aplicaciones de servidor altamente escalables y de alto rendimiento. Al utilizar JavaScript tanto en el cliente como en el servidor, es posible compartir código y lógica entre ambas partes, lo que facilita el desarrollo de aplicaciones web completas. Además, Node.js cuenta con un amplio ecosistema de paquetes y módulos, administrados a través del gestor de paquetes npm, que permite a los desarrolladores aprovechar una gran cantidad de funcionalidades preexistentes.

Node.js se utiliza ampliamente para desarrollar aplicaciones web y servicios backend, pero también se puede utilizar para crear aplicaciones de línea de comandos, herramientas de automatización, servidores de tiempo real, microservicios y mucho más. Al ser de código abierto y tener una gran comunidad de desarrolladores, Node.js continúa evolucionando y mejorando constantemente.

Node.js ofrece varias ventajas y tiene una amplia gama de aplicaciones.

### Algunas de las ventajas más destacadas de Node.js son:

1. Eficiencia y rendimiento: Node.js utiliza una arquitectura no bloqueante y orientada a eventos, lo que permite manejar múltiples solicitudes simultáneas de manera eficiente. Esto lo hace especialmente adecuado para aplicaciones que requieren una alta concurrencia y rendimiento.
2. Compartir código entre el cliente y el servidor: Al utilizar JavaScript tanto en el cliente como en el servidor, se puede compartir código y lógica, lo que simplifica el desarrollo y la mantenibilidad de las aplicaciones.
3. Amplio ecosistema de paquetes: Node.js cuenta con npm, el gestor de paquetes más grande del mundo, que proporciona acceso a miles de módulos y bibliotecas listos para usar. Esto permite a los desarrolladores aprovechar funcionalidades preexistentes y acelerar el desarrollo de aplicaciones.
4. Escalabilidad: Node.js es altamente escalable y puede manejar una gran cantidad de solicitudes concurrentes con recursos mínimos. También permite la creación de arquitecturas distribuidas y basadas en microservicios.
5. Desarrollo rápido: La facilidad de uso y la disponibilidad de paquetes y módulos preexistentes permiten un desarrollo rápido y eficiente de aplicaciones.

### Algunas de las aplicaciones más comunes de Node.js son:

1. Aplicaciones web en tiempo real: Node.js es especialmente adecuado para aplicaciones que requieren actualizaciones en tiempo real, como chats en vivo, sistemas de colaboración y juegos multijugador.
2. APIs y servicios web: Node.js es ampliamente utilizado para desarrollar servicios web y APIs (Application Programming Interfaces) debido a su capacidad de manejar solicitudes concurrentes y su eficiencia en el manejo de datos.
3. Aplicaciones de streaming: La naturaleza no bloqueante de Node.js lo hace ideal para aplicaciones de streaming, como transmisión de audio y video en tiempo real.
4. Herramientas de línea de comandos: Node.js se puede utilizar para crear scripts y herramientas de línea de comandos, automatizando tareas y agilizando el flujo de trabajo.
5. Aplicaciones de Internet de las cosas (IoT): Node.js se utiliza en el desarrollo de aplicaciones para dispositivos conectados a Internet, permitiendo la comunicación y el control de sensores y actuadores.

## 34.2. ¿Qué es Express?

Express es un framework web rápido y minimalista para Node.js. Proporciona una capa de abstracción sobre el núcleo de Node.js, lo que facilita la creación de aplicaciones web y servicios API de manera eficiente y sencilla. Express es extremadamente popular y ampliamente utilizado en la comunidad de desarrollo de Node.js debido a su simplicidad y flexibilidad.

Algunas características y ventajas de Express son:

1. Enrutamiento: Express facilita la definición de rutas y manejo de solicitudes HTTP. Permite establecer rutas para diferentes URL y métodos HTTP, y proporciona un mecanismo sencillo para manejar y responder a esas solicitudes.
2. Middleware: Express utiliza una arquitectura de middleware que permite agregar funciones de procesamiento en el flujo de solicitud y respuesta. Esto permite realizar tareas como el manejo de sesiones, autenticación, compresión, registro, entre otros, de manera modular y reutilizable.
3. Integración con motor de plantillas: Express permite renderizar vistas HTML utilizando diferentes motores de plantillas populares como EJS, Handlebars o Pug (anteriormente conocido como Jade). Esto facilita la generación de páginas HTML dinámicas basadas en datos enviados desde el servidor.
4. Soporte para API RESTful: Express es una opción popular para crear servicios API RESTful. Permite definir rutas, manejar métodos HTTP como GET, POST, PUT y DELETE, y responder con datos JSON, lo que hace que el desarrollo de APIs sea rápido y sencillo.
5. Amplio ecosistema: Express cuenta con una gran comunidad de desarrolladores y un ecosistema sólido de paquetes y módulos de terceros. A través de npm (Node Package Manager), puedes acceder a una amplia variedad de complementos y middleware para agregar funcionalidades adicionales a tu aplicación.

### Middleware

En Express, el middleware es una función que se ejecuta durante el ciclo de procesamiento de una solicitud HTTP antes de que se envíe una respuesta. El middleware se utiliza para realizar diversas tareas, como la manipulación de la solicitud, la modificación de la respuesta, la autenticación, el manejo de errores, el registro de solicitudes, etc. Básicamente, es una forma de agregar funcionalidades adicionales a una aplicación web de Express.

El middleware se puede utilizar a nivel de aplicación o a nivel de ruta en Express. A nivel de aplicación, el middleware se aplica a todas las solicitudes que llegan a la aplicación. A nivel de ruta, el middleware se aplica solo a las solicitudes que coinciden con una ruta específica.

Express ofrece una amplia variedad de funciones de middleware incorporadas, como **`express.json()`** para el análisis de datos JSON, **`express.urlencoded()`** para el análisis de datos enviados a través de formularios, **`express.static()`** para servir archivos estáticos, entre otros. También puedes crear tu propio middleware personalizado para satisfacer las necesidades específicas de tu aplicación.

En resumen, Express es un framework web ligero pero potente que simplifica el desarrollo de aplicaciones web y APIs en Node.js. Ofrece una gran flexibilidad, un sistema de enrutamiento intuitivo, middleware modular y una amplia comunidad de soporte, lo que lo convierte en una opción popular para construir aplicaciones web rápidas y escalables en Node.js.

## 34.3 Instalando Node

Para utilizar Node.js, sigue estos pasos:

Paso 1: Instalación

- Ve al sitio web oficial de Node.js (**[https://nodejs.org](https://nodejs.org/)**) y descarga la versión correspondiente a tu sistema operativo.
- Sigue las instrucciones de instalación proporcionadas en el sitio web para completar la instalación de Node.js en tu computadora.

Paso 2: Creación de un archivo de proyecto

- Crea una carpeta en tu sistema de archivos para tu proyecto de Node.js.
- Inicializa un nuevo proyecto de Node.js ejecutando el siguiente comando:
  ```
  npm init -y
  ```
  Esto creará un archivo package.json con la configuración básica del proyecto.
- Ejecuta el siguiente comando en la terminal para instalar el módulo **`express`**, que es un framework web popular para Node.js: **`npm install express`**
- Abre un editor de texto o un entorno de desarrollo integrado (IDE) de tu elección y crea un nuevo archivo en esa carpeta con una extensión de archivo ".js". Por ejemplo, "app.js".

Paso 3: Configuración del proyecto

- Abre el archivo "app.js" en tu editor de texto o IDE y comienza a escribir tu código de Node.js.

Paso 4: Escritura de código de Node.js

- Abre **`app.js`** en tu editor de texto o IDE y escribe el siguiente código:

```jsx
// Importa el módulo 'express'
const express = require("express");

// Crea una instancia de la aplicación Express
const app = express();

// Define el puerto en el que se ejecutará el servidor
const port = 3000;

// Define una ruta raíz y una respuesta para esa ruta
app.get("/", (req, res) => {
  res.send("¡Hola, mundo!");
});

// Inicia el servidor en el puerto especificado
app.listen(port, () => {
  console.log(`Servidor escuchando en http://localhost:${port}`);
});
```

- En este código, primero importamos el módulo **`express`** que instalamos en el paso anterior a través de npm. Asignamos el objeto **`express`** a la constante **`express`**.
- Luego, creamos una instancia de la aplicación Express utilizando **`express()`**. Esto nos permite utilizar todas las funcionalidades y métodos proporcionados por Express en nuestra aplicación.
- A continuación, definimos la variable **`port`** para especificar en qué puerto queremos que se ejecute nuestro servidor. En este caso, utilizamos el puerto 3000. Esto indica en qué puerto queremos que nuestro servidor escuche las solicitudes entrantes. Puedes cambiar este número de puerto según tus necesidades.
- Luego, definimos una ruta raíz utilizando **`app.get('/', ...)`**. El primer parámetro es la ruta **`/`**, que es la ruta raíz de nuestro servidor. El segundo parámetro es una función de controlador **`(req, res) => { ... }`**, que se ejecutará cuando se acceda a esta ruta. En este caso, estamos utilizando el método **`send()`** del objeto **`res`** para enviar la respuesta "¡Hola, mundo!" al cliente que realizó la solicitud.
- Finalmente, llamamos al método **`app.listen()`** para iniciar el servidor en el puerto especificado. También mostramos un mensaje en la consola para indicar que el servidor está escuchando correctamente. Estamos utilizando el método **`listen()`** de nuestra aplicación Express para iniciar el servidor en el puerto especificado (**`port`**). La función de callback se ejecuta cuando el servidor se inicia correctamente, y simplemente muestra un mensaje en la consola indicando que el servidor está escuchando en la URL **`http://localhost:3000`**.
- A partir de ahí, puedes comenzar a escribir tu lógica de aplicación utilizando las funciones y métodos proporcionados por los módulos de Node.js y JavaScript.

Paso 5: Ejecución de la aplicación Node.js

- Abre una terminal o línea de comandos y navega hasta la carpeta de tu proyecto de Node.js. Asegúrate de estar en la carpeta de tu proyecto.
- Ejecuta tu aplicación Node.js escribiendo **`node app.js`** en la terminal.

  ![node install](img/section-34-2.png)

- Verás un mensaje en la terminal que indica que el servidor está escuchando en el puerto 3000. Esto iniciará la ejecución de tu código y comenzará a escuchar en el puerto especificado (si estás creando un servidor web).
- Abre un navegador web y visita **`http://localhost:3000`**.
- Verás el mensaje "¡Hola, mundo!", que se muestra en la página, lo cual significa que tu servidor Node.js está funcionando correctamente.

  ![node install](img/section-34-1.png)

- De esta manera has levantado un servidor web básico utilizando Node.js y Express.

### Utilizar la sintaxis de import/export en nuestro proyecto

En Node.js, puedes usar las palabras clave **`import`** y **`export`** para importar y exportar módulos y evitar la sintaxis de requerimiento (require) de CommonJS, que es la forma tradicional (antigua) de importar módulos en Node.js.

Para poder utilizar módulos en tu proyecto de Node.js, puedes seguir estos pasos:

1. Asegúrate de tener un archivo **`package.json`** válido en la raíz de tu proyecto.
2. Abre el archivo **`package.json`**
3. Agrega o modifica la sección **`"type"`** en el archivo **`package.json`** y establece su valor como **`"module"`**. Esto indica que estás utilizando módulos ECMAScript. También, agrega una sección **`"scripts"`** si aún no la tienes.

   ```
   {
     "name": "nombre_del_proyecto",
     "version": "1.0.0",
     "type": "module",
     "description": "node js project",
     "scripts": {
       "test": "echo \"Error: no test specified\" && exit 1"
     },
     "author": "Mario Karajallo",
     "license": "ISC",
     "dependencies": {
       "express": "^4.18.2"
     }
   }
   ```

   Hemos agregado **`"type": "module"`** a la sección **`"type"`** del archivo **`package.json`**.

4. Guarda los cambios en el archivo **`package.json`**.
5. Después de configurar el archivo **`package.json`**, puedes utilizar la sintaxis **`import`** y **`export`** en tu código JavaScript. Ejemplo nuestro app.js

   ```jsx
   // app.js
   // Importa el módulo 'express' y archivos js utilizando la sintaxis de import/export
   import express from "express";

   // Crea una instancia de la aplicación Express
   const app = express();

   // Define el puerto en el que se ejecutará el servidor
   const port = 3000;

   // Define una ruta raíz y una respuesta para esa ruta
   app.get("/", (req, res) => {
     res.send("¡Hola, mundo!");
   });

   // Inicia el servidor en el puerto especificado
   app.listen(port, () => {
     console.log(`Servidor escuchando en http://localhost:${port}`);
   });
   ```

6. Ejecutamos en la terminal `node app` y vemos como funciona ahora con la sintaxis de import/export

### Nodemon

Nodemon es una herramienta de desarrollo para Node.js que facilita la tarea de reiniciar automáticamente la aplicación cada vez que se detectan cambios en los archivos del proyecto. Esto es especialmente útil durante el desarrollo, ya que te permite ahorrar tiempo y esfuerzo al no tener que reiniciar manualmente la aplicación cada vez que realizas cambios en tu código.

Al utilizar Nodemon, puedes iniciar tu aplicación Node.js con el comando **`nodemon`** en lugar de **`node`**. Nodemon monitorea los archivos en tu proyecto y, cuando detecta un cambio, reinicia automáticamente la aplicación. Esto te permite ver los resultados actualizados de tus cambios de inmediato, sin tener que detener y reiniciar manualmente el servidor cada vez.

Para usar Nodemon, primero debes instalarlo en tu proyecto a través de npm. Puedes hacerlo ejecutando el siguiente comando en la línea de comandos:

```
npm install --save-dev nodemon
```

Una vez que Nodemon esté instalado, puedes ejecutar tu aplicación con Nodemon de la siguiente manera, con el nombre del archivo principal de tu aplicación. :

```
nodemon app.js
```

Nodemon iniciará tu aplicación y la mantendrá en ejecución. Si realizas cambios en los archivos de tu proyecto y los guardas, Nodemon detectará automáticamente los cambios y reiniciará la aplicación para reflejar los cambios actualizados.

#### **npm run dev**

Si deseas utilizar el comando **`npm run dev`** en lugar de **`nodemon`** para ejecutar tu aplicación Node.js con reinicio automático, puedes configurar un script personalizado en tu archivo **`package.json`**. Aquí tienes los pasos para hacerlo:

1. Abre el archivo **`package.json.`**
2. Encuentra la sección **`"scripts"`** en el archivo **`package.json`**. Si no existe, puedes agregarla como un objeto vacío.
3. Agrega un nuevo script llamado **`"dev"`** dentro de la sección **`"scripts"`** y establece su valor como **`nodemon app.js`** o **`nodemon <ruta del archivo principal de tu aplicación>`**. Puedes elegir el nombre **`dev`** para el script, pero puedes cambiarlo según tus preferencias.

   ```
   //package.json
   {
     "name": "nombre_del_proyecto",
     "version": "1.0.0",
     "scripts": {
       "dev": "nodemon app.js"
     },
     "dependencies": {
       // Dependencias del proyecto
     },
     "devDependencies": {
       // Dependencias de desarrollo del proyecto
     }
   }
   ```

4. Guarda los cambios en el archivo **`package.json`**.

   Ahora, puedes ejecutar tu aplicación con el comando **`npm run dev`** en lugar de **`nodemon`**. Ejecuta el siguiente comando en la línea de comandos:

   ```
   npm run dev
   ```

   Esto iniciará tu aplicación utilizando **`nodemon`** según la configuración especificada en el script **`"dev"`** en el archivo **`package.json`**. Nodemon monitoreará los archivos en tu proyecto y reiniciará automáticamente la aplicación cuando se detecten cambios.

Con estos pasos básicos, puedes comenzar a desarrollar y ejecutar aplicaciones utilizando Node.js. Puedes aprovechar la amplia gama de módulos y paquetes disponibles a través de npm para agregar funcionalidad adicional a tu proyecto. Además, Node.js ofrece una gran documentación y una activa comunidad de desarrollo que puede ayudarte en tu viaje de desarrollo con Node.js.
