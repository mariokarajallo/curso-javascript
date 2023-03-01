# Sección 3: **Strings o Cadenas de Texto y sus Métodos**

## 3.1 Crear Strings en JavaScript

Representan un texto que se puede asignar a una variable.

Existen 3 formas de crearlos que son más populares.

- Dos formas de crear una cadena de `texto primitiva` y Una forma no tan común.

```jsx
/***Forma Primitiva***/

//comillas dobles o sencillas ya lo convierte en string automaticamente
const producto = 'Monitor 20 Pulgadas'; // Utiliza comillas sencillas
const producto2 = "Monitor 20 Pulgadas"; // Utiliza comillas o dobles

// La segunda forma 
const producto2 = String('monitor');

/***Forma menos comun***/

// tercera forma menos comun, objeto de tipo string
const producto3 = new String('monitor');

//escapando un string con barra invertida -> \
// Ejemplo con Pulgadas
const producto4 = "Monitor 24\""; //Monitor 24"
```

Reglas para crear String:

- Utilizar comillas dobles o sencillas al inicio o final, pero no se pueden mezclar.
- Escapar comilla en un string → \”

## 3.2 String Methods - INCLUDES y LENGTH

Veamos algunos métodos existentes en los strings o cadenas de Texto:

### Lenght

Método para saber cuantas letras tiene una variable tipo String o cadena de texto. length es de los muy pocos métodos que no usan () y es más que nada porque no es un método como tal sino una propiedad.

```jsx
const producto = 'Monitor 20 Pulgadas';
console.log(producto.length)
```

### IndexOf()

Revisa si existe una palabra dentro de la variable y te da la posición

```jsx
const producto = 'Monitor 20 Pulgadas';
console.log(producto.indexOf("Pulgadas")) // Nos dirá que posición tiene el texto en caso de encontrarlo
console.log(producto.indexOf('Tablet')); // -1 Significa que no lo pudo encontrar
```

### Includes()

te devuelve True o False si existe la palabra dentro de una variable. Puede distinguir entre mayúsculas y minúsculas

```jsx
const producto = 'Monitor 20 Pulgadas';
console.log(producto.includes('monitor')) // false
console.log(producto.includes('Monitor')); // true

```

## 3.3 Concatenar un String y Template Strings

Método `concat` une dos cadenas de texto o concatena texto y obtengo una sola solida

```jsx
const producto ="Monitor 20 Pulgadas";  
const precio ='30 usd';

console.log(producto.concat('En Descuento')); // Concactenar un string
console.log(producto.concat(precio)); // Concacatenar una variable

// otras maneras de concatener con el simbolo +
console.log(producto + " con un precio de: " + precio);
console.log("el producto " + producto + " tiene un precio de "+ precio);

//en lugar de utilizar signo de + puedes usar ,
console.log("el producto ",producto," tiene un precio de ",precio);

// mejor forma de concatener variables template literal o template string
// comillas inclinadas o "backtips"
// las variables se agregan con las sintaxis ${variable}
console.log(`El producto ${producto} tiene un precio de $ ${precio}`);

```

## 3.4 Cortar Espacios en Blanco de un String

Eliminar espacios en blanco en una cadena de texto, se utiliza para validar formularios.

en java script se puede utilizar los métodos en forma encadenada, es decir colocar un método tras otro se lo conoce como `channing`

```jsx
const producto ="          Monitor 20 Pulgadas          ";
console.log(producto);
console.log(producto.length); //49

//eliminar espacios en blanco
console.log(producto.trimStart()); //elimina espacios en blanco desde el inicio
console.log(producto.trimEnd());//elimina espacios del final de la palabra

// Los métodos en javaScript se pueden encadenar, es decir, colocarse uno junto al otro
console.log(producto.trimStart().trimEnd()); //elimina espacios en blanco al inicio y final
console.log(producto.trim()); // elimina espacios en blanco al inicio y final, es un metodo antiguo
```

## 3.5 String Methods - Replace, Slice y Substring

```jsx
const producto ="Monitor 20 Pulgadas";

//.replace
// para reemplazar una cadena de texto por otra nueva
console.log(producto);
console.log(producto.replace('Pulgadas','"'));
console.log(producto.replace('Monitor', 'Pantalla Curvo'));

//.slice
// para cortar o extraer una parte de una cadena de texto
// se le pasa la posicion del inicio y del final de la cadena de texto a cortar
console.log( producto.slice(0, 10)); // Iniciar en 0 y cortar hasta 10
console.log(producto.slice(8));// Cortar desde el 8 hasta el fin
console.log(producto.slice(2, 10)); // cortar desde 2 hasta el 10

console.log(producto.slice(2,1)); // NO VA A HACER NADA, POR que el primer indice debe ser mayor no corta hacia atras

// alternativa a slice
// .substring()
// si puede cortar de adelante para atras
console.log(producto.substring(0,10));
console.log(producto.substring(2,1));// Si el número es mayor al segundo, va a cortar hacia atras (voltear los números)

const usuario = "Juan";
console.log(usuario.substring(0,1));

//chartAt()
// corta o extrae solo el primer caracter, dependiendo la posicion que elijas
console.log(usuario.charAt(0));
```

## 3.6 String Methods - Repeat y Split

```jsx
const producto ="Monitor 20 Pulgadas";

//.repeat 
// te va a permitir repetir una cadena de texto
const texto= ' en Promocion'.repeat(4); // repite 4 veces el texto
console.log(texto);
console.log(`${producto} ${texto}!!! `);
console.log(producto.repeat(2.2)); // va a redondear a entero

//.split 
// dividir un string y convierte en un array 
const hobbies= "jugar, caminar, cantar, bailar, programar";
// pasar como parametro un caracter por el cual va a dividir el string
console.log(hobbies.split(", "));
```

## 3.7 String Methods - Convertir a Mayusculas o Minusculas

```jsx
const producto ="Monitor 20 Pulgadas";
console.log(producto);

// .toUpperCase()
// convierte la cadena de texto a mayusculas
console.log(producto.toUpperCase());

// .toLowerCase
// convierte la cadena de texto en minusculas
console.log(producto.toLowerCase());

//.toString convierte numero a texto
const precio=6000;
console.log(precio);
console.log(precio.toString());
```