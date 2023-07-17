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

## 35.2 La Estructura de Archivos de React y Vite

### Que es Vite?

Vite es un entorno de desarrollo ultrarrápido para aplicaciones web en JavaScript. Fue creado con el objetivo de mejorar la experiencia de desarrollo al proporcionar un entorno de compilación extremadamente rápido y eficiente. Vite se centra en la velocidad y la simplicidad, permitiendo a los desarrolladores construir aplicaciones web de manera rápida y eficiente.

A diferencia de otros entornos de desarrollo, como webpack o Parcel, que se basan en la generación de bundles (paquetes) estáticos, Vite utiliza una técnica llamada "Dev Server" para lograr un tiempo de inicio y una velocidad de actualización en caliente muy rápidos. En lugar de agrupar todos los archivos y dependencias en un solo archivo bundle, Vite aprovecha el soporte nativo de los navegadores modernos para módulos ES y carga los módulos de forma individual durante el desarrollo.

Algunas características y ventajas importantes de Vite son:

1. Tiempo de inicio rápido: Vite se inicia rápidamente gracias a su enfoque de carga de módulos individuales. Esto permite un rápido tiempo de desarrollo y una respuesta instantánea en el navegador al realizar cambios en el código fuente.
2. Recarga en caliente (Hot Module Replacement): Vite proporciona una funcionalidad de recarga en caliente que actualiza automáticamente los cambios en el código fuente sin necesidad de recargar la página completa. Esto agiliza el proceso de desarrollo y mejora la productividad.
3. Soporte nativo para módulos ES: Vite aprovecha las capacidades de los navegadores modernos para cargar módulos ES (ECMAScript) directamente, sin necesidad de transpilación o empaquetamiento adicional. Esto mejora el rendimiento y reduce la complejidad del entorno de desarrollo.
4. Configuración simple: Vite utiliza una configuración simple basada en convenciones y una API intuitiva. Esto facilita la configuración y personalización de las aplicaciones, al tiempo que reduce la complejidad y el tiempo de configuración.
5. Integración con frameworks populares: Vite es compatible con frameworks populares como React, Vue.js, Preact y Svelte, lo que facilita la construcción de aplicaciones utilizando estas tecnologías.

Vite y React son tecnologías que se pueden utilizar juntas para desarrollar aplicaciones web modernas. Aunque son tecnologías independientes, pueden complementarse y aprovechar las fortalezas de cada una para mejorar la experiencia de desarrollo.

Vite se destaca por su velocidad y eficiencia en el entorno de desarrollo. Proporciona un tiempo de inicio rápido y una recarga en caliente instantánea, lo que permite una iteración rápida durante el desarrollo. Vite se integra bien con React y otros frameworks, lo que significa que se puede utilizar como entorno de desarrollo optimizado para desarrollar aplicaciones React.

Aquí hay algunas formas en las que Vite y React se relacionan:

1. Desarrollo rápido: Vite proporciona una experiencia de desarrollo rápida y ágil al cargar módulos individualmente y aprovechar la recarga en caliente. Esto beneficia a los desarrolladores de React al permitirles realizar cambios en el código y ver los resultados inmediatamente, sin tener que esperar largos tiempos de compilación o recargar la página completa.
2. Integración sencilla: Vite se integra de manera fluida con React. Al utilizar Vite como entorno de desarrollo, se pueden aprovechar las características de velocidad y rendimiento de Vite mientras se desarrollan aplicaciones React. Vite es compatible con JSX, la sintaxis utilizada por React, lo que facilita el uso de ambos en conjunto.
3. Optimizaciones específicas de React: Vite puede aplicar optimizaciones específicas de React para mejorar aún más el rendimiento de las aplicaciones React. Por ejemplo, Vite puede realizar una división automática de código (code splitting) basada en los límites de ruta de React, lo que significa que solo se cargan los componentes necesarios para una determinada ruta, reduciendo así el tamaño del paquete y mejorando la velocidad de carga.
4. Soporte para otras tecnologías de React: Vite no se limita solo a React. También se integra bien con otros frameworks y bibliotecas relacionadas con React, como React Router para la gestión de enrutamiento o React Redux para la gestión del estado. Esto permite utilizar Vite como un entorno de desarrollo rápido y eficiente para aplicaciones React que utilizan estas tecnologías complementarias.

Vite y React pueden trabajar juntos de manera armoniosa para proporcionar un entorno de desarrollo rápido y eficiente para aplicaciones web basadas en React. Vite aprovecha su velocidad y recarga en caliente para mejorar la experiencia de desarrollo, mientras que React ofrece un enfoque declarativo y una biblioteca rica para construir interfaces de usuario interactivas.

### \***\*Monta tu primer proyecto Vite\*\***

Para crear un proyecto con React y Vite, puedes seguir estos pasos:

1. Asegúrate de tener Node.js instalado en tu computadora, ya que necesitarás npm (Node Package Manager) para instalar las dependencias del proyecto.
2. Abre tu línea de comandos o terminal y navega hasta el directorio en el que deseas crear tu proyecto.
3. Ejecuta el siguiente comando para crear un nuevo proyecto utilizando Vite :

   ```

   npm create vite@latest
   ```

   También puedes especificar directamente el nombre del proyecto y la plantilla que deseas usar a través de las opciones de línea de comandos adicionales. Por ejemplo, para montar un proyecto de Vite + react, ejecuta:
   Esto creará un nuevo directorio llamado "my-react-app" con una estructura de proyecto inicial y las dependencias necesarias.

   ```jsx
   npm create vite@latest my-react-app -- --template react
   ```

4. Navega al directorio del proyecto recién creado:

   ```
   cd my-react-app
   ```

5. Instala las dependencias del proyecto ejecutando el siguiente comando:

   ```
   npm install
   ```

   Esto instalará todas las dependencias especificadas en el archivo **`package.json`**, incluido React.

6. Una vez finalizada la instalación, puedes iniciar el servidor de desarrollo de Vite ejecutando el siguiente comando:

   ```
   npm run dev
   ```

   Esto iniciará el servidor de desarrollo y se abrirá tu aplicación en el navegador en la dirección **`http://localhost:3000`**.

¡Y eso es todo! Ahora tienes un proyecto de React configurado con Vite. Puedes comenzar a editar los archivos en el directorio **`src`** para construir tu aplicación React. Los cambios se reflejarán automáticamente en el navegador debido a la recarga en caliente proporcionada por Vite.

Recuerda consultar la documentación oficial de Vite y React para obtener más información sobre cómo trabajar con estas tecnologías y aprovechar al máximo sus características y funcionalidades.

### Estructura del proyecto

La estructura de un proyecto en React con Vite sigue una convención similar a otros proyectos en React, pero con algunas diferencias debido al uso de Vite. Aquí está una estructura de carpetas típica y una explicación de los archivos más importantes:

