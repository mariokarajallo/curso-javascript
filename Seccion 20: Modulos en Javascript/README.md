# Sección 20: **Modulos en javascript**

## 20.1 Básicos de los Módulos en ES6

En esta sección veremos como utilizar modulos para exportar/importar variables

### Modulos

un módulo es una unidad de código que se utiliza para encapsular variables, funciones y/o clases relacionadas en un paquete separado y reutilizable. Los módulos pueden ser importados y utilizados en otros programas o módulos para evitar la duplicación de código y mejorar la organización y modularidad del proyecto.

En JavaScript, los módulos son una característica que se introdujo en la especificación ECMAScript 6 (ES6). Los módulos permiten definir un conjunto de variables, funciones y/o clases como un paquete separado y reutilizable que puede ser importado en otros módulos o scripts.

### Las funciones IIFE (Immediately Invoked Function Expression)

son funciones que se invocan inmediatamente después de ser definidas. Esto se logra envolviendo la función en paréntesis y agregando paréntesis adicionales para invocarla, como en el siguiente ejemplo:

```jsx
javascriptCopy code
(function() {
  // código de la función
})();
```

Esto es útil para encapsular variables y evitar que se filtren al ámbito global. También puede ser utilizado para crear módulos y mantener el código organizado y modularizado.

#### index.html

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<!-- codigo -->
</head>
<body>
	<!-- codigo -->    
  <script src="js/cliente.js" type="module"></script>
  <script src="js/app.js" type="module"></script>
</body>
</html>
```

#### app.js

Este código demuestra cómo se pueden utilizar módulos para importar variables desde otros archivos en JavaScript. Los módulos permiten una mejor organización del código y evitan la contaminación del alcance global con variables que podrían ser sobreescritas por otras partes del código.

```jsx
// PROBLEMA VARIABLE GLOBAL
// Queremos utilizar una variable que no esta declarado en nuestro archivo app.js, pero si esta en otro archivo cliente.js
// Esto puede provocar que se mezclen variables con el mismo nombre de otros archivos o librerías, lo que puede causar errores difíciles de rastrear.
//-> console.log(nombreCliente);

// SOLUCION CON IIFE
// se propone utilizar IIFEs (Funciones Autoejecutables) que permiten encapsular el código en un ámbito local y evitar la contaminación del ámbito global.
// Agrupar cada variable o codigo en lo que se conoce como un IIFE (ver el archivo cliente.js) y ejecutar ahi si la variable encapsulada
//-> console.log(window.nombreCliente);

// IMPORTANDO VARIABLES 
// Para leer variables exportadas desde otro archivo utilizamos la sentencia imports.
// En este caso, se importa la variable nombreCliente desde el archivo cliente.js.
import { nombreCliente } from './cliente.js';

console.log(nombreCliente); 

// es importante destacar que para poder utilizar la sentencia import y export
// el archivo debe ser tratado como un módulo, lo que se logra agregando el atributo type="module"
// a la etiqueta <script> que carga el archivo en el HTML.

import { nombreCliente, ahorro }  from './cliente.js';

console.log(nombreCliente); 
console.log(ahorro); 

// no solo es posible importar variables, sino también funciones y clases desde otros módulos.
```

#### cliente.js

Este código muestra cómo se pueden utilizar funciones IIFE (Immediately Invoked Function Expression) y módulos en JavaScript. para exportar variables, funciones y clases a otros archivos.

```jsx
"use strict"; // implica que se aplicarán más restricciones y se evitarán ciertas prácticas de programación consideradas inseguras o propensas a errores.

// VENTANA GLOBAL
// El Problema al definir de esta manera nuestras variables o codigo, se mezclaran con todo le codigo de otros archivos por que son definida de manera alcance global.
//-> const nombreCliente =  'Juan';
//-> let ahorro = 200;

