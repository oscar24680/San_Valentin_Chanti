<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>San Valentín</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            text-align: center;
            color: #333;
            flex-direction: column;
            background-color: #f8d7da;
            background-image: url('https://www.dexerto.com/cdn-image/wp-content/uploads/2024/07/23/Tandemaus-Pokemon-TCG.jpg'); /* Fondo inicial */
            background-size: cover;
            background-position: center;
            transition: background-image 1s ease-in-out;
            overflow: hidden; /* Para evitar scroll cuando la imagen ocupe toda la pantalla */
        }

        h1 {
            font-size: 2em;
            margin-bottom: 20px;
        }

        .options {
            margin: 20px;
        }

        button {
            padding: 10px 20px;
            font-size: 1.2em;
            margin: 10px;
            cursor: pointer;
            border: none;
            background-color: #ff69b4;
            color: white;
            border-radius: 5px;
            transition: all 0.3s;
        }

        button:hover {
            background-color: #ff1493;
        }

        #yes-message {
            display: none;
            font-size: 1.5em;
            color: #db7093;
            position: absolute;
            top: 10%;
            left: 50%;
            transform: translateX(-50%);
            font-weight: bold;
            z-index: 10;
        }

        #yes-message img {
            margin-top: 20px;
            width: 200px;
            border-radius: 10px;
        }

        .hidden {
            display: none;
        }

        #full-screen-image {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            object-fit: cover;
            z-index: -1; /* Para que esté detrás del contenido */
            transition: all 1s ease;
        }

        #message-wrapper {
            display: none;
        }

        #song-background {
            display: none;
        }
    </style>
</head>
<body>

    <h1 id="question-text">¿Quieres ser mi San Valentín?</h1> <!-- Se añadió un id para poder ocultarlo -->
    
    <div class="options">
        <button id="yes-btn">Sí</button>
        <button id="no-btn">No</button>
    </div>

    <div id="yes-message">
        La primera de muchos, mi niña bella ❤️
    </div>

    <div id="message-wrapper">
        <button class="increase-size">Sí</button>
        <img src="https://images5.alphacoders.com/127/1274714.jpg" id="couple-image">
    </div>

    <img src="https://images5.alphacoders.com/127/1274714.jpg" id="full-screen-image" class="hidden">

    
    <script>
        const yesBtn = document.getElementById('yes-btn');
        const noBtn = document.getElementById('no-btn');
        const yesMessage = document.getElementById('yes-message');
        const fullScreenImage = document.getElementById('full-screen-image');
        const song1 = document.getElementById('song1');
        const song2 = document.getElementById('song2');
        const body = document.querySelector('body');
        const questionText = document.getElementById('question-text'); // Elemento de la pregunta
    
        yesBtn.addEventListener('click', () => {
            // Ocultar la pregunta inicial
            questionText.style.display = 'none'; // Ocultar el mensaje "¿Quieres ser mi San Valentín?"
            yesBtn.parentElement.style.display = 'none';

            // Mostrar el mensaje de "La primera de muchos"
            yesMessage.style.display = 'block';

            // Hacer que la imagen se expanda a pantalla completa
            fullScreenImage.classList.remove('hidden');

            // Cambiar fondo de pantalla al seleccionar "Sí"
            body.style.backgroundImage = "url('https://images5.alphacoders.com/127/1274714.jpg')"; // Fondo para el "Sí"

            // Detener la primera canción y comenzar la canción de fondo
            song1.pause();
            song2.play();
            song2.classList.remove('hidden');
        });

        noBtn.addEventListener('click', () => {
            // Ocultar la pregunta inicial
            questionText.style.display = 'none'; // Ocultar el mensaje "¿Quieres ser mi San Valentín?"
            fullScreenImage.classList.add('hidden'); // Ocultar la imagen a pantalla completa
            messageWrapper.classList.remove('hidden');

            // Cambiar fondo de pantalla al seleccionar "No"
            body.style.backgroundImage = "url('https://www.excelsior.com.mx/800x600/filters:format(webp):quality(75)/media/pictures/2024/11/21/3216015.jpg')"; // Fondo para el "No"
        });
        song1.play();
    </script>
    
</body>
</html>

