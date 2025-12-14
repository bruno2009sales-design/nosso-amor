# nosso-amor<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Nosso Amor 💖</title>
  <style>
    * { box-sizing: border-box; font-family: 'Arial', sans-serif; }
    body {
      margin: 0;
      background: linear-gradient(180deg, #ffdde1, #ee9ca7);
      color: #333;
    }
    .container {
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 20px;
    }
    .card {
      background: #fff;
      border-radius: 20px;
      padding: 25px;
      width: 100%;
      max-width: 420px;
      box-shadow: 0 10px 30px rgba(0,0,0,0.15);
      animation: fadeIn 1s ease;
    }
    h1, h2 {
      text-align: center;
    }
    input {
      width: 100%;
      padding: 12px;
      border-radius: 10px;
      border: 1px solid #ccc;
      margin-top: 10px;
      font-size: 16px;
    }
    button {
      width: 100%;
      padding: 12px;
      margin-top: 15px;
      background: #ee9ca7;
      border: none;
      color: #fff;
      font-size: 16px;
      border-radius: 12px;
    }
    button:hover { opacity: 0.9; }
    .hidden { display: none; }
    .counter {
      text-align: center;
      font-size: 18px;
      margin-top: 15px;
    }
    .timeline {
      margin-top: 25px;
    }
    .moment {
      background: #ffeef1;
      border-radius: 15px;
      padding: 15px;
      margin-bottom: 15px;
    }
    .moment img, .moment video {
      width: 100%;
      border-radius: 12px;
      margin-top: 10px;
    }
    .final-message {
      text-align: center;
      margin-top: 20px;
      font-weight: bold;
    }
    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(10px); }
      to { opacity: 1; transform: translateY(0); }
    }
  </style>
</head>
<body>

  <!-- TELA DE SENHA -->
  <div class="container" id="login">
    <div class="card">
      <h1>💖 Só quem viveu isso pode entrar 💖</h1>
      <input type="password" id="password" placeholder="Digite a senha" />
      <button onclick="checkPassword()">Entrar</button>
      <p id="error" style="color:red; text-align:center;"></p>
    </div>
  </div>

  <!-- CONTEÚDO PRINCIPAL -->
  <div class="container hidden" id="content">
    <div class="card">
      <h2>⏳ Nós estamos juntos há</h2>
      <div class="counter" id="counter"></div>
      <p style="text-align:center;">Desde 30 de julho de 2023 ❤️</p>

      <div class="timeline">
        <h2>🕰️ Nossa História</h2>

        <!-- MOMENTO 1 -->
        <div class="moment">
          <strong>Nosso começo 💕</strong>
          <p>Escreva aqui o que você lembra desse dia. Não precisa de data exata, só o sentimento.</p>
          <img src="foto1.jpg" alt="Nosso começo">
        </div>

        <!-- MOMENTO 2 -->
        <div class="moment">
          <strong>Um dia inesquecível ✨</strong>
          <p>Conte o que aconteceu, por que esse dia foi especial pra vocês.</p>
          <img src="foto2.jpg" alt="Dia especial">
        </div>

        <!-- MOMENTO 3 (COM VÍDEO) -->
        <div class="moment">
          <strong>Momentos que moram no coração ❤️</strong>
          <p>Escreva aqui a legenda desse vídeo.</p>
          <video src="video1.mp4" controls></video>
        </div>

        <!-- PARA ADICIONAR MAIS MOMENTOS, É SÓ COPIAR UM BLOCO DESSES -->
      </div>

        <div class="moment">
          <strong>Um dia inesquecível ✨</strong>
          <p>Conte esse momento com suas palavras.</p>
          <video src="video1.mp4" controls></video>
        </div>
      </div>

      <div class="final-message">
        Obrigado por viver tudo isso comigo 💖
      </div>
    </div>
  </div>

  <script>
    const correctPassword = "amor"; // MUDE A SENHA AQUI

    function checkPassword() {
      const input = document.getElementById("password").value;
      if (input === correctPassword) {
        document.getElementById("login").classList.add("hidden");
        document.getElementById("content").classList.remove("hidden");
        startCounter();
      } else {
        document.getElementById("error").innerText = "Senha incorreta 💔";
      }
    }

    function startCounter() {
      const startDate = new Date(2023, 6, 30, 0, 0, 0); // 30/07/2023
      setInterval(() => {
        const now = new Date();
        let diff = now - startDate;

        const seconds = Math.floor(diff / 1000) % 60;
        const minutes = Math.floor(diff / (1000 * 60)) % 60;
        const hours = Math.floor(diff / (1000 * 60 * 60)) % 24;
        const days = Math.floor(diff / (1000 * 60 * 60 * 24));

        document.getElementById("counter").innerHTML =
          `${days} dias, ${hours} horas, ${minutes} minutos e ${seconds} segundos ❤️`;
      }, 1000);
    }
  </script>

</body>
</html>
