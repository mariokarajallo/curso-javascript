# Sección 19: **Sets Maps y Symbols**

## 19.1 Sets y sus Características

Un `set` te permite crear una lista de valores sin duplicados.

Aún no es tan utilizado, muchas personas prefieren crear arreglos, iterar sobre el arreglo y si algún elemento ya existen en el arreglo no lo agregan y evitar duplicados, pero sería más sencillo con un set, de hecho en algunas ocasiones termina siendo mejor opción que un arreglo o un objeto. Un set cuando maneja mucho volumen de datos tiende a ser más rápido que un objeto o un arreglo.

Algunos métodos que existe en los `arreglos` se pueden utilizar en los `sets`, pero no todos. Sets tiene sus propios métodos.

```jsx
// Creando un Set
let carrito = new Set();
carrito.add('Camisa');
carrito.add('Disco #1');
carrito.add('Disco #2');
carrito.add('Disco #3');
carrito.add('Disco #3');

// Convertir un set a un arreglo...
const arregloCarrito = [...carrito];
console.log(arregloCarrito);

// Dispone de sus propios metodos -> set methods, veamoslo.
```

### Set method ADD()

Nos permite agregar elementos a un, set. los `sets` solo son valores, no como un objeto que contiene “llave:valor”.

Para evitar duplicados en los sets, si agregas nuevamente `el mismo valor por sintaxis,` en realidad no va a agregarlo un nuevo elemento a los sets y recuerda  también que son `case sensitive`

```jsx
let carrito = new Set();
carrito.add('Camisa');
carrito.add('Camisa');// no agregara por que ya existe 
carrito.add('CAMISA');// si agregara por que es diferente a los elementos anteriores,  esta en mayusculas

```

### Set method Size()

Nos permite saber el tamaño de un set, equivalente a `lenght` en un arreglo

```jsx
let carrito = new Set();
carrito.add('Disco #1');
carrito.add('Disco #2');
carrito.add('Disco #3');

console.log(carrito.size); // .size -> mos permite saber el tamano de un set, equivalente a .lenght en un arreglo

// En un arreglo
let numeros = new Set([1,2,3,4,5,6,7,3,3,3,3]);
console.log(numeros.size); // .size -> mos permite saber el tamano de un setSet method Has()
```

Comprobando si un valor existe en el set. retorna true o false

```jsx
let carrito = new Set();
carrito.add('Camisa');

console.log( carrito.has('Camisa') ); // true
```

### Set method Delete()

Elimina un elemento del set, si le pasamos un valor que no existe te devuelve un false.

```jsx
let carrito = new Set();
carrito.add('Camisa');

console.log( carrito.delete('Camisa') ); // true
console.log( carrito.delete('Disco') ); // false

// del siguiente arreglo eliminar los duplicados
const numeros = [10,20,30,40,50,10,20]

const noDuplicados = new Set(numeros);
console.log(noDuplicados); // eliminara de una forma sencilla los duplicados de un arreglo

```

### Set method Clear()

Limpia o elimina todos los elementos de un set

```jsx
let carrito = new Set();
carrito.add('Disco #1');
carrito.add('Disco #2');
carrito.add('Disco #3');

carrito.clear(); // vacia el set
console.log(carrito); // imprime un set vacio
```

### Set method ForEach()

Los sets son iterables, podemos acceder a cada elemento de un set con `ForEach`

- Sintaxis de `Foreach` a un set ((elementoActual, indice, set_al_que_pertenece))

Los `sets` solo almacenan valores (no llave y valor como un objeto), asi que en un `forEach` dentro de un set en nuestro segundo parámetro (indice) será lo mismo que el primer parámetro (elementoActual)

```jsx
let carrito = new Set();
carrito.add('Camisa');
carrito.add('Disco #1');
carrito.add('Disco #2');
carrito.add('Disco #3');
carrito.add('Disco #3');

carrito.forEach((producto, index, pertenece) =>  {
    console.log(index); // imprime el elemento del set
		console.log(producto); // al igual que index, imprime el elemento del set, un set no tiene llave:valor, solo el valor
    console.log(pertenece  === carrito); // nombre de la variable -> true
})
```

## 19.2 Qué es un WeakSet y en que se diferencia de un Set

A diferencia del `set` en el set le puedes pasar cualquier valor: objetos, números, boléanos, etc. En el `weakset` solamente le puedes pasar o agregar objetos.

No tienen la propiedad o método size no podremos conocer la extensión del `weakset` asi como si lo tiene `set`, aunque si tienen length. Tampoco son iterables, no podemos usar foreach como hicimos con los `sets`  ni tienen keys, values entries etc.

```jsx
// Weakset se escribe de esta manera
// creamos un set debil
var ws = new WeakSet();

// como solo podemos agregar objetos, declaramos un objeto.
const cliente = {
    nombre: 'mario',
    saldo: 3000
}
```

### Weakset method add()

con el método add podemos agregar valores a nuestros `weakset`, pero solo podemos agregar objetos, cualquier otro tipo de valor nos daría error.

```jsx
var weakset = new WeakSet();

// como solo podemos agregar objetos, declaramos un objeto.
const cliente = {
    nombre: 'mario',
    saldo: 3000
}

const nombre = 'Pedro';

weakset.add(cliente) // no agregar el objeto en el weakset
console.log(weakset) // comprobamos en consola nuestro weakset

weakset.add(nombre) // nos dara error por que queremos agregar un valor tipo string que no es valido para los weakset

```

### Weakset method has()

con este método podemos saber si existe o no un valor dentro de nuestro `weakset`

```jsx
var weakset = new WeakSet();

const cliente = {
    nombre: 'mario',
    saldo: 3000
}

const nombre = 'Pedro';

console.log( weakset.has(cliente) ); // devolvera true
console.log( weakset.has(cliente2));  // como no existe devolvera undefined
console.log( weakset.has(nombre));  // devolvera false, por que no existe un valor string en weaksets
```

### Weakset method delete()

podemos eliminar un valor que se encuentra dentro de nuestro `weakset`

```jsx
var weakset = new WeakSet();

const cliente = {
    nombre: 'mario',
    saldo: 3000
}

const nombre = 'Pedro';

weakset.delete(cliente); // elimina el objeto cliente dentro del wakset
console.log( weakset.delete(cliente2)); // devolvera un falso, por que no existe ese valor en nuestro weakset

```
