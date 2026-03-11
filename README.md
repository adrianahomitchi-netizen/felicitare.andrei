<!DOCTYPE html>
<html lang="ro">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>La mulți ani!</title>

<style>

body{
margin:0;
font-family:Arial, sans-serif;
min-height:100vh;
display:flex;
justify-content:center;
align-items:center;
background:linear-gradient(135deg,#1a1a2e,#16213e,#0f3460);
overflow:hidden;
color:white;
}

.card{
background:white;
color:#333;
width:90%;
max-width:420px;
border-radius:20px;
padding:30px;
text-align:center;
box-shadow:0 15px 40px rgba(0,0,0,0.5);
transform:scale(0);
animation:openCard 1.5s forwards;
}

@keyframes openCard{
to{transform:scale(1)}
}

h2{
font-size:32px;
margin-bottom:10px;
color:#0f3460;
}

p{
font-size:18px;
line-height:1.4;
}

button{
margin-top:20px;
padding:14px 24px;
border:none;
border-radius:10px;
background:#0f3460;
color:white;
font-size:18px;
cursor:pointer;
}

button:hover{
background:#e94560;
}

.surprise{
position:fixed;
top:0;
left:0;
width:100%;
height:100%;
background:rgba(0,0,0,0.9);
display:flex;
justify-content:center;
align-items:center;
flex-direction:column;
text-align:center;
font-size:28px;
padding:20px;
opacity:0;
pointer-events:none;
transition:0.5s;
}

.surprise.show{
opacity:1;
pointer-events:auto;
}

.confetti{
position:absolute;
width:10px;
height:10px;
top:-10px;
animation:fall linear infinite;
}

@keyframes fall{
to{
transform:translateY(110vh) rotate(720deg);
}
}

</style>
</head>

<body>

<div class="card">

<h2>La Mulți Ani, dl Andrei! 🎉</h2>

<p>
31 de ani de experiențe, succes și aventuri!  
Îți doresc sănătate, noroc și multe realizări. 
Ești un profesor minunat și un om deosebit. 
Să ai parte de un an extraordinar!
</p>

<button onclick="showSurprise()">
Deschide surpriza 🎁
</button>

</div>

<div class="surprise" id="surprise">

<h1>🎂 La Mulți Ani, dl Andrei! 🎂</h1>

<p>
Să ai parte de sănătate, succes și multe momente frumoase!  
Fie ca acest nou an din viața ta să fie plin de realizări și bucurii.
</p>

<button onclick="closeSurprise()">Închide</button>

</div>

<script>

function showSurprise(){
document.getElementById("surprise").classList.add("show");
}

function closeSurprise(){
document.getElementById("surprise").classList.remove("show");
}

for(let i=0;i<80;i++){
let conf=document.createElement("div");
conf.classList.add("confetti");

conf.style.left=Math.random()*100+"vw";
conf.style.animationDuration=(Math.random()*3+2)+"s";
conf.style.background="hsl("+Math.random()*360+"deg,80%,60%)";

document.body.appendChild(conf);
}

</script>

</body>
</html>
