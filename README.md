<html>
<head>
  <style>
    body {
      margin: 0;
      padding: 0;
      overflow: hidden;
      background-image: url('small-brown-aesthetic-hearts-say7e3lt43ujclfy.jpg');
      background-size: cover;
      background-position: center;
      font-family: 'Segoe UI', sans-serif;
    }

    .rain {
      position: absolute;
      white-space: nowrap;
      animation: fall linear infinite;
      font-size: 24px;
      font-weight: bold;
      color: #ffcccc;
      text-shadow: 1px 1px 2px #00000088;
    }

    @keyframes fall {
      0% {
        top: -10%;
        opacity: 0;
      }
      10% {
        opacity: 1;
      }
      100% {
        top: 110%;
        opacity: 0;
      }
    }
  </style>
</head>
<body>
  <script>
    const count = 50; // number of falling messages
    for (let i = 0; i < count; i++) {
      const drop = document.createElement("div");
      drop.className = "rain";
      drop.textContent = "I MISS YOU ❤️";
      drop.style.left = Math.random() * 100 + "vw";
      drop.style.animationDuration = (Math.random() * 3 + 3) + "s";
      drop.style.animationDelay = Math.random() * 5 + "s";
      document.body.appendChild(drop);
    }
  </script>
</body>
</html>
