# Día 32

## Listeners para eventos del usuario

Son funciones que se ejecutan en respuesta a eventos específicos que ocurren en el DOM, como por ejemplo clicks, movimientos del mouse, teclas presionadas, teclas levantadas, etc. Para agregar un evento usamos `addEventListener(evento,función)`.

```js
// selector item DOM
const boton = document.querySelector("button");

// agregar un event listener para el evento de click
boton.addEventListener("click" , () => {console.log("HOLA")});
boton.addEventListener("click" , miFuncion );

function miFuncion(){
    console.log(`HOLA`);
}
```

## Pasar parámetros a funciones con eventos

A veces necesitamos enviar parámetros adicionales a la función que maneja el evento.

```js
boton.addEventListener("click", function(){
    miFunction("Tomi");
})

boton.addEventListener("click", () => miFunction("María")); // ejecutar la función enviando parámetros, la debo meter dentro de una función flecha.
boton.addEventListener("click" , miFuncion ); // ejecutar la función sin enviar parámetros.

function miFuncion(usuario){
    console.log(`HOLA ${usuario}`);
}
```

EJercicio: 
1. Cambiar el color de un elemento al hacerle click:
Crear dos botones (rojo y azul) que cambie el color de fondo de un bloque al hacerle click. La función de cambiar de color tiene que ser la misma.
2. Mensaje al pasar el mouse:
Crear un elemento que muestre un mensaje cuando el ratón pase por encima de él.

### Parámetro "e" (event/evento)

Es un objeto que contiene información sobre el evento ocurrido. Este se pasa automáticamente a la función que maneja el evento.

```js
function handleClick(e){
    console.log("El botón ha sido clickeado");
    console.log("Coordenadas del mouse: ", e.clientX, e.clientY);
}
boton.addEventListener("click", handleClick);

```

Ejercicio 3:

Formulario de entrada:
Crear un formulario que valide la entrada de un usuario, y muestre en pantalla si la entrada no es válida.