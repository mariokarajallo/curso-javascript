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

## 19.3 Que son los Maps

son listas ordenadas en llave - valor, (algo así como un objeto, pero un objeto con una sola propiedad) donde la llave y el valor pueden ser cualquier tipo de dato, a diferencia de un objeto puede tener la llave de cualquier tipo de dato.

Y en cuanto a performance los maps tienen mejor performance que los objetos, son especialmente diseñados para agregar o quitar elementos así como recorrer, también cuando son muy grandes tienen mejor performance que un objeto

```jsx
// MAPS se crean al igual que los sets
let cliente = new Map();
```

### Map Method set()

para agregar un elemento en los Maps se utiliza set

```jsx
let cliente = new Map();

// guardamos en nuestro map su valores "llave:valor"
// pueden tener cualquier tipo de datos como llave y como valor
cliente.set('nombre', 'mario');
cliente.set('tipo', 'Premium');
cliente.set('saldo', 3000);
cliente.set(true, true);
cliente.set([0], true);

console.log(cliente); // imprime nuestro maps con sus valores

// También se puede inicializar un map con diferentes valores...
const paciente = new Map([['nombre', 'juan'], ['cuarto', 'no definido']]);
console.log(paciente) // el valor de nombre ahora es juan, cuarto -> no definido

// pdemos reemplazar un valor existente
paciente.set('nombre', 'Antonio');
paciente.set('cuarto', 400);

console.log(paciente); // el valor de nombre ahora sera antonio, cuarto -> 400

```

### Map Method get()

nos ayuda a obtener los valores que existen de un map

```jsx
let cliente = new Map();

cliente.set('nombre', 'mario');
cliente.set('tipo', 'Premium');
cliente.set('saldo', 3000);

// acceder a los valores
console.log(cliente.get('nombre')); // mario
console.log(cliente.get('tipo')); // Premium
console.log(cliente.get('saldo')); // saldo
```

### Map Method size()

podemos obtener la extensión de nuestro Map, en otras palabras cuantos elementos hay nuestro map

```jsx
let cliente = new Map();

cliente.set('nombre', 'mario');
cliente.set('tipo', 'Premium');
cliente.set('saldo', 3000);

// Tamaño del MAP
console.log(cliente.size); // 3
```

### Map Method has()

comprueba si un valor existe dentro de nuestro map

```jsx
let cliente = new Map();

cliente.set('nombre', 'mario');
cliente.set('tipo', 'Premium');
cliente.set('saldo', 3000);

// Contiene un valor
console.log(cliente.has('tipo')); //true
console.log(cliente.has('nombre')); //true
console.log(cliente.has('nombre2')); //false
```

### Map Method delete()

elimina los elementos de un map

```jsx
let cliente = new Map();

cliente.set('nombre', 'mario');
cliente.set('tipo', 'Premium');
cliente.set('saldo', 3000);

// Borrar
cliente.delete('nombre');

console.log(cliente.has('nombre')); //false
console.log(cliente.get('nombre')); //undefined
```

### Map Method clear()

limpia o elimina todos los elementos de un map

```jsx
let cliente = new Map();

cliente.set('nombre', 'mario');
cliente.set('tipo', 'Premium');
cliente.set('saldo', 3000);

// Borrar el map
cliente.clear();

console.log(cliente);
```

### Map Method forEach()

los maps también son iterables, y podemos acceder a cada elemento

```jsx
let cliente = new Map();

cliente.set('nombre', 'mario');
cliente.set('tipo', 'Premium');
cliente.set('saldo', 3000);

// Foreach a un map

cliente.forEach((datos, index) => {
    // console.log(datos);
    console.log(`${index}:${datos}`); // nombre:mario tipo:premium saldo:3000
});
```

## 19.4 Que son los WeakMaps

Son similares a los `MAPs` y al igual que los `weakset` tienen ciertas diferencias con su par `sets`, `weakmaps` tiene cierta diferencia con su par `map`. Son los menos utilizados, quizás se utilizan en algunas librerías.

