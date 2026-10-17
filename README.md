# MOSA-A-
prototipo 
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MOSAÏA — Capas. Texturas. Tiempo.</title>
<meta name="description" content="Postres artesanales en vaso. Ediciones limitadas en Culhuacán y Coyoacán, CDMX.">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;1,300;1,400&family=Inter:wght@300;400;500&display=swap" rel="stylesheet">
<style>
:root{
  --negro:#0e0d0b;--negro-suave:#161412;--hueso:#f2ede4;
  --hueso-60:rgba(242,237,228,.6);--hueso-35:rgba(242,237,228,.35);--hueso-14:rgba(242,237,228,.14);
  --jamaica:#6e1423;--jamaica-osc:#3f0b14;--ocre:#d9a441;--rojo:#b0413e;
  --serif:'Cormorant Garamond',serif;--sans:'Inter',sans-serif;
}
*{margin:0;padding:0;box-sizing:border-box}
html{scroll-behavior:smooth}
body{background:var(--negro);color:var(--hueso);font-family:var(--sans);font-weight:300;line-height:1.7;overflow-x:hidden}
[hidden]{display:none!important}
::selection{background:var(--jamaica);color:var(--hueso)}
.grain{position:fixed;inset:-100%;width:300%;height:300%;
  background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='300' height='300'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='2'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.55'/%3E%3C/svg%3E");
  opacity:.045;pointer-events:none;z-index:2000;animation:grain 7s steps(8) infinite}
@keyframes grain{0%,100%{transform:translate(0,0)}20%{transform:translate(-3%,2%)}40%{transform:translate(2%,-3%)}60%{transform:translate(-2%,-2%)}80%{transform:translate(3%,3%)}}
.wrap{max-width:1100px;margin:0 auto;padding:0 28px}
.label{font-size:11px;font-weight:400;letter-spacing:.32em;text-transform:uppercase;color:var(--hueso-60)}
hr.hair{border:none;border-top:1px solid var(--hueso-14)}
.reveal{opacity:0;transform:translateY(28px);transition:opacity 1s cubic-bezier(.22,.61,.36,1),transform 1s cubic-bezier(.22,.61,.36,1)}
.reveal.visible{opacity:1;transform:none}
@media(prefers-reduced-motion:reduce){.reveal{opacity:1;transform:none;transition:none}.grain{animation:none}}

/* NAV */
nav{position:fixed;top:0;left:0;right:0;z-index:1000;padding:22px 28px;display:flex;justify-content:space-between;align-items:center;transition:.5s}
nav.scrolled{background:rgba(14,13,11,.82);backdrop-filter:blur(14px);padding:14px 28px;border-bottom:1px solid var(--hueso-14)}
.nav-logo{font-family:var(--serif);font-size:20px;letter-spacing:.38em;text-transform:uppercase;color:var(--hueso);text-decoration:none}
.nav-links{display:flex;gap:30px;list-style:none;align-items:center}
.nav-links a{font-size:11px;letter-spacing:.22em;text-transform:uppercase;color:var(--hueso-60);text-decoration:none;transition:color .4s}
.nav-links a:hover{color:var(--hueso)}
.acceso{border:1px solid var(--hueso-14);padding:8px 14px;color:var(--hueso-35)!important}
.acceso:hover{color:var(--hueso)!important;border-color:var(--hueso-35)}
@media(max-width:760px){.nav-links li:not(:last-child){display:none}}

/* HERO */
.hero{min-height:100vh;display:flex;flex-direction:column;justify-content:center;align-items:center;text-align:center;position:relative;padding:0 24px}
.hero::before{content:'';position:absolute;inset:0;background:radial-gradient(ellipse 60% 40% at 50% 68%,rgba(110,20,35,.16),transparent 70%),radial-gradient(ellipse 40% 30% at 50% 30%,rgba(217,164,65,.05),transparent 70%)}
.hero .label{margin-bottom:34px}
.hero h1{font-family:var(--serif);font-weight:300;font-size:clamp(56px,11vw,150px);letter-spacing:clamp(.18em,.3vw,.34em);text-transform:uppercase;line-height:1;padding-left:.3em}
.hero .tagline{font-family:var(--serif);font-style:italic;font-size:clamp(19px,2.6vw,28px);color:var(--hueso-60);margin-top:30px}
.hero .ubicacion{margin-top:46px;font-size:11px;letter-spacing:.28em;text-transform:uppercase;color:var(--hueso-35)}
.scroll-hint{position:absolute;bottom:36px;left:50%;width:1px;height:64px;background:linear-gradient(var(--hueso-35),transparent);animation:caer 2.4s ease-in-out infinite}
@keyframes caer{0%{transform:translateX(-50%) scaleY(0);transform-origin:top}45%{transform:translateX(-50%) scaleY(1);transform-origin:top}55%{transform:translateX(-50%) scaleY(1);transform-origin:bottom}100%{transform:translateX(-50%) scaleY(0);transform-origin:bottom}}

section{padding:120px 0}
.section-head{margin-bottom:60px}
.section-head .num{font-family:var(--serif);font-style:italic;color:var(--hueso-35);font-size:15px}
.section-head h2{font-family:var(--serif);font-weight:300;font-size:clamp(34px,5vw,58px);line-height:1.15;margin-top:14px}

/* MANIFIESTO */
.manifiesto p{font-family:var(--serif);font-weight:300;font-size:clamp(24px,3.6vw,40px);line-height:1.5;max-width:820px}
.manifiesto p+p{margin-top:38px}
.manifiesto .acento{font-style:italic}
.manifiesto .tenue{color:var(--hueso-35)}

