<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Happy Valentine ❤️</title>
  <style>
    body {
      margin: 0;
      height: 100vh;
      background: linear-gradient(135deg, #ff758c, #ff7eb3);
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: 'Segoe UI', sans-serif;
      color: white;
      text-align: center;
      overflow: hidden;
    }

    /* Floating hearts */
    .heart-float {
      position: absolute;
      color: rgba(255,255,255,0.7);
      font-size: 20px;
      animation: float 6s linear infinite;
    }

    @keyframes float {
      0% {
        transform: translateY(100vh) scale(1);
        opacity: 1;
      }
      100% {
        transform: translateY(-10vh) scale(1.5);
        opacity: 0;
      }
    }

    .card {
      background: rgba(255, 255, 255, 0.15);
      padding: 40px;
      border-radius: 20px;
      box-shadow: 0 10px 30px rgba(0,0,0,0.2);
      max-width: 400px;
      animation: fadeIn 1.5s ease;
      position: relative;
      z-index: 10;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(30px); }
      to { opacity: 1; transform: translateY(0); }
    }

    h1 {
      font-size: 2.4em;
      margin-bottom: 10px;
    }

    .main-heart {
      font-size: 50px;
      animation: beat 1s infinite;
      margin: 20px 0;
    }

    @keyframes beat {
      0%, 100% { transform: scale(1); }
      50% { transform: scale(1.3); }
    }

    .question {
      font-size: 1.3em;
      margin: 20px 0;
    }

    .buttons {
      display: flex;
      justify-content: center;
      gap: 20px;
      margin-top: 20px;
      position: relative;
    }

    button {
      padding: 12px 25px;
      font-size: 1em;
      border: none;
      border-radius: 30px;
      cursor: pointer;
      font-weight: bold;
    }

    .yes {
      background: white;
      color: #ff4f7a;
    }

    .no {
      background: #ff4f7a;
      color: white;
      position: absolute;
    }

    .result {
      margin-top: 25px;
      font-size: 1.2em;
      opacity: 0;
    }

    .show {
      animation: pop 0.8s forwards;
    }

    @keyframes pop {
      from { opacity: 0; transform: scale(0.5); }
      to { opacity: 1; transform: scale(1); }
    }

    footer {
      margin-top: 25px;
      font-size: 0.9em;
      opacity: 0.9;
    }
  </style>
</head>
<body>

  <div class="card">
    <h1>Happy Valentine 💖</h1>
    <div class="main-heart">❤️</div>

    <div class="question">
      Will you be my Valentine? 💌
    </div>

    <div class="buttons">
      <button class="yes" onclick="sayYes()">YES 💕</button>
      <button class="no" id="noBtn" onmouseover="moveNo()">NO 😜</button>
    </div>

    <div id="result" class="result">
      Yayyy! 💖  
      You just made my day 🥰
    </div>

    <footer>
      — From Prajwal 🌹
    </footer>
  </div>

  <script>
    // YES button
    function sayYes() {
      document.getElementById("result").classList.add("show");
    }

    // NO button runs away
    function moveNo() {
      const btn = document.getElementById("noBtn");
      const x = Math.random() * 200 - 100;
      const y = Math.random() * 100 - 50;
      btn.style.transform = `translate(${x}px, ${y}px)`;
    }

    // Floating hearts generator
    setInterval(() => {
      const heart = document.createElement("div");
      heart.className = "heart-float";
      heart.innerHTML = "❤️";
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.fontSize = Math.random() * 20 + 15 + "px";
      heart.style.animationDuration = Math.random() * 3 + 4 + "s";
      document.body.appendChild(heart);

      setTimeout(() => {
        heart.remove();
      }, 6000);
    }, 300);
  </script>

</body>
</html>
