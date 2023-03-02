# Sección 7: **Objetos en JavaScript**

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