/* VASO */
.vaso-grid{display:grid;grid-template-columns:1fr 1fr;gap:70px;align-items:center}
@media(max-width:820px){.vaso-grid{grid-template-columns:1fr;gap:56px}}
.escena{display:flex;flex-direction:column;align-items:center;gap:34px}
.glass{position:relative;width:min(250px,68vw);height:360px;border:1px solid var(--hueso-14);border-radius:16px 16px 30px 30px;display:flex;flex-direction:column-reverse;overflow:hidden;box-shadow:0 40px 80px rgba(0,0,0,.5),inset 0 0 40px rgba(0,0,0,.25);background:linear-gradient(105deg,rgba(242,237,228,.045) 0%,transparent 30%,transparent 70%,rgba(242,237,228,.03) 100%)}
.glass::after{content:'';position:absolute;top:0;bottom:0;left:14%;width:2px;background:linear-gradient(rgba(242,237,228,.28),rgba(242,237,228,.04))}
.layer{width:100%;position:relative;cursor:pointer;transition:filter .5s,background 1s;transform-origin:bottom;animation:llenar 1.4s cubic-bezier(.22,.61,.36,1) both}
@keyframes llenar{from{transform:scaleY(0)}to{transform:scaleY(1)}}
.layer:nth-child(1){animation-delay:.2s}.layer:nth-child(2){animation-delay:.55s}.layer:nth-child(3){animation-delay:.9s}
.layer.dim{filter:brightness(.4) saturate(.6)}.layer.lit{filter:brightness(1.12)}
.layer[data-l="1"]{height:27%;background:linear-gradient(180deg,var(--c1a),var(--c1b))}
.layer[data-l="2"]{height:21%;background:linear-gradient(180deg,var(--c2a),var(--c2b))}
.layer[data-l="3"]{height:36%;background:linear-gradient(180deg,var(--c3a),var(--c3b))}
.layer[data-l="2"]::before{content:'';position:absolute;inset:0;background:radial-gradient(6px 4px at 20% 40%,rgba(0,0,0,.22),transparent 70%),radial-gradient(8px 5px at 65% 60%,rgba(0,0,0,.18),transparent 70%),radial-gradient(5px 4px at 85% 30%,rgba(255,255,255,.14),transparent 70%)}
.leyenda{list-style:none;width:min(300px,80vw)}
.leyenda li{display:flex;align-items:baseline;gap:16px;padding:15px 4px;border-bottom:1px solid var(--hueso-14);cursor:pointer;transition:.4s}
.leyenda li:first-child{border-top:1px solid var(--hueso-14)}
.leyenda li:hover,.leyenda li.lit{padding-left:14px;background:rgba(242,237,228,.03)}
.leyenda .dot{width:9px;height:9px;border-radius:50%;flex-shrink:none;position:relative;top:1px}
.leyenda .nombre{font-family:var(--serif);font-size:19px}
.leyenda .desc{margin-left:auto;font-size:11px;color:var(--hueso-35);text-align:right}
.sabores-toggle{display:flex;gap:12px;flex-wrap:wrap;justify-content:center}
.sabores-toggle button{font-family:var(--sans);font-size:11px;letter-spacing:.22em;text-transform:uppercase;background:transparent;color:var(--hueso-60);border:1px solid var(--hueso-14);padding:12px 22px;cursor:pointer;transition:.45s}
.sabores-toggle button:hover{color:var(--hueso);border-color:var(--hueso-35)}
.sabores-toggle button.activo{color:var(--negro);background:var(--hueso);border-color:var(--hueso)}
.texto-vaso h3{font-family:var(--serif);font-weight:300;font-size:clamp(26px,3.4vw,36px);margin-bottom:22px}
.texto-vaso p{color:var(--hueso-60);max-width:440px}
.texto-vaso .nota{margin-top:34px;font-family:var(--serif);font-style:italic;color:var(--hueso-35);font-size:17px}

/* SABORES */
.sabores-grid{display:grid;grid-template-columns:1fr 1fr;gap:26px}
@media(max-width:820px){.sabores-grid{grid-template-columns:1fr}}
.sabor-card{position:relative;border:1px solid var(--hueso-14);padding:52px 44px;min-height:340px;display:flex;flex-direction:column;overflow:hidden;transition:border-color .5s}
.sabor-card:hover{border-color:var(--hueso-35)}
.sabor-card::before{content:'';position:absolute;inset:auto -30% -50% -30%;height:80%;background:radial-gradient(ellipse at center,var(--glow),transparent 70%);opacity:.5;transition:opacity .6s;pointer-events:none}
.sabor-card:hover::before{opacity:.9}
.sabor-card .idx{font-family:var(--serif);font-style:italic;color:var(--hueso-35);font-size:14px}
.sabor-card h3{font-family:var(--serif);font-weight:300;font-size:clamp(30px,4vw,44px);margin:20px 0 8px}
.sabor-card .sub{font-family:var(--serif);font-style:italic;color:var(--hueso-60);font-size:19px;margin-bottom:26px}
.sabor-card .notas{list-style:none;margin-top:auto}
.sabor-card .notas li{font-size:11px;letter-spacing:.24em;text-transform:uppercase;color:var(--hueso-35);padding:11px 0;border-top:1px solid var(--hueso-14)}
.sabor-card .estado{display:inline-block;margin-top:26px;font-size:10px;letter-spacing:.28em;text-transform:uppercase;color:var(--hueso-35);border:1px solid var(--hueso-14);padding:8px 14px;align-self:flex-start}

/* PEDIDOS + FOOTER */
.pedidos .inner{border:1px solid var(--hueso-14);padding:clamp(44px,7vw,90px);text-align:center;position:relative;overflow:hidden}
.pedidos .inner::before{content:'';position:absolute;inset:0;background:radial-gradient(ellipse 70% 60% at 50% 110%,rgba(110,20,35,.18),transparent 70%)}
.pedidos h2{font-family:var(--serif);font-weight:300;font-size:clamp(32px,5vw,52px);line-height:1.2}
.pedidos .zona{margin:26px auto 0;max-width:480px;color:var(--hueso-60)}
#estado-edicion{margin-top:18px;font-family:var(--serif);font-style:italic;color:var(--ocre);font-size:17px;position:relative}
.cta-row{display:flex;gap:16px;justify-content:center;margin-top:44px;flex-wrap:wrap;position:relative}
.btn{font-family:var(--sans);font-size:11px;letter-spacing:.26em;text-transform:uppercase;padding:17px 36px;text-decoration:none;transition:.45s;display:inline-block;cursor:pointer;border:none}
.btn-solid{background:var(--hueso);color:var(--negro);border:1px solid var(--hueso)}
.btn-solid:hover{background:transparent;color:var(--hueso)}
.btn-ghost{background:transparent;color:var(--hueso-60);border:1px solid var(--hueso-14)}
.btn-ghost:hover{color:var(--hueso);border-color:var(--hueso-35)}
.btn.sm{padding:11px 22px;font-size:10px}
.pedidos .aviso{margin-top:34px;font-size:11px;letter-spacing:.2em;text-transform:uppercase;color:var(--hueso-35);position:relative}
footer{padding:90px 0 50px;border-top:1px solid var(--hueso-14)}
.footer-word{font-family:var(--serif);font-weight:300;text-transform:uppercase;font-size:clamp(44px,10vw,120px);letter-spacing:.3em;color:rgba(242,237,228,.06);text-align:center;user-select:none;padding-left:.3em}
.footer-meta{display:flex;justify-content:space-between;gap:20px;margin-top:60px;flex-wrap:wrap}
.footer-meta span,.footer-meta a{font-size:11px;letter-spacing:.24em;text-transform:uppercase;color:var(--hueso-35);text-decoration:none;transition:color .4s}
.footer-meta a:hover{color:var(--hueso)}

