# Sección 21: **IndexDB base datos en javascript**

## 21.1 Introducción a IndexedDB

IndexedDB es una base de datos NoSQL que se utiliza para almacenar grandes cantidades de datos en el navegador del usuario. Algunas de las características y detalles más importantes de IndexedDB son los siguientes:

1. NoSQL: IndexedDB es una base de datos NoSQL, lo que significa que no tiene un esquema fijo y no requiere que los datos estén estructurados en una tabla relacional. En cambio, los datos se almacenan en objetos y se pueden recuperar usando índices.
2. Almacenamiento de datos en objetos: IndexedDB almacena datos como objetos. Esto permite a los desarrolladores almacenar y recuperar datos complejos de manera eficiente, lo que es útil para aplicaciones que requieren almacenamiento de datos complejos como imágenes, videos, documentos y archivos.
3. Almacenamiento en el lado del cliente: Los datos se almacenan en el lado del cliente, lo que significa que las aplicaciones web pueden acceder a ellos sin tener que enviar solicitudes al servidor.
4. Almacenamiento persistente: Los datos almacenados en IndexedDB persisten incluso después de que se cierre la aplicación o el navegador web. Esto significa que los usuarios pueden volver a la aplicación más tarde y encontrar sus datos tal como los dejaron.
5. JavaScript API: IndexedDB se utiliza a través de una API de JavaScript, lo que significa que las aplicaciones web pueden acceder a ella utilizando el lenguaje de programación que ya conocen.
6. Índices: IndexedDB utiliza índices para permitir búsquedas rápidas y eficientes de datos. Los índices se crean para las propiedades de los objetos almacenados y se utilizan para buscar rápidamente los datos.
7. Transacciones: IndexedDB utiliza transacciones para garantizar la integridad de los datos y la eficiencia de las operaciones. Las transacciones permiten a los desarrolladores agrupar varias operaciones en una sola y ejecutarlas de manera atómica, lo que significa que todas las operaciones se completarán o ninguna.
8. Capacidad de almacenamiento: IndexedDB tiene una capacidad de almacenamiento bastante grande en comparación con otras tecnologías de almacenamiento de datos en el lado del cliente. Los navegadores modernos permiten hasta 50 MB de almacenamiento en IndexedDB, aunque algunos navegadores permiten más.
9. Acceso asincrónico: Todas las operaciones en IndexedDB se realizan de forma asincrónica. Esto significa que el código no se bloqueará mientras se ejecutan operaciones de lectura y escritura en la base de datos, lo que mejora el rendimiento de la aplicación.
10. Soporte para transacciones en segundo plano: IndexedDB admite transacciones en segundo plano que permiten a los desarrolladores realizar operaciones en la base de datos sin afectar la interacción del usuario con la aplicación.
11. Es compatible con todos los principales navegadores modernos: IndexedDB es compatible con todos los navegadores modernos

En resumen, IndexedDB es una base de datos NoSQL que ofrece una gran capacidad de almacenamiento, índices para búsquedas eficientes, transacciones para la integridad de los datos, acceso asincrónico y transacciones en segundo plano. Es compatible con todos los principales navegadores modernos y es útil para aplicaciones que requieren almacenamiento de datos complejos y búsquedas eficientes.

### IndexDB vs. LocalStorage

IndexedDB y localStorage son ambas tecnologías de almacenamiento en el lado del cliente que se utilizan en el navegador web, pero hay algunas diferencias clave entre ellas:

1. Capacidad de almacenamiento: Una de las diferencias más importantes entre IndexedDB y localStorage es la capacidad de almacenamiento que ofrecen. `localStorage` generalmente tiene una capacidad de almacenamiento más limitada que IndexedDB, con un límite de almacenamiento que varía según el navegador, pero suele estar en el rango de 5-10 MB. `IndexedDB`, por otro lado, puede ofrecer una capacidad de almacenamiento mucho mayor, con algunos navegadores que permiten hasta 50 MB o más.
2. Tipo de datos almacenados: localStorage solo puede almacenar datos en formato de cadena, mientras que IndexedDB puede almacenar datos más complejos, como objetos, matrices y datos binarios. Esto hace que IndexedDB sea más útil para aplicaciones que necesitan almacenar y recuperar datos complejos, como imágenes, videos y archivos.
3. Estructura de datos: localStorage almacena datos en pares clave-valor, similar a un objeto JavaScript, mientras que IndexedDB almacena datos en objetos. IndexedDB permite la creación de índices que pueden acelerar las búsquedas, mientras que localStorage no proporciona esta capacidad.
4. Transacciones: IndexedDB utiliza transacciones para garantizar la integridad de los datos y la eficiencia de las operaciones, mientras que localStorage no ofrece soporte para transacciones.
5. Acceso asincrónico: Ambas tecnologías permiten el acceso asincrónico a los datos almacenados, lo que significa que las operaciones no bloquean el hilo principal del navegador. Sin embargo, IndexedDB utiliza una API más avanzada para acceder a los datos de manera asincrónica, lo que permite un mejor rendimiento en operaciones más complejas.

En resumen, IndexedDB es más adecuado para aplicaciones que necesitan almacenar grandes cantidades de datos complejos y realizar búsquedas eficientes, mientras que localStorage es más adecuado para aplicaciones que necesitan almacenar datos simples en pequeñas cantidades. Además, IndexedDB proporciona soporte para transacciones, índices y una mayor capacidad de almacenamiento, mientras que localStorage es más simple y fácil de usar en comparación con IndexedDB.

Ten en cuenta que funciona en el cliente, en otras palabras en el navegador y los datos almacenados siguen siendo visibles para cualquiera, por lo que no es recomendable almacenar passwords, tarjetas de créditos o información sensible.