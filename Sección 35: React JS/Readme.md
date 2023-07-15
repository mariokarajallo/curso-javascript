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
