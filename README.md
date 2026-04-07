<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>K37B - Lớp 7B</title>

  <style>
    * { margin:0; padding:0; box-sizing:border-box; }

    body {
      font-family: Arial;
      background: radial-gradient(circle, #1a1a2e, #16213e);
      color: white;
      overflow-x: hidden;
    }

    header {
      text-align:center;
      padding:20px;
    }

    h1 {
      text-shadow:0 0 10px #00f7ff;
    }

    nav button {
      margin:5px;
      padding:10px;
      border:none;
      border-radius:10px;
      cursor:pointer;
    }

    section { display:none; padding:20px; }
    .active { display:block; }

    .card {
      background: rgba(255,255,255,0.1);
      padding:20px;
      border-radius:15px;
      max-width:500px;
      margin:20px auto;
      text-align:center;
    }

    input {
      padding:10px;
      margin:10px;
      border-radius:10px;
      border:none;
    }

    canvas {
      position:fixed;
      top:0; left:0;
      z-index:-1;
    }
  </style>
</head>

<body>

<canvas id="bg"></canvas>

<header>
  <h1>✨ K37B - Lớp 7B ✨</h1>
  <nav>
    <button onclick="show('home')">Trang chủ</button>
    <button onclick="show('members')">Thành viên</button>
    <button onclick="show('teachers')">Thầy cô</button>
    <button onclick="show('news')">Thông báo</button>
    <button onclick="show('login')">Đăng nhập</button>
  </nav>
</header>

<section id="home" class="active">
  <div class="card">
    <h2 id="hello">Chào mừng 😎</h2>
  </div>
</section>

<section id="members">
  <div class="card">
    <h2>👥 Thành viên</h2>
    <p>Trọng 😎</p>
    <p>Nguyễn Văn A</p>
  </div>
</section>

<section id="teachers">
  <div class="card">
    <h2>👩‍🏫 Thầy cô</h2>
    <p>Thầy chủ nhiệm</p>
  </div>
</section>

<section id="news">
  <div class="card">
    <h2>📢 Thông báo</h2>
    <p>Mai kiểm tra</p>
  </div>
</section>

<section id="login">
  <div class="card">
    <h2>🔐 Đăng nhập</h2>
    <input id="name" placeholder="Nhập tên">
    <br>
    <button onclick="saveName()">Lưu</button>
    <button onclick="logout()">Xoá</button>
  </div>
</section>

<script>
  function show(id){
    document.querySelectorAll('section').forEach(s=>s.classList.remove('active'));
    document.getElementById(id).classList.add('active');
  }

  function saveName(){
    const name = document.getElementById('name').value;
    localStorage.setItem('user', name);
    loadName();
  }

  function loadName(){
    const name = localStorage.getItem('user');
    if(name){
      document.getElementById('hello').innerText = 'Xin chào ' + name + ' 😎';
    }
  }

  function logout(){
    localStorage.removeItem('user');
    location.reload();
  }

  loadName();

  // hiệu ứng rơi
  const c = document.getElementById('bg');
  const ctx = c.getContext('2d');
  c.width = window.innerWidth;
  c.height = window.innerHeight;

  let p = [];
  for(let i=0;i<80;i++){
    p.push({x:Math.random()*c.width,y:Math.random()*c.height,r:Math.random()*2,d:Math.random()});
  }

  setInterval(()=>{
    ctx.clearRect(0,0,c.width,c.height);
    ctx.fillStyle='white';
    p.forEach(e=>{
      ctx.beginPath();
      ctx.arc(e.x,e.y,e.r,0,Math.PI*2);
      ctx.fill();
      e.y+=e.d;
      if(e.y>c.height){e.y=0;e.x=Math.random()*c.width}
    });
  },30);
</script>

</body>
</html>