Sirve para mantener una serie de datos en privado, utiliza como elemento “llave:valor” y no se pueden iterar ni usar el método Foreach(), ni conocer su extensión con el método size().

Recuerda los `weakset` o `weakmap`,  solamente aceptan objetos, no aceptan un Sting, número, booleano etc.

```jsx
// Weakmap
const producto = {
	idProducto = 10
}

//instanciamos
const weakmap = new WeakMap();

//agregan elementos en nuestro weakmap
weakmap.set(producto,"Monitor");

//comprobar si existe un objeto dentro de nuestro weakmap
weakmap.has(producto); //true

// extraer elemento del weakmap
weakmap.get(producto); //Monitor

// eliminar elementos o vaciar nuestro weakmap
weakmap.delete(producto); // true

weakmap.get(key); //undefined

// no podemos conocer la extension de un weakmap
weakmap.size; //undefined
```

## 19.5 Symbols y sus Características

Los `symbols` se lanzaron en el **ECMAScript** 6, te van a permitir crear una propiedad única, no hay dos `symbol` que sean igual.

No se crea con la palabra reservada `New`. Si declaras `new Symbol` enviará un error.

```jsx
const sym = Symbol('1');
const sym2 = Symbol('1');

// Los symbolos siempre son diferentes

if (sym === sym2){
	console.log("Son iguales"); 
} else {
		console.log("Son diferentes"); 
}
// Son diferentes

console.log( Symbol() === Symbol() ); // false

// creamos dos propiedades
// Llaves de objetos únicas
const nombre = Symbol();
const apellido = Symbol();

// Crear un objeto vacio
const  persona = {}

console.log(persona); // {}

// agregamos las propiedades (nombre, apellido) al objeto (cliente), deben tener corchetes
// agregar nombre y apellido como llaves del objeto 
persona[nombre] = 'Mario';
persona[apellido] = 'Karajallo';

// agregamos mas propiedades a este objeto (cliente) de una forma "nomral"
persona.tipoCliente = 'Premium';
persona.saldo = 500;

// ahora veamos como se compartan las propiedades
console.log(persona);

// si quiero acceder al valor de la propiedad "nombre", debemos de usar corchetes
console.log(persona.nombre); // undefined
console.log(persona[nombre]); // mario

// Las propiedades que esten definidas por medio de un symbol no son iterables
// No se puede acceder al SYMBOL con un for.
for(let i in persona) {
    console.log(`${i} : ${persona[i]}`); // "tipo de cliente : premium", "saldo:500"
}

// También se puede crear UNA DESCRIPCION DEL SYMBOLO
const nombreCliente = Symbol('Nombre del cliente');
const cliente = {};

//agregamos propiedad a nuestro objeto
cliente[nombreCliente] = 'Pedro';

// Probar
console.log(cliente); // Symbol (nombre del cliente): Pedro
console.log(cliente[nombreCliente]); // Pedro
console.log(nombreCliente); // Symbol (Nombre del Cliente)
```

## 19.6 Iteradores en JavaScript

Aprendamos a crear nuestro propio iterador.

```jsx
// Iterators
// la funcion recibira los elementos que queremos iterar
function crearIterador(carrito) {
		//iniciamos a iterar en la pocicion 0
    let i = 0;

    return {
        siguiente: () => {
						//saber cuando llegamos al final de nuestro elemento a iterar
            const fin = (i >= carrito.length);
						// obtener el valor actual de la posicion, si esta en la pocision final devuelve undefined
            const valor = !fin ? carrito[i++] : undefined;

            return {
                fin,
                valor
            };
        }
    };
}

// creamos el arreglo que vamos a iterar
const carrito = ['Producto 1', 'Producto 2', 'Producto 3', 'Producto 4'];

// utilizar el iterador
const recorrerCarrito = crearIterador(carrito);

console.log(recorrerCarrito.siguiente() ); // {fin: false,  valor: Producto 1}
console.log(recorrerCarrito.siguiente() );// {fin: false,  valor: Producto 2}
console.log(recorrerCarrito.siguiente() );// {fin: false,  valor: Producto 3}
console.log(recorrerCarrito.siguiente() );// {fin: false,  valor: Producto 4}
console.log(recorrerCarrito.siguiente() );// {fin: true,  valor: undefined}
```

