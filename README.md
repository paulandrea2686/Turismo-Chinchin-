<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Turismo en Chinchiná – Nivel Leyenda</title>

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
<style>
:root{
--verde:#1b5e20;
--verde2:#2e7d32;
--fondo:#f4f4f4;
--texto:#333;
}
body.dark{--fondo:#121212;--texto:#f4f4f4;}
body{margin:0;font-family:Arial;background:var(--fondo);color:var(--texto);transition:0.4s;}

/* VIDEO HEADER */
header{position:relative;height:100vh;overflow:hidden;display:flex;justify-content:center;align-items:center;text-align:center;color:white;}
header video{position:absolute;top:0;left:0;width:100%;height:100%;object-fit:cover;z-index:-1;}
header h1{font-size:3em;background:rgba(0,0,0,0.6);padding:15px;border-radius:15px;}

/* NAV */
nav{background:var(--verde);display:flex;justify-content:space-between;padding:15px 30px;position:sticky;top:0;z-index:1000;}
nav a{color:white;text-decoration:none;margin:0 10px;font-weight:bold;}
.toggle{color:white;cursor:pointer;}

/* SECCIONES */
section{padding:70px 10%;opacity:0;transform:translateY(40px);transition:1s;}
section.visible{opacity:1;transform:translateY(0);}
h2{text-align:center;margin-bottom:40px;color:var(--verde);}

/* CARDS */
.grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(250px,1fr));gap:20px;}
.card{background:white;border-radius:15px;box-shadow:0 6px 15px rgba(0,0,0,0.2);transition:0.3s;overflow:hidden;}
body.dark .card{background:#1e1e1e;}
.card:hover{transform:scale(1.05);}
.card img{width:100%;height:200px;object-fit:cover;}
.card h3,p{padding:10px;}
.boton{display:inline-block;margin:10px;padding:8px 15px;background:var(--verde2);color:white;border-radius:20px;text-decoration:none;}

/* CONTADORES */
.contadores{display:flex;justify-content:center;gap:50px;font-size:2em;text-align:center;}

/* GALERÍA */
.galeria{display:flex;overflow:hidden;margin-bottom:30px;}
.galeria img{width:100%;animation:slide 15s infinite;}
@keyframes slide{0%{transform:translateX(0);}33%{transform:translateX(-100%);}66%{transform:translateX(-200%);}100%{transform:translateX(0);}}

/* CHAT */
#chat{position:fixed;bottom:20px;right:20px;width:300px;background:white;border-radius:10px;box-shadow:0 5px 15px rgba(0,0,0,0.3);display:flex;flex-direction:column;overflow:hidden;}
#chat-header{background:var(--verde);color:white;padding:10px;font-weight:bold;display:flex;justify-content:space-between;align-items:center;}
#chat-messages{padding:10px;height:200px;overflow-y:auto;font-size:0.9em;}
#chat-input{display:flex;border-top:1px solid #ccc;}
#chat-input input{flex:1;padding:10px;border:none;}
#chat-input button{background:var(--verde2);color:white;border:none;padding:10px;cursor:pointer;}
body.dark #chat{background:#1e1e1e;color:white;}
body.dark #chat-input button{background:#2e7d32;}

footer{background:var(--verde);color:white;text-align:center;padding:20px;}
</style>
</head>

<body>

<header>
<video autoplay muted loop>
<source src="https://cdn.coverr.co/videos/coverr-coffee-plantation-1573/1080p.mp4" type="video/mp4">
</video>
<h1>Descubre Chinchiná ☕</h1>
</header>

<nav>
<div>
<a href="#atracciones">Atracciones</a>
<a href="#datos">Datos</a>
<a href="#galeria">Galería</a>
<a href="#mapa">Ubicación</a>
</div>
<div>
<i class="fas fa-moon toggle" onclick="modoOscuro()"></i>
</div>
</nav>

<section id="atracciones">
<h2>Atracciones Turísticas</h2>
<div class="grid">
<div class="card">
<img src="https://upload.wikimedia.org/wikipedia/commons/5/56/Cafe_colombiano.jpg">
<h3>Ruta Cafetera</h3>
<p>Experiencia del café.</p>
<a class="boton" href="https://es.wikipedia.org/wiki/Caf%C3%A9_de_Colombia" target="_blank">Saber más</a>
</div>
<div class="card">
<img src="https://upload.wikimedia.org/wikipedia/commons/4/4e/Rio_Cameguadua.jpg">
<h3>Río Cameguadua</h3>
<p>Naturaleza y paisajes.</p>
<a class="boton" href="https://www.google.com/maps?q=R%C3%ADo+Cameguadua" target="_blank">Ver mapa</a>
</div>
<div class="card">
<img src="https://upload.wikimedia.org/wikipedia/commons/6/6a/Basilica_Chinchina.jpg">
<h3>Basílica</h3>
<p>Templo histórico.</p>
<a class="boton" href="https://www.google.com/maps?q=Bas%C3%ADlica+Chinchin%C3%A1" target="_blank">Cómo llegar</a>
</div>
</div>
</section>

<section id="datos">
<h2>Datos de Chinchiná</h2>
<div class="contadores">
<div><span id="habitantes">0</span><br>Habitantes</div>
<div><span id="temperatura">0</span>°C<br>Clima</div>
<div><span id="cafeteras">0</span><br>Fincas cafeteras</div>
</div>
</section>

<section id="galeria">
<h2>Galería</h2>
<div class="galeria">
<img src="https://upload.wikimedia.org/wikipedia/commons/3/3f/Chinchina_Caldas.jpg">
<img src="https://upload.wikimedia.org/wikipedia/commons/5/56/Cafe_colombiano.jpg">
<img src="https://upload.wikimedia.org/wikipedia/commons/4/4e/Rio_Cameguadua.jpg">
</div>
</section>

<section id="mapa">
<h2>Ubicación</h2>
<iframe src="https://www.google.com/maps?q=Chinchiná,Caldas,Colombia&output=embed"
width="100%" height="350"></iframe>
</section>

<!-- CHAT -->
<div id="chat">
<div id="chat-header">Pregunta sobre Chinchiná <i class="fas fa-times" onclick="document.getElementById('chat').style.display='none'"></i></div>
<div id="chat-messages"></div>
<div id="chat-input">
<input type="text" id="mensaje" placeholder="Escribe tu pregunta">
<button onclick="enviar()">Enviar</button>
</div>
</div>

<footer>
Proyecto Escolar - Turismo en Chinchiná © 2026
</footer>

<script>
/* Modo oscuro */
function modoOscuro(){document.body.classList.toggle("dark");}

/* Animar secciones */
window.addEventListener("scroll", function(){
document.querySelectorAll("section").forEach(sec=>{
if(sec.getBoundingClientRect().top < window.innerHeight - 100){
sec.classList.add("visible");
}
});
});

/* Contadores */
function animar(id,max){let num=0;let i=setInterval(()=>{num+=Math.ceil(max/100);if(num>=max){num=max;clearInterval(i);}document.getElementById(id).innerText=num;},30);}
animar("habitantes",52000);animar("temperatura",22);animar("cafeteras",150);

/* Chat interactivo simple */
function enviar(){
let msg=document.getElementById("mensaje").value.toLowerCase();
let respuesta="No entiendo, pregunta otra cosa :)";
if(msg.includes("café")) respuesta="Chinchiná es famosa por su café de especialidad ☕";
if(msg.includes("clima")) respuesta="El clima es templado, entre 18°C y 24°C 🌤️";
if(msg.includes("mapa")) respuesta="Puedes ver la ubicación en la sección 'Ubicación' 🗺️";
let div=document.createElement("div");div.textContent="Tú: "+document.getElementById("mensaje").value;document.getElementById("chat-messages").appendChild(div);
let div2=document.createElement("div");div2.textContent="Info: "+respuesta;document.getElementById("chat-messages").appendChild(div2);
document.getElementById("mensaje").value="";document.getElementById("chat-messages").scrollTop=document.getElementById("chat-messages").scrollHeight;
}

/* Sonido ambiente opcional */
let audio=new Audio('https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3');
audio.loop=true;
// audio.play(); // Descomenta para reproducir automáticamente
</script>

</body>
</html>
