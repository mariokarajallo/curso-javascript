# Sección 18: Programación Orientada a Objetos en JavaScript

## 18.1 Definiendo e Instanciando una clase

Las Classes en JavaScript llegaron hasta hace pocos años, muchas personas no consideraban a `javascript` como un lenguaje serio, ya que la programación orientada a objetos era el `object constructor` y los métodos eran los `prototypes`.

Así que en 2015 llegaron las classes a javascript, que solo es una mejora en la sintaxis, al final sigue siendo un `object constructor con sus prototypes`.

En realidad sigue siendo lo mismo, pero la facilidad de crear objetos y añadirle métodos si mejoro bastante gracias a las classes.

### Class Declaration

Las classes se crean con la palabra reservada class. El Nombre debe ser en mayusculas Y esta forma se le conoce como CLASS DECLARATION en el CONSTRUCTOR pasamos los valores que va a tener el objeto una vez instanciados

```jsx
class Cliente { 
    constructor( nombre, saldo ) {
        this.nombre = nombre;
        this.saldo = saldo;
    }
}

// Si recuerdas previamente instanciabamos nuestro objecto con...
const juan = new Cliente('Juan', 400);
// para pasar esos valores ('juan',400) las classes introducieron lo que se conoce como constructores...
// en algunos lenguajes el constructor es el mismo nombre de la clase pero en javascript es constructor
console.log(juan);
```

### Class Expression

Existe una segunda forma de crear classes, se le conoce como CLASS EXPRESSION

```jsx
const Cliente2 = class {
    constructor( nombre, saldo ) {
        this.nombre = nombre;
        this.saldo = saldo;
    }

}

const juan2 = new Cliente2('Juan', 400);
console.log(juan2);
```

## 18.2 Métodos y Métodos estáticos en las clases

Los métodos terminan siendo lo mismo que los prototypes. Son funciones específicas para los objetos, que se crean a partir de una clase.

Los métodos son también llamados funciones.

```jsx
// Veamos como añadir métodos a nuestras classes...
class Cliente { 

    constructor( nombre, saldo ) {
        this.nombre = nombre;
        this.saldo = saldo;
    }

    // cualquier método agregado a la clase será parte del proto
		// si mandamos llamar imprimirSaldo(), obtendremos los valores que se establecieron una vez instanciados la clase.
		// this. -> siempre hace referencia al objeto actual
		// de esta manera agregamos un metodo:
    imprimirSaldo() {
        return `Hola ${this.nombre}, tu saldo es: ${this.saldo}`;
    }

    retiraSaldo(retiro) {
        this.saldo -= retiro;
    }

		// existe otra manera de "crear un metodo"
    // También existe algo llamado las propiedades estaticas, estas no requieren ser instanciadas...

    static bienvenida(){
        return `Bienvenido al cajero`;
    }

}

// javascript es constructaor
const juan = new Cliente('Juan', 400);

console.log(juan);

// de esta manera podemos acceder a los metodos de nuestra clase -> clase.metodo()
console.log(juan.imprimirSaldo() ); // Hola Juan, tu saldo es: 400
juan.retiraSaldo(200);
console.log(juan.imprimirSaldo() ); // Hola Juan, tu saldo es: 200

// si llamas a una propiedad estatica, desde un objeto instanciado...
juan.bienvenida(); // No va a funcionar

// las propiedades estaticas se mandan llamar directamente desde las clases...
console.log( Cliente.bienvenida() ); // Esto si va a funcionar
```

## 18.3 Heredar una clase

De la misma forma que puedes heredar un `constructor` con `Prototoypes` y sus `métodos`, también puedes `heredar` una `clase`, es una de la característica que hay en POO (programación orientada a objetos)

```jsx
class Cliente { 
    constructor( nombre, saldo ) {
        this.nombre = nombre;
        this.saldo = saldo;
    }
    imprimirSaldo() {
        return `Hola ${this.nombre}, tu saldo es: ${this.saldo}`;
    }

    retiraSaldo(retiro) {
        this.saldo -= retiro;
    }
    static bienvenida(){
        return `Bienvenido al cajero`;
    }
}

// Queremos crear una CLASE nueva que HEREDE los mismos atributos y propiedades de OTRA CLASE
// Herencia - > se crea el nombre de la clase y se extiende con el nombre de la clase que queremos heredar
class Empresa extends Cliente {
    constructor(nombre, saldo, telefono, tipo) {
        // Va hacia el constructor del padre, y busca los atributos que necesita heredar
        super(nombre, saldo);
        // otros atributos se declaran fuera
        this.telefono = telefono;
        this.tipo = tipo;
    }

		// Reescribir un método...
		// si el padre tiene el mismo nombre de metodo tambien en el hijo
		// el metodo del padre se va a reescribe con el metodo del hijo
    static bienvenida(mensaje){ 
        return `Bienvenido al cajero para empresas`;
    }
}

const pedro = new Cliente('Pedro', 3000);
console.log(pedro);
console.log(pedro.imprimirSaldo() ); // Hola Pedro, tu saldo es: 3000

// Heredando y creando una instancia de empresa
const empresa = new Empresa('Empresa1', 10000, 10290193, 'Construccion');

// Debido a que heredamos podemos acceder a imprimirSaldo
console.log(empresa.imprimirSaldo() ); // Hola Empresa1, tu saldo es: 10000

// Acceder al statico sin instanciar de ambos
console.log(Empresa.bienvenida() ); // Bienvenido al cajero para empresas
console.log(Cliente.bienvenida() ); // Bienvenido al cajero
```