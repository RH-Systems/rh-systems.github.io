<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<link rel="icon" type="image/svg+xml" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 64 64'><rect width='64' height='64' rx='10' fill='%230a0414'/><polygon points='32,6 54,16 54,36 32,58 10,36 10,16' fill='%237c3aff' opacity='0.2'/><polygon points='32,6 54,16 54,36 32,58 10,36 10,16' fill='none' stroke='%237c3aff' stroke-width='2'/><text x='12' y='40' font-family='Arial Black,Arial,sans-serif' font-size='20' font-weight='900' fill='white'>RH</text><text x='40' y='28' font-family='Arial,sans-serif' font-size='11' font-weight='900' fill='%23a855f7'>2</text></svg>">
<meta name="theme-color" content="#0a0414">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link rel="preconnect" href="https://cdnjs.cloudflare.com">
<link rel="preconnect" href="https://cdn.jsdelivr.net">
<link rel="dns-prefetch" href="https://ipapi.co">
<link rel="dns-prefetch" href="https://ipwho.is">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=5.0">
<title>RH²-Systems | Enterprise Cybersecurity & Offensive Security</title>
<meta name="description" content="RH²-Systems delivers enterprise-grade penetration testing, red teaming, and secure infrastructure auditing for high-risk environments.">
<meta name="author" content="RH²-Systems">
<link rel="canonical" href="https://rh2-systems.com/">
<meta property="og:title" content="RH²-Systems | Enterprise Cybersecurity">
<meta property="og:description" content="Advanced penetration testing, red team operations, and secure engineering for high-risk enterprise infrastructure.">
<meta property="og:type" content="website">
<meta property="og:url" content="https://rh2-systems.com/">
<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/@studio-freight/lenis@1.0.42/dist/lenis.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/ScrollTrigger.min.js"></script>
<link rel="preload" href="https://fonts.googleapis.com/css2?family=Anton&family=Sora:wght@300;400;600&family=Fira+Code:wght@400&display=swap" as="style" onload="this.onload=null;this.rel='stylesheet'">
<noscript><link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Anton&family=Sora:wght@300;400;600&family=Fira+Code:wght@400&display=swap"></noscript>
<style>
:root {
  --ink:#03060a;--ink2:#060c12;--ink3:#091018;--ink4:#0c1520;
  --fire:#7c3aff;--fire2:#a855f7;--gold:#e879f9;--ice:#38bdf8;
  --white:#f0f6ff;--dim:#3d5468;--dim2:#6b8599;
  --gf:rgba(124,58,255,0.22);--gi:rgba(56,189,248,0.15);--gg:rgba(232,121,249,0.12);
  --b1:rgba(124,58,255,0.1);--b2:rgba(124,58,255,0.3);--b3:rgba(124,58,255,0.6);
  --ff-d:'Anton',sans-serif;--ff-b:'Sora',sans-serif;--ff-m:'Fira Code',monospace;
  --ease:cubic-bezier(0.16,1,0.3,1);--snap:cubic-bezier(0.4,0,0.2,1);
}
*,*::before,*::after{margin:0;padding:0;box-sizing:border-box;-webkit-tap-highlight-color:transparent}
html{font-size:16px}
body{background:var(--ink);color:var(--white);font-family:var(--ff-b);line-height:1.7;overflow-x:hidden;cursor:none}
a{text-decoration:none;color:inherit;cursor:pointer}
ul{list-style:none}
button{border:none;background:none;font-family:inherit;cursor:pointer}

