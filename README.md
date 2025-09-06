# home
home ai
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document of game random</title>
  <style>
    :root {
      --bg: #0b0c10;
      --card: #111217;
      --accent: #e63946;
      --text: #e6e6e6;
    }
    html,body { height:100%; margin:0; font-family: Inter, Roboto, Arial, sans-serif; background:var(--bg); color:var(--text); }
    #blocker {
      position:fixed; inset:0; z-index:99999;
      display:flex; align-items:center; justify-content:center;
      background:linear-gradient(180deg, rgba(0,0,0,0.75), rgba(0,0,0,0.85));
      backdrop-filter: blur(4px);
    }
    .panel {
      width:min(920px, 96%);
      background:linear-gradient(180deg, rgba(17,18,23,0.95), rgba(14,15,18,0.98));
      padding:28px; border-radius:12px; box-shadow:0 10px 40px rgba(0,0,0,0.6);
      border:1px solid rgba(255,255,255,0.03);
    }
    h1 { margin:0 0 10px 0; font-size:24px; color:var(--accent); }
    p { margin:0 0 14px 0; line-height:1.45; color:var(--text); opacity:0.95; }
    hr { border:0; height:1px; background:rgba(255,255,255,0.03); margin:14px 0; }
    .small { font-size:13px; opacity:0.8; }
    .controls { display:flex; flex-direction:column; gap:10px; margin-top:14px; }
    input[type="password"], input[type="text"]{
      padding:10px 12px; border-radius:8px;
      border:1px solid rgba(255,255,255,0.06);
      background:transparent; color:var(--text);
      outline:none; min-width:220px;
    }
    button { padding:10px 14px; border-radius:8px; border:0; cursor:pointer; background:var(--accent); color:white; font-weight:600; }
    button.ghost { background:transparent; border:1px solid rgba(255,255,255,0.06); color:var(--text); }
    .note { margin-top:10px; font-size:13px; opacity:0.8; }
    #site-content { filter:blur(2px) grayscale(0.3); pointer-events:none; user-select:none; }
  </style>
