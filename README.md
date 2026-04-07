<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>K37B - Lớp 7B</title>

  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }

    body {
      font-family: Arial, sans-serif;
      overflow: hidden;
      background: radial-gradient(circle at top, #1a1a2e, #0f3460, #16213e);
      color: white;
    }

    canvas {
      position: fixed;
      top: 0;
      left: 0;
      z-index: -1;
    }

    header {
      text-align: center;
      padding: 30px;
    }

    h1 {
      font-size: 40px;
      text-shadow: 0 0 10px #00f7ff, 0 0 20px #00f7ff;
    }

    nav a {
      margin: 0 15px;
      color: white;
      text-decoration: none;
      font-weight: bold;
      transition: 0.3s;
    }

    nav a:hover {
      color: #00f7ff;
      text-shadow: 0 0 10px #00f7ff;
    }

    .container {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 70vh;
    }

    .card {
      background: rgba(255,255,255,0.05);
      border: 1px solid rgba(255,255,255,0.2);
      backdrop-filter: blur(15px);
      padding: 40px;
      border-radius: 20px;
      text-align: center;
      box-shadow: 0 0 30px rgba(0,247,255,0.3);
      animation: float 3s ease-in-out infinite;
    }

    @keyframes float {
      0%,100% { transform: translateY(0); }
      50% { transform: translateY(-10px); }
    }

    .card h2 {
      margin-bottom: 10px;
      text-shadow: 0 0 10px #fff;
    }

    button {
      margin-top: 20px;
      padding: 12px 25px;
      border: none;
      border-radius: 10px;
      background: linear-gradient(45deg, #00f7ff, #00ff88);
      color: black;
      font-weight: bold;
      cursor: pointer;
      transition: 0.3s;
    }

    button:hover {
      transform: scale(1.1);
      box-shadow: 0 0 20px #00f7ff;
    }

    footer {
      position: fixed;
      bottom: 0;
      width: 100%;
      text-align: center;
      padding: 10px;
      background: rgba(0,0,0,0.5);
    }
  </style>
</head>

<body>

<canvas id="bg"></canvas>

<header>
  <h1>✨ K37B - Lớp 7B ✨</h1>
  <nav>
    <a href="#">Trang chủ</a>
    <a href="#">Thành viên</a>
    <a href="#">Hoạt động</a>
  </nav>
</header>

<div class="container">
  <div class="card">
    <h2>Chào mừng đến với K37B 🎉</h2>
    <p>Website siêu xịn của lớp 😎🔥</p>
    <button onclick="clickMe()">Bấm thử đi 😏</button>
  </div>
</div>

<footer>
  © 2026 K37B - Lớp 7B 😎
</footer>

<script>
  function clickMe() {
    alert("K37B mãi đỉnh 😎🔥");
  }

  // Hiệu ứng rơi rơi (particles)
  const canvas = document.getElementById('bg');
  const ctx = canvas.getContext('2d');

  canvas.width = window.innerWidth;
  canvas.height = window.innerHeight;

  let particles = [];

  for (let i = 0; i < 100; i++) {
    particles.push({
      x: Math.random() * canvas.width,
      y: Math.random() * canvas.height,
      r: Math.random() * 2,
      d: Math.random() * 1
    });
  }

  function draw() {
    ctx.clearRect(0, 0, canvas.width, canvas.height);
    ctx.fillStyle = 'white';

    particles.forEach(p => {
      ctx.beginPath();
      ctx.arc(p.x, p.y, p.r, 0, Math.PI * 2);
      ctx.fill();
    });

    update();
  }

  function update() {
    particles.forEach(p => {
      p.y += p.d;
      if (p.y > canvas.height) {
        p.y = 0;
        p.x = Math.random() * canvas.width;
      }
    });
  }

  setInterval(draw, 30);
</script>

</body>
</html>
