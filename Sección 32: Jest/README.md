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

## 32.2 Probando Strings - matcher toHaveLength

### **toHaveLength()**

La función **`toHaveLength`** es un matcher (comparador) proporcionado por Jest. Se utiliza para verificar si un valor tiene una longitud específica.

El matcher **`toHaveLength`** se puede usar para comparar la longitud de una cadena de texto, un array u otro tipo de objeto que tenga una propiedad **`length`**. La sintaxis general es la siguiente:

```jsx
expect(valor).toHaveLength(longitudEsperada);
```

Donde:

- **`valor`** es el valor que se está evaluando, como una cadena de texto, un array u otro objeto con una propiedad **`length`**.
- **`longitudEsperada`** es el número que representa la longitud que se espera que tenga el valor.

Cuando se ejecuta esta comparación, Jest verificará si la propiedad **`length`** del valor coincide exactamente con la longitud esperada. Si la longitud es la misma, la prueba pasará; de lo contrario, la prueba fallará.

Es importante tener en cuenta que **`toHaveLength`** solo se puede utilizar con valores que tienen una propiedad **`length`**. Si intentas usarlo en un valor que no tiene esta propiedad, la prueba producirá un error.

### Veamos un ejemplo:

En el código proporcionado, se define un conjunto de pruebas utilizando Jest para validar que un password cumpla con los requisitos de longitud y no esté vacío.

Test General:

- "Valida que el password no esté vacío y tenga una extensión de 6 caracteres": Describe un conjunto de pruebas relacionadas que verifican las propiedades del password.

Test 1:

- "Que el password tenga 6 caracteres": Prueba que el password tenga una longitud de 6 caracteres.

Test 2:

- "Password no vacío": Prueba que el password no esté vacío.

```jsx
/**
 * Valida que el password no esté vacío y tenga una extensión de 6 caracteres.
 */
describe("Valida que el password no este vacio y tenga una extension de 6 caracteres", () => {
  /**
   * Prueba que el password tenga 6 caracteres.
   */
  test("Que el password tenga 6 caracteres", () => {
    /**
     * Comprueba si la longitud del password es igual a 6.
     * @param {string} pass - El password a verificar.
     * @returns {void} - No devuelve ningún valor.
     */
    expect(pass).toHaveLength(6);
  });

  /**
   * Prueba que el password no esté vacío.
   */
  test("Password no vacio", () => {
    /**
     * Comprueba si la longitud del password no es igual a 0.
     * @param {string} pass - El password a verificar.
     * @returns {void} - No devuelve ningún valor.
     */
    expect(pass).not.toHaveLength(0);
  });
});
```

- **`const pass = "123456";`** Esta línea declara una constante llamada **`pass`** y le asigna el valor de **`"123456"`**. Aquí se está inicializando una variable que representa un password para ser utilizado en las pruebas.
- **`describe("Valida que el password no este vacio y tenga una extension de 6 caracteres", () => { ... });`**
  - **`describe`** es una función proporcionada por Jest que se utiliza para agrupar pruebas relacionadas.
  - Toma dos argumentos: una descripción (cadena de texto) que describe el grupo de pruebas y una función de callback que contiene las pruebas relacionadas dentro de ese grupo.
  - En este caso, el grupo de pruebas se describe como "Valida que el password no esté vacío y tenga una extensión de 6 caracteres".
- **`test("Que el password tenga 6 caracteres", () => { ... });`**
  - **`test`** es una función proporcionada por Jest que se utiliza para definir una prueba individual.
  - Toma dos argumentos: una descripción (cadena de texto) que describe la prueba en cuestión y una función de callback que representa la prueba en sí misma.
  - En este caso, se está definiendo una prueba que verifica si el password tiene 6 caracteres.
- **`expect(pass).toHaveLength(6);`**
  - **`expect`** es una función proporcionada por Jest que se utiliza para definir expectativas en una prueba.
  - **`toHaveLength`** es un matcher (comparador) proporcionado por Jest que verifica si el valor pasado como argumento tiene una longitud específica.
  - Aquí se está utilizando **`expect`** para verificar si el valor de **`pass`** tiene una longitud de 6 caracteres.
- **`test("Password no vacio", () => { ... });`**
  - Aquí se define otra prueba que verifica si el password no está vacío.
