# Sección 30: **Debug, Medir Performance y Seguridad**

## 30.1 Performance.now()

En JavaScript, la función **`performance.now()`** se utiliza para medir el rendimiento y la precisión temporal de tu código. Proporciona un valor de tiempo de alta resolución y se utiliza comúnmente para medir el tiempo transcurrido entre dos puntos en el código, lo que permite evaluar el rendimiento de una función o sección específica.

La función **`performance.now()`** devuelve un valor de tipo **`DOMHighResTimeStamp`**, que representa el número de milisegundos transcurridos desde que se cargó la página o la aplicación. La precisión de este valor depende de la implementación del navegador y el sistema operativo, pero generalmente se mide con una resolución de microsegundos (1/1000 de milisegundo). A diferencia de otras funciones de tiempo en JavaScript, como **`Date.now()`** que tiene una precisión en milisegundos, **`performance.now()`** ofrece una mayor precisión temporal.

Aquí hay un ejemplo sencillo de cómo puedes utilizar **`performance.now()`** para medir el rendimiento de una porción de código en JavaScript:

```jsx
// Inicio de la medición
const startTime = performance.now();

// Código que deseas medir
for (let i = 0; i < 1000000; i++) {
  // Realizar operaciones aquí
}

// Fin de la medición
const endTime = performance.now();

// Calcular la duración en milisegundos
const duration = endTime - startTime;

console.log(`El código tardó ${duration} milisegundos en ejecutarse.`);
```

- En este ejemplo, se utiliza **`performance.now()`** para capturar la marca de tiempo antes y después de ejecutar un bucle que realiza alguna tarea repetitiva. Al restar **`startTime`** de **`endTime`**, obtendrás la duración en milisegundos que tardó en ejecutarse ese código específico.

Esta función es especialmente útil cuando deseas medir el rendimiento de diferentes algoritmos, funciones o enfoques para encontrar el más eficiente.

Recuerda que **`performance.now()`** puede variar ligeramente en su valor cada vez que se llama, puede variar en diferentes entornos y navegadores, y su precisión depende de la capacidad del hardware y la implementación del navegador en sí. Por lo que se recomienda realizar múltiples mediciones y calcular promedios para obtener resultados más precisos. Sin embargo, en general, se considera una forma confiable de medir el rendimiento dentro del navegador para optimizar y mejorar la eficiencia de tu código JavaScript.
