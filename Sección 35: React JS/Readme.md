# Sección 35: **Introducción React JS**

## 35.1 ¿Qué es React?

React.js, también conocido como React, es una biblioteca de JavaScript de código abierto desarrollada por Facebook. Se utiliza para construir interfaces de usuario interactivas y escalables para aplicaciones web y móviles.

En lugar de ser un framework completo, React se considera una biblioteca porque se enfoca en un aspecto específico del desarrollo web: la creación de componentes reutilizables que representan partes específicas de una interfaz de usuario.

La principal característica distintiva de React es su enfoque en el rendimiento y la eficiencia. Utiliza un Virtual DOM (DOM virtual) para representar los componentes y actualizar solo las partes necesarias de la interfaz de usuario en lugar de realizar cambios en todo el DOM. Esto mejora el rendimiento de la aplicación al reducir la cantidad de manipulaciones del DOM real.

React se basa en el concepto de componentes. Un componente es una unidad independiente y reutilizable que encapsula la lógica y la interfaz de usuario de una parte específica de la aplicación. Estos componentes pueden ser combinados y anidados para construir interfaces más complejas.

Otra característica importante de React es su enfoque declarativo. En lugar de manipular directamente el DOM, en React se describe cómo debería verse la interfaz de usuario en función del estado actual de la aplicación. React se encarga de actualizar el DOM para que coincida con ese estado, lo que facilita el desarrollo y mantenimiento de la aplicación.

React también ofrece una forma eficiente de manejar y actualizar el estado de una aplicación. El estado es un objeto que contiene datos que pueden cambiar durante el ciclo de vida de un componente. Cuando el estado cambia, React actualiza automáticamente la interfaz de usuario para reflejar esos cambios.

Además, React cuenta con una gran comunidad de desarrolladores y una amplia gama de herramientas y bibliotecas complementarias. Esto hace que sea más fácil aprender React y encontrar soluciones a desafíos comunes durante el desarrollo de aplicaciones.

### Conceptos clave de React:

1. **Componentes:** React es una biblioteca de JavaScript basada en componentes. Los componentes son bloques de construcción reutilizables y autónomos que permiten construir interfaces de usuario (UI) de manera modular. Los componentes pueden ser desde elementos simples, como un botón, hasta elementos complejos, como un formulario completo.
2. **Reactividad**: React permite actualizar la interfaz de usuario de manera eficiente en respuesta a los cambios en los datos o el estado de la aplicación. Cuando los datos cambian, React compara el estado anterior con el nuevo y actualiza solo las partes relevantes de la interfaz de usuario, lo que minimiza la carga en el navegador.
3. **JSX**: JSX es una extensión de sintaxis que permite escribir código HTML dentro de JavaScript. Con JSX, puedes describir la estructura de los componentes React y su apariencia visual en un solo lugar.
4. **Virtual DOM:** React utiliza un Virtual DOM (DOM virtual) para representar los componentes y actualizar eficientemente solo las partes necesarias de la interfaz de usuario. El Virtual DOM es una copia liviana del DOM real y permite que React realice comparaciones eficientes para determinar los cambios necesarios y actualizar solo esas partes, lo que mejora el rendimiento de la aplicación.
5. **Estado (State):** El estado es un objeto que contiene datos que pueden cambiar durante el ciclo de vida de un componente. React permite manejar y actualizar el estado de manera eficiente, lo que facilita la actualización de la interfaz de usuario en función de los cambios en el estado.
6. **Ciclo de vida del componente:** Los componentes en React tienen un ciclo de vida que consta de diferentes etapas, como la creación, actualización y destrucción. Estas etapas permiten ejecutar lógica específica en momentos clave del ciclo de vida de un componente, como realizar una llamada a una API cuando se crea un componente o limpiar recursos antes de que un componente se destruya.

### Origen de React:

React fue creado por el equipo de Facebook y fue lanzado por primera vez en 2013. Fue desarrollado para abordar la necesidad de una manera eficiente de construir interfaces de usuario interactivas y escalables. Desde su lanzamiento, React ha ganado una gran popularidad y se ha convertido en una de las bibliotecas más utilizadas para construir aplicaciones web y móviles.

### Características importantes de React:

1. **Declarativo**: React fomenta un estilo de programación declarativo, lo que significa que describes cómo debe lucir tu interfaz de usuario en función del estado actual, y React se encarga de actualizar la interfaz de usuario para que coincida con ese estado.
2. **Reutilizable**: La arquitectura basada en componentes de React permite crear componentes reutilizables, lo que facilita la construcción y mantenimiento de aplicaciones.
3. **Eficiente**: Gracias al uso del Virtual DOM y a su enfoque de actualización selectiva, React es eficiente en la forma en que actualiza y renderiza la interfaz de usuario. Esto se traduce en un rendimiento más rápido de las aplicaciones.
4. **Comunidad activa:** React cuenta con una comunidad de desarrolladores activa y próspera. Esto significa que hay una gran cantidad de recursos, bibliotecas y herramientas disponibles para ayudarte a aprender y trabajar con React de manera efectiva.

Recuerda que este es solo un breve resumen de los conceptos clave de React. A medida que profundices en tu documentación. Es recomendable consultar la documentación oficial de React (**[https://reactjs.org](https://reactjs.org/)**) y realizar tutoriales o ejemplos prácticos para familiarizarte con su uso.
