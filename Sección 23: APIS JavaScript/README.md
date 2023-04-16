# Sección 23: **APIS Nativas JavaScript**

## 23.1 Notificacion API

La API Notification de JavaScript es una interfaz que permite a las aplicaciones web mostrar notificaciones en el escritorio del usuario. Esto significa que puedes enviar mensajes o alertas importantes, incluso cuando la página web no está activa en la pantalla del usuario. Utiliza el sistema de notificaciones nativo del sistema operativo en el que se está ejecutando el navegador.

Para utilizar la API Notification, primero debes solicitar permiso al usuario para mostrar notificaciones en su escritorio. Este permiso se solicita una sola vez, y una vez que se concede, la aplicación web puede mostrar notificaciones utilizando el constructor de la API Notification sin tener que solicitar permiso cada vez.

Una vez que se ha concedido el permiso, puedes crear notificaciones utilizando la función **`Notification()`**. Esta función toma dos parámetros: el título de la notificación y un objeto que define las opciones de la notificación (como el cuerpo del mensaje, el icono de la notificación, etc.).

Las notificaciones pueden incluir un título, un icono y un cuerpo de texto. Además, se pueden agregar acciones a la notificación que el usuario puede realizar, como hacer clic en un botón para abrir una página web.

```jsx
// Pedir permiso para mostrar notificaciones
Notification.requestPermission().then(function(permission) {
  if (permission === 'granted') {
    // Crear una nueva notificación
    var notification = new Notification('Título de la notificación', {
      body: 'Cuerpo de la notificación',
      icon: 'ruta/a/icono.png'
    });
    
    // Agregar una acción a la notificación
    notification.addAction('Abrir', 'ruta/a/pagina.html');
  }
});
```

Ten en cuenta que la API Notification solo funciona en navegadores compatibles y puede variar según el navegador y la plataforma en la que se esté ejecutando. Además, ten en cuenta que las notificaciones pueden ser molestas si se utilizan en exceso, por lo que es importante usarlas de manera responsable y en situaciones apropiadas.

### Implementando API de Notificación Nativas

Este código utiliza la API Notification de JavaScript para crear y mostrar notificaciones en el escritorio del usuario.

<img src="./img/section-23-1.png"/>

```jsx
// Notificaciones nátivas

// Primero, se selecciona el botón "Notificar" del DOM utilizando el método querySelector, asigna el botón "#notificar" a la variable "notificarBtn" 
const notificarBtn = document.querySelector('#notificar');

// se agrega un evento click que llama al método requestPermission de la API Notification "Notification.requestPermission()". Este método solicita al usuario permiso para mostrar notificaciones.
// La respuesta se maneja en la promesa que devuelve requestPermission, donde se imprime en la consola el resultado obtenido.
notificarBtn.addEventListener('click', () => {
    Notification
        .requestPermission()
        .then( resultado => {
            console.log('El resultado es ', resultado)
         })
})

// Ir mas alla con nuestra notificación...
// se selecciona el botón "Ver Notificación" del DOM utilizando querySelector asigna el botón "#verNotificacion" a la variable "verNotificacionBtn" y se agrega un evento click.
const verNotificacionBtn = document.querySelector('#verNotificacion');

verNotificacionBtn.addEventListener('click', () => {
		//se verifica si se ha concedido permiso para mostrar notificaciones mediante la propiedad permission de la API Notification
    if(Notification.permission == 'granted') {
				// Si el permiso está concedido, se crea una nueva notificación con el título "Esta es la notificación"
				// y el cuerpo "Tutorial de JavaScript", y se le asigna un ícono.
        const notificacion = new Notification('Esta es la notificación', { 
            icon: 'img/logo.png',
            body: 'Tutorial de JavaScript'
        });

        // Ir al sitio web desde la notificacion
				// Además, se agrega un evento onclick a la notificación que abre el sitio web de Google cuando se hace clic en la notificación.
        notificacion.onclick = function() {
            window.open('https://www.google.com')
        }

    }
})
```

