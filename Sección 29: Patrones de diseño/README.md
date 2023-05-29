# Sección 29: **Design Patterns o Patrones de Diseño en JavaScript**

## 29.1 ¿Qué son los Design Patterns o Patrones de Diseño ?

Los patrones de diseño (Design Patterns) en JavaScript son soluciones reutilizables y probadas para resolver problemas comunes en el diseño de software. Estos patrones proporcionan un enfoque estandarizado y eficiente para abordar desafíos específicos en el desarrollo de software, lo que permite a los ingenieros de software escribir código más mantenible, escalable y fácil de entender.

### Los beneficios de utilizar patrones de diseño:

1. Reutilización de código: Los patrones de diseño promueven la reutilización de soluciones probadas y eficientes, lo que ahorra tiempo y esfuerzo en el desarrollo.
2. Mantenibilidad: Los patrones de diseño facilitan la comprensión del código y su mantenimiento a lo largo del tiempo, ya que siguen principios bien establecidos y organizan el código de manera estructurada.
3. Escalabilidad: Al utilizar patrones de diseño, se pueden construir aplicaciones escalables y flexibles, lo que facilita la incorporación de nuevas funcionalidades y la adaptación a cambios futuros.
4. Claridad y legibilidad del código: Los patrones de diseño promueven una estructura clara y consistente en el código, lo que facilita su lectura y comprensión por parte de otros desarrolladores.

### Existen varias categorías de patrones de diseño:

A continuación, se presentan algunas de las categorías más comunes:

#### 1. Patrones de diseño creacionales:

- Estos patrones se utilizan para crear objetos de manera flexible y encapsulada. Algunos ejemplos de patrones creacionales son el patrón de fábrica (factory), el patrón constructor (constructor), el patrón prototipo (prototype) y el patrón de una sola instancia (singleton).

#### 2. Patrones de diseño estructurales:

- Estos patrones se centran en la composición de clases y objetos para formar estructuras más grandes y flexibles. Ejemplos de patrones estructurales incluyen el patrón de adaptador (adapter), el patrón de decorador (decorator), el patrón de fachada (facade) y el patrón de puente (bridge).

#### 3. Patrones de diseño de comportamiento:

- Estos patrones se enfocan en la interacción y comunicación entre objetos. Ayudan a definir cómo los objetos se relacionan y distribuyen responsabilidades. Algunos ejemplos de patrones de comportamiento son el patrón de observador (observer), el patrón de estrategia (strategy), el patrón de plantilla (template) y el patrón de mando (command).

#### 4. Patrones de diseño de arquitectura:

- Estos patrones abordan la estructura y organización de sistemas más grandes, como patrones MVC (Model-View-Controller), MVVM (Model-View-ViewModel) y Flux.

Es importante tener en cuenta que los patrones de diseño son soluciones generales y flexibles, y pueden adaptarse y combinarse según las necesidades específicas de cada proyecto. La clave para utilizarlos de manera efectiva es comprender los problemas que resuelven y cómo se pueden aplicar en diferentes situaciones.

## 29.2 Class Pattern

El patrón de clase (Class Pattern) en JavaScript es una forma de implementar la programación orientada a objetos (POO) utilizando la sintaxis de clases introducida en ECMAScript 2015 (ES6). Aunque JavaScript es un lenguaje basado en prototipos, el patrón de clase brinda una estructura más familiar para aquellos familiarizados con otros lenguajes de programación orientados a objetos, como Java o C++.

El patrón de clase en JavaScript consiste en utilizar la palabra clave **`class`** para definir una clase, que puede tener propiedades (atributos) y métodos. Los objetos se crean mediante la palabra clave **`new`**, y las propiedades y métodos se pueden acceder utilizando la notación de punto.

Aquí tienes un ejemplo sencillo de cómo se utiliza el patrón de clase en JavaScript:

```jsx
class Persona {
  constructor(nombre, edad) {
    this.nombre = nombre;
    this.edad = edad;
  }

  saludar() {
    console.log(`Hola, mi nombre es ${this.nombre} y tengo ${this.edad} años.`);
  }
}

// Crear un objeto utilizando la clase Persona
const persona = new Persona("Mario", 25);
persona.saludar(); // Imprime: "Hola, mi nombre es Mario y tengo 25 años."
```

