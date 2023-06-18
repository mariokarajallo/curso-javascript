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