```
my-react-app/
  ├─ node_modules/
  ├─ public/
  │    ├─ favicon.ico
  │    └─ index.html
  ├─ src/
  │    ├─ components/
  │    ├─ App.css
  │    ├─ App.jsx
  │    └─ main.js
  ├─ .gitignore
  ├─ package.json
  ├─ README.md
  └─ vite.config.js
```

A continuación, se proporciona una explicación de los archivos y carpetas más importantes:

- **`node_modules/`**: Esta carpeta contiene todas las dependencias de tu proyecto, incluidas las bibliotecas de React y Vite.
- **`public/`**: Esta carpeta contiene los archivos estáticos de tu aplicación, como **`index.html`** y cualquier otro recurso (imágenes, iconos, etc.) que desees utilizar.
  - **`favicon.ico`**: El icono que se mostrará en la pestaña del navegador.
  - **`index.html`**: El archivo HTML principal que sirve como punto de entrada de tu aplicación React.
- **`src/`**: Esta carpeta es donde escribirás la mayor parte del código fuente de tu aplicación.
  - **`components/`**: Esta carpeta es opcional, pero se recomienda crearla para almacenar los componentes de React reutilizables que construirás para tu aplicación.
  - **`App.css`**: Un archivo CSS donde puedes escribir estilos específicos para el componente **`App`**.
  - **`App.jsx`**: El componente principal de tu aplicación React. Aquí es donde puedes escribir tu código JSX para construir la interfaz de usuario.
  - **`main.js`**: El archivo JavaScript que inicializa y monta la aplicación React en el elemento HTML especificado en el archivo **`index.html`**.
- **`.gitignore`**: Un archivo que especifica los archivos y directorios que no se deben incluir en el repositorio de Git. Puedes personalizarlo según tus necesidades.
- **`package.json`**: El archivo de configuración de npm que contiene la información sobre tu proyecto, así como las dependencias y scripts de npm.
- **`README.md`**: Un archivo de documentación donde puedes proporcionar información sobre tu proyecto, instrucciones de configuración, etc.
- **`vite.config.js`**: Un archivo de configuración para Vite donde puedes personalizar varias opciones, como el puerto de desarrollo, la ruta de compilación, etc.

Estos son solo los archivos y carpetas básicos que se generan inicialmente al crear un proyecto con Vite y React. A medida que agregues más funcionalidad y componentes a tu aplicación, es posible que crees más archivos y carpetas para organizar tu código de manera eficiente.

Recuerda que esta es una estructura básica y puedes personalizarla según tus necesidades y preferencias a medida que desarrolles tu proyecto.

## 35.3. Instalar Tailwind En React y Vite

### Tailwind

Tailwind CSS es un framework de diseño de código abierto que proporciona una forma rápida y eficiente de construir interfaces de usuario (UI) personalizadas para aplicaciones web. A diferencia de otros frameworks CSS como Bootstrap o Foundation, que ofrecen componentes y estilos predefinidos, Tailwind CSS se basa en una metodología de diseño utilitario.

La principal premisa de Tailwind CSS es proporcionar una amplia colección de clases CSS pequeñas y reutilizables, cada una de las cuales tiene un propósito específico y se puede combinar para construir rápidamente interfaces personalizadas. En lugar de escribir CSS personalizado para cada elemento de la interfaz, se utilizan estas clases utilitarias para aplicar estilos de manera rápida y coherente.

Algunas características y conceptos clave de Tailwind CSS son:

1. Clases utilitarias: Tailwind CSS utiliza clases CSS utilitarias para aplicar estilos a los elementos de la interfaz. Estas clases están diseñadas para realizar tareas específicas, como cambiar los colores de fondo, ajustar los márgenes o alinear elementos. Las clases utilitarias se pueden combinar y anidar para lograr estilos más complejos.
2. Diseño basado en componentes: Aunque Tailwind CSS no proporciona componentes predefinidos, se puede utilizar junto con otros frameworks o bibliotecas de componentes para construir interfaces basadas en componentes. Las clases utilitarias de Tailwind CSS se aplican a los elementos de los componentes para personalizar su apariencia y comportamiento.
3. Configuración personalizable: Tailwind CSS ofrece un enfoque altamente personalizable. Puedes configurar tus propias clases utilitarias, colores, tipografía y otros aspectos del diseño. Esto permite adaptar el framework a las necesidades y la identidad visual específicas de tu proyecto.
4. Tamaño de archivo pequeño: Aunque Tailwind CSS proporciona muchas clases utilitarias, el tamaño del archivo final generado es relativamente pequeño debido a su enfoque de diseño utilitario. Al utilizar solo las clases necesarias, se evita la inclusión de estilos no utilizados, lo que resulta en una carga de página más rápida.
5. Comunidad y ecosistema: Tailwind CSS cuenta con una comunidad activa y un ecosistema en crecimiento. Existen numerosos recursos, complementos y herramientas disponibles para facilitar el uso y la personalización de Tailwind CSS.

### Tailwind CSS en un proyecto de React con Vite

Para instalar Tailwind CSS en un proyecto de React con Vite, puedes seguir estos pasos:

1.  Asegúrate de tener Node.js instalado en tu computadora, ya que necesitarás npm (Node Package Manager) para instalar las dependencias del proyecto.
2.  Abre tu línea de comandos o terminal y navega hasta el directorio raíz de tu proyecto creado con Vite y React.
3.  Ejecuta el siguiente comando para instalar Tailwind CSS y sus dependencias como desarrollo:

    ```
    npm install -D tailwindcss postcss autoprefixer
    ```

    Este comando instalará las siguientes dependencias:

    - **`tailwindcss`**: El propio framework de Tailwind CSS.
    - **`postcss`**: Un procesador de CSS que se utilizará junto con Tailwind CSS.
    - **`autoprefixer`**: Un plugin de PostCSS que agrega automáticamente prefijos de proveedores CSS para garantizar la compatibilidad con diferentes navegadores.

4.  Una vez finalizada la instalación, crea un archivo de configuración de Tailwind CSS ejecutando el siguiente comando:

    ```
    npx tailwindcss init -p
    ```

    Esto generará el archivo **`tailwind.config.cjs`** y el archivo de configuración de PostCSS (**`postcss.config.cjs`**) en el directorio raíz de tu proyecto. Ahí podrás personalizar la configuración de Tailwind CSS y PostCSS según tus necesidades.

