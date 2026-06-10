# KristinaSabitova.github.io

[index.html](https://github.com/user-attachments/files/28803165/index.html)
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Kristina Sabitova — Portfolio</title>
<link href="https://fonts.googleapis.com/css2?family=Press+Start+2P&family=VT323:wght@400&family=Share+Tech+Mono&display=swap" rel="stylesheet">
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}

:root{
  --black:  #05050A;
  --dark:   #0A0A14;
  --dark2:  #0F0F1E;
  --panel:  #12121F;
  --teal:   #00FFD1;
  --pink:   #FF2D78;
  --yellow: #FFE600;
  --purple: #9D4EDD;
  --blue:   #0080FF;
  --green:  #00FF88;
  --border: rgba(0,255,209,0.2);
  --pixel:  'Press Start 2P', monospace;
  --vt:     'VT323', monospace;
  --mono:   'Share Tech Mono', monospace;
}

body{
  font-family:var(--mono);
  background:var(--black);
  color:var(--teal);
  overflow-x:hidden;
  cursor:crosshair;
}

/* Dot grid bg */
body::before{
  content:'';position:fixed;inset:0;z-index:0;
  background-image:radial-gradient(rgba(0,255,209,0.08) 1px,transparent 1px);
  background-size:28px 28px;pointer-events:none;
}

/* ── HUD / NAV ── */
.hud{
  position:fixed;top:0;left:0;right:0;z-index:100;
  background:rgba(5,5,10,0.95);
  border-bottom:2px solid var(--teal);
  padding:8px 24px;
  display:flex;align-items:center;justify-content:space-between;
  image-rendering:pixelated;
}

.hud-left,.hud-right{
  font-family:var(--pixel);font-size:7px;color:var(--teal);
  letter-spacing:1px;
}

.hud-center{
  display:flex;gap:28px;
}

.hud-link{
  font-family:var(--pixel);font-size:6px;color:var(--teal);
  text-decoration:none;letter-spacing:1px;
  padding:4px 8px;border:1px solid transparent;
  transition:all .15s;text-transform:uppercase;
}
.hud-link:hover{
  border-color:var(--teal);
  background:rgba(0,255,209,0.08);
  color:var(--yellow);
}

.hp-bar{
  display:flex;align-items:center;gap:6px;
}
.hp-text{font-family:var(--pixel);font-size:6px;color:var(--pink)}
.hp-fill{
  width:80px;height:8px;
  background:rgba(255,45,120,0.2);border:1px solid var(--pink);
  position:relative;overflow:hidden;
}
.hp-fill::after{
  content:'';position:absolute;inset:0 15% 0 0;
  background:var(--pink);
}

/* ── START SCREEN ── */
.start-screen{
  position:relative;z-index:1;
  min-height:100vh;
  display:flex;flex-direction:column;
  align-items:center;justify-content:center;
  padding:80px 24px 40px;
  text-align:center;
  overflow:hidden;
}

/* Stars */
.stars{
  position:absolute;inset:0;z-index:0;pointer-events:none;
  overflow:hidden;
}
.star{
  position:absolute;width:3px;height:3px;
  background:var(--yellow);
  animation:twinkle var(--d,2s) var(--del,0s) ease-in-out infinite;
}
@keyframes twinkle{0%,100%{opacity:1}50%{opacity:0.1}}

/* Decorative pixel clouds */
.cloud{
  position:absolute;
  font-size:32px;
  opacity:0.6;
  animation:float var(--fd,6s) ease-in-out infinite;
}
@keyframes float{0%,100%{transform:translateY(0)}50%{transform:translateY(-12px)}}

.start-xp{
  font-family:var(--pixel);font-size:8px;
  color:var(--purple);letter-spacing:2px;
  margin-bottom:20px;position:relative;z-index:1;
}

.start-year{
  font-family:var(--pixel);font-size:18px;
  color:var(--yellow);
  text-shadow:0 0 20px var(--yellow),0 0 40px rgba(255,230,0,0.4);
  letter-spacing:4px;margin-bottom:8px;
  position:relative;z-index:1;
}

.start-title{
  font-family:var(--pixel);
  font-size:clamp(20px,5vw,44px);
  color:var(--pink);
  text-shadow:4px 4px 0 #8B0033,0 0 30px rgba(255,45,120,0.5);
  letter-spacing:4px;line-height:1.3;
  margin-bottom:16px;
  position:relative;z-index:1;
}

.start-name{
  font-family:var(--pixel);font-size:10px;
  color:var(--teal);letter-spacing:3px;
  margin-bottom:32px;position:relative;z-index:1;
}