</head>
<body>
  <div id="site-content" aria-hidden="true">
    <h2 style="padding:20px; color: #ddd;">Твой сайт (скрыт пока)</h2>
    <p style="padding:0 20px 40px 20px; color:#bbb;">Когда блок будет снят — пользователь увидит этот контент.</p>
  </div>

  <div id="blocker" role="alertdialog" aria-modal="true">
    <div class="panel" role="document">
      <h1>🚫 Доступ временно ограничен</h1>
      <p><strong>Правило:</strong> в соответствии с правилами сайта — доступ закрыт для всех посетителей.</p>
      <hr>
      <p class="small">Введите секретный код и подтвердите, что вы человек:</p>

      <!-- CAPTCHA -->
      <div class="controls">
        <p id="captchaText"></p>
        <input id="captchaAnswer" type="text" placeholder="Решите пример" />
        <input id="secret" type="password" placeholder="Введите секретный код" autocomplete="off" />
        <button id="unlock">Разблокировать</button>
        <button id="forceBan" class="ghost">Заблокировать навсегда (для этого браузера)</button>
      </div>

      <p class="note" id="msg" aria-live="polite"></p>
    </div>
  </div>

  <script>
    (function(){
      const OWNER_SECRET = "ASADBKantiban";
      const STORAGE_KEY = "site_banned_all";
      const storage = localStorage;

      const blocker = document.getElementById('blocker');
      const secretInput = document.getElementById('secret');
      const captchaText = document.getElementById('captchaText');
      const captchaAnswer = document.getElementById('captchaAnswer');
      const unlockBtn = document.getElementById('unlock');
      const forceBanBtn = document.getElementById('forceBan');
      const msg = document.getElementById('msg');
      const siteContent = document.getElementById('site-content');

      let captchaCorrect = 0;

      function generateCaptcha(){
        let a = Math.floor(Math.random()*10+1);
        let b = Math.floor(Math.random()*10+1);
        captchaCorrect = a + b;
        captchaText.textContent = `Докажите, что вы человек: ${a} + ${b} = ?`;
      }

      function showMessage(text, ok=false) {
        msg.textContent = text;
        msg.style.color = ok ? '#9be15d' : '#f66';
      }

      function applyBlock() {
        blocker.style.display = 'flex';
        siteContent.setAttribute('aria-hidden','true');
        siteContent.style.pointerEvents = 'none';
        generateCaptcha();
      }

      function removeBlock() {
        blocker.style.display = 'none';
        siteContent.removeAttribute('aria-hidden');
        siteContent.style.pointerEvents = '';
        showMessage('', true);
      }

      function isBanned() {
        return storage.getItem(STORAGE_KEY) === "true";
      }

      if (isBanned()) {
        applyBlock();
        showMessage('Этот браузер заблокирован навсегда.', false);
      } else {
        applyBlock();
        showMessage('Введите секретный код для входа.', false);
      }

      unlockBtn.addEventListener('click', function(){
        const val = secretInput.value || '';
        const captchaVal = parseInt(captchaAnswer.value,10);

        if(captchaVal !== captchaCorrect){
          showMessage('⚠ Неверно решена CAPTCHA.', false);
          generateCaptcha();
          captchaAnswer.value='';
          return;
        }

        if (val === OWNER_SECRET) {
          sessionStorage.setItem('site_owner_unlocked', 'true');
          removeBlock();
          showMessage('✔ Сайт разблокирован (сессия).', true);
        } else {
          showMessage('❌ Неверный код.', false);
          secretInput.value = '';
        }
      });

      forceBanBtn.addEventListener('click', function(){
        storage.setItem(STORAGE_KEY, 'true');
        applyBlock();
        showMessage('🚫 Этот браузер заблокирован навсегда.', false);
      });

      if (sessionStorage.getItem('site_owner_unlocked') === 'true' && !isBanned()) {
        removeBlock();
      }
    })();
  </script>
  <style>
    body {
      background-color: #ffffff;
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 20px;
      text-align: center;
    }

    h1 {
      border: 2px solid #000;
      padding: 10px;
      background: linear-gradient(145deg, #f0f0f0, #d9d9d9);
      box-shadow: 5px 5px 15px rgba(0,0,0,0.3),
                  -5px -5px 15px rgba(255,255,255,0.8);
      border-radius: 10px;
      display: inline-block;
      transform: perspective(500px) rotateX(5deg);
    }

    img {
      border-radius: 15px;
      box-shadow: 0 10px 20px rgba(0,0,0,0.4);
      transition: transform 0.3s ease;
    }
    img:hover {
      transform: scale(1.05) rotateY(5deg);
    }

    p {
      font-size: 20px;
      color: rgb(80, 80, 80);
      text-shadow: 1px 1px 2px rgba(0,0,0,0.2);
    }

    div {
      background-color: rgb(0, 0, 0);
      padding: 15px;
      border-radius: 10px;
      box-shadow: inset 3px 3px 10px rgba(255,255,255,0.2),
                  inset -3px -3px 10px rgba(0,0,0,0.7);
    }
    div p {
      color: rgb(200, 200, 200);
      margin: 0;
    }

    ol {
      text-align: left;
      display: inline-block;
      padding: 20px;
      background: #f9f9f9;
      border-radius: 10px;
      box-shadow: 4px 4px 15px rgba(0,0,0,0.3),
                  -4px -4px 15px rgba(255,255,255,0.6);
    }

    button {
      margin: 10px;
      padding: 10px 20px;
      border: none;
      border-radius: 12px;
      background: linear-gradient(145deg, #00c6ff, #0072ff);
      color: white;
      font-weight: bold;
      font-size: 14px;
      cursor: pointer;
      box-shadow: 5px 5px 15px rgba(0,0,0,0.4),
                  -3px -3px 10px rgba(255,255,255,0.3);
      transition: transform 0.2s ease, box-shadow 0.3s ease;
    }
    button:hover {
      transform: scale(1.05) translateY(-2px);
      box-shadow: 8px 8px 20px rgba(0,0,0,0.5),
                  -5px -5px 15px rgba(255,255,255,0.4);
    }
    button a {
      text-decoration: none;
      color: white;
    }
  </style>
</head>
<body>
  <h1>Welcome</h1>
  <br>
  <img src="https://moya-planeta.ru/upload/images/xl/85/ec/85ec639804ea05eb0d5bf4e6793c540e5951d508.jpg" alt="a"> 
  <br><br>
  <h1 style="color: rgb(0, 0, 0);">Welcome</h1> 
  <br>
  <p>This is a my web site home.</p>
  <div> 
   <p>This is home of my web sites</p>
  </div>
  <p>My popular projects</p>
  <ol>
    <li>Game random</li>
    <li>OpenXi.uz</li>
    <li>Hacking2</li>
    <li>My brouser3</li>
    <li>About-Me</li>
    <li>OpenXi.ru</li>
  </ol>
  <br>
  <button><a href="https://asadbek470.github.io/ChatXI.uz/">OpenXi.uz</a></button>
  <button><a href="https://asadbek470.github.io/random-game5.3/">random-game5</a></button>
  <button><a href="https://asadbek470.github.io/Hacking2.3.5/">Hacking2</a></button>
  <button><a href="https://asadbek470.github.io/my-brouser3/"> my-brouser3</a></button>
  <button><a href="https://asadbek470.github.io/About-Me1./">About-Me</a></button>
  <button><a href="https://asadbek470.github.io/OpenXI.ru2/">OpenXi.ru</a></button>
  <p>Thank you for visiting my web site!</p>
 
</body>
</html>
