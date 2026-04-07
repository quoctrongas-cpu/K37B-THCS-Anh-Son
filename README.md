<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>K37B - Lớp 7B</title>

  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      font-family: Arial, sans-serif;
      background: linear-gradient(120deg, #667eea, #764ba2);
      color: white;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
    }

    header {
      background: rgba(0,0,0,0.6);
      padding: 20px;
      text-align: center;
    }

    header h1 {
      margin-bottom: 10px;
    }

    nav a {
      color: white;
      margin: 0 15px;
      text-decoration: none;
      font-weight: bold;
      transition: 0.3s;
    }

    nav a:hover {
      color: #ffd700;
    }

    .container {
      flex: 1;
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 20px;
    }

    .card {
      background: rgba(255,255,255,0.15);
      padding: 30px;
      border-radius: 20px;
      text-align: center;
      width: 90%;
      max-width: 500px;
      backdrop-filter: blur(10px);
      box-shadow: 0 10px 30px rgba(0,0,0,0.3);
    }

    .card h2 {
      margin-bottom: 10px;
    }

    .card p {
      margin-bottom: 20px;
      opacity: 0.9;
    }

    button {
      padding: 12px 25px;
      border: none;
      border-radius: 10px;
      background: #ffd700;
      font-weight: bold;
      cursor: pointer;
      transition: 0.3s;
    }

    button:hover {
      background: #ffcc00;
      transform: scale(1.05);
    }

    footer {
      background: rgba(0,0,0,0.6);
      text-align: center;
      padding: 15px;
      font-size: 14px;
    }
  </style>
</head>

<body>

  <header>
    <h1>🏫 K37B - Lớp 7B</h1>
    <nav>
      <a href="#">Trang chủ</a>
      <a href="#">Thành viên</a>
      <a href="#">Hoạt động</a>
    </nav>
  </header>

  <div class="container">
    <div class="card">
      <h2>Chào mừng đến với lớp 7B 🎉</h2>
      <p>Đây là website chính thức của K37B!</p>
      <button onclick="clickMe()">Bấm vào đây 😎</button>
    </div>
  </div>

  <footer>
    © 2026 K37B - Lớp 7B 😎
  </footer>

  <script>
    function clickMe() {
      alert("Hello K37B 😎🔥");
    }
  </script>

</body>
</html>