.start-btn{
  font-family:var(--pixel);font-size:10px;
  color:var(--black);background:var(--green);
  border:none;padding:12px 28px;
  cursor:pointer;text-decoration:none;
  display:inline-block;
  box-shadow:4px 4px 0 #006633;
  transition:transform .1s,box-shadow .1s;
  animation:btn-pulse 1.5s ease-in-out infinite;
  position:relative;z-index:1;
}
.start-btn:hover{transform:translate(2px,2px);box-shadow:2px 2px 0 #006633}
@keyframes btn-pulse{0%,100%{opacity:1}50%{opacity:0.7}}

/* Ground strip */
.ground{
  position:absolute;bottom:0;left:0;right:0;height:32px;
  background:repeating-linear-gradient(90deg,var(--green) 0,var(--green) 16px,#00CC66 16px,#00CC66 32px);
  opacity:0.7;z-index:1;
}

/* Marquee strip */
.marquee-strip{
  background:var(--purple);
  border-top:2px solid var(--teal);border-bottom:2px solid var(--teal);
  padding:8px 0;overflow:hidden;position:relative;z-index:2;
}
.marquee-track{
  display:flex;gap:40px;width:max-content;
  animation:scroll-left 18s linear infinite;
}
@keyframes scroll-left{from{transform:translateX(0)}to{transform:translateX(-50%)}}
.marquee-item{
  font-family:var(--pixel);font-size:7px;color:var(--yellow);
  letter-spacing:1px;white-space:nowrap;
  display:flex;align-items:center;gap:12px;
}
.marquee-item::after{content:'★';color:var(--teal)}

/* ── LEVEL SECTION ── */
.level-section{
  position:relative;z-index:1;
  padding:64px 40px;
  max-width:1100px;margin:0 auto;
}

.level-header{
  display:flex;align-items:flex-start;gap:24px;
  margin-bottom:48px;
}

.level-num{
  font-family:var(--pixel);
  font-size:clamp(40px,6vw,72px);
  color:var(--pink);
  text-shadow:4px 4px 0 #8B0033;
  line-height:1;
  flex-shrink:0;
}

.level-info{}
.level-subtitle{
  font-family:var(--pixel);font-size:8px;color:var(--teal);
  letter-spacing:1px;margin-bottom:8px;
}
.level-title{
  font-family:var(--pixel);
  font-size:clamp(14px,2.5vw,22px);
  color:var(--yellow);
  text-shadow:2px 2px 0 #8B7000;
  letter-spacing:2px;line-height:1.4;
}

/* ── WINDOW PANELS ── */
.window{
  background:var(--panel);
  border:2px solid var(--teal);
  position:relative;
  box-shadow:4px 4px 0 rgba(0,255,209,0.15);
}

.window-bar{
  background:var(--teal);
  padding:4px 10px;
  display:flex;align-items:center;justify-content:space-between;
}
.window-bar span{
  font-family:var(--pixel);font-size:7px;color:var(--black);letter-spacing:1px;
}
.window-controls{display:flex;gap:6px}
.wc{
  width:10px;height:10px;
  background:var(--black);border:1px solid var(--black);
  font-family:var(--pixel);font-size:6px;color:var(--teal);
  display:flex;align-items:center;justify-content:center;
}

.window-body{padding:20px}

/* ── LEVEL 01 — PLAYER INFO ── */
.player-layout{
  display:grid;grid-template-columns:320px 1fr;gap:24px;
  align-items:start;
}

/* DS-style frame para la foto */
.ds-frame{
  background:#1a1a2e;
  border:3px solid var(--pink);
  padding:12px;
  box-shadow:6px 6px 0 var(--pink), inset 0 0 20px rgba(255,45,120,0.1);
  position:relative;
}

.ds-screen{
  position:relative;overflow:hidden;
  border:2px solid #333;
  background:#000;
}

.ds-photo{
  width:100%;display:block;
  image-rendering:auto;
  filter:contrast(1.1) saturate(0.9);
}

.ds-scanlines{
  position:absolute;inset:0;
  background:repeating-linear-gradient(0deg,rgba(0,0,0,0.15) 0,rgba(0,0,0,0.15) 1px,transparent 1px,transparent 3px);
  pointer-events:none;
}

.ds-bottom{
  background:#111;
  border-top:2px solid var(--pink);
  padding:8px 10px;
  display:flex;align-items:center;justify-content:center;gap:8px;
}
.ds-btn{
  width:10px;height:10px;border-radius:50%;
  background:var(--pink);border:1px solid #fff;
}
.ds-btn.blue{background:var(--blue)}
.ds-btn.yellow{background:var(--yellow)}

.ds-label{
  font-family:var(--pixel);font-size:6px;
  color:var(--pink);letter-spacing:1px;
  text-align:center;margin-top:8px;
}

/* Player info window */
.player-info-grid{
  display:flex;flex-direction:column;gap:14px;
}

.info-row{
  display:flex;gap:0;border-bottom:1px solid rgba(0,255,209,0.1);padding-bottom:10px;
}
.info-row:last-child{border-bottom:none;padding-bottom:0}
.info-key{
  font-family:var(--pixel);font-size:7px;color:var(--pink);
  min-width:110px;letter-spacing:0.5px;padding-top:2px;
}
.info-val{
  font-family:var(--vt);font-size:18px;color:var(--teal);line-height:1.2;
}

.status-badge{
  display:inline-flex;align-items:center;gap:6px;
  background:rgba(0,255,136,0.08);border:1px solid var(--green);
  padding:3px 10px;
}
.status-dot{width:6px;height:6px;border-radius:50%;background:var(--green);animation:pulse 2s infinite}
@keyframes pulse{0%,100%{opacity:1}50%{opacity:0.3}}
.status-text{font-family:var(--pixel);font-size:6px;color:var(--green);letter-spacing:1px}

/* ── WEAPONS / SKILLS ── */
.weapons-grid{
  display:grid;grid-template-columns:1fr 1fr;gap:16px;
}

.weapon-item{
  background:rgba(0,255,209,0.04);
  border:1px solid rgba(0,255,209,0.15);
  padding:14px 16px;
  display:flex;align-items:center;justify-content:space-between;
  transition:border-color .2s,background .2s;
}
.weapon-item:hover{
  border-color:var(--teal);background:rgba(0,255,209,0.08);
}

.weapon-name{font-family:var(--pixel);font-size:7px;color:var(--teal);letter-spacing:0.5px}

.weapon-lvl{display:flex;gap:3px}
.pip{
  width:8px;height:8px;
  background:transparent;border:1px solid rgba(0,255,209,0.3);
}
.pip.on{background:var(--teal);border-color:var(--teal);box-shadow:0 0 6px var(--teal)}

/* ── MISSIONS / PROYECTOS ── */
.missions-list{display:flex;flex-direction:column;gap:20px}

.mission-card{
  background:var(--panel);
  border:2px solid rgba(0,255,209,0.2);
  transition:border-color .2s,transform .2s;
  display:grid;grid-template-columns:1fr auto;
  gap:0;overflow:hidden;
}
.mission-card:hover{border-color:var(--pink);transform:translateX(4px)}

.mission-body{padding:24px 28px}
.mission-num{
  font-family:var(--pixel);font-size:8px;color:var(--purple);
  letter-spacing:1px;margin-bottom:10px;
}
.mission-badge{
  display:inline-flex;align-items:center;gap:5px;
  font-family:var(--pixel);font-size:6px;
  padding:3px 8px;margin-bottom:10px;width:fit-content;
}
.b-live{background:rgba(0,255,136,0.1);color:var(--green);border:1px solid rgba(0,255,136,0.3)}
.b-live::before{content:'●';font-size:5px;animation:pulse 2s infinite}
.b-ctf{background:rgba(157,78,221,0.1);color:var(--purple);border:1px solid rgba(157,78,221,0.3)}
.b-lab{background:rgba(255,230,0,0.1);color:var(--yellow);border:1px solid rgba(255,230,0,0.3)}

.mission-title{
  font-family:var(--pixel);
  font-size:clamp(10px,1.5vw,14px);
  color:var(--yellow);
  text-shadow:2px 2px 0 #8B7000;
  letter-spacing:1px;margin-bottom:10px;
  line-height:1.5;
}
.mission-title a{color:inherit;text-decoration:none;transition:color .15s}
.mission-title a:hover{color:var(--pink)}

.mission-desc{
  font-family:var(--mono);font-size:12px;color:rgba(0,255,209,0.7);
  line-height:1.7;margin-bottom:14px;
}

.mission-tags{display:flex;flex-wrap:wrap;gap:5px;margin-bottom:14px}
.tag{
  font-family:var(--pixel);font-size:6px;color:var(--teal);
  background:rgba(0,255,209,0.05);border:1px solid rgba(0,255,209,0.2);
  padding:3px 8px;
}

.mission-link{
  font-family:var(--pixel);font-size:7px;color:var(--green);
  text-decoration:none;letter-spacing:1px;
  display:inline-flex;align-items:center;gap:6px;
  transition:gap .15s;
}
.mission-link:hover{gap:10px;color:var(--yellow)}

.mission-status{
  background:rgba(0,0,0,0.4);
  border-left:2px solid rgba(0,255,209,0.2);
  padding:20px 16px;
  display:flex;flex-direction:column;align-items:center;justify-content:center;gap:8px;
  min-width:80px;
}
.mission-icon{font-size:28px;}
.mission-xp{font-family:var(--pixel);font-size:6px;color:var(--yellow);letter-spacing:1px;text-align:center}

/* ── TRAINING LOG / FORMACIÓN ── */
.training-grid{
  display:grid;grid-template-columns:1fr 1fr;gap:20px;
}

.training-entry{
  background:rgba(0,0,0,0.3);
  border:1px solid rgba(0,255,209,0.15);
  padding:18px 20px;
}

.training-year{
  font-family:var(--pixel);font-size:7px;color:var(--purple);
  letter-spacing:1px;margin-bottom:6px;
}
.training-title{
  font-family:var(--pixel);font-size:8px;color:var(--yellow);
  letter-spacing:1px;margin-bottom:4px;line-height:1.5;
}
.training-org{
  font-family:var(--mono);font-size:12px;color:var(--teal);
  margin-bottom:6px;
}
.training-badge{
  display:inline-block;
  font-family:var(--pixel);font-size:6px;
  background:rgba(0,255,209,0.08);color:var(--teal);
  border:1px solid rgba(0,255,209,0.2);padding:2px 8px;
}

/* ── CONTACT ── */
.contact-terminal{
  background:var(--black);
  border:2px solid var(--teal);
  padding:24px 28px;
  font-family:var(--mono);
}

.terminal-line{
  font-size:14px;color:var(--teal);
  margin-bottom:8px;line-height:1.6;
}
.terminal-line .prompt{color:var(--pink)}
.terminal-line .cmd{color:var(--yellow)}
.terminal-line .out{color:rgba(0,255,209,0.7)}
.terminal-cursor{
  display:inline-block;width:8px;height:14px;
  background:var(--teal);
  animation:blink 1s step-end infinite;vertical-align:middle;
}
@keyframes blink{0%,100%{opacity:1}50%{opacity:0}}

.contact-links{
  display:grid;grid-template-columns:repeat(3,1fr);gap:12px;margin-top:20px;
}

.contact-link{
  background:rgba(0,255,209,0.05);
  border:1px solid rgba(0,255,209,0.2);
  padding:14px 12px;text-decoration:none;
  text-align:center;
  transition:border-color .15s,background .15s;
}
.contact-link:hover{border-color:var(--pink);background:rgba(255,45,120,0.08)}
.cl-icon{font-size:20px;display:block;margin-bottom:6px}
.cl-label{font-family:var(--pixel);font-size:6px;color:var(--teal);letter-spacing:1px}
.cl-val{font-family:var(--mono);font-size:11px;color:rgba(0,255,209,0.6);margin-top:2px}

/* ── BOTTOM STRIP ── */
.bottom-strip{
  background:var(--purple);
  border-top:2px solid var(--teal);
  padding:10px 24px;
  display:flex;align-items:center;justify-content:space-between;
}
.bs-text{font-family:var(--pixel);font-size:7px;color:var(--yellow);letter-spacing:1px}

/* SECTION DIVIDERS */
.level-divider{
  border:none;
  border-top:2px solid rgba(0,255,209,0.15);
  margin:0;
  background:repeating-linear-gradient(90deg,transparent,transparent 8px,rgba(0,255,209,0.05) 8px,rgba(0,255,209,0.05) 16px);
  height:16px;
}

/* Responsive */
@media(max-width:800px){
  .player-layout,.weapons-grid,.training-grid,.contact-links{grid-template-columns:1fr}
  .mission-card{grid-template-columns:1fr}
  .mission-status{flex-direction:row;border-left:none;border-top:2px solid rgba(0,255,209,0.2);min-width:unset}
  .hud-center{display:none}
  .level-section{padding:48px 20px}
}
</style>
</head>
<body>

<!-- HUD -->
<div class="hud">
  <div class="hud-left">XP: CIBER · LEVEL 03</div>
  <div class="hud-center">
    <a href="#player" class="hud-link">Player</a>
    <a href="#missions" class="hud-link">Missions</a>
    <a href="#skills" class="hud-link">Skills</a>
    <a href="#contact" class="hud-link">Contact</a>
  </div>
  <div class="hud-right">
    <div class="hp-bar">
      <span class="hp-text">HP</span>
      <div class="hp-fill"></div>
      <span class="hp-text">PLAYER 01</span>
    </div>
  </div>
</div>

<!-- START SCREEN -->
<section class="start-screen">
  <div class="stars">
    <div class="star" style="left:0%;top:0%;--d:1s;--del:0.0s"></div><div class="star" style="left:37%;top:97%;--d:2s;--del:0.3s"></div><div class="star" style="left:74%;top:94%;--d:3s;--del:0.6s"></div><div class="star" style="left:11%;top:91%;--d:1s;--del:0.8999999999999999s"></div><div class="star" style="left:48%;top:88%;--d:2s;--del:1.2s"></div><div class="star" style="left:85%;top:85%;--d:3s;--del:1.5s"></div><div class="star" style="left:22%;top:82%;--d:1s;--del:1.7999999999999998s"></div><div class="star" style="left:59%;top:79%;--d:2s;--del:0.10000000000000009s"></div><div class="star" style="left:96%;top:76%;--d:3s;--del:0.3999999999999999s"></div><div class="star" style="left:33%;top:73%;--d:1s;--del:0.6999999999999997s"></div><div class="star" style="left:70%;top:70%;--d:2s;--del:1.0s"></div><div class="star" style="left:7%;top:67%;--d:3s;--del:1.2999999999999998s"></div><div class="star" style="left:44%;top:64%;--d:1s;--del:1.5999999999999996s"></div><div class="star" style="left:81%;top:61%;--d:2s;--del:1.9s"></div><div class="star" style="left:18%;top:58%;--d:3s;--del:0.20000000000000018s"></div><div class="star" style="left:55%;top:55%;--d:1s;--del:0.5s"></div><div class="star" style="left:92%;top:52%;--d:2s;--del:0.7999999999999998s"></div><div class="star" style="left:29%;top:49%;--d:3s;--del:1.0999999999999996s"></div><div class="star" style="left:66%;top:46%;--d:1s;--del:1.3999999999999995s"></div><div class="star" style="left:3%;top:43%;--d:2s;--del:1.7000000000000002s"></div><div class="star" style="left:40%;top:40%;--d:3s;--del:0.0s"></div><div class="star" style="left:77%;top:37%;--d:1s;--del:0.2999999999999998s"></div><div class="star" style="left:14%;top:34%;--d:2s;--del:0.5999999999999996s"></div><div class="star" style="left:51%;top:31%;--d:3s;--del:0.8999999999999995s"></div><div class="star" style="left:88%;top:28%;--d:1s;--del:1.1999999999999993s"></div><div class="star" style="left:25%;top:25%;--d:2s;--del:1.5s"></div><div class="star" style="left:62%;top:22%;--d:3s;--del:1.7999999999999998s"></div><div class="star" style="left:99%;top:19%;--d:1s;--del:0.09999999999999964s"></div><div class="star" style="left:36%;top:16%;--d:2s;--del:0.40000000000000036s"></div><div class="star" style="left:73%;top:13%;--d:3s;--del:0.6999999999999993s"></div><div class="star" style="left:10%;top:10%;--d:1s;--del:1.0s"></div><div class="star" style="left:47%;top:7%;--d:2s;--del:1.299999999999999s"></div><div class="star" style="left:84%;top:4%;--d:3s;--del:1.5999999999999996s"></div><div class="star" style="left:21%;top:1%;--d:1s;--del:1.9000000000000004s"></div><div class="star" style="left:58%;top:98%;--d:2s;--del:0.1999999999999993s"></div><div class="star" style="left:95%;top:95%;--d:3s;--del:0.5s"></div><div class="star" style="left:32%;top:92%;--d:1s;--del:0.7999999999999989s"></div><div class="star" style="left:69%;top:89%;--d:2s;--del:1.0999999999999996s"></div><div class="star" style="left:6%;top:86%;--d:3s;--del:1.4000000000000004s"></div><div class="star" style="left:43%;top:83%;--d:1s;--del:1.6999999999999993s"></div>
  </div>
  <!-- Decorative clouds -->
  <div class="cloud" style="top:15%;left:5%;--fd:7s;">☁️</div>
  <div class="cloud" style="top:20%;right:8%;--fd:9s;">☁️</div>
  <div class="cloud" style="top:10%;left:40%;--fd:6s;">☁️</div>

  <div class="start-xp">EVOLVE ACADEMY · MÁSTER CIBERSEGURIDAD E IA</div>
  <div class="start-year">2026</div>
  <div class="start-title">PORTFOLIO</div>
  <div class="start-name">KRISTINA SABITOVA</div>
  <a href="#player" class="start-btn">▶ START</a>

  <div class="ground"></div>
</section>

<!-- MARQUEE -->
<div class="marquee-strip">
  <div class="marquee-track">
    <span class="marquee-item">About Me</span>
    <span class="marquee-item">About Me</span>
    <span class="marquee-item">About Me</span>
    <span class="marquee-item">About Me</span>
    <span class="marquee-item">About Me</span>
    <span class="marquee-item">About Me</span>
    <span class="marquee-item">About Me</span>
    <span class="marquee-item">About Me</span>
    <span class="marquee-item">About Me</span>
    <span class="marquee-item">About Me</span>
    <span class="marquee-item">About Me</span>
    <span class="marquee-item">About Me</span>
  </div>
</div>

<!-- LEVEL 01 — MEET THE PLAYER -->
<div class="level-section" id="player">
  <div class="level-header">
    <div class="level-num">Level<br>01</div>
    <div class="level-info">
      <div class="level-subtitle">Meet the player</div>
      <div class="level-title">Kristina<br>Sabitova</div>
    </div>
  </div>

  <div class="player-layout">
    <!-- DS Frame con foto -->
    <div>
      <div class="ds-frame">
        <div class="ds-screen">
          <img class="ds-photo" src="data:image/jpeg;base64,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" alt="Kristina">
          <div class="ds-scanlines"></div>
        </div>
        <div class="ds-bottom">
          <div class="ds-btn"></div>
          <div class="ds-btn blue"></div>
          <div class="ds-btn yellow"></div>
        </div>
      </div>
      <div class="ds-label">PLAYER_01.exe</div>
    </div>

    <!-- Info window -->
    <div class="window">
      <div class="window-bar">
        <span>HELLO !!</span>
        <div class="window-controls">
          <div class="wc">_</div><div class="wc">□</div><div class="wc">×</div>
        </div>
      </div>
      <div class="window-body">
        <div class="player-info-grid">
          <div class="info-row">
            <div class="info-key">Player:</div>
            <div class="info-val">Kristina Sabitova</div>
          </div>
          <div class="info-row">
            <div class="info-key">Role:</div>
            <div class="info-val">Ciberseguridad<br>Red Team · IA</div>
          </div>
          <div class="info-row">
            <div class="info-key">Mission:</div>
            <div class="info-val">Encontrar lo que<br>otros no ven.</div>
          </div>
          <div class="info-row">
            <div class="info-key">Origin:</div>
            <div class="info-val">Imagen médica<br>→ Ciber</div>
          </div>
          <div class="info-row">
            <div class="info-key">Location:</div>
            <div class="info-val">Alicante, España</div>
          </div>
          <div class="info-row">
            <div class="info-key">Languages:</div>
            <div class="info-val">ES · RU · EN</div>
          </div>
          <div class="info-row">
            <div class="info-key">Status:</div>
            <div>
              <div class="status-badge">
                <div class="status-dot"></div>
                <span class="status-text">Ready to play. Let's go!</span>
              </div>
            </div>
          </div>
          <div class="info-row" style="border-bottom:none;">
            <div class="info-key">Quote:</div>
            <div class="info-val" style="font-size:14px;color:rgba(0,255,209,0.7);font-style:italic;">"В деталях вся суть.<br>Details make the difference."</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

<div class="level-divider"></div>

<!-- LEVEL 02 — WEAPONS / SKILLS -->
<div class="level-section" id="skills">
  <div class="level-header">
    <div class="level-num">Level<br>02</div>
    <div class="level-info">
      <div class="level-subtitle">Weapons mastery</div>
      <div class="level-title">Skills &<br>Arsenal</div>
    </div>
  </div>

  <div style="display:grid;grid-template-columns:1fr 1fr;gap:20px;">
    <div class="window">
      <div class="window-bar"><span>WEAPONS.exe</span><div class="window-controls"><div class="wc">_</div><div class="wc">□</div><div class="wc">×</div></div></div>
      <div class="window-body">
        <div class="weapons-grid">
          <div class="weapon-item"><span class="weapon-name">Burp Suite</span><div class="weapon-lvl"><div class="pip on"></div><div class="pip on"></div><div class="pip on"></div><div class="pip on"></div><div class="pip"></div></div></div>
          <div class="weapon-item"><span class="weapon-name">Nmap/Masscan</span><div class="weapon-lvl"><div class="pip on"></div><div class="pip on"></div><div class="pip on"></div><div class="pip on"></div><div class="pip"></div></div></div>
          <div class="weapon-item"><span class="weapon-name">Kali Linux</span><div class="weapon-lvl"><div class="pip on"></div><div class="pip on"></div><div class="pip on"></div><div class="pip on"></div><div class="pip"></div></div></div>
          <div class="weapon-item"><span class="weapon-name">Metasploit</span><div class="weapon-lvl"><div class="pip on"></div><div class="pip on"></div><div class="pip on"></div><div class="pip"></div><div class="pip"></div></div></div>
          <div class="weapon-item"><span class="weapon-name">Python/Bash</span><div class="weapon-lvl"><div class="pip on"></div><div class="pip on"></div><div class="pip on"></div><div class="pip"></div><div class="pip"></div></div></div>
          <div class="weapon-item"><span class="weapon-name">OWASP Top10</span><div class="weapon-lvl"><div class="pip on"></div><div class="pip on"></div><div class="pip on"></div><div class="pip on"></div><div class="pip"></div></div></div>
          <div class="weapon-item"><span class="weapon-name">Nginx/SSL</span><div class="weapon-lvl"><div class="pip on"></div><div class="pip on"></div><div class="pip on"></div><div class="pip on"></div><div class="pip"></div></div></div>
          <div class="weapon-item"><span class="weapon-name">Wireshark</span><div class="weapon-lvl"><div class="pip on"></div><div class="pip on"></div><div class="pip on"></div><div class="pip"></div><div class="pip"></div></div></div>
        </div>
      </div>
    </div>

    <div class="window">
      <div class="window-bar"><span>TRAINING_LOG.exe</span><div class="window-controls"><div class="wc">_</div><div class="wc">□</div><div class="wc">×</div></div></div>
      <div class="window-body">
        <div style="display:flex;flex-direction:column;gap:14px;">
          <div class="training-entry">
            <div class="training-year">2025 – 2026</div>
            <div class="training-title">Máster Ciberseguridad e IA</div>
            <div class="training-org">Evolve Academy</div>
            <span class="training-badge">EN CURSO</span>
          </div>
          <div class="training-entry">
            <div class="training-year">2025 – ACT.</div>
            <div class="training-title">Desarrollo de Aplicaciones Web (DAW)</div>
            <div class="training-org">DIGITECH FP</div>
            <span class="training-badge">EN CURSO</span>
          </div>
          <div class="training-entry">
            <div class="training-year">2021</div>
            <div class="training-title">Técnico Superior Imagen Diagnóstica</div>
            <div class="training-org">ILERNA</div>
            <span class="training-badge">COMPLETADO ✓</span>
          </div>
          <div class="training-entry">
            <div class="training-year">2021 – 2024</div>
            <div class="training-title">3D Oncology Planning</div>
            <div class="training-org">Cella Medical Solutions</div>
            <span class="training-badge">COMPLETADO ✓</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

<div class="level-divider"></div>

<!-- LEVEL 03 — MISSIONS / PROYECTOS -->
<div class="level-section" id="missions">
  <div class="level-header">
    <div class="level-num">Level<br>03</div>
    <div class="level-info">
      <div class="level-subtitle">Active missions</div>
      <div class="level-title">Proyectos<br>en producción</div>
    </div>
  </div>

  <div class="missions-list">

    <div class="mission-card">
      <div class="mission-body">
        <div class="mission-num">MISSION_01</div>
        <span class="mission-badge b-live">LIVE</span>
        <h3 class="mission-title"><a href="https://spectra.ksabitova.dev/login" target="_blank">SPECTRA ↗</a></h3>
        <p class="mission-desc">Plataforma de auditoría de seguridad para pipelines de agentes IA. Detecta inyecciones de prompt indirectas. Hardening A+ en producción.</p>
        <div class="mission-tags"><span class="tag">Python</span><span class="tag">LLM Security</span><span class="tag">Prompt Injection</span><span class="tag">FastAPI</span><span class="tag">Railway</span></div>
        <a href="https://spectra.ksabitova.dev/login" target="_blank" class="mission-link">▶ ACCEDER A MISIÓN</a>
      </div>
      <div class="mission-status">
        <div class="mission-icon">🛡️</div>
        <div class="mission-xp">+500 XP</div>
        <div class="mission-xp">A+ SEC</div>
      </div>
    </div>

    <div class="mission-card">
      <div class="mission-body">
        <div class="mission-num">MISSION_02</div>
        <span class="mission-badge b-live">LIVE</span>
        <h3 class="mission-title"><a href="https://domini.ksabitova.dev/login" target="_blank">DOMINI + SENTINEL ↗</a></h3>
        <p class="mission-desc">Suite de reconocimiento de dominios y OSINT. Footprinting pasivo y activo, análisis DNS, masscan integrado. Repo oficial Evolve Academy.</p>
        <div class="mission-tags"><span class="tag">OSINT</span><span class="tag">Nmap</span><span class="tag">Masscan</span><span class="tag">DNS</span><span class="tag">Python</span></div>
        <a href="https://domini.ksabitova.dev/login" target="_blank" class="mission-link">▶ ACCEDER A MISIÓN</a>
      </div>
      <div class="mission-status">
        <div class="mission-icon">🔍</div>
        <div class="mission-xp">+450 XP</div>
        <div class="mission-xp">OSINT</div>
      </div>
    </div>

    <div class="mission-card">
      <div class="mission-body">
        <div class="mission-num">MISSION_03</div>
        <span class="mission-badge b-ctf">CTF</span>
        <h3 class="mission-title">RickdiculouslyEasy · VulnHub</h3>
        <p class="mission-desc">7/7 flags capturadas en entorno emulado Apple Silicon M1. Reconocimiento, enumeración, explotación y post-explotación documentados.</p>
        <div class="mission-tags"><span class="tag">Kali Linux</span><span class="tag">Nmap</span><span class="tag">Post-explotación</span><span class="tag">ARM M1</span></div>
      </div>
      <div class="mission-status">
        <div class="mission-icon">🚩</div>
        <div class="mission-xp">7/7 FLAGS</div>
        <div class="mission-xp">CLEARED</div>
      </div>
    </div>

    <div class="mission-card">
      <div class="mission-body">
        <div class="mission-num">MISSION_04</div>
        <span class="mission-badge b-lab">LAB</span>
        <h3 class="mission-title">HackTheBox · Starting Point</h3>
        <p class="mission-desc">Activa en HTB. Responder: captura NTLM via LFI + crackeo con John the Ripper. Práctica continua en Windows y Linux.</p>
        <div class="mission-tags"><span class="tag">NTLM</span><span class="tag">LFI</span><span class="tag">Responder</span><span class="tag">John the Ripper</span></div>
      </div>
      <div class="mission-status">
        <div class="mission-icon">⚡</div>
        <div class="mission-xp">IN PROGRESS</div>
        <div class="mission-xp">HTB</div>
      </div>
    </div>

  </div>
</div>

<div class="level-divider"></div>

<!-- LEVEL 04 — CONTACT -->
<div class="level-section" id="contact">
  <div class="level-header">
    <div class="level-num">Level<br>04</div>
    <div class="level-info">
      <div class="level-subtitle">New game +</div>
      <div class="level-title">¿Hablamos?</div>
    </div>
  </div>

  <div class="contact-terminal">
    <div class="terminal-line"><span class="prompt">kristina@ksabitova.dev</span><span style="color:var(--teal)">:~$</span> <span class="cmd">whoami</span></div>
    <div class="terminal-line"><span class="out">Kristina Sabitova — Ciberseguridad · Red Team · IA</span></div>
    <div class="terminal-line" style="margin-top:8px"><span class="prompt">kristina@ksabitova.dev</span><span style="color:var(--teal)">:~$</span> <span class="cmd">cat mensaje.txt</span></div>
    <div class="terminal-line"><span class="out">Busco oportunidad en seguridad ofensiva o IA + Ciber.</span></div>
    <div class="terminal-line"><span class="out">No traigo años de experiencia — traigo proyectos reales.</span></div>
    <div class="terminal-line" style="margin-top:8px"><span class="prompt">kristina@ksabitova.dev</span><span style="color:var(--teal)">:~$</span> <span class="cmd">./contact.sh</span><span class="terminal-cursor"></span></div>
  </div>

  <div class="contact-links" style="margin-top:20px;">
    <a href="mailto:sabitova.solomatova@gmail.com" class="contact-link">
      <span class="cl-icon">✉️</span>
      <div class="cl-label">EMAIL</div>
      <div class="cl-val">sabitova.solomatova@gmail.com</div>
    </a>
    <a href="https://github.com/KristinaSabitova" target="_blank" class="contact-link">
      <span class="cl-icon">⌨️</span>
      <div class="cl-label">GITHUB</div>
      <div class="cl-val">KristinaSabitova</div>
    </a>
    <a href="https://www.linkedin.com/in/kristina-solomatova-sabitova-8207a4163" target="_blank" class="contact-link">
      <span class="cl-icon">🔗</span>
      <div class="cl-label">LINKEDIN</div>
      <div class="cl-val">kristina-solomatova-sabitova</div>
    </a>
    <a href="https://spectra.ksabitova.dev/login" target="_blank" class="contact-link">
      <span class="cl-icon">🛡️</span>
      <div class="cl-label">SPECTRA</div>
      <div class="cl-val">spectra.ksabitova.dev</div>
    </a>
    <a href="https://domini.ksabitova.dev/login" target="_blank" class="contact-link">
      <span class="cl-icon">🔍</span>
      <div class="cl-label">DOMINI</div>
      <div class="cl-val">domini.ksabitova.dev</div>
    </a>
    <div class="contact-link" style="cursor:default;">
      <span class="cl-icon">📍</span>
      <div class="cl-label">LOCATION</div>
      <div class="cl-val">Alicante, España</div>
    </div>
  </div>
</div>

<!-- BOTTOM STRIP -->
<div class="bottom-strip">
  <div class="bs-text">Missions</div>
  <div class="bs-text">★ Missions ★ Missions ★ Missions ★</div>
  <div class="bs-text">Missions</div>
</div>

</body>
</html>
