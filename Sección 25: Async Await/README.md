# Sección 25: **Async Await**

## 25.1 ¿Que es Try Catch?

### Try catch

En programación, **try-catch** es una estructura de control que se utiliza para manejar errores en tiempo de ejecución. Básicamente, permite que el programa intente ejecutar un bloque de código y, si se produce un error, captura ese error y ejecuta un bloque de código alternativo en su lugar.

El bloque **`try`** contiene el código que puede generar una excepción, mientras que el bloque **`catch`** se utiliza para capturar y manejar esa excepción en caso de que ocurra.

Cuando se ejecuta un código dentro del bloque **`try`**, el programa monitorea si ocurre alguna excepción. Si no hay excepciones, el código se ejecuta normalmente y se salta el bloque **`catch`**. Sin embargo, si se produce una excepción dentro del bloque **`try, el programa salta a la sección`** catch` correspondiente y se ejecuta el código dentro de dicho bloque.

El uso del bloque **`try`** y **`catch`** es beneficioso porque permite que el programa continúe ejecutándose incluso si se produce un error, evitando que se detenga abruptamente. Además, brinda la oportunidad de manejar el error de manera adecuada, ya sea mostrando un mensaje de error al usuario o tomando medidas correctivas.

Aquí tienes un ejemplo sencillo en JavaScript que muestra cómo se utiliza **`try`** y **`catch`**:

```jsx
try {
  // Código que puede generar una excepción
  const num = 10 / 0; // Intentamos dividir entre cero
  console.log(num); // Esta línea no se ejecutará si se genera una excepción
} catch (error) {
  // Manejo de la excepción
  console.log("Se produjo un error:", error.message);
}
```

En este ejemplo, estamos intentando dividir el número 10 entre cero, lo cual generará una excepción porque la división por cero no está definida. En el bloque **`catch`**, capturamos la excepción y mostramos un mensaje de error que incluye el mensaje asociado al error. En este caso, imprimirá "Se produjo un error: Division by zero" en la consola.

El uso de **`try`** y **`catch`** permite que el programa controle el flujo de ejecución incluso cuando ocurren errores, lo que es especialmente útil al tratar con operaciones potencialmente problemáticas o dependientes de factores externos.