- En este ejemplo, se define una clase **`Persona`** con un constructor que recibe el nombre y la edad como parámetros y los asigna a las propiedades **`nombre`** y **`edad`**.
- La clase también tiene un método **`saludar()`** que imprime un mensaje utilizando los valores de las propiedades.
- Luego, se crea un objeto **`persona`** utilizando la clase **`Persona`**, pasando los valores **`'Mario'`** y **`25`** al constructor.
- Finalmente, se llama al método **`saludar()`** en **`persona`**, lo que imprime el mensaje con el nombre y la edad.

El patrón de clase en JavaScript simplifica la sintaxis y la estructura del código cuando se trabaja con programación orientada a objetos, lo que facilita la creación y el mantenimiento de clases y objetos en tu aplicación.

## 29.3 Constructor Pattern

El patrón Constructor en JavaScript es una forma de crear objetos utilizando funciones constructoras. Este patrón se basa en el concepto de clases y objetos, donde una función constructora actúa como una plantilla para crear múltiples instancias de un objeto con propiedades y métodos similares.

En lugar de utilizar un objeto literal o una función de fábrica para crear objetos, el patrón Constructor emplea una función constructora que se invoca con la palabra clave **new** para crear e inicializar objetos.

### Características del patrón Constructor:

1. Encapsula la creación y la inicialización de objetos en una función constructora.
2. Permite la creación de múltiples objetos con propiedades y métodos similares.
3. Facilita la herencia y la reutilización de código a través de prototipos.

Aquí tienes un ejemplo sencillo de cómo implementar el patrón Constructor en JavaScript:

```jsx
// Definir la función constructora
function Auto(marca, modelo, anio) {
  this.marca = marca;
  this.modelo = modelo;
  this.anio = anio;

  this.getDescripcion = function () {
    returnthis.marca + " " + this.modelo + " (" + this.anio + ")";
  };
}

// Crear instancias de Auto utilizando el patrón Constructor
var auto1 = new Auto("Toyota", "Corolla", 2020);
var auto2 = new Auto("Honda", "Civic", 2019);

// Llamar a un método en las instancias creadas
console.log(auto1.getDescripcion()); // Output: "Toyota Corolla (2020)"
console.log(auto2.getDescripcion()); // Output: "Honda Civic (2019)"
```

- En este ejemplo, la función **Auto** es la función constructora que define las propiedades **marca**, **modelo** y **anio**, así como el método **getDescripcion**.
- Al utilizar la palabra clave **new** para crear instancias de **Auto**, se crea un nuevo objeto con las propiedades y métodos definidos en la función constructora.
- Luego, puedes interactuar con las instancias creadas y llamar a sus métodos, como en el caso de **auto1.getDescripcion()** y **auto2.getDescripcion()**.

Con la introducción de las clases en ECMAScript 2015 (ES6), el patrón constructor también se puede implementar utilizando la sintaxis de clases.

El Constructor Pattern con la sintaxis de clases en ES6 consiste en definir una clase que actúa como un constructor para crear objetos. El constructor se define utilizando el método especial **`constructor()`**, que se ejecuta automáticamente cuando se crea una nueva instancia de la clase. Dentro del constructor, se pueden definir propiedades y métodos para los objetos creados.

Aquí tienes un ejemplo sencillo del Constructor Pattern utilizando la sintaxis de clases de ES6:

```jsx
// Constructor Pattern es cuando utilizamos una clase base
class Persona {
  constructor(nombre, email, empresa) {
    this.nombre = nombre;
    this.email = email;
  }
}

class Cliente extends Persona {
  constructor(nombre, email, empresa) {
    super(nombre, email);
    this.empresa = empresa;
  }
}

const persona = new Persona("Juan", "correo@correo.com");
console.log(persona);

const cliente = new Cliente("Miguel", "cliente@cliente.com", "Código Con Juan");
console.log(cliente);
```

- En este ejemplo se demuestra la herencia utilizando la palabra clave **extends** y la función **super()**. La clase **Cliente** hereda de la clase **Persona**, lo que significa que **Cliente** tiene acceso a las propiedades y métodos de **Persona**. En el primer ejemplo, no se muestra la herencia.
- Ambos ejemplos siguen el patrón Constructor, pero el segundo ejemplo utiliza la sintaxis de clases de ES6, que es más moderna y fácil de leer. Además, el segundo ejemplo demuestra cómo implementar la herencia utilizando clases de ES6, lo que no se muestra en el primer ejemplo. En general, se recomienda utilizar la sintaxis de clases de ES6 cuando sea posible, ya que proporciona una forma más clara y estructurada de trabajar con objetos y herencia en JavaScript.

## 29.4 Singleton

