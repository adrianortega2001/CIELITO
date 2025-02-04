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

    <div id="album" style="display: none;">
        <img id="albumImage" src="foto1.jpeg" alt="Álbum de fotos">
        <button id="nextButton" onclick="nextPhoto()">Siguiente</button>
        <h2 id="finalMessage" style="display: none;">¡Gracias por ver el álbum!</h2>
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
            document.getElementById("image").src = "imagen_final.jpeg";  // Imagen final permanece
            document.getElementById("question").style.display = "none";
            document.querySelector(".yes").style.display = "none";
            document.querySelector(".no").style.display = "none";
            document.getElementById("nextStep").style.display = "block";
        }

        function showAlbum() {
            document.getElementById("albumImage").src = albumImages[photoIndex];
            document.getElementById("nextStep").style.display = "none";
            document.getElementById("album").style.display = "block";
            document.getElementById("finalMessage").style.display = "none";  // Ocultar mensaje final
        }

        function nextPhoto() {
            photoIndex++;
            if (photoIndex < albumImages.length) {
                document.getElementById("albumImage").src = albumImages[photoIndex];
            }
            if (photoIndex === albumImages.length - 1) {
                document.getElementById("nextButton").style.display = "none"; // Ocultar el botón al final
                document.getElementById("finalMessage").style.display = "block"; // Mostrar mensaje final
            }
        }
    </script>
</body>
</html>
