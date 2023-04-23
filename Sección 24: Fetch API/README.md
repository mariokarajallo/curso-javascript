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

## 24.2. Consultar un JSON

### Json (JavaScript Object Notation)

JSON (JavaScript Object Notation) es un formato de datos utilizado para transmitir datos estructurados en la web. Es un formato de texto sencillo y ligero que es fácil de leer y escribir para humanos, y fácil de interpretar y generar para las aplicaciones. Es un formato muy popular utilizado para intercambiar datos en aplicaciones web modernas, como RESTful APIs.

En JavaScript, los objetos también JSON se pueden crear y manipular utilizando funciones nativas como **`JSON.parse()`** y **`JSON.stringify()`**. 

- **`JSON.parse()`** se utiliza para convertir una cadena JSON en un objeto JavaScript.
- **`JSON.stringify()`** se utiliza para convertir un objeto JavaScript en una cadena JSON.

JSON es una notación de objeto que se utiliza para almacenar y transferir datos entre el `servidor y el cliente` en aplicaciones web. Los objetos JSON son una colección de pares clave-valor, similares a los objetos en JavaScript, pero con una sintaxis diferente. Por ejemplo:

```jsx
{
  "nombre": "Mario",
  "edad": 30,
  "email": "mario@example.com"
}
```

En este ejemplo, tenemos un objeto JSON que tiene tres propiedades: "nombre", "edad" y "email". Cada propiedad tiene un valor asociado separado por dos puntos. Los objetos JSON se utilizan comúnmente para enviar datos estructurados entre el servidor y el cliente en una solicitud HTTP, y pueden ser fácilmente interpretados y manipulados en JavaScript.

En resumen, JSON es un formato de datos muy utilizado en el desarrollo web y se utiliza ampliamente en aplicaciones de JavaScript para transferir y manipular datos.

### Ejemplo de una consulta JSON en Fetch

este ejemplo utiliza Fetch API para obtener un archivo JSON y luego utiliza la función "mostrarHTML" para mostrar los datos en una página web.

```jsx
// Fetch API desde un JSON (Array)
// se selecciona el botón con id "cargarJSON" y se le agrega un event listener que espera que se haga clic en él.
const cargarJSONBtn = document.querySelector('#cargarJSON');
// Cuando se haga clic, se ejecutará la función "obtenerDatos".
cargarJSONBtn.addEventListener('click', obtenerDatos);

//Dentro de la función "obtenerDatos", se llama a la función "fetch" con la ruta del archivo "empleado.json" como argumento y realiza una solicitud HTTP GET a la ruta "data/empleado.json" para obtener los datos del empleado.
function obtenerDatos() {
    fetch('data/empleado.json') 
				// se encadena una promesa "then" para manejar la respuesta del método "fetch()".
        .then( respuesta => {
						// // se utiliza la función "json()" del objeto "respuesta" para convertir los datos JSON en un objeto JavaScript.
            return respuesta.json()
        }) 
				// se encadena otra promesa "then" que recibe el objeto JavaScript resultante.
        .then(resultado => {
						// se llama a la función "mostrarHTML" y se le pasa el objeto JavaScript como argumento.
            mostrarHTML(resultado);
						// Finalmente, se imprime el objeto JavaScript en la consola del navegador utilizando la función "console.log".
            console.log(resultado)
        })
}

//La función "mostrarHTML" recibe un objeto JavaScript como argumento.
//utiliza destructuring para obtener los valores de "empresa", "id", "nombre" y "trabajo"
function mostrarHTML({empresa,  id, nombre, trabajo}) {
		// se selecciona el elemento con id "contenido"
    const contenido = document.querySelector('#contenido');

		//se establece su propiedad "innerHTML" con un string que contiene los valores del objeto JavaScript
		//se muestra el contenido del objeto JavaScript en el elemento "contenido" del HTML.
    contenido.innerHTML = `
        <p>Empleado: ${nombre} </p>
        <p>ID: ${id} </p>
        <p>Empresa: ${empresa} </p>
        <p>Trabajo: ${trabajo} </p>
    `
}
```