El patrón Singleton es un patrón de diseño creacional que se utiliza para garantizar que una clase tenga una única instancia y proporcionar un punto de acceso global a ella. En otras palabras, el patrón Singleton garantiza que solo haya una instancia de una clase en todo el programa y proporciona una forma de acceder a esa instancia desde cualquier parte del programa.

El patrón Singleton se utiliza a menudo en situaciones en las que es importante que solo haya una instancia de una clase, como en el caso de una conexión de base de datos o un registro de eventos. Al utilizar el patrón Singleton, se garantiza que solo haya una instancia de la clase y que todas las solicitudes de esa instancia se dirijan a la misma instancia.

```jsx
// Singleton no te va a permitir crear múltiples instancias de una clase..., en cambio te va a retornar el objeto ya instanciado...
let instancia = null;

class Persona {
  constructor(nombre, email) {
    if (!instancia) {
      this.nombre = nombre;
      this.email = email;
      instancia = this;
    } else {
      return instancia;
    }
  }
}

const persona = new Persona("Juan", "correo@correo.com");
const persona2 = new Persona("Karen", "karen@karen.com");

console.log(persona);
console.log(persona2);
```

- En este ejemplo, **`persona`** y **`persona2`** hacen referencia a la misma instancia de **`Persona`**, ya que el patrón Singleton asegura que no se puedan crear múltiples instancias y que todas las llamadas a la creación de instancias devuelvan la instancia existente.
- Al imprimir **`persona`** y **`persona2`**, verás que ambos objetos tienen los mismos valores de **`nombre`** y **`email`**, lo que demuestra que están utilizando la misma instancia del Singleton.

Es importante tener en cuenta que la implementación del patrón Singleton puede variar según el lenguaje de programación utilizado. Además, es importante tener en cuenta que el patrón Singleton puede tener algunas desventajas, como la dificultad para probar y la posible violación del principio de responsabilidad única. Por lo tanto, se recomienda utilizar el patrón Singleton con precaución y solo en situaciones en las que sea realmente necesario.

## 29.5 Factory

El patrón Factory (Fábrica) es un patrón de diseño creacional que proporciona una interfaz para crear objetos en una superclase, permitiendo a las subclases alterar el tipo de objetos que se crearán. En lugar de llamar directamente al constructor de una clase para crear un objeto, se utiliza una función o método de fábrica para crear el objeto.

La implementación del Factory Pattern en JavaScript ES6 se beneficia de la sintaxis de clases y métodos estáticos. Aquí tienes un ejemplo para ilustrar cómo se puede implementar:

```jsx
class Producto {
  constructor(nombre, precio) {
    this.nombre = nombre;
    this.precio = precio;
  }

  describir() {
    console.log(`Producto: ${this.nombre}, Precio: ${this.precio}`);
  }
}

class FabricaProductos {
  static crearProducto(tipo) {
    switch (tipo) {
      case "A":
        return new Producto("Producto A", 100);
      case "B":
        return new Producto("Producto B", 200);
      case "C":
        return new Producto("Producto C", 300);
      default:
        throw new Error("Tipo de producto inválido");
    }
  }
}

// Uso del Factory Pattern
const productoA = FabricaProductos.crearProducto("A");
const productoB = FabricaProductos.crearProducto("B");
const productoC = FabricaProductos.crearProducto("C");

productoA.describir(); // Producto: Producto A, Precio: 100
productoB.describir(); // Producto: Producto B, Precio: 200
productoC.describir(); // Producto: Producto C, Precio: 300
```

- En este ejemplo, la clase **`Producto`** representa un objeto de producto con propiedades de nombre y precio, y un método **`describir()`** para mostrar la información del producto.
- La clase **`FabricaProductos`** es la fábrica que encapsula la lógica de creación de objetos de producto. Contiene un método estático **`crearProducto(tipo)`** que acepta un parámetro **`tipo`** y devuelve un objeto **`Producto`** basado en el tipo especificado.
- En este caso, se utiliza un switch para determinar qué tipo de producto crear y se retorna la instancia correspondiente.
- Al utilizar el Factory Pattern, puedes crear objetos de productos sin necesidad de conocer los detalles internos de cómo se crean. Simplemente utilizas el método estático **`crearProducto`** de la fábrica para obtener el objeto deseado.

Este patrón es útil cuando necesitas crear diferentes tipos de objetos en función de ciertos parámetros o condiciones, y deseas mantener la lógica de creación centralizada en una fábrica. Esto puede facilitar la gestión y la extensibilidad del código a medida que se agregan nuevos tipos de objetos en el futuro.

## 29.6. Module