5.  Abre el archivo **`tailwind.config.cjs`** y personaliza la configuración según tus necesidades. Aquí puedes ajustar los colores, fuentes, márgenes, tamaños y otras opciones de configuración de Tailwind CSS.

    ```jsx
    module.exports = {
      content: [],
      theme: {
        extend: {},
      },
      plugins: [],
    };
    ```

    Aquí tienes una explicación de las secciones y opciones presentes:

    1. **`content`**: Esta opción se utiliza para configurar la purga de clases no utilizadas en producción. Debes proporcionar una matriz de archivos en la propiedad **`content`** para que Tailwind CSS pueda analizar y eliminar las clases no utilizadas del archivo CSS resultante. Por ejemplo:

       ```jsx
       content: ['./src/**/*.html', './src/**/*.js'],
       ```

       En este caso, Tailwind CSS analizará todos los archivos HTML y JS en el directorio **`src`** y sus subdirectorios en busca de clases utilizadas y eliminará las clases no utilizadas del archivo CSS final.

    2. **`theme`**: En esta sección, puedes personalizar el tema de Tailwind CSS. Puedes agregar colores personalizados, modificar espaciado, tamaños de fuente, breakpoints, etc. Al utilizar la propiedad **`extend`** dentro de la sección **`theme`**, puedes extender el tema existente con nuevas configuraciones.
    3. **`plugins`**: Esta sección te permite agregar plugins de terceros para ampliar las funcionalidades de Tailwind CSS. Puedes agregar plugins como **`typography`** para estilos de tipografía avanzados, **`forms`** para estilos de formularios personalizados, entre otros.

    Es importante tener en cuenta que esta configuración no incluye opciones para las variantes de clases utilitarias. Si deseas habilitar o personalizar variantes como **`hover`**, **`focus`**, **`active`**, entre otras, debes agregarlas dentro de la sección **`variants`**.

    Recuerda que esta configuración básica puede modificarse según tus necesidades específicas. Puedes personalizar y extender la sección **`theme`** con tus propias configuraciones, y también puedes agregar plugins a la sección **`plugins`** para agregar funcionalidades adicionales a Tailwind CSS.

    Recuerda que el archivo **`tailwind.config.cjs`** es altamente personalizable y puedes ajustar estas opciones y añadir otras según tus requisitos específicos. Consulta la documentación oficial de Tailwind CSS para obtener más detalles y opciones avanzadas de configuración.

6.  Localiza el archivo de estilos principal de tu proyecto. Por lo general, se encuentra en la raíz del proyecto y se nombra **`styles.css`** o **`app.css` o `index.css`**. Puedes verificar el archivo que se importa en tu archivo principal de JavaScript (por ejemplo, **`index.js`** o **`main.js`**) para encontrar la ruta del archivo de estilos principal.
    Aquí hay un ejemplo de cómo podría verse un archivo de estilos con las directivas de Tailwind CSS donde añade sus clases:

    ````jsx
    /_ styles.css _/

        @tailwind base;
        @tailwind components;
        @tailwind utilities;

        /* Tus estilos personalizados */
        /* ... */
        ```

    ````

7.  Abre el archivo **`src/main.jsx`** (o **`src/index.jsx`**, dependiendo de cómo se llame el archivo principal de tu aplicación) y agrega el siguiente código al principio del archivo:

    ```
    import 'styles.css';
    //o
    import '**app.css**';
    ```

    Esto importará el archivo CSS generado por Tailwind CSS en tu proyecto.

8.  Ahora puedes comenzar a utilizar las clases de Tailwind CSS en tus componentes React.

Tailwind CSS está configurado y listo para usarse en tu proyecto de React con Vite. Puedes utilizar las clases utilitarias de Tailwind CSS en tus componentes para aplicar estilos personalizados de manera rápida y sencilla.

Recuerda que, una vez instalado y configurado Tailwind CSS, puedes consultar la documentación oficial de Tailwind CSS para explorar las clases utilitarias disponibles y aprender a utilizarlas de manera efectiva para personalizar el diseño de tu aplicación.

## 35.4. Extensiones útiles para trabajar con react y React Dev Tools

Aquí tienes algunas de las mejores extensiones para trabajar con React:

1. **ESLint -** [ESLint - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint): Una extensión para Visual Studio Code que ofrece soporte para ESLint, una herramienta de linting que te ayuda a mantener un código JavaScript limpio y libre de errores.
2. **Prettier -** [Prettier - Code formatter - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode): Una extensión que formatea automáticamente tu código para seguir un estilo consistente. Prettier es especialmente útil para mantener la consistencia en proyectos de React con múltiples desarrolladores.
3. **Tailwind CSS IntelliSense -** [Tailwind CSS IntelliSense - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss): Proporciona completado automático para las clases de Tailwind CSS en tus archivos de JSX.
4. **ES7+ React/Redux/React-Native snippets -** [ES7+ React/Redux/React-Native snippets - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=dsznajder.es7-react-js-snippets): Ofrece una amplia variedad de snippets (fragmentos de código) para React, Redux y React Native, lo que agiliza la escritura de código repetitivo.
5. **Simple React Snippets -** [Simple React Snippets - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=burkeholland.simple-react-snippets): Proporciona snippets útiles y rápidos para escribir código de React, como la creación de componentes, el uso de hooks, entre otros.

En cuanto a las extensiones en navegadores, React Developer Tools ([React Developer Tools – React](https://react.dev/learn/react-developer-tools)) es la recomendada para inspeccionar y depurar componentes React directamente en el navegador. Puedes instalarla desde la tienda de extensiones de tu navegador favorito, como Chrome o Firefox.

Recuerda que las extensiones pueden variar según tus preferencias y necesidades específicas. Puedes explorar la tienda de extensiones de Visual Studio Code y probar diferentes opciones para encontrar las que mejor se adapten a tu flujo de trabajo con React.

## 35.5. ¿Qué es JSX?

JSX (JavaScript XML) es una extensión de sintaxis utilizada en React para definir la estructura de la interfaz de usuario de una aplicación. Combina HTML (o XML) y JavaScript en un solo lugar, lo que facilita la creación y manipulación de elementos y componentes de la interfaz de usuario en React.

Aquí hay un ejemplo simple de JSX:

```jsx
import React from "react";

function App() {
  return (
    <div>
      <h1>Hola, mundo!</h1>
      <p>Esta es una aplicación en React con JSX.</p>
    </div>
  );
}