En resumen, este código proporciona una idea básica de cómo utilizar la `API Notification` para crear y mostrar notificaciones en el escritorio del usuario, y cómo agregar acciones personalizadas a las notificaciones para realizar acciones adicionales al hacer clic en ellas. Sin embargo, es importante tener en cuenta que la compatibilidad de la `API Notification` varía según el navegador y el sistema operativo.

## 23.2 API Intersection Observer 

El Intersection Observer es una API de JavaScript que permite a los desarrolladores observar cambios en la intersección de un elemento con un contenedor específico. Esto es útil cuando se quiere realizar una acción cuando un elemento se encuentra en el área visible de la pantalla del usuario o, por el contrario, cuando está fuera de ella.

El uso principal del Intersection Observer es para la carga de imágenes, técnicas de carga perezosa (lazy loading) de imágenes o elementos multimedias ej: videos que están en la parte inferior de una página web. En lugar de cargar todos los elementos al mismo tiempo, se puede utilizar el Intersection Observer para cargar solo los elementos que están a punto de aparecer en la pantalla del usuario, reduciendo así el tiempo de carga de la página.

El funcionamiento de Intersection Observer es simple: se crea una instancia del objeto IntersectionObserver que recibe una función callback que se ejecutará cada vez que se observe una intersección del elemento observado con el área visible del contenedor. Esta función callback recibe un array de objetos IntersectionObserverEntry que contienen información sobre el elemento observado y su intersección con el área visible del contenedor.

Para crear un objeto IntersectionObserver se utiliza el siguiente código:

```jsx
const observer = new IntersectionObserver(callback, options);
```

Donde "callback" es la función que se ejecutará cuando se observe una intersección, y "options" es un objeto que contiene opciones de configuración para el observer, como por ejemplo, el threshold o umbral de intersección que se desea observar.

Una vez creado el objeto observer, se puede observar un elemento utilizando el método observe:

```jsx
observer.observe(element);
```

Donde "element" es el elemento que se desea observar.

En resumen, Intersection Observer es una API útil para mejorar el rendimiento de las páginas web al cargar contenido de manera perezosa, permitiendo que los elementos se carguen solo cuando son visibles para el usuario, reduciendo así la cantidad de datos que se deben cargar inicialmente.

Aquí te dejo un ejemplo de cómo podrías utilizar el Intersection Observer:

```jsx
// Seleccionamos el elemento que queremos observar
// se selecciona un elemento HTML con la clase "mi-elemento" utilizando el método querySelector.
const elementoObservado = document.querySelector('.mi-elemento');

// Creamos una instancia del Intersection Observer
const observador = new IntersectionObserver((entries, observer) => {
	// Código a ejecutar cada vez que se observe una intersección
  // entries es un array de objetos que contienen información sobre cada uno de los elementos observados
	// Dentro de la función callback, se utiliza el método forEach del array entries para iterar sobre cada uno de los objetos IntersectionObserverEntry 
	//y comprobar si el elemento observado está dentro o fuera del área visible del contenedor
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      // El elemento está dentro del área visible, realizamos la acción que deseemos
      console.log('El elemento está dentro del área visible');
    } else {
      // El elemento está fuera del área visible, podemos realizar otra acción
      console.log('El elemento está fuera del área visible');
    }
  });
});

// Configuramos el observador para que observe el elemento seleccionado
observador.observe(elementoObservado);
```

En este ejemplo, estamos observando un elemento con la clase **`.mi-elemento`**. Cuando el elemento está dentro del área visible, se muestra un mensaje en la consola. Si está fuera, se muestra otro mensaje.  Es importante destacar que esta API es muy flexible y se pueden configurar varias opciones, como el threshold o umbral de intersección que se desea observar, la raíz del elemento contenedor, entre otras.