# Sección 9: **Funciones en JavaScript**

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