// USO DE IIFE
// una alternativa de solucion para evitar que se mezcle nuestro codigo es crear una funcion IIFE
// que contiene la declaración de dos variables: nombreCliente y ahorro. Estas variables estarán limitadas al alcance (scope) de la función, por lo que no se mezclarán con las variables definidas en otros archivos.
(function() {
    const nombreCliente =  'Juan';
    let ahorro = 200;

    // El problema es que implementar un IIFE, si evita que nuestro código se mezcle con otro, 
		// pero si queremos tener un código más ordenado y separar en distintos archivos sería imposible hacerlo
		// ya que si se desea dividir el código en distintos archivos, no se podrá acceder a estas variables desde otros archivos. 
		//Para solucionar esto, se podría utilizar la notación
    //-> window.nombreCliente =  'Juan';
		// pero esta no es la forma más organizada y mantenible de hacerlo. En su lugar, se recomienda utilizar módulos.
})();

// IMPLEMENTAR MODULOS
// Importar y exportar multiples valores
// En este caso, se utiliza la palabra clave export para hacer que las variables nombreCliente y ahorro estén disponibles para ser importadas en otros módulos.

export const nombreCliente =  'Juan'; // los exports solo funcionan en modules...
export const ahorro = 200

// Estos exports solo funcionarán en módulos, por lo que es necesario declarar el archivo principal con la propiedad type="module" en la etiqueta <script> correspondiente en el archivo HTML (index.html).
```

### EXPORT DEFAULT vs EXPORT

La forma en que se importan variables, funciones y clases desde un módulo externo en JavaScript depende de cómo se exportaron en el módulo de origen.

Hay dos formas comunes de exportar desde un módulo en JavaScript: 

- la primera es exportar por defecto (con la palabra clave **`export default`**),
- la segunda es exportar múltiples valores (con la palabra clave **`export`**).

Cuando se exporta un valor por defecto, se utiliza la sintaxis de exportación sin llaves **`{}`**. 

Por ejemplo, si en el módulo **`modulo.js`** se exporta un valor por defecto como sigue:

```jsx
export default function sumar(a, b) {
  return a + b;
}
```

Entonces, para importarlo en otro archivo, se utiliza la sintaxis sin llaves, así:

```jsx
import sumar from './modulo.js';
```

Por otro lado, cuando se exportan múltiples valores, se utiliza la sintaxis de exportación con llaves **`{}`**. 

Por ejemplo, si en el módulo **`modulo.js`** se exportan dos valores como sigue:

```jsx
export const nombre = 'Juan';
export const edad = 30;
```

Entonces, para importarlos en otro archivo, se utiliza la sintaxis con llaves, así:

```jsx
import { nombre, edad } from './modulo.js';
```

Es importante destacar que, en ambos casos, el nombre utilizado en la importación debe coincidir con el nombre utilizado en la exportación.

## 20.1 Exportar e Importar Funciones

veamos como exportar e importar valores y funciones. La modularidad de este enfoque facilita la organización y mantenimiento del código.

#### App.js

como importar funciones y usar modulos.

```jsx
// se utiliza la palabra clave import para importar varias funciones y variables desde un archivo llamado cliente.js
// se realiza mediante destructuración de objetos, lo que significa que cada elemento importado debe tener el mismo nombre que en el archivo original.
// En este caso, se están importando cuatro elementos: nombreCliente, ahorro, mostrarInformacion y tieneSaldo.
import { nombreCliente, ahorro, mostrarInformacion, tieneSaldo} from './cliente.js'

// se usan las variables y funciones  que importamos en el código actual
console.log(nombreCliente);
console.log(ahorro);

// llama a la función mostrarInformacion y se pasa como argumentos las variables nombreCliente y ahorro.
console.log(mostrarInformacion(nombreClinete, ahorro));

//llama a la función tieneSaldo y se pasa como argumento la variable ahorro.
// La función tieneSaldo verifica si la variable ahorro es mayor que cero y muestra un mensaje correspondiente en la consola.
tieneSaldo(ahorro)

