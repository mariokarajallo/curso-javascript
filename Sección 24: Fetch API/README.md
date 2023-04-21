# Sección 24: **Fetch API**

## 24.1. Que es y como utilizar FETCH API

Fetch API es una interfaz de programación de aplicaciones (API) que proporciona una forma más moderna y flexible de realizar solicitudes de red en JavaScript. Es compatible con todos los navegadores modernos y permite ejecutar solicitudes HTTP/HTTPS asíncronas y manejar las respuestas de una manera más clara y sencilla que las API de XMLHttpRequest (XHR) antiguas (solicitudes AJAX).

Para utilizar Fetch API, primero debes llamar al método **`fetch()`** en una URL para enviar una solicitud de red. Por ejemplo:

```jsx
fetch('https://api.example.com/data')
  .then(response => {
    // Manejar la respuesta
  })
  .catch(error => {
    // Manejar el error
  });
```

La llamada a **`fetch()`** toma un argumento de URL y devuelve una Promesa que representa la respuesta del servidor. (objeto **`Response`**) cuando la solicitud se completa correctamente. Puedes usar los métodos **`then()`** y **`catch()`** para manejar la respuesta y el error respectivamente.

La respuesta incluye información sobre el estado de la solicitud (código de estado HTTP, encabezados, etc.) y el cuerpo de la respuesta, que puedes leer mediante los métodos **`json()`**, **`text()`**, **`blob()`** o **`arrayBuffer()`** según el tipo de contenido de la respuesta.  También puedes utilizar Fetch API para enviar solicitudes GET, POST, PUT, DELETE y otras, y recibir y manejar las respuestas del servidor de una manera más sencilla.

Por ejemplo:

```jsx
fetch('https://api.example.com/data')
  .then(response => response.json())
  .then(data => {
    // Manejar los datos en formato JSON
  })
  .catch(error => {
    // Manejar el error
  });
```

En este ejemplo, se emplea el método **`json()`** para leer el cuerpo de la respuesta como un objeto JSON y se maneja los datos en el siguiente método **`then()`**. También puedes manejar las respuestas de otros tipos de contenido, como texto plano, imágenes o archivos binarios, usando los métodos adecuados.

La ventaja de Fetch API es que es más fácil de usar que XHR y es compatible con las Promesas de JavaScript, lo que permite escribir código más limpio y fácil de leer. Además, Fetch API proporciona soporte nativo para la lectura de datos en diferentes formatos, como JSON, texto y binario. También admite el uso de la sintaxis async/await para escribir código asíncrono más legible y fácil de entender.

En resumen, Fetch API proporciona una forma más sencilla y flexible de realizar solicitudes de red en JavaScript. Nos permite ejecutar solicitudes de diferentes tipos y manipular las respuestas del servidor de manera fácil y eficiente.

Este código utiliza la Fetch API de JavaScript para obtener datos de un archivo de texto (**`datos.txt`**) y mostrarlos en la consola del navegador cuando se hace clic en un botón.

A continuación, te explico línea por línea:

```jsx
// Fetch API consumir datos desde un txt...

// obtiene una referencia al botón con el ID cargarTxt en el documento HTML y lo almacena en una constante llamada cargarTxtBtn.
//Esto permite seleccionar el botón que activará la función "obtenerDatos" cuando se haga clic en él.
const cargarTxtBtn = document.querySelector('#cargarTxt');

// Se agrega un "event listener" al botón que escucha el evento "click"
// y ejecuta la función "obtenerDatos" cuando el botón es clickeado.
cargarTxtBtn.addEventListener('click', obtenerDatos);

//Se define la función "obtenerDatos" que se ejecutará cuando se haga clic en el botón "cargarTxt".
function obtenerDatos() {
		//Se utiliza el método fetch para obtener los datos del archivo de texto
		// ubicado en la URL "data/datos.txt". 
		// Este método devuelve una promesa que se resolverá cuando se complete la solicitud.
    fetch('data/datos.txt') // URL
				// Se encadena un "then" a la promesa devuelta por el método fetch para manejar la respuesta de la solicitud.
				// La variable "respuesta" es el objeto Response que se devuelve después de la solicitud.
        .then( respuesta => {
            console.log(respuesta);
						// se utilizan algunos métodos y propiedades del objeto Response para obtener información sobre la respuesta.
						// como el tipo de contenido (Content-Type), 
						// el estado de la respuesta (status),
						// el mensaje de estado en inglés (statusText),
						// la URL a la que se realizó la solicitud (url)
						//y el tipo de solicitud (type).
            console.log(respuesta.headers.get("Content-Type"));
            console.log(respuesta.status); // Estado
            console.log(respuesta.statusText); //estado en ingles
            console.log(respuesta.url); // URL a la que consultamos
            console.log(respuesta.type); // Tipo de consulta

            // Se utiliza el método "text()" del objeto Response para obtener el contenido del archivo de texto y devolverlo como una promesa en el siguiente "then".
            return respuesta.text(); // Que este mal escrito

        })
				//Se agrega otro "then" que maneja los datos devueltos por la promesa anterior. 
				// En este caso, simplemente se utiliza la función "console.log" para mostrar los datos en la consola del navegador.
        .then( datos => {
            console.log(datos);
        })
				// Finalmente, se agrega un "catch" que maneja cualquier error que pueda ocurrir durante la solicitud. 
				//Si se produce un error, se muestra un mensaje en la consola del navegador.
        .catch( error => {
            console.log(error);
        })
}
```