export default App;
```

En JSX, puedes escribir código similar a HTML dentro de bloques JavaScript. Esto permite crear y renderizar elementos de React de manera más declarativa y legible. Aunque JSX se parece mucho a HTML, hay algunas diferencias clave a tener en cuenta:

1. Sintaxis dentro de JavaScript: En JSX, puedes incluir elementos HTML directamente dentro de tu código JavaScript. Por ejemplo:

   ```jsx
   const element = <h1>Hello, world!</h1>;
   ```

2. Expresiones JavaScript: Puedes utilizar expresiones JavaScript dentro de llaves **`{}`** en JSX. Esto permite insertar variables, llamar a funciones y realizar operaciones dentro del código JSX. Por ejemplo:

   ```jsx
   const name = "John";
   const element = <h1>Hello, {name}!</h1>;
   ```

3. Atributos y propiedades: Los atributos HTML en JSX se especifican utilizando una sintaxis similar a la de HTML, pero se escriben en camelCase en lugar de kebab-case. Además, en lugar de utilizar comillas dobles, los valores de los atributos se pasan como expresiones JavaScript. Por ejemplo:

   ```jsx
   const element = (
     <a href="https://example.com" target="_blank">
       Click me!
     </a>
   );
   ```

   **Atributos HTML**: Los atributos HTML se especifican en camelCase en lugar de kebab-case. Por ejemplo, en lugar de **`class`**, usamos **`className`**, y en lugar de **`for`**, usamos **`htmlFor`**. Esto se debe a que JavaScript considera **`class`** y **`for`** como palabras reservadas. Por ejemplo: **`className="mi-clase"`**, **`htmlFor="etiqueta"`**. Ten en cuenta que en JSX, puedes utilizar la misma sintaxis que en HTML para otros atributos, como **`src`**, **`href`**, **`alt`**, etc.

   ```jsx
   <input type="text" value={nombre} onChange={handleChange} />
   ```

   **Propiedades personalizadas**: Además de los atributos HTML, también puedes utilizar propiedades personalizadas para pasar datos a los componentes de React. En el ejemplo, hemos pasado la función **`handleChange`** como la propiedad **`onChange`** al componente **`input`**.
   Es importante recordar que los atributos en JSX representan las propiedades de los elementos de React. Estas propiedades se utilizan para configurar el comportamiento de los componentes y pueden ser accesibles a través de **`props`** en los componentes funcionales o **`this.props`** en los componentes de clase.

4. Elementos anidados: En JSX, puedes anidar elementos dentro de otros elementos, al igual que en HTML. Por ejemplo:

   ```jsx
   const element = (
     <div>
       <h1>Title</h1>
       <p>Content</p>
     </div>
   );
   ```

5. Componentes de React: JSX te permite utilizar componentes de React de forma similar a los elementos HTML. Los componentes de React son funciones o clases que encapsulan una parte de la interfaz de usuario reutilizable. Puedes utilizarlos como si fueran etiquetas HTML en JSX. Por ejemplo:

   ```jsx
   const MyComponent = () => {
     return <h1>Hello, world!</h1>;
   };

   const element = <MyComponent />;
   ```

6. **Clases y estilos**: Las clases de CSS y estilos en línea se definen utilizando la propiedad **`className`** en lugar de **`class`**, debido a que **`class`** es una palabra reservada en JavaScript. Por ejemplo: **`<div className="mi-clase">Contenido</div>`**.
7. **Comentarios**: Los comentarios en JSX se escriben entre llaves y comillas. Por ejemplo: **`{/* Este es un comentario en JSX */}`**

JSX es una parte integral de React y facilita la construcción de interfaces de usuario dinámicas y reactivas utilizando la sintaxis familiar de HTML combinada con el poder de JavaScript. Al compilar el código JSX con herramientas como Babel, se traduce en llamadas a funciones de React que crean y actualizan los elementos de la interfaz de usuario en el navegador.

## 35.6. Componentes en React

En React, los componentes son la piedra angular de la construcción de interfaces de usuario. Representan piezas reutilizables e independientes de código que encapsulan la lógica y la presentación de una parte específica de la interfaz de usuario. Los componentes permiten dividir una aplicación en partes más pequeñas y manejables, lo que facilita el desarrollo y el mantenimiento del código.

Hay dos tipos principales de componentes en React:

1.  **Componentes Funcionales (Functional Components)**:
    Los componentes funcionales son la forma más simple de crear componentes en React. Son funciones de JavaScript que reciben **`props`** (propiedades) como argumentos y devuelven elementos JSX. Hasta la versión 16.7 de React, los componentes funcionales no podían tener estado ni acceder a las características avanzadas de React (como el ciclo de vida y los hooks). Sin embargo, desde la versión 16.8, React introdujo los Hooks, lo que permitió que los componentes funcionales también tengan estado y utilicen características avanzadas de React. Hoy en día, los componentes funcionales son ampliamente utilizados debido a su simplicidad y porque los Hooks los hacen igualmente poderosos que los componentes de clase.

    ````jsx
    import React from 'react';

        function MiComponente(props) {
          return <div>Hola, {props.nombre}!</div>;
        }

        export default MiComponente;
        ```

    ````

2.  **Componentes de Clase (Class Components)**:
    Los componentes de clase son una forma más antigua de crear componentes en React. Son clases de JavaScript que extienden la clase **`React.Component`**. Estos componentes tienen un método **`render()`** obligatorio que devuelve elementos JSX. Los componentes de clase también pueden tener estado (**`state`**) y métodos de ciclo de vida. Los componentes de clase tienen un estado interno y pueden acceder a todas las características de React, como el ciclo de vida de los componentes y los métodos de ciclo de vida. Sin embargo, con la introducción de los Hooks en React, los componentes de clase han perdido popularidad en favor de los componentes funcionales con Hooks, ya que estos últimos son más simples y fáciles de mantener.

    ````jsx
    import React, { Component } from 'react';

        class MiComponente extends Component {
          render() {
            return <div>Hola, {this.props.nombre}!</div>;
          }
        }

        export default MiComponente;
        ```
    ````

En la actualidad, se recomienda utilizar componentes funcionales con Hooks en lugar de componentes de clase, a menos que tengas una razón específica para utilizar componentes de clase en proyectos heredados.

Además de estos dos tipos principales de componentes, también existen otros tipos de componentes y patrones que se utilizan en React:

- **Componentes de orden superior (Higher-Order Components, HOC)**: Los HOCs son funciones que toman un componente existente y devuelven un nuevo componente con funcionalidades adicionales. Se utilizan para reutilizar lógica entre varios componentes.
- **Componentes de renderizado condicional**: Los componentes de renderizado condicional se utilizan para mostrar diferentes elementos JSX en función de ciertas condiciones. Pueden basarse en expresiones lógicas, estados o propiedades.
- **Componentes controlados y no controlados**: Los componentes controlados son aquellos en los que el estado de los datos se maneja a través de React, mientras que los componentes no controlados se basan en el DOM para gestionar su estado.
- **Componentes de presentación y componentes de contenedor**: Los componentes de presentación (también conocidos como componentes tontos o dumb components) se centran en la visualización de la interfaz de usuario y no tienen lógica interna, mientras que los componentes de contenedor (también conocidos como componentes inteligentes o smart components) se encargan de la lógica y la gestión de datos.

Estos son solo algunos ejemplos de los tipos de componentes que se utilizan en React. Puedes combinarlos y utilizarlos de acuerdo con tus necesidades específicas de desarrollo y diseño de la interfaz de usuario.

Recuerda que React fomenta la creación de componentes reutilizables para facilitar el desarrollo y el mantenimiento de las aplicaciones.

## 35.7. ¿Qué es el state en React?

### State

En React, el "state" (estado) es un concepto fundamental que representa los datos que pueden cambiar en un componente a lo largo del tiempo. Es un objeto que contiene información dinámica que afecta cómo se renderiza y se comporta un componente. Cuando el estado de un componente cambia, React se encarga de actualizar automáticamente la interfaz de usuario para reflejar esos cambios.

El estado es específico de cada componente, lo que significa que cada componente puede tener su propio estado independiente de otros componentes en la aplicación. Para definir y manejar el estado en un componente de React, se utiliza el método **`useState`** o, en componentes de clase, el objeto de estado (**`this.state`**).

En componentes funcionales, puedes utilizar el hook **`useState`** para agregar estado a un componente. Aquí tienes un ejemplo sencillo:

```jsx
import React, { useState } from "react";

