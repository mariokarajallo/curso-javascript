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