## 19.7 Generadores en JavaScript

Las funciones regulares devuelven solo un valor único (o nada).

Los generadores pueden producir (“`yield`”) múltiples valores, uno tras otro, a pedido. Son funciones especiales que pueden pausar su ejecución en cualquier momento y luego continuarla desde donde se detuvieron en el punto de pausa. Funcionan muy bien con los iterables, permitiendo crear flujos de datos con facilidad. Es una funcion que retorna un Iterador.

Se indican con un asterisco después de  la palabra function

Para crear un generador, necesitamos una construcción de sintaxis especial: `function*`, la llamada “función generadora”. Que se diferencia de una función normal por el uso de la palabra clave **`function*`**  en lugar de **`function`** . También se utiliza la palabra clave **`yield`** dentro de la función para pausar la ejecución y devolver un valor.

```jsx
function* crearGenerador() {
    // Yiel es nuevo también en es6 y son los valores que podemos utilizar para iterar...
  yield 1;
  yield 2;
	yield 'Nombre';
  yield 3 +3;
  yield true;
  return 3;
}

// Se llaman como funciones normales pero retornan un iteraador
const iterador = crearGenerador();
```

Las funciones generadoras se comportan de manera diferente a las normales. Cuando se llama a dicha función, no ejecuta su código. En su lugar, devuelve un objeto especial, llamado “objeto generador”, para gestionar la ejecución.

El método principal de un generador es `next()`. Cuando se llama, se ejecuta hasta la declaración `yield <value>` más cercana (se puede omitir `value`, entonces será `undefined`). Luego, la ejecución de la función se detiene y el `value` obtenido se devuelve al código externo.

El resultado de `next()` es siempre un objeto con dos propiedades:

- `value`: el valor de yield.
- `done`: `true` si el código de la función ha terminado, de lo contrario `false`.

### Generador Estático

```jsx
function* crearGenerador() {
  yield 1;
  yield 2;
	yield 'Nombre';
  yield 3 +3;
  yield true;
  return 3;
}

// Se llaman como funciones normales pero retornan un iteraador
const iterador = crearGenerador();

console.log(iterador.next().value); // 1
console.log(iterador.next()); // {value: 2, done: false}
console.log(iterador.next().done); // false
console.log(iterador.next());// {value: 6, done: false}
console.log(iterador.next()); // {value: true, done: false}
console.log(iterador.next()); // {value: 3, done: true}

//Las nuevas llamadas a generator.next() ya no tienen sentido. Si las hacemos, devuelven el mismo objeto: {done: true}.
console.log(iterador.next()); // {done: true}
```

### Generador Dinámico

```jsx
// Crear el generador llamada nuevoGenerador que acepta un parámetro carrito.
function* generadorCarrito(carrito) {
		//La función utiliza un bucle for para recorrer los elementos del arreglo carrito
		// y utiliza la palabra clave yield para pausar la ejecución y devolver cada elemento del arreglo uno por uno.
    for( let i = 0; i < carrito.length; i++) {
        yield carrito[i];
    }
}
// se crea un arreglo "carrito" que contiene varios elementos 
const carrito = ['Producto 1', 'Producto 2', 'Producto 3', 'Producto 4'];

// recorrer el iterador
// se llama a la función nuevoGenerador pasando el arreglo como argumento. Esto devuelve un iterador que se almacena en la variable iterador.

let iterador = generadorCarrito(carrito);

// se utilizan varias llamadas al método next() del iterador para recorrer los elementos del arreglo carrito.
// Cada vez que se llama al método next(), el generador se ejecuta hasta la siguiente pausa
// y devuelve un objeto que contiene el valor del elemento actual y un indicador de si el iterador ha llegado al final del arreglo.
console.log(iterador.next() ); // {value: Producto 1, done: false}
console.log(iterador.next() ); // {value: Producto 2, done: false}
console.log(iterador.next() ); // {value: Producto 3, done: false}
console.log(iterador.next() ); // {value: Producto 4, done: true}
console.log(iterador.next() ); // {done: true}
```

