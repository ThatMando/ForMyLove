<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Love Letter for Neat</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      height: 100vh;
      overflow: hidden;
      background: linear-gradient(45deg, #ff9a9e, #fad0c4);
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      font-family: 'Arial', sans-serif;
      position: relative;
    }

    /* Raining emojis */
    .emoji {
      position: absolute;
      top: -50px;
      font-size: 30px;
      opacity: 0.8;
      animation: fall linear infinite;
    }

    @keyframes fall {
      0% {
        transform: translateY(0);
        opacity: 1;
      }
      100% {
        transform: translateY(110vh);
        opacity: 0;
      }
    }

    /* Envelope */
    #envelope {
      position: relative;
      height: 180px;
      width: 280px;
      border-bottom-left-radius: 6px;
      border-bottom-right-radius: 6px;
      background-color: #ff2a22;
      box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
      cursor: pointer;
      margin-bottom: 50px;
    }

    .front {
      position: absolute;
      width: 0;
      height: 0;
      z-index: 3;
    }

    .flap {
      border-top: 98px solid #ff2a22;
      border-left: 140px solid transparent;
      border-right: 140px solid transparent;
      border-bottom: 82px solid transparent;
      transform-origin: top;
    }

    .pocket {
      border-left: 140px solid #ff748d;
      border-right: 140px solid #ff748d;
      border-bottom: 90px solid #ff98a7;
      border-top: 90px solid transparent;
      border-bottom-left-radius: 6px;
      border-bottom-right-radius: 6px;
    }

    .letter {
      position: absolute;
      background-color: white;
      width: 90%;
      height: 90%;
      top: 5%;
      left: 5%;
      border-radius: 10px;
      box-shadow: 0 2px 26px rgba(0, 0, 0, .12);
      z-index: 1;
      transition: transform 0.4s ease;
    }

    .open .flap {
      transform: rotateX(180deg);
      transition: transform 0.4s ease;
      z-index: 1;
    }

    .close .flap {
      transform: rotateX(0deg);
      transition: transform 0.4s ease;
      z-index: 5;
    }

    .open .letter {
      transform: translateY(-120px);
      z-index: 2;
    }

    .close .letter {
      transform: translateY(0);
      z-index: 1;
    }

    /* Text inside letter */
    .message {
      position: absolute;
      top: 20%;
      left: 10%;
      width: 80%;
      text-align: center;
      font-size: 18px;
      opacity: 0;
      animation: fadeIn 3s forwards;
      animation-delay: 1s;
      color: #222;
    }

    @keyframes fadeIn {
      to {
        opacity: 1;
      }
    }

    .valentine {
      font-size: 30px;
      margin-top: 20px;
      color: #fff;
      text-shadow: 1px 1px 2px #ff2a22;
    }

    /* Sparkles */
    .sparkle {
      position: absolute;
      width: 10px;
      height: 10px;
      background: white;
      border-radius: 50%;
      opacity: 0.8;
      animation: sparkleAnim 2s infinite ease-in-out;
    }

    @keyframes sparkleAnim {
      0% { transform: scale(0.5); opacity: 0.3; }
      50% { transform: scale(1.5); opacity: 1; }
      100% { transform: scale(0.5); opacity: 0.3; }
    }
  </style>
</head>
<body class="close">
  <!-- Falling emojis -->
  <script>
    const emojis = ['❤️','😍','❤️','🥰','💕','💖','😘'];
    for (let i = 0; i < 30; i++) {
      const emoji = document.createElement('div');
      emoji.classList.add('emoji');
      emoji.style.left = `${Math.random() * 100}%`;
      emoji.style.animationDuration = `${3 + Math.random() * 3}s`;
      emoji.textContent = emojis[Math.floor(Math.random() * emojis.length)];
      document.body.appendChild(emoji);
    }
  </script>

  <!-- Sparkles -->
  <script>
    for (let i = 0; i < 15; i++) {
      const sparkle = document.createElement('div');
      sparkle.className = 'sparkle';
      sparkle.style.left = `${Math.random() * 100}%`;
      sparkle.style.top = `${Math.random() * 100}%`;
      sparkle.style.animationDelay = `${Math.random() * 2}s`;
      document.body.appendChild(sparkle);
    }
  </script>

  <!-- Envelope -->
  <div id="envelope" onclick="toggleEnvelope()">
    <div class="front flap"></div>
    <div class="front pocket"></div>
    <div class="letter">
      <div class="message">
        Dear Neat,<br/>
        You are so beautiful,<br/>
        it makes my world stop. 💗<br/>
        <small>— From Leapheng 🌟</small>
      </div>
    </div>
  </div>

  <!-- Greeting -->
  <div class="valentine">Happy Girlfriend Day 💘</div>

  <!-- JS for envelope toggle -->
  <script>
    function toggleEnvelope() {
      const body = document.body;
      body.classList.toggle('open');
      body.classList.toggle('close');
    }
  </script>
</body>
</html>
