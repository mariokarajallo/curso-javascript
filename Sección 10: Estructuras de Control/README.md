# Sección 10: **Estructuras de Control**


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