function Contador() {
  // El primer valor devuelto por useState es el estado actual,
  // y el segundo valor es una función para actualizar ese estado.
  const [contador, setContador] = useState(0);

  const incrementar = () => {
    setContador(contador + 1);
  };

  return (
    <div>
      <p>Contador: {contador}</p>
      <button onClick={incrementar}>Incrementar</button>
    </div>
  );
}

export default Contador;
```

En este ejemplo, el componente **`Contador`** tiene un estado llamado **`contador`** inicializado a **`0`** mediante el hook **`useState`**. Cuando se hace clic en el botón "Incrementar", la función **`incrementar`** se ejecuta y actualiza el estado del contador mediante **`setContador`**, lo que hace que el componente se vuelva a renderizar y muestre el nuevo valor del contador.

En componentes de clase, el estado se define utilizando el objeto **`this.state`**, y se actualiza mediante el método **`setState`**. Aquí tienes el equivalente del ejemplo anterior utilizando un componente de clase:

```jsx
import React, { Component } from "react";

class Contador extends Component {
  constructor() {
    super();
    this.state = {
      contador: 0,
    };
  }

  incrementar = () => {
    this.setState({ contador: this.state.contador + 1 });
  };

  render() {
    return (
      <div>
        <p>Contador: {this.state.contador}</p>
        <button onClick={this.incrementar}>Incrementar</button>
      </div>
    );
  }
}

export default Contador;
```

En resumen, el estado en React es un mecanismo que te permite almacenar y actualizar datos que pueden cambiar durante la vida útil de un componente. Es esencial para crear componentes interactivos y dinámicos en tus aplicaciones de React.

### useState

**`useState`** es un hook de React que te permite agregar estado a componentes funcionales. Los hooks son funciones especiales que te permiten agregar funcionalidades de React a componentes funcionales sin necesidad de utilizar clases.

La función **`useState`** devuelve una tupla que contiene dos elementos: el valor actual del estado y una función para actualizar ese estado. La sintaxis es la siguiente:

```jsx
const [estado, setEstado] = useState(valorInicial);
```

- **`estado`**: Representa el valor actual del estado. Puedes utilizarlo para mostrar información en la interfaz de usuario.
- **`setEstado`**: Es la función que se utiliza para actualizar el estado. Cuando esta función se llama con un nuevo valor, React re-renderiza el componente con el nuevo estado y actualiza la interfaz de usuario.
- **`valorInicial`**: Es el valor que se asigna al estado cuando el componente es renderizado por primera vez.

Aquí tienes un ejemplo simple de cómo utilizar **`useState`**:

```jsx
import React, { useState } from "react";

function Contador() {
  const [contador, setContador] = useState(0);

  const incrementar = () => {
    setContador(contador + 1);
  };

  return (
    <div>
      <p>Contador: {contador}</p>
      <button onClick={incrementar}>Incrementar</button>
    </div>
  );
}