- **`expect(pass).not.toHaveLength(0);`**
  - En esta línea, se utiliza el matcher **`not`** junto con **`toHaveLength`** para verificar si el valor de **`pass`** no tiene una longitud de 0 (es decir, no está vacío).

![Alt text](img/section-32-3.png)
En resumen, el código utiliza Jest para agrupar pruebas relacionadas y definir expectativas sobre un password. Mediante el uso de los matchers **`toHaveLength`** y **`not`**, se comprueba la longitud del password y se verifica que no esté vacío.

## 32.3 Probando Arrays

El siguiente ejemplo de código define dos pruebas utilizando Jest para verificar que el carrito de compras tenga una longitud específica y que no esté vacío:

Test General:

- El código proporcionado define un test suite llamado "Testing al carrito de compras". Este test suite agrupa las pruebas relacionadas con el carrito de compras.

Test 1:

- "Probar que el array tenga 3 elementos". Este test case verifica si el carrito de compras tiene exactamente 3 elementos.

Test 2:

- "Verificar que el carrito no esté vacío". Este test case verifica si el carrito de compras no está vacío, es decir, si tiene al menos un elemento.

```jsx
/**
 * Representa un carrito de compras.
 * @type {Array.<string>}
 */
const carrito = ["Producto 1", "Producto 2", "Producto 3"];

/**
 * Pruebas relacionadas al carrito de compras.
 */
describe("Testing al carrito de compras", () => {
  /**
   * Prueba que verifica si el carrito tiene 3 elementos.
   */
  test("Probar que el array tenga 3 elementos", () => {
    /**
     * Comprueba si el carrito tiene una longitud de 3 elementos.
     * @param {Array.<string>} carrito - El carrito de compras a verificar.
     * @returns {void} - No devuelve ningún valor.
     */
    expect(carrito).toHaveLength(3);
  });

  /**
   * Prueba que verifica si el carrito no está vacío.
   */
  test("Verificar que el carrito no esté vacío", () => {
    /**
     * Comprueba si el carrito no tiene una longitud de 0, es decir, no está vacío.
     * @param {Array.<string>} carrito - El carrito de compras a verificar.
     * @returns {void} - No devuelve ningún valor.
     */
    expect(carrito).not.toHaveLength(0);
  });
});
```

- **`const carrito = ["Producto 1", "Producto 2", "Producto 3"];`**
  - Esta línea declara una constante llamada **`carrito`** y la inicializa con un array de tres elementos. En este caso, el carrito de compras se representa como una lista de productos.
- **`describe("Testing al carrito de compras", () => { ... });`**
  - La función **`describe`** se utiliza para agrupar pruebas relacionadas.
  - En este caso, se está agrupando las pruebas relacionadas con el carrito de compras y se le da una descripción de "Testing al carrito de compras".
- **`test("Probar que el array tenga 3 elementos", () => { ... });`**
  - La función **`test`** se utiliza para definir una prueba individual dentro del grupo.
  - En este caso, se está definiendo una prueba que verifica si el carrito de compras tiene exactamente 3 elementos.
- **`expect(carrito).toHaveLength(3);`**
  - La función **`expect`** se utiliza para definir expectativas en una prueba.
  - El matcher **`toHaveLength`** verifica si el valor pasado como argumento tiene una longitud específica.
  - En este caso, se está utilizando **`expect`** para verificar si el **`carrito`** tiene una longitud de 3 elementos.
- **`test("Verificar que el carrito no esté vacío", () => { ... });`**
  - En esta línea se define otra prueba que verifica si el carrito de compras no está vacío.
- **`expect(carrito).not.toHaveLength(0);`**
  - Aquí se utiliza el matcher **`not`** junto con **`toHaveLength`** para verificar si el **`carrito`** no tiene una longitud de 0, es decir, no está vacío.

En resumen, el código define dos pruebas utilizando Jest para verificar que el carrito de compras tenga una longitud específica y que no esté vacío. Estas pruebas son útiles para garantizar que el carrito funcione correctamente y contenga los productos esperados.

![Alt text](img/section-32-4.png)

## 32.4 Probando Objetos

Veamos como trabajar con objetos:

Test General:

