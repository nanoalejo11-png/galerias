# galerias
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>Galería de Arte — Información Elegante</title>

<!-- TIPOGRAFÍA ELEGANTE -->
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@500;700&family=Inter:wght@300;400;500&display=swap" rel="stylesheet">

<style>
    :root {
        --bg: #f7f7f9;
        --card: #ffffff;
        --primary: #1f4e79;
        --secondary: #6b89a7;
        --shadow: rgba(0,0,0,0.15);
    }

    body {
        font-family: "Inter", sans-serif;
        background: var(--bg);
        margin: 0;
        padding: 40px 20px;
        color: #333;
    }

    h1 {
        text-align: center;
        font-family: "Playfair Display", serif;
        font-size: 42px;
        margin-bottom: 50px;
        color: var(--primary);
        letter-spacing: 1px;
    }

    h2 {
        font-family: "Playfair Display", serif;
        font-size: 30px;
        margin: 50px 0 20px 0;
        color: var(--primary);
        border-left: 5px solid var(--primary);
        padding-left: 12px;
    }

    /* TARJETAS ELEGANTES */
    .gallery {
        max-width: 850px;
        margin: 25px auto;
        background: var(--card);
        padding: 25px;
        border-radius: 18px;
        box-shadow: 0 10px 30px var(--shadow);
        position: relative;
        overflow: hidden;
    }

    /* SLIDER */
    .slides {
        display: flex;
        transition: transform 0.6s ease-in-out;
    }

    .slide {
        min-width: 100%;
        padding: 20px;
        box-sizing: border-box;
    }

    /* CAJAS DE INFORMACIÓN ELEGANTES */
    .info {
        background: #f0f3f7;
        padding: 20px;
        border-radius: 14px;
        line-height: 1.6;
        border-left: 5px solid var(--secondary);
        transition: 0.3s;
    }

    .info:hover {
        background: #e8ecf3;
        transform: translateY(-2px);
    }

    .info h3 {
        margin-top: 0;
        font-family: "Playfair Display", serif;
        color: var(--primary);
    }

    /* BOTONES */
    .btn {
        position: absolute;
        top: 50%;
        transform: translateY(-50%);
        background: var(--primary);
        border: none;
        color: white;
        padding: 12px 16px;
        font-size: 20px;
        cursor: pointer;
        border-radius: 50%;
        box-shadow: 0 5px 15px var(--shadow);
        transition: 0.3s;
    }

    .btn:hover {
        background: #163956;
    }

    .prev { left: 15px; }
    .next { right: 15px; }

</style>
</head>

<body>

<h1>Galería Informativa de Arte</h1>

<!-- =====================================================
                    VAN GOGH
===================================================== -->
<h2>Vincent van Gogh</h2>

<div class="gallery" id="vangogh-gallery">
    <button class="btn prev" onclick="prevSlide('vangogh')">❮</button>
    <button class="btn next" onclick="nextSlide('vangogh')">❯</button>

    <div class="slides" id="vangogh-slides">

        <!-- SLIDE 1 -->
        <div class="slide">
            <div class="info">
                <h3>La noche estrellada (1889)</h3>
                <p><b>Autor:</b> Vincent van Gogh</p>
                <p><b>Lugar actual:</b> Museo de Arte Moderno (MoMA), Nueva York</p>
                <p><b>Técnica:</b> Óleo sobre lienzo</p>
                <p>Una obra maestra emocional, donde Van Gogh expresa turbulencia interior mediante un cielo nocturno vibrante.</p>
            </div>
        </div>

        <!-- SLIDE 2 -->
        <div class="slide">
            <div class="info">
                <h3>Los girasoles (1888)</h3>
                <p><b>Lugar actual:</b> National Gallery, Londres</p>
                <p><b>Técnica:</b> Óleo sobre lienzo</p>
                <p>Parte de una icónica serie donde explora los tonos amarillos para retratar la luz del sur de Francia.</p>
            </div>
        </div>

        <!-- SLIDE 3 -->
        <div class="slide">
            <div class="info">
                <h3>Noche estrellada sobre el Ródano (1888)</h3>
                <p><b>Lugar actual:</b> Museo de Orsay, París</p>
                <p><b>Técnica:</b> Óleo sobre lienzo</p>
                <p>Una contemplativa vista nocturna que mezcla luces artificiales con reflejos naturales del cielo.</p>
            </div>
        </div>

    </div>
</div>

<!-- =====================================================
                    MAGRITTE
===================================================== -->
<h2>René Magritte</h2>

<div class="gallery" id="magritte-gallery">
    <button class="btn prev" onclick="prevSlide('magritte')">❮</button>
    <button class="btn next" onclick="nextSlide('magritte')">❯</button>

    <div class="slides" id="magritte-slides">

        <!-- SLIDE 1 -->
        <div class="slide">
            <div class="info">
                <h3>El hijo del hombre (1964)</h3>
                <p><b>Lugar actual:</b> Colección privada</p>
                <p><b>Técnica:</b> Óleo sobre lienzo</p>
                <p>La icónica figura del bombín cuyo rostro es ocultado por una manzana verde cuestiona la percepción visual.</p>
            </div>
        </div>

        <!-- SLIDE 2 -->
        <div class="slide">
            <div class="info">
                <h3>La traición de las imágenes (1929)</h3>
                <p><b>Lugar actual:</b> LACMA, Los Ángeles</p>
                <p><b>Técnica:</b> Óleo sobre lienzo</p>
                <p>“Esto no es una pipa” desafía la relación entre lenguaje, objeto y representación.</p>
            </div>
        </div>

        <!-- SLIDE 3 -->
        <div class="slide">
            <div class="info">
                <h3>Los amantes (1928)</h3>
                <p><b>Lugar actual:</b> MoMA, Nueva York</p>
                <p><b>Técnica:</b> Óleo sobre lienzo</p>
                <p>Dramática escena donde dos personas se besan con el rostro cubierto, simbolizando el misterio y la distancia emocional.</p>
            </div>
        </div>

    </div>
</div>

<script>
/* ÍNDICES DE SLIDES */
const index = { vangogh: 0, magritte: 0 };

function showSlide(artist) {
    const slides = document.getElementById(artist + "-slides");
    slides.style.transform = `translateX(-${index[artist] * 100}%)`;
}

function nextSlide(artist) {
    const total = document.getElementById(artist + "-slides").children.length;
    index[artist] = (index[artist] + 1) % total;
    showSlide(artist);
}

function prevSlide(artist) {
    const total = document.getElementById(artist + "-slides").children.length;
    index[artist] = (index[artist] - 1 + total) % total;
    showSlide(artist);
}
</script>

</body>
</html>
