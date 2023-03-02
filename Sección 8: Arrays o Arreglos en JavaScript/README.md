# Sección 8: **Arrays o Arreglos en JavaScript**

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
