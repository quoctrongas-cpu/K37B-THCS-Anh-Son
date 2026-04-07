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
      overflow-x: hidden;
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
      cursor: pointer;
    }

    section {
      display: none;
      padding: 40px;
      text-align: center;
    }

    .active {
      display: block;
    }

    .card {
      background: rgba(255,255,255,0.05);
      border: 1px solid rgba(255,255,255,0.2);
      backdrop-filter: blur(15px);
      padding: 30px;
      border-radius: 20px;
      margin: 20px auto;
      max-width: 600px;
      box-shadow: 0 0 20px rgba(0,247,255,0.3);
    }

    ul {
      list-style: none;
      margin-top: 15px;
    }

    li {
      margin: 10px 0;
      padding: 10px;
      background: rgba(255,255,255,0.1);
      border-radius: 10px;
    }

    footer {
      text-align: center;
      padding: 10px;
      background: rgba(0,0,0,0.5);
      margin-top: 30px;
    }
  </style>
</head>

<body>

<canvas id="bg"></canvas>

<header>
  <h1>✨ K37B - Lớp 7B ✨</h1>
  <nav>
    <a onclick="showPage('home')">Trang chủ</a>
    <a onclick="showPage('members')">Thành viên</a>
    <a onclick="showPage('teachers')">Thầy cô</a>
    <a onclick="showPage('news')">Thông báo</a>
  </nav>
</header>

<!-- Trang chủ -->
<section id="home" class="active">
  <div class="card">
    <h2>Chào mừng 🎉</h2>
    <p>Website chính thức của K37B 😎</p>
  </div>
</section>

<!-- Thành viên -->
<section id="members">
  <div class="card">
    <h2>👥 Thành viên lớp</h2>
    <ul>
      <li>Trọng 😎</li>
      <li>Nguyễn Văn A</li>
      <li>Trần Thị B</li>
      <li>Lê Văn C</li>
    </ul>
  </div>
</section>

<!-- Thầy cô -->
<section id="teachers">
  <div class="card">
    <h2>👩‍🏫 Thầy cô</h2>
    <ul>
      <li>Thầy chủ nhiệm</li>
      <li>Cô Toán</li>
      <li>Cô Văn</li>
    </ul>
  </div>
</section>

<!-- Thông báo -->
<section id="news">
  <div class="card">
    <h2>📢 Thông báo</h2>
    <ul>
      <li>Mai kiểm tra Toán</li>
      <li>Thứ 6 lao động</li>
      <li>Nộp bài tập trước CN</li>
    </ul>
  </div>
</section>

<footer>
  © 2026 K37B 😎
</footer>

<script>
  function showPage(id) {
    document.querySelectorAll('section').forEach(sec => {
      sec.classList.remove('active');
    });
    document.getElementById(id).classList.add('active');
  }

  // hiệu ứng rơi
  const canvas = document.getElementById('bg');
  const ctx = canvas.getContext('2d');
  canvas.width = window.innerWidth;
  canvas.height = window.innerHeight;

  let particles = [];
  for (let i = 0; i < 100; i++) {
    particles.push({ x: Math.random()*canvas.width, y: Math.random()*canvas.height, r: Math.random()*2, d: Math.random() });
  }

  function draw() {
    ctx.clearRect(0,0,canvas.width,canvas.height);
    ctx.fillStyle = 'white';
    particles.forEach(p => {
      ctx.beginPath();
      ctx.arc(p.x,p.y,p.r,0,Math.PI*2);
      ctx.fill();
    });
    particles.forEach(p => {
      p.y += p.d;
      if(p.y > canvas.height){ p.y = 0; p.x = Math.random()*canvas.width; }
    });
  }
  setInterval(draw,30);
</script>

</body>
</html>