## 24.3 Consultar e Imprimir los Resultados de un Fetch

Para consultar e imprimir los resultados de un Fetch, se utiliza el método **`then()`** después de llamar a la función **`fetch()`**. Dentro de la función anónima del método **`then()`**, se pueden realizar diferentes operaciones con los datos obtenidos de la respuesta.

Por ejemplo, supongamos que queremos realizar una solicitud GET a una API para obtener los datos de una lista de usuarios y mostrarlos en la consola. Podemos utilizar el siguiente código:

```jsx
fetch('https://jsonplaceholder.typicode.com/users')
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error(error));
```

En este código, se utiliza la función **`fetch()`** para realizar una solicitud GET a la API en la URL especificada. Después, se llama al método **`then()`** para analizar los datos de la respuesta con el método **`json()`**. 

La promesa devuelta por **`json()`** se pasa a otra función **`then()`** donde los datos se muestran en la consola mediante la función **`console.log()`**.

Finalmente, se utiliza el método **`catch()`** para manejar cualquier error que pueda ocurrir durante la solicitud.

Si en lugar de mostrar los datos en la consola, queremos mostrarlos en el HTML de la página, podemos hacerlo de la siguiente manera:

```jsx
// Realiza una solicitud HTTP GET a la API JSONPlaceholder para obtener la lista de usuarios
fetch('https://jsonplaceholder.typicode.com/users')
  .then(response => response.json()) // Convierte la respuesta en un objeto JavaScript
  .then(data => { // El objeto JavaScript se recibe como parámetro "data"
    const userList = document.querySelector('#user-list'); // Obtiene el elemento "ul" con ID "user-list"
    data.forEach(user => { // Recorre cada usuario en el objeto "data"
      const userElement = document.createElement('li'); // Crea un elemento de lista "li" en el HTML
      userElement.textContent = user.name; // Establece el contenido de texto del elemento "li" en el nombre del usuario
      userList.appendChild(userElement); // Agrega el elemento "li" al elemento "ul" en el HTML
    });
  })
  .catch(error => console.error(error)); // Maneja cualquier error que ocurra durante la solicitud y lo muestra en la consola del navegador
```

Este código utiliza el método **`fetch()`** para obtener una lista de usuarios en formato JSON desde una API pública de prueba llamada JSONPlaceholder. 

Luego, la respuesta de la solicitud se convierte a un objeto JavaScript utilizando el método **`.json()`**.

Después de que el objeto JavaScript se haya recibido, se utiliza el método **`forEach()`** para recorrer cada usuario en la lista de usuarios y crear un elemento de lista **`li`** en el HTML para cada usuario. Se establece el contenido de texto de cada elemento **`li`** en el nombre del usuario utilizando la propiedad **`textContent`**.

Finalmente, los elementos de lista **`li`** se agregan al elemento de lista **`ul`** en el HTML de la página, que tiene un ID de "user-list". Si ocurre algún error durante la solicitud, se maneja y se muestra en la consola del navegador utilizando el método **`.catch()`**.

### **Ejemplo Práctico**

El siguiente ejemplo es una muestra de cómo consumir un archivo JSON con Fetch API en JavaScript y mostrar su contenido en una página web.