/* ===== PORTAL ===== */
.login{position:fixed;inset:0;background:rgba(10,9,8,.94);z-index:3000;display:flex;align-items:center;justify-content:center;backdrop-filter:blur(8px)}
.login-card{border:1px solid var(--hueso-14);padding:44px;max-width:420px;width:92%;background:var(--negro-suave)}
.rolesel{display:flex;gap:8px;margin:22px 0 8px}
.rolesel button{flex:1;background:none;border:1px solid var(--hueso-14);color:var(--hueso-60);padding:11px 4px;font-size:10px;letter-spacing:.16em;text-transform:uppercase;cursor:pointer;font-family:var(--sans);transition:.4s}
.rolesel button.activo{background:var(--hueso);color:var(--negro);border-color:var(--hueso)}
.hint{font-size:11px;color:var(--hueso-35);margin-top:10px;letter-spacing:.1em}
.cerrar{margin-top:26px;background:none;border:none;color:var(--hueso-35);cursor:pointer;font-size:11px;letter-spacing:.2em;text-transform:uppercase;width:100%;font-family:var(--sans)}
.cerrar:hover{color:var(--hueso)}
label{font-size:10px;letter-spacing:.24em;text-transform:uppercase;color:var(--hueso-35);display:block;margin:18px 0 6px}
input,select,textarea{background:transparent;border:1px solid var(--hueso-14);color:var(--hueso);font-family:var(--sans);font-size:14px;font-weight:300;padding:12px 14px;width:100%;transition:border-color .4s}
input:focus,select:focus,textarea:focus{outline:none;border-color:var(--hueso-35)}
select option{background:var(--negro)}
.pbar{display:flex;justify-content:space-between;align-items:center;gap:16px;padding:18px 28px;border-bottom:1px solid var(--hueso-14);position:sticky;top:0;background:rgba(14,13,11,.92);backdrop-filter:blur(12px);z-index:900}
#quien{font-size:11px;letter-spacing:.24em;text-transform:uppercase;color:var(--hueso-60)}
.tabs{display:flex;gap:8px;flex-wrap:wrap;padding:24px 28px 0}
.tab{background:none;border:1px solid var(--hueso-14);color:var(--hueso-60);padding:9px 18px;font-size:10px;letter-spacing:.2em;text-transform:uppercase;cursor:pointer;transition:.4s;font-family:var(--sans)}
.tab:hover{color:var(--hueso)}
.tab.activo{background:var(--hueso);color:var(--negro);border-color:var(--hueso)}
#panel{padding:44px 0 90px}
.card{border:1px solid var(--hueso-14);padding:30px;margin-bottom:20px}
.cardhead{display:flex;justify-content:space-between;align-items:center;gap:14px;flex-wrap:wrap}
.cardhead h3{font-family:var(--serif);font-weight:300;font-size:24px}
.sub2{color:var(--hueso-35);font-size:13px;margin-top:6px}
.notar{font-family:var(--serif);font-style:italic;color:var(--hueso-60);margin-top:14px}
.cols2{display:grid;grid-template-columns:1fr 1fr;gap:26px;margin:20px 0}
@media(max-width:640px){.cols2{grid-template-columns:1fr}}
.row2{display:grid;grid-template-columns:repeat(auto-fit,minmax(160px,1fr));gap:16px;align-items:end}
.lista{list-style:none}.lista li{font-size:14px;color:var(--hueso-60);padding:7px 0;border-bottom:1px solid var(--hueso-14)}
ol.lista{padding-left:18px;list-style:decimal}
.obs li{font-size:13px;color:var(--hueso-60);padding:8px 0;border-top:1px solid var(--hueso-14);list-style:none}
.obs li span{color:var(--hueso-35);font-size:11px;margin-right:10px}
.vacio{color:var(--hueso-35);font-size:13px}
.badge{font-size:10px;letter-spacing:.2em;text-transform:uppercase;border:1px solid var(--hueso-14);padding:5px 10px;color:var(--hueso-60);white-space:nowrap}
.badge.ok{color:var(--ocre);border-color:var(--ocre)}
.badge.bad{color:var(--rojo);border-color:var(--rojo)}
.linkdel{background:none;border:none;color:var(--hueso-35);font-size:10px;letter-spacing:.2em;text-transform:uppercase;cursor:pointer;margin-top:14px;font-family:var(--sans)}
.linkdel:hover{color:var(--rojo)}
table.p{width:100%;border-collapse:collapse;font-size:13.5px;margin:10px 0 20px}
table.p th{font-size:10px;letter-spacing:.2em;text-transform:uppercase;color:var(--hueso-35);text-align:left;padding:10px;border-bottom:1px solid var(--hueso-14)}
table.p td{padding:12px 10px;border-top:1px solid var(--hueso-14);color:var(--hueso-60)}
.kpis{display:grid;grid-template-columns:repeat(auto-fit,minmax(150px,1fr));gap:1px;background:var(--hueso-14);border:1px solid var(--hueso-14);margin-bottom:14px}
.kpi{background:var(--negro);padding:24px;display:flex;flex-direction:column;gap:10px}
.kpi .v{font-family:var(--serif);font-size:30px}
.p-h{font-family:var(--serif);font-weight:300;font-size:24px;margin:34px 0 16px}
.bars{display:flex;align-items:flex-end;gap:10px;height:130px;border-bottom:1px solid var(--hueso-14);padding-bottom:0}
.bcol{flex:1;display:flex;flex-direction:column;justify-content:flex-end;align-items:center;gap:8px;height:100%}
.bcol i{width:100%;display:block;background:linear-gradient(var(--jamaica),var(--jamaica-osc));min-height:2px;transition:height .8s}
.bcol span{font-size:10px;color:var(--hueso-35)}
.incid{padding:12px 0;border-top:1px solid var(--hueso-14);font-size:14px}
.fecha{color:var(--hueso-35);font-size:11px;margin-left:8px}
.idea{display:flex;gap:14px;align-items:center;flex-wrap:wrap}
details summary{font-family:var(--serif);font-size:22px;cursor:pointer;list-style:none;display:flex;justify-content:space-between;align-items:center;gap:14px}
details summary::-webkit-details-marker{display:none}
</style>
</head>
<body>
<div class="grain" aria-hidden="true"></div>

<!-- ============ PÚBLICO ============ -->
<nav id="nav">
  <a class="nav-logo" href="#top">Mosaïa</a>
  <ul class="nav-links">
    <li><a href="#manifiesto">Manifiesto</a></li>
    <li><a href="#vaso">El vaso</a></li>
    <li><a href="#sabores">Sabores</a></li>
    <li><a href="#pedidos">Pedidos</a></li>
    <li><a href="#" onclick="abrirLogin();return false">Acceso</a></li>
  </ul>
</nav>

<main id="publico">
<header class="hero" id="top">
  <p class="label reveal">Postres artesanales en vaso</p>
  <h1 class="reveal">Mosaïa</h1>
  <p class="tagline reveal">Capas. Texturas. Tiempo.</p>
  <p class="ubicacion reveal">Culhuacán · Coyoacán · Ciudad de México</p>
  <div class="scroll-hint" aria-hidden="true"></div>
</header>

<section id="manifiesto" class="manifiesto">
  <div class="wrap">
    <div class="section-head reveal"><span class="num">01</span><h2>Manifiesto</h2></div>
    <p class="reveal">No es una gelatina. No es un yogurt. <span class="tenue">Es lo que queda cuando decides que un postre puede tener</span> <span class="acento">capas, silencios y texturas.</span></p>
    <p class="reveal">Producimos poco. Probamos mucho. <span class="tenue">Algunas combinaciones se quedan. Otras se van.</span> <span class="acento">Así se construye algo honesto.</span></p>
  </div>
</section>
<hr class="hair">

<section id="vaso">
  <div class="wrap">
    <div class="section-head reveal"><span class="num">02</span><h2>El vaso, por dentro</h2></div>
    <div class="vaso-grid">
      <div class="escena reveal">
        <div class="glass" id="glass">
          <div class="layer" data-l="1"></div><div class="layer" data-l="2"></div><div class="layer" data-l="3"></div>
        </div>
        <ul class="leyenda" id="leyenda"></ul>
        <div class="sabores-toggle">
          <button id="btn-pj" class="activo">Piña + Jamaica</button>
          <button id="btn-pc">Plátano + Café</button>
        </div>
      </div>
      <div class="texto-vaso reveal">
        <h3 id="vaso-titulo"></h3><p id="vaso-texto"></p><p class="nota" id="vaso-nota"></p>
      </div>
    </div>
  </div>
