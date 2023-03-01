# Sección 4: **Números en JavaScripts**

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
