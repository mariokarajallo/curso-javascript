# Curso de java Script

## **Sección 1: Introducción al Curso y JavaScript**
- [1. Introducción al curso y JavaScript](#1-introducción-al-curso-y-javaScript)



# 1. **Introducción al curso y JavaScript**
### 1. INTRODUCCIÓN

Se recomienda colocar el Script al final de un html o usualmente en un archivo externo, para que cargue lo mas pesado por ultimo.

Es recomendable colocar la etiqueta `script` antes de finalizar la etiqueta `body` y agregar rutas relativas, es decir colocar la dirección del archivo que contiene java script dentro de la misma carpeta del proyecto.

```jsx
// evita que se ejecute mas lineas de codigo siempre y cuando este dentro de una funcion.
return; 
```

“Un buen Código habla por si solo” (sugiere al habito de poder comentar nuestro código)

### Comentar el código en JavaScript

```jsx
// comentario de una sola linea

/*
comentarios de multiples
lineas
*/
```

## Template String

En ES6 aparecen los **JavaScript template Strings** que nos permiten usar plantillas sencillas directamente en el código. Las plantillas son muy practicas y están delimitadas **por el caracter ” `  “** . Nos permiten simplificar sobre manera la forma de construir una estructura **HTML dinámica de forma sencilla.**

```jsx
//template string 
`${variable}`
```

### la consola de javascript

todos los navegadores tienen una consola. 

Pueden trabajar en la consola y crear variables e imprimir en la consola

```jsx
console.log('hola consola')
console.error('esto es un error')

console.time('hola')
console.warn('eso no esta permitido')
console.timeEnd('hola')
```

### **Consideraciones en JavaScript con el ;**

En javaScript no necesariamente es obligatorio el ; pero es recomendable. es un buen habito.

Se recomienda una instrucción por linea.

Espacio o fabulación dentro de funciones.

### Plugins **ESLint para solucionar errores de código**

Es una herramienta que crea un ambiente de desarrollo mas profesional. Ayuda a corregir y detectar errores en la codificación.