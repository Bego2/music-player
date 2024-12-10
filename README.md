# music-player

En este README he recopilado la descripción de la tarea y las notas que he ido tomando, para aprender pasito a pasito, sin llenar mucho el código de comentarios

1. Crear un array con 5 canciones, recorrer el array y mostrar en consola cada canción.
2. Crear un array con 5 artistas que correspondan a cada canción del primer array.

3. Mostrar en un HTML un DIV por cada canción y artista generado con JS a partir de la información del array.

```js

// Desde un mismo array podemos acceder a dos arrays, eso es lo útil de todo esto
// Para ello hemos usado +=    significa agregar al final de la lista un nuevo elemento
  const listaCanciones = [...];
  const listaArtistas = [...];

listaCanciones.forEach((cancion, idx) => {
        console.log(`${cancion} - id ${idx}`);

        const song = listaCanciones[idx];
        const artista = listaArtistas[idx];

        // innerHTML
        divListaCanciones.innerHTML += 
        `<div id="song_${idx}" class="Lista-cancion"> 
          <b> ${idx + 1}. ${cancion}</b> <br> 
          ${artista}</div>`;
      });

```

4. Crear un botón con el texto "Tema 3" que al hacer click muestre en consola el nombre de la canción y el artista de la canción que se encuentra en la posición 3 del array.

5. Agrega botones de "siguiente", "anterior", "play", "pausa" con ids únicos para cada uno, y agrega el siguiente código JS en tu archivo, pruebalo y comenta que hace el código:

```js

   /**Este codigo lo que hace es
       * (1) Escuchar si alguien clicka en alguna parte del documento
       * (2) La información de ese click se guarda en el objeto "event"
       * (3) Event.target nos dice a QUIEN afectó en el evento (a un div/a un button/etc)
       * (4) Target.id Nos dice el ID de a quien afectó el evento
       * En definitiva (event: qué) (target: quién) (id: cómo se llama para encontrarle) 
      */
document.addEventListener('click', (event) => {
    console.log(event.target.id);
});
```

6. Agregar un atributo id a cada div generado en el punto 3, y hacer que al hacer click en cada div muestre en consola el nombre de la canción y el artista de la canción correspondiente.



7. Actualiza el punto anterior para mostrar en el HTML un párrafo con el nombre de la canción y el artista de la canción correspondiente al hacer click en cada div. Te animas a agregar un tercer array con imágenes del artista y mostrar la imagen correspondiente al hacer click en cada div?

8. Dale la funcionalidad necesaria a los botones Siguiente, Anterior para que pase de una canción a otra en el array de canciones mostrado en el HTML.

```js

// Opción más CLARA para hacer esto:
// preguntar algo si es la última canción
btnSig.addEventListener("click", () => {
if (idCancionActual === lista_canciones.length - 1) {
  // si es cierto, idCancion = 0
  idCancionActual = 0;
} else {
  // si no es cierto, idCancion va a sumar 1
  idCancionActual++;
}
// revisar que no me pase de la última canción (empiece por la primera)
imprimirReproduciendo();

});

btnAnt.addEventListener("click", () => {
// preguntar si estoy en la primera canción
if (idCancionActual == 0) {
  idCancionActual = lista_canciones.length - 1; // 4
} else {
  idCancionActual--;
}
});

// OPCIÓN MÁ SINTETIZADA
//listaCanciones.length -1 equivale a la posición de la última canción
  btnSiguiente.addEventListener("click", ()=> {
        idCancionActual = (idCancionActual < listaCanciones.length -1) ? idCancionActual +1 : 0; 
                          // si la canción actual no es la última =     entonces avanza +1  / Si es la última: vuelve a cero 
        imprimirReproduciendo();
      });

      btnAnterior.addEventListener("click", ()=> {
        idCancionActual = (idCancionActual > 0) ? idCancionActual -1                  : listaCanciones.length -1;
                          // si la canción actual no es la primera = decrementa -1 /  Si es la primera: ve a la última 
        imprimirReproduciendo();
      });


// 

```

