# music-player


1. Crear un array con 5 canciones, recorrer el array y mostrar en consola cada canción.
2. Crear un array con 5 artistas que correspondan a cada canción del primer array.


AQUI YA JS 
3. Mostrar en un HTML un DIV por cada canción y artista generado con JS a partir de la información del array.

4. Crear un botón con el texto "Tema 3" que al hacer click muestre en consola el nombre de la canción y el artista de la canción que se encuentra en la posición 3 del array.

5. Agrega botones de "siguiente", "anterior", "play", "pausa" con ids únicos para cada uno, y agrega el siguiente código JS en tu archivo, pruebalo y comenta que hace el código:

```js
document.addEventListener('click', (event) => {
    console.log(event.target.id);
});
```

6. Agregar un atributo id a cada div generado en el punto 3, y hacer que al hacer click en cada div muestre en consola el nombre de la canción y el artista de la canción correspondiente.

7. Actualiza el punto anterior para mostrar en el HTML un párrafo con el nombre de la canción y el artista de la canción correspondiente al hacer click en cada div. Te animas a agregar un tercer array con imágenes del artista y mostrar la imagen correspondiente al hacer click en cada div?

8. Dale la funcionalidad necesaria a los botones Siguiente, Anterior para que pase de una canción a otra en el array de canciones mostrado en el HTML.




  <body>
    <h1>Music Player</h1>

    <h2>Lista de Canciones</h2>

    <div id="divListaCanciones" class="Lista-cancion"></div>

    <button id="btnTema3">Tema 3</button>

    <h3>Canción reproduciéndose</h3>


    <div id="playingSong"> </div>

    
    <div class="btnsMenu">
      <button id="btnAnterior">Anterior</button>
      <button id="btnPausa">Pausa</button>
      <button id="btnPlay">Play</button>
      <button id="btnSiguiente">Siguiente</button>
    </div>

    <script>
      const listaCanciones = [
        "Harvest sky",
        "Normal",
        "Romero Santo",
        "Barro",
        "Winter Baby",
      ];
      const listaArtistas = [
        "Oklou",
        "Carolina Durante",
        "Judeline",
        "Duki",
        "070",
      ];

      const divListaCanciones = document.getElementById("divListaCanciones");
      const btnTema3 = document.getElementById("btnTema3");

      listaCanciones.forEach((cancion, idx) => {
        const artista = listaArtistas[idx];
        const song = listaCanciones[idx];

        divListaCanciones.innerHTML += ` <div id="song_${idx} class="Lista-cancion"> 
           ${idx+1}. ${song} <br> ${artista}</div>`;
      });

      btnTema3.addEventListener("click", () => {
        console.log("Canción: ", listaCanciones[2]);
        console.log(`Artista: ${listaArtistas[2]}`);
      });

      //Ejercicio 5

      // Ejercicio 6 
      // Busca todos los divs con class Lista-cancion  

      const divsCanciones = document.querySelectorAll(".Lista-cancion");
      const divPlayingSong = document.getElementById("#playingSong")


      divsCanciones.forEach ((divCancion, i ) => {

        divCancion.addEventListener("click", (event) => {
            const song = listaCanciones[i]; 
            const artist = listaArtistas[i]; 
            console.log ("Artista: "+artist+ " canción: "+song);


            divPlayingSong.innerHTML = `<div> canción: ${song} <br> canción: ${artist}<
            </div>`; 
        });

      });