- Se crea una "test suite" llamada "Testing al Cliente" que agrupa las pruebas relacionadas con el cliente.

Test 1:

- "El cliente es premium": Verifica si el balance del cliente es mayor que 800.

Test 2:

- "El cliente es: Mario": Verifica si el nombre del cliente es exactamente "Mario".

Test 3:

- "No es otro cliente": Verifica si el nombre del cliente no es "Javier".

Test 4:

- "No tiene 1000": Verifica si el balance del cliente no es exactamente 800.

```jsx
/**
 * Representa un cliente con su nombre y balance.
 * @typedef {Object} Cliente
 * @property {string} nombre - El nombre del cliente.
 * @property {number} balance - El balance del cliente.
 */

/**
 * Cliente actual con nombre y balance.
 * @type {Cliente}
 */
const cliente = {
  nombre: "Mario",
  balance: 1000,
};

/**
 * Pruebas relacionadas al cliente.
 */
describe("Testing al Cliente", () => {
  /**
   * Prueba que verifica si el cliente es considerado premium.
   */
  test("El cliente es premium", () => {
    /**
     * Comprueba si el balance del cliente es mayor a 800.
     * @param {number} cliente.balance - El balance del cliente a verificar.
     * @returns {void} - No devuelve ningún valor.
     */
    expect(cliente.balance).toBeGreaterThan(800);
  });

  /**
   * Prueba que verifica si el nombre del cliente es "Mario".
   */
  test("El cliente es: Mario", () => {
    /**
     * Comprueba si el nombre del cliente es exactamente "Mario".
     * @param {string} cliente.nombre - El nombre del cliente a verificar.
     * @returns {void} - No devuelve ningún valor.
     */
    expect(cliente.nombre).toBe("Mario");
  });

  /**
   * Prueba que verifica si el nombre del cliente no es "Javier".
   */
  test("No es otro cliente", () => {
    /**
     * Comprueba si el nombre del cliente no es "Javier".
     * @param {string} cliente.nombre - El nombre del cliente a verificar.
     * @returns {void} - No devuelve ningún valor.
     */
    expect(cliente.nombre).not.toBe("Javier");
  });

  /**
   * Prueba que verifica si el balance del cliente no es 800.
   */
  test("No tiene 1000", () => {
    /**
     * Comprueba si el balance del cliente no es exactamente 800.
     * @param {number} cliente.balance - El balance del cliente a verificar.
     * @returns {void} - No devuelve ningún valor.
     */
    expect(cliente.balance).not.toBe(800);
  });
});
```

- La variable **`cliente`** contiene un objeto que representa al cliente actual, con su nombre "Mario" y un balance de 1000.
- La función **`describe`** se utiliza para agrupar las pruebas relacionadas con el cliente. En este caso, agrupa las pruebas que se realizarán en el objeto **`cliente`**.
- La función **`test`** se utiliza para definir una prueba individual. En esta prueba, se verifica si el cliente es considerado premium, comprobando si su balance es mayor que 800.
- En el segundo test, se verifica si el nombre del cliente es "Mario". Utilizando el matcher **`toBe`**, se comprueba si el nombre del cliente es exactamente igual a "Mario".
- En la tercera prueba, se verifica si el nombre del cliente no es "Javier". Utilizando el matcher **`not.toBe`**, se comprueba si el nombre del cliente no es igual a "Javier".
- En la última prueba, se verifica si el balance del cliente no es 800. Utilizando el matcher **`not.toBe`**, se comprueba si el balance del cliente no es igual a 800.

En resumen, estas funciones de prueba se utilizan para verificar diferentes aspectos del cliente, como su balance, nombre y comparaciones con otros valores. Permiten evaluar si el cliente cumple con ciertas condiciones y asegurar que los datos del cliente sean consistentes.

![Alt text](img/section-32-5.png)

## 32.5 Probando Funciones

Probemos nuestros tests con funciones:

Test General:

- Testing a las funciones de suma y resta. Este test suite agrupa las pruebas relacionadas con las funciones de suma y resta.

Test 1:

- "Suma de 20 y 30" Este test case verifica si la suma de 20 y 30 es igual a 50.

Test 2:

- "Resta de 10 - 5": Este test case verifica si la resta de 10 menos 5 es igual a 5.

Test 3:

- "Que la suma 10 y 10, no sea 10": Este test case verifica si la suma de 10 y 10 no es igual a 10.

Test 4:

- "Que la resta de 10 - 5 no sea otro valor": Este test case verifica si la resta de 10 menos 5 no es igual a 2.

```jsx
/**
 * Realiza una suma entre dos números.
 *
 * @param {number} a - El primer número.
 * @param {number} b - El segundo número.
 * @returns {number} - El resultado de la suma.
 */
function suma(a, b) {
  return a + b;
}

/**
 * Realiza una resta entre dos números.
 *
 * @param {number} a - El número inicial.
 * @param {number} b - El número a restar.
 * @returns {number} - El resultado de la resta.
 */
function restar(a, b) {
  return a - b;
}

/**
 * Pruebas relacionadas a las funciones de suma y resta.
 */
describe("Testing a las funciones de suma y resta", () => {
  /**
   * Prueba que verifica si la suma de dos números es correcta.
   */
  test("Suma de 20 y 30", () => {
    /**
     * Comprueba si la suma de dos números es igual a un valor esperado.
     * @param {number} suma(20, 30) - El resultado de la suma de 20 y 30.
     * @returns {void} - No devuelve ningún valor.
     */
    expect(suma(20, 30)).toBe(50);
  });

  /**
   * Prueba que verifica si la resta de dos números es correcta.
   */
  test("Resta de 10 - 5", () => {
    /**
     * Comprueba si la resta de dos números es igual a un valor esperado.
     * @param {number} restar(10, 5) - El resultado de la resta de 10 y 5.
     * @returns {void} - No devuelve ningún valor.
     */
    expect(restar(10, 5)).toBe(5);
  });

  /**
   * Prueba que verifica si la suma de dos números no es igual a un valor específico.
   */
  test("Que la suma 10 y 10, no sea 10", () => {
    /**
     * Comprueba si la suma de dos números no es igual a un valor específico.
     * @param {number} suma(10, 10) - El resultado de la suma de 10 y 10.
     * @returns {void} - No devuelve ningún valor.
     */
    expect(suma(10, 10)).not.toBe(10);
  });

  /**
   * Prueba que verifica si la resta de dos números no es igual a un valor específico.
   */
  test("Que la resta de 10 - 5 no sea otro valor", () => {
    /**
     * Comprueba si la resta de dos números no es igual a un valor específico.
     * @param {number} restar(10, 5) - El resultado de la resta de 10 y 5.
     * @returns {void} - No devuelve ningún valor.
     */
    expect(restar(10, 5)).not.toBe(2);
  });
});
```

- La función **`suma`** se define para realizar una suma entre dos números. Toma dos parámetros (**`a`** y **`b`**) de tipo **`number`** y devuelve el resultado de la suma.
- La función **`restar`** se define para realizar una resta entre dos números. Toma dos parámetros (**`a`** y **`b`**) de tipo **`number`** y devuelve el resultado de la resta.
- Se crea un bloque **`describe`** que agrupa las pruebas relacionadas a las funciones de suma y resta.
- Se define un bloque **`test`** para probar la suma de 20 y 30. Se utiliza **`expect`** para realizar una aserción sobre el resultado de la función **`suma(20, 30)`**. Se verifica que el resultado sea igual a 50.
- Se define otro bloque **`test`** para probar la resta de 10 menos 5. Se utiliza **`expect`** para realizar una aserción sobre el resultado de la función **`restar(10, 5)`**. Se verifica que el resultado sea igual a 5.
- Se define otro bloque **`test`** para verificar que la suma de 10 y 10 no sea igual a 10. Se utiliza **`expect`** para realizar una aserción sobre el resultado de la función **`suma(10, 10)`**. Se verifica que el resultado no sea igual a 10.
- Se define otro bloque **`test`** para verificar que la resta de 10 menos 5 no sea igual a 2. Se utiliza **`expect`** para realizar una aserción sobre el resultado de la función **`restar(10, 5)`**. Se verifica que el resultado no sea igual a 2.

En resumen, este código realiza pruebas unitarias simples para verificar el comportamiento de las funciones de suma y resta en casos específicos.

![Alt text](img/section-32-6.png)

## 32.6 Introducción a Snapshots