export default Contador;
```

Este código es un componente funcional en React llamado **`Contador`** que utiliza el hook **`useState`** para agregar un estado de contador a la interfaz de usuario. Aquí está la explicación detallada:

1. **`import React, { useState } from 'react';`**: En esta línea, importamos React y el hook **`useState`** desde el paquete 'react'. Esto nos permite utilizar la biblioteca de React y el hook **`useState`** para manejar el estado en nuestro componente.
2. **`function Contador() { ... }`**: Definimos el componente **`Contador`** como una función de React. Los componentes funcionales son simplemente funciones que devuelven elementos JSX para representar la interfaz de usuario.
3. **`const [contador, setContador] = useState(0);`**: Utilizamos el hook **`useState`** para agregar estado a nuestro componente. Aquí, declaramos una constante **`contador`** que almacenará el valor actual del estado y otra constante **`setContador`**, que es la función que utilizaremos para actualizar el estado. Le pasamos **`0`** como valor inicial para el contador.
4. **`const incrementar = () => { ... }`**: Definimos una función llamada **`incrementar`**. Esta función se ejecutará cuando hagamos clic en el botón de incrementar.
5. **`setContador(contador + 1);`**: Dentro de la función **`incrementar`**, llamamos a **`setContador`** con el nuevo valor del contador, que es **`contador + 1`**. Cuando esta función se ejecuta, React actualizará automáticamente el estado y volverá a renderizar el componente.
6. **`return ( ... )`**: En el bloque de retorno, definimos la estructura de la interfaz de usuario que queremos mostrar. Utilizamos el valor actual del contador en el texto del párrafo y definimos un botón que, cuando se hace clic, llamará a la función **`incrementar`**.
7. **`<p>Contador: {contador}</p>`**: Mostramos el valor actual del contador en un elemento de párrafo.
8. **`<button onClick={incrementar}>Incrementar</button>`**: Creamos un botón que llama a la función **`incrementar`** cuando se hace clic.

En resumen, este componente **`Contador`** muestra un número en la interfaz de usuario y un botón que permite incrementar ese número en uno cada vez que se hace clic. El estado del contador es manejado por el hook **`useState`**, y cuando el estado cambia, React se encarga de actualizar automáticamente la interfaz de usuario para reflejar esos cambios.

#### Reglas importantes a tener en cuenta al usar **`useState`**:

1. **No modifiques el estado directamente**: No debes modificar el estado directamente, como hacer **`estado = nuevoValor`**. En su lugar, utiliza la función **`setEstado`** proporcionada por **`useState`**.
2. **Llamadas a useState siempre deben ser en el nivel superior**: Asegúrate de llamar a **`useState`** siempre en el nivel superior del componente. No lo utilices dentro de condicionales, bucles o funciones anidadas.
3. **El orden de llamada de los hooks debe ser consistente**: Siempre llama a los hooks en el mismo orden en cada renderizado. No los llames dentro de condicionales o ciclos, ya que puede provocar comportamientos inesperados.
4. **No utilices useState dentro de clases**: Los hooks como **`useState`** solo se pueden usar en componentes funcionales. Si necesitas manejar el estado en un componente de clase, utiliza el objeto de estado (**`this.state`**) y el método **`setState`**.

Siguiendo estas reglas, **`useState`** te proporciona una forma simple y poderosa de agregar estado a tus componentes funcionales y crear interfaces de usuario interactivas en React.

### Administrar el estado en React

Administrar el estado en React es una parte crucial del desarrollo de aplicaciones interactivas y dinámicas. Aquí tienes algunas pautas y enfoques para administrar el estado de manera efectiva en tus componentes:

- **Utiliza useState para componentes funcionales**: En componentes funcionales, utiliza el hook **`useState`** para agregar y actualizar el estado. Como se mostró en el ejemplo anterior, **`useState`** te permite declarar el estado y la función para actualizarlo. Recuerda que **`useState`** no combina el estado existente con el nuevo estado, sino que reemplaza el estado actual por el nuevo valor.
- **Stateful vs Stateless Components**: Separa los componentes en dos categorías: componentes con estado (stateful) y componentes sin estado (stateless). Los componentes con estado se refieren a aquellos que manejan datos cambiantes a través del estado, mientras que los componentes sin estado se encargan principalmente de la visualización de la interfaz de usuario a partir de los props que reciben. Esta separación ayuda a tener un mejor control sobre el flujo de datos en tu aplicación.
- **Levantamiento de estado (Lifting State Up)**: Si dos o más componentes necesitan compartir el mismo estado o necesitan comunicarse entre sí, puedes "elevar" el estado común a un componente superior que los contenga. De esta manera, los componentes comparten el mismo estado y cualquier cambio realizado en él se reflejará en todos los componentes que lo utilizan.
- **Props para pasar datos**: Utiliza props para pasar datos y funciones entre componentes, especialmente cuando necesitas compartir información desde componentes padres a componentes hijos. Los componentes hijos pueden recibir datos como props y enviar eventos al componente padre mediante funciones que se pasan como props.
- **Controlled vs Uncontrolled Components**: En formularios, tienes la opción de utilizar componentes controlados o no controlados. Los componentes controlados son aquellos cuyos valores están vinculados al estado de React y se actualizan a través de eventos. Los componentes no controlados se basan en el DOM para mantener su estado. Es recomendable utilizar componentes controlados siempre que sea posible, ya que React puede controlar el flujo de datos y validar los cambios antes de actualizar la interfaz de usuario.
- **Context API**: La Context API de React te permite crear un contexto que puede compartir datos entre componentes, evitando el paso explícito de props a través de componentes intermedios. Es útil cuando tienes datos que son necesarios en varios niveles de tu árbol de componentes.
- **Redux o otros estados globales**: Si tu aplicación se vuelve más compleja y necesitas compartir estado entre múltiples componentes sin necesidad de pasarlo a través de props, puedes considerar el uso de bibliotecas de administración de estado como Redux o Mobx. Estas bibliotecas proporcionan un almacenamiento centralizado para el estado de la aplicación y permiten un flujo de datos más predecible y estructurado.

Recuerda que la elección de cómo administrar el estado depende de la complejidad y las necesidades de tu aplicación. En general, comienza utilizando el hook **`useState`** para componentes funcionales y luego, a medida que la aplicación crece y se vuelve más compleja, considera otras opciones como levantar el estado, usar Context API o implementar una biblioteca de administración de estado como Redux.

## 35.8. Que son los eventos en React

En React, los eventos son acciones que ocurren dentro de los componentes y que pueden ser capturadas y manejadas por el código. Los eventos en React siguen una convención similar a la de los eventos en JavaScript estándar, pero con algunas diferencias sutiles.

Convenciones para manejar eventos en React:

1. En React, los nombres de eventos utilizan camelCase en lugar de minúsculas, como es común en JavaScript. Por ejemplo, en lugar de utilizar **`onclick`**, se utiliza **`onClick`**. Además, en lugar de pasar una cadena de código como manejador de eventos, se pasa una referencia a una función.
2. **Asociación de eventos**: Para asociar un manejador de eventos a un elemento en React, se utiliza la sintaxis de JSX **`onNombreEvento={manejador}`.** Por ejemplo, puedes agregar un manejador de eventos al hacer referencia a la función en el atributo del elemento JSX, como **`onClick={handleClick}`**.
3. **Manejadores de eventos**: Un manejador de eventos en React es una función que se ejecuta cuando ocurre un evento específico. Los manejadores de eventos se definen como métodos en los componentes de clase o como funciones en los componentes funcionales. Por ejemplo, un manejador de clic (**`onClick`**) será una función que se llame cuando se haga clic en un elemento.

Ejemplo básico de manejo de eventos en React:

#### Onclick

```jsx
import React, { useState } from "react";

function Contador() {
  const [contador, setContador] = useState(0);

  const incrementar = () => {
    setContador(contador + 1);
  };

  const resetear = () => {
    setContador(0);
  };

  return (
    <div>
      <p>Contador: {contador}</p>
      <button onClick={incrementar}>Incrementar</button>
      <button onClick={resetear}>Resetear</button>
    </div>
  );
}

export default Contador;
```

En este ejemplo, hemos agregado dos botones: uno para incrementar el contador y otro para resetearlo a cero. Hemos definido dos manejadores de eventos, **`incrementar`** y **`resetear`**, que se ejecutarán cuando se hagan clic en los botones correspondientes. Cada manejador de eventos actualiza el estado del contador utilizando **`setContador`**, lo que provoca que React actualice el componente y vuelva a renderizar la interfaz de usuario con el nuevo valor del contador.

#### onChange

aquí tienes un ejemplo de cómo utilizar el evento **`onChange`** en React. En este ejemplo, crearemos un componente funcional que muestra un campo de entrada (input) y una etiqueta (label) que se actualiza dinámicamente cuando el usuario escribe en el campo de entrada:

```jsx
import React, { useState } from "react";

function InputConEtiqueta() {
  const [texto, setTexto] = useState("");

  const handleChange = (event) => {
    setTexto(event.target.value);
  };

  return (
    <div>
      <label>Ingrese su texto:</label>
      <input type="text" value={texto} onChange={handleChange} />
      <p>Texto ingresado: {texto}</p>
    </div>
  );
}

