# Sección 31: **Testing**

## 31.1. Introducción al Testing

ventajas, consideraciones, tipos, herramientas

El testing en programación es el proceso de verificar y validar que un software o aplicación funciona correctamente y cumple con los requisitos establecidos. En el contexto de JavaScript, el testing se refiere a la creación y ejecución de pruebas para asegurar que el código JavaScript funcione como se espera y no presente errores o comportamientos inesperados.

### Ventajas del testing:

1. Detección temprana de errores: El testing permite identificar y corregir errores en las etapas iniciales del desarrollo, lo que evita que se propaguen y se conviertan en problemas más graves en el futuro.
2. Mejora de la calidad del software: Las pruebas exhaustivas ayudan a garantizar que el software cumpla con los requisitos y expectativas establecidos, lo que resulta en un producto de mayor calidad y confiabilidad.
3. Facilita el mantenimiento del código: Las pruebas unitarias y de integración brindan una capa adicional de seguridad al realizar cambios o actualizaciones en el código existente. Esto permite realizar refactorizaciones y mejoras sin temor a introducir nuevos errores.
4. Mayor confianza en los cambios: El testing proporciona confianza al equipo de desarrollo al realizar cambios en el código, ya que pueden verificar rápidamente que las funcionalidades existentes sigan funcionando correctamente después de las modificaciones.

### Consideraciones a tener en cuenta:

1. Planificación adecuada: Es importante dedicar tiempo y recursos suficientes para el testing. Incorporarlo como una parte integral del proceso de desarrollo y no considerarlo como una tarea secundaria.
2. Diseño de casos de prueba efectivos: Los casos de prueba deben cubrir tanto las funcionalidades esperadas como las no esperadas, con el objetivo de encontrar errores y fallos en el sistema.
3. Mantenimiento de las pruebas: Las pruebas deben actualizarse y adaptarse a medida que el software evoluciona. Es esencial revisar y ajustar las pruebas existentes para reflejar los cambios en el sistema.
4. Equilibrio entre cantidad y calidad: Es esencial encontrar un equilibrio entre la cantidad de pruebas realizadas y la calidad de las mismas. Realizar pruebas exhaustivas pero innecesarias puede ser ineficiente y consumir recursos innecesarios.
5. Mocking y stubbing: Considera utilizar técnicas de mocking y stubbing para crear pruebas más controladas y reproducibles.

### Tipos de pruebas:

1. Pruebas unitarias (Unit testing): Estas pruebas se centran en probar pequeñas unidades de código, como funciones o módulos, de forma aislada. El objetivo es asegurar que cada unidad funcione correctamente de manera independiente. Para realizar pruebas unitarias en JavaScript, se pueden utilizar frameworks como Jest, Mocha o Jasmine.
2. Pruebas de integración (Integration testing): Las pruebas de integración se enfocan en verificar que las diferentes unidades de código funcionen correctamente cuando se combinan o interactúan entre sí. Estas pruebas ayudan a identificar problemas de compatibilidad o comunicación entre módulos o componentes.
3. Pruebas de extremo a extremo (End-to-end testing): Estas pruebas evalúan el funcionamiento de la aplicación en su totalidad, desde la interfaz de usuario hasta la base de datos y los servicios de backend. El objetivo es asegurar que todos los componentes del sistema funcionen correctamente en conjunto. Para realizar pruebas de extremo a extremo en aplicaciones JavaScript, se pueden utilizar herramientas como Cypress, Puppeteer o Selenium.
4. Pruebas de rendimiento (Performance testing): Estas pruebas evalúan el rendimiento y la eficiencia de la aplicación en diferentes condiciones y cargas de trabajo. El objetivo es identificar cuellos de botella y optimizar el rendimiento del código. Herramientas como Lighthouse o WebPageTest pueden ser útiles para realizar pruebas de rendimiento en aplicaciones web basadas en JavaScript.
5. Pruebas de seguridad (Security testing): Estas pruebas buscan identificar vulnerabilidades y riesgos de seguridad en la aplicación. El objetivo es garantizar que la aplicación esté protegida contra ataques y accesos no autorizados. Herramientas como OWASP ZAP o Burp Suite pueden ser útiles para realizar pruebas de seguridad en aplicaciones web basadas en JavaScript.
6. Pruebas de regresión: Considera realizar pruebas de regresión para verificar que las modificaciones o actualizaciones en el código no hayan introducido nuevos errores o afectado el funcionamiento previo.

