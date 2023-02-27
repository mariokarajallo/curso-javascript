# Curso de java Script

## **Sección 1: Introducción al Curso y JavaScript**
- [1. Introducción al curso y JavaScript](#1-introducción-al-curso-y-javaScript)
- [2. Variable en JavaScript](#2-variable-en-javascript)
- [3. Strings o Cadenas de Texto y sus Métodos](#3-strings-o-cadenas-de-texto-y-sus-métodos)
- [4. Números en JavaScripts](#4-números-en-javascripts)
- [5. Operadores en JavaScript](#5-operadores-en-javascript)
- [6. Booleans en JavaScript](#6-booleans-en-javascript)
- [7. Objetos en JavaScript](#7-objetos-en-javascript)
- [8. Arrays o Arreglos en JavaScript](#8-arrays-o-arreglos-en-javascript)
- [9. Funciones en JavaScript](#9-funciones-en-javascript)
- [10. Estructuras de Control](#10-estructuras-de-control)
- [11. Iteradores en JavaScript](#11-iteradores-en-javascript)
- [12. Array Methods](#12-array-methods)



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

## 4.1 **Crear Números en JavaScript**

- En JS todos los números se crean de la misma forma. No debes especificar el tipo de datos a pesar de que sean enteros, fracciones, float incluso números negativos.
- Si le ponemos comillas seria un string de números.

```jsx
// Una nota muy importante es que en la consola los números 
// se muestran de diferente color cuando es número que cuando es
// un string que representa un número

const numero6 = 20;
const numero7 = "20";

// Crear Números

const numero1 = 30;
const numero2 = 20;
const numero3 = 20.20;
const numero4 = .10213;
const numero5 = -3;

// Otra forma de crear número de tipo objeto

const numero8 = new Number(20);
console.log(numero8);
```

## 4.2 Operaciones en JavaScript

Operaciones básicas

```jsx
// Operaciones
let resultado;
const numero 1 = 30;
const numero 2 = 20

// Estos signos se les conoce como operadores,
// hay para realziar sumas, multiplicaciones, restas y comparar
// si un número es mayor a otro

// Suma
resultado = numero1 + numero2;
// Resta
resultado = numero1 - numero2;
// Mult
resultado = numero1 * numero2;
// Division
resultado = numero1 / numero2;
// Modulo
resultado = numero1 % numero2;

console.log(resultado);
```

## 4.3 El objeto Math

Math es parte de la ventana global de JavaScript, tiene una serie de operaciones que pueden ser muy útiles y algunas actúan de forma algo extraña.

```jsx
let resultado; 

// Pi
resultado = Math.PI;
// redondeo a numeros enteros
resultado = Math.round(2.5);
// redondeo hacia arriba
resultado = Math.ceil(2.2);
// redondeo hacia abajo
resultado = Math.floor(2.9);
// Raiz cuadrada
resultado = Math.sqrt(144); //12
// valor Abssoluto
resultado = Math.abs(-300); //300
// Potencia
resultado = Math.pow(8, 3); //512
// Minimo, saber el menor numero de una serie de valores
resultado = Math.min(3,5,1,2,9,4,2, -3);
// Max, saber el mayor numero de una serie de valores
resultado = Math.max(4,1,21,4,15,5,11,5);
// Aleatorio, pocas veces te dan numeros entero 
resultado = Math.random();
// Aleatorio dentro de un rango: ejemplo numero del 0 al 30
resultado =  Math.floor( Math.random() * 30 );

console.log(resultado);
```

## 4.4 El orden de las operaciones

El Orden en que se ejecutan las operaciones en JavaScript es igual que en la escuela, es decir multiplicaciones y divisiones se ejecutan primero, sumas y restas después.

```jsx
let resultado 
// El orden de las operaciones

resultado = 20 + 30 * 2; // 80
resultado =  ( 20 + 30 ) * 2; // los parentecis se ejecutan primero

// ejemplo, 20% De descuento en un carrito de compra.
resultado = ( 20+10+30+40+50 ) * .20;

console.log(resultado);
```

## 4.5 Incrementos o Decrementos

Incrementando un valor de 1 en 1 o en determinada cantidad

```jsx
// Incluir incremento por 1 y menos 1

let puntaje = 5;
//realiza el incremento o decremento despues de llamar a la variable
puntaje++;
puntaje--;

// realiza el incremento o decremento antes de llamar a la variable
++puntaje;
--puntaje;

//incremento o decremento con otros valores

puntaje += 3;
puntaje -= 3;

console.log(puntaje);
```

## 4.6 Convertir un Strings a números

Veamos un par de funciones para convertir a números

```jsx
const numero1 = "20";
const numero2 = "20.2";
const numero3 = "Uno";
const numero4 = 20;

console.log(numero1);

// Convertir de Strings a Números flotantes o Enteros

console.log(Number.parseInt(numero1)); // Convertir de String a Número entero
console.log(Number.parseFloat(numero2)); // Convertir a número con decimales 
console.log(Number.parseInt(numero3)); // resultado del tipo -> NaN

// Revisar si un número es entero
console.log(Number.isInteger(numero4) ); // Revisar si un número es entero o no devuelve tru o false
console.log(Number.isInteger(numero3) ); // devuelve true o false

// Convertir String a numero
console.log(numero4.toString());
```

# 5. **Operadores en JavaScript**

## 5.1 Operador Mayor que y Menor Que

Previamente ya vimos que existen operadores de suma, resta, multiplicación, pero existen unos muy útiles de comparación

Devuelven como resultado valores `Booleans`. Verdadero, Falso.

```jsx
const numero1 = 20;
const numero2 = "20";
const numero3 = 30;

// Operador Mayor a 
console.log( numero1 > numero3 );
console.log( numero3 > numero1 );

// Operador Menor que
console.log(numero3 < numero1);
```

## 5.2 Comparar 2 valores

Operadores que sirven para revisar si son iguales

```jsx
const numero1 = 20;
const numero2 = "20";
const numero3 = 30;

// Revisar si 2 valores son iguales o diferentes
// no es un comparador muy estricto, solo se fija en el valor
console.log(numero1 == numero3); //false
console.log(numero1 == numero2); //true

// Typeof
// devuelve el tipo de valor
console.log( typeof numero1 );
console.log( typeof numero2 );

// Operador estricto (revisa valor y tipo de dato)
// se fija en el valor y en el tipo de dato
console.log(numero1 === numero2 ); //false
// podemos convertir un tipo de variable y comparar
console.log(numero1 === parseInt(numero2)) //true

// Diferente a !=
// no importa si es mayor o menor, o igual compara si son diferentes
console.log(numero1 != numero3);
console.log(numero1 != numero2);//false
console.log(numero1 !== numero2);// true
console.log(numero1 !== parseInt(numero2));// false
```

## 5.3 Comprar Null y undefined en JavaScript

### Null y Undefined

En javascript existen diferentes tipos de datos primitivos a los que hemos visto, además de `string` y `number` se tienen `booleans` que son `true o false`,  y existen un par más llamados `undefined` y `null`

```jsx
// veamos un ejemplo de undefined.
let numero;

//La variable esta definida pero su valor no, por lo tanto es undefined.../
console.log(numero); // undefined
console.log(typeof numero) //

// En el caso de null es más bien asignarlo
let numero2 = null;
console.log(numero2);
// ahora esto nos dirá que es un objeto, la especificación de ecma que es quien define el standard del lenguaje dice que null debe ser un objeto
console.log(typeof numero2); 

// Comparando null y undefined - Comparar un valor null y un undefined 
// puede ser de las cosas más complicadas
console.log (numero == numero2); //true

// Puedes ver que el resultado es true, a pesar de que numero 
// no tiene un valor, eso usualmente nos lleva a ejecución de código no deseada o con comportamientos extraños ya que comparamos 
// un valor que no existe, y nos retorna true

// para ello llega a ser muy  util el comparador estricto
console.log(numero === numero2); //false

// De esta forma no comparamos un falso positivo y evitamos errores.
```

# 6. **Booleans en JavaScript**

## 6.1 Crear y Comparar Booleans

El tipo de dato boolean solo puede tener 2 valores, true o false:

- esta prendido o apagado
- si o no

```jsx
const boolean1 = true;
const boolean2 = false;

console.log(boolean1);
console.log(boolean2);

// que tipo de datos es
console.log(typeof boolean2);

//También un Boolean se puede crear con la palabra new

const boolean3 = new Boolean(true);
console.log(boolean3);

// podemos ver que es una variable de tipo objeto
// no una variable primitiva
console.log(typeof boolean3);
```

## 6.2 Más sobre Comparar Booleans

Comparar booleans es exactamente igual que cualquier comparación de números o strings

```jsx
const boolean1 = true;
const boolean2 = false;

// comparar 2 variables
console.log(boolean1 === boolean2); //false

console.log(boolean1 === true); // comparar si un boolean es verdadero //true
console.log(boolean2 === true);// comparar si un boolean es verdadero // false

// Aún no hemos llegado a ello, pero muchas personas cometen el
// siguiente error cuando escriben código javascript en un if

if(boolean1 === true) {
    console.log('si es true')
} else {
    console.log('no, no es true')
}

// Pero este código se puede simplificar quitando
// el === true porque ya sabemos que la variable es true

// Este mismo ejemplo aplica si un usuario esta autenticado puede
// darle me gusta a una foto o ver una página, así como si ya tienes
// una cuenta en netflix y has pagado
```

## 6.3 Buenas practicas a la hora de evaluar un Boolean

Existe otra forma de comparar si un valor es verdadero y es por medio de algo llamado un operador ternario

```jsx
const boolean1 = true;
const boolean2 = false;

if(boolean1) {
    console.log('si es true')
} else {
    console.log('no, no es true')
}

//El código anterior es fácil de leer no?, pero se puede simplificar un poco más
// operador ternario
console.log( boolean1  ? 'Si es true' : 'No no es true' )
```

# 7. **Objetos en JavaScript**

## 7.1 Crear Objetos en JavaScript

Los objetos son la pieza principal en JavaScript, en lugar de crear diferentes variables

```jsx
const nombreProducto = "Monitor 20 Pulgadas";
const precio = 30;
const disponible = true;

// Podemos crear un objeto que agrupe toda esta información en una sola variable 

const producto = { // Esto se le conoce como object literal...

}

// Estas llaves despues del signo = representan un objeto

const producto = {
    nombre: // Esto se le llama una propiedad o llave del objeto
}

const producto = {
    nombre: 'Monitor 20 pulgadas' // Nota como en lugar del signo igual se utilizan : , esta sintaxis es propia de los objetos y representa el valor que tendrá la propiedad o la llave del objeto, muchas veces se les dice llave valor
}

// si deseas agregar más propiedades puedes hacerlo de la siguiente forma

const producto = {
    nombre: "Monitor 20 pulgadas", // La coma (,) es importante, sin ella tendriamos un error
    precio: 30,
    disponible: true, // el último elemento puede o no tener la coma(,)
}

console.log(producto);
```

## 7.2 Como Acceder a los valores de un objeto

Veamos como acceder a las propiedades de un objeto:

```jsx
// se puede ver los objetos como multiples variables en una sola
const producto = {
    nombre: "Monitor 20 pulgadas", // La , es importante, sin ella tendriamos un error
    precio: 30,
    disponible: true, // el último elemento puede o no tener la ,
}

console.log(producto);

// Supongamos que deseamos acceder al nombre, en los objetos de javascript existe algo llamado la sintaxis de punto

console.log(producto.nombre);
console.log(producto.precio);
console.log(producto.disponible);

// Otra forma aunque no tan común es:
console.log(producto['nombre']);

```

## 7.3 Agregar o Eliminar Propiedades de un objeto

```jsx
// Añadir propiedades nuevas a un objeto...
// Para añadir nuevas propiedades se utiliza de la misma forma la sintaxis de punto
producto.imagen = "image.jpg";

// Finalmente para eliminar una propiedad se utiliza delete

delete producto.nombre;

console.log(producto);

// Algunas veces deseas asignar el valor de un objeto hacia una variable, veamos como hacerlo en la siguiente seccion
```

## 7.4 Destructuring de Objetos

Destructuring significa, sacar de una estructura, puede ser complejo, no lo es tanto sobretodo cuando lo practicas

```jsx
const producto = {
    nombre: "Monitor 20 pulgadas", // La (,) es importante, sin ella tendriamos un error
    precio: 30,
    disponible: true, // el último elemento puede o no tener la (,)
}

// forma de agregar variables
//const nombre = producto.nombre;
//console.log(nombre);

// Otra forma de hacerlo y que también es nueva,
// es con algo llamado object destructuring...

// Destructuring significa, sacar de una estructura, 
// puede ser complejo, no lo es tanto sobretodo cuando lo practicas

const { nombre } = producto;

// si deseas extraer más variables;
const { precio } = producto;

// se puede simplificar aun mas 
// y extraer todas las variables que necesitemos de un objeto
// ademas de extraer un valor puede crear la variable
// puedes hacerlo de esta manera
const {nombre, precio} = producto;

console.log(nombre)
console.log(precio)

```

## 7.5 Objetos dentro de Objetos

 Un objeto puede contener cualquier tipo de dato dentro de el, incluso puede tener otros objetos: esto se le conoce como `Objetos anidados.`

```jsx
const producto = {
    nombre: "Monitor 20 pulgadas",
    precio: 30,
    disponible: true,
    informacion : {
        peso: '1kg',
        medida: '1m'
    }
}

// Puedes ver que tenemos un objeto dentro de un objeto.
console.log(producto);

// De nueva cuenta para acceder a un objeto, se utiliza la sintaxis de punto

console.log(producto.informacion);
console.log(producto.informacion.peso);
console.log(producto.informacion.medida);
```

## 7.6 Destructuring de Objetos Anidados

Veamos como hacer `destructuring` de un objeto que esta dentro de otro objeto…

```jsx
const producto = {
    nombre: "Monitor 20 pulgadas",
    precio: 30,
    disponible: true,
    informacion : {
        peso: '1kg',
        medida: '1m'
    }
}

//extrae la informacion y crea la variable en un solo paso
//puede ser complejo con la practica quedara mas claro

const { nombre, informacion, informacion: { peso, medida } } = producto;

console.log(nombre)
console.log(informacion)
console.log(peso)
console.log(medida)
```

## 7.7 El Problema con los objetos

Si recuerdas una variable con const una vez que es definida no puede reasignarse su valor. En el caso de los objetos veremos que tienen un comportamiento diferente, ya que sus propiedades si se pueden reescribir. Un objeto de tipo `const` a pesar del tipo de dato constante sus variables si se pueden modificar, o eliminar

```
// Si recuerdas una variable con const una vez que es definida no puede reasginarse su valor.

// const producto = "Monitor";
// producto = 'Tablet';
// console.log(producto);

// En el caso de los objetos veremos que tienen un 
// comportamiento diferente, ya que sus propiedades si se pueden reescribir.
// una objeto de tipo const a pesar del tipo de dato constante
// sus variables si se pueden modificar, o eliminar

const producto = {
    nombre: "Monitor 20 pulgadas",
    precio: 30,
    disponible: true
}

console.log(producto);

producto.disponible = false;

// Puedes ver que lo pudimos modificar, a pesar de ser const,
// veamos como prevenir esto en el próximo video
console.log(producto); 
```

## 7.8 Congelar un Objeto para no poderlo modificar

### Método Freeze

Freeze toma como argumento el objeto no se puede modificar variables existentes de un objeto, tampoco permite agregar nuevas propiedades ni eliminar propiedades

```jsx
// es como decir que evalue el codigo de forma estricta ===, 
// exige que se cumplan ciertas reglas a la hora de escribir codigo de javascript
"use strict"; 

// Como vimos anteriormente los objetos si se pueden modificar
// sus valores, veamos como prevenirlo en caso de que sea algo que 
// desees hacer.

const producto = {
    nombre: "Monitor 20 pulgadas",
    precio: 30,
    disponible: true
}

console.log(producto);

// para hacer que un objeto se comporte realmente como una constante (no eliminar ni modificar)
// Para ello utilizaremos un Object Method o Métodos de objetos.

// por que se les dice Métodos, eso suena como algo de programación orientada a objetos

// Pero veamos como prevenir que un objeto sea modificado, para ello utilizaremos 
// freeze, y funciona de la siguiente forma:

Object.freeze( producto ); // Freeze toma como argumento el objeto
// no se puede modificar variables existentes de un objeto
// producto.disponible = false;

// Freeze tampoco permite agregar nuevas propiedades
// producto.imagen = "imagen.jpg";

// Tampoco se pueden eliminar propiedades
// delete producto.nombre;

// Finalmente si quieres revisar si un objeto esta congelado puedes usar
console.log(Object.isFrozen(producto) ); // devuelve true o false
console.log(producto);
```

## 7.9 Sellar un Objeto

### Método SEAL

Similar a `Freeze` que congela un objeto (no puedes modificar, eliminar ni agregar otras propiedades a un objeto), existe otro object method llamado `Seal`.

A diferencia de `Freeze` no se pueden agregar ni eliminar propiedades pero si se pueden modificar las existentes.

```jsx
"use strict";

const producto = {
    nombre: "Monitor 20 pulgadas",
    precio: 30,
    disponible: true
}

Object.seal(producto);

// con seal Se pueden reasignar/ modificar las llaves existentes de un objeto
producto.nombre = 'Tablet';

// Pero no te permine eliminar
// delete producto.precio;

// Tampoco se pueden añadir nuevas proiedades
// producto.imagen = "imagen.jpg";

// Verificar si un objeto esta sellado y devuelve true o false
console.log(Object.isSealed(producto))

console.log(producto);
```

## 7.10 Copiar 2 objetos

Veamos como `unir 2 objetos`, esto llega a ser muy común ya que algunas veces en una base de datos obtienes el ID del cliente y también tienes los clientes que pertenecen a ese ID y te gustaría unirlos

### Método Assign

Una forma de unir los objetos es con el object method llamado assign

### Spread Operator o Rest Operator

Otra forma de hacerlo que se considera más moderna es con El Spread Operator o Rest Operator

```jsx
// creamos nuestro primer objeto
const producto = {
    nombre: "Monitor 20 pulgadas",
    precio: 30,
    disponible: true
}

// creamos segundo objeto
const medidas = {
    peso: '1 kg',
    medida: '1 metro'
}

// Una forma de unir los objetos es con el object method llamado assign
// unimos los dos objetos y asigamos a uno nuevo llamado "resultado"
const resultado = Object.assign(producto, medidas);
console.log(resultado);

// Otra forma de hacerlo que se considera más moderna es con
// El Spread Operator o Rest Operator
// es mas utilizado esta forma
const resultado2 = { ...producto, ...medidas };
console.log(resultado2);
```

## 7.11 Funciones en Objetos y acceder a sus valores

Estaremos viendo la palabra reservada `this`... `This` se refiere al valor que existe en el mismo `objeto` o `context` que se esta ejecutando en ese momento.

busca la propiedad que necesitamos dentro del mismo objeto y no fuera de el.

```jsx
// Aún no hemos visto las funciones, pero lo haremos en los próximos capitulos...
const nombre='Mouse';
const precio=10

const producto = {
    nombre: "Monitor 20 pulgadas",
    precio: 30,
    disponible: true,
		mostrarInfo: function() {
        return `El Producto: ${nombre}  tiene un precio de ${precio}`;
    }
    mostrarInfo2: function() {
        return `El Producto: ${this.nombre}  tiene un precio de ${this.precio}`;
    }
}

console.log(producto.mostrarInfo() );
console.log(producto.mostrarInfo2() );
```

## 7.12 El Object Constructor vs Object Literal

Crear objetos de la forma `Object Constructor`, estuvimos utilizando anteriormente `Object Literal`, es decir:

```jsx
// definir el objeto con mi codigo 
const producto = {
    nombre: "Monitor 20 pulgadas",
    precio: 30,
    disponible: true
}
		
```

podemos automatizarlo aun mas, cuando van a ser por ejemplo múltiples objetos

```jsx
// Object literal
const producto = {
    nombre: "Monitor 20 pulgadas",
    precio: 30,
    disponible: true
}

// object Constructor
// es un poco mas dinamico que el object literal
function Producto (nombre, precio){
	this.nombre = nombre;
	this.precio = precio;
	this.disponible = true;
}

const producto2 = new Producto('Monitor',500);
console.log(producto2);

// se va manteniendo los valores de referencia por que tenemos
// la palabra reservada this en nuestro object constructor
const producto3 = new Producto('Teclado',100);
console.log(producto32);

```

## 7.13 Object .keys, .values y .entries

Estaremos viendo tres métodos para objetos `Object.keys` y `object.values` y `entries`, estos son más conocidos como `iteradores de objetos`, 

```jsx
const producto = {
    nombre: "Monitor 20 pulgadas",
    precio: 30,
    disponible: true
}

// Object.keys
// nos devolverá un arreglo con los keys del objeto
// para saber si el objeto tiene o no tiene informacion, propiedades, llaves
console.log(Object.keys(producto));

// Object.values
// nos devolverá un arreglo con los valores del objeto
console.log(Object.values(producto)); 

// Object.entries 
// nos va a retornar una matriz de llaves y valores
// nos retorna todo la informacion pero en "pares"
console.log(Object.entries(producto)); 
```

Y con eso tenemos un buen conocimiento de `Objectos` en JavaScript, los estaremos retomando más adelante pero primero hay que conocer otros conceptos como `Arreglos` y `Funciones` para poderle sacar más provecho.

# 8. **Arrays o Arreglos en JavaScript**

## 8.1 Crear Arrays en JavaScript

Los arreglos agrupan elementos del mismo tipo, y se cuentan desde la posición 0,1,2... se crean con corchetes y solamente tienen valores a diferencia de los objetos que poseen `llave y valor`

Al igual que los objetos los arreglos forman una parte muy importante en cualquier lenguaje de programación 

Un ejemplo de un arreglo es un carrito de compras, sirve para agrupar elementos del mismo tipo. 

<aside>
🧑🏻‍💻 También la forma en que facebook muestra un listado de amigos o personas que le dieron Me Gusta a tu última foto, seguramente es un arreglo.

</aside>

Veamos primero como crear un Arreglo...

```jsx
const numeros = [10,20,30,40,50];
console.log(numeros);

// En JavaScript cuando veas esos corchetes son buen indicativo de que 
// esto es un arreglo, a diferencia de los objetos,que su sintaxis son llaves {}
```

El arreglo anterior fue de números, también puedes crear uno de Strings, por ejemplo y se puede crear utilizando la palabra new

```jsx
const meses = new Array('Enero', 'Febrero', 'Marzo', 'Abril', 'Mayo', 'Junio');
console.log(meses);
```

Ahora no es obligatorio que el arreglo tenga números o strings unicamente, también puede tener un poco de todo:

```jsx
const deTodo = ["Hola", 10, true, "si", null, { nombre: 'Juan', trabajo: 'Programador'}, [1,2,3,4]];
console.log(deTodo);
```

incluso un array o arreglo puede tener un array dentro, 

Personalmente encuentro más fácil de utilizar la sintaxis de `corchetes[]` en vez de `New Array()`, así que esa sera la que estaremos utilizando, pero recuerda, un arreglo es una forma de agrupar grandes cantidades de información en una sola variable.

## 8.2 Acceder a los valores de un Array

Veamos como acceder a los elementos de un arreglo:

```jsx
const numeros = [10,20,30,40,50,[1,2,3]];

// otra forma de ver en la consola, a traves de tablas. 
console.table(numeros);
```

 La forma en la que accedes a un arreglo es por lo que se conoce como el indice en el arreglo, los arreglos inician en 0 usualmente aunque hay lenguajes donde inician en 1.

```jsx
console.log(numeros[0]);
console.log(numeros[1]);
console.log(numeros[3]);
console.log(numeros[20]);
console.log(numeros[5][1]); // acceder en el sub indice de un arreglo dentro de otro arreglo
```

## 8.3 Recorrer un Array

Veamos algunas operaciones útiles en los arreglos,

Si quieres saber cuantos elementos hay un arreglo o cuanto mide un arreglo puedes utilizar la propiedad .`lenght` cuenta la cantidad de elementos desde el 1,2,3...

```jsx
const meses = ['Enero', 'Febrero', 'Marzo', 'Abril', 'Mayo', 'Junio'];

console.log(meses.length);
```

Ahora, si recuerdas ya vimos como acceder a un arreglo, pero si este arreglo tuviera 40 elementos sería muy complicado ir 1 por 1, si tienes un carrito de compras y agregas o quitas elementos del carrito, ese arreglo crece de forma dinámica, entonces, como acceder a todos los elementos? con algo llamado un `iterador`, y en javascript hay varios, veamos el `for` que existe en diferentes lenguajes.

```jsx
for (let i = 0; i < meses.length; i++) {
    console.log(meses[i]);
}
```

### 8.4 Agregar nuevos valores a un array

Manipular un arreglo sin tener que tocar el arreglo directamente.

Al Igual que los objetos un arreglo se puede modificar a pesar de que estén declarados con la palabra `const`

```jsx
const meses = ['Enero', 'Febrero', 'Marzo', 'Abril', 'Mayo', 'Junio'];

// podemos modificar el valor de un arreglo, a traves de su posicion
meses[0] = 'Nuevo Mes'

// También se puede añadir un elemento al final de un arreglo, 
// desventaja tienen que conocer las pociciones que tiene un arreglo
// creando la posicion y valor/elemento
meses[6] = 'Ultimo Mes'

console.log(meses);
```

Al igual que los objetos en los arrays existen métodos que son bastante útiles, así que veamos algunos ejemplos mas adelante.

## 8.5 Añadir nuevos elementos al fin o Inicio de un array

Supongamos que creamos un carrito de compras desde la consola

```jsx
// creamos un arreglo (carrito) vacio
const carrito = [];

// Añadir un elemento al carrito...
// definimos los elementos para nuestro arreglo o "productos del carrito"
const producto = {
    nombre: 'Monitor 20 Pulgadas', 
    precio: 500
}

const producto2 = {
    nombre: 'Celular', 
    precio: 500
}
```

### Push

Con .`push` no tengo que conocer la posición del arreglo y lo va a agregar siempre al final de mi arreglo

```jsx
carrito.push(producto);
carrito.push(producto2);

// Añadir al Inicio del carrito...
const producto3 =  { 
    nombre: 'Teclado', 
    precio: 50
}
```

### Unshift

.`unshift` agrega el elemento en la posición 0 de un arreglo

```jsx
codecarrito.unshift(producto3);
console.log(carrito);
```

 Existen otras formas más modernas de hacerlo... pero esta sintaxis aún se utiliza mucho

## 8.6 Crear un nuevo arreglo con el spread operator

Veamos como añadir un elemento a un arreglo utilizando el `Spread Operato`r o `Rest Operator`... sin utilizar el `push` o `unshitf`

### Formas declarativas o imperativas

Ambas formas de funciones son muy utilizadas en JavaScript, 

`forma imperativa:` modifica la variable original .`push`, .`unshift`,  trabaja sobre ella la variable misma, sobre la ella misma la reescribe y modifica los datos.

`forma declarativas`: es un paradigma que expresa la lógica sin describir tanto el flujo de control.

```jsx
const carrito = [];

// Añadir un elemento al carrito...
const producto = {
    nombre: 'Monitor 20 Pulgadas', 
    precio: 500
}

const producto2 = {
    nombre: 'Celular', 
    precio: 500
}
const producto3 =  { 
    nombre: 'Teclado', 
    precio: 50
}
```

Para añadir producto al arreglo utilizando `spread operator` simplemente agregamos...

```jsx
let resultado = [...carrito, producto];
 resultado = [...resultado, producto2];

// Para añadir al inicio...
resultado = [producto3, ...resultado];

console.log(resultado);
```

Esta forma se conoce más como `Declarativa` mientras que la sección anterior es más `imperativa`, ambas son muy utilizadas en programación JavaScript.

> La forma imperativa modifica el objeto, variable actual la forma declarativa no.
> 

## 8.7 Eliminar elementos con Splice

```jsx
const carrito = [];

const producto = {
    nombre: 'Monitor 20 Pulgadas', 
    precio: 500
}

const producto2 = {
    nombre: 'Celular', 
    precio: 500
}

// .push agregamos elementos al final del arreglo
carrito.push(producto);
carrito.push(producto2);

const producto3 =  { 
    nombre: 'Teclado', 
    precio: 50
}

// .unshift agregamos elementos al inicio del arreglo
carrito.unshift(producto3);
```

Veamos como Eliminar elementos de un arreglo.

Con un objeto solo se utiliza `delete`, los arreglos también son sencillos de manipular

```jsx
// Eliminar el primer elemento de un arreglo...
carrito.shift();

// Eliminar el ultimo elemento de un arreglo...
carrito.pop();
```

### Splice

Ahora supongamos que deseas eliminar del centro... 

el primer parámetro es la posiciona de donde empezar a cortar. El segundo parámetro es que tantos elementos vamos a borrar, 0 significa nada, entonces seria igual a no tener nada ( si no le pasas un valor va a borrar todos a partir de ahi en adelante.)

```jsx
carrito.splice(1,0); 

//esto elimina el primer elemento
carrito.splice(0, 1);

console.log(carrito);
```

## 8.8 Destructuring de Arrays

`Array Destructuring` - Al igual que los objetos algunas veces quieres crear la variable y el valor del arreglo, veamos algunos ejemplos:

tenemos una estructura en un objeto y extraemos el valor, “sacamos de su estructura”

con el `Destructuring` queremos crear la variable y extraer el valor todo en un mismo paso

```jsx
const numeros = [10,20,30,40,50];

// accedo al valor entre [] y creo la variable
const [primero, segundo, tercero ] = numeros;

// si solo queremos extraer un valor en una posicion determinada
// Si quieres saltarte un valor, pon una coma....
const [ , ,tercero ] = numeros;

console.log(numeros);
console.log(primero);
console.log(segundo);
console.log(tercero);

// ahora, como extraes todos los otros valores, digamos que solo quieres crear
// la primer variable, mantener el arreglo original..
const [primero, ...tercero ] = numeros;
console.log(tercero);

```

## 8.9 `.forEach` para iterar un array

De aquí en adelante estaremos viendo una serie de métodos de arreglos

```jsx
const carrito = [
    { nombre: 'Monitor 20 Pulgadas', precio: 500},
    { nombre: 'Televisión 50 Pulgadas', precio: 700},
    { nombre: 'Tablet ', precio: 300},
    { nombre: 'Audifonos', precio: 200},
    { nombre: 'Teclado', precio: 50},
    { nombre: 'Celular', precio: 500},
]

// Recorrer un arreglo de la forma tradicional y mostrar su contenido...
for(let i = 0; i < carrito.length; i++ ){
    console.log( `Articulo: ${ carrito[i].nombre } Precio: $ ${carrito[i].precio} ` )
}

// ForEach
// el iterador se llamara producto
carrito.forEach( function(producto) {
    console.log( `Articulo: ${ producto.nombre } Precio: $ producto.precio} ` )
})
```

## 8.10 `.map` para iterar un array, y sus diferencias con `forEach`

Muy similar al `forEach` existe un array metod llamado `map`, la diferencia es que map te crea un array nuevo...

```jsx
const carrito = [
    { nombre: 'Monitor 20 Pulgadas', precio: 500},
    { nombre: 'Televisión 50 Pulgadas', precio: 700},
    { nombre: 'Tablet ', precio: 300},
    { nombre: 'Audifonos', precio: 200},
    { nombre: 'Teclado', precio: 50},
    { nombre: 'Celular', precio: 500},
]

// .map va a crear un arreglo nuevo, va a llenar una variable con un arreglo nuevo
const nuevoArray = carrito.map( function(producto) {
   return  `Articulo: ${ producto.nombre } Precio: $ producto.precio} `;
})

const nuevoArray2 = carrito.forEach( function(producto) {
    return  `Articulo: ${ producto.nombre } Precio: $ producto.precio} `;
 })

console.log(nuevoArray); // un arreglo nuevo
console.log(nuevoArray2); // undefined
```
# 9. **Funciones en JavaScript**

## 9.1 Crear Funciones en JavaScript

### Function expression y Function Declaration

Las funciones en cualquier lenguaje son una serie de procedimientos o instrucciones, que realizan una acción, una ventaja de las funciones es que permiten tener un código más `ordenado` y fácil de `mantener`.

Otra ventaja de las funciones es que son `reutilizables`, puedes tener una función que valide un formulario y utilizarla en todos tus formularios, puedes tener también una función que envié datos al servidor y reutilizarla múltiples veces.

Existen 2 formas de crear funciones en JavaScript:

### Declaración de Función (Function Declaration)

Lla expresión de la función utiliza la palabra reservada function, seguida de un nombre y un paréntesis, en este paréntesis se colocan los argumentos, finalmente el cuerpo de la función se define por unas llaves.

```jsx
// definimos la funcion
function sumar() {
    console.log(2 + 2);
}

// Las funciones deben llamarse, de otra forma en realidad no hacen mucho:
sumar(); // se manda llamar por su nombre seguido del parentesis()
```

### Expresión de función (Function Expression)

Este tipo de funciones se asigna como si fuera una variable

```jsx
// creamos function expression
const sumar2 = function() {
    console.log(3 + 3);
}

sumar2(); // se manda llamar de la misma forma
```

Existe una 3ra forma de crear funciones, que más bien son métodos, la veremos un poco más adelante...

## 9.2 La Diferencia entre Function expression y Declaration

Ademas de las muy notables diferencias en sintaxis, quiero mostrarte las diferencias entre ambas. Si llamamos la función antes de declararla, el `function expression` va a funcionar bien, mientras que `function Declaration` nos va a marcar un error. Eso pasa porque JavaScript se ejecuta digamos en 2 vueltas, a eso se le conoce como Hoisting

> `Hoisting:`
> 
> - Primera vuelta etapa de creación: la primer vuelta registra todas las funciones y determina las variables, esta etapa se le llama de creación.
> - Segunda vuelta etapa de ejecución: la segunda pasada es la que ejecuta tu código, se llama de ejecución.

```jsx
//function declaration
sumar();
function sumar() {
    console.log(2 + 2);
}

//function expression
sumar2();
const sumar2 = function() {
    console.log(3 + 3);
}
```

Por lo tanto el primer código (sumar) funciona porque function se registra primero y después se ejecuta el código.

La segunda función (sumar2) no funciona porque si bien es una función no es declarada como tal, lo ve más bien como una variable.

Esto se le conoce como `hosting` que básicamente son esas 2 etapas (creación y ejecución)

 básicamente tu código se ejecuta asi:

```jsx
const sumar2;
sumar2(); // a estas alturas es undefined...
sumar2 = function() {
    console.log(3 + 3); // pero como ya habiamos llamado la función, se queda como undefined
}

// Y esta es pregunta para obtener un trabajo como JS Developer...
```

## 9.3 Algunas funciones nativas en JavaScript

Funciones del Lenguaje JavaScript cuenta con más de `4 mil funciones listas` para ser usadas.
Java, python, PHP todos incluyen miles de funciones, estas funciones se les conoce como la `libreria estandard`.

En JavaScript no hay librería estandard, pero si hay funciones que son parte digamos del Core...

```jsx
alert('Hubo un error...'); // ya declarado en window 

prompt('Cual es tu edad?');

console.log(parseInt('1'));

// Son ejemplos de funciones. puedes ver que cuentan con un nombre y son llamadas con un parentesis...
```

## 9.4 La Diferencia entre Función y Método

Es un termino que se da de acuerdo al lugar de donde han sido llamada, o en el contexto que son utilizadas. 

Aunque en realidad terminan siendo prácticamente lo mismo, la forma en que se utilizan tiene que ver más que nada en el contexto que son utilizadas.

```jsx
// Veamos la diferencia entre un método y una función...
const numero1 = 20;
const numero2 = "20";

console.log( parseInt(numero2) ); // Esto es una función

console.log( numero1.toString()); // Esto es un método
```

Puedes ver que mientras la función toma el valor en el paréntesis, el método añade un punto luego del nombre de variable, y seguido el nombre del método, esa seria la diferencia.

Ahora ese valor que se pasa en el paréntesis, se llaman argumentos de la función, veamos como crear funciones que toman argumentos y parámetros.

## 9.5 Parámetros y Argumentos en Funciones

Funciones que toman parámetros y argumentos.

```jsx
function sumar(){
	console.log(2+2);
}
sumar();
```

Nuestra primera función no tiene nada de emocionante, es demasiado simple, para que tus funciones puedan ser más versátiles e inteligentes deberán utilizar parámetros y argumentos

```jsx
// nombre y apellido son parametros, son valores que se le pueden pasar a la función... Los valores digamos no son reales, pues son variables...
function saludar(nombre, apellido) { 
    console.log( `Hola ${nombre}  ${apellido} ` );
}
saludar('Juan', 'De la torre'); // Pablo y De la torre son argumentos, son los valores reales...

// podemos llamar la funcion sin pasar valor
// Puedes ver que en la consola aparecerá undefined
saludar(); // Hola undefined undefind
```

## 9.6 Parámetros por default

Algunas veces mandaras llamar una función que no tendrá los argumentos que se requieren, por ejemplo cuando llenas tu perfil de facebook tal vez no llenas todos los campos,  en esos casos son muy convenientes por parámetros por default, veamos nuestra función si solo le pasamos el nombre pero no el apellido:

```jsx
// dentro de nuestra funcion podemos declarar valores por defecto a los parametros
// nombre y apellido son parametros, son valores que se le pueden pasar a la función.
// Los valores digamos no son reales, pues son variables...
function saludar(nombre = 'Desconocido', apellido = '') { 
    console.log( `Hola ${nombre}  ${apellido} ` );
}

saludar('Juan', 'De la torre'); // Pablo y De la torre son argumentos, son los valores reales...

saludar('Juan'); // Hola Juan

// si no esta presente el argunmento tomara los valores del parametro por default
saludar(); // Hola Desconocido
```

## 9.7 Como se Comunican las funciones

Como se comunican las funciones entre si...

Tus funciones se van a comunicar, en lugar de tener una gran función con 800 lineas es recomendable dividirla en pequeñas partes, realizan una operación y se van hacia la otra función para que se comuniquen unas con otras...

```jsx
//funcion que inicia todo y luego se van encadenando las funciones
iniciarApp();

function iniciarApp() {
    console.log('Iniciando App...');
    segundaFuncion();
}

function segundaFuncion() {
    console.log('Desde la segunda función...')
    usuarioAutenticado('Pablo');
}

function usuarioAutenticado(usuario) {
    console.log('Autenticando usuario...');
    console.log(`Usuario autenticado con éxito ${usuario} `)
}
```

## 9.8 Ejemplo con múltiples funciones que se pasan valores

Funciones que retornan valores.
Actualmente hemos tenido funciones que envían datos a la consola, ya cuando veamos la parte del `DOM` algunas funciones van a validar formularios y seguramente ejecutaran todo el código ahí, pero también tendremos funciones que retornan valores para pasarlos hacia otras funciones o hacer algo más.

```jsx
function sumar(a, b) {
    return a + b;
}

// si tenemos un valor retornado debemos de asignar en una nueva variable ese valor retornado
const resultado = sumar(1,2);
console.log(resultado); // 3

// Ejemplo más avanzado....
let total = 0;
function agregarCarrito(precio) {
    return total += precio;
}

function calcularImpuesto(total) {
    return 1.15 * total;
}

total = agregarCarrito(200);
total = agregarCarrito(300);
total = agregarCarrito(400);
console.log(total);

const totalPagar = calcularImpuesto(total);

console.log(`El total a pagar es de ${totalPagar}`);
```

## 9.9 Añadir Funciones en un Objeto

Veremos lo que son los métodos de propiedad, es decir son funciones con una sintaxis similar a las de un método. También llegan a ser muy comunes sobre todo porque es un objeto grande con todas las funciones...

```jsx
const reproductor = {
		// cuando una llave tiene una funcion (pueden tener parametros/argumentos) como valor
		// este se le conoce como metodo de propiedad
    reproducir: function(id) {
        console.log(`Reproduciendo canción id ${id}`);
    },
    pausar: function() {
        console.log('pausando...');
    },
    borrar: function(id) {
        console.log(`Borrando canción con id: ${id}`)
    },
    crearPlaylist: function(nombre) {
        console.log(`Creando la Playlist ${nombre}`);
    },
    reproducirPlaylist: function(nombre) {
        console.log(`Reproduciendo la Playlist ${nombre}`)
    }
}
reproductor.reproducir(30);
reproductor.pausar();

// Tambien los métodos pueden crearse por fuera del objeto
//reproductor.borrar = function(id) {
//		console.log(`Borrando canción con id: ${id}`)r
//}

reproductor.borrar(20);
reproductor.crearPlaylist('Heavy Metal');
reproductor.reproducirPlaylist('Heavy Metal');

```

un proyecto grande los métodos de propiedad pueden ser muy útiles por que todo va a estar en objetos, y podemos acceder a la ventana global en la consola para poder estudiar el objeto y podemos acceder a el fácilmente.

## 9.10 Arrow Functions (funciones de flechas)

Los `arrow functions` son otra forma de declarar funciones y fueron agregadas en las últimas versiones, la sintaxis es más corta al inicio pueden parecer algo complejas, veremos todo lo que tienes que saber de `arrow functions`.

Su sintaxis es mas corta que las funciones tradicionales

```jsx
// funcion tradicional 
const aprendiendo = function() {
    console.log('Aprendiendo JavaScript');
}

//aplicando a la funcion arrow function
const aprendiendo = () =>  {
    console.log('Aprendiendo JavaScript');
}

// funcion con una sola linea no requiere llaves{} (opcionales) y da por implicito un retorno de valor "return"
const aprendiendo = () => console.log('Aprendiendo JavaScript');

// retornar un valor
const aprendiendo = () => 'Aprendiendo JavaScript';

console.log(aprendiendo());
```

## 9.11 Las Ventajas de los Arrow Functions

Parámetros en un arrow Function...

```jsx
// pasando Parametros
const aprendiendo = (tecnologia) => console.log(`aprendiendo ${tecnologia}`);
aprendiendo('JavaScript');

// si es un solo parmetro no ocupamos el parentesis (opcional)
const aprendiendo = tecnologia => console.log(`aprendiendo ${tecnologia}`);
aprendiendo('JavaScript');

// multiples parametros (dos o mas) si requieren parentesis
const aprendiendo = (tecn1, tecn2) => console.log(`Aprendiendo ${tecn1} ${tecn2}`);

aprendiendo('JS', 'ES');
```

## 9.12 Arrow Functions en un `forEach` y un `map`

`ForEach` y `Map` con `arrow functions.`..

```jsx
const carrito = [
    { nombre: 'Monitor 20 Pulgadas', precio: 500},
    { nombre: 'Televisión 50 Pulgadas', precio: 700},
    { nombre: 'Tablet ', precio: 300},
    { nombre: 'Audifonos', precio: 200},
    { nombre: 'Teclado', precio: 50},
    { nombre: 'Celular', precio: 500},
]

// sintaxis .map sin arrow function
const nuevoArray = carrito.map( function(producto) {
   return  `Articulo: ${ producto.nombre } Precio: $ producto.precio} `;
})

// sintaxis .map con arrow function
const nuevoArray = carrito.map(  producto => `Articulo: ${ producto.nombre } Precio: $ producto.precio} `)

// sintaxis .foreach sin arrow function
const nuevoArray2 = carrito.forEach( function(producto) {
    return  `Articulo: ${ producto.nombre } Precio: $ producto.precio} `;
 })

// sintaxis .foreach con arrow function
const nuevoArray2 = carrito.forEach( producto => console.log( `Articulo: ${ producto.nombre } Precio: $ producto.precio} `));

console.log(nuevoArray);
console.log(nuevoArray2);
```

Los `arrow functions` si no se coloca el `return` y queda en una sola linea dan por implícito el `return`

## 9.13 Arrow Functions en el Reproductor de Música

Arrow functions en métodos de propiedad

```jsx
//objeto sin funciones arrow function
const reproductor = {
    reproducir: function(id) {
        console.log(`Reproduciendo canción id ${id}`);
    },
    pausar: function() {
        console.log('pausando...');
    },
    borrar: function(id) {
        console.log(`Borrando canción con id: ${id}`)
    },
    crearPlaylist: function(nombre) {
        console.log(`Creando la Playlist ${nombre}`);
    },
    reproducirPlaylist: function(nombre) {
        console.log(`Reproduciendo la Playlist ${nombre}`)
    }
}

// objeto con funciones arrow function
const reproductor = {
    cancion: '',
    reproducir: id => console.log(`Reproduciendo canción id ${id}`),
    pausar: () => console.log('pausando...'),
    borrar: id => console.log(`Borrando canción con id: ${id}`),
    crearPlaylist: nombre =>  console.log(`Creando la Playlist ${nombre}`),
    reproducirPlaylist: nombre =>  console.log(`Reproduciendo la Playlist ${nombre}`),

    // También existen los Set y Get si tienes experiencia con esos términos, 
		// y si no, set es para añadir un valor, get es para obtenerlo...

    set nuevaCancion(cancion) {
        this.cancion = cancion;
        console.log(`Añadiendo ${cancion}`)
    },
    get obtenerCancion() {
        console.log(`${this.cancion}`)
    }
}
reproductor.reproducir(30);
reproductor.pausar();
reproductor.borrar(20);
reproductor.crearPlaylist('Heavy Metal');
reproductor.reproducirPlaylist('Heavy Metal');

// Probando set y get se utiliza de la siguiente forma
// anadiendo un nuevo valor con set
reproductor.nuevaCancion = 'Enter Sandman';
// como utiliza un get no es necesario el parentesis ().
reproductor.obtenerCancion;
```

> 💡 Las funciones que toman como parámetros otra función son funciones de alto nivel por ejemplo `filter()`

# 10. **Estructuras de Control**

## 10.2 Creando un If

De momento todo nuestro código se ejecuta de arriba hacia abajo salvo cuando llamamos una función. Algunas veces vas a desear que tu código se ejecute basado en una condición.

por ejemplo cuando vas a un cajero, lo primero que haces es insertar tu tarjeta, segundo colocas tu número, si el número esta bien, puedes continuar, sino, te dice que hubo un error, después eliges la operación que deseas hacer, si quieres retirar dinero, el cajero va a revisar que tengas primero esa cantidad, no puedes retirar una cantidad que no tienes.
Lo mismo pasa en programación, si no eres amigo de alguien en facebook, no lo puedes contactar o escribir, dependiendo de la configuración tal vez tampoco puedas darle me gusta  a su foto de perfil... también si no eres usuario de este curso  no podrías verlo salvo que lo hayas descargado de internet.
 Y para ejecutar nuestro código basado en una condición, se utilizan las estructuras de control...

```jsx
// Operador if
const puntaje = '1000';

// es igual

if(puntaje == 1000) { // si la condicion se cumple se ejecuta lo que esta dentro de las llaves
    console.log("Si es igual!");
    //Si esta condición se cumple se ejecutará el código, 
		//pero que pasa si no se cumple???
} else { // si no se cumple, cuando la condicion no se cumpla haria esto, los else son opcionales
    console.log("No no es igual");
}
```

Ahora los `if else` también pueden ir sin llaves, pero esa sintaxis no es muy común en javascript

## 10.2 Comparador Estricto

Veamos otras comparaciones

== (doble es igual) Operador que no es estricto: revisa solo el valor
=== (triple es igual) Operador Estricto: revisa el valor y el tipo de datos

```jsx
// existen muchas comparaciones que podemos realizar
// No es igual
if(puntaje != 1000) { // != diferente == igual a
    console.log("Si! es diferente!");
}  else {
    console.log("No, no es diferente");
}

// comparador estricto de tipo y valor
if(puntaje === 1000) {
    console.log("Si es igual!");
} else {
    console.log("No no es igual");
}

// comparador estricto de tipo y valor
if(puntaje !== 1000) {
    console.log("Si es DIFERENTE (ESTRICTO) !");
} else {
    console.log("No no es igual");
}
```

## 10.3 Comparando Mayor o Menor que

Veamos como utilizar los operadores de mayor que o menor que...

```jsx
// operador mayor que y menor que
let dinero = 500;
let totalCarrito = 300;

if( dinero > totalCarrito ) {
    console.log('Pago Correcto');
} else {
    console.log('Fondos Insuficientes');
}

// También puede ser sin llaves
let dinero = 500;
let totalCarrito = 300;

if( dinero > totalCarrito )
    console.log('Pago Correcto');
else
    console.log('Fondos Insuficientes');
```

## 10.4 Mayor o Igual y else if

```jsx
// Algunas veces vas a desear revisar si se cumple más de una condición...
let rol = 'ADMIN';

if(rol === 'ADMIN') {
    console.log('El Usuario puede editar, eliminar y ver toda la información');
} else if(rol === 'EDITOR' ) {
    console.log('El usuario solo puede editar sus registros');
} else {
    console.log('El Usuario es visitante, solo puede ver la información');
}

// El problema del else if es que si agregas múltiples llegan a ser complejos de leer...

let rol = 'ADMIN';

if(rol === 'ADMIN') {
    console.log('El Usuario puede editar, eliminar y ver toda la información');
} else if(rol === 'EDITOR' ) {
    console.log('El usuario puede editar todos los registros');
} else if(rol === 'AUTOR') { 
    console.log('El usuario solo puede registrar usuarios');
} else {
    console.log('El Usuario es visitante, solo puede ver la información');
}

// Para ello llegan a ser más útiles los Switch, veamos que son y después volvemos hacia más ejemplos de if else
```

## 10.5 Switch para evaluar múltiples Condiciones

Cuando tienes múltiples condiciones por revisar, una forma fácil de leerlo es con un switch...

`Switch case`es un método de verificar múltiples condiciones en caso de que se cumplan y es mas fácil de leer lo hace por medio de `case`, que verifican que si si el case es igual a determinado valor entonces realiza una acción.

```jsx
const metodoPago = 'efectivo';

// dentro de () va a verificar el valor que queremos comprobar
switch(metodoPago) {
    case 'efectivo': // los case son opcionales de colocar
        console.log(`Pagaste con ${metodoPago}`);
// muy importante que una vez haya hecho todo lo que necesitas, debes colocar break.
// de esta forma detenemos la ejecucion del switch
        break;
    case 'cheque':
        console.log(`Pagaste con ${metodoPago} revisaremos que tenga fondos primero`);
        break;
    case 'tarjeta':
        console.log(`Pagaste con ${metodoPago} espere un momento...`);
        break;
    default: // muy similar al else, si ningun condicion/caso se cumple ejecuta el default, y si es obligatorio colocar
        console.log('Aún no has pagado');
        break;
}
```

Los `Switch` también pueden ejecutar funciones, no solamente `console.logs` y también puedes tener 2 condiciones en un mismo if

## 10.6 El Operador && (AND, para revisar que se cumplan 2 o más condiciones)

Veamos que son el `Operador &&` y en el siguiente vemos que es el `OR`
El Operador && Revisa que se `cumplan ambas condiciones` en otras palabras que se cumplan dos condiciones o mas dentro del `IF`...
Cuando vas a comprar en Amazon, `primero` debes tener una cuenta y `segundo` debes tener suficiente saldo, además de que tu producto debe estar disponible...
 Vamos a crear un par de variables:

```jsx
const usuario = false;
const puedePagar = true;

// que se cumpla la condicion 1 y la condicion 2
if (usuario && puedePagar) {
    console.log('Tu Pedido se hizo con éxito...');
} else { // si una de las condiciones no se cumple, entonces toma la accion dentro del else
    console.log('hubo un error con tu pago.')
}

// Cambiar true o false...

// Ahora si quieres darle mensajes de error más detallados a tus usuarios puedes 
// revisar o negar una condición
// el orden de las condiciones termina siendo importante al trabajar con condiciones ELSE IF
if (usuario && puedePagar) {
    console.log('Tu Pedido se hizo con éxito...');
} else if (!usuario) {
    console.log('Inicia sesión para realizar el pedido')
} else if(!puedePagar) {
    console.log('Fondos Insuficientes')
} else {
    console.log('hubo un error con tu pago.')
}
```

Lo importante es que recuerdes que el `operador &&` revisa porque se cumplan ambas condiciones, ahora que pasa cuando solo quieres revisar una, veamos el operador `OR` ...

## 10.7 El Operador || OR (para que se cumpla al menos una condición)

La lección anterior vimos el operador `&&` y vimos que en el se deben `cumplir ambas condiciones`.
El operador `OR` revisa porque se `cumpla al menos una o la otra`, si colocas 2  o 3  condiciones y todas se cumplen se va a ejecutar el código porque revisa que se cumpla al menos 1.

```jsx
let efectivo = 300;
let credito = 400;
let disponible = efectivo + credito;
let totalCarrito = 700;

// || operador OR
if(efectivo > totalCarrito || credito > totalCarrito ) {
    console.log('Puedes pagar con efectivo o credito');
} else if(disponible >= totalCarrito) {
    console.log('Paga con ambos');
} else {
    console.log('No puedes pagar');
}
```

Puedes ver que se cumple una u otra condición, y con eso basta para que el código de la primera condición se cumpla.

## 10.8 Detener la ejecución de un if con una función

Buenas practicas con ifs. Veamos algunas buenas practicas, sencillas para escribir ifs

```jsx
// una muy común es que muchas personas hacen lo siguiente...
const autenticado = true;

// cuando estas evaluando con true no es necesario comparar por ejemplo la variable "autenticado
// por que ya se por echo que sera true
// Debido a que el IF ya retorna true, puedes eliminarlo y tu código será mejor..
if(autenticado === true) {
    console.log('El Usuario esta autenticado')
}

// También muchas personas escriben ifs pensando que se podrán ejecutar 2 condiciones
// al mismo tiempo, el if solo va aejecutar la primera que se cumpla...

const puntaje = 500;

if(puntaje > 300) {
    console.log('Buen puntaje... felicidades');
} else if(puntaje > 400) {
    console.log('Excelente esfuerzo')
} else {
    console.log('No sabria decirte, pero buen esfuerzo...')
}

// puedes ver que ambas condiciones se cumplen, la de 300 y 400, muchas personas 
// creen que se van a ejecutar ambas porque ambas se cumplen pero el if va a ejecutar 
// la que más pronto (en orden este primero) cumpla su condición, también recuerda que el
// orden puede ser importante, lo más seguro es que quieras cambiar el orden del 300 y 400
```

## 10.9 El Operador Ternario

Previamente vimos los operadores ternarios, llegan a ser muy útiles ya que te dan un código más simplificado, veamos como se utilizan.

```jsx
const autenticado = false;
const puedePagar = false

// muy similar al if pero todo en una sola linea
// condicion ? si es verdadero entonces hace esto : si no hace esto
console.log( autenticado  ? 'Si esta autenticado' : 'No esta autenticado');

// El OR y el && también se pueden utilizar en el ternario
console.log( autenticado && puedePagar ? 'Si esta autenticado' : 'No esta autenticado');

// Ternario anidado... (es muy poco comun)
// como si fuera un IF dentro de otro IF
console.log( autenticado  ?  puedePagar ? 'Si puede pagar' : 'esta autenticado pero no puede pgar' : 'No esta autenticado');
```

En el siguiente sección vamos a ver los iteradores, en JavaScript hay varios.

# 11. **Iteradores en JavaScript**

## 11.1 For Loop

Algunas veces vas a desear ejecutar tu código hasta que una condición se cumpla o se deje de cumplir. los `For Loops` tienen esa característica, se ejecutan hasta que el código deja de cumplir esa condición...

```jsx
// For loop consta de tres partes
// 1. Inicializar el for
// 2. condición
// 3. Incremento

for(let i = 0; i <= 10; i += 2) {
    console.log(`Numero:  ${i} `);
}

// Podemos cambiar el <= < o el número hasta unos 20, también iniciarlizar o avanzar con i+= 2

// Podemos llevar este ejemplo más allá una pregunta sencilla para programadores JR
// es como identificas un numero par o impar en un for loop...
for(let i = 0; i <= 10; i++) {
    if(i % 2 == 0) {
        console.log(`Numero ${i} ES PAR `);
    } else {
        console.log(`Numero ${i} ES IMPAR `);
    }
}
    
// Los for son útiles cuando tienes un arreglo, por ejemplo un carrito de compras...
// recuerda que podemos acceder al valor de un arreglo por su indice array[n]
const carrito = [
    { nombre: 'Monitor 20 Pulgadas', precio: 500},
    { nombre: 'Televisión 50 Pulgadas', precio: 700},
    { nombre: 'Tablet ', precio: 300},
    { nombre: 'Audifonos', precio: 200},
    { nombre: 'Teclado', precio: 50},
    { nombre: 'Celular', precio: 500},
]

for(let i = 0; i < carrito.length; i++ ) {
    console.log(carrito[i].nombre);
}

// en este caso nuestro for loop corre hasta que una condición se cumple, ahora como este
// arreglo el usuario se va a encargar de llenarlo, que el carrito tenga elementos, un for
// loop ejecutará el código hasta que lleguemos al final del carrito...
```
## 11.2 break y continue; en un for loop

Veamos lo que es `break` y `continue`, break cortará la ejecución del `for loop`, mientras que `continue` nos permitirá interceptar digamos un elemento y continuar su ejecución.

### uso de `breack`

```jsx
for(let i = 0; i <= 10; i++) {
    if( i === 5) {
        console.log('Estamos en el 5... FIN.');
        break; // rompe un for loops, no se ejecuta nada mas a partir de aqui y termina el for
    }
    console.log(`Numero:  ${i} `);
}

for(let i = 0; i <= 10; i++) {
    if( i === 5) {
        console.log('Estamos en el 5... CONTINUAR....');
        continue;// llega aqui y vuelve al incio del FOR, y no se ejecuta mas esta accion
    }
    console.log(`Numero:  ${i} `);
}
```

### Y en que casos puedes utilizar el `continue`?

```jsx
// informar que un elemento tiene descuento
const carrito = [
    { nombre: 'Monitor 20 Pulgadas', precio: 500},
    { nombre: 'Televisión 50 Pulgadas', precio: 700},
    { nombre: 'Tablet ', precio: 300, descuento: true},
    { nombre: 'Audifonos', precio: 200},
    { nombre: 'Teclado', precio: 50, descuento: true},
    { nombre: 'Celular', precio: 500},
]

for(let i = 0; i <= carrito.length; i++) {
    if(carrito[i].descuento) {
        console.log(`El articulo ${carrito[i].nombre} Tiene descuento... `);
        continue;
    }
    console.log(carrito[i].nombre);
}
```
## 11.3 El Ejercicio Fizz Buzz

El Reto de Fizz BUZZ

Fizz Buzz es un reto que complica mucho a los programadores, básicamente si un número es múltiplo de 3 imprimes FIZ, si es múltiplo de 5 imprimes BUZZ y si es múltiplo de ambos como 15, 30, 45 debes imprimir FIZZ BUZZ.

```jsx
// 3 6 9 12 15 ...  FIZZ
// 5 10 15 20 25 ... BUZZ
// 15 30 45 ... Fizz Buzz

for(let i = 1; i < 100; i++  ) {
    if(i % 15 === 0) {
        console.log(`${i} FIZZ BUZZ`)
    } else if(i % 3 === 0) {
        console.log(`${i} fizz`);
    } else if ( i % 5 === 0 ) {
        console.log(`${i} buzz`)
    } 
}
```

## 11.4 While Loop

Otro iterador muy común es el `while loop`, este se ejecuta mientras una condición sea verdadera.

 Tambien consta de 3 partes, pero no se declaran en el mismo lugar así como el FOR LOOPS

```jsx
let i = 0; // Inicializar el while
while (i < 10) { // condicion va en ()
    // Bloque de código que se ejecuta si cumple la condicion osea la condicion es true...
    console.log(`Numero: ${i}`);
        i++; // incremento
}

// El while se ejecuta mientras una condición sea verdadera, por lo tanto si inicicializamos
// en 20 u otro numero, no hará nada, ya que la condicion nos dara FALSE.
```

Intenta realizar los mismos ejemplos  Detectar pares y nones y el fizz buzz con el 
while

```jsx
// numeros pares
let i=20;
while (i<20){
	if (i % 2 == 0){
		console.log(`${i} es Numero par`);
	}	else {
		console.log(`${i} es Numero impar`);
	}
	i++;
}

//fiz buzz
let i=20;
while (i<20) {
	if (i % 15 == 0 ) {
		console.log(`${i} fiz buz!`);
	} else if ( i% 3 == 0){
		console.log(`${i} fiz`);	
	} else if ( i% 5 == 0){
		console.log(`${i} buz`);	
	}
	i++;
}
```

## 11.5 Do While Loop

Veamos otro iterador que es muy común en otros lenguajes y también en javascript, es el `do while`. A diferencia del `for` y del `while`, el `do while` se ejecuta al menos una vez, y después verifica si la condición se cumple.

```jsx
// Do While va a correr al menos una vez.
let i = 0; // inicio 

do {// este codigo se va a ejecutar al menos una vez y continua mientras se cumpla la condicion
    console.log(`Numero: ${i}`)
    i++;// incremento
} while( i < 10 ); //condicion que se debe cumplir para seguir ejecutando

// Ahora, lo que hace diferente a un while de un for o un do while, es que al menos se va
// a ejecutar una vez aunque la condición no se cumpla...

// cambiamos el i a 100 y revisamos...
```

## 11.6 `.forEach` y `.map`

Bueno veamos otros iteradores que existen en JavaScript, previamente ya habíamos visto `forEach` y `Map`,  veamos sus diferencias.

### Recorrer por un Foreach

```jsx
let pendientes = ['Tarea', 'Comer', 'Proyecto', 'Estudiar JavaScript'];
// ideal para recorrer arreglos va a ejectarse al menos una vez por cada vez que alla elementos 
pendientes.forEach( (pendiente, index) =>  {
    console.log(`${index} : ${pendiente}`);
}); // 0 : Tarea ... 1 : comer ...

// Recuerda que como es una sola linea, la llave es opcional...
// y si le pasamos un solo parametro el parentesis tambien es opcional ()
pendientes.forEach( pendientes => console.log (pendiente)); // Tarea... Comer .. Proyecto...
```

### Recorrer con un MAP

```jsx
// Recorrer arreglo de objetos
const carrito = [
    {id: 1, nombreProducto: 'Libro' },
    {id: 2, nombreProducto: 'Camisa'},
    {id: 3, nombreProducto: 'Disco'}
];

// iteramos sobre cada elemento del arreglo con objeto
carrito.forEach( producto =>  {
    console.log(`Agregaste ${producto.nombreProducto}`);
});

// Lo mismo aplica para los maps, la sintaxis es la misma, solo recuerda, el map te crea
// un nuevo arreglo, si solo deseas recorrer los elementos utiliza el Foreach, si requieres
// crear un nuevo arreglo, sin duda el map sera mejor...

const nuevoArreglo = carrito.forEach( producto => producto.nombreProducto); 

const nuevoArreglo2 = carrito.map( producto => producto.nombreProducto);

console.log(nuevoArreglo); // nos devuelve undefined

console.log(nuevoArreglo2); // nos devuelve un nuevo arreglo con elementos, por que .map crea un nuevo arreglo
```

## 11.7 for ....of

`For of` no es como un `for` tradicional que ejecuta una pieza de código mientras una condición sea verdadera, este ejecuta `mientras haya elementos` por iterar como puede ser un arreglo y otros llamados `Maps` y `Sets` que veremos más adelante.

```jsx
let pendientes = ['Tarea', 'Comer', 'Proyecto', 'Estudiar JavaScript'];

// primero damos el nombre del iterador como querramos
// segundo le indicamos donde vamos a recorrer mientras haya elementos
for (let pendiente of pendientes) {
    console.log(pendiente);
}

// Sin duda una forma más sencilla que un foreach y un for
```

## 11.8 for ...in

el `for in` va a iterar sobre todas las propiedades de un objeto, pero primero veamos como recorrer un arreglo con objetos.

```jsx
const carrito = [
    {id: 1, producto: 'Libro' },
    {id: 2, producto: 'Camisa'},
    {id: 3, producto: 'Disco'}
];

// FOR..OF nos permite iterar sobre un ARREGLO
for (let producto of carrito) {
    console.log(producto.producto);
}

let automovil = {
    modelo: 'Camaro',
    motor: '6.0',
    anio: '1969',
    marca: 'Chevrolet'
}

// FOR..IN nos permite interar sobre OBJETOS
for(let auto in automovil) {
    console.log(`${auto} : ${automovil[auto]}`);
}

// si queremos iterar un OBJETO con FOR..OF
// debemos usar Object.entries
for (let [llave, valor] of Object.entries(automovil){
	console.log(valor);
	console.log(llave);
}
```

Y con eso terminamos lo que son los `iteradores`, veamos una serie de `Array Methods`, que son similares a estos iteradores y sus usos. ya vamos terminando toda la parte de básicos de JavaScript para movernos al `DOM` pero vamos viendo una sección más!

# 12. **Array Methods**

## 12.1 `.some` y `.includes`

Previamente vimos algunos métodos para strings, para números y también para objetos.

Veamos una serie de métodos muy útiles cuando se trabaja con arrays y algunos casos de uso

### Arreglo tradicional o de indices

```jsx
//arreglo tradicional o de indices
const meses = ['Enero', 'Febrero', 'Marzo', 'Abril', 'Mayo', 'Junio'];

// Si te gustaría saber si nuestro arreglo de meses, tiene el mes de Febrero, podrías
// hacerlo con un foreach...

meses.forEach(mes => {
    if(mes === 'Enero') {
        console.log('Enero si existe...')
    }
})

// O también podrías utilizar el Array Method de .includes
```

### Array Method `.includes`

.includes revise si un valor existe dentro de un arreglo, solo soporta/sirve para arreglos tradicionales o de indices

```jsx
//arreglo tradicional o de indices
const meses = ['Enero', 'Febrero', 'Marzo', 'Abril', 'Mayo', 'Junio'];

const resultado = meses.includes('Enero'); // si existe enero asignara a la variable resultado
console.log(resultado); // devuelve un true o false
```

### Arreglo de Objetos

```jsx
// arreglo de objeto
const carrito = [
    { nombre: 'Monitor 20 Pulgadas', precio: 500},
    { nombre: 'Televisión 50 Pulgadas', precio: 700},
    { nombre: 'Tablet', precio: 300},
    { nombre: 'Audifonos', precio: 200},
    { nombre: 'Teclado', precio: 50},
    { nombre: 'Celular', precio: 500},
    { nombre: 'Bocinas', precio: 300},
    { nombre: 'Laptop', precio: 800},
];
```

### Array Method `.SOME`

En el caso de un arreglo de objetos, `.includes` no es la mejor opción, podrías utilizar uno llamado `.some` .

El array method `Some` revisa que al menos un elemento cumpla la condición (es como la versión del OR)

```jsx
// arreglo de objeto
const carrito = [
    { nombre: 'Monitor 20 Pulgadas', precio: 500},
    { nombre: 'Televisión 50 Pulgadas', precio: 700},
    { nombre: 'Tablet', precio: 300},
    { nombre: 'Audifonos', precio: 200},
    { nombre: 'Teclado', precio: 50},
    { nombre: 'Celular', precio: 500},
    { nombre: 'Bocinas', precio: 300},
    { nombre: 'Laptop', precio: 800},
];

const existe = carrito.some( producto => producto.nombre === 'Celular' );
console.log(existe);// devuelve un buleano true or false

// Some en un arreglo tradicional o de indices...

//arreglo tradicional o de indices
const meses = ['Enero', 'Febrero', 'Marzo', 'Abril', 'Mayo', 'Junio'];

const existe2 = meses.some( mes => mes === 'Febrero' );
console.log(existe2);// devuelve un buleano
```

## 12.2 `.findIndex` para encontrar la posición en un array

El Segundo Array Method que quiero mostrarte es `findIndex`. Este método nos devuelve el indice de elemento que estemos buscando y asigna el valor del indice a una nueva variable.

```jsx
const meses = ['Enero', 'Febrero', 'Marzo', 'Abril', 'Mayo', 'Junio'];

const carrito = [
    { producto: 'Monitor 20 Pulgadas', precio: 500},
    { producto: 'Televisión 50 Pulgadas', precio: 700},
    { producto: 'Tablet', precio: 300},
    { producto: 'Audifonos', precio: 200},
    { producto: 'Teclado', precio: 50},
    { producto: 'Celular', precio: 500},
    { producto: 'Bocinas', precio: 300},
    { producto: 'Laptop', precio: 800},
];

// Primero veamos como seria el ejemplo con un forEach...
meses.forEach( (mes, index) => {
    if(mes === 'Abril') { // Si ponemos diciembre no lo va a encontrar...
        console.log(`Encontrado en el indice ${index}`);
    }
});

// FindIndex te dirá el indice es decir la ubicación del elemento en el arreglo...
// asigna el valor del indice a una nueva variable
const indice = meses.findIndex( mes => mes === 'Abril' ); 
// si cambiamos a 'Diciembre', osea un valor que no existe en nuestro arreglo
// tendremos -1 eso quiere decir que no lo encontró
console.log(indice); // 3
```

## 12.3 Array Method `.reduce`

El método `.reduce`es una función reductora. Básicamente lo que hace es tomar una gran cantidad de datos unirlos y entregar un resultado..

```jsx
// Supongamos que tenemos nuestro carrito de compras y queremos decirle al usuario
// cuanto es el total a pagar...
const carrito = [
    { producto: 'Monitor 20 Pulgadas', precio: 500},
    { producto: 'Televisión 50 Pulgadas', precio: 700},
    { producto: 'Tablet', precio: 300},
    { producto: 'Audifonos', precio: 200},
    { producto: 'Teclado', precio: 50},
    { producto: 'Celular', precio: 500},
    { producto: 'Bocinas', precio: 300},
    { producto: 'Laptop', precio: 800},
];

// Con un foreach lo podrías hacer asi...
let total = 0;
carrito.forEach( producto => total += producto.precio );
console.log(total);

// Puedes ver que si bien no se ve mal, podemos tenerlo todo en una sola linea con un .reduce
// el primer parametro es el valor inicial, valor previo, valor total
// el segundo parametero que se le pasa el valor actual
let resultado = carrito.reduce((total, producto) => total + producto.precio, 0); //0 es el inicio
console.log( resultado );
```

## 12.4 Array Method `.filter`

El método `Filter` va a crearte un nuevo arreglo basado en un parámetro que es evaluado.

```jsx
const carrito = [
    { nombre: 'Monitor 20 Pulgadas', precio: 500},
    { nombre: 'Televisión 50 Pulgadas', precio: 700},
    { nombre: 'Tablet', precio: 300},
    { nombre: 'Audifonos', precio: 200},
    { nombre: 'Teclado', precio: 50},
    { nombre: 'Celular', precio: 500},
    { nombre: 'Bocinas', precio: 300},
    { nombre: 'Laptop', precio: 800},
];

let resultado = carrito.filter( producto => producto.precio > 400 ); // Todos los mayores a 400 - añadir  && producto.precio < 600
let resultado2 = carrito.filter( producto => producto.nombre === 'Celular'  ); // Traerte el celular
let resultado3 = carrito.filter(producto => producto.nombre !== 'Laptop'); // Todos menos la laptop

console.log(resultado);
console.log(resultado2);
console.log(resultado3);

// Filter es en mi opinión el más util y el más utilizado que reduce!
```

## 12.5 Array Method `.find`

El método `FIND` te creará un arreglo nuevo en base al primer resultado que sea true.

```jsx
const carrito = [
    { nombre: 'Monitor 20 Pulgadas', precio: 500},
    { nombre: 'Televisión 50 Pulgadas', precio: 700},
    { nombre: 'Tablet', precio: 300},
    { nombre: 'Audifonos', precio: 200},
    { nombre: 'Teclado', precio: 50},
    { nombre: 'Celular', precio: 500},
    { nombre: 'Bocinas', precio: 300},
    { nombre: 'Laptop', precio: 800},
];

// con un foreach seria algo asi...
// queremos obtener los valores (el objeto) de la pocision en que se encuentro el producto 'Bocinas'
// y lo guardamos en una variable resultado, recuerda el metodo .forEach no crea nuevos arreglos
let resultado = '';
carrito.forEach((producto, index) => {
    if(producto.nombre === 'Bocinas') {
        resultado = carrito[index]
    }
});
console.log(resultado);// { nombre: 'Bocinas', precio: 300}

// con .find seria
// importante, .find solo te va a retornar el primer elemento que cumpla su condicion
// si no cumple la condicion nos devuelve undefined
const resultado2 = carrito.find( producto => producto.nombre === 'Bocinas');
console.log(resultado2);
```

## 12.6 Array Method `.every`

Every es raro, ya que todos los elementos del arreglo deberán cumplir una condición para que nos retorne un TRUE.

```jsx
const carrito = [
    { nombre: 'Monitor 20 Pulgadas', precio: 500},
    { nombre: 'Televisión 50 Pulgadas', precio: 700},
    { nombre: 'Tablet', precio: 300},
    { nombre: 'Audifonos', precio: 200},
    { nombre: 'Teclado', precio: 50},
    { nombre: 'Celular', precio: 500},
    { nombre: 'Bocinas', precio: 300},
    { nombre: 'Laptop', precio: 800},
];

// con un foreach seria algo asi.
let cumple = true;
carrito.forEach( producto => {
    if(producto.precio > 700) {
        cumple = false;
        return
    }
})
console.log(cumple);

// con .every todos los elementos deben de cumplir una condicion
//seria como la version del AND
// Mil se cumple, 700 no...
const resultado = carrito.every(producto => producto.precio < 1000);
console.log(resultado); //devuelve un boleano

```

## 12.7 Array Method `.concat`

Veremos como unir 2 arreglos, para ello existe un array method llamado `.concat`

```jsx
const meses = ['Enero', 'Febrero', 'Marzo', 'Abril', 'Mayo', 'Junio'];
const meses2 = ['Julio', 'Agosto', 'Septiembre', 'Octubre'];
const meses3 = ['Noviembre', 'Diciembre'];

// Unir arreglos con concat...
// puedes concatener todos los arreglos que quieras .concat()
const mesesTotales = meses.concat(meses2,meses3, 'otros mes');
console.log(mesesTotales);

```

### rest operator o spread operator

Existe otra forma... que es con rest operator o spread operator

```jsx
const meses = ['Enero', 'Febrero', 'Marzo', 'Abril', 'Mayo', 'Junio'];
const meses2 = ['Julio', 'Agosto', 'Septiembre', 'Octubre'];
const meses3 = ['Noviembre', 'Diciembre'];

// la sintaxis "...arreglo"(tres puntos de seguido y el arreglo) : quiere decir que copia ese arreglo
// Tienes que asegurarte de que sean arrays cuando usas ... spread operator, convierte el texto en arreglo
const meses4 = [...meses,...meses2,'ano',...'dia' ]; 
console.log(meses4)
```

## 12.8 Array Method `Spread Operator`

Un poco más sobre el rest operator. El `rest operator` es muy útil para crear un nuevo arreglo sin modificar el original como si haría push y eso es muy útil en un tipo de programación llamada funcional (evita modificar los datos originales).

```jsx
const meses = ['Enero', 'Febrero', 'Marzo', 'Abril', 'Mayo', 'Junio'];

const carrito = [
    { producto: 'Monitor 20 Pulgadas', precio: 500},
    { producto: 'Televisión 50 Pulgadas', precio: 700},
    { producto: 'Tablet', precio: 300},
    { producto: 'Audifonos', precio: 200},
    { producto: 'Teclado', precio: 50},
    { producto: 'Celular', precio: 500},
    { producto: 'Bocinas', precio: 300},
    { producto: 'Laptop', precio: 800},
];

// Si tienes 2 arreglos los unes como vimos en la seccion anterior, pero digamos que tienes
// un arreglo y quieres añadir un elemento al final que es un string utilizarias...
const meses2 = [...meses, 'Julio'];
console.log(meses);

// Recuerda esto no modifica el arreglo original como si haria push y eso es muy útil
// en un tipo de programación llamada funcional (evita modificar los datos originales)
console.log(meses2); 

// si queremos mover un string al inicio... en lugar de utilizar .unshift, 
const meses3 = ['Julio',...meses ]; 

// tal vez quieres añadir un objeto a un arreglo de objetos al final
const producto = {producto: 'Disco Duro', precio: 300};
const carrito2 = [...carrito, producto];
console.log(carrito2);

// o si queremos agregar el objeto al inicio
const carrito3 = [producto, ...carrito];
console.log(carrito3);
```
