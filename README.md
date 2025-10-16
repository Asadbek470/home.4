# home
home ai
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>OpenXI Community Center | Home AI</title>
    <link href="https://fonts.googleapis.com/css2?family=Electrolize&display=swap" rel="stylesheet">
    
    <style>
        /* === 1. Стилизация заднего фона (Матрица) === */
        #matrixRain {
            position: fixed;
            inset: 0;
            z-index: -2; 
            background: black;
        }

        /* === 2. Основные стили страницы и текста === */
        body {
            font-family: 'Electrolize', Arial, sans-serif;
            color: #00ff41; 
            background-color: transparent; 
            line-height: 1.6;
            margin: 0;
            padding: 20px;
            position: relative;
            z-index: 1;
        }

        /* Общие стили для контента, чтобы он был читабелен */
        .content-section {
            background-color: rgba(0, 0, 0, 0.85); 
            padding: 30px;
            margin: 20px auto;
            max-width: 900px;
            border-radius: 10px;
            box-shadow: 0 0 20px rgba(0, 255, 65, 0.5); 
            border: 1px solid #00ff41;
        }

        /* Улучшенный заголовок */
        h1, h2 {
            text-align: center;
            color: #39ff14; 
            text-shadow: 0 0 10px #39ff14; 
            margin-bottom: 20px;
            text-transform: uppercase;
        }
        /* Стиль для главного текста (параграфы) */
        p {
            text-align: justify;
            margin-bottom: 15px;
            font-size: 1.1em; 
            padding: 0 10px;
        }
        strong {
            color: #ffffff; 
            text-shadow: 0 0 5px #ffffff;
        }
        
        /* Стили для валюты Эски */
        .eski-currency {
            color: #ff9900; 
            text-shadow: 0 0 8px #ff9900, 0 0 15px rgba(255, 153, 0, 0.5); 
            font-weight: bold;
            letter-spacing: 1px;
            font-size: 1.1em;
        }
        
        /* Стиль для изображения */
        .center-img {
            display: block;
            margin: 0 auto 30px; 
            border: 3px solid #00ff41;
            box-shadow: 0 0 15px rgba(0, 255, 65, 0.8);
            border-radius: 8px;
            opacity: 0.9;
        }

        /* Стили для ИНСТРУКЦИИ */
        .alliance-header {
            color: #00ffff; 
            text-shadow: 0 0 12px #00ffff;
        }
        .step-list {
            text-align: left;
            margin: 20px auto;
            max-width: 600px;
            list-style-type: none;
            padding-left: 0;
        }
        .step-list li {
            background-color: rgba(0, 0, 0, 0.7);
            border: 1px solid #00ffff;
            padding: 15px;
            margin-bottom: 10px;
            border-radius: 5px;
            font-size: 1.1em;
            color: #fff;
        }
        .step-number {
            color: #00ffff;
            font-weight: bold;
            margin-right: 10px;
            text-shadow: 0 0 5px #00ffff;
        }
        
        /* === НОВЫЙ СТИЛЬ: ЗАКОНЫ И ПРАВИЛА === */
        .laws-section h2 {
            color: #ff0000; /* Красное свечение для предупреждения */
            text-shadow: 0 0 15px #ff0000;
        }
        .laws-list {
            list-style-type: none;
            padding: 0;
            text-align: left;
            margin: 0 auto;
            max-width: 750px;
        }
        .laws-list li {
            margin-bottom: 12px;
            padding-left: 20px;
            position: relative;
            font-size: 1.05em;
        }
        .laws-list li::before {
            content: "█"; /* Футуристический маркер */
            color: #ff0000;
            font-weight: bold;
            display: inline-block;
            width: 1em;
            margin-left: -1em;
            text-shadow: 0 0 5px #ff0000;
        }
        .critical-warning {
            color: #ff0000;
            font-weight: bold;
            text-shadow: 0 0 7px #ff0000;
        }

        /* === 3. Стилизация кнопок и футера === */
        .button-group {
            text-align: center;
            margin: 30px 0;
        }

        button {
            background-color: #000;
            color: #00ff41;
            border: 2px solid #00ff41;
            padding: 10px 20px;
            margin: 5px;
            border-radius: 5px;
            cursor: pointer;
            text-transform: uppercase;
            font-weight: bold;
            transition: background-color 0.3s, box-shadow 0.3s;
        }

        button:hover {
            background-color: #00ff41;
            color: #000;
            box-shadow: 0 0 15px #00ff41;
        }

        button a {
            text-decoration: none;
            color: inherit; 
        }

        footer {
            text-align: center;
            padding: 20px;
            margin-top: 40px;
            border-top: 1px dashed #00ff41;
            font-size: 0.9em;
            color: #00cc00;
        }
    </style>
