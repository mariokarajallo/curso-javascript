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