/* NOISE */
body::before{content:'';position:fixed;inset:0;z-index:9990;pointer-events:none;background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 512 512' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.75' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E");opacity:0.032;mix-blend-mode:overlay}

/* CURSOR */
#cur{position:fixed;top:0;left:0;z-index:99999;pointer-events:none;mix-blend-mode:difference}
.cur-d{position:absolute;width:8px;height:8px;background:var(--white);border-radius:50%;transform:translate(-50%,-50%);transition:width 0.15s,height 0.15s}
.cur-r{position:absolute;width:40px;height:40px;border:1.5px solid var(--white);border-radius:50%;transform:translate(-50%,-50%);transition:width 0.3s var(--ease),height 0.3s var(--ease),border-radius 0.3s}
body.hov .cur-d{width:0;height:0}
body.hov .cur-r{width:64px;height:64px;border-radius:4px;border-color:var(--fire)}

/* PRELOADER */
#pre{position:fixed;inset:0;z-index:99998;background:var(--ink);display:flex;flex-direction:column;align-items:center;justify-content:center;transition:clip-path 1s var(--ease);clip-path:inset(0 0 0 0)}
#pre.out{clip-path:inset(0 0 100% 0)}
.pre-os{width:min(780px,94vw);font-family:var(--ff-m);position:relative;z-index:2}
.bios-top{border:1px solid rgba(124,58,255,0.3);border-radius:4px 4px 0 0;background:rgba(124,58,255,0.06);padding:10px 18px;display:flex;justify-content:space-between;align-items:center}
.bios-top span{font-size:0.65rem;letter-spacing:0.18em;text-transform:uppercase;color:var(--dim2)}
.bios-top strong{font-size:0.65rem;letter-spacing:0.18em;color:var(--fire)}
.bios-screen{background:#000;border:1px solid rgba(124,58,255,0.2);border-top:none;border-radius:0 0 4px 4px;padding:20px 22px 16px;min-height:320px;position:relative;overflow:hidden}
.bios-screen::before{content:'';position:absolute;inset:0;pointer-events:none;z-index:10;background:repeating-linear-gradient(0deg,transparent,transparent 2px,rgba(0,0,0,0.15) 2px,rgba(0,0,0,0.15) 4px)}
.bios-screen::after{content:'';position:absolute;inset:0;pointer-events:none;background:radial-gradient(ellipse 80% 60% at 50% 50%,rgba(124,58,255,0.04),transparent 70%)}
.boot-line{font-size:0.72rem;letter-spacing:0.04em;line-height:1.9;white-space:pre;overflow:hidden;max-width:100%;word-break:break-all}
.boot-line.c-dim{color:rgba(124,58,255,0.5)}.boot-line.c-ok{color:#00c853}.boot-line.c-warn{color:#ffab00}.boot-line.c-err{color:#ff3d3d}.boot-line.c-hi{color:var(--fire);font-weight:600}.boot-line.c-white{color:rgba(255,255,255,0.85)}.boot-line.c-fire{color:var(--fire)}
.boot-cursor{display:inline-block;width:9px;height:15px;background:var(--fire);vertical-align:middle;animation:blink 0.6s step-end infinite;margin-left:2px}
.boot-progress-wrap{margin-top:14px;padding-top:12px;border-top:1px solid rgba(124,58,255,0.1)}
.boot-prog-label{display:flex;justify-content:space-between;font-size:0.6rem;letter-spacing:0.16em;color:var(--dim);margin-bottom:7px}
.boot-prog-label span{color:var(--fire)}
.boot-prog-bar{height:3px;background:rgba(255,255,255,0.04);border-radius:3px;overflow:hidden}
.boot-prog-fill{height:100%;width:0;border-radius:3px;background:linear-gradient(90deg,rgba(124,58,255,0.8),var(--fire),var(--gold));box-shadow:0 0 10px var(--fire);transition:width 0.3s ease}

/* SCROLL TOP */
#stt{position:fixed;bottom:32px;right:32px;z-index:500;width:50px;height:50px;background:var(--fire);color:var(--white);border-radius:2px;display:flex;align-items:center;justify-content:center;font-size:1.2rem;opacity:0;pointer-events:none;transition:opacity 0.3s,transform 0.3s;box-shadow:0 0 30px var(--gf);cursor:pointer}
#stt.on{opacity:1;pointer-events:all}
#stt:hover{transform:translateY(-4px) scale(1.05)}

/* LAYOUT */
.W{width:min(1320px,92%);margin:auto}
section{position:relative}

/* HEADER */
header{position:fixed;top:0;left:0;right:0;z-index:1000;height:74px;transition:opacity 0.3s ease,transform 0.3s ease;backdrop-filter:blur(32px);-webkit-backdrop-filter:blur(32px);border-bottom:1px solid var(--b1)}
nav{height:100%;display:flex;align-items:center;justify-content:space-between}
.logo{display:flex;align-items:center;text-decoration:none;position:relative}
.logo-svg{width:auto;height:38px;overflow:visible;display:block}
.logo-path-rh{stroke:#f0f6ff;stroke-width:2.2;fill:none;stroke-linecap:round;stroke-linejoin:round;stroke-dasharray:400;stroke-dashoffset:400;animation:drawLogo 1.8s cubic-bezier(0.4,0,0.2,1) 0.4s forwards}
.logo-path-sq{stroke:var(--fire);stroke-width:2.2;fill:none;stroke-linecap:round;stroke-linejoin:round;stroke-dasharray:100;stroke-dashoffset:100;animation:drawLogo 0.7s cubic-bezier(0.4,0,0.2,1) 1.8s forwards}
.logo-text-sys{font-family:var(--ff-d);font-size:13px;letter-spacing:0.12em;fill:rgba(240,246,255,0);animation:logoFadeIn 0.6s ease 2.3s forwards}
.logo-accent{fill:var(--fire);filter:drop-shadow(0 0 5px rgba(124,58,255,0.9));animation:logoPulse 3s ease infinite 2.6s}
.logo-dot-svg{fill:var(--fire);animation:ldot 2s ease infinite,logoPulse 3s ease infinite 2.6s}
@keyframes drawLogo{to{stroke-dashoffset:0}}
@keyframes logoFadeIn{to{fill:rgba(240,246,255,0.95)}}
@keyframes ldot{0%,100%{opacity:1}50%{opacity:0.15}}
@keyframes logoPulse{0%,100%{filter:drop-shadow(0 0 5px rgba(124,58,255,0.9))}50%{filter:drop-shadow(0 0 16px rgba(168,85,247,1)) drop-shadow(0 0 30px rgba(168,85,247,0.5))}}
.logo:hover .logo-svg{animation:logoGlitch 0.35s steps(3) forwards}
@keyframes logoGlitch{0%{transform:none;filter:none}25%{transform:translate(-2px,0) skewX(-3deg);filter:hue-rotate(60deg) brightness(1.3)}50%{transform:translate(2px,0) skewX(3deg);filter:hue-rotate(-60deg)}75%{transform:translate(-1px,0);filter:brightness(1.8)}100%{transform:none;filter:none}}

.nl{display:flex;align-items:center;gap:36px}
.nl a{font-family:var(--ff-m);font-size:0.68rem;letter-spacing:0.12em;text-transform:uppercase;color:var(--dim2);transition:color 0.25s;position:relative}
.nl a::before{content:attr(data-n);position:absolute;top:-14px;left:0;font-size:0.5rem;color:var(--fire);opacity:0.6;letter-spacing:0.1em}
.nl a:hover{color:var(--fire)}
.nl-cta{padding:10px 22px;background:var(--fire);color:var(--white) !important;border-radius:2px;box-shadow:0 0 24px var(--gf)}
.hbtn{display:none;flex-direction:column;gap:5px;padding:6px;cursor:pointer}
.hbtn span{display:block;width:26px;height:2px;background:var(--fire);border-radius:1px;transition:opacity 0.3s ease,transform 0.3s ease}
.hbtn.x span:nth-child(2){opacity:0}
.hbtn.x span:nth-child(3){transform:translateY(-7px) rotate(-45deg)}
.mdr{display:none;position:fixed;inset:0;top:74px;background:rgba(3,6,10,0.98);backdrop-filter:blur(40px);flex-direction:column;align-items:center;justify-content:center;gap:48px;opacity:0;pointer-events:none;transition:opacity 0.3s;z-index:999}
.mdr.on{opacity:1;pointer-events:all}
.mdr a{font-family:var(--ff-d);font-size:2.8rem;letter-spacing:0.1em;color:var(--white);transition:color 0.2s,text-shadow 0.2s}
.mdr a:hover{color:var(--fire);text-shadow:0 0 40px var(--gf)}

/* HERO */
.hero{min-height:100dvh;display:flex;align-items:center;padding-top:74px;overflow:hidden;position:relative}
.hero-split{position:absolute;inset:0;z-index:-1;background:linear-gradient(105deg,var(--ink) 55%,#0a0d0f 55%)}
.hero-split::after{content:'';position:absolute;top:0;right:0;bottom:0;width:45%;background:radial-gradient(ellipse 80% 60% at 80% 50%,rgba(124,58,255,0.07),transparent 70%),radial-gradient(ellipse 60% 80% at 100% 80%,rgba(0,200,255,0.04),transparent 70%)}
.hero-vert{position:absolute;right:0;top:50%;transform:translateY(-50%);writing-mode:vertical-rl;text-orientation:mixed;font-family:var(--ff-d);font-size:clamp(5rem,12vw,9rem);letter-spacing:0.04em;color:rgba(255,255,255,0.03);user-select:none;pointer-events:none;z-index:1;white-space:nowrap;line-height:1}
.hero-inner{position:relative;z-index:2;width:100%;padding:80px 0}
.hero-grid{display:grid;grid-template-columns:1fr 1fr;gap:60px;align-items:center}
.hero-badge{display:inline-flex;align-items:center;gap:10px;padding:7px 18px;border-radius:99px;background:rgba(124,58,255,0.08);border:1px solid rgba(124,58,255,0.25);font-family:var(--ff-m);font-size:0.66rem;letter-spacing:0.2em;text-transform:uppercase;color:var(--fire);margin-bottom:2rem;box-shadow:0 0 24px rgba(124,58,255,0.1)}
.bdot{width:6px;height:6px;border-radius:50%;background:var(--fire);box-shadow:0 0 8px var(--fire);animation:bdot 2s ease infinite}
@keyframes bdot{0%,100%{opacity:1}50%{opacity:0.2}}
.hero-h1{font-family:var(--ff-d);font-size:clamp(3.5rem,6.5vw,6.2rem);line-height:0.96;letter-spacing:0.04em;color:var(--white);margin-bottom:2rem}
.hero-h1 .w1{display:block;overflow:hidden}
.hero-h1 .w1 span{display:block;animation:slideUp 0.9s var(--ease) both}
.hero-h1 .w1:nth-child(2) span{animation-delay:0.12s}
.hero-h1 .w1:nth-child(3) span{animation-delay:0.24s}
@keyframes slideUp{from{transform:translateY(105%);opacity:0}to{transform:translateY(0);opacity:1}}
.hero-h1 .fire-word{background:linear-gradient(90deg,var(--fire) 0%,var(--fire2) 40%,var(--gold) 100%);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;filter:drop-shadow(0 0 30px rgba(124,58,255,0.4))}
.hero-desc{color:var(--dim2);font-size:1rem;max-width:440px;margin-bottom:2.8rem;line-height:1.8;animation:fadeUp 1s 0.6s both}
.hero-btns{display:flex;gap:16px;flex-wrap:wrap;animation:fadeUp 1s 0.8s both}
.btn{display:inline-flex;align-items:center;gap:10px;padding:14px 32px;border-radius:2px;font-family:var(--ff-m);font-size:0.75rem;letter-spacing:0.1em;text-transform:uppercase;transition:opacity 0.3s ease,transform 0.3s ease;position:relative;overflow:hidden;cursor:pointer}
.btn-fire{background:var(--fire);color:var(--white);box-shadow:0 0 0 0 var(--gf)}
.btn-fire::before{content:'';position:absolute;inset:0;background:linear-gradient(135deg,rgba(255,255,255,0.2),transparent 60%);opacity:0;transition:opacity 0.3s}
.btn-fire:hover{transform:translateY(-3px)}
.btn-fire:hover::before{opacity:1}
.btn-ghost{background:transparent;color:var(--white);border:1px solid rgba(255,255,255,0.15)}
.btn-ghost:hover{border-color:var(--fire);color:var(--fire);transform:translateY(-3px)}
.hero-r{animation:fadeUp 1s 0.5s both}
.term-big{background:rgba(6,12,18,0.9);border:1px solid rgba(124,58,255,0.15);border-radius:8px;overflow:hidden;box-shadow:0 0 60px rgba(124,58,255,0.06),0 40px 80px rgba(0,0,0,0.5);position:relative}
.term-big::before{content:'';position:absolute;top:0;left:0;right:0;height:1px;background:linear-gradient(90deg,transparent,var(--fire),var(--gold),transparent)}
.tb-chrome{display:flex;align-items:center;gap:8px;padding:14px 20px;background:rgba(0,0,0,0.3);border-bottom:1px solid rgba(255,255,255,0.04)}
.tb-dots{display:flex;gap:6px}
.tb-dot{width:11px;height:11px;border-radius:50%}
.tbd1{background:#ff5f57}.tbd2{background:#ffbd2e}.tbd3{background:#28c840}
.tb-title{font-family:var(--ff-m);font-size:0.68rem;color:var(--dim);letter-spacing:0.08em;margin-left:10px;flex:1}
.tb-live{display:flex;align-items:center;gap:6px;font-family:var(--ff-m);font-size:0.65rem;color:var(--fire)}
.tbl{width:7px;height:7px;border-radius:50%;background:var(--fire);animation:tbl 1.4s ease infinite}
@keyframes tbl{0%,100%{box-shadow:0 0 0 0 var(--gf)}60%{box-shadow:0 0 0 5px transparent}}
.tb-body{padding:20px 24px;font-family:var(--ff-m);font-size:0.78rem;line-height:2}
.tl{display:flex;gap:10px;align-items:flex-start}
.tl-p{color:var(--fire);flex-shrink:0;opacity:0.7}
.tl-c{color:var(--dim2)}
.tl-c .v{color:#6deeff}.tl-c .g{color:#6dff9e}.tl-c .r{color:var(--fire)}.tl-c .w{color:var(--white)}.tl-c .y{color:var(--gold)}
.tb-cursor{display:inline-block;width:8px;height:14px;background:var(--fire);vertical-align:middle;animation:blink 0.8s step-end infinite}
@keyframes blink{0%,100%{opacity:1}50%{opacity:0}}
.hero-stats{display:flex;gap:0;margin-top:48px;border:1px solid var(--b1);border-radius:4px;overflow:hidden;animation:fadeUp 1s 1s both}
.hs{flex:1;padding:20px 24px;text-align:center;border-right:1px solid var(--b1);background:rgba(124,58,255,0.02);transition:background 0.3s}
.hs:last-child{border-right:none}
.hs:hover{background:rgba(124,58,255,0.05)}
.hs-n{font-family:var(--ff-d);font-size:1.8rem;letter-spacing:0.06em;color:var(--fire);line-height:1;text-shadow:0 0 30px var(--gf)}
.hs-l{font-family:var(--ff-m);font-size:0.6rem;letter-spacing:0.14em;text-transform:uppercase;color:var(--dim);margin-top:5px}

/* TICKER */
.ticker-wrap{background:var(--ink2);border-top:1px solid var(--b1);border-bottom:1px solid var(--b1);padding:0;overflow:hidden;position:relative}
.ticker-wrap::before,.ticker-wrap::after{content:'';position:absolute;top:0;bottom:0;width:80px;z-index:2;pointer-events:none}
.ticker-wrap::before{left:0;background:linear-gradient(90deg,var(--ink2),transparent)}
.ticker-wrap::after{right:0;background:linear-gradient(270deg,var(--ink2),transparent)}
.ticker-inner{display:flex;animation:tick 28s linear infinite;white-space:nowrap}
@keyframes tick{from{transform:translateX(0)}to{transform:translateX(-50%)}}
.ti{display:inline-flex;align-items:center;gap:10px;padding:14px 36px;font-family:var(--ff-m);font-size:0.7rem;letter-spacing:0.1em;color:var(--dim2);border-right:1px solid var(--b1)}
.ti .dot{width:5px;height:5px;border-radius:50%;flex-shrink:0}
.dot-f{background:var(--fire);box-shadow:0 0 8px var(--fire)}
.dot-i{background:var(--ice);box-shadow:0 0 6px var(--ice)}
.dot-g2{background:#00ff88;box-shadow:0 0 6px #00ff88}
.ti em{font-style:normal;color:var(--white);font-weight:600}

/* SERVICES */
#services{padding:140px 0;background:var(--ink)}
.sec-head{margin-bottom:80px}
.sec-eyebrow{font-family:var(--ff-m);font-size:0.66rem;letter-spacing:0.28em;text-transform:uppercase;color:var(--fire);display:inline-flex;align-items:center;gap:12px;margin-bottom:1.2rem}
.sec-eyebrow::before{content:'';width:28px;height:1px;background:var(--fire);box-shadow:0 0 8px var(--fire)}
.sec-title-xl{font-family:var(--ff-d);font-size:clamp(3.5rem,8vw,8rem);line-height:0.92;letter-spacing:0.04em;color:var(--white);position:relative}
.sec-title-xl .outline{-webkit-text-stroke:1px rgba(255,255,255,0.15);color:transparent}
.sec-title-xl .filled{color:var(--white)}
.sec-title-xl sup{font-family:var(--ff-m);font-size:0.2em;vertical-align:super;color:var(--fire);letter-spacing:0.2em}
.svc-reel-wrap{position:relative;overflow:hidden;margin:0 -4%;padding:0 4%;cursor:grab}
.svc-reel-wrap:active{cursor:grabbing}
.svc-reel-wrap::before,.svc-reel-wrap::after{content:'';position:absolute;top:0;bottom:0;width:120px;z-index:10;pointer-events:none}
.svc-reel-wrap::before{left:0;background:linear-gradient(90deg,var(--ink),transparent)}
.svc-reel-wrap::after{right:0;background:linear-gradient(270deg,var(--ink),transparent)}
.svc-layout{display:flex;gap:28px;padding:20px 40px 30px;overflow-x:auto;scroll-snap-type:x mandatory;scrollbar-width:none;-ms-overflow-style:none;cursor:grab;user-select:none}
.svc-layout:active{cursor:grabbing}
.svc-layout::-webkit-scrollbar{display:none}
.reel-hint{text-align:center;margin-top:20px;font-family:var(--ff-m);font-size:0.62rem;letter-spacing:0.2em;text-transform:uppercase;color:var(--dim);display:flex;align-items:center;justify-content:center;gap:10px}
.reel-hint::before,.reel-hint::after{content:'';flex:1;max-width:80px;height:1px;background:linear-gradient(90deg,transparent,var(--dim))}
.reel-hint::after{background:linear-gradient(270deg,transparent,var(--dim))}
.sc{background:var(--ink2);padding:0;position:relative;overflow:hidden;transition:background 0.4s var(--ease),transform 0.4s var(--ease);cursor:none;flex:0 0 380px;scroll-snap-align:start;border-radius:12px;border:1px solid var(--b1)}
.sc:hover{background:var(--ink3);transform:translateY(-6px) scale(1.01);box-shadow:0 30px 60px rgba(0,0,0,0.5),0 0 40px rgba(124,58,255,0.06)}
.sc-wm{position:absolute;bottom:-20px;right:-10px;font-family:var(--ff-d);font-size:8rem;color:rgba(124,58,255,0.04);line-height:1;pointer-events:none;user-select:none;transition:color 0.4s,transform 0.4s var(--ease)}
.sc:hover .sc-wm{color:rgba(124,58,255,0.07);transform:scale(1.05)}
.sc-inner{padding:52px 44px;position:relative;z-index:1}
.sc::before{content:'';position:absolute;left:0;top:0;bottom:100%;width:2px;background:linear-gradient(to bottom,var(--fire),var(--gold));transition:bottom 0.5s var(--ease);box-shadow:0 0 12px var(--fire)}
.sc:hover::before{bottom:0}
.sc-icon{width:60px;height:60px;margin-bottom:2rem;border-radius:6px;background:rgba(124,58,255,0.06);border:1px solid rgba(124,58,255,0.4);display:flex;align-items:center;justify-content:center;box-shadow:0 0 30px rgba(124,58,255,0.22)}
.sc-icon svg{width:28px;height:28px;stroke:var(--fire);fill:none;stroke-width:1.6;stroke-linecap:round;stroke-linejoin:round}
.sc-tag{font-family:var(--ff-m);font-size:0.6rem;letter-spacing:0.22em;color:var(--dim);text-transform:uppercase;margin-bottom:1rem}
.sc h3{font-family:var(--ff-d);font-size:clamp(1.4rem,2.2vw,1.8rem);letter-spacing:0.06em;color:var(--white);margin-bottom:1rem;line-height:1.1}
.sc p{color:var(--dim2);font-size:0.9rem;line-height:1.8}
.sc-arrow{display:inline-flex;align-items:center;gap:8px;font-family:var(--ff-m);font-size:0.68rem;letter-spacing:0.12em;text-transform:uppercase;color:var(--fire);margin-top:1.8rem;opacity:0;transform:translateX(-8px);transition:opacity 0.3s,transform 0.3s var(--ease)}
.sc:hover .sc-arrow{opacity:1;transform:translateX(0)}
.sc-arrow svg{width:14px;height:14px;stroke:currentColor;fill:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round}

/* TEAM */
#team{padding:140px 0;background:var(--ink2);position:relative;overflow:hidden}
#team::before{content:'OPERATORS';position:absolute;bottom:-60px;left:-20px;font-family:var(--ff-d);font-size:clamp(6rem,15vw,14rem);color:rgba(124,58,255,0.03);letter-spacing:0.08em;pointer-events:none;user-select:none;white-space:nowrap;line-height:1}
.team-head{display:flex;align-items:flex-end;justify-content:space-between;gap:40px;margin-bottom:80px;flex-wrap:wrap}
.team-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:28px;max-width:860px;margin:0 auto}
.tc{display:block;border:1px solid var(--b1);border-radius:12px;background:var(--ink);overflow:hidden;text-decoration:none;color:inherit;transition:border-color 0.4s,transform 0.4s var(--ease);position:relative;cursor:pointer}
.tc::after{content:'';position:absolute;inset:0;border-radius:12px;background:radial-gradient(ellipse 70% 50% at 50% 0%,rgba(124,58,255,0.05),transparent 60%);opacity:0;transition:opacity 0.4s}
.tc:hover{border-color:var(--b3);transform:translateY(-8px);box-shadow:0 40px 80px rgba(0,0,0,0.5),0 0 60px rgba(124,58,255,0.08)}
.tc:hover::after{opacity:1}
.tc-top{padding:48px 40px 36px;background:linear-gradient(160deg,#060e14,#030810);border-bottom:1px solid var(--b1);display:flex;align-items:center;gap:28px;position:relative;overflow:hidden}
.tc-top::before{content:'';position:absolute;top:-30px;right:-30px;width:150px;height:150px;border:1px solid rgba(124,58,255,0.06);border-radius:50%;box-shadow:0 0 0 25px rgba(124,58,255,0.03),0 0 0 50px rgba(255,58,0,0.015)}
.tc-av{width:84px;height:84px;border-radius:50%;flex-shrink:0;background:linear-gradient(135deg,#0d1e28,#03080f);border:2px solid rgba(124,58,255,0.3);display:flex;align-items:center;justify-content:center;font-family:var(--ff-d);font-size:1.4rem;letter-spacing:0.06em;color:var(--fire);position:relative;z-index:1;box-shadow:0 0 30px rgba(124,58,255,0.15),inset 0 0 20px rgba(124,58,255,0.04)}
.tc-av::after{content:'';position:absolute;inset:-5px;border-radius:50%;border:1px dashed rgba(255,58,0,0.18);animation:spin 10s linear infinite}
@keyframes spin{from{transform:rotate(0deg)}to{transform:rotate(360deg)}}
.tc-info{z-index:1}
.tc-info h3{font-family:var(--ff-d);font-size:2rem;letter-spacing:0.06em;color:var(--white);line-height:1;margin-bottom:6px}
.tc-role{font-family:var(--ff-m);font-size:0.66rem;letter-spacing:0.16em;text-transform:uppercase;color:var(--fire)}
.tc-body{padding:36px 40px}
.tc-body p{color:var(--dim2);font-size:0.92rem;margin-bottom:1.6rem;line-height:1.85}
.tc-skills{display:flex;flex-wrap:wrap;gap:8px;margin-bottom:2rem}
.sk{font-family:var(--ff-m);font-size:0.62rem;letter-spacing:0.08em;padding:5px 14px;border-radius:2px;border:1px solid rgba(124,58,255,0.12);color:var(--white)}
.tc-cta{display:inline-flex;align-items:center;gap:10px;font-family:var(--ff-m);font-size:0.7rem;letter-spacing:0.12em;text-transform:uppercase;color:var(--fire);transition:gap 0.3s var(--ease)}
.tc:hover .tc-cta{gap:16px}
.tc-cta svg{width:14px;height:14px;stroke:currentColor;fill:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round}

/* ═══════════════════════════════════════════
   INTEL / TELEMETRY SECTION — FULL REWRITE
   ═══════════════════════════════════════════ */
#intelligence{padding:140px 0;background:var(--ink);position:relative}
#intelligence::after{content:'';position:absolute;top:50%;right:-200px;transform:translateY(-50%);width:600px;height:600px;border-radius:50%;background:radial-gradient(circle,rgba(124,58,255,0.05),transparent 65%);pointer-events:none}
.intel-layout{display:grid;grid-template-columns:1fr 1.1fr;gap:80px;align-items:start;margin-top:4rem}
.intel-info p{color:var(--dim2);font-size:1rem;margin-bottom:2.5rem;line-height:1.85}
.intel-facts{display:flex;flex-direction:column;gap:0}
.if-row{display:flex;align-items:center;gap:16px;padding:18px 0;border-bottom:1px solid var(--b1)}
.if-row:first-child{border-top:1px solid var(--b1)}
.if-ico{width:38px;height:38px;border-radius:4px;background:rgba(124,58,255,0.06);border:1px solid var(--b1);display:flex;align-items:center;justify-content:center;flex-shrink:0}
.if-ico svg{width:16px;height:16px;stroke:var(--fire);fill:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round}
.if-text span{font-family:var(--ff-m);font-size:0.6rem;letter-spacing:0.16em;text-transform:uppercase;color:var(--dim);display:block;margin-bottom:2px}
.if-text strong{color:var(--white);font-weight:500;font-size:0.9rem}

/* INTEL HUD TERMINAL — no scroll, grid layout */
.intel-term{position:relative;border-radius:14px;overflow:hidden;background:linear-gradient(160deg,#07030f,#040210);box-shadow:0 0 0 1px rgba(124,58,255,0.2),0 0 60px rgba(124,58,255,0.07),0 40px 80px rgba(0,0,0,0.6)}
.intel-term::before{content:'';position:absolute;inset:0;border-radius:14px;z-index:0;padding:1px;background:conic-gradient(from var(--angle,0deg),rgba(124,58,255,0.8),rgba(168,85,247,0.4),rgba(56,189,248,0.6),rgba(232,121,249,0.4),rgba(124,58,255,0.8));-webkit-mask:linear-gradient(#fff 0 0) content-box,linear-gradient(#fff 0 0);-webkit-mask-composite:xor;mask-composite:exclude;animation:spinBorder 4s linear infinite}
@property --angle{syntax:'<angle>';initial-value:0deg;inherits:false}
@keyframes spinBorder{to{--angle:360deg}}

.it-chrome,.it-hud-row,.it-prompt,.it-body,.it-threat,.it-foot,.scan-beam,.scan-v,.it-c1,.it-c2,.it-c3,.it-c4{position:relative;z-index:2}
.it-c1,.it-c2,.it-c3,.it-c4{position:absolute;width:20px;height:20px;z-index:10;pointer-events:none}
.it-c1{top:1px;left:1px;border-top:2px solid var(--fire);border-left:2px solid var(--fire);border-radius:3px 0 0 0}
.it-c2{top:1px;right:1px;border-top:2px solid var(--fire);border-right:2px solid var(--fire);border-radius:0 3px 0 0}
.it-c3{bottom:1px;left:1px;border-bottom:2px solid var(--fire);border-left:2px solid var(--fire);border-radius:0 0 0 3px}
.it-c4{bottom:1px;right:1px;border-bottom:2px solid var(--fire);border-right:2px solid var(--fire);border-radius:0 0 3px 0}
.it-chrome{display:flex;align-items:center;gap:8px;padding:13px 20px;background:rgba(0,0,0,0.55);border-bottom:1px solid rgba(124,58,255,0.1)}
.it-dots{display:flex;gap:6px}
.it-dot{width:11px;height:11px;border-radius:50%}
.itd1{background:#ff5f57}.itd2{background:#ffbd2e}.itd3{background:#28c840}
.it-title{font-family:var(--ff-m);font-size:0.68rem;color:var(--dim);flex:1;margin-left:8px;letter-spacing:0.06em}
.it-live{display:flex;align-items:center;gap:6px;font-family:var(--ff-m);font-size:0.64rem;color:var(--fire)}
.itl{width:7px;height:7px;border-radius:50%;background:var(--fire);animation:tbl 1.4s ease infinite}
.it-hud-row{display:flex;justify-content:space-between;align-items:center;padding:8px 22px;background:rgba(124,58,255,0.05);border-bottom:1px solid rgba(124,58,255,0.07);font-family:var(--ff-m);font-size:0.58rem;letter-spacing:0.14em;text-transform:uppercase}
.hud-seg{display:flex;align-items:center;gap:7px;color:var(--dim2)}
.hud-seg .hv{color:var(--fire)}
.hud-blink{width:5px;height:5px;border-radius:50%;background:var(--fire);animation:tbl 1s ease infinite}
.scan-beam{position:absolute;left:0;right:0;top:0;z-index:9;pointer-events:none;height:3px;opacity:0;background:linear-gradient(90deg,transparent 0%,rgba(124,58,255,0.2) 20%,var(--fire) 50%,rgba(168,85,247,0.9) 80%,transparent 100%);box-shadow:0 0 16px var(--fire),0 0 40px rgba(124,58,255,0.5);filter:blur(0.5px);animation:scanb 3.5s ease-in-out infinite}
@keyframes scanb{0%{top:0;opacity:0}5%{opacity:1}90%{opacity:1}100%{top:100%;opacity:0}}
.scan-v{position:absolute;top:0;bottom:0;left:0;z-index:9;pointer-events:none;width:2px;opacity:0;background:linear-gradient(180deg,transparent,rgba(124,58,255,0.6),var(--fire),rgba(124,58,255,0.6),transparent);box-shadow:0 0 10px rgba(124,58,255,0.5);animation:scanv 5s ease-in-out 1.8s infinite}
@keyframes scanv{0%{left:0;opacity:0}4%{opacity:0.7}92%{opacity:0.7}100%{left:100%;opacity:0}}
.it-prompt{padding:10px 22px;border-bottom:1px solid rgba(124,58,255,0.06);display:flex;justify-content:space-between;align-items:center;background:rgba(0,0,0,0.25)}
.it-prompt code{font-family:var(--ff-m);font-size:0.72rem;color:rgba(124,58,255,0.7)}
#scStat{font-family:var(--ff-m);font-size:0.63rem;color:var(--dim)}
.ok{color:#28c840 !important}.fail{color:#ff4060 !important}.warn{color:#ffab00 !important}

/* DATA GRID — NO SCROLL */
.it-body{padding:10px 18px 14px}
.it-grid{display:grid;grid-template-columns:1fr 1fr;gap:0 12px}
.it-cat{grid-column:1/-1;padding:8px 0 3px;margin-top:6px}
.it-cat:first-child{margin-top:0}
.it-cat-label{font-family:var(--ff-m);font-size:0.54rem;letter-spacing:0.22em;text-transform:uppercase;color:var(--fire);opacity:0.8;display:flex;align-items:center;gap:8px}
.it-cat-label::after{content:'';flex:1;height:1px;background:rgba(124,58,255,0.18)}
.ir{display:flex;flex-direction:column;gap:1px;padding:5px 0;border-bottom:1px solid rgba(255,255,255,0.025);position:relative;overflow:hidden}
.ir::after{content:'';position:absolute;bottom:0;left:0;width:0;height:1px;background:linear-gradient(90deg,var(--fire),transparent);transition:width 0.8s var(--ease)}
.ir.lit::after{width:100%}
.ir:last-child{border-bottom:none}
.ik{font-family:var(--ff-m);font-size:0.54rem;color:var(--dim);letter-spacing:0.1em;text-transform:uppercase}
.ik::before{content:'⟩ ';color:var(--fire);opacity:0.45;font-size:0.85em}
.iv{font-family:var(--ff-m);font-size:0.7rem;color:#b8c8e0;word-break:break-all;transition:color 0.4s;line-height:1.3}
.iv.loading{color:var(--dim)}
.iv.loading::after{content:'▋';animation:blink 0.75s step-end infinite;font-size:0.7rem;color:var(--fire);opacity:0.7;margin-left:2px}
.iv.loaded{color:#d4b8ff;animation:valIn 0.4s var(--ease)}
@keyframes valIn{from{opacity:0;transform:translateX(6px)}to{opacity:1;transform:none}}
.iv.hi{background:rgba(124,58,255,0.1);border:1px solid rgba(124,58,255,0.35);border-radius:3px;padding:1px 8px;color:var(--fire) !important;text-shadow:0 0 14px rgba(124,58,255,0.6);animation:ping 2.5s ease-in-out infinite;display:inline-block}
@keyframes ping{0%,100%{box-shadow:0 0 0 0 rgba(124,58,255,0.4)}60%{box-shadow:0 0 0 8px rgba(124,58,255,0)}}
.iv.session-id{font-size:0.82rem;color:var(--gold) !important;text-shadow:0 0 20px rgba(232,121,249,0.5);letter-spacing:0.12em;font-weight:600}
.iv.live-clock{color:#6deeff !important;font-size:0.72rem}
.iv.ok-val{color:#28c840 !important}
.iv.warn-val{color:#ffab00 !important}

/* Threat bar */
.it-threat{padding:10px 22px 4px;border-top:1px solid rgba(124,58,255,0.06)}
.it-tl-label{display:flex;justify-content:space-between;font-family:var(--ff-m);font-size:0.58rem;letter-spacing:0.14em;text-transform:uppercase;color:var(--dim);margin-bottom:8px}
.it-tl-label span{color:var(--fire)}
.tbar{height:4px;background:rgba(255,255,255,0.04);border-radius:4px;overflow:hidden;position:relative}
.tbar-fill{height:100%;width:0;border-radius:4px;background:linear-gradient(90deg,rgba(124,58,255,0.8),var(--fire),var(--gold));box-shadow:0 0 12px var(--fire);transition:width 2.5s cubic-bezier(0.4,0,0.2,1) 0.5s}
.tbar-fill.go{width:73%}
.tbar::after{content:'';position:absolute;inset:0;background:linear-gradient(90deg,transparent,rgba(255,255,255,0.1),transparent);animation:barShimmer 2s ease infinite}
@keyframes barShimmer{0%{transform:translateX(-100%)}100%{transform:translateX(100%)}}
.it-foot{padding:9px 22px;background:rgba(124,58,255,0.03);border-top:1px solid rgba(124,58,255,0.06);display:flex;justify-content:space-between;font-family:var(--ff-m);font-size:0.6rem;color:var(--dim)}

/* CONTACT */
#contact{padding:140px 0;background:var(--ink2);position:relative;overflow:hidden}
#contact::before{content:'CONTACT';position:absolute;top:50%;left:50%;transform:translate(-50%,-50%);font-family:var(--ff-d);font-size:clamp(6rem,14vw,14rem);color:rgba(255,58,0,0.025);letter-spacing:0.1em;pointer-events:none;user-select:none;white-space:nowrap}
.contact-grid{display:grid;grid-template-columns:1fr 1.4fr;gap:100px;align-items:start;margin-top:4rem}
.c-left p{color:var(--dim2);font-size:1rem;margin-bottom:2.5rem;line-height:1.85}
.c-details{display:flex;flex-direction:column}
.cd{display:flex;align-items:flex-start;gap:16px;padding:20px 0;border-bottom:1px solid var(--b1)}
.cd:first-child{border-top:1px solid var(--b1)}
.cd-ico{width:40px;height:40px;border-radius:4px;background:rgba(124,58,255,0.06);border:1px solid var(--b1);display:flex;align-items:center;justify-content:center;flex-shrink:0}
.cd-ico svg{width:16px;height:16px;stroke:var(--fire);fill:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round}
.cd-t span{font-family:var(--ff-m);font-size:0.6rem;letter-spacing:0.16em;text-transform:uppercase;color:var(--dim);display:block;margin-bottom:3px}
.cd-t strong{color:var(--white);font-weight:500;font-size:0.92rem}
.c-note{margin-top:1.8rem;padding:16px 20px;border:1px solid rgba(124,58,255,0.12);border-radius:4px;background:rgba(124,58,255,0.03);font-family:var(--ff-m);font-size:0.68rem;color:var(--fire);letter-spacing:0.04em}
.c-note::before{content:'// ';opacity:0.5}
.c-form{background:var(--ink);border:1px solid var(--b1);border-radius:12px;padding:56px 52px;position:relative;overflow:hidden}
.c-form::before{content:'';position:absolute;top:0;left:0;right:0;height:1px;background:linear-gradient(90deg,transparent,var(--fire),var(--gold),transparent)}
.c-form::after{content:'';position:absolute;top:0;right:0;width:80px;height:80px;border-top:1px solid rgba(124,58,255,0.12);border-right:1px solid rgba(124,58,255,0.12);border-radius:0 12px 0 0}
.fg{display:grid;grid-template-columns:1fr 1fr;gap:20px}
.fi{display:flex;flex-direction:column;gap:8px;margin-bottom:22px}
.fi label{font-family:var(--ff-m);font-size:0.62rem;letter-spacing:0.16em;text-transform:uppercase;color:var(--dim2)}
.fi input,.fi textarea{background:rgba(0,0,0,0.3);border:1px solid rgba(255,255,255,0.06);border-radius:4px;padding:14px 18px;color:var(--white);font-family:var(--ff-b);font-size:16px;width:100%;transition:border-color 0.3s,box-shadow 0.3s;-webkit-appearance:none;caret-color:var(--fire)}
.fi input:focus,.fi textarea:focus{outline:none;border-color:rgba(124,58,255,0.35);background:rgba(255,58,0,0.025);box-shadow:0 0 0 3px rgba(124,58,255,0.06)}
.fi textarea{resize:vertical;min-height:140px}
.fsub{width:100%;padding:18px;background:var(--fire);color:var(--white);border-radius:4px;border:none;font-family:var(--ff-m);font-size:0.8rem;font-weight:600;letter-spacing:0.16em;text-transform:uppercase;transition:transform 0.3s ease,box-shadow 0.3s ease;cursor:pointer;position:relative;overflow:hidden;box-shadow:0 0 30px rgba(124,58,255,0.25)}
.fsub::before{content:'';position:absolute;top:0;left:-100%;right:100%;bottom:0;background:rgba(255,255,255,0.15);transition:left 0.4s var(--ease),right 0.4s var(--ease)}
.fsub:hover{transform:translateY(-2px);box-shadow:0 16px 50px rgba(124,58,255,0.35)}
.fsub:hover::before{left:0;right:0}
.fsub:disabled{opacity:0.5;transform:none;cursor:not-allowed}

/* SUCCESS */
#sov{position:fixed;inset:0;background:rgba(3,6,10,0.96);backdrop-filter:blur(20px);-webkit-backdrop-filter:blur(20px);display:flex;align-items:center;justify-content:center;z-index:99997;opacity:0;pointer-events:none;transition:opacity 0.4s}
#sov.on{opacity:1;pointer-events:all}
.sm{background:var(--ink2);border:1px solid var(--b3);border-radius:16px;padding:70px 60px;text-align:center;max-width:460px;width:90%;box-shadow:0 0 120px rgba(124,58,255,0.15),0 0 240px rgba(124,58,255,0.05);transform:scale(0.85) translateY(28px);transition:transform 0.5s cubic-bezier(0.175,0.885,0.32,1.275)}
#sov.on .sm{transform:scale(1) translateY(0)}
.sm-ring{width:92px;height:92px;border-radius:50%;border:2px solid var(--fire);margin:0 auto 28px;display:flex;align-items:center;justify-content:center;font-size:2.6rem;color:var(--fire);box-shadow:0 0 50px rgba(124,58,255,0.3)}
.sm h3{font-family:var(--ff-d);font-size:2rem;letter-spacing:0.08em;color:var(--white);margin-bottom:12px}
.sm p{color:var(--dim2);margin-bottom:32px}

/* FOOTER */
footer{background:var(--ink);border-top:1px solid var(--b1);padding:100px 0 48px}
.foot-grid{display:grid;grid-template-columns:1.6fr 1fr 1fr;gap:80px;margin-bottom:70px;padding-bottom:70px;border-bottom:1px solid var(--b1)}
.foot-logo{font-family:var(--ff-d);font-size:2.2rem;letter-spacing:0.08em;color:var(--white);margin-bottom:16px;display:flex;align-items:center;gap:8px}
.foot-logo em{font-style:normal;color:var(--fire);text-shadow:0 0 20px var(--gf)}
.foot-brand p{color:var(--dim2);font-size:0.92rem;max-width:300px;line-height:1.8}
.foot-col h5{font-family:var(--ff-m);font-size:0.63rem;letter-spacing:0.22em;text-transform:uppercase;color:var(--dim);margin-bottom:1.4rem}
.foot-col ul{display:flex;flex-direction:column;gap:12px}
.foot-col a{color:var(--dim2);font-size:0.9rem;transition:color 0.25s,padding-left 0.25s;display:flex;align-items:center;gap:0}
.foot-col a:hover{color:var(--fire);padding-left:8px}
.foot-bottom{display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:16px}
.foot-copy{font-family:var(--ff-m);font-size:0.62rem;color:rgba(61,84,104,0.6);letter-spacing:0.08em}
.foot-right{font-family:var(--ff-m);font-size:0.62rem;color:var(--dim)}
.foot-right span{color:var(--fire)}

/* SCROLL REVEAL */
.rv{opacity:1;transform:none}
.rv.in{opacity:1;transform:none}
.rv.d1{transition-delay:0.1s}.rv.d2{transition-delay:0.2s}.rv.d3{transition-delay:0.3s}.rv.d4{transition-delay:0.4s}.rv.d5{transition-delay:0.5s}

/* SCROLL WORM */
.sworm{position:absolute;bottom:36px;left:50%;transform:translateX(-50%);display:flex;flex-direction:column;align-items:center;gap:8px;font-family:var(--ff-m);font-size:0.58rem;letter-spacing:0.22em;text-transform:uppercase;color:var(--dim);z-index:10;animation:fadeUp 1s 1.2s both}
.sw-o{width:22px;height:38px;border:1.5px solid var(--dim);border-radius:11px;display:flex;justify-content:center;padding-top:5px}
.sw-i{width:3px;height:8px;background:var(--fire);border-radius:2px;box-shadow:0 0 6px var(--fire);animation:worm 2s ease-in-out infinite}
@keyframes worm{0%,100%{transform:translateY(0);opacity:1}80%{transform:translateY(16px);opacity:0}}

/* KEYFRAMES */
@keyframes fadeUp{from{opacity:0;transform:translateY(30px)}to{opacity:1;transform:translateY(0)}}
@keyframes fadeIn{from{opacity:0}to{opacity:1}}

/* MATRIX RAIN */
#matrixCanvas{position:absolute;inset:0;width:100%;height:100%;z-index:0;opacity:0.18;pointer-events:none}
#webglCanvas{position:absolute;top:0;right:0;bottom:0;left:0;width:100%;height:100%;z-index:1;pointer-events:none;opacity:0.9}

/* CLICK RIPPLE */
.ripple{position:fixed;border-radius:50%;pointer-events:none;z-index:9995;border:2px solid var(--fire);transform:translate(-50%,-50%) scale(0);animation:rippleOut 0.9s cubic-bezier(0.4,0,0.2,1) forwards}
@keyframes rippleOut{0%{transform:translate(-50%,-50%) scale(0);opacity:1}100%{transform:translate(-50%,-50%) scale(2.5);opacity:0}}
.ripple2{position:fixed;border-radius:50%;pointer-events:none;z-index:9994;background:radial-gradient(circle,rgba(124,58,255,0.15),transparent 70%);transform:translate(-50%,-50%) scale(0);animation:rippleOut2 1.2s cubic-bezier(0.4,0,0.2,1) forwards}
@keyframes rippleOut2{0%{transform:translate(-50%,-50%) scale(0);opacity:1}100%{transform:translate(-50%,-50%) scale(3.5);opacity:0}}

/* SVG PATH DRAW */
.svg-draw{position:absolute;top:0;left:0;pointer-events:none;z-index:3;opacity:0.25}
.svg-draw path,.svg-draw line,.svg-draw polyline{stroke-dasharray:2000;stroke-dashoffset:2000;animation:drawPath 3s cubic-bezier(0.4,0,0.2,1) 1.5s forwards}
@keyframes drawPath{to{stroke-dashoffset:0}}

/* WAVEFORM */
.wave-wrap{margin-top:28px;border:1px solid rgba(124,58,255,0.15);border-radius:8px;overflow:hidden;background:rgba(0,0,0,0.3);position:relative}
.wave-header{display:flex;justify-content:space-between;align-items:center;padding:10px 18px;border-bottom:1px solid rgba(124,58,255,0.08);font-family:var(--ff-m);font-size:0.62rem;letter-spacing:0.14em;text-transform:uppercase}
.wave-header .wh-l{color:var(--dim2)}
.wave-header .wh-r{color:var(--fire);display:flex;align-items:center;gap:6px}
.wave-blink{width:5px;height:5px;border-radius:50%;background:var(--fire);animation:tbl 1s ease infinite}
#waveCanvas{display:block;width:100%;height:120px}

/* 3D GLOBE */
#globeSection{padding:120px 0;background:var(--ink2);position:relative;overflow:hidden}
#globeSection::before{content:'GLOBAL THREAT INTEL';position:absolute;top:50%;left:50%;transform:translate(-50%,-50%);font-family:var(--ff-d);font-size:clamp(3rem,8vw,9rem);color:rgba(124,58,255,0.025);letter-spacing:0.1em;pointer-events:none;user-select:none;white-space:nowrap}
.globe-layout{display:grid;grid-template-columns:1fr 1fr;gap:60px;align-items:center;position:relative;z-index:1}
#globeCanvas{width:100%;height:480px;display:block;border-radius:12px}
.globe-stats{display:flex;flex-direction:column;gap:0;margin-top:2rem}
.gs{display:flex;align-items:center;justify-content:space-between;padding:16px 0;border-bottom:1px solid var(--b1)}
.gs:first-child{border-top:1px solid var(--b1)}
.gs-label{font-family:var(--ff-m);font-size:0.66rem;letter-spacing:0.14em;text-transform:uppercase;color:var(--dim2)}
.gs-val{font-family:var(--ff-d);font-size:1.5rem;color:var(--fire);letter-spacing:0.06em;text-shadow:0 0 20px rgba(124,58,255,0.4)}
.gs-trend{font-family:var(--ff-m);font-size:0.6rem;color:#28c840}

/* CHAT MODE BAR */
.chat-mode-bar{display:flex;border-bottom:1px solid rgba(124,58,255,0.1);background:rgba(0,0,0,0.2)}
.cm{flex:1;padding:8px 4px;font-family:var(--ff-m);font-size:0.58rem;letter-spacing:0.1em;text-transform:uppercase;color:var(--dim2);border-right:1px solid rgba(124,58,255,0.08);transition:color 0.2s,background 0.2s;background:none;cursor:pointer}
.cm:last-child{border-right:none}
.cm.active{color:var(--fire);background:rgba(124,58,255,0.08)}
.cm:hover:not(.active){color:var(--white);background:rgba(255,255,255,0.03)}
.chat-token-bar{height:2px;background:rgba(124,58,255,0.08)}
.chat-token-fill{height:100%;width:0;background:linear-gradient(90deg,var(--fire),var(--gold));transition:width 0.5s ease;box-shadow:0 0 8px var(--fire)}
.chat-typing{display:flex;align-items:center;gap:5px;padding:12px 16px;align-self:flex-start}
.chat-typing span{width:6px;height:6px;border-radius:50%;background:var(--fire);opacity:0.4;animation:chatDot 1.2s ease infinite}
.chat-typing span:nth-child(2){animation-delay:0.2s}
.chat-typing span:nth-child(3){animation-delay:0.4s}
@keyframes chatDot{0%,80%,100%{opacity:0.2;transform:scale(0.8)}40%{opacity:1;transform:scale(1.2)}}

/* AI CHATBOT */
#chatBtn{position:fixed;bottom:32px;right:96px;z-index:500;width:56px;height:56px;border-radius:50%;background:linear-gradient(135deg,#7c3aff,#a855f7);color:var(--white);display:flex;align-items:center;justify-content:center;font-size:1.4rem;cursor:pointer;box-shadow:0 0 0 0 rgba(124,58,255,0.4);animation:chatPulse 2.5s ease infinite;transition:transform 0.3s;border:none}
@keyframes chatPulse{0%,100%{box-shadow:0 0 0 0 rgba(124,58,255,0.4)}50%{box-shadow:0 0 0 12px rgba(124,58,255,0)}}
#chatBtn:hover{transform:scale(1.1)}
#chatBtn.open{animation:none;background:linear-gradient(135deg,#ff3a00,#ff6a00)}
#chatBox{position:fixed;bottom:100px;right:24px;z-index:9000;width:380px;max-width:calc(100vw - 32px);background:var(--ink2);border:1px solid rgba(124,58,255,0.25);border-radius:16px;overflow:hidden;box-shadow:0 0 0 1px rgba(124,58,255,0.1),0 40px 80px rgba(0,0,0,0.7);opacity:0;pointer-events:none;transform:translateY(20px) scale(0.95);transition:opacity 0.3s ease,transform 0.3s ease;display:flex;flex-direction:column}
#chatBox.on{opacity:1;pointer-events:all;transform:translateY(0) scale(1)}
.chat-hdr{padding:16px 20px;background:linear-gradient(135deg,rgba(124,58,255,0.15),rgba(168,85,247,0.08));border-bottom:1px solid rgba(124,58,255,0.12);display:flex;align-items:center;gap:12px}
.chat-av{width:36px;height:36px;border-radius:50%;background:linear-gradient(135deg,#7c3aff,#a855f7);display:flex;align-items:center;justify-content:center;font-size:1rem;flex-shrink:0}
.chat-hdr-info h4{font-family:var(--ff-d);font-size:0.95rem;letter-spacing:0.06em;color:var(--white)}
.chat-hdr-info p{font-family:var(--ff-m);font-size:0.6rem;color:var(--fire);letter-spacing:0.1em}
.chat-close{margin-left:auto;color:var(--dim2);font-size:1.2rem;cursor:pointer;line-height:1;background:none;border:none;padding:4px}
.chat-close:hover{color:var(--white)}
.chat-msgs{flex:1;overflow-y:auto;padding:16px;display:flex;flex-direction:column;gap:12px;min-height:260px;max-height:340px}
.chat-msgs::-webkit-scrollbar{width:3px}
.chat-msgs::-webkit-scrollbar-thumb{background:rgba(124,58,255,0.3);border-radius:3px}
.msg{max-width:88%;padding:10px 14px;border-radius:12px;font-size:0.85rem;line-height:1.6;animation:msgIn 0.3s var(--ease)}
@keyframes msgIn{from{opacity:0;transform:translateY(8px)}to{opacity:1;transform:none}}
.msg.bot{background:rgba(124,58,255,0.1);border:1px solid rgba(124,58,255,0.15);color:var(--white);align-self:flex-start;border-radius:4px 12px 12px 12px}
.msg.user{background:linear-gradient(135deg,rgba(124,58,255,0.25),rgba(168,85,247,0.15));color:var(--white);align-self:flex-end;border-radius:12px 4px 12px 12px}
.chat-foot{padding:12px 16px;border-top:1px solid rgba(124,58,255,0.1);display:flex;gap:10px;align-items:center}
.chat-inp{flex:1;background:rgba(0,0,0,0.3);border:1px solid rgba(124,58,255,0.15);border-radius:8px;padding:10px 14px;color:var(--white);font-family:var(--ff-b);font-size:0.85rem;outline:none;transition:border-color 0.25s;caret-color:var(--fire)}
.chat-inp:focus{border-color:rgba(124,58,255,0.4)}
.chat-inp::placeholder{color:var(--dim)}
.chat-send{width:38px;height:38px;border-radius:8px;background:linear-gradient(135deg,#7c3aff,#a855f7);color:var(--white);border:none;cursor:pointer;display:flex;align-items:center;justify-content:center;font-size:1rem;transition:transform 0.2s;flex-shrink:0}
.chat-send:hover{transform:scale(1.08);box-shadow:0 0 20px rgba(124,58,255,0.4)}
.chat-send:disabled{opacity:0.4;transform:none}
.chat-suggestions{display:flex;flex-wrap:wrap;gap:6px;padding:4px 0}
.cs{font-family:var(--ff-m);font-size:0.62rem;letter-spacing:0.06em;padding:5px 10px;border:1px solid rgba(124,58,255,0.2);border-radius:6px;color:var(--dim2);cursor:pointer;transition:color 0.2s,border-color 0.2s,background 0.2s;background:rgba(124,58,255,0.04)}
.cs:hover{color:var(--fire);border-color:rgba(124,58,255,0.5);background:rgba(124,58,255,0.08)}

/* CINEMATIC TRANSITIONS */
.sec-transition{position:fixed;inset:0;z-index:9996;pointer-events:none;display:grid;grid-template-columns:repeat(6,1fr)}
.st-slat{background:var(--ink);transform:scaleY(0);transform-origin:bottom;transition:transform 0.6s cubic-bezier(0.86,0,0.07,1)}
.sec-transition.in .st-slat{transform:scaleY(1)}
.sec-transition.in .st-slat:nth-child(1){transition-delay:0s}.sec-transition.in .st-slat:nth-child(2){transition-delay:0.04s}.sec-transition.in .st-slat:nth-child(3){transition-delay:0.08s}.sec-transition.in .st-slat:nth-child(4){transition-delay:0.12s}.sec-transition.in .st-slat:nth-child(5){transition-delay:0.16s}.sec-transition.in .st-slat:nth-child(6){transition-delay:0.2s}
.sec-transition.out .st-slat{transform:scaleY(0);transform-origin:top}
.sec-transition.out .st-slat:nth-child(1){transition-delay:0.2s}.sec-transition.out .st-slat:nth-child(2){transition-delay:0.16s}.sec-transition.out .st-slat:nth-child(3){transition-delay:0.12s}.sec-transition.out .st-slat:nth-child(4){transition-delay:0.08s}.sec-transition.out .st-slat:nth-child(5){transition-delay:0.04s}.sec-transition.out .st-slat:nth-child(6){transition-delay:0s}

/* CURSOR TRAIL */
.cursor-trail{position:fixed;border-radius:50%;pointer-events:none;z-index:99993;background:rgba(124,58,255,0.4);transform:translate(-50%,-50%);transition:width 0.3s,height 0.3s,opacity 0.5s}

/* WIPE REVEAL */
.rv.wipe{opacity:1 !important;transform:none !important;clip-path:inset(0 100% 0 0);transition:clip-path 1.1s cubic-bezier(0.16,1,0.3,1)}
.rv.wipe.in{clip-path:inset(0 0% 0 0)}

/* PERFORMANCE */
.ticker-inner{transform:translateZ(0);backface-visibility:hidden;will-change:transform}
.scan-beam,.scan-v{transform:translateZ(0);backface-visibility:hidden}
#pre{transform:translateZ(0)}
#chatBox{transform:translateZ(0);backface-visibility:hidden}
.logo-path-rh{filter:none !important}
.hero{min-height:100vh}
#webglCanvas,#matrixCanvas,#shaderCanvas{position:absolute;width:100% !important;height:100% !important}
.sec-title-xl,.hero-h1{-webkit-font-smoothing:antialiased;text-rendering:optimizeLegibility}
@font-face{font-display:swap}
.sc{transition:transform 0.4s cubic-bezier(0.23,1,0.32,1),box-shadow 0.4s ease}
.tc{transition:transform 0.4s cubic-bezier(0.23,1,0.32,1),box-shadow 0.4s ease}
.btn{transition:transform 0.3s ease,background 0.3s ease,box-shadow 0.3s ease}
header{transition:background 0.4s ease,box-shadow 0.4s ease;transform:translateZ(0);backface-visibility:hidden}

/* 3D TILT */
.tc,.sc{transform-style:preserve-3d;will-change:transform}
.tc::before{content:'';position:absolute;inset:0;border-radius:12px;background:radial-gradient(circle at var(--gx,50%) var(--gy,50%),rgba(124,58,255,0.12),transparent 60%);opacity:0;transition:opacity 0.3s;z-index:0;pointer-events:none}
.tc:hover::before{opacity:1}
.sc::after{content:'';position:absolute;inset:0;background:radial-gradient(circle at var(--gx,50%) var(--gy,50%),rgba(124,58,255,0.08),transparent 55%);opacity:0;transition:opacity 0.3s;pointer-events:none}
.sc:hover::after{opacity:1}

/* RESPONSIVE */
@media(max-width:1100px){.hero-grid{grid-template-columns:1fr;gap:60px}.hero-r{display:none}.hero-h1{font-size:clamp(3rem,8vw,5.5rem)}.intel-layout{grid-template-columns:1fr;gap:60px}.foot-grid{grid-template-columns:1fr 1fr}}
@media(max-width:900px){.svc-layout{grid-template-columns:1fr}.team-cards{grid-template-columns:1fr}.contact-grid{grid-template-columns:1fr;gap:60px}.hero-stats{flex-wrap:wrap}.hs{min-width:45%}.nl{display:none}.hbtn{display:flex}.mdr{display:flex}.tc{margin-bottom:20px}section{padding:80px 0}.foot-grid{grid-template-columns:1fr;gap:40px}.foot-bottom{flex-direction:column;text-align:center;gap:12px}.c-form{padding:32px 24px}.fg{grid-template-columns:1fr}body{cursor:auto}#cur{display:none}button,a{cursor:pointer}}
@media(max-width:768px){.hero-h1{font-size:clamp(2.6rem,9vw,4rem) !important}.hero-stats{flex-wrap:wrap;gap:20px}.hs{flex:1 1 calc(50% - 10px)}.hero-btns{flex-direction:column;align-items:center;gap:12px}.hero-btns .btn{width:100%;max-width:280px;text-align:center;justify-content:center}.sec-title-xl{font-size:clamp(2rem,8vw,3.2rem) !important}.sec-head{text-align:center}.sc{flex:0 0 min(320px,85vw)}.team-grid{grid-template-columns:1fr !important;gap:20px}.it-grid{grid-template-columns:1fr}.c-form{padding:28px 18px}.fg{grid-template-columns:1fr}}
@media(max-width:480px){.hero-h1{font-size:clamp(2rem,10vw,3rem) !important}.hero-stats{flex-direction:column;align-items:flex-start;gap:16px}.hs{width:100%}.hero-badge{font-size:0.6rem}.sec-title-xl{font-size:clamp(1.8rem,9vw,2.8rem) !important}section{padding:60px 0}.sc{flex:0 0 88vw}.sc-inner{padding:24px 18px}.tc-av{width:64px;height:64px;font-size:1.4rem}#chatBox{width:calc(100vw - 24px) !important;right:12px !important;bottom:70px !important;max-height:70vh}#chatBtn{right:16px;bottom:16px}#stt{right:16px;bottom:72px}header{padding:0 16px}.logo-svg{width:150px}.it-grid{grid-template-columns:1fr}}
@media(min-width:901px){.hero-vert{display:block !important}.hero-r{display:block !important}}
</style>
</head>
<body>
<div class="sec-transition" id="secTrans"><div class="st-slat"></div><div class="st-slat"></div><div class="st-slat"></div><div class="st-slat"></div><div class="st-slat"></div><div class="st-slat"></div></div>
<main id="scroll-container" data-scroll-container>
<div id="cur"><div class="cur-d"></div><div class="cur-r"></div></div>

<!-- PRELOADER -->
<div id="pre">
  <div class="pre-os">
    <div class="bios-top"><span>RH²-SYS BIOS v4.2.1 · SECURE BOOT ENABLED</span><strong id="bootTime">00:00:00</strong></div>
    <div class="bios-screen">
      <div id="bootLines"></div>
      <span class="boot-cursor" id="bootCursor"></span>
      <div class="boot-progress-wrap" id="bootPWrap" style="display:none">
        <div class="boot-prog-label">SYSTEM READY <span id="bootPct">0%</span></div>
        <div class="boot-prog-bar"><div class="boot-prog-fill" id="bootFill"></div></div>
      </div>
    </div>
  </div>
</div>

<div id="sov" role="dialog" aria-modal="true"><div class="sm"><div class="sm-ring">✓</div><h3>TRANSMISSION SECURED</h3><p>Message encrypted and delivered to RH²-Systems servers.</p><button class="fsub" id="closeSov" style="max-width:200px;margin:auto;display:block;">ACKNOWLEDGE</button></div></div>
<button id="stt" aria-label="Back to top">↑</button>
<button id="chatBtn" aria-label="Chat with RH² AI">🛡️</button>

<!-- CHAT BOX -->
<div id="chatBox" role="dialog" aria-label="RH² AI Assistant">
  <div class="chat-hdr"><div class="chat-av">🛡️</div><div class="chat-hdr-info"><h4>RH²-AI ASSIST</h4><p>Offline · End-to-end encrypted</p></div><button class="chat-close" id="chatClose" aria-label="Close chat">✕</button></div>
  <div class="chat-mode-bar"><button class="cm active" data-mode="general">General</button><button class="cm" data-mode="pentest">PenTest</button><button class="cm" data-mode="redteam">Red Team</button><button class="cm" data-mode="quote">Get Quote</button></div>
  <div class="chat-token-bar"><div class="chat-token-fill" id="chatTokenFill"></div></div>
  <div class="chat-msgs" id="chatMsgs">
    <div class="msg bot">Hello, Operator. I'm RH²-AI — your encrypted security intelligence assistant. I can answer technical questions, explain our offensive capabilities, or help scope an engagement. How can I help you today?</div>
    <div class="chat-suggestions" id="chatSugg"><button class="cs">What is Red Teaming?</button><button class="cs">How does PenTesting work?</button><button class="cs">How much does it cost?</button><button class="cs">Who are your operators?</button></div>
  </div>
  <div class="chat-foot"><input class="chat-inp" id="chatInp" type="text" placeholder="Ask anything about security..." maxlength="600" autocomplete="off"><button class="chat-send" id="chatSend" aria-label="Send">➤</button></div>
</div>

<!-- HEADER -->
<header id="hdr">
  <div class="W"><nav>
    <a href="#" class="logo" aria-label="RH²-Systems">
      <svg class="logo-svg" viewBox="0 0 200 42" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
        <path class="logo-path-rh" d="M6,34 L6,8 L18,8 Q28,8 28,18 Q28,28 18,28 L6,28 M18,28 L30,34"/>
        <path class="logo-path-rh" d="M36,8 L36,34 M36,21 L50,21 M50,8 L50,34" style="animation-delay:0.9s"/>
        <path class="logo-path-sq" d="M55,6 Q55,2 59,2 Q63,2 63,5 Q63,8 55,11 L63,11"/>
        <line class="logo-path-sq" x1="68" y1="10" x2="68" y2="34" style="stroke:rgba(240,246,255,0.25);stroke-dasharray:24;stroke-dashoffset:24;animation-delay:2s"/>
        <text class="logo-text-sys" x="74" y="29">SYSTEMS</text>
        <circle class="logo-dot-svg" cx="194" cy="8" r="3.5"/>
        <line x1="74" y1="33" x2="186" y2="33" stroke="var(--fire)" stroke-width="1.2" opacity="0" class="logo-accent" style="animation:logoFadeIn 0.5s ease 2.6s forwards"/>
      </svg>
    </a>
    <ul class="nl">
      <li><a href="#services" data-n="01">Services</a></li>
      <li><a href="#team" data-n="02">Team</a></li>
      <li><a href="#intelligence" data-n="03">Intel</a></li>
      <li><a href="#contact" class="nl-cta">Contact</a></li>
    </ul>
    <button class="hbtn" id="hbtn" aria-label="Menu" aria-expanded="false"><span></span><span></span><span></span></button>
  </nav></div>
</header>

<nav class="mdr" id="mdr"><a href="#services" class="ml">Services</a><a href="#team" class="ml">Team</a><a href="#intelligence" class="ml">Intel</a><a href="#contact" class="ml">Contact</a></nav>

<!-- HERO -->
<section class="hero">
  <canvas id="matrixCanvas" aria-hidden="true"></canvas>
  <canvas id="webglCanvas" aria-hidden="true"></canvas>
  <div class="hero-split" aria-hidden="true"></div>
  <svg class="svg-draw" width="100%" height="100%" viewBox="0 0 1400 900" preserveAspectRatio="xMidYMid slice" aria-hidden="true">
    <path d="M0,450 Q350,100 700,450 Q1050,800 1400,450" stroke="rgba(124,58,255,0.8)" stroke-width="1" fill="none"/>
    <path d="M0,200 Q200,500 400,300 Q600,100 800,400 Q1000,700 1200,350 Q1350,150 1400,300" stroke="rgba(168,85,247,0.5)" stroke-width="0.8" fill="none"/>
    <line x1="0" y1="0" x2="400" y2="900" stroke="rgba(124,58,255,0.2)" stroke-width="0.6"/>
    <line x1="1400" y1="0" x2="1000" y2="900" stroke="rgba(124,58,255,0.2)" stroke-width="0.6"/>
    <polyline points="100,50 200,200 150,350 300,400 250,550" stroke="rgba(232,121,249,0.4)" stroke-width="0.8" fill="none"/>
    <polyline points="1300,50 1200,200 1250,350 1100,400 1150,600" stroke="rgba(232,121,249,0.4)" stroke-width="0.8" fill="none"/>
  </svg>
  <div class="hero-vert" aria-hidden="true">OFFENSIVE</div>
  <div class="orb-p" style="position:absolute;width:500px;height:500px;top:20%;left:30%;border-radius:50%;background:radial-gradient(circle,rgba(124,58,255,0.06),transparent 65%);pointer-events:none;will-change:transform;"></div>
  <div class="orb-p" style="position:absolute;width:350px;height:350px;bottom:10%;right:15%;border-radius:50%;background:radial-gradient(circle,rgba(168,85,247,0.05),transparent 65%);pointer-events:none;will-change:transform;"></div>
  <div class="orb-p" style="position:absolute;width:250px;height:250px;top:60%;left:10%;border-radius:50%;background:radial-gradient(circle,rgba(56,189,248,0.04),transparent 65%);pointer-events:none;will-change:transform;"></div>
  <div class="W hero-inner">
    <div class="hero-grid">
      <div class="hero-l">
        <div class="hero-badge"><span class="bdot"></span>SYSTEM OPERATIONAL · <span id="utcClock">00:00:00 UTC</span></div>
        <h1 class="hero-h1">
          <div class="w1"><span>OFFENSIVE</span></div>
          <div class="w1"><span class="fire-word">SECURITY.</span></div>
          <div class="w1"><span id="typeEl"></span><span class="tb-cursor" aria-hidden="true"></span></div>
        </h1>
        <p class="hero-desc">Advanced penetration testing, red team operations, and secure engineering for high-risk enterprise infrastructure worldwide.</p>
        <div class="hero-btns">
          <a href="#contact" class="btn btn-fire"><svg viewBox="0 0 24 24" width="16" height="16" stroke="currentColor" fill="none" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg>Initiate Confidential Audit</a>
          <a href="#services" class="btn btn-ghost">Explore Capabilities<svg viewBox="0 0 24 24" width="14" height="14" stroke="currentColor" fill="none" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="9 18 15 12 9 6"/></svg></a>
        </div>
        <div class="hero-stats">
          <div class="hs"><div class="hs-n">150+</div><div class="hs-l">Engagements</div></div>
          <div class="hs"><div class="hs-n">100%</div><div class="hs-l">Confidentiality</div></div>
          <div class="hs"><div class="hs-n">24/7</div><div class="hs-l">Support</div></div>
          <div class="hs"><div class="hs-n">0</div><div class="hs-l">Breaches</div></div>
        </div>
      </div>
      <div class="hero-r">
        <div class="term-big">
          <div class="tb-chrome"><div class="tb-dots"><div class="tb-dot tbd1"></div><div class="tb-dot tbd2"></div><div class="tb-dot tbd3"></div></div><span class="tb-title">rh2sys — active_session</span><div class="tb-live"><span class="tbl"></span>LIVE</div></div>
          <div class="tb-body">
            <div class="tl"><span class="tl-p">$</span><span class="tl-c"><span class="g">rh2sys</span> --init offensive_mode</span></div>
            <div class="tl"><span class="tl-p">›</span><span class="tl-c"><span class="v">Loading</span> exploit framework... <span class="g">OK</span></span></div>
            <div class="tl"><span class="tl-p">›</span><span class="tl-c"><span class="v">Scanning</span> attack surface... <span class="g">OK</span></span></div>
            <div class="tl"><span class="tl-p">›</span><span class="tl-c"><span class="v">Target</span> vectors: <span class="y">14 identified</span></span></div>
            <div class="tl"><span class="tl-p">›</span><span class="tl-c"><span class="v">CVE database</span>: <span class="w">1,240+ loaded</span></span></div>
            <div class="tl"><span class="tl-p">›</span><span class="tl-c"><span class="r">CRITICAL</span>: <span class="w">3 zero-days staged</span></span></div>
            <div class="tl"><span class="tl-p">›</span><span class="tl-c"><span class="v">Encryption</span>: <span class="g">AES-256 active</span></span></div>
            <div class="tl"><span class="tl-p">$</span><span class="tl-c"><span class="g">_</span></span></div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="sworm" aria-hidden="true"><div class="sw-o"><div class="sw-i"></div></div>Scroll</div>
</section>

<!-- TICKER -->
<div class="ticker-wrap" aria-hidden="true">
  <div class="ticker-inner" id="ticker">
    <div class="ti"><span class="dot dot-f"></span>THREATS BLOCKED: <em>2,847</em></div>
    <div class="ti"><span class="dot dot-g2"></span>ACTIVE ENGAGEMENTS: <em>14</em></div>
    <div class="ti"><span class="dot dot-f"></span>CVEs RESEARCHED: <em>1,240+</em></div>
    <div class="ti"><span class="dot dot-i"></span>CLIENT BREACHES: <em>ZERO</em></div>
    <div class="ti"><span class="dot dot-f"></span>RED TEAM OPS LIVE: <em>3</em></div>
    <div class="ti"><span class="dot dot-g2"></span>UPTIME: <em>99.99%</em></div>
    <div class="ti"><span class="dot dot-i"></span>ENCRYPTED CHANNELS: <em>ACTIVE</em></div>
    <div class="ti"><span class="dot dot-f"></span>ZERO-DAYS STAGED: <em>3</em></div>
    <div class="ti"><span class="dot dot-f"></span>THREATS BLOCKED: <em>2,847</em></div>
    <div class="ti"><span class="dot dot-g2"></span>ACTIVE ENGAGEMENTS: <em>14</em></div>
    <div class="ti"><span class="dot dot-f"></span>CVEs RESEARCHED: <em>1,240+</em></div>
    <div class="ti"><span class="dot dot-i"></span>CLIENT BREACHES: <em>ZERO</em></div>
    <div class="ti"><span class="dot dot-f"></span>RED TEAM OPS LIVE: <em>3</em></div>
    <div class="ti"><span class="dot dot-g2"></span>UPTIME: <em>99.99%</em></div>
    <div class="ti"><span class="dot dot-i"></span>ENCRYPTED CHANNELS: <em>ACTIVE</em></div>
    <div class="ti"><span class="dot dot-f"></span>ZERO-DAYS STAGED: <em>3</em></div>
  </div>
</div>

<!-- SERVICES -->
<section id="services">
  <div class="W">
    <div class="sec-head rv wipe">
      <div class="sec-eyebrow">01 — Capabilities</div>
      <div class="sec-title-xl"><span class="filled">CORE</span><br><span class="outline">SECURITY</span><br><span class="filled">SERVICES<sup>03</sup></span></div>
    </div>
    <div class="svc-reel-wrap"><div class="svc-layout" id="svcReel">
      <div class="sc rv"><div class="sc-wm">01</div><div class="sc-inner"><div class="sc-icon"><svg viewBox="0 0 24 24"><circle cx="11" cy="11" r="8"/><line x1="21" y1="21" x2="16.65" y2="16.65"/></svg></div><div class="sc-tag">SVC_001</div><h3>Penetration Testing</h3><p>Manual and automated assessments of Web, Mobile, API, and Cloud infrastructure aligned with OWASP Top 10 and NIST frameworks.</p><div class="sc-arrow">Engage<svg viewBox="0 0 24 24"><line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/></svg></div></div></div>
      <div class="sc rv d2"><div class="sc-wm">02</div><div class="sc-inner"><div class="sc-icon"><svg viewBox="0 0 24 24"><polygon points="13 2 3 14 12 14 11 22 21 10 12 10 13 2"/></svg></div><div class="sc-tag">SVC_002</div><h3>Red Team Operations</h3><p>Adversary simulation replicating nation-state APT tactics to test your detection and response capabilities in real-time scenarios.</p><div class="sc-arrow">Engage<svg viewBox="0 0 24 24"><line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/></svg></div></div></div>
      <div class="sc rv d4"><div class="sc-wm">03</div><div class="sc-inner"><div class="sc-icon"><svg viewBox="0 0 24 24"><polyline points="16 18 22 12 16 6"/><polyline points="8 6 2 12 8 18"/></svg></div><div class="sc-tag">SVC_003</div><h3>Secure Engineering</h3><p>DevSecOps integration, Zero Trust architecture design, and source code review to embed security into the DNA of your software.</p><div class="sc-arrow">Engage<svg viewBox="0 0 24 24"><line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/></svg></div></div></div>
    </div></div>
    <div class="reel-hint">← Drag to explore →</div>
  </div>
</section>

<!-- TEAM -->
<section id="team">
  <div class="W">
    <div class="team-head rv wipe">
      <div class="rv">
        <div class="sec-eyebrow">02 — Leadership</div>
        <div class="sec-title-xl"><span class="filled">THE</span><br><span class="outline">OPERATORS</span></div>
      </div>
      <p style="color:var(--dim2);max-width:340px;font-size:0.98rem;line-height:1.85" class="rv d2">Built by engineers who understand both the attack vector and the defense mechanism.</p>
    </div>
    <div class="team-grid">
      <a href="https://rh-systems.github.io/Raj-Hridoy/" target="_blank" rel="noopener noreferrer" class="tc rv d1">
        <div class="tc-top"><div class="tc-av">RH</div><div class="tc-info"><h3>Raj Hridoy</h3><span class="tc-role">Cybersecurity Engineer</span></div></div>
        <div class="tc-body"><p>Specializing in secure software architecture and complex vulnerability analysis. Raj bridges high-level development with low-level security protocols.</p><div class="tc-skills"><span class="sk">Secure Arch</span><span class="sk">Python / Go</span><span class="sk">Cloud Security</span><span class="sk">DevSecOps</span></div><div class="tc-cta">View Profile<svg viewBox="0 0 24 24"><line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/></svg></div></div>
      </a>
      <a href="https://rh-systems.github.io/Riyad-Hasan/" target="_blank" rel="noopener noreferrer" class="tc rv d2">
        <div class="tc-top"><div class="tc-av">RH</div><div class="tc-info"><h3>Riyad Hasan</h3><span class="tc-role">Ethical Hacker</span></div></div>
        <div class="tc-body"><p>Focused on advanced threat modeling and penetration testing. Riyad specializes in breaking systems to make them unbreakable through adversarial analysis.</p><div class="tc-skills"><span class="sk">PenTesting</span><span class="sk">Network Forensics</span><span class="sk">Red Teaming</span><span class="sk">Exploit Dev</span></div><div class="tc-cta">View Profile<svg viewBox="0 0 24 24"><line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/></svg></div></div>
      </a>
    </div>
  </div>
</section>

<!-- INTEL -->
<section id="intelligence">
  <div class="W">
    <div class="rv" style="text-align:center;margin-bottom:0">
      <div class="sec-eyebrow" style="justify-content:center">03 — Telemetry</div>
      <div class="sec-title-xl" style="text-align:center"><span class="filled">NETWORK</span><span class="outline"> INTEL</span></div>
      <p style="color:var(--dim2);max-width:500px;margin:1rem auto 0;font-size:0.98rem">Real-time analysis of your active connection — demonstrating reconnaissance techniques used in live security assessments.</p>
    </div>
    <div class="intel-layout">
      <div class="rv d1">
        <p>Every security assessment begins here — mapping your digital footprint before a single exploit is staged. This is what attackers see before you even know they're watching.</p>
        <div class="intel-facts">
          <div class="if-row"><div class="if-ico"><svg viewBox="0 0 24 24"><path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"/><circle cx="12" cy="10" r="3"/></svg></div><div class="if-text"><span>Location</span><strong>Rajshahi Division, Bangladesh</strong></div></div>
          <div class="if-row"><div class="if-ico"><svg viewBox="0 0 24 24"><circle cx="12" cy="12" r="10"/><polyline points="12 6 12 12 16 14"/></svg></div><div class="if-text"><span>Availability</span><strong>24 / 7 Incident Support</strong></div></div>
          <div class="if-row"><div class="if-ico"><svg viewBox="0 0 24 24"><rect x="3" y="11" width="18" height="11" rx="2"/><path d="M7 11V7a5 5 0 0 1 10 0v4"/></svg></div><div class="if-text"><span>Encryption</span><strong>End-to-end · TLS 1.3 · AES-256</strong></div></div>
        </div>
        <div class="wave-wrap rv d2">
          <div class="wave-header"><span class="wh-l">Live Threat Activity</span><span class="wh-r"><span class="wave-blink"></span>Real-time Feed</span></div>
          <canvas id="waveCanvas" aria-hidden="true"></canvas>
        </div>
      </div>

      <!-- ════ TELEMETRY TERMINAL — NO SCROLL ════ -->
      <div class="intel-term rv d2">
        <div class="it-c1"></div><div class="it-c2"></div><div class="it-c3"></div><div class="it-c4"></div>
        <div class="scan-beam" aria-hidden="true"></div>
        <div class="scan-v" aria-hidden="true"></div>
        <div class="it-chrome">
          <div class="it-dots"><div class="it-dot itd1"></div><div class="it-dot itd2"></div><div class="it-dot itd3"></div></div>
          <span class="it-title">rh2sys_recon v5.0 — full telemetry scan</span>
          <div class="it-live"><span class="itl"></span>LIVE</div>
        </div>
        <div class="it-hud-row" aria-hidden="true">
          <div class="hud-seg"><span class="hud-blink"></span>ENC: <span class="hv">AES-256</span></div>
          <div class="hud-seg">PROTO: <span class="hv">TLS 1.3</span></div>
          <div class="hud-seg">MODE: <span class="hv">PASSIVE RECON</span></div>
          <div class="hud-seg">SIG: <span class="hv" id="scStat">INIT...</span></div>
        </div>
        <div class="it-prompt">
          <code>$ ./recon --full --passive --stealth --target=visitor</code>
        </div>

        <!-- DATA GRID — ALL VISIBLE, NO SCROLL -->
        <div class="it-body" id="itBody">
          <div class="it-grid">

            <!-- NETWORK IDENTITY -->
            <div class="it-cat"><div class="it-cat-label">Network Identity</div></div>
            <div class="ir"><span class="ik">IP Address</span><span class="iv loading" id="intel-ip">Scanning...</span></div>
            <div class="ir"><span class="ik">Country</span><span class="iv loading" id="intel-country">Resolving...</span></div>
            <div class="ir"><span class="ik">City / Region</span><span class="iv loading" id="intel-city">Resolving...</span></div>
            <div class="ir"><span class="ik">ISP / ASN</span><span class="iv loading" id="intel-isp">Querying...</span></div>
            <div class="ir"><span class="ik">IP Timezone</span><span class="iv loading" id="intel-timezone">Calculating...</span></div>
            <div class="ir"><span class="ik">Connection</span><span class="iv" id="intel-conn">Detecting...</span></div>
            <div class="ir"><span class="ik">Downlink</span><span class="iv" id="intel-dl">—</span></div>
            <div class="ir"><span class="ik">RTT Latency</span><span class="iv" id="intel-rtt">—</span></div>

            <!-- DEVICE INFORMATION -->
            <div class="it-cat"><div class="it-cat-label">Device Information</div></div>
            <div class="ir"><span class="ik">Browser</span><span class="iv" id="intel-browser">Detecting...</span></div>
            <div class="ir"><span class="ik">OS</span><span class="iv" id="intel-os">Detecting...</span></div>
            <div class="ir"><span class="ik">Device Type</span><span class="iv" id="intel-devtype">Detecting...</span></div>
            <div class="ir"><span class="ik">CPU Cores</span><span class="iv" id="intel-cpu">—</span></div>
            <div class="ir"><span class="ik">Device RAM</span><span class="iv" id="intel-ram">—</span></div>
            <div class="ir"><span class="ik">Data Saver</span><span class="iv" id="intel-datasaver">—</span></div>

            <!-- DISPLAY INFORMATION -->
            <div class="it-cat"><div class="it-cat-label">Display Information</div></div>
            <div class="ir"><span class="ik">Resolution</span><span class="iv" id="intel-screen">—</span></div>
            <div class="ir"><span class="ik">Viewport</span><span class="iv" id="intel-viewport">—</span></div>
            <div class="ir"><span class="ik">Pixel Ratio</span><span class="iv" id="intel-dpr">—</span></div>
            <div class="ir"><span class="ik">Color Depth</span><span class="iv" id="intel-color">—</span></div>

            <!-- GPU INFORMATION -->
            <div class="it-cat"><div class="it-cat-label">GPU Information</div></div>
            <div class="ir"><span class="ik">GPU Vendor</span><span class="iv" id="intel-gpu-vendor">Probing...</span></div>
            <div class="ir"><span class="ik">GPU Renderer</span><span class="iv" id="intel-gpu-renderer">Probing...</span></div>
            <div class="ir"><span class="ik">WebGL Ver.</span><span class="iv" id="intel-webgl">—</span></div>

            <!-- CLIENT SYSTEM -->
            <div class="it-cat"><div class="it-cat-label">Client System</div></div>
            <div class="ir"><span class="ik">Local Time</span><span class="iv live-clock" id="intel-localtime">—</span></div>
            <div class="ir"><span class="ik">TZ Offset</span><span class="iv" id="intel-tzoffset">—</span></div>
            <div class="ir"><span class="ik">Page Load</span><span class="iv" id="intel-loadtime">—</span></div>
            <div class="ir"><span class="ik">DNS Lookup</span><span class="iv" id="intel-dns">—</span></div>

            <!-- SESSION -->
            <div class="it-cat"><div class="it-cat-label">Session</div></div>
            <div class="ir"><span class="ik">Session ID</span><span class="iv session-id" id="intel-session">Generating...</span></div>
            <div class="ir"><span class="ik">Session Start</span><span class="iv" id="intel-sessstart">—</span></div>
            <div class="ir"><span class="ik">Load Duration</span><span class="iv" id="intel-loaddur">—</span></div>
            <div class="ir"><span class="ik">Visit Count</span><span class="iv" id="intel-visitnum">—</span></div>

          </div>
        </div>

        <div class="it-threat">
          <div class="it-tl-label">Exposure Risk Level <span id="threatPct">0%</span></div>
          <div class="tbar"><div class="tbar-fill" id="threatBar"></div></div>
        </div>
        <div class="it-foot"><span>RH²-SYS RECON ENGINE v5.0 · PASSIVE · ENCRYPTED</span><span id="iTs"></span></div>
      </div>
    </div>
  </div>
</section>

<!-- GLOBE -->
<section id="globeSection">
  <div class="W">
    <div class="rv">
      <div class="sec-eyebrow">04 — Global Intelligence</div>
      <div class="sec-title-xl"><span class="filled">LIVE THREAT</span><br><span class="outline">LANDSCAPE</span></div>
    </div>
    <div class="globe-layout" style="margin-top:3rem">
      <canvas id="globeCanvas" aria-label="3D Globe showing global threat data"></canvas>
      <div class="globe-info rv d2">
        <p style="color:var(--dim2);font-size:1rem;line-height:1.85;margin-bottom:1rem">Real-time visualization of global cyber threat activity. RH²-Systems monitors attack vectors across 140+ countries to keep our clients ahead of emerging threats.</p>
        <div class="globe-stats">
          <div class="gs"><span class="gs-label">Active Threats Monitored</span><div><span class="gs-val" data-count="14829">0</span><span class="gs-trend" style="margin-left:8px">↑ 3.2%</span></div></div>
          <div class="gs"><span class="gs-label">Countries Tracked</span><div><span class="gs-val" data-count="142">0</span><span class="gs-trend" style="margin-left:8px">Global</span></div></div>
          <div class="gs"><span class="gs-label">Attack Vectors / Day</span><div><span class="gs-val" data-count="4200">0</span><span class="gs-trend" style="margin-left:8px">↑ 1.8%</span></div></div>
          <div class="gs"><span class="gs-label">CVEs Tracked</span><div><span class="gs-val" data-count="1240">0</span><span class="gs-trend" style="margin-left:8px">Updated daily</span></div></div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="W">
    <div class="rv"><div class="sec-eyebrow">05 — Contact</div><div class="sec-title-xl"><span class="filled">SECURE</span><br><span class="outline">CONSULTATION</span></div></div>
    <div class="contact-grid">
      <div class="rv d1">
        <p>Ready to fortify your infrastructure? Reach out for a confidential discussion about your security posture and threat exposure.</p>
        <div class="c-details">
          <div class="cd"><div class="cd-ico"><svg viewBox="0 0 24 24"><path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"/><circle cx="12" cy="10" r="3"/></svg></div><div class="cd-t"><span>Location</span><strong>Rajshahi Division, Bangladesh</strong></div></div>
          <div class="cd"><div class="cd-ico"><svg viewBox="0 0 24 24"><circle cx="12" cy="12" r="10"/><polyline points="12 6 12 12 16 14"/></svg></div><div class="cd-t"><span>Availability</span><strong>24 / 7 Incident Support</strong></div></div>
          <div class="cd"><div class="cd-ico"><svg viewBox="0 0 24 24"><rect x="3" y="11" width="18" height="11" rx="2"/><path d="M7 11V7a5 5 0 0 1 10 0v4"/></svg></div><div class="cd-t"><span>Channels</span><strong>Encrypted comms available on request</strong></div></div>
        </div>
        <div class="c-note">All submissions are end-to-end encrypted via Firebase.</div>
      </div>
      <div class="c-form rv d2">
        <form id="cForm" novalidate>
          <div class="fg">
            <div class="fi"><label for="fn">Full Name / Organization</label><input type="text" id="fn" name="name" placeholder="Acme Corp / Jane Doe" required autocomplete="name"></div>
            <div class="fi"><label for="fe">Work Email</label><input type="email" id="fe" name="email" placeholder="security@company.com" required autocomplete="email"></div>
          </div>
          <div class="fi"><label for="fm">Project Scope / Details</label><textarea id="fm" name="message" rows="5" placeholder="Describe your infrastructure and security goals..." required></textarea></div>
          <button type="submit" class="fsub" id="submitBtn">TRANSMIT ENCRYPTED REQUEST</button>
        </form>
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="W">
    <div class="foot-grid">
      <div class="foot-brand">
        <div class="foot-logo">
          <svg class="logo-svg" style="height:44px" viewBox="0 0 200 42" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
            <path class="logo-path-rh" d="M6,34 L6,8 L18,8 Q28,8 28,18 Q28,28 18,28 L6,28 M18,28 L30,34" style="animation-delay:0.1s"/>
            <path class="logo-path-rh" d="M36,8 L36,34 M36,21 L50,21 M50,8 L50,34" style="animation-delay:1s"/>
            <path class="logo-path-sq" d="M55,6 Q55,2 59,2 Q63,2 63,5 Q63,8 55,11 L63,11" style="animation-delay:1.8s"/>
            <line x1="68" y1="10" x2="68" y2="34" stroke="rgba(240,246,255,0.2)" stroke-width="1" stroke-dasharray="24" stroke-dashoffset="24" style="animation:drawLogo 0.4s ease 2s forwards"/>
            <text class="logo-text-sys" x="74" y="29" style="animation-delay:2.1s">SYSTEMS</text>
            <circle class="logo-dot-svg" cx="194" cy="8" r="3.5"/>
          </svg>
        </div>
        <p>Enterprise-grade cybersecurity and offensive security operations for high-risk infrastructure worldwide. 100% confidentiality guaranteed.</p>
      </div>
      <div class="foot-col"><h5>Services</h5><ul><li><a href="#services">Penetration Testing</a></li><li><a href="#services">Red Team Operations</a></li><li><a href="#services">Secure Engineering</a></li></ul></div>
      <div class="foot-col"><h5>Company</h5><ul><li><a href="#team">Our Team</a></li><li><a href="#intelligence">Intel Scan</a></li><li><a href="#globeSection">Threat Globe</a></li><li><a href="#contact">Contact</a></li></ul></div>
    </div>
    <div class="foot-bottom">
      <div class="foot-copy">© 2026 RH²-SYSTEMS · ALL RIGHTS RESERVED · CONFIDENTIALITY GUARANTEED</div>
      <div class="foot-right">Rajshahi, Bangladesh · <span>Offensive Security</span></div>
    </div>
  </div>
</footer>

<script>
/* ── DEVICE PERFORMANCE DETECTION ── */
window._perf=(function(){const cores=navigator.hardwareConcurrency||2;const mem=navigator.deviceMemory||2;const mobile=/Android|iPhone|iPad/i.test(navigator.userAgent);const low=cores<=2||mem<=2||mobile;const mid=!low&&(cores<=4||mem<=4);return{low,mid,high:!low&&!mid};})();
if(window._perf.low){document.addEventListener('DOMContentLoaded',()=>{const m=document.getElementById('matrixCanvas');const s=document.getElementById('shaderCanvas');if(m)m.style.display='none';if(s)s.style.display='none';});}

/* ── BOOT PRELOADER ── */
(function(){
  const lines=[{t:'c-dim',s:'RH²-SYSTEMS SECURE BOOT SEQUENCE v4.2.1',d:0},{t:'c-dim',s:'Copyright (C) 2026 RH²-Systems. All rights reserved.',d:60},{t:'c-dim',s:'━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━',d:100},{t:'c-white',s:'CPU: RH2-X1 Secure Processor @ 4.8GHz [8 Cores Active]',d:180},{t:'c-white',s:'RAM: 65536MB ECC DDR5 — Integrity Check... PASSED',d:260},{t:'c-ok',s:'[ OK ] Memory encryption module loaded',d:360},{t:'c-ok',s:'[ OK ] Secure enclave initialized',d:440},{t:'c-ok',s:'[ OK ] TPM 2.0 attestation verified',d:520},{t:'c-warn',s:'[WARN] External network interfaces isolated',d:620},{t:'c-ok',s:'[ OK ] Firewall rules loaded — 2,847 entries active',d:700},{t:'c-dim',s:'Loading kernel modules...',d:800},{t:'c-ok',s:'[ OK ] rh2_exploit_engine.ko [ARMED]',d:900},{t:'c-ok',s:'[ OK ] rh2_recon_passive.ko [STANDBY]',d:980},{t:'c-ok',s:'[ OK ] rh2_redteam_core.ko [LOADED]',d:1060},{t:'c-warn',s:'[WARN] Zero-day payload buffer: 3 staged',d:1150},{t:'c-ok',s:'[ OK ] Cryptographic subsystem: AES-256-GCM active',d:1240},{t:'c-ok',s:'[ OK ] TLS 1.3 channel established',d:1320},{t:'c-dim',s:'━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━',d:1400},{t:'c-hi',s:'INITIALIZING RH²-SYSTEMS OFFENSIVE SECURITY PLATFORM',d:1480},{t:'c-fire',s:'All systems operational. Welcome, Operator.',d:1600}];
  const container=document.getElementById('bootLines');const cursor=document.getElementById('bootCursor');const pw=document.getElementById('bootPWrap');const fill=document.getElementById('bootFill');const pctEl=document.getElementById('bootPct');const timeEl=document.getElementById('bootTime');const pre=document.getElementById('pre');
  let bootSec=0;const clockIv=setInterval(()=>{bootSec++;const h=String(Math.floor(bootSec/3600)).padStart(2,'0');const m=String(Math.floor((bootSec%3600)/60)).padStart(2,'0');const s=String(bootSec%60).padStart(2,'0');if(timeEl)timeEl.textContent=h+':'+m+':'+s;},1000);
  lines.forEach(({t,s,d})=>{setTimeout(()=>{const el=document.createElement('div');el.className='boot-line '+t;el.textContent=s;container.appendChild(el);container.scrollTop=container.scrollHeight;},d);});
  setTimeout(()=>{if(pw)pw.style.display='block';let p=0;const pIv=setInterval(()=>{p+=Math.random()*4+1;if(p>=100){p=100;clearInterval(pIv);}if(fill)fill.style.width=Math.floor(p)+'%';if(pctEl)pctEl.textContent=Math.floor(p)+'%';},40);},1700);
  window.addEventListener('load',()=>{setTimeout(()=>{clearInterval(clockIv);if(cursor)cursor.style.display='none';pre.classList.add('out');document.documentElement.classList.add('booted');window.dispatchEvent(new Event('booted'));},2800);});
  setTimeout(()=>{clearInterval(clockIv);pre.classList.add('out');},4500);
})();

/* ── CURSOR ── */
(function(){
  if(window.matchMedia('(max-width:768px)').matches)return;
  const c=document.getElementById('cur');const dot=c.querySelector('.cur-d');const ring=c.querySelector('.cur-r');let mx=0,my=0,rx=0,ry=0;
  dot.style.cssText='position:fixed;pointer-events:none;left:0;top:0;will-change:transform';
  ring.style.cssText='position:fixed;pointer-events:none;left:0;top:0;will-change:transform';
  document.addEventListener('mousemove',e=>{mx=e.clientX;my=e.clientY},{passive:true});
  (function anim(){rx+=(mx-rx)*0.12;ry+=(my-ry)*0.12;dot.style.transform=`translate(${mx}px,${my}px)`;ring.style.transform=`translate(${rx}px,${ry}px)`;requestAnimationFrame(anim);})();
  document.querySelectorAll('a,button,.sc,.tc,.btn').forEach(el=>{el.addEventListener('mouseenter',()=>document.body.classList.add('hov'));el.addEventListener('mouseleave',()=>document.body.classList.remove('hov'));});
})();

/* ── HEADER & SCROLL TOP ── */
window.addEventListener('scroll',()=>{document.getElementById('hdr').classList.toggle('stuck',window.scrollY>10);document.getElementById('stt').classList.toggle('on',window.scrollY>500);});
document.getElementById('stt').addEventListener('click',()=>window.scrollTo({top:0,behavior:'smooth'}));

/* ── MOBILE NAV ── */
const hbtn=document.getElementById('hbtn');const mdr=document.getElementById('mdr');
hbtn.addEventListener('click',()=>{const on=mdr.classList.toggle('on');hbtn.classList.toggle('x',on);hbtn.setAttribute('aria-expanded',on);document.body.style.overflow=on?'hidden':'';});
document.querySelectorAll('.ml').forEach(a=>a.addEventListener('click',()=>{mdr.classList.remove('on');hbtn.classList.remove('x');hbtn.setAttribute('aria-expanded','false');document.body.style.overflow='';}));

/* ── TYPEWRITER ── */
(function(){const words=['ENGINEERED.','UNBREAKABLE.','ADVERSARIAL.','RELENTLESS.'];const el=document.getElementById('typeEl');let wi=0,ci=0,del=false;(function tick(){const w=words[wi];el.textContent=del?w.substring(0,--ci):w.substring(0,++ci);let d=del?20:60;if(!del&&ci===w.length){d=2000;del=true}if(del&&ci===0){del=false;wi=(wi+1)%words.length}setTimeout(tick,d);})();})();

/* ── UTC CLOCK ── */
(function(){function upd(){const t=new Date();document.getElementById('utcClock').textContent=[t.getUTCHours(),t.getUTCMinutes(),t.getUTCSeconds()].map(n=>String(n).padStart(2,'0')).join(':')+' UTC';}upd();setInterval(upd,1000);})();

/* ── TEXT SCRAMBLE ── */
class Scramble{constructor(el){this.el=el;this.orig=el.textContent;this.chars='!<>-_\\/[]{}—=+*^?#ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789';this.running=false;}run(){if(this.running)return;this.running=true;let iter=0;const total=this.orig.length;const iv=setInterval(()=>{this.el.textContent=this.orig.split('').map((ch,i)=>{if(ch===' ')return ' ';if(i<iter)return ch;return this.chars[Math.floor(Math.random()*this.chars.length)];}).join('');iter+=0.5;if(iter>=total){this.el.textContent=this.orig;this.running=false;clearInterval(iv);}},30);}}
(function(){const targets=document.querySelectorAll('.sec-title-xl .filled,.sec-title-xl .outline');const scramblers=new Map();targets.forEach(el=>scramblers.set(el,new Scramble(el)));const so=new IntersectionObserver(entries=>{entries.forEach(e=>{if(e.isIntersecting){const s=scramblers.get(e.target);if(s)setTimeout(()=>s.run(),100);}});},{threshold:0.5});targets.forEach(el=>so.observe(el));})();

/* ── 3D TILT CARDS ── */
(function(){if(window.matchMedia('(max-width:900px)').matches)return;let pending=false;document.querySelectorAll('.tc,.sc').forEach(card=>{let mx=0,my=0,rect=null;card.addEventListener('mouseenter',()=>{rect=card.getBoundingClientRect();});card.addEventListener('mousemove',e=>{mx=e.clientX;my=e.clientY;if(pending||!rect)return;pending=true;requestAnimationFrame(()=>{pending=false;if(!rect)return;const x=mx-rect.left,y=my-rect.top;const cx=rect.width/2,cy=rect.height/2;const rX=((y-cy)/cy)*-8;const rY=((x-cx)/cx)*8;card.style.transform=`perspective(900px) rotateX(${rX}deg) rotateY(${rY}deg) translateY(-4px)`;card.style.setProperty('--gx',Math.round((x/rect.width)*100)+'%');card.style.setProperty('--gy',Math.round((y/rect.height)*100)+'%');});},{passive:true});card.addEventListener('mouseleave',()=>{rect=null;card.style.transform='';});});})();

/* ── MAGNETIC BUTTONS ── */
(function(){if(window.matchMedia('(max-width:900px)').matches)return;document.querySelectorAll('.btn,.nl-cta').forEach(btn=>{let raf=false;btn.addEventListener('mousemove',e=>{if(raf)return;raf=true;requestAnimationFrame(()=>{raf=false;const r=btn.getBoundingClientRect();const x=(e.clientX-r.left-r.width/2)*0.2;const y=(e.clientY-r.top-r.height/2)*0.25;btn.style.transform=`translate(${x}px,${y}px)`;});},{passive:true});btn.addEventListener('mouseleave',()=>{btn.style.transition='transform 0.4s cubic-bezier(0.175,0.885,0.32,1.275)';btn.style.transform='';setTimeout(()=>btn.style.transition='',400);});});})();

/* ── WAVEFORM ── */
(function(){const canvas=document.getElementById('waveCanvas');if(!canvas)return;const ctx=canvas.getContext('2d');const DPR=Math.min(window.devicePixelRatio||1,2);let W,H,t=0;const waves=[{amp:22,freq:0.018,speed:0.032,color:'rgba(124,58,255,0.7)',width:2},{amp:14,freq:0.028,speed:0.048,color:'rgba(168,85,247,0.5)',width:1.5},{amp:8,freq:0.042,speed:0.065,color:'rgba(232,121,249,0.4)',width:1},{amp:18,freq:0.012,speed:0.022,color:'rgba(56,189,248,0.35)',width:1.5}];const spikes=Array.from({length:28},(_,i)=>({x:(i/27),h:Math.random()*0.6+0.1,hTarget:Math.random()*0.6+0.1,speed:Math.random()*0.04+0.01}));function resize(){W=canvas.offsetWidth;H=canvas.offsetHeight;canvas.width=W*DPR;canvas.height=H*DPR;canvas.style.width=W+'px';canvas.style.height=H+'px';ctx.scale(DPR,DPR);}function draw(){ctx.clearRect(0,0,W,H);t+=0.016;waves.forEach(w=>{ctx.beginPath();ctx.strokeStyle=w.color;ctx.lineWidth=w.width;ctx.shadowColor=w.color;ctx.shadowBlur=8;for(let x=0;x<=W;x+=2){const y=H/2+Math.sin(x*w.freq+t*w.speed*60)*w.amp+Math.sin(x*w.freq*2.1+t*w.speed*40)*(w.amp*0.3);x===0?ctx.moveTo(x,y):ctx.lineTo(x,y);}ctx.stroke();ctx.shadowBlur=0;});spikes.forEach(s=>{s.h+=(s.hTarget-s.h)*s.speed;if(Math.abs(s.h-s.hTarget)<0.01)s.hTarget=Math.random()*0.65+0.08;const bx=s.x*W;const bh=s.h*(H*0.38);const by=H-bh;const grad=ctx.createLinearGradient(0,by,0,H);grad.addColorStop(0,'rgba(124,58,255,0.9)');grad.addColorStop(0.5,'rgba(168,85,247,0.6)');grad.addColorStop(1,'rgba(124,58,255,0.1)');ctx.fillStyle=grad;ctx.shadowColor='rgba(124,58,255,0.6)';ctx.shadowBlur=6;ctx.fillRect(bx-2,by,4,bh);ctx.shadowBlur=0;});requestAnimationFrame(draw);}window.addEventListener('resize',resize);resize();draw();})();

/* ══════════════════════════════════════════
   FULL TELEMETRY ENGINE v5.0
   ══════════════════════════════════════════ */
(function(){
  const _sessionStart = new Date();
  let rowsDone = 0;

  function sv(id, val, cls) {
    const el = document.getElementById(id);
    if (!el) return;
    el.textContent = val || '—';
    el.classList.remove('loading');
    el.classList.add('loaded');
    if (cls) { cls.split(' ').forEach(c => c && el.classList.add(c)); }
    const row = el.closest('.ir');
    if (row) setTimeout(() => row.classList.add('lit'), 60);
    rowsDone++;
    const pct = Math.min(Math.round((rowsDone / 22) * 73), 73);
    const bar = document.getElementById('threatBar');
    const lbl = document.getElementById('threatPct');
    if (bar) { bar.style.width = pct + '%'; bar.classList.add('go'); }
    if (lbl) lbl.textContent = pct + '%';
  }

  // SESSION ID
  (function() {
    const hex = () => Math.floor(Math.random() * 65536).toString(16).toUpperCase().padStart(4,'0');
    sv('intel-session', 'RHX-' + hex() + '-' + hex(), 'session-id');
    sv('intel-sessstart', _sessionStart.toTimeString().split(' ')[0]);
  })();

  // VISIT COUNTER
  try {
    let v = parseInt(sessionStorage.getItem('rh2v') || '0') + 1;
    sessionStorage.setItem('rh2v', v);
    sv('intel-visitnum', v === 1 ? 'First this session' : 'Visit #' + v);
  } catch(e) { sv('intel-visitnum', 'Session active'); }

  // BROWSER
  const ua = navigator.userAgent;
  let br = 'Unknown', brVer = '';
  if (/SamsungBrowser\/([\\d.]+)/i.test(ua)) { br='Samsung Internet'; brVer=RegExp.$1; }
  else if (/OPR\/([\\d.]+)/i.test(ua)) { br='Opera'; brVer=RegExp.$1; }
  else if (/Trident/i.test(ua)) { br='Internet Explorer'; brVer='11'; }
  else if (/Edg\/([\\d.]+)/i.test(ua)) { br='Edge'; brVer=RegExp.$1; }
  else if (/Firefox\/([\\d.]+)/i.test(ua)) { br='Firefox'; brVer=RegExp.$1; }
  else if (/Chrome\/([\\d.]+)/i.test(ua)) { br='Chrome'; brVer=RegExp.$1; }
  else if (/Safari\/([\\d.]+)/i.test(ua)) { br='Safari'; brVer=RegExp.$1; }
  sv('intel-browser', brVer ? br + ' v' + brVer.split('.')[0] : br);

  // OS
  let os = 'Unknown';
  if (/Windows NT 10\\.0/i.test(ua)) os='Windows 10/11';
  else if (/Windows/i.test(ua)) os='Windows';
  else if (/Android ([\\d.]+)/i.test(ua)) os='Android '+((ua.match(/Android ([\\d.]+)/i)||[])[1]||'');
  else if (/iPhone OS ([\\d_]+)/i.test(ua)) os='iOS '+((ua.match(/iPhone OS ([\\d_]+)/i)||[])[1]||'').replace(/_/g,'.');
  else if (/iPad.*OS ([\\d_]+)/i.test(ua)) os='iPadOS '+((ua.match(/iPad.*OS ([\\d_]+)/i)||[])[1]||'').replace(/_/g,'.');
  else if (/Mac OS X ([\\d_]+)/i.test(ua)) os='macOS '+((ua.match(/Mac OS X ([\\d_]+)/i)||[])[1]||'').replace(/_/g,'.');
  else if (/CrOS/i.test(ua)) os='ChromeOS';
  else if (/Linux/i.test(ua)) os='Linux';
  sv('intel-os', os);

  // DEVICE TYPE
  let devType = 'Desktop';
  if (/iPad/i.test(ua)||(navigator.maxTouchPoints>1&&/Mac/i.test(ua))) devType='Tablet';
  else if (/Android/i.test(ua)&&screen.width>=768) devType='Tablet (Android)';
  else if (/Android/i.test(ua)) devType='Mobile (Android)';
  else if (/iPhone|iPod/i.test(ua)) devType='Mobile (iOS)';
  else if (/Mobi/i.test(ua)) devType='Mobile';
  sv('intel-devtype', devType, devType.includes('Mobile')?'warn-val':'ok-val');

  // CPU & RAM
  sv('intel-cpu', navigator.hardwareConcurrency ? navigator.hardwareConcurrency + ' logical cores' : 'Not exposed');
  sv('intel-ram', navigator.deviceMemory ? navigator.deviceMemory + ' GB (approx)' : 'Not exposed');

  // DISPLAY
  sv('intel-screen', screen.width + '×' + screen.height + ' px');
  sv('intel-viewport', window.innerWidth + '×' + window.innerHeight + ' px');
  sv('intel-dpr', (window.devicePixelRatio||1) + 'x');
  sv('intel-color', (screen.colorDepth||screen.pixelDepth||24) + '-bit');

  // NETWORK INFO API
  const conn = navigator.connection || navigator.mozConnection || navigator.webkitConnection;
  if (conn) {
    sv('intel-conn', conn.effectiveType ? conn.effectiveType.toUpperCase() + (conn.type ? ' / ' + conn.type : '') : conn.type || 'Unknown');
    sv('intel-dl', conn.downlink != null ? conn.downlink + ' Mbps' : '—');
    sv('intel-rtt', conn.rtt != null ? conn.rtt + ' ms' : '—', conn.rtt < 100 ? 'ok-val' : 'warn-val');
    sv('intel-datasaver', conn.saveData ? 'ENABLED ⚠' : 'Disabled', conn.saveData ? 'warn-val' : 'ok-val');
    conn.addEventListener('change', () => {
      sv('intel-conn', conn.effectiveType ? conn.effectiveType.toUpperCase() : conn.type || '—');
      sv('intel-dl', conn.downlink != null ? conn.downlink + ' Mbps' : '—');
      sv('intel-rtt', conn.rtt != null ? conn.rtt + ' ms' : '—');
    });
  } else {
    sv('intel-conn', 'API unavailable'); sv('intel-dl', 'N/A'); sv('intel-rtt', 'N/A'); sv('intel-datasaver', 'N/A');
  }

  // GPU
  (function(){
    try {
      const c = document.createElement('canvas');
      const gl = c.getContext('webgl2') || c.getContext('webgl') || c.getContext('experimental-webgl');
      if (!gl) { sv('intel-gpu-vendor','WebGL unavailable'); sv('intel-gpu-renderer','—'); sv('intel-webgl','—'); return; }
      const dbg = gl.getExtension('WEBGL_debug_renderer_info');
      if (dbg) {
        let vendor = gl.getParameter(dbg.UNMASKED_VENDOR_WEBGL) || 'Unknown';
        let renderer = gl.getParameter(dbg.UNMASKED_RENDERER_WEBGL) || 'Unknown';
        sv('intel-gpu-vendor', vendor.length > 28 ? vendor.substring(0,28)+'…' : vendor);
        sv('intel-gpu-renderer', renderer.length > 26 ? renderer.substring(0,26)+'…' : renderer);
      } else {
        sv('intel-gpu-vendor', gl.getParameter(gl.VENDOR) || 'Masked by browser');
        sv('intel-gpu-renderer', gl.getParameter(gl.RENDERER) || 'Masked');
      }
      sv('intel-webgl', c.getContext('webgl2') ? 'WebGL 2.0' : 'WebGL 1.0', 'ok-val');
    } catch(e) { sv('intel-gpu-vendor','Detection failed'); sv('intel-gpu-renderer','—'); sv('intel-webgl','—'); }
  })();

  // TIMEZONE OFFSET
  const off = -(new Date().getTimezoneOffset());
  const offH = Math.floor(Math.abs(off)/60), offM = Math.abs(off)%60;
  sv('intel-tzoffset', 'UTC' + (off>=0?'+':'-') + offH + (offM?':'+String(offM).padStart(2,'0'):''));

  // LOCAL CLOCK — live updating
  function updateClock() {
    const n = new Date();
    const time = [n.getHours(),n.getMinutes(),n.getSeconds()].map(v=>String(v).padStart(2,'0')).join(':');
    const date = n.toLocaleDateString('en-GB',{day:'2-digit',month:'short'});
    const el = document.getElementById('intel-localtime');
    if (el) { el.textContent = date + ' · ' + time; el.classList.remove('loading'); el.classList.add('loaded','live-clock'); }
  }
  updateClock();
  setInterval(updateClock, 1000);

  // PAGE PERFORMANCE
  function reportPerf() {
    try {
      const nav = performance.getEntriesByType('navigation')[0];
      if (nav) {
        const load = Math.round(nav.loadEventEnd - nav.startTime);
        const dns  = Math.round(nav.domainLookupEnd - nav.domainLookupStart);
        sv('intel-loadtime', load > 0 ? load + ' ms' : '< 1 ms', load < 2000 ? 'ok-val' : 'warn-val');
        sv('intel-dns', dns > 0 ? dns + ' ms' : '< 1 ms', dns < 100 ? 'ok-val' : 'warn-val');
        sv('intel-loaddur', load > 0 ? load + ' ms' : '—');
      } else {
        const approx = Math.round(performance.now());
        sv('intel-loadtime', approx + ' ms (approx)');
        sv('intel-dns', 'Not available');
        sv('intel-loaddur', approx + ' ms');
      }
    } catch(e) { sv('intel-loadtime','—'); sv('intel-dns','—'); sv('intel-loaddur','—'); }
  }
  if (document.readyState === 'complete') reportPerf();
  else window.addEventListener('load', () => setTimeout(reportPerf, 300));

  // FOOTER TIMESTAMP
  const ts = document.getElementById('iTs');
  if (ts) ts.textContent = new Date().toISOString().replace('T',' ').split('.')[0] + ' UTC';

  // IP / NETWORK API FALLBACK CHAIN
  const APIS = [
    {url:'https://ipapi.co/json/',ok:d=>d&&!d.error&&d.ip&&d.country_name,parse:d=>({ip:d.ip,country:(d.country_name||'')+(d.country_code?' ('+d.country_code+')':''),city:(d.city||'—')+', '+(d.region||'—'),isp:d.org||d.asn||'—',tz:d.timezone||'—'})},
    {url:'https://ipwho.is/',ok:d=>d&&d.success&&d.ip,parse:d=>({ip:d.ip,country:(d.country||'')+(d.country_code?' ('+d.country_code+')':''),city:(d.city||'—')+', '+(d.region||'—'),isp:(d.connection&&(d.connection.isp||d.connection.org))||'—',tz:(d.timezone&&d.timezone.id)||'—'})},
    {url:'https://freeipapi.com/api/json',ok:d=>d&&d.ipAddress,parse:d=>({ip:d.ipAddress,country:(d.countryName||'')+(d.countryCode?' ('+d.countryCode+')':''),city:(d.cityName||'—')+', '+(d.regionName||'—'),isp:d.isp||d.asn||'—',tz:d.timeZone||'—'})},
    {url:'https://ipinfo.io/json',ok:d=>d&&d.ip,parse:d=>({ip:d.ip,country:d.country||'—',city:(d.city||'—')+', '+(d.region||'—'),isp:d.org||'—',tz:d.timezone||'—'})},
    {url:'https://api64.ipify.org?format=json',ok:d=>d&&d.ip,parse:d=>({ip:d.ip,country:'—',city:'—',isp:'—',tz:'—'})}
  ];
  const filled = {ip:false,country:false,city:false,isp:false,tz:false};
  async function tryApis() {
    for (let i = 0; i < APIS.length; i++) {
      if (filled.ip&&filled.country&&filled.city&&filled.isp&&filled.tz) break;
      try {
        const api = APIS[i];
        const ctrl = new AbortController();
        const timer = setTimeout(() => ctrl.abort(), 6000);
        const r = await fetch(api.url, {signal:ctrl.signal, cache:'no-store'});
        clearTimeout(timer);
        if (!r||!r.ok) continue;
        const d = await r.json();
        if (!api.ok(d)) continue;
        const p = api.parse(d);
        if (!filled.ip && p.ip) { sv('intel-ip', p.ip, 'hi'); filled.ip=true; }
        if (!filled.country && p.country && p.country!=='—') { sv('intel-country', p.country); filled.country=true; }
        if (!filled.city && p.city && p.city!=='—') { sv('intel-city', p.city); filled.city=true; }
        if (!filled.isp && p.isp && p.isp!=='—') { sv('intel-isp', p.isp); filled.isp=true; }
        if (!filled.tz && p.tz && p.tz!=='—') { sv('intel-timezone', p.tz); filled.tz=true; }
      } catch(e) { continue; }
    }
    if (!filled.ip) sv('intel-ip','Unavailable');
    if (!filled.country) sv('intel-country','Unavailable');
    if (!filled.city) sv('intel-city','Unavailable');
    if (!filled.isp) sv('intel-isp','Unavailable');
    if (!filled.tz) sv('intel-timezone','Unavailable');
    const s = document.getElementById('scStat');
    if (s) { s.textContent = filled.ip&&filled.country ? 'COMPLETE' : 'PARTIAL'; s.classList.add(filled.ip&&filled.country?'ok':'warn'); }
  }
  tryApis();
})();

/* ── MATRIX RAIN ── */
(function(){const cv=document.getElementById('matrixCanvas');if(!cv)return;const ctx=cv.getContext('2d');const chars='ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789@#$%アイウエオカキクケコ';let W,H,cols,drops=[],running=true,lastDraw=0;const FPS=24,FRAME=1000/FPS;function resize(){W=cv.offsetWidth;H=cv.offsetHeight;cv.width=W;cv.height=H;cols=Math.floor(W/18);drops=Array.from({length:cols},()=>Math.random()*-80);}function draw(ts){if(!running){requestAnimationFrame(draw);return;}if(ts-lastDraw<FRAME){requestAnimationFrame(draw);return;}lastDraw=ts;ctx.fillStyle='rgba(3,6,10,0.1)';ctx.fillRect(0,0,W,H);ctx.font='12px monospace';drops.forEach((y,i)=>{const ch=chars[Math.floor(Math.random()*chars.length)];const x=i*18;ctx.fillStyle=i%4===0?'rgba(168,85,247,0.9)':'rgba(124,58,255,0.35)';ctx.fillText(ch,x,y*18);if(y*18>H&&Math.random()>0.975)drops[i]=0;drops[i]+=0.6;});requestAnimationFrame(draw);}const obs=new IntersectionObserver(e=>{running=e[0].isIntersecting;},{threshold:0.01});obs.observe(cv.parentElement||cv);window.addEventListener('resize',resize);resize();requestAnimationFrame(draw);})();

/* ── WEBGL THREE.JS 3D OBJECT ── */
(function(){if(!window.THREE)return;const cv=document.getElementById('webglCanvas');if(!cv)return;const renderer=new THREE.WebGLRenderer({canvas:cv,alpha:true,antialias:true});renderer.setPixelRatio(Math.min(window.devicePixelRatio,2));renderer.setClearColor(0x000000,0);const scene=new THREE.Scene();const camera=new THREE.PerspectiveCamera(60,1,0.1,1000);camera.position.z=4.5;function resize(){const W=cv.offsetWidth,H=cv.offsetHeight;renderer.setSize(W,H,false);camera.aspect=W/H;camera.updateProjectionMatrix();}
const icoGeo=new THREE.IcosahedronGeometry(1.8,1);const icoMat=new THREE.MeshBasicMaterial({color:0x7c3aff,wireframe:true,transparent:true,opacity:0.25});const ico=new THREE.Mesh(icoGeo,icoMat);scene.add(ico);
const innerGeo=new THREE.IcosahedronGeometry(1.1,0);const innerMat=new THREE.MeshPhongMaterial({color:0x3b0764,emissive:0x7c3aff,emissiveIntensity:0.3,transparent:true,opacity:0.7,shininess:100});const inner=new THREE.Mesh(innerGeo,innerMat);scene.add(inner);
const ring1=new THREE.Mesh(new THREE.TorusGeometry(2.4,0.008,6,50),new THREE.MeshBasicMaterial({color:0xa855f7,transparent:true,opacity:0.5}));ring1.rotation.x=Math.PI/3;scene.add(ring1);
const ring2=new THREE.Mesh(new THREE.TorusGeometry(2.8,0.005,6,50),new THREE.MeshBasicMaterial({color:0xe879f9,transparent:true,opacity:0.3}));ring2.rotation.x=Math.PI/5;ring2.rotation.z=Math.PI/4;scene.add(ring2);
const pGeo=new THREE.BufferGeometry();const pCount=120;const pPos=new Float32Array(pCount*3);for(let i=0;i<pCount*3;i++)pPos[i]=(Math.random()-0.5)*7;pGeo.setAttribute('position',new THREE.BufferAttribute(pPos,3));const particles=new THREE.Points(pGeo,new THREE.PointsMaterial({color:0x7c3aff,size:0.04,transparent:true,opacity:0.7}));scene.add(particles);
scene.add(new THREE.AmbientLight(0x7c3aff,0.4));const pLight=new THREE.PointLight(0xa855f7,2,10);pLight.position.set(3,3,3);scene.add(pLight);const pLight2=new THREE.PointLight(0xe879f9,1.5,10);pLight2.position.set(-3,-2,2);scene.add(pLight2);
let mx=0,my=0;document.addEventListener('mousemove',e=>{mx=(e.clientX/window.innerWidth-0.5)*2;my=(e.clientY/window.innerHeight-0.5)*2;});
let t=0,globeVisible=false;new IntersectionObserver(e=>{globeVisible=e[0].isIntersecting;},{threshold:0.01}).observe(cv);
function animate(){requestAnimationFrame(animate);if(!globeVisible)return;t+=0.008;ico.rotation.y+=0.004;ico.rotation.x+=0.002;inner.rotation.y-=0.006;inner.rotation.z+=0.003;ring1.rotation.z+=0.006;ring2.rotation.y+=0.004;particles.rotation.y+=0.001;scene.rotation.y+=(mx*0.3-scene.rotation.y)*0.05;scene.rotation.x+=(-my*0.2-scene.rotation.x)*0.05;innerMat.emissiveIntensity=0.2+Math.sin(t*2)*0.15;pLight.intensity=1.5+Math.sin(t*3)*0.8;renderer.render(scene,camera);}
window.addEventListener('resize',resize);resize();animate();cv.style.right='0';cv.style.left='auto';cv.style.width='55%';})();

/* ── SCROLL-DRIVEN WIPES ── */
(function(){const wipes=document.querySelectorAll('.rv.wipe');const wo=new IntersectionObserver(entries=>{entries.forEach(e=>{if(e.isIntersecting)e.target.classList.add('in');});},{threshold:0.08});wipes.forEach(el=>wo.observe(el));})();

/* ── CLICK RIPPLE ── */
(function(){document.addEventListener('click',e=>{if(e.target.closest('a,button,input,textarea'))return;const size=Math.max(window.innerWidth,window.innerHeight)*0.5;const r=document.createElement('div');r.className='ripple';r.style.cssText=`left:${e.clientX}px;top:${e.clientY}px;width:${size}px;height:${size}px`;document.body.appendChild(r);const r2=document.createElement('div');r2.className='ripple2';r2.style.cssText=`left:${e.clientX}px;top:${e.clientY}px;width:${size*1.5}px;height:${size*1.5}px`;document.body.appendChild(r2);setTimeout(()=>{r.remove();r2.remove();},1300);});})();

/* ── 3D GLOBE ── */
(function(){if(!window.THREE)return;const cv=document.getElementById('globeCanvas');if(!cv)return;const renderer=new THREE.WebGLRenderer({canvas:cv,alpha:true,antialias:true});renderer.setPixelRatio(Math.min(window.devicePixelRatio,2));renderer.setClearColor(0x000000,0);const scene=new THREE.Scene();const W=cv.offsetWidth,H=cv.offsetHeight||480;renderer.setSize(W,H,false);const camera=new THREE.PerspectiveCamera(45,W/H,0.1,1000);camera.position.z=3.2;
const globe=new THREE.Mesh(new THREE.SphereGeometry(1,32,32),new THREE.MeshPhongMaterial({color:0x06030f,emissive:0x0d0526,transparent:true,opacity:0.95,shininess:30}));scene.add(globe);
scene.add(new THREE.Mesh(new THREE.SphereGeometry(1.005,18,18),new THREE.MeshBasicMaterial({color:0x7c3aff,wireframe:true,transparent:true,opacity:0.12})));
scene.add(new THREE.Mesh(new THREE.SphereGeometry(1.12,18,18),new THREE.MeshBasicMaterial({color:0x7c3aff,transparent:true,opacity:0.07,side:THREE.BackSide})));
function ll2v(lat,lng,r=1){const phi=(90-lat)*Math.PI/180;const theta=(lng+180)*Math.PI/180;return new THREE.Vector3(-r*Math.sin(phi)*Math.cos(theta),r*Math.cos(phi),r*Math.sin(phi)*Math.sin(theta));}
const cities=[[40.7,-74],[51.5,-0.1],[35.6,139.7],[48.8,2.35],[55.7,37.6],[-33.8,151.2],[1.3,103.8],[19.0,72.8],[24.7,46.7],[31.2,121.5],[23.7,90.4],[6.5,3.4],[-23.5,-46.6],[37.5,127],[-34.6,-58.4]];
cities.forEach(([lat,lng])=>{const v=ll2v(lat,lng,1.01);const dot=new THREE.Mesh(new THREE.SphereGeometry(0.012,8,8),new THREE.MeshBasicMaterial({color:0xa855f7}));dot.position.copy(v);scene.add(dot);const ring=new THREE.Mesh(new THREE.RingGeometry(0.018,0.024,16),new THREE.MeshBasicMaterial({color:0x7c3aff,transparent:true,opacity:0.6,side:THREE.DoubleSide}));ring.position.copy(v);ring.lookAt(new THREE.Vector3(0,0,0));scene.add(ring);});
const attacks=[[0,4],[1,7],[2,0],[3,8],[4,2],[5,1],[6,3],[7,9],[8,5],[9,6],[10,0],[11,2],[0,12],[13,1],[14,3]];
const arcMeshes=[];attacks.forEach(([a,b],i)=>{const start=ll2v(...cities[a],1.01);const end=ll2v(...cities[b],1.01);const mid=start.clone().add(end).multiplyScalar(0.5).normalize().multiplyScalar(1.5);const curve=new THREE.QuadraticBezierCurve3(start,mid,end);const geo=new THREE.BufferGeometry().setFromPoints(curve.getPoints(60));const col=i%3===0?0xe879f9:i%3===1?0x7c3aff:0xa855f7;const mat=new THREE.LineBasicMaterial({color:col,transparent:true,opacity:0});const line=new THREE.Line(geo,mat);scene.add(line);arcMeshes.push({line,mat,prog:Math.random(),speed:0.004+Math.random()*0.006,delay:i*0.4});});
scene.add(new THREE.AmbientLight(0x7c3aff,0.5));const pl=new THREE.PointLight(0xa855f7,2,8);pl.position.set(2,2,2);scene.add(pl);const pl2=new THREE.PointLight(0xe879f9,1,8);pl2.position.set(-2,-1,1);scene.add(pl2);
let t=0,drag=false,lastX=0,rotY=0;cv.addEventListener('mousedown',e=>{drag=true;lastX=e.clientX});window.addEventListener('mouseup',()=>drag=false);window.addEventListener('mousemove',e=>{if(drag){rotY+=(e.clientX-lastX)*0.006;lastX=e.clientX}});
function animate(){requestAnimationFrame(animate);t+=0.008;globe.rotation.y+=drag?0:0.002;if(rotY!==0){globe.rotation.y+=rotY*0.1;rotY*=0.85;}pl.intensity=1.5+Math.sin(t*2)*0.7;arcMeshes.forEach((a,i)=>{if(t<a.delay)return;a.prog+=a.speed;if(a.prog>1.6){a.prog=0;a.speed=0.004+Math.random()*0.006;}const opacity=a.prog<0.1?a.prog/0.1:a.prog>1.4?(1.6-a.prog)/0.2:1;a.mat.opacity=Math.max(0,Math.min(0.75,opacity));});renderer.render(scene,camera);}
animate();
const statEls=document.querySelectorAll('.gs-val[data-count]');const cio=new IntersectionObserver(entries=>{entries.forEach(e=>{if(!e.isIntersecting)return;const el=e.target;const target=parseInt(el.dataset.count);let cur=0;const step=target/80;const iv=setInterval(()=>{cur+=step;if(cur>=target){cur=target;clearInterval(iv);}el.textContent=Math.floor(cur).toLocaleString();},20);cio.unobserve(el);});},{threshold:0.5});statEls.forEach(el=>cio.observe(el));
window.addEventListener('resize',()=>{const W2=cv.offsetWidth,H2=cv.offsetHeight||480;renderer.setSize(W2,H2,false);camera.aspect=W2/H2;camera.updateProjectionMatrix();});})();

/* ── FILM-REEL DRAG ── */
(function(){const reel=document.getElementById('svcReel');if(!reel)return;let isDown=false,startX,scrollLeft;reel.addEventListener('mousedown',e=>{isDown=true;reel.style.cursor='grabbing';startX=e.pageX-reel.offsetLeft;scrollLeft=reel.scrollLeft;});window.addEventListener('mouseup',()=>{isDown=false;if(reel)reel.style.cursor='grab';});reel.addEventListener('mousemove',e=>{if(!isDown)return;e.preventDefault();const x=e.pageX-reel.offsetLeft;reel.scrollLeft=scrollLeft-(x-startX)*1.4;});let tx=0;reel.addEventListener('touchstart',e=>{tx=e.touches[0].pageX;scrollLeft=reel.scrollLeft;},{passive:true});reel.addEventListener('touchmove',e=>{const dx=tx-e.touches[0].pageX;reel.scrollLeft=scrollLeft+dx;},{passive:true});})();

/* ── GLSL PLASMA SHADER ── */
(function(){const hero=document.querySelector('.hero');if(!hero)return;const cv=document.createElement('canvas');cv.id='shaderCanvas';cv.style.cssText='position:absolute;inset:0;width:100%;height:100%;z-index:0;opacity:0.35;pointer-events:none;mix-blend-mode:screen';hero.insertBefore(cv,hero.firstChild);const gl=cv.getContext('webgl')||cv.getContext('experimental-webgl');if(!gl)return;const vert=`attribute vec2 a;void main(){gl_Position=vec4(a,0,1);}`;const frag=`precision mediump float;uniform float u_t;uniform vec2 u_r;uniform vec2 u_m;void main(){vec2 uv=gl_FragCoord.xy/u_r;vec2 p=uv*2.0-1.0;p.x*=u_r.x/u_r.y;float t=u_t*0.4;float v=0.0;v+=sin(p.x*3.0+t)*0.5;v+=sin(p.y*2.5-t*0.8)*0.5;v+=sin((p.x+p.y)*2.0+t*1.2)*0.4;v+=sin(length(p-u_m)*6.0-t*2.0)*0.3;v+=sin(p.x*4.0-p.y*3.0+t*0.6)*0.3;float r=0.5+0.5*sin(v*3.14159+0.0);float g=0.5+0.5*sin(v*3.14159+2.094);float b=0.5+0.5*sin(v*3.14159+4.189);vec3 col=vec3(r*0.5+0.1,g*0.1,b*0.5+0.3);col=mix(col,vec3(0.48,0.23,1.0),0.4);gl_FragColor=vec4(col,0.9);}`;
function shader(type,src){const s=gl.createShader(type);gl.shaderSource(s,src);gl.compileShader(s);return s;}
const prog=gl.createProgram();gl.attachShader(prog,shader(gl.VERTEX_SHADER,vert));gl.attachShader(prog,shader(gl.FRAGMENT_SHADER,frag));gl.linkProgram(prog);gl.useProgram(prog);
const buf=gl.createBuffer();gl.bindBuffer(gl.ARRAY_BUFFER,buf);gl.bufferData(gl.ARRAY_BUFFER,new Float32Array([-1,-1,1,-1,-1,1,1,1]),gl.STATIC_DRAW);const aLoc=gl.getAttribLocation(prog,'a');gl.enableVertexAttribArray(aLoc);gl.vertexAttribPointer(aLoc,2,gl.FLOAT,false,0,0);
const uT=gl.getUniformLocation(prog,'u_t');const uR=gl.getUniformLocation(prog,'u_r');const uM=gl.getUniformLocation(prog,'u_m');let W,H,mx=0.5,my=0.5;
function resize(){W=Math.floor(cv.offsetWidth*0.5);H=Math.floor(cv.offsetHeight*0.5);cv.width=W;cv.height=H;cv.style.imageRendering='pixelated';gl.viewport(0,0,W,H);}
window.addEventListener('resize',resize);resize();document.addEventListener('mousemove',e=>{mx=e.clientX/window.innerWidth;my=1-e.clientY/window.innerHeight;});
let t=0,shaderVisible=true;new IntersectionObserver(e=>{shaderVisible=e[0].isIntersecting;},{threshold:0.01}).observe(hero);
function draw(){requestAnimationFrame(draw);if(!shaderVisible)return;t+=0.016;gl.uniform1f(uT,t);gl.uniform2f(uR,W,H);gl.uniform2f(uM,mx,my);gl.drawArrays(gl.TRIANGLE_STRIP,0,4);}draw();})();

/* ── AI CHATBOT ── */
(function(){
  const btn=document.getElementById('chatBtn');const box=document.getElementById('chatBox');const closeBtn=document.getElementById('chatClose');const msgs=document.getElementById('chatMsgs');const inp=document.getElementById('chatInp');const send=document.getElementById('chatSend');const tokenFill=document.getElementById('chatTokenFill');if(!btn||!box)return;
  let currentMode='general';let msgCount=0;
  btn.addEventListener('click',()=>{const on=box.classList.toggle('on');btn.classList.toggle('open',on);if(on)setTimeout(()=>inp.focus(),400);});
  if(closeBtn)closeBtn.addEventListener('click',()=>{box.classList.remove('on');btn.classList.remove('open');});
  document.querySelectorAll('.cm').forEach(cm=>{cm.addEventListener('click',()=>{document.querySelectorAll('.cm').forEach(c=>c.classList.remove('active'));cm.classList.add('active');currentMode=cm.dataset.mode;addMsg(`Mode: ${cm.textContent}. How can I help?`,'bot');updateSuggestions(currentMode);});});
  function updateSuggestions(mode){const sugg=document.getElementById('chatSugg');if(!sugg)return;const qs={general:['What is Red Teaming?','How does PenTesting work?','How much does it cost?','Who are your operators?'],pentest:['What vulnerabilities do you find?','How long does a pentest take?','Do you test APIs?','What report do I get?'],redteam:['What is APT simulation?','How do you test defenses?','What is MITRE ATT&CK?','Do you test phishing?'],quote:['Scope a web app test','I need compliance testing','Quote for small startup','Enterprise security audit']};sugg.innerHTML=(qs[mode]||qs.general).map(q=>`<button class="cs">${q}</button>`).join('');sugg.querySelectorAll('.cs').forEach(b=>b.addEventListener('click',()=>{inp.value=b.textContent;submit();}));}
  document.querySelectorAll('.cs').forEach(b=>b.addEventListener('click',()=>{inp.value=b.textContent;submit();}));
  function addMsg(text,role){if(role==='user'){const s=document.getElementById('chatSugg');if(s)s.style.display='none';}const el=document.createElement('div');el.className='msg '+role;el.innerHTML=text.replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;').replace(/\*\*(.*?)\*\*/g,'<strong>$1</strong>').replace(/`([^`]+)`/g,'<code style="background:rgba(124,58,255,0.15);padding:1px 5px;border-radius:3px;font-family:var(--ff-m);font-size:0.8em">$1</code>').replace(/\n/g,'<br>');msgs.appendChild(el);msgs.scrollTop=msgs.scrollHeight;msgCount++;if(tokenFill)tokenFill.style.width=Math.min(msgCount*8,100)+'%';return el;}
  function addTyping(){const el=document.createElement('div');el.className='chat-typing';el.id='chatTyping';el.innerHTML='<span></span><span></span><span></span>';msgs.appendChild(el);msgs.scrollTop=msgs.scrollHeight;return el;}
  const KB={greet:["Hello, Operator. RH²-Systems is an elite offensive security firm based in Rajshahi Division, Bangladesh. Founded by **Raj Hridoy** and **Riyad Hasan**. How can I assist you today?"],pentest:["Our **Penetration Testing** service covers Web Applications, Mobile Apps, APIs, Cloud Infrastructure, and Network systems. We follow OWASP Top 10, PTES, and NIST frameworks. Every engagement ends with a detailed vulnerability report and remediation guide.","We conduct **manual + automated penetration tests**. Our team identifies business logic flaws, auth bypasses, injection vectors, and misconfigurations that automated tools miss. We've completed **150+ engagements** with zero client breaches."],redteam:["Our **Red Team Operations** simulate real nation-state APT attacks. We replicate the full kill chain — initial access, lateral movement, privilege escalation, persistence, and data exfiltration.","Red teaming tests your **people, processes, and technology** simultaneously. Our operators use custom tooling, living-off-the-land techniques, and social engineering to find gaps your blue team hasn't considered."],secure:["Our **Secure Engineering** service embeds security into your development lifecycle. We do DevSecOps integration, Zero Trust architecture design, source code review, and CI/CD pipeline hardening."],team:["RH²-Systems was founded by two elite operators:\n\n**Raj Hridoy** — Cybersecurity Engineer specializing in secure architecture, cloud security, and DevSecOps.\n\n**Riyad Hasan** — Ethical Hacker focused on penetration testing, network forensics, and exploit development."],cost:["Engagement pricing depends on scope, duration, and complexity. **Contact us directly** for a confidential quote — use the contact form and describe your infrastructure and goals."],stats:["RH²-Systems track record: **150+ security engagements** completed, **100% client confidentiality** maintained, **24/7 incident support** available, **zero client breaches** post-engagement."],contact:["You can reach RH²-Systems through the **secure contact form** on this page. All submissions are end-to-end encrypted via Firebase. We respond within 24 hours."],location:["RH²-Systems is headquartered in **Rajshahi Division, Bangladesh**. We operate globally."],methodology:["Our methodology: **Reconnaissance → Threat Modeling → Exploitation → Post-Exploitation → Reporting → Remediation Verification**. Every phase is documented."],report:["Every engagement produces a **comprehensive report** including: executive summary, technical findings with CVSS scores, proof-of-concept evidence, and remediation recommendations."],compliance:["We help organizations prepare for **ISO 27001, PCI-DSS, SOC 2, GDPR, and HIPAA** compliance through security assessments, gap analysis, and remediation support."],fallback:["That's a great question. For detailed information, reach out via our **contact form** — our operators will give you a precise, tailored answer.","For the most accurate information, contact our team directly. Use the **secure contact form** on this page — all inquiries are treated with full confidentiality."]};
  function match(q){const t=q.toLowerCase();if(/hello|hi|hey|greet|start|who are you/i.test(t))return'greet';if(/pentest|penetrat|web test|api test|vuln|scan|owasp|injection|xss|sql/i.test(t))return'pentest';if(/red.?team|apt|adversar|attack sim|mitre|kill.?chain|nation.?state/i.test(t))return'redteam';if(/secure.?eng|devsecops|code review|zero.?trust|cicd/i.test(t))return'secure';if(/team|founder|raj|riyad|who built|operator|staff/i.test(t))return'team';if(/cost|price|how much|fee|rate|budget/i.test(t))return'cost';if(/stat|number|how many|engag|breach|track.?record/i.test(t))return'stats';if(/contact|reach|email|phone|touch|hire|book/i.test(t))return'contact';if(/location|where|bangladesh|rajshahi|based/i.test(t))return'location';if(/method|process|approach|how do you work/i.test(t))return'methodology';if(/report|deliverable|document|findings/i.test(t))return'report';if(/complian|iso|pci|soc2|gdpr|hipaa/i.test(t))return'compliance';if(/service|what do you do|offer|capabilit/i.test(t))return'pentest';return'fallback';}
  const used={};function getReply(key){const arr=KB[key]||KB.fallback;if(!used[key])used[key]=0;const reply=arr[used[key]%arr.length];used[key]++;return reply;}
  function ask(q){send.disabled=true;inp.disabled=true;const typing=addTyping();setTimeout(()=>{typing.remove();const key=match(q);const reply=getReply(key);addMsg(reply,'bot');if(key==='cost'||key==='contact'){setTimeout(()=>{const cta=document.createElement('div');cta.className='msg bot';cta.innerHTML='Ready? <a href="#contact" onclick="document.getElementById(\'chatBox\').classList.remove(\'on\')">Use our secure contact form →</a>';msgs.appendChild(cta);msgs.scrollTop=msgs.scrollHeight;},700);}send.disabled=false;inp.disabled=false;inp.focus();},800+Math.random()*600);}
  function submit(){const q=inp.value.trim();if(!q||send.disabled)return;addMsg(q,'user');inp.value='';ask(q);}
  send.addEventListener('click',submit);inp.addEventListener('keydown',e=>{if(e.key==='Enter'&&!e.shiftKey){e.preventDefault();submit();}});
  document.addEventListener('keydown',e=>{if(e.key==='/'&&document.activeElement.tagName!=='INPUT'&&document.activeElement.tagName!=='TEXTAREA'){e.preventDefault();box.classList.add('on');btn.classList.add('open');setTimeout(()=>inp.focus(),400);}if(e.key==='Escape'){box.classList.remove('on');btn.classList.remove('open');}});
})();

/* ── CINEMATIC TRANSITION ── */
const secTrans=document.getElementById('secTrans');
function triggerTransition(cb){if(!secTrans){if(cb)cb();return;}secTrans.classList.remove('out');secTrans.classList.add('in');setTimeout(()=>{if(cb)cb();setTimeout(()=>{secTrans.classList.remove('in');secTrans.classList.add('out');setTimeout(()=>secTrans.classList.remove('out'),700);},300);},700);}
document.querySelectorAll('.nl a,.mdr a,.ml').forEach(a=>{a.addEventListener('click',e=>{const href=a.getAttribute('href');if(href&&href.startsWith('#')){e.preventDefault();triggerTransition(()=>{const target=document.querySelector(href);if(target)target.scrollIntoView({behavior:'smooth'});});}});});

/* ── CURSOR TRAIL ── */
(function(){if(window.matchMedia('(max-width:768px)').matches)return;const trail=[];const COUNT=8;for(let i=0;i<COUNT;i++){const el=document.createElement('div');const size=6-i*0.5;el.className='cursor-trail';el.style.cssText=`width:${size}px;height:${size}px;opacity:${0.6-i*0.07}`;document.body.appendChild(el);trail.push({el,x:0,y:0});}let mx=0,my=0;document.addEventListener('mousemove',e=>{mx=e.clientX;my=e.clientY;});(function anim(){trail.forEach((t,i)=>{const prev=i===0?{x:mx,y:my}:trail[i-1];t.x+=(prev.x-t.x)*(0.4-i*0.03);t.y+=(prev.y-t.y)*(0.4-i*0.03);t.el.style.left=t.x+'px';t.el.style.top=t.y+'px';});requestAnimationFrame(anim);})();})();

/* ── LENIS SMOOTH SCROLL ── */
(function(){if(typeof Lenis==='undefined')return;const lenis=new Lenis({duration:1.1,easing:t=>Math.min(1,1.001-Math.pow(2,-10*t)),direction:'vertical',smooth:true,smoothTouch:false,touchMultiplier:2});if(window.gsap&&window.ScrollTrigger){gsap.registerPlugin(ScrollTrigger);lenis.on('scroll',function(){ScrollTrigger.update();});gsap.ticker.add(function(time){lenis.raf(time*1000);});gsap.ticker.lagSmoothing(0);}else{function lenisRaf(time){lenis.raf(time);requestAnimationFrame(lenisRaf);}requestAnimationFrame(lenisRaf);}document.querySelectorAll('a[href^="#"]').forEach(a=>{a.addEventListener('click',e=>{const id=a.getAttribute('href');if(id==='#')return;const target=document.querySelector(id);if(target){e.preventDefault();lenis.scrollTo(target,{offset:-74,duration:1.6});}});});window._lenis=lenis;})();

/* ── GSAP SCROLL ANIMATIONS ── */
(function(){if(!window.gsap||!window.ScrollTrigger)return;gsap.registerPlugin(ScrollTrigger);window.addEventListener('load',function(){setTimeout(function(){document.querySelectorAll('.sec-title-xl').forEach(function(el){gsap.fromTo(el,{y:40,opacity:0},{y:0,opacity:1,duration:0.8,ease:'power3.out',scrollTrigger:{trigger:el,start:'top 88%',once:true}});});document.querySelectorAll('.sec-eyebrow').forEach(function(el){gsap.fromTo(el,{x:-25,opacity:0},{x:0,opacity:1,duration:0.6,ease:'power2.out',scrollTrigger:{trigger:el,start:'top 90%',once:true}});});var scs=document.querySelectorAll('.sc');if(scs.length){gsap.fromTo(scs,{y:40,opacity:0},{y:0,opacity:1,duration:0.7,ease:'power3.out',stagger:0.1,scrollTrigger:{trigger:scs[0],start:'top 90%',once:true}});}document.querySelectorAll('.tc').forEach(function(el,i){gsap.fromTo(el,{x:i%2===0?-50:50,opacity:0},{x:0,opacity:1,duration:0.8,ease:'power3.out',scrollTrigger:{trigger:el,start:'top 88%',once:true}});});document.querySelectorAll('.ir').forEach(function(el,i){gsap.fromTo(el,{x:15,opacity:0},{x:0,opacity:1,duration:0.5,ease:'power2.out',delay:i*0.03,scrollTrigger:{trigger:el,start:'top 95%',once:true}});});var hv=document.querySelector('.hero-vert');if(hv){gsap.to(hv,{y:'-20%',ease:'none',scrollTrigger:{trigger:'.hero',start:'top top',end:'bottom top',scrub:2}});}document.querySelectorAll('.orb-p').forEach(function(o,i){gsap.to(o,{y:(i+1)*-80,ease:'none',scrollTrigger:{trigger:'.hero',start:'top top',end:'bottom top',scrub:1.5+i*0.3}});});ScrollTrigger.refresh();},200);});var bootWait=setInterval(function(){var pre=document.getElementById('pre');if(pre&&pre.classList.contains('out')||!pre){clearInterval(bootWait);var spans=document.querySelectorAll('.hero-h1 .w1 span');if(spans.length){gsap.fromTo(spans,{y:'100%',opacity:0},{y:0,opacity:1,stagger:0.1,duration:0.8,ease:'power3.out'});}document.querySelectorAll('.hs-n').forEach(function(el){var txt=el.textContent;var num=parseInt(txt.replace(/[^0-9]/g,''));if(!num)return;var sfx=txt.replace(/[0-9]/g,'');gsap.fromTo({v:0},{v:num},{duration:1.6,ease:'power2.out',onUpdate:function(){el.textContent=Math.floor(this.targets()[0].v)+sfx;}});});}},100);})();
</script>

<!-- FIREBASE -->
<script type="module">
import{initializeApp}from"https://www.gstatic.com/firebasejs/12.9.0/firebase-app.js";
import{getFirestore,collection,addDoc}from"https://www.gstatic.com/firebasejs/12.9.0/firebase-firestore.js";
const app=initializeApp({apiKey:"AIzaSyBl4bO6hNumDov3d26YNFj1y7Id498rBTU",authDomain:"rh2-systems.firebaseapp.com",projectId:"rh2-systems",storageBucket:"rh2-systems.firebasestorage.app",messagingSenderId:"492917852953",appId:"1:492917852953:web:9fc6ff86f6fcd2fc965388"});
const db=getFirestore(app);
const ov=document.getElementById('sov');
document.getElementById('closeSov').addEventListener('click',()=>ov.classList.remove('on'));
ov.addEventListener('click',e=>{if(e.target===ov)ov.classList.remove('on')});
const form=document.getElementById('cForm');const btn=document.getElementById('submitBtn');
form.addEventListener('submit',async e=>{e.preventDefault();const name=document.getElementById('fn').value.trim();const email=document.getElementById('fe').value.trim();const message=document.getElementById('fm').value.trim();if(!name||!email||!message)return;btn.textContent='ENCRYPTING...';btn.disabled=true;try{await addDoc(collection(db,'messages'),{name,email,message,timestamp:new Date(),source:'rh2-systems.com'});form.reset();ov.classList.add('on');}catch(err){alert('Error: '+err.message);}finally{btn.textContent='TRANSMIT ENCRYPTED REQUEST';btn.disabled=false;}});
</script>
</main>
</body>
</html>
