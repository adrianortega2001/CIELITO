<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>¿Quieres ser mi cita?</title>
    <style>
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
</head>
<body>
    <img id="image" src="imagen1.jpeg" alt="Imagen romántica">
    <h2 id="question">¿Quieres ser mi cita este 14 de febrero?</h2>
    <button class="yes" onclick="sayYes()">Sí</button>
    <button class="no" onclick="sayNo()">No</button>

    <div id="nextStep" style="display: none;">
        <h2>¡Sabía que dirías que sí! ¡Te amo!</h2>
        <button onclick="showAlbum()">A continuación, un álbum de fotos</button>
    </div>

    <div id="albumScreen" style="display: none;">
        <img id="albumImage" src="foto1.jpeg" alt="Álbum de fotos">
        <button id="nextButton" onclick="nextPhoto()">Siguiente</button>
    </div>

    <script>
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
            document.getElementById("image").src = "imagen_final.jpeg"; // Esto solo ocurre al responder "Sí"
            document.getElementById("question").style.display = "none";
            document.querySelector(".yes").style.display = "none";
            document.querySelector(".no").style.display = "none";
            document.getElementById("nextStep").style.display = "block";
        }

        function showAlbum() {
            // Ocultar la pantalla de la pregunta y mostrar el álbum de fotos
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
</body>
</html>
