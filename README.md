<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Seleccionar Temporada</title>
    <style>
        body {
            background-color: #000;
            color: #fff;
            text-align: center;
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
        }

        .image-container {
            width: 100%;
            max-width: 1200px;
            margin: 20px auto;
            overflow: hidden;
            border-radius: 15px;
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.5);
        }

        .image-container img {
            width: 100%;
            height: auto;
            transition: transform 0.5s ease, filter 0.5s ease;
            filter: brightness(80%);
        }

        .image-container:hover img {
            transform: scale(1.05);
            filter: brightness(100%);
        }

        .temporadas {
            margin-top: 40px;
        }

        .season-btn {
            background-color: #fff;
            color: #000;
            padding: 15px 30px;
            border: none;
            border-radius: 12px;
            font-size: 20px;
            cursor: pointer;
            margin: 10px;
            transition: background-color 0.3s ease, transform 0.3s ease, box-shadow 0.3s ease;
            box-shadow: 0 0 10px rgba(255, 255, 255, 0.3), 0 0 30px rgba(255, 255, 255, 0.1);
        }

        .season-btn:hover {
            background-color: #f0f0f0;
            transform: scale(1.05);
            box-shadow: 0 0 15px rgba(255, 255, 255, 0.5), 0 0 40px rgba(255, 255, 255, 0.3);
        }

        .chapter-list {
            display: none;
            margin-top: 10px;
            text-align: left;
            background-color: #fff;
            color: #000;
            padding: 10px;
            border-radius: 8px;
            box-shadow: 0px 8px 16px rgba(0, 0, 0, 0.4);
            position: relative;
            overflow: hidden;
        }

        .chapter-list ul {
            list-style: none;
            padding: 0;
            margin: 0;
        }

        .chapter-list li {
            padding: 10px 15px;
            border-bottom: 1px solid #ddd;
            font-size: 16px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .chapter-list li:last-child {
            border-bottom: none;
        }

        .chapter-list li a {
            text-decoration: none;
            color: #000;
            font-weight: bold;
        }

        .chapter-list li a:hover {
            color: #007BFF;
            text-shadow: 0 0 10px rgba(0, 123, 255, 0.8);
        }

        .chapter-list.show {
            display: block;
            animation: fadeIn 0.5s ease forwards;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: scale(0.95);
            }
            to {
                opacity: 1;
                transform: scale(1);
            }
        }

        .emoji {
            position: absolute;
            font-size: 36px;
            animation: float 1s forwards;
            pointer-events: none;
            opacity: 1;
        }

        @keyframes float {
            0% {
                transform: translateY(-50px);
                opacity: 1;
            }
            100% {
                transform: translateY(0);
                opacity: 0;
            }
        }
    </style>
    <script>
        function toggleChapters(id) {
            const chapterList = document.getElementById(id);
            chapterList.classList.toggle('show');

            if (chapterList.classList.contains('show')) {
                createEmojis(chapterList);
            }
        }

        function createEmojis(chapterList) {
            const numberOfEmojis = 5;
            const emojis = ['🦸‍♂️', '🦹'];
            for (let i = 0; i < numberOfEmojis; i++) {
                const emoji = document.createElement('div');
                emoji.classList.add('emoji');
                emoji.textContent = emojis[Math.floor(Math.random() * emojis.length)];
                emoji.style.left = Math.random() * (chapterList.clientWidth - 40) + 'px';
                emoji.style.top = Math.random() * (chapterList.clientHeight - 40) + 'px';
                chapterList.appendChild(emoji);
                
                emoji.addEventListener('animationend', () => {
                    emoji.remove();
                });
            }
        }

        function redirectTo(url) {
            window.open(url, '_blank'); 
        }
    </script>
</head> 
<body>
    <div class="image-container">
        <img src="https://pbs.twimg.com/media/FEe_meRVQAk1LKp.jpg" alt="Imagen de la serie">
    </div>

    <div class="temporadas">
        <button class="season-btn" onclick="redirectTo('https://drive.google.com/drive/folders/1HRytDRyVn2E4KgTuImeg98HQ2M64EN0h?usp=drive_link')">Temporada 1</button>
        <button class="season-btn" onclick="redirectTo('https://drive.google.com/drive/folders/1SYmyCuusGK2wLvra0daRplwRCpH5uEx5?usp=drive_link')">Temporada 2</button>
        <button class="season-btn" onclick="redirectTo('https://drive.google.com/drive/folders/1yYYqZzbjMsc4lJpOy6AuWDVaVBJ3mZEP?usp=drive_link')">Temporada 3</button>
        <button class="season-btn" onclick="redirectTo('https://drive.google.com/drive/folders/11ZzEP8OUKL-8GPmUWBTgzz0J2Z22tSXm?usp=drive_link')">Temporada 4</button>
    </div>
</body>
</html>