## 19.8 Iteradores en JavaScript

Ahora veamos unas series de iteradores que se pueden considerar nuevos en JavaScript, ya estuvimos viendo en secciones anteriores algunos y usualmente con un `for` un `map` estarás bien a la hora de tu carrera como programador, pero hay otros que pueden simplificarte y facilitarte tu código.

Veamos los diferentes métodos compatibles  de como iterar un `arrelgo`, un `set` y un  `map` 

### Enties Iterator

El iterador **`entries()`**  en JavaScript es una función de los objetos **`Array`, `Map`, `Set`**. Y otros tipos de colecciones (objeto que contiene un conjunto de elementos) que devuelve un iterador que produce un arreglo de dos elementos para cada entrada en la colección. Devuelve un array de pares `[propiedad, valor]`

El uso del método **`entries()`**  puede ser útil en situaciones en las que se necesita acceder tanto a las claves como a los valores de una colección (objeto que contiene un conjunto de elementos).

```jsx
const ciudades = ['Londres', 'New York', 'Madrid', 'Paris']; // puede contener todo tipo de elementos separados por comas.
const ordenes = new Set([123, 231, 131, 102]); // set solo recibe valores, no "llave : valor"
const datos = new Map(); // contiene dos entradas "llave:valor" como elementos
datos.set('nombre', 'Mario');
datos.set('profesion', 'Desarrollador Web');

// entries a las ciudades
/*la variable "entry" (iterador) almacena en cada iteración un arreglo de dos elementos, 
donde el primer elemento es el índice del elemento en el arreglo ciudades y el segundo elemento es el valor del elemento.
Por lo tanto, en cada iteración del bucle, el valor de entry es un arreglo con la forma [indice, valor]*/

for( let entry of ciudades.entries() ){
    console.log(entry);
}
// [0, 'Londres'], [1, 'New York'], [2, 'Madrid'], [3, 'Paris']

// entries a las ordenes
/*la variable entry (iterador) almacena en cada iteración un arreglo de dos elementos, donde el primer elemento es el valor 
del elemento en el conjunto ordenes y el segundo elemento es el mismo valor. En un conjunto, la clave es igual al valor. 
Por lo tanto, en cada iteración del bucle, el valor de entry es un arreglo con la forma [valor, valor].*/

for( let entry of ordenes.entries() ){
    console.log(entry);
}
// [123, 123], [231, 231], [131, 131],[102, 102]

// entries a los datos
/*La variable entry almacena en cada iteración un arreglo de dos elementos, donde el primer elemento es la clave de la entrada
en el objeto Map datos y el segundo elemento es el valor correspondiente a esa clave. Por lo tanto, en cada iteración 
del bucle, el valor de entry es un arreglo con la forma [clave, valor].*/

for( let entry of datos.entries() ){
    console.log(entry);
}
// ['nombre', 'Mario'], ['profesion', 'Desarrollador Web']

```

En resumen, el método **`entries()`**  en JavaScript es una función útil para acceder a las claves y valores de una colección de manera controlada y ordenada. Puede ser utilizado con objetos **`Array`,`Map`**,**`Set`** y otros tipos de colecciones.

### Values Iterator

El método **`values()`** devuelve un objeto iterador que produce los valores de cada elemento en una colección, en el mismo orden en que aparecen en la colección. Por lo tanto, un bucle **`for...of`**  que utiliza un iterador **`values()`**  recorre la colección y accede solamente a los valores, no a las claves o índices. Devuelve un array de valores.

