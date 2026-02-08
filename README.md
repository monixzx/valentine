<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Happy Propose Day 💍</title>

  <style>
    body {
      margin: 0;
      height: 100vh;
      background: linear-gradient(135deg, #ff5f6d, #ffc371);
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: 'Segoe UI', sans-serif;
      color: white;
      text-align: center;
      overflow: hidden;
    }

    /* Floating hearts */
    .heart {
      position: absolute;
      font-size: 20px;
      animation: float 6s linear infinite;
      opacity: 0.8;
    }

    @keyframes float {
      0% { transform: translateY(100vh) scale(1); }
      100% { transform: translateY(-10vh) scale(1.5); opacity: 0; }
    }

    .card {
      background: rgba(255,255,255,0.2);
      padding: 35px;
      border-radius: 20px;
      box-shadow: 0 10px 30px rgba(0,0,0,0.25);
      max-width: 420px;
      animation: fadeIn 1.4s ease;
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

    /* Person image */
    .person {
      width: 140px;
      height: 140px;
      border-radius: 50%;
      object-fit: cover;
      border: 4px solid white;
      margin: 15px auto;
      box-shadow: 0 10px 25px rgba(0,0,0,0.3);
      animation: glow 2.5s infinite;
    }

    @keyframes glow {
      0%,100% { box-shadow: 0 0 15px rgba(255,255,255,0.6); }
      50% { box-shadow: 0 0 30px rgba(255,255,255,1); }
    }

    /* Flower image */
    .flower {
      width: 120px;
      margin: 10px auto;
      animation: flowerFloat 3s ease-in-out infinite;
      border-radius: 10px;
    }

    @keyframes flowerFloat {
      0%,100% { transform: translateY(0); }
      50% { transform: translateY(-10px); }
    }

    .ring {
      font-size: 45px;
      margin: 10px 0;
      animation: pulse 1.2s infinite;
    }

    @keyframes pulse {
      0%,100% { transform: scale(1); }
      50% { transform: scale(1.3); }
    }

    .question {
      font-size: 1.25em;
      margin: 18px 0;
    }

    .buttons {
      margin-top: 18px;
      position: relative;
      height: 60px;
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
      color: #ff5f6d;
      margin-right: 20px;
    }

    .no {
      background: #ff5f6d;
      color: white;
      position: absolute;
    }

    .message {
      margin-top: 22px;
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
      margin-top: 20px;
      font-size: 0.9em;
      opacity: 0.9;
    }
  </style>
</head>

<body>

  <div class="card">
    <img class="person" src="skin.jpg" alt="You">
    <h1>Happy Propose Day 💍</h1>

    <img class="person" src="monixx.jpg" alt="You">

   
    

    <div class="ring">💖</div>

    <div class="question">
     Roses are red, violets are blue…<br>
     I can't stop thinking of you! 🌸💌<br>
      Will you be mine? 💍
 
    </div>

    <div class="buttons">
      <button class="yes" onclick="yesClicked()">YES 💕</button>
      <button class="no" id="noBtn" onmouseover="moveNo()">NO 😜</button>
    </div>

    <div id="msg" class="message">
      You are special to me 💗<br>
      You make me smile 😊<br>
      I like like the day when I am with you 🌙<br>
      I want you by my side 🤍<br>
      Happy Propose Day 💕

    </div>

    <footer>
      — From Prajwal 🌹
    </footer>
  </div>

  <script>
    function yesClicked() {
      document.getElementById("msg").classList.add("show");
    }

    function moveNo() {
      const btn = document.getElementById("noBtn");
      const x = Math.random() * 200 - 100;
      const y = Math.random() * 80 - 40;
      btn.style.transform = `translate(${x}px, ${y}px)`;
    }

    // Floating hearts
    setInterval(() => {
      const heart = document.createElement("div");
      heart.className = "heart";
      heart.innerHTML = "❤️";
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.fontSize = Math.random() * 20 + 15 + "px";
      heart.style.animationDuration = Math.random() * 3 + 4 + "s";
      document.body.appendChild(heart);

      setTimeout(() => heart.remove(), 6000);
    }, 300);
  </script>

</body>
</html>
