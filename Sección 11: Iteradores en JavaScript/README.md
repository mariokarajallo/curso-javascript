# Sección 11. **Iteradores en JavaScript**

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

