<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <title>Điều Bất Ngờ Nhỏ Nhắn 💖</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      background: #ffe6f0;
      font-family: 'Segoe UI', sans-serif;
      overflow: hidden;
    }

    .container {
      text-align: center;
      color: #c71585;
      padding: 50px;
    }

    h1 {
      font-size: 2.5em;
      margin-bottom: 10px;
      animation: fadeIn 2s ease-in-out;
    }

    .typing {
      font-size: 1.5em;
      border-right: 2px solid;
      white-space: nowrap;
      overflow: hidden;
      width: 0;
      animation: typing 6s steps(40, end), blink .75s step-end infinite;
      margin: 20px auto;
    }

    @keyframes typing {
      from { width: 0; }
      to { width: 100%; }
    }

    @keyframes blink {
      from, to { border-color: transparent; }
      50% { border-color: #c71585; }
    }

    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }

    .heart {
      position: absolute;
      width: 20px;
      height: 20px;
      background: red;
      transform: rotate(45deg);
      animation: float 10s infinite;
    }

    .heart:before,
    .heart:after {
      content: "";
      position: absolute;
      width: 20px;
      height: 20px;
      background: red;
      border-radius: 50%;
    }

    .heart:before {
      top: -10px;
      left: 0;
    }

    .heart:after {
      left: -10px;
      top: 0;
    }

    @keyframes float {
      0% {
        transform: translateY(0) rotate(45deg);
        opacity: 1;
      }
      100% {
        transform: translateY(-1000px) rotate(45deg);
        opacity: 0;
      }
    }

    .popup {
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      background: white;
      padding: 20px;
      border-radius: 15px;
      box-shadow: 0 0 20px pink;
      display: none;
      z-index: 999;
    }

    .popup img {
      max-width: 300px;
      border-radius: 10px;
    }

    audio {
      display: none;
    }
  </style>
</head>
<body>

  <audio autoplay loop>
    <source src="https://www.bensound.com/bensound-music/bensound-love.mp3" type="audio/mpeg">
  </audio>

  <div class="container">
    <h1>Gửi đến người đặc biệt 💌</h1>
    <div class="typing">Tớ có một điều nhỏ nhỏ muốn nói với cậu...</div>
  </div>

  <div class="popup" id="popup">
    <img src="https://i.pinimg.com/originals/55/e5/5e/55e55ea4a3e2b63f8fd72f9e524bcb35.gif" alt="Cute surprise">
    <p style="color: #c71585; font-size: 1.2em; margin-top: 10px;">Cảm ơn cậu vì đã đến bên tớ 💖</p>
  </div>

  <script>
    // Tạo tim bay
    function createHeart() {
      const heart = document.createElement('div');
      heart.classList.add('heart');
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.top = "100vh";
      heart.style.animationDuration = (5 + Math.random() * 5) + "s";
      document.body.appendChild(heart);
      setTimeout(() => heart.remove(), 10000);
    }

    setInterval(createHeart, 300);

    // Hiện popup sau 15 giây
    setTimeout(() => {
      document.getElementById("popup").style.display = "block";
    }, 15000);

    // Tự chuyển trang sau 30s
    setTimeout(() => {
      document.body.innerHTML = `
        <div class="container">
          <h1>Một hành trình 2 phút chỉ mới bắt đầu...</h1>
          <div class="typing" style="animation: typing 10s steps(60, end), blink .75s step-end infinite;">Mong rằng cậu luôn hạnh phúc, và nụ cười luôn ở lại trên môi. 💕</div>
        </div>`;
    }, 30000);
  </script>

</body>
</html>