export default InputConEtiqueta;
```

En este ejemplo, hemos creado el componente funcional **`InputConEtiqueta`**. Definimos un estado llamado **`texto`** utilizando el hook **`useState`**, y le damos un valor inicial de una cadena vacía.

Luego, hemos creado una función llamada **`handleChange`**, que es el manejador del evento **`onChange`**. Cuando el usuario escribe en el campo de entrada, esta función se ejecuta y actualiza el estado **`texto`** con el valor del campo de entrada utilizando **`setTexto`**.

Finalmente, en el bloque de retorno, mostramos una etiqueta, un campo de entrada y un párrafo que muestra el texto ingresado. El campo de entrada tiene su valor vinculado al estado **`texto`**, por lo que siempre mostrará el valor actual del estado. Cada vez que el usuario escribe en el campo de entrada, el evento **`onChange`** se activa y llama a la función **`handleChange`**, lo que actualiza el estado **`texto`** y muestra el texto ingresado en tiempo real.

Este es solo un ejemplo simple de cómo usar el evento **`onChange`** en React. Puedes utilizar este evento para manejar cualquier cambio en el contenido de los campos de entrada, deslizadores, selectores, etc., y realizar acciones en función de esos cambios.

Recuerda que los eventos en React pueden manejar diferentes tipos de interacciones, como clics, cambios de entrada, cambios de enfoque, envíos de formularios, entre otros. Puedes utilizar eventos como **`onClick`**, **`onChange`**, **`onSubmit`**, **`onFocus`**, entre otros, según tus necesidades.

Es importante tener en cuenta las convenciones de nombres de eventos en React y asociar correctamente los manejadores de eventos a los elementos de la interfaz de usuario para garantizar que tu aplicación responda a las interacciones del usuario de manera esperada.

## 35.9. Componentes con Props

### Props

Los componentes en React pueden recibir datos desde el componente padre utilizando props. Las props son una forma de pasar datos de un componente padre a un componente hijo, lo que permite que los componentes sean más reutilizables y configurables.

Aquí tienes un ejemplo de un componente funcional en React que recibe y utiliza props:

```jsx
import React from "react";

function Saludo(props) {
  return <p>Hola, {props.nombre}!</p>;
}

export default Saludo;
```

En este ejemplo, el componente **`Saludo`** recibe una prop **`nombre`** a través del objeto **`props`**. Luego, utiliza la prop **`nombre`** para mostrar un saludo personalizado en el elemento de párrafo.

Para utilizar este componente y pasar la prop **`nombre`**, puedes hacerlo desde su componente padre:

```jsx
import React from "react";
import Saludo from "./Saludo";

function App() {
  return <Saludo nombre="Juan" />;
}

export default App;
```

En este caso, el componente **`App`** utiliza el componente **`Saludo`** y le pasa la prop **`nombre`** con el valor "Juan". El componente **`Saludo`** recibe esa prop a través de **`props`** y muestra el saludo personalizado.

Las props pueden ser cualquier tipo de dato, como cadenas de texto, números, booleanos, objetos o incluso funciones. Puedes pasar múltiples props a un componente separándolas por comas. Además, puedes utilizar expresiones de JavaScript dentro de las llaves para calcular o manipular los valores de las props.

Aquí tienes un ejemplo que muestra cómo utilizar múltiples props y una expresión de JavaScript dentro de una prop:

```jsx
import React from "react";

function Producto(props) {
  return (
    <div>
      <h2>{props.nombre}</h2>
      <p>Precio: ${props.precio}</p>
      <button onClick={props.onComprar}>Comprar</button>
    </div>
  );
}

export default Producto;
```

En este ejemplo, el componente **`Producto`** recibe tres props: **`nombre`**, **`precio`** y **`onComprar`**. Las utiliza para mostrar el nombre y precio del producto, así como un botón de compra. El evento **`onClick`** del botón está vinculado a la prop **`onComprar`**, que se espera que sea una función proporcionada desde el componente padre.

Recuerda que las props son de solo lectura, lo que significa que no se deben modificar directamente dentro del componente. Si necesitas mantener un estado interno en un componente, puedes utilizar el hook **`useState`** o el estado de un componente de clase para manejarlo. Los **`props`** son una forma de comunicación unidireccional, donde los datos fluyen desde el componente padre al componente hijo, y si necesitas actualizar los datos, debes hacerlo desde el componente padre y pasarlos nuevamente a través de los **`props`**.

El uso de props en React es una forma efectiva de pasar datos y configuraciones entre componentes, lo que hace que tu código sea más modular y fácil de mantener. Puedes utilizar props para personalizar la apariencia y el comportamiento de tus componentes, así como para reutilizarlos en diferentes partes de tu aplicación.

## 35.10 Helpers

### Helpers

En el contexto de React, los "helpers" son funciones o utilidades que se utilizan para realizar tareas específicas y facilitar el desarrollo de componentes y aplicaciones. Estas funciones auxiliares no están vinculadas directamente a la lógica del componente, sino que se utilizan para mejorar la legibilidad, reusabilidad y eficiencia del código.

Los helpers en React pueden abordar diferentes aspectos, como la manipulación de datos, el formateo de contenido, la validación, el cálculo, el manejo de eventos, entre otros. Al organizar estas funciones en helpers, se pueden utilizar en múltiples lugares de la aplicación y mantener un código más limpio y modular.

Aquí tienes algunos ejemplos de helpers comunes en React:

1. **Formateo de fechas**: Un helper que toma una fecha en formato de objeto o cadena y devuelve la fecha formateada en una presentación más legible, como "dd/mm/aaaa" o "hh:mm AM/PM".
2. **Validación de formularios**: Un helper que se utiliza para verificar la validez de los datos ingresados en un formulario y devolver mensajes de error cuando es necesario.
3. **Cálculos matemáticos**: Un helper que realiza cálculos matemáticos complejos o fórmulas específicas que se utilizan en varios componentes.
4. **Manejo de eventos**: Un helper que encapsula el manejo de eventos comunes, como el debouncing (retardo) o throttling (limitación) de eventos para mejorar el rendimiento.
5. **Filtrado y búsqueda de datos**: Un helper que realiza filtrado y búsqueda de datos en listas o arreglos, según criterios específicos. Los helpers pueden ser utilizados para encapsular las llamadas a API y gestionar la comunicación con servicios externos. Esto ayuda a mantener separada la lógica de acceso a datos de los componentes de presentación.
6. **API requests**: Un helper que encapsula las llamadas a API y gestiona la respuesta y el manejo de errores de manera consistente. Los helpers pueden ser utilizados para encapsular las llamadas a API y gestionar la comunicación con servicios externos. Esto ayuda a mantener separada la lógica de acceso a datos de los componentes de presentación.

Es importante tener en cuenta que los helpers en React no son parte de la biblioteca de React en sí, sino que son funciones o utilidades adicionales creadas por los desarrolladores para mejorar la organización y la reutilización del código. Puedes organizar los helpers en archivos separados y luego importarlos en los componentes donde los necesites.

Mantener una buena estructura de helpers puede hacer que tu código sea más mantenible y escalable, ya que permite aislar la lógica específica en funciones reutilizables, lo que facilita las futuras modificaciones y mejoras de tu aplicación.

Recuerda que los helpers son solo una herramienta adicional para facilitar el desarrollo en React y ayudarte a escribir código más limpio y organizado. No son una parte esencial de React y su uso depende de las necesidades y preferencias de tu proyecto.

## 35.11. ¿Qué es useEffect? y como se utiliza

### useEffect

**`useEffect`** es otro hook importante en React que permite realizar efectos secundarios en componentes funcionales. Los efectos secundarios son acciones que ocurren fuera del flujo de renderizado normal, como llamadas a API, suscripciones a eventos, manipulación del DOM y más. **`useEffect`** te permite ejecutar código relacionado con estos efectos secundarios de manera controlada y segura en tus componentes.

La sintaxis básica de **`useEffect`** es la siguiente:

```jsx
import React, { useEffect } from "react";