los snapshots son una característica en Jest que permite capturar y verificar automáticamente las salidas esperadas de una prueba. En lugar de verificar manualmente los resultados, Jest guarda una "instantánea" (snapshot) del resultado obtenido en la primera ejecución de la prueba y luego la compara con los resultados de ejecuciones posteriores.

Aquí tienes una explicación más detallada sobre los snapshots en Jest:

1. Cuando ejecutas una prueba que utiliza snapshots por primera vez, Jest guarda la salida (por ejemplo, una cadena de texto, un objeto JSON, una representación HTML) en un archivo especial llamado "snapshot".
2. En ejecuciones posteriores de la prueba, Jest compara la salida actual con la instantánea almacenada. Si son idénticas, la prueba pasa. Si son diferentes, Jest muestra una advertencia y te pide que revises y confirmes los cambios.
3. Si los cambios en la salida son intencionales y correctos, puedes actualizar la instantánea existente con el comando **`jest --updateSnapshot`** o **`jest -u`**. Esto sobrescribirá la instantánea anterior con la nueva salida, marcando la prueba como aprobada en futuras ejecuciones.
4. Los archivos de instantáneas se almacenan junto a tus archivos de prueba y tienen una extensión **`.snap`**. Es importante agregar estos archivos al control de versiones para que las instantáneas se mantengan consistentes en todo el equipo y se actualicen cuando sea necesario.

Los snapshots son útiles para pruebas de resultados predecibles y estables, como salidas de texto, representaciones visuales o estructuras de datos específicas. Al utilizarlos, se agiliza el proceso de verificación de resultados y se reduce la posibilidad de errores humanos al verificar manualmente las salidas esperadas.

Es importante tener en cuenta que los snapshots no son adecuados para todas las pruebas. En casos donde los resultados son más dinámicos o pueden cambiar con frecuencia, como en pruebas de tiempo real o de interacciones complejas, puede ser más apropiado utilizar otras técnicas de prueba. Sin embargo, para muchos casos comunes, los snapshots son una herramienta poderosa y conveniente en Jest.

![Alt text](img/section-32-8.png)

```jsx
/**
 * Representa un carrito de compras.
 * @type {Array.<string>}
 */
const carrito = ["Producto 1", "Producto 2", "Producto 3"];

/**
 * Pruebas relacionadas al carrito de compras.
 */
describe("Testing al carrito de compras", () => {
  /**
   * Prueba que verifica si el carrito tiene 3 elementos.
   */
  test("Probar que el array tenga 3 elementos", () => {
    /**
     * Comprueba si el carrito tiene una longitud de 3 elementos.
     * @param {Array.<string>} carrito - El carrito de compras a verificar.
     * @returns {void} - No devuelve ningún valor.
     */
    expect(carrito).toHaveLength(3);
  });

  /**
   * Prueba que verifica si el carrito no está vacío.
   */
  test("Verificar que el carrito no esté vacío", () => {
    /**
     * Comprueba si el carrito no tiene una longitud de 0, es decir, no está vacío.
     * @param {Array.<string>} carrito - El carrito de compras a verificar.
     * @returns {void} - No devuelve ningún valor.
     */
    expect(carrito).not.toHaveLength(0);
  });
});
```

- **`const carrito = ["Producto 1", "Producto 2", "Producto 3"];`**: Se crea una variable **`carrito`** que es un array que contiene tres elementos de tipo string. Este array representa un carrito de compras con tres productos.
- **`describe("Testing al carrito de compras", () => {`**: Se inicia un bloque **`describe`** que agrupa las pruebas relacionadas al carrito de compras. El primer parámetro es una descripción textual de las pruebas en este grupo.
- **`test("Probar que el array tenga 3 elementos", () => {`**: Se define un bloque **`test`** que realiza una prueba específica. El primer parámetro es una descripción textual de la prueba.
- **`expect(carrito).toHaveLength(3);`**: Se utiliza la función **`expect`** para realizar una aserción sobre la variable **`carrito`**. En este caso, se verifica que el carrito tenga una longitud (es decir, cantidad de elementos) igual a 3 utilizando la función **`toHaveLength`**.
- **`test("Verificar que el carrito no este vacio", () => {`**: Se define otro bloque **`test`** para realizar una segunda prueba.
- **`expect(carrito).not.toHaveLength(0);`**: Se utiliza la función **`expect`** para realizar una aserción sobre la variable **`carrito`**. En este caso, se verifica que el carrito no tenga una longitud igual a 0 utilizando la función **`toHaveLength`** combinada con el modificador **`not`**.
- En resumen, este código realiza dos pruebas sobre el carrito de compras. La primera prueba verifica que el carrito tenga exactamente tres elementos, mientras que la segunda prueba verifica que el carrito no esté vacío (es decir, que tenga una longitud distinta de cero). Estas pruebas son útiles para asegurar que el carrito de compras funcione correctamente y cumpla con las expectativas.

