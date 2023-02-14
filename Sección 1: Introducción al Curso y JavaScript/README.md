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