```jsx
const ciudades = ['Londres', 'New York', 'Madrid', 'Paris']; // puede contener todo tipo de elementos separados por comas.
const ordenes = new Set([123, 231, 131, 102]); // set solo recibe valores, no "llave : valor"
const datos = new Map(); // contiene dos entradas "llave:valor" como elementos
datos.set('nombre', 'Mario');
datos.set('profesion', 'Desarrollador Web');

// values a arreglo
/*En el caso de un arreglo, el método values() devuelve un iterador que produce los valores de cada elemento en el arreglo.
El iterador values() produce los valores de cada elemento en el arreglo ciudades, por lo que el bucle for...of imprime
en la consola cada valor en el arreglo en el mismo orden en que aparece en el arreglo:
*/

for(let value of ciudades.values()) {
    console.log(value);
}
// Londres, New York, Madrid, Paris

// values de un objeto SET
/*el método values() devuelve un iterador que produce los valores de cada elemento en el conjunto.
El iterador values() produce los valores de cada elemento en el conjunto ordenes, por lo que el bucle for...of imprime
 en la consola cada valor en el conjunto en el mismo orden en que aparece en el conjunto
*/

for( let value of ordenes.values() ){
    console.log(value);
}
//123 //231 //131 //102

// values de un objeo MAP
/*el método values() devuelve un iterador que produce los valores de cada entrada en el objeto Map.
El iterador values() produce los valores de cada entrada en el objeto Map datos, por lo que el bucle for...of imprime 
en la consola cada valor en el objeto en el mismo orden en que aparece en el objeto
*/
for( let value of datos.values() ){
    console.log(value);
}
// Mario //Desarrollador Web

```

### Keys Iterator

El método **`keys()`** devuelve un objeto iterador que produce las claves de cada elemento en una colección(array, set, map), en el mismo orden en que aparecen en la colección.

Por lo tanto, un bucle **`for...of`**  que utiliza un iterador **`keys()`**  recorre la colección y accede solamente a las claves o índices, no a los valores. Devuelve un array de propiedades.

```jsx
const ciudades = ['Londres', 'New York', 'Madrid', 'Paris']; // puede contener todo tipo de elementos separados por comas.
const ordenes = new Set([123, 231, 131, 102]); // set solo recibe valores, no "llave : valor"
const datos = new Map(); // contiene dos entradas "llave:valor" como elementos
datos.set('nombre', 'Mario');
datos.set('profesion', 'Desarrollador Web');

// Keys iterator

// keys a un arreglo
/*En el caso de un arreglo, el método keys() devuelve un iterador que produce los índices de cada elemento en el arreglo.
El iterador keys() produce los índices de cada elemento en el arreglo ciudades, por lo que el bucle for...of imprime 
en la consola cada índice en el arreglo en el mismo orden en que aparece en el arreglo*/
for(let keys of ciudades.keys() ) {
    console.log(keys);
}
//0
//1
//2
//3

// keys a un objeto SET
/* En el caso de un objeto Set, el método keys() devuelve un iterador que produce los valores de cada elemento en el conjunto.
El iterador keys() produce los valores de cada elemento en el conjunto ordenes, por lo que el bucle for...of imprime
 en la consola cada valor en el conjunto en el mismo orden en que aparece en el conjunto.
*/
for( let keys of ordenes.keys()  ){
    console.log(keys);
}
//123
//231
//131
//102

// keyss a un objeto MAP
/*En el caso de un objeto Map, el método keys() devuelve un iterador que produce las claves de cada entrada en el objeto Map.
El iterador keys() produce las claves de cada entrada en el objeto Map datos, por lo que el bucle for...of imprime
en la consola cada clave en el objeto en el mismo orden en que aparece en el objeto*/
for( let keys of datos.keys()  ){
    console.log(keys);
}
//nombre
//profesion

```

### Default iterador

El iterador por defecto en JavaScript se refiere al comportamiento predeterminado que se aplica a un objeto cuando se utiliza en un bucle **`for...of`**
 pero no se especifica ningún método específico.

