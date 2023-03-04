# Sección 14: **Eventos en JavaScript**

## 14.1 Detectar cuando el HTML está listo

Cuando visitamos un sitio o aplicación web, existen una gran cantidad de eventos que pasan.

Cuando te gusta un tweet o das retweet, cuando le das me gusta o compartir a una publicación de Facebook, cuando navegas entre los diferentes productos de amazon, todos estos son eventos que ocurren, al llenar un formulario de airbnb y ver la galería de fotos también son eventos.

Todos los eventos utilizan el método en el document de `addEventListener`, este registra un evento en específico, como puede ser un `clic` en un enlace o imagen, `submit` a un formulario, o cuando el usuario escribe.

Por lo tanto, la sintaxis es de la sig. Forma: `document.addEventListener` seguido del evento que estamos escuchando.

```jsx
// Un evento que es muy común y utilizaras en todos tus proyectos es uno llamado 
// DOMContentLoaded: es un evento que se ejecuta una vez que es cargado todo el documento HTML
// Los eventos siempre seran en una funcion anonima
console.log(1)
    document.addEventListener('DOMContentLoaded', () => {
        console.log(2);
    }) // Nota todos los eventos que hay disponibles
console.log(3);

// este evento espera a que todo este listo primero, que todo este cargado y luego se ejecuta
```

## 14.2 Eventos con el Mouse

Estaremos viendo eventos que ocurren con el mouse

```jsx
// seleccionamos la navegacion de nuestro HTML
const nav = document.querySelector('.navegacion');

// vamos a registrar el eventListener para el nav..

nav.addEventListener('mouseenter', () => {
    console.log('entrando a navegacion')

    nav.style.backgroundColor = 'white';
});

nav.addEventListener('mouseout', () => {
    console.log('saliendo de la navegacion');

    nav.style.backgroundColor = 'transparent';
})
```

### otros eventos

- mouseenter : cuando el puntero está entrando en el elemento, registra el evento.
- mouseout : cuando el puntero está saliendo del elemento.
- mousedown : cuando presionamos.
- click : similar, de hecho es probablemente el más utilizado.
- dbclick : doble clic como cuando quieres abrir un archivo.
- mouseup : al soltar

## 14.3 Eventos sobre los Inputs

Estaremos viendo eventos que suceden con el teclado, es decir, cuando el usuario escribe en una etiqueta html input.

### Algunos eventos del teclado

- keydown  - cuando presionas una tecla.
- keyup - Cuando sueltas la tecla.
- blur - cuando sales del input - ideal para validación.

También hay eventos para cortar, copiar y pegar:

- cut - detecta el evento del cortar ctrl + x.
- copy - detecta el evento de copiar  ctrl + c.
- paste - detecta el evento de pegar ctrl + v.
- input - (todo en 1) escucha cuando se ejecutan todas las que se citaron arriba excepto el blur. Incluyendo cortar, pegar y copiar

```jsx
// tenemos un formulario 
const busqueda = document.querySelector('.busqueda');

busqueda.addEventListener('input', () => {
     console.log('escribiendo...');
})
```

¿Ahora, no tiene mucha utilidad enviar a la consola un mensaje, no? Lo ideal sería saber el texto que se escribe o poderlo leer...

```jsx
busqueda.addEventListener('input', e => {
     console.log(e); // Mucha información, muestra todos los eventos que se estan presentando
     console.log( e.type ); // Te dira sobre que elemento estamos trabajando...
     console.log(e.target); // el input completo, te dira toda la info completa del elemento...
     console.log(e.target.value) // te dira lo que el usuario escribe en el momento...
})
```

También puede ser como función → busqueda.addEventListener('input',  leerInput);

```jsx
function leerInput(e) {
    console.log(e); // Mucha información...
    console.log( e.type ); // Te dira sobre que elemento estamos trabajando...
    console.log(e.target); // el input completo...
    console.log(e.target.value) // lo que el usuario escribe...

}
```

## 14.4 Evento Submit a un formulario

Veamos los eventos para un formulario, básicamente es uno, pero es muy importante y merecía su propio sección.

Cuando envías un formulario, usualmente lo que esté en el `action`, es la página que se abre...

```jsx
const formulario = document.querySelector('.formulario');

formulario.addEventListener('submit', e => {
// PreventDefault es evitar que el navegador realice la acción por default, en este caso ir al action...
    e.preventDefault(); 
// Usualmente utilizaras preventDefault para validar el formulario antes de enviarlo a un servidor
// Crear consultas Ajax entre otras cosas
    console.log('enviando...');
    console.log(e);// Mucha información valiosa en este e -> evento...
    console.log(e.target.method) // podemos conocer el tipo de metodo que utiliza el formulario
    console.log(e.target.action) // podemos conocer tambien la accion del formulario
})

// utilizando un evento sin funcion anonima
formulario.addEventListener('submit', validadFormulario);

function validarFormulario(e) {
	e.preventDefault(); // evitamos que ejecute su accion por defecto para trabajar antes con los datos del formulario
// por ejemplo evitar el metodo post o get para poder validar un formulario o enviar los datos a algun ENDPOINT de alguna API
	console.log('Consultar una api'); // por ejemplo desde aqui podemos consultar una api
	console.log('e.target.action'); // podemos conocer la accion que hara nuestro formulario
}
```

## 14.5 Eventos al dar scroll con el mouse

