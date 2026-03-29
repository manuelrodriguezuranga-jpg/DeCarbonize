<!doctype html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>#DeCabonize</title>

<style>
*{margin:0;padding:0;box-sizing:border-box;}

body{
  font-family: Georgia, serif;
  background:#ffffff;
  color:#222;
  line-height:1.7;
}

header{
  text-align:center;
  padding:30px;
  border-bottom:2px solid #e5e5e5;
}

h1{
  font-size:2.5em;
  color:#2e7d32;
}

nav{
  display:flex;
  justify-content:center;
  gap:20px;
  padding:15px;
  border-bottom:1px solid #eee;
}

nav a{
  text-decoration:none;
  color:#333;
  font-weight:bold;
}

nav a:hover{
  color:#2e7d32;
}

.container{
  max-width:900px;
  margin:auto;
  padding:30px;
}

.card{
  border-bottom:1px solid #eee;
  padding:20px 0;
  transition:0.2s;
}

.card:hover{
  padding-left:5px;
}

.card h2{
  font-size:1.5em;
  margin-bottom:10px;
}

.card h2:hover{
  color:#2e7d32;
}

.card p{
  margin-bottom:10px;
  color:#444;
}

section{
  margin-top:40px;
}

footer{
  text-align:center;
  padding:25px;
  color:#888;
  border-top:1px solid #eee;
  margin-top:30px;
}
html{scroll-behavior:smooth;}
</style>

</head>
<body>

<header>
<h1>#DeCarbonize Notices</h1>
<p>Tu estilo de vida sostenible</p>
</header>

<nav>
<a href="#inicio">Inicio</a>
<a href="#problemas">Problemas</a>
<a href="#soluciones">Soluciones</a>
<a href="#acciones">Acciones</a>
</nav>

<div class="container">

<section id="inicio">
<div class="card">
<h2>Bienvenida</h2>
<p>Este espacio reúne noticias y reflexiones sobre el cuidado ambiental.</p>
</div>
</section>

<section id="problemas">
<div class="card">
<h2>Contaminación urbana en aumento</h2>
<p>Los niveles de contaminación crecen y obligan a replantear políticas actuales.</p>
<p>Empresas como Microsoft trabajan en reducir emisiones.</p>
</div>

<div class="card">
<h2>Deforestación sin freno</h2>
<p>La tala continúa generando desequilibrio ambiental.</p>
<p>Natura invierte en proteger la Amazonía.</p>
</div>

<div class="card">
<h2>Problema del plástico</h2>
<p>El uso excesivo sigue siendo un desafío global.</p>
<p>Nestlé busca reducir envases contaminantes.</p>
</div>
</section>

<section id="soluciones">
<div class="card">
<h2>Energías renovables en expansión</h2>
<p>Las energías limpias crecen, aunque no lo suficiente.</p>
<p>Acciona desarrolla proyectos sostenibles.</p>
</div>

<div class="card">
<h2>Reciclaje en evolución</h2>
<p>El reciclaje avanza, pero aún presenta desafíos.</p>
<p>Grupo Bimbo impulsa economía circular.</p>
</div>

<div class="card">
<h2>Reforestación en aumento</h2>
<p>Se plantan más árboles como estrategia ambiental.</p>
<p>Empresas compensan emisiones.</p>
</div>
</section>

<section id="acciones">
<div class="card">
<h2>Consumo responsable</h2>
<p>Las personas modifican hábitos de compra.</p>
<p>Patagonia promueve reutilización.</p>
</div>

<div class="card">
<h2>Transporte sostenible</h2>
<p>Se adoptan nuevas formas de movilidad.</p>
<p>Mercado Libre impulsa logística verde.</p>
</div>

<div class="card">
<h2>Educación ambiental</h2>
<p>La educación es clave para el cambio.</p>
<p>Coca-Cola impulsa programas educativos.</p>
</div>
</section>

</div>

<footer>
© 2026 - Noticias Ambientales | Derechos reservados TGS y Manuel
</footer>


<!-- PANEL FUNCIONES (sin modificar contenido existente) -->
<div style="position:fixed;bottom:10px;right:10px;background:#fff;border:1px solid #ddd;padding:10px;border-radius:8px;font-size:12px;">
  <div>Visitas: <span id="visitas"></span></div>
  <button onclick="toggleModo()">Modo oscuro</button><br><br>
  <input type="text" placeholder="Buscar..." onkeyup="buscar(this.value)">
</div>

<style>
.dark{background:#111;color:#eee}

/* BOTONES Y BUSCADOR MINIMALISTAS */
button{
  background:#ffffff;
  border:1px solid #ddd;
  padding:6px 10px;
  border-radius:6px;
  font-size:12px;
  cursor:pointer;
  transition:0.2s;
}

button:hover{
  background:#f5f5f5;
  border-color:#2e7d32;
  color:#2e7d32;
}

input{
  border:1px solid #ddd;
  padding:6px 8px;
  border-radius:6px;
  font-size:12px;
  outline:none;
  transition:0.2s;
}

input:focus{
  border-color:#2e7d32;
}
.featured{font-size:1.2em;border-left:4px solid #2e7d32;padding-left:10px}
</style>

<script>
document.addEventListener("DOMContentLoaded",()=>{

// 1. Contador visitas
let visitas = localStorage.getItem("visitas") || 0;
visitas++;
localStorage.setItem("visitas", visitas);
document.getElementById("visitas").innerText = visitas;

// 2. Modo oscuro
window.toggleModo = function(){
  document.body.classList.toggle("dark");
}

// 3. Buscador
window.buscar = function(texto){
  let cards = document.querySelectorAll(".card");
  cards.forEach(c => {
    c.style.display = c.innerText.toLowerCase().includes(texto.toLowerCase()) ? "block" : "none";
  });
}

// 5. Favoritos
let cards = document.querySelectorAll(".card");
cards.forEach((card,i)=>{
  let btn=document.createElement("button");
  btn.textContent="⭐ Guardar";
  btn.onclick=()=>{
    localStorage.setItem("fav_"+i,card.innerText);
    btn.textContent="✔ Guardado";
  };
  card.appendChild(btn);
});

// 6. Animación scroll
window.addEventListener("scroll",()=>{
  document.querySelectorAll(".card").forEach(card=>{
    let top=card.getBoundingClientRect().top;
    if(top<window.innerHeight){
      card.style.opacity=1;
      card.style.transform="translateY(0)";
    }
  });
});

// estado inicial animación
cards.forEach(card=>{
  card.style.opacity=0;
  card.style.transform="translateY(20px)";
  card.style.transition="0.5s";
});

// 7. Noticia destacada
if(cards[0]){
  cards[0].classList.add("featured");
}

});
</script>

</body>
</html>