El patrón Module (Módulo) en JavaScript es un patrón de diseño estructural que permite organizar y encapsular código relacionado en módulos independientes. Este patrón es útil para mantener el código organizado, facilitar la reutilización y evitar la contaminación del espacio de nombres global.

En ECMAScript 6 (ES6), el patrón Module se implementa utilizando módulos nativos de JavaScript, que permiten exportar e importar funciones, clases y variables entre archivos. Aquí tienes un ejemplo de cómo usar módulos en ES6:

1. Creamos un archivo llamado **math.js** que exporta algunas funciones matemáticas:

```jsx
// math.js
exportfunctionadd(a, b) {
return a + b;
}

exportfunctionsubtract(a, b) {
return a - b;
}

exportfunctionmultiply(a, b) {
return a * b;
}

exportfunctiondivide(a, b) {
return a / b;
}
```

2. Creamos otro archivo llamado **app.js** que importa y utiliza las funciones matemáticas:

```jsx
// app.js
import { add, subtract, multiply, divide } from "./math";

console.log(add(1, 2)); // 3
console.log(subtract(5, 3)); // 2
console.log(multiply(2, 3)); // 6
console.log(divide(10, 2)); // 5
```

- En este ejemplo, hemos creado un módulo **math.js** que exporta varias funciones matemáticas. Luego, en **app.js**, importamos y utilizamos estas funciones. Los módulos ES6 nos permiten mantener nuestro código organizado y separado en archivos diferentes, lo que facilita la comprensión y el mantenimiento del código.

Además de las funciones, también puedes exportar e importar clases, objetos y variables utilizando módulos ES6. Esto te permite crear una estructura modular y escalable para tus aplicaciones JavaScript.

## 29.7. Mixin Pattern

El patrón Mixin es un patrón de diseño que permite componer múltiples comportamientos en una sola clase, sin la necesidad de utilizar la herencia de clases. En lugar de heredar comportamientos de una clase base, los mixins permiten "mezclar" comportamientos en una clase de manera flexible y reutilizable.

En ECMAScript 6 (ES6), puedes implementar el patrón Mixin utilizando clases y funciones. Aquí tienes un ejemplo de cómo hacerlo:

```jsx
// Objeto Mixin de ejemplo
const mixin = {
  mixinMethod() {
    console.log("Soy un método del mixin");
  },

  mixinProperty: "Soy una propiedad del mixin",
};

// Clase de ejemplo
class MiClase {
  // Métodos y propiedades de la clase
}

// Aplicar el mixin a la clase
Object.assign(MiClase.prototype, mixin);

// Uso del Mixin Pattern
const objeto = new MiClase();
objeto.mixinMethod(); // Soy un método del mixin
console.log(objeto.mixinProperty); // Soy una propiedad del mixin
```

- Tenemos un objeto **`mixin`** que contiene un método **`mixinMethod()`** y una propiedad **`mixinProperty`** que deseamos mezclar con nuestra clase **`MiClase`**.
- Luego utilizamos **`Object.assign()`** para asignar el mixin al prototipo de la clase de ejemplo llamado**`MiClase`**. Esto hace que todas las instancias de **`MiClase`** tengan acceso a los métodos y propiedades definidos en objeto `mixin`.
- Después de aplicar el mixin, creamos una instancia de **`MiClase`** llamada **`objeto`** y podemos llamar al método **`mixinMethod()`** y acceder a **`mixinProperty`** a través de esa instancia.

El Mixin Pattern es útil cuando deseas agregar funcionalidades adicionales a una clase sin tener que utilizar la herencia tradicional de clases. Puedes mezclar múltiples mixins con una clase para extender su funcionalidad de manera flexible y modular. Esto facilita la composición de comportamientos y evita la complejidad que a menudo surge de la herencia múltiple o profunda.

## 29.8 Namespace

El patrón de diseño Namespace en JavaScript ES6 se utiliza para organizar y agrupar código relacionado dentro de un espacio de nombres o contenedor. Su objetivo principal es evitar colisiones de nombres y proporcionar una estructura más ordenada y modular para las variables, funciones y clases.

Los namespaces son especialmente útiles en lenguajes de programación que no tienen soporte nativo para la modularidad, como JavaScript antes de la introducción de los módulos ES6. Con los namespaces, puedes simular la estructura modular y evitar la contaminación del ámbito global.

Es importante tener en cuenta que aunque los namespaces pueden ser útiles en algunos casos, la tendencia actual en JavaScript es utilizar módulos ES6 para lograr una modularidad más efectiva y un mejor manejo de la dependencia entre diferentes partes del código.

