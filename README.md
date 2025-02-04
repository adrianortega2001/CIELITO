<title>¿Quieres ser mi cita?
body {
background-color: pink;
display: flex;
flex-direction: column;
align-items: center;
justify-content: center;
height: 100vh;
text-align: center;
font-family: Arial, sans-serif;
}
img {
width: 300px;
height: auto;
border-radius: 10px;
}
button {
margin: 10px;
padding: 10px 20px;
font-size: 16px;
border: none;
cursor: pointer;
border-radius: 5px;
}
.yes {
background-color: lightgreen;
}
.no {
background-color: lightcoral;
}
</style>
¿Quieres ser mi cita este 14 de febrero?<button class="yes" onclick="sayYes()">Sí<button class="no" onclick="sayNo()">No
¡Sabía que dirías que sí! ¡Te amo!<button onclick="showAlbum()">A continuación, un álbum de fotos
<button id="nextButton" onclick="nextPhoto()">Siguiente
let noClickCount = 0;
const images = ["imagen1.jpeg", "imagen2.jpeg", "imagen3.jpeg"];
const albumImages = ["foto1.jpeg", "foto2.jpeg", "foto3.jpeg", "foto4.jpeg", "foto5.jpeg"];
let photoIndex = 0;
function sayNo() {
noClickCount++;
document.getElementById("image").src = images[noClickCount % images.length];
}
function sayYes() {
// Cambiar la imagen al responder "Sí" y ocultar botones
document.getElementById("image").src = "imagen_final.jpeg";
document.getElementById("question").style.display = "none";
document.querySelector(".yes").style.display = "none";
document.querySelector(".no").style.display = "none";
document.getElementById("nextStep").style.display = "block";
}
function showAlbum() {
// Ocultar la pantalla anterior y mostrar el álbum de fotos
document.getElementById("nextStep").style.display = "none";
document.getElementById("albumScreen").style.display = "block";
// Reiniciar el índice de fotos al mostrar el álbum
photoIndex = 0;
document.getElementById("albumImage").src = albumImages[photoIndex];
}
function nextPhoto() {
photoIndex++;
if (photoIndex < albumImages.length) {
document.getElementById("albumImage").src = albumImages[photoIndex];
}
if (photoIndex === albumImages.length - 1) {
document.getElementById("nextButton").style.display = "none"; // Ocultar el botón después de la última foto
}
}
</script>