```

#### Cliente.js

veamos cómo se pueden exportar valores y funciones en un módulo en JavaScript.

```jsx
// Ambas constantes nombreCLiente, ahorro se exportan para que puedan ser utilizadas en otros archivos de JavaScript que importen este módulo.
export const nombreCliente = 'Mario'
export const ahorro = 200;

// Las siguientes líneas son dos funciones que también se exportan
export function mostrarInformacion(nombre, ahorro) {
	return `Cliente: ${nombre} - Ahorro: ${ahorro}`;
}

export function tieneSaldo(ahorro){
	if (ahorro>0){
		console.log('si tiene saldo');
	} else {
		console.log('El cliente no tiene saldo');
	}
}

```

Exportar estos valores y funciones permite que se puedan utilizar en otros archivos que importen este módulo.

## 20.3 Exportar e Importar una clase

Veamos como exportar e importar clases.

#### App.js

Este código muestra cómo importar variables y funciones desde otro archivo utilizando la sintaxis de destructuración de objetos, y cómo utilizarlas en el código actual. También muestra cómo crear una instancia de una clase y llamar a sus métodos.

```jsx
// se utiliza la palabra clave import para importar varias funciones y variables desde un archivo llamado cliente.js
// se realiza mediante destructuración de objetos, lo que significa que cada elemento importado debe tener el mismo nombre que en el archivo original.
// En este caso, se están importando cuatro elementos: nombreCliente, ahorro, mostrarInformacion, tieneSaldo y la clase Cliente.
import { nombreCliente, ahorro, mostrarInformacion, tieneSaldo, Cliente} from './cliente.js'

// se usan las variables y funciones  que importamos en el código actual
console.log(nombreCliente);
console.log(ahorro);

// llama a la función mostrarInformacion y se pasa como argumentos las variables nombreCliente y ahorro.
console.log(mostrarInformacion(nombreClinete, ahorro));

//llama a la función tieneSaldo y se pasa como argumento la variable ahorro.
// La función tieneSaldo verifica si la variable ahorro es mayor que cero y muestra un mensaje correspondiente en la consola.
tieneSaldo(ahorro)

// se crea una instancia de la clase Cliente utilizando nombreCliente y ahorro como argumentos, y se muestra su información 
// utilizando la función mostrarInformacion definida en la clase.
const cliente = new Cliente ( nombreCliente, ahorro);

console.log(cliente.mostrarInformacion ())

```

#### Cliente.js

Este código es un módulo de JavaScript que exporta constantes, funciones y una clase que pueden ser utilizadas en otros archivos JavaScript que importen este módulo.

```jsx
// Ambas constantes nombreCLiente, ahorro se exportan para que puedan ser utilizadas en otros archivos de JavaScript que importen este módulo.
export const nombreCliente = 'Mario'
export const ahorro = 200;

// Las siguientes líneas son dos funciones que también se exportan
export function mostrarInformacion(nombre, ahorro) {
	return `Cliente: ${nombre} - Ahorro: ${ahorro}`;
}

export function tieneSaldo(ahorro){
	if (ahorro>0){
		console.log('si tiene saldo');
	} else {
		console.log('El cliente no tiene saldo');
	}
}

// exporta una clase llamada Cliente. 
// La clase tiene un constructor que acepta dos argumentos, nombre y ahorro, y establece estas propiedades en el objeto de la clase.
// también tiene un método llamado mostrarInformacion que devuelve información sobre el cliente.
export class Cliente {
	constructor(nombre, ahorro){
		this.nombre = nombre;
		this.ahorro = ahorro;
	}

	mostrarInformacion(){
		return `CLiente: ${this.nombre} - Ahorro: ${this.ahorro}`
	}
}

// Exportar estas constantes, funciones y clase permite que otros archivos de JavaScript las importen y las utilicen en su propio código.
```