```jsx
// Definición del namespace
const MiNamespace = {
  // Variables y constantes
  variableA: 10,
  variableB: "Hola",

  // Funciones
  funcionA() {
    console.log("Función A");
  },

  funcionB() {
    console.log("Función B");
  },

  // Clases
  MiClase: class {
    constructor(nombre) {
      this.nombre = nombre;
    }

    saludar() {
      console.log(`Hola, soy ${this.nombre}`);
    }
  },
};

// Uso del namespace
console.log(MiNamespace.variableA); // 10
MiNamespace.funcionA(); // Función A

const instancia = new MiNamespace.MiClase("Juan");
instancia.saludar(); // Hola, soy Juan
```

- En este ejemplo, creamos un objeto literal llamado **`MiNamespace`**, que actúa como nuestro espacio de nombres. Dentro de este objeto, definimos variables, funciones y una clase.
- Las variables **`variableA`** y **`variableB`** son propiedades del namespace y se pueden acceder mediante **`MiNamespace.variableA`** y **`MiNamespace.variableB`**.
- Las funciones **`funcionA`** y **`funcionB`** son métodos del namespace y se pueden invocar utilizando **`MiNamespace.funcionA()`** y **`MiNamespace.funcionB()`**.
- La clase **`MiClase`** también se define dentro del namespace y se puede instanciar utilizando **`new MiNamespace.MiClase()`**. Luego, se pueden llamar a los métodos de la clase utilizando la instancia creada.

```jsx
// Namespaces es un design pattern de organización de código, ayuda a evitar colision con nombres en el scope global de javascript.

// la idea del namespace es crear un objeto global alrededor de tu aplicación y agregar todas las funciones dentro en lugar de crear múltiples funciones y objetos que se puedan acceder de forma global.

const restaurApp = {};

restaurApp.platillos = [
  {
    platillo: "Pizza",
    precio: 25,
  },
  {
    platillo: "Hamburguesa",
    precio: 20,
  },
  {
    platillo: "Hot Dog",
    precio: 20,
  },
];

restaurApp.funciones = {
  ordenar: (id) => {
    console.log(
      `Tu platillo: ${restaurApp.platillos[id].platillo} se esta preparando`
    );
  },
  agregarPlatillo: (platillo, precio) => {
    const nuevo = {
      platillo,
      precio,
    };
    restaurApp.platillos.push(nuevo);
  },
  mostrarMenu: (platillos) => {
    console.log(`Bienvenidos a nuestro Menú:`);
    platillos.forEach((platillo, index) => {
      console.log(`${index})  ${platillo.platillo} $ ${platillo.precio}`);
    });
  },
};

restaurApp.funciones.agregarPlatillo("Pastel", 20);
// console.log(restaurApp );
const { platillos } = restaurApp;

restaurApp.funciones.mostrarMenu(platillos);
restaurApp.funciones.ordenar(1);
```

- Dentro del **`restaurApp`**, tienes una propiedad **`platillos`** que es un array que almacena información sobre los platillos disponibles en el menú del restaurante.
- Además, tienes un objeto **`funciones`** dentro de **`restaurApp`** que contiene diferentes funciones relacionadas con la aplicación del restaurante. Estas funciones incluyen **`ordenar`**, que muestra un mensaje indicando que se está preparando un platillo específico, **`agregarPlatillo`**, que permite agregar nuevos platillos al menú, y **`mostrarMenu`**, que muestra en consola el menú con todos los platillos y sus precios.
- Al final del código, estás utilizando las funciones del namespace **`restaurApp`**. Por ejemplo, estás agregando un nuevo platillo llamado "Pastel" mediante **`restaurApp.funciones.agregarPlatillo('Pastel', 20)`**, y luego mostrando el menú completo con **`restaurApp.funciones.mostrarMenu(platillos)`**. También estás realizando un pedido específico usando **`restaurApp.funciones.ordenar(1)`**.

El patrón de diseño Namespace en JavaScript ES6 proporciona una forma de organizar el código en un espacio de nombres único y evitar conflictos de nombres entre diferentes partes del código. Esto promueve la modularidad y el mantenimiento del código a medida que el proyecto crece.

Ten en cuenta que, si bien puedes simular el patrón Namespace en JavaScript ES6 con objetos literales, existen otras formas más avanzadas de implementar namespaces utilizando módulos y sistemas de construcción de JavaScript, como Webpack o TypeScript, que ofrecen soporte nativo para la organización de código en espacios de nombres.