```jsx
// Fetch API desde un JSON (Objeto)
// Se comienza por asignar a la variable cargarJSONArrayBtn el elemento del HTML que tiene como ID "cargarJSONArray".
const cargarJSONArrayBtn = document.querySelector('#cargarJSONArray');
// se agrega un event listener al botón asignado en el paso anterior que llama a la función obtenerDatos cuando se hace click sobre él.
cargarJSONArrayBtn.addEventListener('click', obtenerDatos);

// La función obtenerDatos hace una solicitud a un archivo JSON mediante el uso de fetch() y la URL del archivo.
function obtenerDatos() {
    fetch('data/empleados.json')
				// El método .then() se encarga de manejar la respuesta de la solicitud anterior.
				// En este caso, se convierte la respuesta en formato JSON usando el método json().
        .then( respuesta => {
            return respuesta.json()
        }) 
				// Otra vez, el método .then() maneja la promesa retornada por json()
				// y se llama a la función mostrarHTML para renderizar el contenido JSON en la página web.
        .then(resultado => {
            mostrarHTML(resultado);
            console.log(resultado)
        })
}

// La función mostrarHTML recibe el array de empleados en formato JSON como argumento
// y se encarga de construir una cadena de HTML con los datos de cada empleado.
function mostrarHTML(empleados) {
    const contenido = document.querySelector('#contenido');

    let html = '';
		// se utiliza un bucle forEach para recorrer el array de objetos empleados que se ha obtenido previamente del archivo JSON.
    empleados.forEach( empleado => {
				// Para cada objeto empleado, se extraen sus propiedades id, nombre, empresa y trabajo usando la sintaxis de desestructuración de objetos de JavaScript.
        const { id, nombre, empresa, trabajo} = empleado;
				// se construye un bloque de HTML utilizando una cadena de plantilla y las propiedades del objeto empleado. 
				// Este bloque de HTML se va concatenando a la variable html en cada iteración del bucle.
        html += `
            <p>Empleado: ${nombre} </p>
            <p>ID: ${id} </p>
            <p>Empresa: ${empresa} </p>
            <p>Trabajo: ${trabajo} </p>
        `
    });
		// Finalmente, el contenido de html se inserta en el elemento del DOM con ID contenido, utilizando la propiedad innerHTML.
		// Esto hace que el HTML generado se muestre en la página web como una lista de empleados con su información correspondiente.
    contenido.innerHTML = html;
    
}
```

## 24.4 Consultar e Imprimir los Resultados de una API

Cuando trabajamos con APIs, una de las tareas más comunes es hacer una consulta a una API y luego imprimir los resultados en nuestra página web. Para hacer esto, podemos seguir los siguientes pasos:

1. Utilizar la función **`fetch()`** para hacer una petición a la API y obtener los datos. La URL a la que se hace la petición y el método HTTP que se utiliza dependen de la API en cuestión.
2. Una vez que se han obtenido los datos de la API, se debe analizar la respuesta para extraer la información que necesitamos. En algunos casos, la respuesta puede ser un objeto JSON que se puede parsear y trabajar como un objeto JavaScript.
3. Una vez que se tiene la información que se necesita, se puede utilizar JavaScript para modificar el contenido de la página web y mostrar los resultados. Esto puede implicar la creación de elementos HTML dinámicamente y la inserción de datos en ellos.

Por ejemplo, supongamos que queremos obtener información sobre un usuario a partir de su nombre de usuario en GitHub y mostrar su avatar, nombre y bio en nuestra página web. Para hacer esto, podemos utilizar la API pública de GitHub.

El siguiente código muestra cómo hacer una consulta a la API de GitHub para obtener la información de un usuario y mostrarla en nuestra página web:

