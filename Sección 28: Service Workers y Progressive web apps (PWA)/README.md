# Sección 28: **Service Workers y Progressive web apps (PWA)**

## 28.1 Que son los Service Workers y Progressive Web Apps

### Service Workers

Los Service Workers son una característica clave de las Progressive Web Apps (PWAs) que permiten que las aplicaciones web funcionen de manera offline y brinden funcionalidades avanzadas, como notificaciones push y actualizaciones automáticas.

Un Service Worker es un script de JavaScript que se ejecuta en segundo plano de forma independiente al hilo principal del navegador y actúa como un intermediario entre la aplicación web y el navegador.

Aquí te explico en qué consisten los Service Workers:

1. Ejecución en segundo plano: Los Service Workers se ejecutan en un contexto independiente al hilo principal del navegador. Esto significa que pueden realizar operaciones sin bloquear la interfaz de usuario, lo que garantiza una experiencia fluida para el usuario.
2. Gestión del ciclo de vida: Los Service Workers tienen un ciclo de vida propio. Se instalan cuando se registra por primera vez, se activan cuando se cumplen ciertas condiciones y se desactivan cuando no se utilizan. Esto permite controlar su comportamiento y realizar acciones específicas en cada etapa.
3. Capacidad de interceptar y controlar solicitudes de red: Un Service Worker puede interceptar las solicitudes de red realizadas por la aplicación web y decidir cómo responder a ellas. Esto permite implementar estrategias de caché, servir contenido desde el almacenamiento en caché cuando no hay conexión a Internet y actualizar los recursos almacenados en caché cuando hay una conexión activa.
4. Funcionamiento offline: Los Service Workers permiten que una aplicación web funcione sin conexión a Internet. Pueden almacenar en caché los recursos necesarios, como archivos HTML, CSS, JavaScript y archivos de imágenes, para que la aplicación pueda cargar y funcionar incluso cuando no hay una conexión activa. Cuando la conexión se restablece, el Service Worker puede sincronizar los datos almacenados en caché con el servidor.
5. Notificaciones Push: Los Service Workers pueden recibir notificaciones push y mostrarlas al usuario incluso cuando la aplicación web no está abierta. Esto permite enviar actualizaciones y mensajes importantes a los usuarios, lo que ayuda a mantenerlos comprometidos con la aplicación.
6. Actualizaciones automáticas: Los Service Workers pueden controlar y gestionar las actualizaciones de la aplicación web de manera automática. Cuando se carga una nueva versión de la PWA, el Service Worker puede detectarla y actualizar los archivos en caché en segundo plano, lo que garantiza que los usuarios siempre tengan acceso a la última versión de la aplicación sin necesidad de recargar la página.

#### Servicios no disponibles

Si bien los Service Workers brindan una amplia gama de funcionalidades y características para mejorar las Progressive Web Apps (PWAs), también hay algunas funciones que no están disponibles dentro del contexto de un Service Worker. Estas son algunas de las funcionalidades que no se pueden utilizar en un Service Worker:

1. Acceso directo al DOM: Los Service Workers no tienen acceso directo al Document Object Model (DOM) de la página web. Esto significa que no pueden manipular directamente el contenido HTML, interactuar con elementos de la interfaz de usuario ni realizar cambios en la página web que se muestra al usuario.
2. Interacción con eventos del navegador: Los Service Workers no pueden escuchar ni responder a eventos relacionados con la interacción del usuario, como clics de botones, eventos de teclado o eventos de desplazamiento. Estos eventos solo están disponibles en el hilo principal del navegador.
3. Acceso a variables de sesión: Los Service Workers no pueden acceder a las variables de sesión ni almacenar información específica del usuario. Tampoco pueden acceder a las cookies del navegador ni a los datos almacenados localmente por el sitio web.
4. Manipulación del historial del navegador: Los Service Workers no pueden acceder ni manipular el historial de navegación del usuario. No pueden agregar ni eliminar entradas del historial ni redireccionar a páginas diferentes.
5. Uso de APIs específicas del navegador: Algunas APIs del navegador no están disponibles dentro del contexto de un Service Worker. Estas incluyen, por ejemplo, la API de geolocalización, la API de notificaciones del sistema, la API de acceso a la cámara o el micrófono, entre otras.

Es importante tener en cuenta estas limitaciones al desarrollar con Service Workers. Si necesitas realizar acciones que no son compatibles dentro del Service Worker, puedes comunicarte con el hilo principal del navegador utilizando mensajes y eventos para llevar a cabo esas tareas específicas.

En resumen, los Service Workers son scripts de JavaScript que se ejecutan en segundo plano y permiten que las PWAs funcionen de manera offline, intercepten y controlen las solicitudes de red, implementen estrategias de caché, brinden notificaciones push y gestionen las actualizaciones automáticas. Proporcionan una funcionalidad avanzada a las aplicaciones web y mejoran significativamente la experiencia del usuario.

### PWA - Progressive Web App

PWA, o Progressive Web App, es una tecnología que permite a los desarrolladores crear aplicaciones web que ofrecen una experiencia similar a las aplicaciones nativas en dispositivos móviles y de escritorio. Las PWA combinan lo mejor de las aplicaciones web y las aplicaciones nativas, proporcionando una experiencia de usuario más rápida, confiable y atractiva.

Algunas características clave de las PWA son:

1. **Responsive**: Las PWA están diseñadas para adaptarse a cualquier tamaño de pantalla, lo que significa que funcionan bien en dispositivos móviles, tabletas y computadoras de escritorio.
2. **Conectividad independiente**: Las PWA pueden funcionar en condiciones de red deficientes o incluso sin conexión a Internet, gracias al uso de Service Workers. Los Service Workers permiten almacenar en caché los recursos necesarios para que la aplicación funcione sin conexión.
3. **Instalable**: Las PWA pueden instalarse en dispositivos móviles y de escritorio, lo que permite a los usuarios acceder a ellas directamente desde la pantalla de inicio o el escritorio, sin necesidad de abrir un navegador web.
4. **Actualizaciones automáticas**: Las PWA se actualizan automáticamente cuando se detectan cambios en el servidor, lo que garantiza que los usuarios siempre tengan la versión más reciente de la aplicación.
5. **Seguridad**: Las PWA se sirven a través de HTTPS, lo que garantiza que la conexión entre el usuario y el servidor esté cifrada y protegida contra ataques de intermediarios.
6. **Experiencia de usuario atractiva**: Las PWA pueden aprovechar las características nativas del dispositivo, como notificaciones push y acceso a la cámara, para ofrecer una experiencia de usuario más atractiva y personalizada.
7. **Fácil de compartir**: Las PWA son fácilmente compartibles a través de URL, lo que facilita la distribución y promoción de la aplicación.
8. **Descubrible**: Las PWA son indexables por los motores de búsqueda, lo que significa que pueden aparecer en los resultados de búsqueda y atraer a nuevos usuarios.

En resumen, las Progressive Web Apps ofrecen una experiencia de usuario mejorada, funcionan en una variedad de dispositivos y condiciones de red, y son fáciles de mantener y actualizar. Estas características las convierten en una opción atractiva para los desarrolladores que buscan crear aplicaciones web modernas y eficientes.
