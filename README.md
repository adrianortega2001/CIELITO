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
        document.getElementById("image").src = "imagen_final.jpeg";  // Imagen final solo después de "Sí"
        document.getElementById("question").style.display = "none";
        document.querySelector(".yes").style.display = "none";
        document.querySelector(".no").style.display = "none";
        document.getElementById("nextStep").style.display = "block";
    }

    function showAlbum() {
        document.getElementById("nextStep").style.display = "none";
        document.getElementById("album").style.display = "block";
        document.getElementById("albumImage").src = albumImages[photoIndex];
    }

    function nextPhoto() {
        photoIndex++;
        if (photoIndex < albumImages.length) {
            document.getElementById("albumImage").src = albumImages[photoIndex];
        }
        if (photoIndex === albumImages.length - 1) {
            document.getElementById("nextButton").style.display = "none";
            document.getElementById("finalMessage").style.display = "block";
        }
    }
</script>
