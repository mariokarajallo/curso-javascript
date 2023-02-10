# Curso de java Script

## **Sección 1: Introducción al Curso y JavaScript**
- [1. Introducción al curso y JavaScript](#1-introducción-al-curso-y-javaScript)
- [2. Variable en JavaScript](#2-variable-en-javascript)
- [3. Strings o Cadenas de Texto y sus Métodos](#3-strings-o-cadenas-de-texto-y-sus-métodos)
- [4. Números en JavaScripts](#4-números-en-javascripts)



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

# 3. **Strings o Cadenas de Texto y sus Métodos**

## 3.1 Crear Strings en JavaScript

Representan un texto que se puede asignar a una variable.

Existen 3 formas de crearlos que son más populares.

- Dos formas de crear una cadena de `texto primitiva` y Una forma no tan común.

```jsx
/***Forma Primitiva***/

//comillas dobles o sencillas ya lo convierte en string automaticamente
const producto = 'Monitor 20 Pulgadas'; // Utiliza comillas sencillas
const producto2 = "Monitor 20 Pulgadas"; // Utiliza comillas o dobles

// La segunda forma 
const producto2 = String('monitor');

/***Forma menos comun***/

// tercera forma menos comun, objeto de tipo string
const producto3 = new String('monitor');

//escapando un string con barra invertida -> \
// Ejemplo con Pulgadas
const producto4 = "Monitor 24\""; //Monitor 24"
```

Reglas para crear String:

- Utilizar comillas dobles o sencillas al inicio o final, pero no se pueden mezclar.
- Escapar comilla en un string → \”

## 3.2 String Methods - INCLUDES y LENGTH

Veamos algunos métodos existentes en los strings o cadenas de Texto:

### Lenght

Método para saber cuantas letras tiene una variable tipo String o cadena de texto. length es de los muy pocos métodos que no usan () y es más que nada porque no es un método como tal sino una propiedad.

```jsx
const producto = 'Monitor 20 Pulgadas';
console.log(producto.length)
```

### IndexOf()

Revisa si existe una palabra dentro de la variable y te da la posición

```jsx
const producto = 'Monitor 20 Pulgadas';
console.log(producto.indexOf("Pulgadas")) // Nos dirá que posición tiene el texto en caso de encontrarlo
console.log(producto.indexOf('Tablet')); // -1 Significa que no lo pudo encontrar
```

### Includes()

te devuelve True o False si existe la palabra dentro de una variable. Puede distinguir entre mayúsculas y minúsculas

```jsx
const producto = 'Monitor 20 Pulgadas';
console.log(producto.includes('monitor')) // false
console.log(producto.includes('Monitor')); // true

```

## 3.3 Concatenar un String y Template Strings

Método `concat` une dos cadenas de texto o concatena texto y obtengo una sola solida

```jsx
const producto ="Monitor 20 Pulgadas";  
const precio ='30 usd';

console.log(producto.concat('En Descuento')); // Concactenar un string
console.log(producto.concat(precio)); // Concacatenar una variable

// otras maneras de concatener con el simbolo +
console.log(producto + " con un precio de: " + precio);
console.log("el producto " + producto + " tiene un precio de "+ precio);

//en lugar de utilizar signo de + puedes usar ,
console.log("el producto ",producto," tiene un precio de ",precio);

// mejor forma de concatener variables template literal o template string
// comillas inclinadas o "backtips"
// las variables se agregan con las sintaxis ${variable}
console.log(`El producto ${producto} tiene un precio de $ ${precio}`);

```

## 3.4 Cortar Espacios en Blanco de un String

Eliminar espacios en blanco en una cadena de texto, se utiliza para validar formularios.

en java script se puede utilizar los métodos en forma encadenada, es decir colocar un método tras otro se lo conoce como `channing`

```jsx
const producto ="          Monitor 20 Pulgadas          ";
console.log(producto);
console.log(producto.length); //49

//eliminar espacios en blanco
console.log(producto.trimStart()); //elimina espacios en blanco desde el inicio
console.log(producto.trimEnd());//elimina espacios del final de la palabra

// Los métodos en javaScript se pueden encadenar, es decir, colocarse uno junto al otro
console.log(producto.trimStart().trimEnd()); //elimina espacios en blanco al inicio y final
console.log(producto.trim()); // elimina espacios en blanco al inicio y final, es un metodo antiguo
```

## 3.5 String Methods - Replace, Slice y Substring

```jsx
const producto ="Monitor 20 Pulgadas";

//.replace
// para reemplazar una cadena de texto por otra nueva
console.log(producto);
console.log(producto.replace('Pulgadas','"'));
console.log(producto.replace('Monitor', 'Pantalla Curvo'));

//.slice
// para cortar o extraer una parte de una cadena de texto
// se le pasa la posicion del inicio y del final de la cadena de texto a cortar
console.log( producto.slice(0, 10)); // Iniciar en 0 y cortar hasta 10
console.log(producto.slice(8));// Cortar desde el 8 hasta el fin
console.log(producto.slice(2, 10)); // cortar desde 2 hasta el 10

console.log(producto.slice(2,1)); // NO VA A HACER NADA, POR que el primer indice debe ser mayor no corta hacia atras

// alternativa a slice
// .substring()
// si puede cortar de adelante para atras
console.log(producto.substring(0,10));
console.log(producto.substring(2,1));// Si el número es mayor al segundo, va a cortar hacia atras (voltear los números)

const usuario = "Juan";
console.log(usuario.substring(0,1));

//chartAt()
// corta o extrae solo el primer caracter, dependiendo la posicion que elijas
console.log(usuario.charAt(0));
```

## 3.6 String Methods - Repeat y Split

```jsx
const producto ="Monitor 20 Pulgadas";

//.repeat 
// te va a permitir repetir una cadena de texto
const texto= ' en Promocion'.repeat(4); // repite 4 veces el texto
console.log(texto);
console.log(`${producto} ${texto}!!! `);
console.log(producto.repeat(2.2)); // va a redondear a entero

//.split 
// dividir un string y convierte en un array 
const hobbies= "jugar, caminar, cantar, bailar, programar";
// pasar como parametro un caracter por el cual va a dividir el string
console.log(hobbies.split(", "));
```

## 3.7 String Methods - Convertir a Mayusculas o Minusculas

```jsx
const producto ="Monitor 20 Pulgadas";
console.log(producto);

// .toUpperCase()
// convierte la cadena de texto a mayusculas
console.log(producto.toUpperCase());

// .toLowerCase
// convierte la cadena de texto en minusculas
console.log(producto.toLowerCase());

//.toString convierte numero a texto
const precio=6000;
console.log(precio);
console.log(precio.toString());
```
# 4. **Números en JavaScripts**