</section>
<hr class="hair">

<section id="sabores">
  <div class="wrap">
    <div class="section-head reveal"><span class="num">03</span><h2>Sabores en prueba</h2></div>
    <div class="sabores-grid">
      <article class="sabor-card reveal" style="--glow:rgba(110,20,35,.35)">
        <span class="idx">N.º 01</span><h3>Piña + Jamaica</h3>
        <p class="sub">Ácido. Dulce. Floral. Todo al mismo tiempo.</p>
        <ul class="notas"><li>Acidez — brillante</li><li>Cuerpo — cremoso</li><li>Final — floral</li></ul>
        <span class="estado">En validación</span>
      </article>
      <article class="sabor-card reveal" style="--glow:rgba(62,42,32,.6)">
        <span class="idx">N.º 02</span><h3>Plátano + Café</h3>
        <p class="sub">Lo amargo y lo dulce no se pelean. Se reconocen.</p>
        <ul class="notas"><li>Entrada — tostada</li><li>Cuerpo — maduro</li><li>Final — redondo</li></ul>
        <span class="estado">En validación</span>
      </article>
    </div>
  </div>
</section>

<section id="pedidos" class="pedidos">
  <div class="wrap">
    <div class="inner reveal">
      <span class="label" style="display:block;margin-bottom:24px">04 — Pedidos</span>
      <h2>Pocos vasos.<br>Cada semana.</h2>
      <p class="zona">Entregas en Culhuacán y zonas cercanas de Coyoacán, Ciudad de México.</p>
      <p id="estado-edicion"></p>
      <div class="cta-row">
        <a class="btn btn-solid" id="wa-publico" href="#" target="_blank" rel="noopener">Apartar un vaso</a>
        <a class="btn btn-ghost" href="https://www.instagram.com/mosaia.mx" target="_blank" rel="noopener">Instagram</a>
      </div>
      <p class="aviso">Se anuncian los lunes · Se agotan cuando se agotan</p>
    </div>
  </div>
</section>

<footer>
  <div class="wrap">
    <div class="footer-word" aria-hidden="true">Mosaïa</div>
    <div class="footer-meta">
      <span>© MMXXVI — Hecho despacio en Coyoacán</span>
      <span><a href="https://www.instagram.com/mosaia.mx" target="_blank" rel="noopener">@mosaia.mx</a></span>
      <span><a href="#" onclick="abrirLogin();return false">Acceso</a></span>
    </div>
  </div>
</footer>
</main>

<!-- ============ LOGIN ============ -->
<div class="login" id="login" hidden>
  <div class="login-card">
    <p class="label">Acceso interno</p>
    <div class="rolesel">
      <button class="activo" onclick="rolTab('d',this)">Distribuidor</button>
      <button onclick="rolTab('e',this)">Equipo</button>
      <button onclick="rolTab('f',this)">Fundador</button>
    </div>
    <form id="f-d" onsubmit="return loginD(event)">
      <label>Código de punto</label><input name="codigo" placeholder="MOSA-01" autocomplete="off">
      <button class="btn btn-solid sm" style="width:100%;margin-top:22px">Entrar</button>
    </form>
    <form id="f-e" hidden onsubmit="return loginE(event)">
      <label>Tu nombre</label><input name="nombre" autocomplete="off">
      <button class="btn btn-solid sm" style="width:100%;margin-top:22px">Entrar</button>
    </form>
    <form id="f-f" hidden onsubmit="return loginF(event)">
      <label>PIN</label><input name="pin" type="password" autocomplete="off">
      <p class="hint">PIN de demostración: 1234</p>
      <button class="btn btn-solid sm" style="width:100%;margin-top:22px">Entrar</button>
    </form>
    <button class="cerrar" onclick="cerrarLogin()">Cerrar</button>
  </div>
</div>

<!-- ============ PORTAL ============ -->
<div id="portal" hidden>
  <div class="pbar">
    <span class="nav-logo">Mosaïa</span>
    <span id="quien"></span>
    <button class="btn btn-ghost sm" onclick="salir()">Salir</button>
  </div>
  <div class="tabs" id="tabs"></div>
  <div class="wrap" id="panel"></div>
</div>

