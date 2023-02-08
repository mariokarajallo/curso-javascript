# Curso de java Script

## **Sección 1: Introducción al Curso y JavaScript**
- [1. Introducción al curso y JavaScript](#1-introducción-al-curso-y-javaScript)
- [2. Variable en JavaScript](#2-variable-en-javascript)



# 1. **Introducción al curso y JavaScript**
## 1. INTRODUCCIÓN

Se recomienda colocar el Script al final de un html o usualmente en un archivo externo, para que cargue lo mas pesado por ultimo.

Es recomendable colocar la etiqueta `script` antes de finalizar la etiqueta `body` y agregar rutas relativas, es decir colocar la dirección del archivo que contiene java script dentro de la misma carpeta del proyecto.

```jsx
// evita que se ejecute mas lineas de codigo siempre y cuando este dentro de una funcion.
return; 
```

“Un buen Código habla por si solo” (sugiere al habito de poder comentar nuestro código)

## Comentar el código en JavaScript

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

## la consola de javascript

todos los navegadores tienen una consola. 

Pueden trabajar en la consola y crear variables e imprimir en la consola

```jsx
console.log('hola consola')
console.error('esto es un error')

console.time('hola')
console.warn('eso no esta permitido')
console.timeEnd('hola')
```

## **Consideraciones en JavaScript con el ;**

En javaScript no necesariamente es obligatorio el ; pero es recomendable. es un buen habito.

Se recomienda una instrucción por linea.

Espacio o fabulación dentro de funciones.

## Plugins **ESLint para solucionar errores de código**

Es una herramienta que crea un ambiente de desarrollo mas profesional. Ayuda a corregir y detectar errores en la codificación.

# 2. **Variable en JavaScript**

## 2. VARIABLES

## 2.1 **Todo lo que debes saber de las variables con VAR**

Si un lenguaje tiene variable es un lenguaje de programación.

Existen 3 formas de crear una variable en javascript aunque en la nuevas versiones se utilizan 2.

Palabra reservada (var nombre=valor)

inicializar variable con un valor 

```jsx
var producto = 'monitor';
```

Se puede reasignar o cambiar su valor mas adelante.

javascript es un lenguaje de tipo dinámico, no se especifica el tipo de dato cuando se crea una variable.

También se puede inicializar sin valor y asignarlo después.

```jsx
var disponible;
disponible= true;
disponible= false;
```

inicializar múltiples variables, no es necesario escribir la palabra reservada `var` varias veces, si se debe colocar la `coma` ,

```jsx
var categoria = 'computadora',
		marca='hp',
		precio=500;
```

La variables no pueden iniciar con números ni ser palabras reservadas, si pueden tener números, letras, o _.

existen diferentes estilos para las variables: 

```jsx
	//camell case
var nombreProducto
//underscore o snake o serpiente
var nombre_producto_categoria
// pascal case
var Producto
```

## 2.2 **Todo lo que debes saber de las variables con LET**

cuando el nombre de una variable te subraya en puntos rojos quiere decir que existe una variable con el mismo nombre en el mismo nivel.

`LET`  te permite inicializar una variable, crear y reasignar valor.

```jsx
let = 'tablet';
```

También puedes crear la variable sin darle ningún valor.  Si llamas a consola su valor sera `undefined`

La diferencia con `VAR` es el `scope` de las variables.

El **scope** puede definirse como **el alcance que una variable tendrá en tu código**. En otras palabras, el scope **decide a qué variables tienes acceso**  en cada parte del código. Existen dos tipos de scope, el **scope global**  y el **scope local**.

### Scope Local

**Cuando puedes acceder a una variable únicamente en cierta parte del código**, se dice que esa variable está declarada en el **scope local**. Estas también son conocidas como **variables locales**.

### Scope Global

Se dice que una variable está en el **sope global** cuando **está declarada fuera de una función o de un bloque**. También son conocidas como **variables globales**.

## 2.3 **Todo lo que debes saber de las variables con CONST**

La reglas son las mismas para crear variables `const`, `let`, `var`.

diferencia es que CONST `no puede ser reasignado`.

las variables con CONST `deben inicializar con un VALOR`.

```jsx
const precio = 500;
```