```jsx
//Se selecciona el formulario HTML y los elementos de entrada de usuario y resultado utilizando querySelector.
const form = document.querySelector('#github-form');
const usernameInput = document.querySelector('#username-input');
const resultContainer = document.querySelector('#result-container');

//Se agrega un evento de escucha para el evento submit del formulario.
form.addEventListener('submit', (event) => {
	// Se previene el comportamiento predeterminado del formulario al enviar datos al servidor y se obtiene el valor de entrada del nombre de usuario.
  event.preventDefault();
  const username = usernameInput.value;

	// Se realiza una solicitud fetch() a la API de GitHub con el nombre de usuario del usuario especificado.
  fetch(`https://api.github.com/users/${username}`)
		// Se maneja la respuesta de la solicitud como un objeto JSON utilizando el método json().
    .then(response => response.json())
		// Se extraen los datos relevantes de la respuesta JSON, como la URL del avatar, el nombre y la biografía del usuario.
    .then(data => {
			//Se crean elementos HTML para mostrar los detalles del perfil de usuario, como la imagen de avatar, el nombre y la biografía.
      const {avatar_url, name, bio} = data;

      const avatar = document.createElement('img');
      avatar.src = avatar_url;

      const nameElement = document.createElement('h2');
      nameElement.textContent = name;

      const bioElement = document.createElement('p');
      bioElement.textContent = bio;

			// Se vacía el contenedor de resultados anterior y se agregan los elementos HTML creados para mostrar la información del perfil de usuario.
      resultContainer.innerHTML = '';
      resultContainer.appendChild(avatar);
      resultContainer.appendChild(nameElement);
      resultContainer.appendChild(bioElement);
    })
		// Se maneja cualquier error de la solicitud fetch() y se muestra un mensaje de error en caso de error.
    .catch(error => {
      console.error(error);
      resultContainer.textContent = 'Hubo un error al obtener la información del usuario.';
    });
});
```

En este ejemplo, el código primero obtiene los elementos HTML relevantes utilizando **`document.querySelector()`**. 

- Luego, se agrega un escucha de evento al formulario para que se ejecute una función cuando se envíe el formulario.
- La función que maneja el envío del formulario utiliza **`fetch()`** para hacer una petición a la API de GitHub.
- La URL a la que se hace la petición se construye a partir del nombre de usuario que se obtiene del campo de entrada.
- Luego, se utiliza **`response.json()`** para analizar la respuesta de la API y extraer los datos relevantes.
- Una vez que se han obtenido los datos del usuario, se crean elementos HTML dinámicamente utilizando **`document.createElement()`** y se les asigna el contenido correspondiente utilizando **`.textContent`** y **`.src`**.
- Luego, se insertan estos elementos en la página utilizando  **`resultContainer.appendChild()`**.
- En caso de que haya un error al obtener la información del usuario, se muestra un mensaje de error en lugar de los datos del usuario.

### Ejemplo Práctico

Este código es un ejemplo de cómo utilizar la Fetch API para obtener datos de una API externa y mostrarlos en una página HTML. En este caso, la API utilizada es la de Picsum, que proporciona una lista de imágenes con sus detalles.

```jsx
// Fetch API desde una API

// Seleccionar el botón "cargarAPI" del documento HTML y añadir un evento de click que llame a la función obtenerDatos().
const cargarAPIBtn = document.querySelector('#cargarAPI');
cargarAPIBtn.addEventListener('click', obtenerDatos);

//Definir la función obtenerDatos()
//utiliza la función fetch() para hacer una solicitud GET a la API de Picsum.
function obtenerDatos() {
    fetch('https://picsum.photos/list') 
				//Cuando se recibe la respuesta, se convierte a JSON utilizando el método json().
        .then( respuesta => {
            return respuesta.json()
        }) 
				//se llama a la función mostrarHTML() para mostrar los datos obtenidos.
        .then(resultado => {
            mostrarHTML(resultado);
            console.log(resultado)
        })
}

//la función mostrarHTML()
// toma los datos de la API recibidos como parámetro y los muestra en el contenido HTML de la página. 
function mostrarHTML(datos) {
    //Primero, se selecciona el elemento del HTML donde se mostrarán los datos.
    const contenido = document.querySelector('#contenido');

    let html = '';
		//Luego, se itera sobre cada objeto del arreglo de datos y se extraen las propiedades necesarias. 
    datos.forEach( perfil => {
				//Para cada objeto "perfil" en el array "datos", se extraen las propiedades "author" y "post_url".
        const { author, post_url } = perfil;
				//Se crea un string con el contenido HTML que se agregará al elemento seleccionado anteriormente.
        html += `
            <p>Autor: ${author} </p>
            <a href="${post_url}" target="_blank">Ver Imagen</a>
        `
    });

		//Finalmente, se establece el contenido de la sección con ID "contenido" en el HTML generado.
    contenido.innerHTML = html;
    
}
```