### Herramientas para el testing de JavaScript:

1. Mocha: Un framework de pruebas que se utiliza para realizar pruebas unitarias y de integración en JavaScript.
2. Jasmine: Otro framework popular para pruebas unitarias y de integración en JavaScript. Proporciona una sintaxis legible y amigable.
3. Jest: Un framework de pruebas desarrollado por Facebook, que combina pruebas unitarias, pruebas de integración y cobertura de código.en que
4. Cypress: Una herramienta de prueba de interfaz de usuario (UI) para probar aplicaciones web en tiempo real, con una sintaxis sencilla y potentes capacidades de depuración.
5. Selenium: Un conjunto de herramientas de automatización de pruebas de UI multiplataforma, ampliamente utilizado para probar aplicaciones web en diferentes navegadores.
6. Istanbul: Una herramienta de cobertura de pruebas para JavaScript. Genera informes detallados sobre la cobertura de código de las pruebas realizadas.

### Consideraciones adicionales:

1. Automatización de pruebas: Considera la automatización de pruebas para agilizar el proceso de testing y aumentar la eficiencia del equipo de desarrollo.
2. Pruebas en tiempo real: Explora herramientas que permitan realizar pruebas en tiempo real, lo que facilita la detección y corrección inmediata de errores.
3. Pruebas en entornos reales: Considera realizar pruebas en entornos similares a los de producción para validar el rendimiento y la funcionalidad del software en condiciones reales.
4. Integración continua y entrega continua: Considera adoptar prácticas de integración continua y entrega continua, que permiten ejecutar pruebas automáticamente y proporcionar retroalimentación rápida sobre la calidad del software.

Recuerda que el testing es un proceso continuo y evolutivo a lo largo del ciclo de vida del desarrollo de software. Es importante diseñar casos de prueba exhaustivos, considerar distintos escenarios y probar tanto las funcionalidades esperadas como las no esperadas. Además, la documentación y el seguimiento de errores encontrados durante las pruebas son elementos esenciales para mantener la calidad del software.

## 31.2 Creando un Mini Framework para Testing

Antes de entrar a ver las herramientas de testing, veamos un ejemplo de un mini framework de testing en JavaScript utilizando funciones y métodos personalizados.

