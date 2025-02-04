# cielo
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
    <img id="image" src="imagen1.jpg" alt="Imagen romántica">
    <h2 id="question">¿Quieres ser mi cita este 14 de febrero?</h2>
    <button class="yes" onclick="sayYes()">Sí</button>
    <button class="no" onclick="sayNo()">No</button>

    <script>
        let noClickCount = 0;
        const images = ["imagen1.jpg", "imagen2.jpg", "imagen3.jpg"];

        function sayNo() {
            noClickCount++;
            document.getElementById("image").src = images[noClickCount % images.length];
        }

        function sayYes() {
            document.getElementById("image").src = "imagen_final.jpg";
            document.getElementById("question").innerText = "Muchas gracias! Sabía que ibas a decir que sí. ¡Te amo!";
            document.querySelector(".yes").style.display = "none";
            document.querySelector(".no").style.display = "none";
        }
    </script>
</body>
</html>