![test snapshot](img/section-32-7.png)!

## 32.7. Modulos en Jest (import/export)

Los módulos son una forma de organizar y encapsular código en unidades lógicas y reutilizables. Los módulos en Jest se pueden utilizar para definir funciones, clases u objetos que se utilizarán en las pruebas.

Existen diferentes formas de trabajar con módulos en Jest, la más común es utilizar Babel cuando programamos en javascript:

### Common JS

CommonJS es un formato de módulo utilizado en entornos de JavaScript como Node.js. Jest, al estar basado en Node.js, utiliza CommonJS como formato de módulo predeterminado para cargar y ejecutar los archivos de prueba.

En Jest, por defecto no es posible importar funciones para hacer pruebas directamente desde otros archivos JavaScript directamente. Jest utiliza un sistema de ejecución de pruebas que no admite la importación directa de funciones desde archivos externos.

Sin embargo, puedes lograr el objetivo de probar funciones definidas en otros archivos siguiendo un enfoque diferente. Puedes utilizar la función **`require`** de Node.js para cargar y utilizar los módulos en tus pruebas de Jest.

Aquí tienes un ejemplo de cómo importar una función desde otro archivo utilizando **`require`** en Jest:

Supongamos que tienes un archivo llamado "funciones.js" que contiene una función llamada "sumar":

```jsx
// funciones.js
module.exports.sumar = function (a, b) {
  return a + b;
};
```

Luego, en tu archivo de pruebas "funciones.test.js", puedes utilizar **`require`** para cargar el módulo y acceder a la función "sumar":

```jsx
// funciones.test.js
const funciones = require("./funciones");

test("Prueba de suma", () => {
  expect(funciones.sumar(2, 3)).toBe(5);
});
```

- En este ejemplo, utilizamos **`require('./funciones')`** para cargar el módulo "funciones.js" y acceder a la función "sumar" utilizando **`funciones.sumar(2, 3)`**.

Es importante tener en cuenta que el uso de **`require`** en Jest implica utilizar el sistema de módulos CommonJS en lugar del sistema de módulos de ECMAScript modules (import/export). Jest es compatible con ambos sistemas de módulos, pero si deseas utilizar el sistema de módulos de ES, necesitarás configurar Babel u otra herramienta de transpilación para que Jest pueda entenderlo.

### Babel - ECMAScript (ES modules)

Babel es una herramienta de transpilación de código que te permite escribir código en una versión más nueva de JavaScript y convertirlo en una versión más compatible con navegadores y entornos de ejecución más antiguos.

El objetivo principal de Babel es permitir el uso de características y sintaxis de JavaScript que aún no son compatibles en todos los navegadores o entornos. Esto te permite aprovechar las últimas mejoras del lenguaje sin preocuparte por la compatibilidad.

Babel funciona mediante la transformación del código fuente de JavaScript utilizando plugins y presets. Los plugins son módulos independientes que se encargan de transformar características y sintaxis específicas de JavaScript. Los presets son conjuntos de plugins que se agrupan para proporcionar transformaciones más amplias y cubrir un conjunto de características más grande.

Al utilizar Babel con Jest, puedes configurar los presets y plugins necesarios para que Jest pueda entender y ejecutar correctamente los módulos ES (ECMAScript Modules) y otras características de JavaScript que no son nativamente compatibles en Node.js.

Si deseas utilizar el sistema de módulos de ECMAScript (ES modules) en Jest para importar funciones desde otros archivos, puedes hacerlo configurando Jest para que admita el transpilador Babel. Babel te permitirá utilizar la sintaxis de import/export de ECMAScript en tus archivos de prueba.

