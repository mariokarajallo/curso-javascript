# Sección 32: **Jest**

## 32.1. Primeros pasos con Jest

El testing es una práctica esencial en el desarrollo de software que nos permite verificar la funcionalidad de nuestro código y detectar posibles errores. Jest es un framework de pruebas desarrollado por Facebook que facilita la escritura y ejecución de pruebas en JavaScript. A continuación, se presenta una guía paso a paso para comenzar a utilizar Jest en tus proyectos.

### 1. Instalación:

- Inicia tu proyecto de JavaScript ejecutando en la terminal **`npm init`** ubicado en la carpeta raíz. Completa los datos necesarios para generar el archivo **`package.json`**.
- Instala Jest como una dependencia de desarrollo ejecutando **`npm install --save-dev jest`**.
- Abre el archivo **`package.json`** en la raíz de tu proyecto, encuentra la sección **`"scripts"`** en el archivo. Modifica el script **`"test"`** para que ejecute Jest en su lugar. Puedes reemplazar la línea **`"echo \"Error: no test specified\" && exit 1"`** por **`"jest"`**.
- Al hacer este cambio, ahora podrás ejecutar tus pruebas utilizando el comando **`npm test`** o **`npm t`**, ya que Jest será el comando asociado al script "test" en el archivo **`package.json`**.

### 2. Estructura de archivos:

- Crea una carpeta llamada `tests` (doble guion bajo en el inicio y final) en la raíz de tu proyecto. Esta carpeta contendrá todos los archivos de prueba.
- Si deseas ubicar tus archivos de prueba fuera de la carpeta **`tests`**, asegúrate de que los nombres de los archivos terminen en **`.test.js`** o **`.spec.js`** para que Jest los detecte automáticamente.
- Ejemplo de como se ve la estructura inicial
  ![ejemplo estructura inicial](img/section-32-1.png)

### 3. Escritura de prueba/test:

- Cada archivo de prueba debe importar si es necesario el código que deseas probar.
- Utiliza el método **`test`** o **`it`** proporcionado por Jest para definir una prueba. Estos métodos reciben dos argumentos: una descripción de la prueba y una función que contiene las expectativas que se verificarán.
- Es importante tener en cuenta que puedes utilizar tanto **`test`** como **`it`** para definir tus pruebas, ya que son métodos equivalentes en Jest. Puedes elegir el que más te resulte cómodo.
- La función **`describe`** se utiliza para agrupar pruebas relacionadas dentro de un bloque. Toma dos argumentos: una descripción del grupo de pruebas y una función que contiene las pruebas dentro de ese grupo.
- Dentro de la función de prueba/test, utiliza las funciones **`expect`** y los `matchers` de Jest para definir las expectativas y comprobar los resultados esperados.
  - **expect:** es una función utilizada para definir las expectativas en tus pruebas. Proporciona una interfaz para realizar afirmaciones sobre los valores y comportamientos de tus programas.
  - Los **matchers** son métodos que se encargan de comparar el valor esperado con el valor actual y determinar si la prueba pasa o falla. Jest incluye una amplia gama de matchers para cubrir diferentes casos de uso.
    - Aquí hay algunos ejemplos de matchers comunes en Jest:
    - **`toBe(valorEsperado)`**: Compara si el valor actual es estrictamente igual al valor esperado utilizando el operador de igualdad (**`===`**).
    - **`toEqual(valorEsperado)`**: Compara si el valor actual es igual al valor esperado. A diferencia de **`toBe`**, **`toEqual`** realiza una comparación profunda de los objetos y matrices.
    - **`toBeDefined()`**: Verifica si el valor actual está definido.
    - **`toBeUndefined()`**: Verifica si el valor actual es **`undefined`**.
    - **`toBeNull()`**: Verifica si el valor actual es **`null`**.
    - **`toBeTruthy()`**: Verifica si el valor actual es considerado "verdadero" en un contexto booleano.
    - **`toBeFalsy()`**: Verifica si el valor actual es considerado "falso" en un contexto booleano.
    - **`toContain(valorEsperado)`**: Verifica si el valor esperado está contenido en el valor actual (para arreglos o cadenas de texto).
    - **`toBeGreaterThan(valorEsperado)`**: Verifica si el valor actual es mayor que el valor esperado.
    - **`toBeLessThan(valorEsperado)`**: Verifica si el valor actual es menor que el valor esperado.
    - **`toThrow()`**: Verifica si el valor actual lanza una excepción.
- Aquí tienes un ejemplo de cómo se usarían **`expect`** y los `matchers` en un ejemplo:
  ```jsx
  test("suma dos números", () => {
    expect(suma(2, 2)).toBe(4);
  });
  ```
  - En este caso, **`expect(suma(2, 2))`** define la expectativa de que la función **`suma`** con los argumentos 2 y 2 debe retornar 4. Luego, el matcher **`toBe(4)`** verifica si el resultado actual es igual a 4.
  - Recuerda que puedes combinar múltiples expectativas en una misma prueba para validar diferentes aspectos del código que estás probando.

### 4. Ejecución de pruebas:

- Ejecuta tus pruebas utilizando el comando **`npm test`** o **`npm t`** en la terminal.

```jsx
// archivo js de prueba
describe("Grupo de pruebas", () => {
  test("Hola mundo en jest", () => {
    // Aquí se pueden agregar expectativas y lógica de prueba
  });

  test("Otro Hola mundo", () => {
    // Aquí se pueden agregar expectativas y lógica de prueba
  });
});
```

- Analicemos el código de ejemplo
  - **`describe`**: Es una función que define un grupo de pruebas. Toma una descripción como primer argumento y una función como segundo argumento que contiene las pruebas asociadas al grupo.
  - **`"Grupo de pruebas"`**: Es una descripción que representa el grupo de pruebas. Puede ser un texto descriptivo que indique el propósito o la funcionalidad que se está probando.
  - **`test`**: Es un método que define una prueba individual dentro del grupo. Toma una descripción como primer argumento y una función como segundo argumento que representa la prueba en sí misma.
  - **`"Hola mundo en jest"`** y **`"Otro Hola mundo"`**: Son descripciones de las pruebas individuales. Al igual que con la descripción del grupo, estas descripciones deben ser claras y descriptivas para comprender lo que se está probando en cada caso.
  - **`() => {}`**: Es la función que representa una prueba en sí misma. Aquí es donde puedes agregar expectativas y lógica de prueba para verificar el comportamiento esperado de tu código.
    Recuerda que dentro de cada prueba, puedes utilizar las funciones **`expect`** y los matchers de Jest para definir las expectativas y verificar los resultados esperados.
  ```jsx
  //escribe en la terminal
  npm test
  ```
- Jest buscará automáticamente los archivos de prueba en la carpeta **`tests`** y los ejecutará.
- Verás el resultado de las pruebas en la terminal, mostrando si las pruebas han pasado o han fallado.
  ![resultado consola test](img/section-32-2.png)

Con Jest, también puedes aprovechar características adicionales como el mocking para simular comportamientos, pruebas asincrónicas para manejar operaciones asíncronas y la generación de informes de cobertura de código.
