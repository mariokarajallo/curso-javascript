# Sección 6: **Booleans en JavaScript**

## 6.1 Crear y Comparar Booleans

El tipo de dato boolean solo puede tener 2 valores, true o false:

- esta prendido o apagado
- si o no

```jsx
const boolean1 = true;
const boolean2 = false;

console.log(boolean1);
console.log(boolean2);

// que tipo de datos es
console.log(typeof boolean2);

//También un Boolean se puede crear con la palabra new

const boolean3 = new Boolean(true);
console.log(boolean3);

// podemos ver que es una variable de tipo objeto
// no una variable primitiva
console.log(typeof boolean3);
```

## 6.2 Más sobre Comparar Booleans

Comparar booleans es exactamente igual que cualquier comparación de números o strings

```jsx
const boolean1 = true;
const boolean2 = false;

// comparar 2 variables
console.log(boolean1 === boolean2); //false

console.log(boolean1 === true); // comparar si un boolean es verdadero //true
console.log(boolean2 === true);// comparar si un boolean es verdadero // false

// Aún no hemos llegado a ello, pero muchas personas cometen el
// siguiente error cuando escriben código javascript en un if

if(boolean1 === true) {
    console.log('si es true')
} else {
    console.log('no, no es true')
}

// Pero este código se puede simplificar quitando
// el === true porque ya sabemos que la variable es true

// Este mismo ejemplo aplica si un usuario esta autenticado puede
// darle me gusta a una foto o ver una página, así como si ya tienes
// una cuenta en netflix y has pagado
```

## 6.3 Buenas practicas a la hora de evaluar un Boolean

Existe otra forma de comparar si un valor es verdadero y es por medio de algo llamado un operador ternario

```jsx
const boolean1 = true;
const boolean2 = false;

if(boolean1) {
    console.log('si es true')
} else {
    console.log('no, no es true')
}

//El código anterior es fácil de leer no?, pero se puede simplificar un poco más
// operador ternario
console.log( boolean1  ? 'Si es true' : 'No no es true' )
```
