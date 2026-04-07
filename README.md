<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>K37B - Lớp 7B</title>

<style>
*{margin:0;padding:0;box-sizing:border-box}
body{
  font-family:Arial;
  background: radial-gradient(circle,#1a1a2e,#16213e);
  color:white;
  overflow-x:hidden;
}

header{text-align:center;padding:20px}
h1{text-shadow:0 0 10px #00f7ff,0 0 20px #00f7ff}

.marquee{overflow:hidden;white-space:nowrap;margin-top:10px}
.marquee span{
  display:inline-block;
  padding-left:100%;
  animation:marquee 10s linear infinite;
  color:#00f7ff;
  text-shadow:0 0 10px #00f7ff;
}
@keyframes marquee{
  0%{transform:translateX(0)}
  100%{transform:translateX(-100%)}
}

nav button{
  margin:5px;padding:10px;border:none;border-radius:10px;
  cursor:pointer;background:rgba(255,255,255,0.1);
  color:white;transition:.3s
}
nav button:hover{
  background:#00f7ff;color:black;
  transform:scale(1.1);
}

section{display:none;padding:20px}
.active{display:block}

.card{
  background:rgba(255,255,255,0.1);
  padding:20px;
  border-radius:20px;
  max-width:700px;
  margin:20px auto;
  text-align:center;
}

.gallery{display:grid;grid-template-columns:repeat(auto-fit,minmax(120px,1fr));gap:10px}
.gallery img{width:100%;border-radius:10px;cursor:pointer}

.member{padding:10px;border-bottom:1px solid #555;cursor:pointer}
.member:hover{background:#00f7ff;color:black}

.chat{max-height:200px;overflow:auto;text-align:left}

#lightbox{
  position:fixed;top:0;left:0;width:100%;height:100%;
  background:black;display:none;align-items:center;justify-content:center
}
#lightbox img{max-width:90%}

input{padding:10px;border-radius:10px;border:none;margin:10px}
button.action{padding:10px 20px;border:none;border-radius:10px;background:linear-gradient(45deg,#00f7ff,#00ff88)}

.light{background:white;color:black}

canvas{position:fixed;top:0;left:0;z-index:-1}

/* profile popup */
#profileBox{
position:fixed;
top:50%;left:50%;
transform:translate(-50%,-50%);
background:#111;
padding:20px;
border-radius:15px;
display:none;
z-index:999;
box-shadow:0 0 20px #00f7ff;
text-align:center;
}
</style>
</head>

<body>

<canvas id="bg"></canvas>

<header>
<h1>✨ K37B - Lớp 7B ✨</h1>
<div class="marquee"><span>🔥 Website lớp 7B siêu xịn 🔥</span></div>

<nav>
<button onclick="show('home')">Trang chủ</button>
<button onclick="show('members')">Thành viên</button>
<button onclick="show('teachers')">Thầy cô</button>
<button onclick="show('news')">Thông báo</button>
<button onclick="show('gallery')">Ảnh</button>
<button onclick="show('chat')">Chat</button>
<button onclick="show('login')">Đăng nhập</button>
<button onclick="toggleMode()">🌙/☀️</button>
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
<div id="memberList"></div>
</div>
</section>

<section id="teachers">
<div class="card">
<h2>👩‍🏫 Thầy cô</h2>
<p>Thầy chủ nhiệm</p>
<p>Cô Toán</p>
</div>
</section>

<section id="news">
<div class="card">
<h2>📢 Thông báo</h2>
<p>Mai kiểm tra</p>
</div>
</section>

<section id="gallery">
<div class="card">
<h2>📸 Ảnh lớp</h2>
<div class="gallery">
<img src="https://picsum.photos/200?1" onclick="zoom(this.src)">
<img src="https://picsum.photos/200?2" onclick="zoom(this.src)">
<img src="https://picsum.photos/200?3" onclick="zoom(this.src)">
</div>
</div>
</section>

<section id="chat">
<div class="card">
<div class="chat" id="chatBox"></div>
<input id="msg" placeholder="nhập tin nhắn">
<button class="action" onclick="send()">Gửi</button>
</div>
</section>

<section id="login">
<div class="card">
<h2>🔐 Đăng nhập</h2>
<input id="name" placeholder="Tên">
<button class="action" onclick="saveName()">Lưu</button>
<button class="action" onclick="logout()">Xoá</button>
</div>
</section>

<div id="lightbox" onclick="this.style.display='none'"><img id="lightImg"></div>

<div id="profileBox">
<h2 id="pName"></h2>
<p id="pInfo"></p>
<button onclick="closeProfile()">Đóng</button>
</div>

<script>
function show(id){
document.querySelectorAll('section').forEach(s=>s.classList.remove('active'))
document.getElementById(id).classList.add('active')
}

function zoom(src){
document.getElementById('lightbox').style.display='flex'
document.getElementById('lightImg').src=src
}

function toggleMode(){document.body.classList.toggle('light')}

function send(){
let msg=document.getElementById('msg').value
let box=document.getElementById('chatBox')
box.innerHTML+=`<p>😎: ${msg}</p>`
localStorage.setItem('chat',box.innerHTML)
}
if(localStorage.getItem('chat')){
document.getElementById('chatBox').innerHTML=localStorage.getItem('chat')
}

function saveName(){
let name=document.getElementById('name').value
localStorage.setItem('user',name)
loadName()
}
function loadName(){
let name=localStorage.getItem('user')
if(name){document.getElementById('hello').innerText='Xin chào '+name+' 😎'}
}
function logout(){localStorage.removeItem('user');location.reload()}
loadName()

// members + profile
let list=document.getElementById('memberList')
for(let i=1;i<=41;i++){
let div=document.createElement('div')
div.className='member'
div.innerText='Thành viên '+i

div.onclick=()=>{
document.getElementById('profileBox').style.display='block'
document.getElementById('pName').innerText=div.innerText
document.getElementById('pInfo').innerText='Lớp 7B - K37B 😎'
}

list.appendChild(div)
}

function closeProfile(){document.getElementById('profileBox').style.display='none'}

// hiệu ứng rơi
const c=document.getElementById('bg')
const ctx=c.getContext('2d')
c.width=window.innerWidth
c.height=window.innerHeight

let p=[]
for(let i=0;i<100;i++){
p.push({x:Math.random()*c.width,y:Math.random()*c.height,r:Math.random()*2,d:Math.random()+0.5})
}

setInterval(()=>{
ctx.clearRect(0,0,c.width,c.height)
ctx.fillStyle='white'
p.forEach(e=>{
ctx.beginPath()
ctx.arc(e.x,e.y,e.r,0,Math.PI*2)
ctx.fill()
e.y+=e.d
if(e.y>c.height){e.y=0;e.x=Math.random()*c.width}
})
},30)
</script>

</body>
</html>