<script>
/* ================= BASE DE DATOS (localStorage) ================= */
const KEY='mosaia_db_v2', SES='mosaia_ses';
const $=s=>document.querySelector(s);
const uid=()=>Math.random().toString(36).slice(2,9);
const hoy=()=>new Date().toISOString().slice(0,10);
const fN=n=>'$'+Number(n||0).toLocaleString('es-MX',{maximumFractionDigits:0});
const esc=s=>(s==null?'':String(s)).replace(/[&<>"']/g,c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c]));
const kpi=(l,v)=>`<div class="kpi"><span class="label">${l}</span><span class="v">${v}</span></div>`;

function seed(){return{
 config:{pin:'1234',wa:'52XXXXXXXXXX'},
 edicion:{abierta:true,sab:{'Piña + Jamaica':12,'Plátano + Café':8}},
 dists:[
  {id:uid(),nombre:'Café La Polvareda',contacto:'Lucía',dir:'Av. Universidad 210, Coyoacán',codigo:'MOSA-01'},
  {id:uid(),nombre:'Punto Nueve',contacto:'Andrés',dir:'Culhuacán',codigo:'MOSA-02'}],
 recetas:[
  {id:uid(),nombre:'Piña + Jamaica',estado:'Prometedora',
   ing:['500 g piña madura','15 flores de jamaica','400 g yogurt natural','6 g grenetina','60 ml agua fría','2 cdas azúcar de caña'],
   pasos:['Hidratar grenetina en agua fría 10 min.','Infusionar jamaica, colar, endulzar e incorporar grenetina. Enfriar en vaso (capa 1).','Cocinar piña con su azúcar hasta compota. Enfriar (capa 2).','Montar yogurt frío (capa 3). Reposar 6 h.'],
   notas:'La jamaica no debe hervirse más de 5 min o amarga.',
   obs:[{f:hoy(),t:'Prueba con menos azúcar: más limpia. Repetir con 1.5 cda.'}]},
  {id:uid(),nombre:'Plátano + Café',estado:'En prueba',
   ing:['2 plátanos maduros','30 ml café de olla concentrado','400 g yogurt','6 g grenetina','1 cda panela'],
   pasos:['Gelatina de café: disolver panela en café caliente + grenetina. Enfriar.','Caramelizar plátano sin quemar. Enfriar.','Montar yogurt. Reposar 6 h.'],
   notas:'El plátano se oxida rápido: caramelizar al momento.',obs:[]}],
 pruebas:[{id:uid(),f:hoy(),rec:'Piña + Jamaica',lote:6,res:'Compota demasiado líquida; la capa se mezcló con el yogurt.',ver:'Repetir'}],
 ideas:[{id:uid(),f:hoy(),t:'Edición de temporada: mandarina + chipotle (invierno).',tag:'Temporada'}],
 ventas:[{id:uid(),f:hoy(),canal:'Directo',vasos:9,monto:810},{id:uid(),f:hoy(),canal:'Cafetería',vasos:6,monto:510}],
 prod:[{id:uid(),f:hoy(),sabor:'Piña + Jamaica',vasos:12,merma:1,min:95,quien:'Equipo'}],
 pedidos:[],incid:[]};}

let db;
try{db=JSON.parse(localStorage.getItem(KEY))||seed()}catch(e){db=seed()}
const save=()=>localStorage.setItem(KEY,JSON.stringify(db));
const fd=e=>{const d=Object.fromEntries(new FormData(e.target));e.preventDefault();return d};

/* ================= SESIÓN ================= */
const sesion=()=>{try{return JSON.parse(sessionStorage.getItem(SES))}catch(e){return null}};
const entrar=(rol,d)=>{sessionStorage.setItem(SES,JSON.stringify({rol,...d}));location.reload()};
const salir=()=>{sessionStorage.removeItem(SES);location.reload()};

function abrirLogin(){$('#login').hidden=false}
function cerrarLogin(){$('#login').hidden=true}
function rolTab(r,btn){['d','e','f'].forEach(x=>$('#f-'+x).hidden=x!==r);document.querySelectorAll('.rolesel button').forEach(b=>b.classList.remove('activo'));btn.classList.add('activo')}
function loginD(e){const d=fd(e);const dist=db.dists.find(x=>x.codigo.toUpperCase()===(d.codigo||'').trim().toUpperCase());if(!dist){alert('Código no reconocido.');return false}entrar('dist',{id:dist.id,nombre:dist.nombre});return false}
function loginE(e){const d=fd(e);if(!d.nombre){alert('Escribe tu nombre.');return false}entrar('equipo',{nombre:d.nombre});return false}
function loginF(e){const d=fd(e);if(d.pin!==db.config.pin){alert('PIN incorrecto.');return false}entrar('founder',{});return false}

/* ================= RUTEADOR DEL PORTAL ================= */
const TABS={
 founder:['Resumen','Recetas','Pruebas','Ideas','Distribuidores','Producción y ventas'],
 dist:['Mi edición','Hacer pedido','Mis pedidos','Incidencias'],
 equipo:['Recetario','Producir','Rendimiento']};
const PANE={};
let tabActiva='';
function ir(t){tabActiva=t;renderTabs();render()}
function renderTabs(){const s=sesion();$('#tabs').innerHTML=TABS[s.rol].map(t=>`<button class="tab ${t===tabActiva?'activo':''}" onclick="ir('${t}')">${t}</button>`).join('')}
function render(){const s=sesion();if(s)$('#panel').innerHTML=PANE[tabActiva]()}

/* ================= FUNDADOR ================= */
function chartVentas(){
 const dias=[...Array(7)].map((_,i)=>new Date(Date.now()-(6-i)*864e5).toISOString().slice(0,10));
 const tot=dias.map(d=>db.ventas.filter(v=>v.f===d).reduce((a,b)=>a+b.monto,0));
 const max=Math.max(...tot,1);
 return `<div class="bars">${dias.map((d,i)=>`<div class="bcol" title="${d}: ${fN(tot[i])}"><i style="height:${Math.max(2,Math.round(tot[i]/max*100))}%"></i><span>${d.slice(5)}</span></div>`).join('')}</div>`;
}
PANE['Resumen']=function(){
 const vp=db.prod.reduce((a,b)=>a+b.vasos,0),merma=db.prod.reduce((a,b)=>a+b.merma,0),
 vv=db.ventas.reduce((a,b)=>a+b.vasos,0),ing=db.ventas.reduce((a,b)=>a+b.monto,0),
 pa=db.pedidos.filter(x=>x.estado==='abierto').length,ia=db.incid.filter(x=>x.estado==='abierta').length;
 return `${kpi2('Vasos producidos',vp)}${kpi2('Vasos vendidos',vv)}${kpi2('Ingreso',fN(ing))}${kpi2('Merma',merma+' u')}${kpi2('Pedidos abiertos',pa)}${kpi2('Incidencias',ia)}
 <h3 class="p-h">Ingreso · últimos 7 días</h3>${chartVentas()}
 <div class="card" style="margin-top:30px"><p class="label">Edición actual</p>
  <form onsubmit="return guardarEdicion(event)"><div class="row2">
   <div><label>Abierta</label><select name="abierta"><option value="1" ${db.edicion.abierta?'selected':''}>Sí</option><option value="0" ${!db.edicion.abierta?'selected':''}>No</option></select></div>
   ${Object.keys(db.edicion.sab).map((k,i)=>`<div><label>${esc(k)} — vasos</label><input name="s${i}" type="number" min="0" value="${db.edicion.sab[k]}"></div>`).join('')}
  </div><button class="btn btn-solid sm" style="margin-top:20px">Guardar</button></form></div>
 <div class="card"><p class="label">Configuración</p>
  <form onsubmit="return guardarCfg(event)"><div class="row2">
   <div><label>PIN de fundador</label><input name="pin" value="${esc(db.config.pin)}"></div>
   <div><label>WhatsApp (lada + número)</label><input name="wa" value="${esc(db.config.wa)}"></div>
  </div><button class="btn btn-solid sm" style="margin-top:20px">Guardar</button></form></div>
 <div class="row2">
  <button class="btn btn-ghost sm" onclick="exportar()">Exportar respaldo</button>
  <label class="btn btn-ghost sm" style="cursor:pointer;text-align:center">Importar<input type="file" accept="application/json" onchange="importar(this)" hidden></label>
 </div>`;
};
const kpi2=(l,v)=>kpi(l,v);
function guardarEdicion(e){const d=fd(e);db.edicion.abierta=d.abierta==='1';Object.keys(db.edicion.sab).forEach((k,i)=>db.edicion.sab[k]=Math.max(0,+d['s'+i]||0));save();render();return false}
function guardarCfg(e){const d=fd(e);if(d.pin)db.config.pin=d.pin;if(d.wa)db.config.wa=d.wa.replace(/\D/g,'');save();render();return false}
function exportar(){const b=new Blob([JSON.stringify(db,null,2)],{type:'application/json'});const a=document.createElement('a');a.href=URL.createObjectURL(b);a.download='mosaia-respaldo.json';a.click()}
function importar(inp){const f=inp.files[0];if(!f)return;const r=new FileReader();r.onload=()=>{try{db=JSON.parse(r.result);save();render();alert('Respaldo importado.')}catch(e){alert('Archivo inválido.')}};r.readAsText(f)}

PANE['Recetas']=function(){
 const opts=['En prueba','Prometedora','Permanente','Descartada'];
 return `<form class="card" onsubmit="return agregarReceta(event)"><p class="label">Nueva receta</p>
 <label>Nombre</label><input name="nombre" required>
 <label>Estado</label><select name="estado">${opts.map(o=>`<option>${o}</option>`).join('')}</select>
 <label>Ingredientes (uno por línea)</label><textarea name="ing" rows="4"></textarea>
 <label>Pasos (uno por línea)</label><textarea name="pasos" rows="5"></textarea>
 <label>Nota del día</label><input name="notas">
 <button class="btn btn-solid sm" style="margin-top:20px">Guardar receta</button></form>
 ${db.recetas.map(r=>`<div class="card">
  <div class="cardhead"><h3>${esc(r.nombre)}</h3>
   <select style="width:auto" onchange="cambiarEstado('${r.id}',this.value)">${opts.map(o=>`<option ${o===r.estado?'selected':''}>${o}</option>`).join('')}</select></div>
  <div class="cols2">
   <div><p class="label">Ingredientes</p><ul class="lista">${r.ing.map(i=>`<li>${esc(i)}</li>`).join('')}</ul></div>
   <div><p class="label">Pasos</p><ol class="lista">${r.pasos.map(i=>`<li>${esc(i)}</li>`).join('')}</ol></div></div>
  ${r.notas?`<p class="notar">“${esc(r.notas)}”</p>`:''}
  <p class="label" style="margin-top:18px">Observaciones</p>
  <ul class="obs" style="list-style:none">${r.obs.map(o=>`<li><span>${o.f}</span>${esc(o.t)}</li>`).join('')||'<li class="vacio">Sin observaciones.</li>'}</ul>
  <form onsubmit="return agregarObs(event,'${r.id}')"><div class="row2"><input name="t" placeholder="Nueva observación…"><button class="btn btn-ghost sm">Añadir</button></div></form>
  <button class="linkdel" onclick="borrarReceta('${r.id}')">Eliminar receta</button></div>`).join('')}`;
};
function agregarReceta(e){const d=fd(e);db.recetas.unshift({id:uid(),nombre:d.nombre,estado:d.estado,ing:(d.ing||'').split('\n').filter(Boolean),pasos:(d.pasos||'').split('\n').filter(Boolean),notas:d.notas||'',obs:[]});save();render();return false}
function cambiarEstado(id,v){const r=db.recetas.find(x=>x.id===id);if(r){r.estado=v;save()}}
function agregarObs(e,id){const d=fd(e);const r=db.recetas.find(x=>x.id===id);if(r&&d.t){r.obs.unshift({f:hoy(),t:d.t});save();render()}return false}
function borrarReceta(id){if(confirm('¿Eliminar esta receta?')){db.recetas=db.recetas.filter(x=>x.id!==id);save();render()}}

PANE['Pruebas']=function(){
 return `<form class="card" onsubmit="return agregarPrueba(event)"><p class="label">Registrar prueba</p>
 <div class="row2">
  <div><label>Fecha</label><input type="date" name="f" value="${hoy()}"></div>
  <div><label>Receta</label><select name="rec">${db.recetas.map(r=>`<option>${esc(r.nombre)}</option>`).join('')}</select></div>
  <div><label>Lote (vasos)</label><input type="number" name="lote" value="6"></div>
  <div><label>Veredicto</label><select name="ver"><option>Repetir</option><option>Se queda</option><option>Se va</option></select></div></div>
 <label>Resultado / observaciones</label><textarea name="res" rows="3"></textarea>
 <button class="btn btn-solid sm" style="margin-top:18px">Guardar</button></form>
 <table class="p"><tr><th>Fecha</th><th>Receta</th><th>Lote</th><th>Resultado</th><th>Veredicto</th><th></th></tr>
 ${db.pruebas.map(p=>`<tr><td>${p.f}</td><td>${esc(p.rec)}</td><td>${p.lote}</td><td>${esc(p.res)}</td><td><span class="badge ${p.ver==='Se queda'?'ok':p.ver==='Se va'?'bad':''}">${p.ver}</span></td><td><button class="linkdel" style="margin:0" onclick="borrarPrueba('${p.id}')">×</button></td></tr>`).join('')||'<tr><td colspan="6" class="vacio">Sin pruebas registradas.</td></tr>'}</table>`;
};
function agregarPrueba(e){const d=fd(e);db.pruebas.unshift({id:uid(),f:d.f,rec:d.rec,lote:+d.lote||0,res:d.res||'',ver:d.ver});save();render();return false}
function borrarPrueba(id){db.pruebas=db.pruebas.filter(x=>x.id!==id);save();render()}

PANE['Ideas']=function(){
 return `<form class="card" onsubmit="return agregarIdea(event)"><p class="label">Captura rápida</p>
 <div class="row2"><div style="grid-column:span 2"><input name="t" placeholder="Idea…" required></div>
 <div><select name="tag"><option>Sabor</option><option>Temporada</option><option>Empaque</option><option>Comunicación</option></select></div>
 <div><button class="btn btn-solid sm">Guardar</button></div></div></form>
 ${db.ideas.map(i=>`<div class="card idea"><span class="badge">${esc(i.tag)}</span><span>${esc(i.t)}</span><span class="fecha">${i.f}</span><button class="linkdel" style="margin:0" onclick="borrarIdea('${i.id}')">×</button></div>`).join('')||'<p class="vacio">Sin ideas guardadas todavía.</p>'}`;
};
function agregarIdea(e){const d=fd(e);db.ideas.unshift({id:uid(),f:hoy(),t:d.t,tag:d.tag});save();render();return false}
function borrarIdea(id){db.ideas=db.ideas.filter(x=>x.id!==id);save();render()}

PANE['Distribuidores']=function(){
 return `<form class="card" onsubmit="return agregarDist(event)"><p class="label">Nuevo punto de distribución</p>
 <div class="row2"><div><label>Nombre</label><input name="nombre" required></div><div><label>Contacto</label><input name="contacto"></div><div><label>Dirección / zona</label><input name="dir"></div></div>
 <button class="btn btn-solid sm" style="margin-top:16px">Registrar</button></form>
 ${db.dists.map(d=>{const ped=db.pedidos.filter(x=>x.dist===d.id),inc=db.incid.filter(x=>x.dist===d.id);
 return `<div class="card">
  <div class="cardhead"><h3>${esc(d.nombre)}</h3><span class="badge">${d.codigo}</span></div>
  <p class="sub2">${esc(d.contacto||'—')} · ${esc(d.dir||'—')}</p>
  <p class="label" style="margin-top:18px">Pedidos (${ped.length})</p>
  ${ped.length?`<table class="p">${ped.slice().reverse().map(x=>`<tr><td>${x.f}</td><td>${x.items.map(i=>`${i.qty} × ${esc(i.sabor)}`).join(', ')}</td><td><span class="badge ${x.estado==='entregado'?'ok':''}">${x.estado}</span></td><td>${x.estado==='abierto'?`<button class="linkdel" style="margin:0" onclick="entregarPedido('${x.id}')">entregado</button>`:''}</td></tr>`).join('')}</table>`:'<p class="vacio">Sin pedidos.</p>'}
  <p class="label" style="margin-top:16px">Incidencias (${inc.length})</p>
  ${inc.length?inc.map(x=>`<div class="incid"><span class="badge ${x.estado==='resuelta'?'ok':'bad'}">${x.estado}</span> <b>${esc(x.tipo)}</b> — ${esc(x.desc)}<span class="fecha">${x.f}</span> ${x.estado==='abierta'?`<button class="linkdel" style="margin:0 0 0 10px" onclick="resolverIncid('${x.id}')">resolver</button>`:''}</div>`).join(''):'<p class="vacio">Sin incidencias.</p>'}
  <button class="linkdel" onclick="borrarDist('${d.id}')">Eliminar punto</button></div>`;}).join('')}`;
};
function agregarDist(e){const d=fd(e);db.dists.push({id:uid(),nombre:d.nombre,contacto:d.contacto||'',dir:d.dir||'',codigo:'MOSA-'+String(db.dists.length+1).padStart(2,'0')});save();render();return false}
function borrarDist(id){if(confirm('¿Eliminar este punto?')){db.dists=db.dists.filter(x=>x.id!==id);save();render()}}
function entregarPedido(id){const p=db.pedidos.find(x=>x.id===id);if(p){p.estado='entregado';save();render()}}
function resolverIncid(id){const i=db.incid.find(x=>x.id===id);if(i){i.estado='resuelta';save();render()}}

PANE['Producción y ventas']=function(){
 return `<form class="card" onsubmit="return agregarVenta(event)"><p class="label">Registrar venta</p>
 <div class="row2"><div><label>Fecha</label><input type="date" name="f" value="${hoy()}"></div>
 <div><label>Canal</label><select name="canal"><option>Directo</option><option>Cafetería</option><option>Evento</option></select></div>
 <div><label>Vasos</label><input type="number" name="vasos" value="1"></div>
 <div><label>Monto (MXN)</label><input type="number" name="monto" value="0"></div></div>
 <button class="btn btn-solid sm" style="margin-top:16px">Guardar</button></form>
 <p class="label">Ventas</p>
 <table class="p"><tr><th>Fecha</th><th>Canal</th><th>Vasos</th><th>Monto</th><th></th></tr>
 ${db.ventas.slice().reverse().map(v=>`<tr><td>${v.f}</td><td>${v.canal}</td><td>${v.vasos}</td><td>${fN(v.monto)}</td><td><button class="linkdel" style="margin:0" onclick="borrarVenta('${v.id}')">×</button></td></tr>`).join('')||'<tr><td colspan="5" class="vacio">Sin ventas.</td></tr>'}</table>
 <p class="label" style="margin-top:26px">Producción (registro del equipo)</p>
 <table class="p"><tr><th>Fecha</th><th>Sabor</th><th>Vasos</th><th>Merma</th><th>Min</th><th>Quién</th></tr>
 ${db.prod.slice().reverse().map(p=>`<tr><td>${p.f}</td><td>${esc(p.sabor)}</td><td>${p.vasos}</td><td>${p.merma}</td><td>${p.min}</td><td>${esc(p.quien)}</td></tr>`).join('')||'<tr><td colspan="6" class="vacio">Sin registros.</td></tr>'}</table>`;
};
function agregarVenta(e){const d=fd(e);db.ventas.push({id:uid(),f:d.f,canal:d.canal,vasos:+d.vasos||0,monto:+d.monto||0});save();render();return false}
function borrarVenta(id){db.ventas=db.ventas.filter(x=>x.id!==id);save();render()}

/* ================= DISTRIBUIDOR ================= */
PANE['Mi edición']=function(){
 const e=db.edicion;
 return e.abierta?`<div class="card"><p class="label">Edición abierta</p><ul class="lista">${Object.entries(e.sab).map(([k,v])=>`<li>${esc(k)} — ${v} vasos disponibles</li>`).join('')}</ul><p class="notar">Los pedidos se cierran el jueves. Entrega viernes o sábado.</p></div>`
 :`<div class="card"><p class="label">Edición cerrada</p><p style="color:var(--hueso-60)">La próxima edición se anuncia el lunes. Vuelve pronto.</p></div>`;
};
PANE['Hacer pedido']=function(){
 const e=db.edicion;if(!e.abierta)return PANE['Mi edición']();
 return `<form class="card" onsubmit="return crearPedido(event)"><p class="label">Hacer pedido</p>
 ${Object.keys(e.sab).map((k,i)=>`<label>${esc(k)} (máx. ${e.sab[k]})</label><input type="number" name="s${i}" min="0" max="${e.sab[k]}" value="0">`).join('')}
 <label>Entrega</label><select name="entrega"><option>Viernes</option><option>Sábado</option></select>
 <label>Notas</label><input name="notas" placeholder="Opcional…">
 <button class="btn btn-solid sm" style="margin-top:18px">Enviar pedido</button></form>`;
};
function crearPedido(e){const d=fd(e);const keys=Object.keys(db.edicion.sab);
 const items=keys.map((k,i)=>({sabor:k,qty:Math.min(+d['s'+i]||0,db.edicion.sab[k])})).filter(i=>i.qty>0);
 if(!items.length){alert('Elige al menos un vaso.');return false}
 const s=sesion();db.pedidos.push({id:uid(),dist:s.id,f:hoy(),items,entrega:d.entrega,notas:d.notas||'',estado:'abierto'});save();ir('Mis pedidos');return false}
PANE['Mis pedidos']=function(){
 const s=sesion();const ped=db.pedidos.filter(x=>x.dist===s.id).slice().reverse();
 return `<p class="label">Mis pedidos</p>`+(ped.length?ped.map(x=>`<div class="card">
  <div class="cardhead"><h3>${x.f} · ${x.entrega}</h3><span class="badge ${x.estado==='entregado'?'ok':''}">${x.estado}</span></div>
  <p style="color:var(--hueso-60)">${x.items.map(i=>`${i.qty} × ${esc(i.sabor)}`).join(' · ')}</p>
  ${x.notas?`<p class="notar">${esc(x.notas)}</p>`:''}
  ${x.estado==='abierto'?`<a class="btn btn-ghost sm" style="margin-top:16px" target="_blank" href="https://wa.me/${db.config.wa}?text=${encodeURIComponent('Hola MOSAÏA, soy '+s.nombre+'. Pedido del '+x.f+' para '+x.entrega+': '+x.items.map(i=>i.qty+' × '+i.sabor).join(', ')+(x.notas?'. Notas: '+x.notas:''))}">Confirmar por WhatsApp</a>`:''}</div>`).join(''):'<p class="vacio">Aún no tienes pedidos.</p>';
};
PANE['Incidencias']=function(){
 const s=sesion();const inc=db.incid.filter(x=>x.dist===s.id).slice().reverse();
 return `<form class="card" onsubmit="return crearIncid(event)"><p class="label">Reportar una incidencia</p>
 <label>Tipo</label><select name="tipo"><option>Entrega</option><option>Calidad</option><option>Temperatura / conservación</option><option>Empaque</option><option>Otro</option></select>
 <label>Descripción</label><textarea name="desc" rows="3" required></textarea>
 <button class="btn btn-solid sm" style="margin-top:16px">Enviar reporte</button></form>
 <p class="label">Mis reportes</p>${inc.length?inc.map(x=>`<div class="card"><span class="badge ${x.estado==='resuelta'?'ok':'bad'}">${x.estado}</span> <b style="margin-left:10px">${esc(x.tipo)}</b><p style="color:var(--hueso-60);margin-top:8px">${esc(x.desc)}</p><span class="fecha">${x.f}</span></div>`).join(''):'<p class="vacio">Sin reportes.</p>'}`;
};
function crearIncid(e){const d=fd(e);const s=sesion();db.incid.push({id:uid(),dist:s.id,f:hoy(),tipo:d.tipo,desc:d.desc,estado:'abierta'});save();render();return false}

/* ================= EQUIPO ================= */
PANE['Recetario']=function(){
 return db.recetas.filter(r=>r.estado!=='Descartada').map(r=>`<details class="card"><summary>${esc(r.nombre)}<span class="badge">${r.estado}</span></summary>
  <div class="cols2"><div><p class="label">Ingredientes</p><ul class="lista">${r.ing.map(i=>`<li>${esc(i)}</li>`).join('')}</ul></div>
  <div><p class="label">Pasos</p><ol class="lista">${r.pasos.map(i=>`<li>${esc(i)}</li>`).join('')}</ol></div></div>
  ${r.notas?`<p class="notar">${esc(r.notas)}</p>`:''}</details>`).join('')||'<p class="vacio">Sin recetas disponibles.</p>';
};
PANE['Producir']=function(){
 return `<form class="card" onsubmit="return registrarProd(event)"><p class="label">Registrar producción</p>
 <div class="row2"><div><label>Fecha</label><input type="date" name="f" value="${hoy()}"></div>
 <div><label>Sabor</label><select name="sabor">${Object.keys(db.edicion.sab).map(k=>`<option>${esc(k)}</option>`).join('')}</select></div>
 <div><label>Vasos producidos</label><input type="number" name="vasos" value="1"></div>
 <div><label>Merma (vasos)</label><input type="number" name="merma" value="0"></div>
 <div><label>Minutos</label><input type="number" name="min" value="60"></div></div>
 <button class="btn btn-solid sm" style="margin-top:16px">Guardar</button></form>
 <p class="notar">Guarda cada tanda. El rendimiento se calcula solo.</p>`;
};
function registrarProd(e){const d=fd(e);const s=sesion();db.prod.push({id:uid(),f:d.f,sabor:d.sabor,vasos:+d.vasos||0,merma:+d.merma||0,min:+d.min||0,quien:s.nombre});save();alert('Registrado.');render();return false}
PANE['Rendimiento']=function(){
 const p=db.prod,tot=p.reduce((a,b)=>a+b.vasos,0),m=p.reduce((a,b)=>a+b.merma,0),mins=p.reduce((a,b)=>a+(+b.min||0),0);
 const vph=mins?Math.round(tot/(mins/60)):0;
 return `<div class="kpis">${kpi('Vasos totales',tot)}${kpi('Vasos / hora',vph)}${kpi('Merma',tot?Math.round(m/tot*100)+' %':'0 %')}</div>
 <p class="label" style="margin-top:26px">Bitácora</p>
 <table class="p"><tr><th>Fecha</th><th>Sabor</th><th>Vasos</th><th>Merma</th><th>Min</th><th>Quién</th></tr>
 ${p.slice().reverse().map(x=>`<tr><td>${x.f}</td><td>${esc(x.sabor)}</td><td>${x.vasos}</td><td>${x.merma}</td><td>${x.min}</td><td>${esc(x.quien)}</td></tr>`).join('')||'<tr><td colspan="6" class="vacio">Sin registros.</td></tr>'}</table>`;
};

/* ================= VASO INTERACTIVO (público) ================= */
const SABORES={
 pj:{titulo:'Un vaso es una secuencia.',texto:'Cada capa se piensa para encontrarse con la siguiente: la acidez de la jamaica, el dulzor maduro de la piña, la calma del yogurt. Se descubren cucharada a cucharada.',nota:'Pasa el cursor sobre cada capa.',
  colores:{c1a:'#8c1a2d',c1b:'#3f0b14',c2a:'#e0b054',c2b:'#b3822f',c3a:'#f2ede4',c3b:'#e3dac8'},
  capas:[{nombre:'Gelatina de jamaica',desc:'profunda · floral',color:'#6e1423'},{nombre:'Compota de piña',desc:'dorada · ácida',color:'#d9a441'},{nombre:'Yogurt natural',desc:'cremoso · en calma',color:'#f2ede4'}]},
 pc:{titulo:'Un vaso es un atardecer.',texto:'El café abre oscuro y tostado; el plátano caramelizado responde con dulzura madura; el yogurt lo redondea todo. Un postre para finales lentos.',nota:'Pasa el cursor sobre cada capa.',
  colores:{c1a:'#4a3325',c1b:'#241610',c2a:'#e8d3a0',c2b:'#c9a860',c3a:'#f2ede4',c3b:'#e3dac8'},
  capas:[{nombre:'Gelatina de café',desc:'oscura · tostada',color:'#3e2a20'},{nombre:'Plátano caramelizado',desc:'maduro · tibio',color:'#e8d3a0'},{nombre:'Yogurt natural',desc:'cremoso · en calma',color:'#f2ede4'}]}};
const glass=$('#glass'),leyenda=$('#leyenda'),root=document.documentElement;
function pintarLeyenda(s){leyenda.innerHTML='';s.capas.forEach((c,i)=>{const li=document.createElement('li');li.dataset.l=i+1;li.innerHTML=`<span class="dot" style="background:${c.color}"></span><span class="nombre">${c.nombre}</span><span class="desc">${c.desc}</span>`;leyenda.appendChild(li)});sincronizar()}
function sincronizar(){[...leyenda.children,...glass.querySelectorAll('.layer')].forEach(el=>{el.onmouseenter=()=>resaltar(el.dataset.l);el.onmouseleave=()=>resaltar(null)})}
function resaltar(n){glass.querySelectorAll('.layer').forEach(l=>{l.classList.toggle('lit',l.dataset.l===n);l.classList.toggle('dim',!!n&&l.dataset.l!==n)});[...leyenda.children].forEach(li=>li.classList.toggle('lit',li.dataset.l===n))}
function cargarSabor(key){const s=SABORES[key];Object.entries(s.colores).forEach(([k,v])=>root.style.setProperty('--'+k,v));$('#vaso-titulo').textContent=s.titulo;$('#vaso-texto').textContent=s.texto;$('#vaso-nota').textContent=s.nota;pintarLeyenda(s)}
$('#btn-pj').onclick=e=>{cargarSabor('pj');e.target.classList.add('activo');$('#btn-pc').classList.remove('activo')};
$('#btn-pc').onclick=e=>{cargarSabor('pc');e.target.classList.add('activo');$('#btn-pj').classList.remove('activo')};

/* ================= INIT ================= */
(function(){
 const nav=$('#nav');
 addEventListener('scroll',()=>nav.classList.toggle('scrolled',scrollY>40),{passive:true});
 const io=new IntersectionObserver(es=>es.forEach(e=>{if(e.isIntersecting){e.target.classList.add('visible');io.unobserve(e.target)}}),{threshold:.15});
 const s=sesion();
 if(s){
  $('#publico').hidden=true;nav.hidden=true;$('#portal').hidden=false;
  $('#quien').textContent=s.rol==='founder'?'Fundador':s.rol==='dist'?s.nombre:'Equipo · '+s.nombre;
  tabActiva=TABS[s.rol][0];renderTabs();render();
 }else{
  document.querySelectorAll('.reveal').forEach(el=>io.observe(el));
  Object.entries(SABORES.pj.colores).forEach(([k,v])=>root.style.setProperty('--'+k,v));
  pintarLeyenda(SABORES.pj);
  const el=$('#estado-edicion');
  if(el)el.textContent=db.edicion.abierta?'Edición abierta · '+Object.entries(db.edicion.sab).map(([k,v])=>v+' de '+k).join(' · '):'Edición cerrada · la próxima se anuncia el lunes';
  const wa=$('#wa-publico');if(wa)wa.href='https://wa.me/'+db.config.wa+'?text='+encodeURIComponent('Hola MOSAÏA, quiero apartar un vaso.');
 }
})();
</script>
</body>
</html>
