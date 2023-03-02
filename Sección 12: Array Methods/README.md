# Sección 12: **Array Methods**

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