</head>
<body>

    <canvas id="matrixRain"></canvas>

    <div class="content-section">
        <h1>Добро пожаловать в</h1>
        <h1><span style="color: #39ff14; font-size: 2em; letter-spacing: 5px;">OPENXI Community Center</span></h1>
    </div>

    <div class="content-section">
        <img src="https://optim.tildacdn.com/tild3662-3738-4462-b738-333430386539/-/resize/824x/-/format/webp/e362c0d0-1b30-490f-a.jpg.webp" alt="Логотип или Изображение OpenXI" class="center-img" width="300" height="200">
        
        <h2>✨ Что такое OpenXI</h2>
        <p>...</p>
        <h2>ℹ️ Информация о сайте и Экосистема</h2>
        <p>...</p>
        <ul style="text-align: left; max-width: 600px; margin: 20px auto; list-style-type: '» '; color: #00ff41;">
            <li><strong style="color: #fff;">Решение</strong> уравнений, неравенств, систем и других математических задач.</li>
            <li><strong style="color: #fff;">Пошаговое объяснение</strong> решений для глубокого понимания.</li>
            <li><strong style="color: #fff;">Построение графиков</strong> функций с высокой точностью.</li>
            <li>Обучающие модули и интерактивные примеры.</li>
            <li>Поддержку **алгебры, геометрии, тригонометрии, анализа** и других разделов математики.</li>
        </ul>

        <h2 style="color: #ff9900; text-shadow: 0 0 10px #ff9900;">🔥 Виртуальная Валюта: Эски</h2>
        <p style="text-align: center;">
            В экосистеме OpenXI действует внутренняя виртуальная валюта, которая называется **<span class="eski-currency">Эски</span>**.
        </p>
        <p>
            **<span class="eski-currency">Эски</span>** (<span class="eski-currency">Eski</span>) — это **цифровые токены**, которые можно зарабатывать за активное участие, решение сложных задач, помощь другим пользователям и вклад в развитие сообщества. Валюта используется для:
            <ul style="text-align: left; max-width: 600px; margin: 20px auto; list-style-type: '⚡ '; color: #ff9900;">
                <li>Получения **премиум-доступа** к расширенным функциям и инструментам.</li>
                <li>Разблокировки **новых обучающих модулей**.</li>
                <li>Покупки **уникальных тем** и оформления профиля.</li>
            </ul>
            **<span class="eski-currency">Эски</span>** стимулируют обучение и взаимодействие, делая OpenXI не просто помощником, а настоящим сообществом.
        </p>
        
        <div class="laws-section">
            <h2 class="critical-warning">📜 КРИПТОГРАФИЧЕСКИЙ ПРОТОКОЛ БЕЗОПАСНОСТИ И ПРАВИЛА СООБЩЕСТВА</h2>
            <p style="text-align: center; color: #ff0000; font-weight: bold; text-shadow: none;">
                ВНИМАНИЕ! Нарушение любого из перечисленных ниже пунктов приведет к **АВТОМАТИЧЕСКОМУ АННУЛИРОВАНИЮ ДОСТУПА**.
            </p>

            <ul class="laws-list">
                <li><strong style="color: #00ff41;">1.0 ЧЕСТНОЕ ИСПОЛЬЗОВАНИЕ:</strong> Каждый пользователь обязуется использовать мои игры, сайты и браузеры честно и по правилам.</li>
                <li><strong class="critical-warning">1.1 ВЗЛОМ СИСТЕМЫ:</strong> Запрещается пытаться взломать систему, изменять код или обходить защиту.</li>
                <li><strong class="critical-warning">1.2 НЕДОПУСТИМОСТЬ ЧИТОВ:</strong> Запрещается использовать читы, баги или уязвимости для получения преимуществ.</li>
                <li><strong style="color: #00ff41;">1.3 УВАЖЕНИЕ:</strong> Пользователь обязуется уважать других игроков и пользователей.</li>
                <li><strong style="color: #00ff41;">1.4 ЗАКОННЫЕ ЦЕЛИ:</strong> Все данные, размещённые в моих сервисах, должны использоваться только в законных целях.</li>

                <li><strong class="critical-warning">2.0 ПОПЫТКА ВЗЛОМА:</strong> Любая попытка взлома приведёт к **автоматической блокировке доступа**.</li>
                <li><strong class="critical-warning">2.1 ЗАМОРОЗКА АККАУНТА:</strong> Если пользователь нарушил правила, его аккаунт может быть **заморожен**.</li>
                <li><strong class="critical-warning">2.2 ПОДОЗРИТЕЛЬНАЯ АКТИВНОСТЬ:</strong> При подозрительной активности система автоматически ограничивает вход.</li>
                <li><strong class="critical-warning">2.3 БОТ-АТАКИ:</strong> Попытки использовать ботов для атаки приведут к **пожизненной блокировке**.</li>

                <li><strong style="color: #00ff41;">3.0 АВТОРСКИЕ ПРАВА:</strong> Все игры, сайты и браузеры защищены авторскими правами.</li>
                <li><strong class="critical-warning">3.1 КОПИРОВАНИЕ:</strong> Копировать или распространять их без разрешения **запрещено**.</li>
                <li><strong class="critical-warning">3.2 МОДИФИКАЦИИ:</strong> Любые модификации без моего разрешения **запрещены**.</li>
                <li><strong class="critical-warning">3.3 ПОТЕРЯ ДОСТУПА:</strong> Нарушители теряют доступ к сервисам.</li>

                <li><strong class="critical-warning">4.0 ОГРАНИЧЕНИЕ ДОСТУПА:</strong> При нарушении правил доступ автоматически ограничивается.</li>
                <li><strong class="critical-warning">4.1 СООБЩЕНИЕ ОБ ОШИБКЕ:</strong> Нарушителю сайт или игра могут отображать сообщение: «Доступ запрещён».</li>
                <li><strong class="critical-warning">4.2 БЛОКИРОВКА УСТРОЙСТВА:</strong> Повторные попытки входа могут привести к полной блокировке устройства.</li>
                <li><strong style="color: #00ff41;">4.3 СНЯТИЕ БЛОКИРОВКИ:</strong> Снятие блокировки возможно только через моё разрешение.</li>

                <li><strong style="color: #00ff41;">5.0 ЛИЧНАЯ ОТВЕТСТВЕННОСТЬ:</strong> Пользователь несёт личную ответственность за свои действия.</li>
                <li><strong style="color: #00ff41;">5.1 ВЗЛОМ АККАУНТА:</strong> Я не несу ответственность за взломанные аккаунты по вине самого пользователя.</li>
                <li><strong class="critical-warning">5.2 ЧУЖИЕ ДАННЫЕ:</strong> Использование чужих данных (логинов, паролей) **запрещено**.</li>
                <li><strong style="color: #00ff41;">5.3 БЕЗОПАСНОСТЬ:</strong> Пользователь обязан хранить свои данные в безопасности.</li>
                <li><strong style="color: #00ff41;">5.4 ФИКСАЦИЯ НАРУШЕНИЙ:</strong> Серьёзные нарушения фиксируются в базе и сохраняются.</li>
                <li><strong class="critical-warning">5.5 "ЧЕРНЫЙ СПИСОК":</strong> Нарушители заносятся в **«чёрный список»** и больше не смогут пользоваться моими сервисами.</li>
                
                <li style="margin-top: 20px;"><strong class="critical-warning" style="font-size: 1.2em;">6.0 КРИТИЧЕСКИЙ ДОСТУП:</strong> Доступ к страницам **Hacking 2** и **About Me** разрешён **только владельцу**. Если чужой пользователь попытается войти или нажать кнопку **«Сделать хакерскую атаку»**, его аккаунт будет **заморожен пожизненно**.</li>
            </ul>
        </div>
        
        <p style="text-align: center;">
            <strong style="color: #00ff41;">📘 Миссия OpenXI</strong> — сделать математику доступной, понятной и увлекательной для всех.
        </p>
        <h2 style="margin-top: 0;">🚀 Слоган: «Математика — это просто, когда рядом OpenXI.»</h2>
    </div>
    
    <div class="content-section">
        <h2 class="alliance-header">🤝 Как стать Союзником OpenXI</h2>
        <p style="text-align: center;">
            Присоединяйтесь к нашей миссии и получите **прямой канал связи** с Владельцем сайта. Следуйте этому **Протоколу Активации Союзника**.
        </p>
        
        <ol class="step-list">
            <li>
                <span class="step-number">ПРОТОКОЛ 01:</span>
                Перейдите на наш основной ресурс — **Искусственный Интеллект по математике** (OpenXI.uz).
            </li>
            <li>
                <span class="step-number">ПРОТОКОЛ 02:</span>
                Прокрутите страницу до самого конца. В футере вы найдете скрытый элемент управления — кнопку **"Admin Pass"**.
            </li>
            <li>
                <span class="step-number">ПРОТОКОЛ 03:</span>
                Нажмите на **"Admin Pass"**. Система выведет на экран **Соглашение о сотрудничестве**. Ознакомьтесь с условиями.
            </li>
            <li>
                <span class="step-number">ПРОТОКОЛ 04:</span>
                После прохождения всех соглашений и активации, появится специальная кнопка **"Связь с Владельцем"**. Нажмите на нее, чтобы установить прямую связь через **WhatsApp** и завершить процедуру.
            </li>
        </ol>
    </div>

    <div class="content-section">
        <h2>Мои популярные проекты</h2>
        <p style="text-align: center;">Это дом всех моих веб-сайтов.</p>
        
        <ol>
            <li>OpenXi.uz</li>
            <li>Game random</li>
            <li>Hacking2</li>
            <li>My brouser3</li>
            <li>About-Me</li>
            <li>OpenXi.ru</li>
        </ol>
        
        <div class="button-group">
            <button><a href="https://asadbek470.github.io/ChatXI.uz/">OpenXi.uz</a></button>
            <button><a href="https://asadbek470.github.io/random-game5.3/">Random Game</a></button>
            <button><a href="https://asadbek470.github.io/Hacking2.3.5/">Hacking2</a></button>
            <button><a href="https://asadbek470.github.io/my-brouser3/"> My Brouser3</a></button>
            <button><a href="https://asadbek470.github.io/About-Me1./">About-Me</a></button>
            <button><a href="https://asadbek470.github.io/OpenXI.ru2/">OpenXi.ru</a></button>
        </div>
    </div>
    
    <footer>
        <p>Thank you for visiting my web site! Powered by AI and a passion for mathematics. [Code Status: OK]</p>
    </footer>

    <script>
        const canvas = document.getElementById('matrixRain');
        const ctx = canvas.getContext('2d');

        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;

        const letters = '01ABCDEFGHIJKLMNOPQRSTUVWXYZабвгдежзийклмнопрстуфхцчшщъыьэюя';
        const fontSize = 16;
        const columns = Math.floor(canvas.width / fontSize);
        const drops = Array.from({ length: columns }, () => 1);

        function draw() {
            ctx.fillStyle = 'rgba(0, 0, 0, 0.1)'; 
            ctx.fillRect(0, 0, canvas.width, canvas.height);

            ctx.fillStyle = '#0F0';
            ctx.font = `${fontSize}px monospace`;

            for (let i = 0; i < drops.length; i++) {
                const text = letters[Math.floor(Math.random() * letters.length)];
                ctx.fillText(text, i * fontSize, drops[i] * fontSize);

                if (drops[i] * fontSize > canvas.height && Math.random() > 0.98) {
                    drops[i] = 0;
                }
                drops[i]++;
            }
        }

        setInterval(draw, 33);

        window.addEventListener('resize', () => {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        });
    </script>
</body>
</html>