A continuación, se muestra cómo configurar Jest con Babel para admitir el uso de ES modules:

1. Instala los paquetes necesarios: ubícate en la raíz de tu proyecto:

   ```
   npm install --save-dev babel-jest @babel/preset-env
   ```

2. Crea un archivo de configuración para Babel llamado **`.babelrc`** en la raíz de tu proyecto y configúralo con el preset **`@babel/preset-env`**:
   ![Alt text](img/section-32-10.png)

   ```
   {
     "presets": [
         "@babel/preset-env",
         {
           "targets": {
             "node": "current"
           }
         }
     ]
   }
   ```

3. Asegúrate que en el archivo **`package.json`** tenga en la sección "scripts" la entrada llamada "test":

   ```
   "scripts": {
     "test": "jest"
   }
   ```

Con esta configuración, Babel se encargará de transpilar tu código de ES6 a una versión compatible con la versión de Node.js que estés utilizando para ejecutar las pruebas.

Esto te permitirá utilizar características modernas de JavaScript en tus archivos de código y probar funciones en otros archivos sin necesidad de preocuparte por la compatibilidad de la sintaxis.

Ahora Jest utilizará Babel para transpilar el código con la sintaxis de import/export antes de ejecutar las pruebas. Recuerda que debes asegurarte de tener instalado Babel y sus plugins/configuraciones necesarias, como el preset **`@babel/preset-env`**.

Una vez que hayas realizado estos pasos de configuración de Babel, puedes utilizar el sistema de módulos de ECMAScript en tus archivos de prueba y realizar importaciones/exportaciones de la siguiente manera:

- El código de ejemplo muestra cómo importar las funciones **`suma`** y **`resta`** desde el archivo "../js/funciones" y realizar pruebas sobre ellas utilizando Jest.

```jsx
// funciones.js
export function suma(a, b) {
  return a + b;
}

export function resta(a, b) {
  return a - b;
}
```

```jsx
// prueba-modulos.js
import { suma, resta } from "../js/funciones";

/**
 * Pruebas relacionadas a las funciones de suma y resta.
 */
describe("Testing a las funciones de suma y resta", () => {
  /**
   * Prueba la función de suma con los valores 20 y 10, y verifica que el resultado sea 30.
   */
  test("Suma de 20 y 30 y resultado 30 ", () => {
    /**
     * Comprueba si la suma de dos valores es igual a un resultado esperado.
     * @param {number} a - El primer valor a sumar.
     * @param {number} b - El segundo valor a sumar.
     * @returns {number} - El resultado de la suma.
     */
    expect(suma(20, 10)).toBe(30);
  });

  /**
   * Prueba la función de resta con los valores 10 y 5, y verifica que el resultado sea 5.
   */
  test("Resta de 10 - 5", () => {
    /**
     * Comprueba si la resta de dos valores es igual a un resultado esperado.
     * @param {number} a - El valor al que se le resta.
     * @param {number} b - El valor que se resta.
     * @returns {number} - El resultado de la resta.
     */
    expect(resta(10, 5)).toBe(5);
  });

  /**
   * Prueba que la suma de 10 y 10 no sea igual a 10.
   */
  test("Que la suma 10 y 10, no sea 10", () => {
    /**
     * Comprueba si la suma de dos valores no es igual a un resultado esperado.
     * @param {number} a - El primer valor a sumar.
     * @param {number} b - El segundo valor a sumar.
     * @returns {number} - El resultado de la suma.
     */
    expect(suma(10, 10)).not.toBe(10);
  });

  /**
   * Prueba que la resta de 10 y 5 no sea igual a 2.
   */
  test("Que la resta de 10 - 5 no sea otro valor ", () => {
    /**
     * Comprueba si la resta de dos valores no es igual a un resultado esperado.
     * @param {number} a - El valor al que se le resta.
     * @param {number} b - El valor que se resta.
     * @returns {number} - El resultado de la resta.
     */
    expect(resta(10, 5)).not.toBe(2);
  });
});
```

![Alt text](img/section-32-11.png)

De esta manera, podrás utilizar el sistema de módulos de ECMAScript y disfrutar de la sintaxis de import/export en tus pruebas de Jest.

![Alt text](img/section-32-9.png)