```jsx
// Mini Framework de Testing

/**
 * El propósito de este código es proporcionar un mini framework de testing en JavaScript.
 * Permite definir pruebas y realizar comparaciones entre el resultado de las pruebas y los valores esperados.
 */

// Funciones

/**
 * Realiza la suma de dos valores.
 * @param {number} a - El primer valor a sumar.
 * @param {number} b - El segundo valor a sumar.
 * @returns {number} El resultado de la suma.
 */
function suma(a, b) {
  return a + b;
}

/**
 * Realiza la resta de dos valores.
 * @param {number} a - El valor del cual se va a restar.
 * @param {number} b - El valor a restar.
 * @returns {number} El resultado de la resta.
 */
function restar(a, b) {
  return a - b;
}

/**
 * Versión asíncrona de la función suma.
 * @param {number} a - El primer valor a sumar.
 * @param {number} b - El segundo valor a sumar.
 * @returns {Promise<number>} Una promesa resuelta con el resultado de la suma.
 */
async function sumaAsync(a, b) {
  return Promise.resolve(suma(a, b));
}

// Variables
let resultado, esperado;

// Pruebas
/**
 * Prueba de suma.
 */
resultado = suma(1, 2);
esperado = 3;
expected(esperado).toBe(resultado);

/**
 * Prueba de resta.
 */
resultado = restar(10, 5);
esperado = 5;
expected(esperado).toBe(resultado);
/**
 * Otra prueba de igualdad.
 */
expected(esperado).toEqual(resultado);

/**
 * Prueba asíncrona de suma.
 */
test("Suma 10 + 20 y el resultado debe ser 30", async () => {
  const resultado = await sumaAsync(10, 20);
  const esperado = 31;
  expected(esperado).toBe(resultado);
});

// Funciones de Testing

/**
 * Ejecuta una prueba y muestra el resultado en la consola.
 * @param {string} mensaje - Descripción de la prueba.
 * @param {function} callback - Función que contiene la lógica de la prueba.
 */
async function test(mensaje, callback) {
  try {
    await callback();
    console.log(`El Test: ${mensaje} se ejecutó correctamente`);
  } catch (error) {
    console.error("Error:");
    console.error(error);
  }
}

/**
 * Crea un objeto con métodos para realizar comparaciones entre el resultado de una prueba y un valor esperado.
 * @param {*} esperado - El valor esperado.
 * @returns {object} Objeto con los métodos toBe y toEqual para realizar las comparaciones.
 */
function expected(esperado) {
  return {
    /**
     * Compara si el resultado es igual al valor esperado utilizando el operador de igualdad estricta (===).
     * Muestra un mensaje en la consola indicando si la prueba pasó o no.
     * @param {*} resultado - El resultado de la prueba.
     */
    toBe(resultado) {
      if (resultado !== esperado) {
        console.error(
          `El ${resultado} es diferente a lo esperado; la prueba no pasó`
        );
      } else {
        console.log("La prueba pasó correctamente");
      }
    },
    /**
     * Compara si el resultado es igual al valor esperado utilizando el operador de igualdad (==).
     * Muestra un mensaje en la consola indicando si la prueba pasó o no.
     * @param {*} resultado - El resultado de la prueba.
     */
    toEqual(resultado) {
      if (resultado !== esperado) {
        console.error(
          `El ${resultado} no es igual a lo esperado; la prueba no pasó`
        );
      } else {
        console.log("La prueba pasó correctamente");
      }
    },
  };
}
```

- En primer lugar, se definen las funciones **suma** y **restar**, que realizan las operaciones matemáticas correspondientes.
- Luego se define la función **sumaAsync**, que es una versión asíncrona de la función **suma** y devuelve una promesa resuelta con el resultado de la suma.
- Se declaran variables **resultado** y **esperado** para almacenar los valores resultantes y esperados de las pruebas. Dentro de cada prueba, se utiliza la función expected para realizar las comparaciones entre el resultado de una operación y el valor esperado. Dependiendo del método utilizado (toBe o toEqual), se muestra un mensaje en la consola indicando si la prueba pasó o no.
- Test asincrono; Cada prueba se inicia llamando a test y pasando como primer parámetro un mensaje descriptivo de la prueba y como segundo parámetro una función anónima que contiene la lógica de la prueba.
- Luego Se declara la función test, que toma dos parámetros: mensaje y callback. Esta función se encarga de ejecutar una prueba. Dentro de test, se utiliza await para esperar a que se resuelva la promesa devuelta por callback. Callback, es una función que contiene la lógica de la prueba a realizar. Si la prueba se ejecuta sin errores, se muestra un mensaje de éxito en la consola mediante console.log. Si se produce un error, se captura mediante catch, se muestra un mensaje de error en la consola mediante console.error y se muestra el error capturado.
- Finalmente, se declara la función expected, que toma como parámetro el valor esperado y devuelve un objeto con dos métodos: toBe y toEqual. Estos métodos se utilizan para realizar las comparaciones entre el resultado de una prueba y el valor esperado.

En resumen, este mini framework de testing permite definir pruebas mediante la función **`test`**, realizar comparaciones mediante la función **`expected`** y mostrar los resultados de las pruebas en la consola. Proporciona una forma sencilla de implementar pruebas unitarias básicas en JavaScript.