```jsx

const ciudades = ['Londres', 'New York', 'Madrid', 'Paris']; // puede contener todo tipo de elementos separados por comas.
const ordenes = new Set([123, 231, 131, 102]); // set solo recibe valores, no "llave : valor"
const datos = new Map(); // contiene dos entradas "llave:valor" como elementos
datos.set('nombre', 'Mario');
datos.set('profesion', 'Desarrollador Web');

// Default sobre un arreglo
/*En este caso, el iterador por defecto se aplica automáticamente al arreglo ciudades, y se utiliza el iterador values() 
para iterar sobre los elementos del arreglo.*/
for(let ciudad of ciudades) {
    console.log(ciudad);
}
//'Londres', 'New York', 'Madrid' y 'Paris'.

// Default en un objeto SET
/*En este caso, el iterador por defecto se aplica automáticamente al objeto 'Set' 'ordenes', y se utiliza el iterador 
values() para iterar sobre los elementos del conjunto*/
for( let orden of ordenes){
    console.log(orden);
}
//123, 231, 131 y 102.

// Default sobre un MAP
/*el iterador por defecto se aplica automáticamente al objeto 'Map' 'datos', y se utiliza el iterador entries()
para iterar sobre las entradas del mapa.*/
for( let dato of datos){
    console.log(dato);
}
//'nombre', 'Mario' y 'profesion','Desarrollador Web'.
```

### Iterar sobre String

En forma "vieja", es decir, en versiones antiguas de JavaScript, se puede iterar un `string` utilizando un bucle **`for`** que recorre cada caracter del `string` utilizando el operador de indexación **`[]`**

```jsx
// Iterar en un string

const mensaje = 'Hola mundo';

// Forma vieja
// En este caso, se utiliza el operador de indexación [] para acceder al caracter en la posición i del string mensaje.
for( let i = 0; i < mensaje.length; i++ ) {
    console.log(mensaje[i]);
}
/*H
o
l
a

m
u
n
d
o
*/
```

En la forma "nueva" de iterar un string, introducida en ECMAScript 6, se puede utilizar un bucle **`for...of`**
 para recorrer cada caracter del string de manera más sencilla:

```jsx
const mensaje = 'Hola mundo';

// forma nueva
/*En este caso, el bucle for...of itera sobre cada elemento del string 'mensaje', y en cada iteración asigna el valor de cada caracter a la variable letra. Esto hace que el código sea más claro y fácil de entender.*/
for( let letra of mensaje) {
    console.log(letra);
}

/*H
o
l
a

m
u
n
d
o
*/
```

### Iterar en un NODE LIST

En JavaScript, un NodeList es una colección de nodos que puede ser obtenida de diferentes formas, como por ejemplo a través de métodos como **`querySelectorAll()`** o **`getElementsByTagName()`** del objeto **`document`.** Es una estructura de datos muy utilizada en el ámbito del desarrollo web, ya que es común necesitar iterar sobre una lista de elementos en el DOM para realizar ciertas operaciones.

Para iterar un NodeList, se puede utilizar un bucle **`for...of`** que recorra cada elemento de la lista de forma sencilla y legible. En cada iteración, se puede acceder a las propiedades y métodos del elemento actual para realizar las operaciones necesarias.

```jsx

// Iterar en un NODE LIST
/*
supongamos que queremos obtener la URL de todos los enlaces de una página web y mostrarlas en la consola.
- se utiliza el método getElementsByTagName() del objeto document para obtener una lista de todos los elementos <a> de la página.
- Luego, se utiliza un bucle for...of para recorrer la lista y acceder a la propiedad href de cada elemento, que contiene la URL del enlace.
- Finalmente, se utiliza el método console.log() para mostrar la URL en la consola.
*/

const enlaces = document.getElementsByTagName('a');

for (let enlace of enlaces) {
    console.log(enlace.href);
}
```

La ventaja de utilizar un bucle **`for...of`**  para iterar un NodeList es que se trata de una forma sencilla y legible de recorrer una colección de elementos.