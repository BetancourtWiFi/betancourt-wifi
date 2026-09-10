<!doctype html>
<html lang="es">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<meta name="theme-color" content="#202a55">
<title>Wi‑Fi | Betancourt</title>
<style>
:root{--navy:#202a55;--gold:#d9ad35;--gold2:#f0c85b;--cream:#f7f3e8}
*{box-sizing:border-box}
body{margin:0;background:var(--navy);color:var(--cream);font-family:Arial,Helvetica,sans-serif}
.wrap{max-width:520px;min-height:100vh;margin:auto;padding:42px 22px 35px;display:flex;flex-direction:column}
header{text-align:center}
.logo{font:400 clamp(48px,14vw,70px)/.95 Georgia,"Times New Roman",serif;color:var(--gold2);letter-spacing:-2px}
.rule{height:2px;background:var(--gold);margin:13px auto 10px;width:86%;position:relative}
.rule:before,.rule:after{content:"";position:absolute;top:50%;width:7px;height:7px;background:var(--gold);transform:translateY(-50%) rotate(45deg)}
.rule:before{left:-3px}.rule:after{right:-3px}
.tag{font:20px Georgia,"Times New Roman",serif;color:var(--gold2)}
.hero{text-align:center;margin-top:55px}
.wifi{font-size:58px;color:var(--gold2);margin-bottom:8px}
h1{font:400 42px Georgia,"Times New Roman",serif;color:var(--gold2);margin:0 0 9px}
.hero p{margin:0;color:#d9dce6;letter-spacing:2.5px;font-size:12px;text-transform:uppercase}
.card{margin-top:32px;border:1px solid var(--gold);border-radius:18px;padding:24px 22px;background:rgba(0,0,0,.08)}
.label{color:var(--gold2);font-size:11px;letter-spacing:3px;text-transform:uppercase;margin-bottom:7px}
.value{font-size:20px;line-height:1.45;word-break:break-all}
.row+.row{border-top:1px solid rgba(217,173,53,.5);margin-top:20px;padding-top:20px}
button{width:100%;margin-top:20px;border:0;border-radius:30px;padding:17px;background:linear-gradient(#f1cd6d,#d7aa36);color:#172143;font-weight:800;font-size:14px;letter-spacing:1.8px;cursor:pointer}
button:active{transform:scale(.985)}
#status{text-align:center;height:22px;margin-top:11px;color:var(--gold2);font-size:13px}
.help{margin-top:35px;border-top:1px solid rgba(217,173,53,.6);padding-top:24px}
.help-title{text-align:center;color:var(--gold2);font-size:12px;letter-spacing:3px;text-transform:uppercase;margin-bottom:18px}
.help p{font-size:14px;line-height:1.55;color:#d9dce6;margin:9px 0}
.help strong{color:var(--cream)}
footer{text-align:center;margin-top:auto;padding-top:42px;color:var(--gold2);font:27px "Brush Script MT","Segoe Script",cursive}
</style>
</head>
<body>
<div class="wrap">
<header>
  <div class="logo">Betancourt</div>
  <div class="rule"></div>
  <div class="tag">Global hairdresser &amp; barber shop</div>
</header>

<section class="hero">
  <div class="wifi">⌁</div>
  <h1>Wi‑Fi</h1>
  <p>Conéctate y disfruta de tu estancia</p>
</section>

<section class="card">
  <div class="row">
    <div class="label">Red</div>
    <div class="value">MOVISTAR_DB21</div>
  </div>
  <div class="row">
    <div class="label">Contraseña</div>
    <div class="value" id="pass">7m2Q6P3zuL6N36nd3aVJ</div>
  </div>
</section>

<button id="copy" type="button">COPIAR CONTRASEÑA</button>
<div id="status"></div>

<section class="help">
  <div class="help-title">Cómo conectarte</div>
  <p><strong>1.</strong> Abre Ajustes → Wi‑Fi en tu móvil.</p>
  <p><strong>2.</strong> Selecciona <strong>MOVISTAR_DB21</strong>.</p>
  <p><strong>3.</strong> Pulsa «Copiar contraseña» arriba y pégala en el campo de contraseña.</p>
</section>

<footer>Gracias por tu visita</footer>
</div>

<script>
document.getElementById("copy").addEventListener("click",async function(){
 const pass=document.getElementById("pass").textContent.trim();
 const status=document.getElementById("status");
 try{
   await navigator.clipboard.writeText(pass);
 }catch(e){
   const area=document.createElement("textarea");
   area.value=pass; document.body.appendChild(area); area.select();
   document.execCommand("copy"); area.remove();
 }
 this.textContent="✓ CONTRASEÑA COPIADA";
 status.textContent="Ahora puedes pegarla en Ajustes → Wi‑Fi";
 setTimeout(()=>{this.textContent="COPIAR CONTRASEÑA";status.textContent=""},3000);
});
</script>
</body>
</html>