function MiComponente() {
  useEffect(() => {
    // Código a ejecutar en el efecto secundario
    // (se ejecuta después de cada renderizado)

    return () => {
      // Código de limpieza del efecto (opcional)
    };
  }, [dependencias]); // Dependencias (opcional)

  return <div>Contenido del componente</div>;
}

export default MiComponente;
```

Explicación de los argumentos de **`useEffect`**:

1. **`useEffect(() => { ... }, []);`**: **`useEffect`** recibe dos argumentos. El primer argumento es una función que contiene el código del efecto secundario a ejecutar. El segundo argumento es un array opcional de dependencias que especifica cuándo debe ejecutarse el efecto secundario. Si el array de dependencias está vacío (**`[]`**), el efecto secundario se ejecutará solo una vez después del primer renderizado.
2. **`return () => { ... };`**: Dentro de la función del efecto secundario, puedes devolver una función de limpieza opcional. Esta función se ejecutará antes de que el componente sea eliminado o antes de que se ejecute el efecto secundario nuevamente si alguna de las dependencias cambia. Puedes utilizar la función de limpieza para cancelar suscripciones, limpiar temporizadores u otras tareas de limpieza necesarias.
3. Dependencias: El array de dependencias (**`[]`** en el ejemplo) especifica qué variables o propiedades deben cambiar para que el efecto secundario se vuelva a ejecutar. Si alguna de las dependencias cambia, el efecto secundario se ejecutará nuevamente. Si omites el array de dependencias, el efecto secundario se ejecutará en cada renderizado. Si este array está vacío, el efecto se ejecutará solo una vez, después del primer renderizado. Si contiene elementos, el efecto se ejecutará cada vez que alguno de los elementos en el array cambie de valor.

Ejemplo de uso de **`useEffect`**:

```jsx
import React, { useEffect, useState } from "react";

function Contador() {
  const [contador, setContador] = useState(0);

  useEffect(() => {
    console.log("El componente se montó o fue actualizado.");
    return () => {
      console.log("El componente se desmontó.");
    };
  }, [contador]);

  const incrementar = () => {
    setContador(contador + 1);
  };

  return (
    <div>
      <p>Contador: {contador}</p>
      <button onClick={incrementar}>Incrementar</button>
    </div>
  );
}

export default Contador;
```

En este ejemplo, **`useEffect`** se utiliza para mostrar mensajes en la consola cuando el componente se monta, se actualiza o se desmonta. La función de efecto se ejecuta después de cada renderizado porque estamos pasando **`[contador]`** como dependencia.

Aquí tienes la documentación detallada de cada paso del ejemplo:

1. **Importar las dependencias necesarias**:

   ```jsx
   import React, { useEffect, useState } from "react";
   ```

   En esta línea, importamos las dependencias necesarias para crear componentes en React y utilizar el hook **`useEffect`** y el hook **`useState`**. **`useEffect`** se utiliza para realizar efectos secundarios, mientras que **`useState`** se utiliza para agregar estado a nuestro componente.

2. **Definir el componente `Contador`**:

   ```jsx
   function Contador() {
     // ...
   }
   ```

   Aquí definimos el componente **`Contador`** como una función de React. Este componente será reutilizable y podrá mostrar y manejar un contador en la interfaz de usuario.

3. **Agregar estado al componente utilizando el hook `useState`**:

   ```jsx
   const [contador, setContador] = useState(0);
   ```

   Con esta línea de código, utilizamos el hook **`useState`** para agregar estado al componente. Creamos una variable de estado llamada **`contador`** y una función **`setContador`** para actualizar ese estado. El valor inicial del contador se establece en **`0`**.

4. **Utilizar el hook `useEffect` para definir el efecto secundario**:

   ```jsx
   useEffect(() => {
     console.log("El componente se montó o fue actualizado.");
     return () => {
       console.log("El componente se desmontó.");
     };
   }, [contador]);
   ```

   Aquí utilizamos el hook **`useEffect`** para definir un efecto secundario. El efecto secundario es una función que se ejecutará después de que el componente se monte y cada vez que **`contador`** cambie.

   Dentro del efecto secundario, se muestra un mensaje en la consola utilizando **`console.log()`**. El mensaje "El componente se montó o fue actualizado." se muestra después de que el componente se renderiza, y el mensaje "El componente se desmontó." se muestra justo antes de que el componente sea eliminado.

   Además, el efecto secundario devuelve una función de limpieza (cleanup function) que se ejecutará antes de que el componente se desmonte. En este ejemplo, no se utiliza para ninguna limpieza específica, pero en casos más complejos, esta función puede usarse para cancelar suscripciones, detener temporizadores o limpiar recursos antes de que el componente sea eliminado.

   La dependencia **`[contador]`** especifica que el efecto secundario solo se ejecutará nuevamente si el valor de **`contador`** cambia.

5. **Definir la función `incrementar` para actualizar el estado del contador**:

   ```jsx
   const incrementar = () => {
     setContador(contador + 1);
   };
   ```

   Aquí definimos la función **`incrementar`** que se llamará cuando se haga clic en el botón "Incrementar". Esta función utiliza la función **`setContador`** para actualizar el estado del contador, incrementándolo en uno.

6. **Renderizar la interfaz de usuario del componente**:

   ```jsx
   return (
     <div>
       <p>Contador: {contador}</p>
       <button onClick={incrementar}>Incrementar</button>
     </div>
   );
   ```

   En esta parte del código, utilizamos el operador **`return`** para renderizar la interfaz de usuario del componente. El valor actual del contador se muestra en un párrafo, y se crea un botón que llama a la función **`incrementar`** cuando se hace clic en él.

Con esta estructura, el componente **`Contador`** es funcional y se renderizará en la interfaz de usuario. Cuando hagas clic en el botón "Incrementar", el estado del contador se actualizará y se ejecutará el efecto secundario asociado al cambio del contador.

Usos comunes de **`useEffect`**:

- Obtener datos de una API.
- Suscribirse a eventos del navegador.
- Realizar operaciones de limpieza.
- Manipular el DOM.
- Actualizar el título de la página.
- Gestionar animaciones y transiciones.

Es importante tener en cuenta que el uso incorrecto de **`useEffect`** puede provocar efectos secundarios no deseados o ciclos de renderizado infinitos. Asegúrate de entender cómo funciona y de utilizarlo de manera adecuada según tus necesidades específicas.

Recuerda leer la documentación oficial de React para obtener más detalles sobre cómo utilizar **`useEffect`** y cómo manejar casos de uso más avanzados.
