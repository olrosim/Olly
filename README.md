<!DOCTYPE html>
<html>
<head>
    <title>Мое второе портфолио</title>
    <!-- Важно: эта строчка заставляет сайт правильно сжиматься на телефонах -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        /* Общие стили для всего сайта */
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            background-color: #f5f5f5;
        }

        h1 {
            color: #333;
            text-align: center;
        }

        h2 {
            color: #555;
            margin-top: 30px;
        }

        p {
            line-height: 1.6;
            color: #666;
        }

        a {
            color: #0066cc;
            text-decoration: none;
        }

        a:hover {
            text-decoration: underline;
        }

        /* КОНТЕЙНЕР ДЛЯ КАРТИНОК */
        .gallery {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 20px; /* Расстояние между картинками */
            margin: 30px 0;
        }

        /* СТИЛИ ДЛЯ КАЖДОЙ КАРТИНКИ */
        .gallery img {
            /* По умолчанию для компьютера */
            width: 300px;
            height: auto;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.2);
            transition: transform 0.3s ease;
            cursor: pointer;
        }

        /* Эффект при наведении на картинку (только на компьютере) */
        .gallery img:hover {
            transform: scale(1.05);
        }

        /* МОДАЛЬНОЕ ОКНО (для просмотра в полный размер) */
        .modal {
            display: none;
            position: fixed;
            z-index: 1000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0,0,0,0.9);
            text-align: center;
        }

        .modal-content {
            margin: auto;
            display: block;
            max-width: 90%;
            max-height: 90%;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
        }

        .close {
            position: absolute;
            top: 15px;
            right: 35px;
            color: #f1f1f1;
            font-size: 40px;
            font-weight: bold;
            cursor: pointer;
        }

        .close:hover {
            color: #bbb;
        }

        /* ===================================== */
        /* АДАПТАЦИЯ ДЛЯ ТЕЛЕФОНОВ              */
        /* ===================================== */
        @media screen and (max-width: 600px) {
            body {
                margin: 10px;
            }

            h1 {
                font-size: 24px;
            }

            .gallery {
                gap: 10px;
            }

            .gallery img {
                width: 100%; /* На телефоне картинка на всю ширину */
                max-width: 100%;
                margin: 0;
            }

            /* На телефоне убираем эффект увеличения при наведении (его там нет) */
            .gallery img:hover {
                transform: none;
            }
        }

        /* ДЛЯ ПЛАНШЕТОВ */
        @media screen and (min-width: 601px) and (max-width: 1024px) {
            .gallery img {
                width: 45%; /* На планшете по 2 картинки в ряд */
            }
        }
    </style>
</head>
<body>

    <h1>Привет! Это мой новый сайт</h1>
    <p>Здесь будет мое второе портфолио.</p>

    <h2>Мои работы</h2>

    <!-- Галерея с картинками -->
    <div class="gallery">
        <img src="61fl090vkuk91.webp" alt="Работа 1" onclick="openModal(this)">
        <img src="7qro3xzukuk91.webp" alt="Работа 2" onclick="openModal(this)">
        <img src="943ko30vkuk91.webp" alt="Работа 3" onclick="openModal(this)">
        <img src="ebsthwzukuk91.webp" alt="Работа 4" onclick="openModal(this)">
        <img src="gbb9gf0vkuk91.webp" alt="Работа 5" onclick="openModal(this)">
        <img src="i6gohc0vkuk91.webp" alt="Работа 6" onclick="openModal(this)">
        <img src="jtwnya0vkuk91.webp" alt="Работа 7" onclick="openModal(this)">
        <img src="uz36vb0vkuk91.webp" alt="Работа 8" onclick="openModal(this)">
    </div>

   

    <!-- Модальное окно для просмотра в полный размер -->
    <div id="myModal" class="modal" onclick="closeModalOnClick(event)">
        <span class="close" onclick="closeModal()">&times;</span>
        <img class="modal-content" id="modalImg">
    </div>

    <!-- Скрипт для открытия картинок в полный размер -->
    <script>
        var modal = document.getElementById('myModal');
        var modalImg = document.getElementById('modalImg');

        function openModal(img) {
            modal.style.display = "block";
            modalImg.src = img.src;
        }

        function closeModal() {
            modal.style.display = "none";
        }

        function closeModalOnClick(event) {
            if (event.target === modal) {
                closeModal();
            }
        }

        // Закрытие по клавише ESC
        document.addEventListener('keydown', function(e) {
            if (e.key === 'Escape') {
                closeModal();
            }
        });
    </script>

</body>
</html>
