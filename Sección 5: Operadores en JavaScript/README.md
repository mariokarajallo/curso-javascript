# Sección 5: **Operadores en JavaScript**

## 5.1 Operador Mayor que y Menor Que

Previamente ya vimos que existen operadores de suma, resta, multiplicación, pero existen unos muy útiles de comparación

Devuelven como resultado valores `Booleans`. Verdadero, Falso.

```jsx
const numero1 = 20;
const numero2 = "20";
const numero3 = 30;

// Operador Mayor a 
console.log( numero1 > numero3 );
console.log( numero3 > numero1 );

// Operador Menor que
console.log(numero3 < numero1);
```

## 5.2 Comparar 2 valores

Operadores que sirven para revisar si son iguales

```jsx
const numero1 = 20;
const numero2 = "20";
const numero3 = 30;

// Revisar si 2 valores son iguales o diferentes
// no es un comparador muy estricto, solo se fija en el valor
console.log(numero1 == numero3); //false
console.log(numero1 == numero2); //true

// Typeof
// devuelve el tipo de valor
console.log( typeof numero1 );
console.log( typeof numero2 );

// Operador estricto (revisa valor y tipo de dato)
// se fija en el valor y en el tipo de dato
console.log(numero1 === numero2 ); //false
// podemos convertir un tipo de variable y comparar
console.log(numero1 === parseInt(numero2)) //true

// Diferente a !=
// no importa si es mayor o menor, o igual compara si son diferentes
console.log(numero1 != numero3);
console.log(numero1 != numero2);//false
console.log(numero1 !== numero2);// true
console.log(numero1 !== parseInt(numero2));// false
```

## 5.3 Comprar Null y undefined en JavaScript

### Null y Undefined

En javascript existen diferentes tipos de datos primitivos a los que hemos visto, además de `string` y `number` se tienen `booleans` que son `true o false`,  y existen un par más llamados `undefined` y `null`

```jsx
// veamos un ejemplo de undefined.
let numero;

//La variable esta definida pero su valor no, por lo tanto es undefined.../
console.log(numero); // undefined
console.log(typeof numero) //

// En el caso de null es más bien asignarlo
let numero2 = null;
console.log(numero2);
// ahora esto nos dirá que es un objeto, la especificación de ecma que es quien define el standard del lenguaje dice que null debe ser un objeto
console.log(typeof numero2); 

// Comparando null y undefined - Comparar un valor null y un undefined 
// puede ser de las cosas más complicadas
console.log (numero == numero2); //true

// Puedes ver que el resultado es true, a pesar de que numero 
// no tiene un valor, eso usualmente nos lleva a ejecución de código no deseada o con comportamientos extraños ya que comparamos 
// un valor que no existe, y nos retorna true

// para ello llega a ser muy  util el comparador estricto
console.log(numero === numero2); //false

// De esta forma no comparamos un falso positivo y evitamos errores.
```