En esta sección estaremos viendo eventos que suceden con el `scroll` del sitio web.

Es muy común que muchos sitios agreguen funcionalidad de que al dar `scroll` y llegar a ver un elemento este tenga alguna animación, eso se hace con eventos en el `mouse`.

Estos eventos suceden en la ventana global y podemos ver todos los eventos que suceden en el proyecto, hay muchísimas información con todo lo relacionado de lo que está sucediendo en nuestra página web

<img src="./img/section-14-5.png"/>

```jsx
// vamos a escuchar por un scroll
window.addEventListener('scroll', () => {
    // console.log('scrolling...'); // cada vez que le de scroll se va a ir ejecuntado este evento
//Detectar el Scrolling vertical...
const pxScroll = window.scrollY; 
console.log(pxScroll); // devuelve la cantidad de pixeles que le da scroll en la pagina

// Detectar un elemento al dar scroll...
const premium = document.querySelector('.premium');
// Este método getBoundingClientRect te da el tamaño de un elemento y su ubicación respecto a la ubicación actual..
// te da la informacion a que distancia se encuentra el elemento antes de mostrar en pantalla
const ubicacion = premium.getBoundingClientRect(); 
console.log(ubicacion);

// entonces podemos saber por medio de esa propiedad cuanto scroll o distancia faltarian para mostra el elemento
    if(ubicacion.top < 100) {
        console.log('Ya esta visible');
    } else {
        console.log('Aún no esta visible..')
    }
})
```

## 14.6 ¿Qué es el Event Bubbling?

Veamos lo que se conoce como Event Bubbling.

`Event Bubling` es cuando presionas en un evento, pero ese evento se propaga por muchos otros lugares dando resultados inesperados.

```jsx
// en nuestro HTML de ejemplo
// tenemos diferentes cards, con información...
// vamos a crear 3 selectores

const cardDiv = document.querySelector('.card');
const infoDiv = document.querySelector('.info');
const titulo = document.querySelector('.titulo');

// el event Bubling se propaga y se va hacia un elemento padre o cualquiera que tenga registrado ese evento
// en otras palabras, tenemos una accion que hacemos en un elemento hijo
// pero tambien se dispara/activa los eventos del elemento padre y elementos hermanos

cardDiv.addEventListener('click', e => {
// al igual que tenemos el preventDefault() podemos detener el Event Bubling, osea la propagacion de los eventos
// con el evento stopPropagation()
    e.stopPropagation();
    console.log('click card');
})
infoDiv.addEventListener('click', e => {
    e.stopPropagation();
    console.log('click info');
})

titulo.addEventListener('click', e => {
    e.stopPropagation();
    console.log('click titulo');
})
```

## 14.7 Prevenir Event Bubbling con Delegation

Otra opción para detener la propagación de eventos es aplicar algo llamado `delegation`.

```jsx
const cardDiv = document.querySelector('.card');

// si tenemos un elemento padre con muchos elementos hijos
// como podemos saber a que elemento le estamos dando click 
// podemos identificarlo con el evento.target, 
// cuando tenemos un elemento padre, y delegamos funciones a dicho elemento
// para tomar acciones dependiendo el elemento hijo, a esto se le denomina "Delegation"

cardDiv.addEventListener('click', e => {
// podemos tener un accion determinada cuando damos click a cierto elemento
    if(e.target.classList.contains('titulo')) {
        console.log('click titulo');
    }
    if(e.target.classList.contains('info')) {
        console.log('click info');
    }
});
```

## 14.8 Prevenir Event Bubbling con un método

Otra manera de agregar funciones hacia un elemento 

```jsx
// Evitar la propagación con contenido creado...
const parrafo1 = document.createElement('P');
parrafo1.textContent = 'Concierto';
parrafo1.classList.add('categoria');
parrafo1.classList.add('concierto');

// Segundo parrafo
const parrafo2 = document.createElement('P');
parrafo2.textContent = 'Concierto de Rock';
parrafo2.classList.add('titulo');

// 3er parrafo...
const parrafo3 = document.createElement('p');
parrafo3.textContent = '$800 por persona';
parrafo3.classList.add('precio');

// estamos generando contenido HTML con scripting
// podemos asociar una funcion a este evento en un determinado elemento creado con scripting
parrafo3.onclick = nuevaFuncion(1);

// tambien podemos crear una funcion anonima para mandar parametros
parrafo3.onclick = function () {
		nuevaFuncion2(1); // creamos un funcion para pasar parametro
}

// crear el div...
const info = document.createElement('div');
info.classList.add('info');
info.appendChild(parrafo1)
info.appendChild(parrafo2)
info.appendChild(parrafo3);

// Vamos a crear la imagen
const imagen = document.createElement('img');
imagen.src = 'img/hacer2.jpg';

// Crear el Card..
const contenedorCard = document.createElement('div');
contenedorCard.classList.add('contenedorCard');

// Vamos a asignar la imagen al card...
contenedorCard.appendChild(imagen);

// y el info
contenedorCard.appendChild(info);

// Insertarlo en el HTML...
const contenedor = document.querySelector('.hacer .contenedor-cards');
contenedor.appendChild(contenedorCard); // al inicio info

// funcion 1
function nuevaFuncion(id) {
    console.log('click..', id)
}

// funcion 2
function nuevaFuncion2(id){
		console.log('click..', id)
}
```