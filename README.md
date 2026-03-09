<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=5.0">
<title>RH²-Systems | Enterprise Cybersecurity & Offensive Security</title>
<meta name="description" content="RH²-Systems delivers enterprise-grade penetration testing, red teaming, and secure infrastructure auditing for high-risk environments.">
<meta name="author" content="RH²-Systems">
<link rel="canonical" href="https://rh2-systems.com/">
<meta property="og:title" content="RH²-Systems | Enterprise Cybersecurity">
<meta property="og:description" content="Advanced penetration testing, red team operations, and secure engineering for high-risk enterprise infrastructure.">
<meta property="og:type" content="website">
<meta property="og:url" content="https://rh2-systems.com/">
<link rel="icon" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 32 32'><rect width='32' height='32' fill='%237c3aff' rx='3'/><text y='23' x='3' font-size='18' font-family='monospace' fill='%23fff' font-weight='900'>R²</text></svg>">
<link rel="preconnect" href="https://fonts.googleapis.com">
<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
<link href="https://fonts.googleapis.com/css2?family=Anton&family=Sora:wght@300;400;600;700&family=Fira+Code:wght@400;600&display=swap" rel="stylesheet">
<style>
:root {
  --ink:     #03060a;
  --ink2:    #060c12;
  --ink3:    #091018;
  --ink4:    #0c1520;
  --fire:    #7c3aff;
  --fire2:   #a855f7;
  --gold:    #e879f9;
  --ice:     #38bdf8;
  --white:   #f0f6ff;
  --dim:     #3d5468;
  --dim2:    #6b8599;
  --gf:      rgba(124,58,255,0.22);
  --gi:      rgba(56,189,248,0.15);
  --gg:      rgba(232,121,249,0.12);
  --b1:      rgba(124,58,255,0.1);
  --b2:      rgba(124,58,255,0.3);
  --b3:      rgba(124,58,255,0.6);
  --ff-d:    'Anton', sans-serif;
  --ff-b:    'Sora', sans-serif;
  --ff-m:    'Fira Code', monospace;
  --ease:    cubic-bezier(0.16,1,0.3,1);
  --snap:    cubic-bezier(0.4,0,0.2,1);
}

*,*::before,*::after{margin:0;padding:0;box-sizing:border-box;-webkit-tap-highlight-color:transparent}
html{scroll-behavior:smooth;font-size:16px}
body{
  background:var(--ink);color:var(--white);
  font-family:var(--ff-b);line-height:1.7;
  overflow-x:hidden;cursor:none
}
a{text-decoration:none;color:inherit;cursor:pointer}
ul{list-style:none}
button{border:none;background:none;font-family:inherit;cursor:pointer}

/* ── NOISE ── */
body::before{
  content:'';position:fixed;inset:0;z-index:9990;pointer-events:none;
  background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 512 512' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.75' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E");
  opacity:0.032;mix-blend-mode:overlay
}

/* ── CURSOR ── */
#cur{position:fixed;top:0;left:0;z-index:99999;pointer-events:none;mix-blend-mode:difference}
.cur-d{
  position:absolute;width:8px;height:8px;
  background:var(--white);border-radius:50%;
  transform:translate(-50%,-50%);
  transition:width 0.15s,height 0.15s
}
.cur-r{
  position:absolute;width:40px;height:40px;
  border:1.5px solid var(--white);border-radius:50%;
  transform:translate(-50%,-50%);
  transition:width 0.3s var(--ease),height 0.3s var(--ease),border-radius 0.3s
}
body.hov .cur-d{width:0;height:0}
body.hov .cur-r{width:64px;height:64px;border-radius:4px;border-color:var(--fire)}

/* ── PRELOADER ── */
#pre{
  position:fixed;inset:0;z-index:99998;background:var(--ink);
  display:flex;flex-direction:column;align-items:center;justify-content:center;
  transition:clip-path 1s var(--ease);
  clip-path:inset(0 0 0 0)
}
#pre.out{clip-path:inset(0 0 100% 0)}
.pre-big{
  font-family:var(--ff-d);font-size:clamp(4rem,12vw,10rem);
  letter-spacing:0.06em;color:var(--white);
  position:relative;overflow:hidden
}
.pre-big::after{
  content:'';position:absolute;left:0;top:0;right:0;bottom:0;
  background:linear-gradient(90deg,transparent,var(--fire),transparent);
  animation:preSweep 1.2s ease forwards
}
@keyframes preSweep{from{transform:translateX(-100%)}to{transform:translateX(100%)}}
.pre-line{
  width:0;height:2px;
  background:linear-gradient(90deg,var(--fire),var(--gold),var(--ice));
  box-shadow:0 0 20px var(--fire);
  margin-top:24px;
  animation:preLine 1.2s var(--ease) forwards
}
@keyframes preLine{to{width:min(400px,80vw)}}
.pre-sub{
  font-family:var(--ff-m);font-size:0.72rem;color:var(--dim2);
  letter-spacing:0.25em;text-transform:uppercase;margin-top:16px;
  animation:fadeIn 0.5s 0.4s both
}
.pre-pct{
  font-family:var(--ff-d);font-size:3rem;color:var(--fire);
  margin-top:8px;text-shadow:0 0 40px var(--gf)
}

/* ── SCROLL TOP ── */
#stt{
  position:fixed;bottom:32px;right:32px;z-index:500;
  width:50px;height:50px;
  background:var(--fire);color:var(--white);
  border-radius:2px;
  display:flex;align-items:center;justify-content:center;
  font-size:1.2rem;
  opacity:0;pointer-events:none;
  transition:opacity 0.3s,transform 0.3s;
  box-shadow:0 0 30px var(--gf);cursor:pointer
}
#stt.on{opacity:1;pointer-events:all}
#stt:hover{transform:translateY(-4px) scale(1.05)}

/* ── LAYOUT ── */
.W{width:min(1320px,92%);margin:auto}
section{position:relative}

/* ── HEADER ── */
header{
  position:fixed;top:0;left:0;right:0;z-index:1000;
  height:74px;transition:all 0.4s var(--snap)
}
header.stuck{
  background:rgba(3,6,10,0.94);
  backdrop-filter:blur(32px);-webkit-backdrop-filter:blur(32px);
  border-bottom:1px solid var(--b1)
}
nav{height:100%;display:flex;align-items:center;justify-content:space-between}
.logo{
  font-family:var(--ff-d);font-size:1.6rem;letter-spacing:0.08em;
  color:var(--white);display:flex;align-items:center;gap:2px;
  position:relative
}
.logo-fire{color:var(--fire);text-shadow:0 0 20px var(--gf)}
.logo-dot{
  width:6px;height:6px;background:var(--fire);border-radius:50%;
  box-shadow:0 0 10px var(--fire);margin-left:4px;margin-bottom:12px;
  animation:ldot 2s ease infinite
}
@keyframes ldot{0%,100%{opacity:1}50%{opacity:0.2}}

.nl{display:flex;align-items:center;gap:36px}
.nl a{
  font-family:var(--ff-m);font-size:0.68rem;letter-spacing:0.12em;
  text-transform:uppercase;color:var(--dim2);
  transition:color 0.25s;position:relative
}
.nl a::before{
  content:attr(data-n);
  position:absolute;top:-14px;left:0;
  font-size:0.5rem;color:var(--fire);opacity:0.6;letter-spacing:0.1em
}
.nl a:hover{color:var(--fire)}
.nl-cta{
  padding:10px 22px;background:var(--fire);color:var(--white) !important;
  border-radius:2px;box-shadow:0 0 24px var(--gf);
  transition:box-shadow 0.25s,transform 0.25s !important
}
.nl-cta:hover{box-shadow:0 0 50px var(--gf) !important;transform:translateY(-2px)}

.hbtn{display:none;flex-direction:column;gap:5px;padding:6px;cursor:pointer}
.hbtn span{display:block;width:26px;height:2px;background:var(--white);border-radius:1px;transition:all 0.3s}
.hbtn.x span:nth-child(1){transform:translateY(7px) rotate(45deg);background:var(--fire)}
.hbtn.x span:nth-child(2){opacity:0}
.hbtn.x span:nth-child(3){transform:translateY(-7px) rotate(-45deg);background:var(--fire)}

.mdr{
  display:none;position:fixed;inset:0;top:74px;
  background:rgba(3,6,10,0.98);backdrop-filter:blur(40px);
  flex-direction:column;align-items:center;justify-content:center;gap:48px;
  opacity:0;pointer-events:none;transition:opacity 0.3s;z-index:999
}
.mdr.on{opacity:1;pointer-events:all}
.mdr a{
  font-family:var(--ff-d);font-size:2.8rem;letter-spacing:0.1em;
  color:var(--white);transition:color 0.2s,text-shadow 0.2s
}
.mdr a:hover{color:var(--fire);text-shadow:0 0 40px var(--gf)}

/* ── HERO ── */
.hero{
  min-height:100dvh;display:flex;align-items:center;
  padding-top:74px;overflow:hidden;position:relative
}
#heroCanvas{position:absolute;inset:0;width:100%;height:100%;z-index:2;opacity:0.25;pointer-events:none}

/* Diagonal split bg */
.hero-split{
  position:absolute;inset:0;z-index:-1;
  background:linear-gradient(105deg,var(--ink) 55%,#0a0d0f 55%)
}
.hero-split::after{
  content:'';position:absolute;
  top:0;right:0;bottom:0;width:45%;
  background:
    radial-gradient(ellipse 80% 60% at 80% 50%,rgba(124,58,255,0.07),transparent 70%),
    radial-gradient(ellipse 60% 80% at 100% 80%,rgba(0,200,255,0.04),transparent 70%)
}

/* Big vertical text */
.hero-vert{
  position:absolute;right:0;top:50%;transform:translateY(-50%);
  writing-mode:vertical-rl;text-orientation:mixed;
  font-family:var(--ff-d);font-size:clamp(5rem,12vw,9rem);
  letter-spacing:0.04em;
  color:rgba(255,255,255,0.03);
  user-select:none;pointer-events:none;z-index:1;
  white-space:nowrap;line-height:1
}

.hero-inner{position:relative;z-index:2;width:100%;padding:80px 0}
.hero-grid{display:grid;grid-template-columns:1fr 1fr;gap:60px;align-items:center}

/* Left col */
.hero-l{}
.hero-badge{
  display:inline-flex;align-items:center;gap:10px;
  padding:7px 18px;border-radius:99px;
  background:rgba(124,58,255,0.08);
  border:1px solid rgba(124,58,255,0.25);
  font-family:var(--ff-m);font-size:0.66rem;letter-spacing:0.2em;
  text-transform:uppercase;color:var(--fire);
  margin-bottom:2rem;
  box-shadow:0 0 24px rgba(124,58,255,0.1)
}
.bdot{width:6px;height:6px;border-radius:50%;background:var(--fire);box-shadow:0 0 8px var(--fire);animation:bdot 2s ease infinite}
@keyframes bdot{0%,100%{opacity:1}50%{opacity:0.2}}

.hero-h1{
  font-family:var(--ff-d);
  font-size:clamp(3.5rem,6.5vw,6.2rem);
  line-height:0.96;letter-spacing:0.04em;
  color:var(--white);margin-bottom:2rem
}
.hero-h1 .w1{display:block;overflow:hidden}
.hero-h1 .w1 span{display:block;animation:slideUp 0.9s var(--ease) both}
.hero-h1 .w1:nth-child(2) span{animation-delay:0.12s}
.hero-h1 .w1:nth-child(3) span{animation-delay:0.24s}
@keyframes slideUp{from{transform:translateY(105%);opacity:0}to{transform:translateY(0);opacity:1}}

.hero-h1 .fire-word{
  background:linear-gradient(90deg,var(--fire) 0%,var(--fire2) 40%,var(--gold) 100%);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
  filter:drop-shadow(0 0 30px rgba(124,58,255,0.4))
}

.hero-desc{
  color:var(--dim2);font-size:1rem;max-width:440px;
  margin-bottom:2.8rem;line-height:1.8;
  animation:fadeUp 1s 0.6s both
}

.hero-btns{display:flex;gap:16px;flex-wrap:wrap;animation:fadeUp 1s 0.8s both}
.btn{
  display:inline-flex;align-items:center;gap:10px;
  padding:14px 32px;border-radius:2px;
  font-family:var(--ff-m);font-size:0.75rem;
  letter-spacing:0.1em;text-transform:uppercase;
  transition:all 0.3s var(--ease);
  position:relative;overflow:hidden;cursor:pointer
}
.btn-fire{
  background:var(--fire);color:var(--white);
  box-shadow:0 0 0 0 var(--gf)
}
.btn-fire::before{
  content:'';position:absolute;inset:0;
  background:linear-gradient(135deg,rgba(255,255,255,0.2),transparent 60%);
  opacity:0;transition:opacity 0.3s
}
.btn-fire:hover{box-shadow:0 8px 40px var(--gf),0 0 80px rgba(124,58,255,0.22);transform:translateY(-3px)}
.btn-fire:hover::before{opacity:1}
.btn-ghost{
  background:transparent;color:var(--white);
  border:1px solid rgba(255,255,255,0.15)
}
.btn-ghost:hover{border-color:var(--fire);color:var(--fire);transform:translateY(-3px)}

/* Right col — terminal block */
.hero-r{animation:fadeUp 1s 0.5s both}
.term-big{
  background:rgba(6,12,18,0.9);
  border:1px solid rgba(124,58,255,0.15);
  border-radius:8px;overflow:hidden;
  box-shadow:0 0 60px rgba(124,58,255,0.06),0 40px 80px rgba(0,0,0,0.5);
  position:relative
}
.term-big::before{
  content:'';position:absolute;top:0;left:0;right:0;height:1px;
  background:linear-gradient(90deg,transparent,var(--fire),var(--gold),transparent)
}
.tb-chrome{
  display:flex;align-items:center;gap:8px;
  padding:14px 20px;background:rgba(0,0,0,0.3);
  border-bottom:1px solid rgba(255,255,255,0.04)
}
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
.tl-c .v{color:#6deeff}
.tl-c .g{color:#6dff9e}
.tl-c .r{color:var(--fire)}
.tl-c .w{color:var(--white)}
.tl-c .y{color:var(--gold)}
.tb-cursor{display:inline-block;width:8px;height:14px;background:var(--fire);vertical-align:middle;animation:blink 0.8s step-end infinite}
@keyframes blink{0%,100%{opacity:1}50%{opacity:0}}

/* Hero stats row */
.hero-stats{
  display:flex;gap:0;margin-top:48px;
  border:1px solid var(--b1);border-radius:4px;overflow:hidden;
  animation:fadeUp 1s 1s both
}
.hs{
  flex:1;padding:20px 24px;text-align:center;
  border-right:1px solid var(--b1);
  background:rgba(124,58,255,0.02);
  transition:background 0.3s
}
.hs:last-child{border-right:none}
.hs:hover{background:rgba(124,58,255,0.05)}
.hs-n{font-family:var(--ff-d);font-size:1.8rem;letter-spacing:0.06em;color:var(--fire);line-height:1;text-shadow:0 0 30px var(--gf)}
.hs-l{font-family:var(--ff-m);font-size:0.6rem;letter-spacing:0.14em;text-transform:uppercase;color:var(--dim);margin-top:5px}

/* ── TICKER ── */
.ticker-wrap{
  background:var(--ink2);
  border-top:1px solid var(--b1);border-bottom:1px solid var(--b1);
  padding:0;overflow:hidden;position:relative
}
.ticker-wrap::before,.ticker-wrap::after{
  content:'';position:absolute;top:0;bottom:0;width:80px;z-index:2;pointer-events:none
}
.ticker-wrap::before{left:0;background:linear-gradient(90deg,var(--ink2),transparent)}
.ticker-wrap::after{right:0;background:linear-gradient(270deg,var(--ink2),transparent)}
.ticker-inner{display:flex;animation:tick 28s linear infinite;white-space:nowrap}
@keyframes tick{from{transform:translateX(0)}to{transform:translateX(-50%)}}
.ti{
  display:inline-flex;align-items:center;gap:10px;
  padding:14px 36px;
  font-family:var(--ff-m);font-size:0.7rem;letter-spacing:0.1em;
  color:var(--dim2);border-right:1px solid var(--b1)
}
.ti .dot{width:5px;height:5px;border-radius:50%;flex-shrink:0}
.dot-f{background:var(--fire);box-shadow:0 0 8px var(--fire)}
.dot-i{background:var(--ice);box-shadow:0 0 6px var(--ice)}
.dot-g2{background:#00ff88;box-shadow:0 0 6px #00ff88}
.ti em{font-style:normal;color:var(--white);font-weight:600}

/* ── SERVICES ── */
#services{padding:140px 0;background:var(--ink)}

.sec-head{margin-bottom:80px}
.sec-eyebrow{
  font-family:var(--ff-m);font-size:0.66rem;letter-spacing:0.28em;
  text-transform:uppercase;color:var(--fire);
  display:inline-flex;align-items:center;gap:12px;margin-bottom:1.2rem
}
.sec-eyebrow::before{content:'';width:28px;height:1px;background:var(--fire);box-shadow:0 0 8px var(--fire)}

/* MASSIVE title */
.sec-title-xl{
  font-family:var(--ff-d);
  font-size:clamp(3.5rem,8vw,8rem);
  line-height:0.92;letter-spacing:0.04em;
  color:var(--white);
  position:relative
}
.sec-title-xl .outline{
  -webkit-text-stroke:1px rgba(255,255,255,0.15);
  color:transparent
}
.sec-title-xl .filled{color:var(--white)}
.sec-title-xl sup{
  font-family:var(--ff-m);font-size:0.2em;
  vertical-align:super;color:var(--fire);letter-spacing:0.2em
}

/* 3-col service cards — dramatic layout */
.svc-layout{
  display:grid;
  grid-template-columns:1fr 1fr 1fr;
  gap:2px;
  background:var(--b1);
  border:1px solid var(--b1);
  border-radius:10px;overflow:hidden
}

.sc{
  background:var(--ink2);
  padding:0;position:relative;overflow:hidden;
  transition:background 0.4s var(--ease);
  cursor:none
}
.sc:hover{background:var(--ink3)}

/* Number watermark */
.sc-wm{
  position:absolute;bottom:-20px;right:-10px;
  font-family:var(--ff-d);font-size:8rem;
  color:rgba(124,58,255,0.04);line-height:1;
  pointer-events:none;user-select:none;
  transition:color 0.4s,transform 0.4s var(--ease)
}
.sc:hover .sc-wm{color:rgba(124,58,255,0.07);transform:scale(1.05)}

.sc-inner{padding:52px 44px;position:relative;z-index:1}

/* Animated left border */
.sc::before{
  content:'';position:absolute;left:0;top:0;bottom:100%;width:2px;
  background:linear-gradient(to bottom,var(--fire),var(--gold));
  transition:bottom 0.5s var(--ease);box-shadow:0 0 12px var(--fire)
}
.sc:hover::before{bottom:0}

.sc-icon{
  width:60px;height:60px;margin-bottom:2rem;
  border-radius:6px;
  background:rgba(124,58,255,0.06);
  border:1px solid rgba(124,58,255,0.15);
  display:flex;align-items:center;justify-content:center;
  transition:all 0.4s var(--ease)
}
.sc:hover .sc-icon{
  background:rgba(124,58,255,0.12);
  border-color:rgba(124,58,255,0.4);
  box-shadow:0 0 30px rgba(124,58,255,0.22)
}
.sc-icon svg{width:28px;height:28px;stroke:var(--fire);fill:none;stroke-width:1.6;stroke-linecap:round;stroke-linejoin:round}

.sc-tag{font-family:var(--ff-m);font-size:0.6rem;letter-spacing:0.22em;color:var(--dim);text-transform:uppercase;margin-bottom:1rem}
.sc h3{
  font-family:var(--ff-d);font-size:clamp(1.4rem,2.2vw,1.8rem);
  letter-spacing:0.06em;color:var(--white);margin-bottom:1rem;line-height:1.1
}
.sc p{color:var(--dim2);font-size:0.9rem;line-height:1.8}

/* Learn more arrow */
.sc-arrow{
  display:inline-flex;align-items:center;gap:8px;
  font-family:var(--ff-m);font-size:0.68rem;letter-spacing:0.12em;
  text-transform:uppercase;color:var(--fire);
  margin-top:1.8rem;
  opacity:0;transform:translateX(-8px);
  transition:opacity 0.3s,transform 0.3s var(--ease)
}
.sc:hover .sc-arrow{opacity:1;transform:translateX(0)}
.sc-arrow svg{width:14px;height:14px;stroke:currentColor;fill:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round}

/* ── TEAM ── */
#team{
  padding:140px 0;
  background:var(--ink2);
  position:relative;overflow:hidden
}

/* Big bg text */
#team::before{
  content:'OPERATORS';
  position:absolute;bottom:-60px;left:-20px;
  font-family:var(--ff-d);font-size:clamp(6rem,15vw,14rem);
  color:rgba(124,58,255,0.03);letter-spacing:0.08em;
  pointer-events:none;user-select:none;white-space:nowrap;line-height:1
}

.team-head{
  display:flex;align-items:flex-end;justify-content:space-between;
  gap:40px;margin-bottom:80px;flex-wrap:wrap
}

.team-cards{
  display:grid;grid-template-columns:repeat(2,1fr);gap:30px
}

/* Card is a full anchor */
.tc{
  display:block;
  border:1px solid var(--b1);border-radius:12px;
  background:var(--ink);overflow:hidden;
  text-decoration:none;color:inherit;
  transition:border-color 0.4s,transform 0.4s var(--ease),box-shadow 0.4s;
  position:relative;cursor:pointer
}
.tc::after{
  content:'';position:absolute;inset:0;border-radius:12px;
  background:radial-gradient(ellipse 70% 50% at 50% 0%,rgba(124,58,255,0.05),transparent 60%);
  opacity:0;transition:opacity 0.4s
}
.tc:hover{
  border-color:var(--b3);
  transform:translateY(-8px);
  box-shadow:0 40px 80px rgba(0,0,0,0.5),0 0 60px rgba(124,58,255,0.08)
}
.tc:hover::after{opacity:1}

.tc-top{
  padding:48px 40px 36px;
  background:linear-gradient(160deg,#060e14,#030810);
  border-bottom:1px solid var(--b1);
  display:flex;align-items:center;gap:28px;
  position:relative;overflow:hidden
}
/* Animated circuit in bg */
.tc-top::before{
  content:'';position:absolute;top:-30px;right:-30px;
  width:150px;height:150px;
  border:1px solid rgba(124,58,255,0.06);border-radius:50%;
  box-shadow:
    0 0 0 25px rgba(124,58,255,0.03),
    0 0 0 50px rgba(255,58,0,0.015)
}

.tc-av{
  width:84px;height:84px;border-radius:50%;flex-shrink:0;
  background:linear-gradient(135deg,#0d1e28,#03080f);
  border:2px solid rgba(124,58,255,0.3);
  display:flex;align-items:center;justify-content:center;
  font-family:var(--ff-d);font-size:1.4rem;letter-spacing:0.06em;
  color:var(--fire);position:relative;z-index:1;
  box-shadow:0 0 30px rgba(124,58,255,0.15),inset 0 0 20px rgba(124,58,255,0.04)
}
.tc-av::after{
  content:'';position:absolute;inset:-5px;border-radius:50%;
  border:1px dashed rgba(255,58,0,0.18);
  animation:spin 10s linear infinite
}
@keyframes spin{from{transform:rotate(0deg)}to{transform:rotate(360deg)}}

.tc-info{z-index:1}
.tc-info h3{
  font-family:var(--ff-d);font-size:2rem;letter-spacing:0.06em;
  color:var(--white);line-height:1;margin-bottom:6px
}
.tc-role{
  font-family:var(--ff-m);font-size:0.66rem;letter-spacing:0.16em;
  text-transform:uppercase;color:var(--fire)
}

.tc-body{padding:36px 40px}
.tc-body p{color:var(--dim2);font-size:0.92rem;margin-bottom:1.6rem;line-height:1.85}
.tc-skills{display:flex;flex-wrap:wrap;gap:8px;margin-bottom:2rem}
.sk{
  font-family:var(--ff-m);font-size:0.62rem;letter-spacing:0.08em;
  padding:5px 14px;border-radius:2px;
  border:1px solid rgba(124,58,255,0.12);color:var(--dim2);
  transition:all 0.25s
}
.tc:hover .sk{border-color:rgba(124,58,255,0.25);color:var(--white)}

.tc-cta{
  display:inline-flex;align-items:center;gap:10px;
  font-family:var(--ff-m);font-size:0.7rem;letter-spacing:0.12em;
  text-transform:uppercase;color:var(--fire);
  transition:gap 0.3s var(--ease)
}
.tc:hover .tc-cta{gap:16px}
.tc-cta svg{width:14px;height:14px;stroke:currentColor;fill:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round}

/* ── INTEL ── */
#intelligence{
  padding:140px 0;
  background:var(--ink);
  position:relative
}
/* Red glow right */
#intelligence::after{
  content:'';position:absolute;top:50%;right:-200px;transform:translateY(-50%);
  width:600px;height:600px;border-radius:50%;
  background:radial-gradient(circle,rgba(124,58,255,0.05),transparent 65%);
  pointer-events:none
}

.intel-layout{
  display:grid;grid-template-columns:1fr 1.1fr;gap:80px;align-items:center;
  margin-top:4rem
}

/* Info side */
.intel-info{}
.intel-info p{color:var(--dim2);font-size:1rem;margin-bottom:2.5rem;line-height:1.85}
.intel-facts{display:flex;flex-direction:column;gap:0}
.if-row{
  display:flex;align-items:center;gap:16px;
  padding:18px 0;border-bottom:1px solid var(--b1)
}
.if-row:first-child{border-top:1px solid var(--b1)}
.if-ico{
  width:38px;height:38px;border-radius:4px;
  background:rgba(124,58,255,0.06);border:1px solid var(--b1);
  display:flex;align-items:center;justify-content:center;flex-shrink:0
}
.if-ico svg{width:16px;height:16px;stroke:var(--fire);fill:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round}
.if-text span{font-family:var(--ff-m);font-size:0.6rem;letter-spacing:0.16em;text-transform:uppercase;color:var(--dim);display:block;margin-bottom:2px}
.if-text strong{color:var(--white);font-weight:500;font-size:0.9rem}

/* ── INTEL HUD TERMINAL ── */
.intel-term{
  position:relative;border-radius:14px;overflow:hidden;
  background:linear-gradient(160deg,#07030f,#040210);
  box-shadow:0 0 0 1px rgba(124,58,255,0.2),0 0 60px rgba(124,58,255,0.07),0 40px 80px rgba(0,0,0,0.6)
}
/* Animated gradient border */
.intel-term::before{
  content:'';position:absolute;inset:0;border-radius:14px;z-index:0;padding:1px;
  background:conic-gradient(from var(--angle,0deg),rgba(124,58,255,0.8),rgba(168,85,247,0.4),rgba(56,189,248,0.6),rgba(232,121,249,0.4),rgba(124,58,255,0.8));
  -webkit-mask:linear-gradient(#fff 0 0) content-box,linear-gradient(#fff 0 0);
  -webkit-mask-composite:xor;mask-composite:exclude;
  animation:spinBorder 4s linear infinite
}
@property --angle{syntax:'<angle>';initial-value:0deg;inherits:false}
@keyframes spinBorder{to{--angle:360deg}}

.it-chrome,.it-hud-row,.it-prompt,.it-body,.it-threat,.it-foot,.scan-beam,.scan-v,.it-c1,.it-c2,.it-c3,.it-c4{position:relative;z-index:2}

/* 4 corner HUD brackets */
.it-c1,.it-c2,.it-c3,.it-c4{
  position:absolute;width:20px;height:20px;z-index:10;pointer-events:none
}
.it-c1{top:1px;left:1px;border-top:2px solid var(--fire);border-left:2px solid var(--fire);border-radius:3px 0 0 0}
.it-c2{top:1px;right:1px;border-top:2px solid var(--fire);border-right:2px solid var(--fire);border-radius:0 3px 0 0}
.it-c3{bottom:1px;left:1px;border-bottom:2px solid var(--fire);border-left:2px solid var(--fire);border-radius:0 0 0 3px}
.it-c4{bottom:1px;right:1px;border-bottom:2px solid var(--fire);border-right:2px solid var(--fire);border-radius:0 0 3px 0}

/* Chrome bar */
.it-chrome{
  display:flex;align-items:center;gap:8px;
  padding:13px 20px;background:rgba(0,0,0,0.55);
  border-bottom:1px solid rgba(124,58,255,0.1)
}
.it-dots{display:flex;gap:6px}
.it-dot{width:11px;height:11px;border-radius:50%}
.itd1{background:#ff5f57}.itd2{background:#ffbd2e}.itd3{background:#28c840}
.it-title{font-family:var(--ff-m);font-size:0.68rem;color:var(--dim);flex:1;margin-left:8px;letter-spacing:0.06em}
.it-live{display:flex;align-items:center;gap:6px;font-family:var(--ff-m);font-size:0.64rem;color:var(--fire)}
.itl{width:7px;height:7px;border-radius:50%;background:var(--fire);animation:tbl 1.4s ease infinite}

/* TOP HUD status bar */
.it-hud-row{
  display:flex;justify-content:space-between;align-items:center;
  padding:8px 22px;background:rgba(124,58,255,0.05);
  border-bottom:1px solid rgba(124,58,255,0.07);
  font-family:var(--ff-m);font-size:0.58rem;letter-spacing:0.14em;text-transform:uppercase
}
.hud-seg{display:flex;align-items:center;gap:7px;color:var(--dim2)}
.hud-seg .hv{color:var(--fire)}
.hud-blink{width:5px;height:5px;border-radius:50%;background:var(--fire);animation:tbl 1s ease infinite}

/* HORIZONTAL scan beam */
.scan-beam{
  position:absolute;left:0;right:0;top:0;z-index:9;pointer-events:none;
  height:3px;opacity:0;
  background:linear-gradient(90deg,transparent 0%,rgba(124,58,255,0.2) 20%,var(--fire) 50%,rgba(168,85,247,0.9) 80%,transparent 100%);
  box-shadow:0 0 16px var(--fire),0 0 40px rgba(124,58,255,0.5);
  filter:blur(0.5px);
  animation:scanb 3.5s ease-in-out infinite
}
@keyframes scanb{0%{top:0;opacity:0}5%{opacity:1}90%{opacity:1}100%{top:100%;opacity:0}}

/* VERTICAL scan beam */
.scan-v{
  position:absolute;top:0;bottom:0;left:0;z-index:9;pointer-events:none;
  width:2px;opacity:0;
  background:linear-gradient(180deg,transparent,rgba(124,58,255,0.6),var(--fire),rgba(124,58,255,0.6),transparent);
  box-shadow:0 0 10px rgba(124,58,255,0.5);
  animation:scanv 5s ease-in-out 1.8s infinite
}
@keyframes scanv{0%{left:0;opacity:0}4%{opacity:0.7}92%{opacity:0.7}100%{left:100%;opacity:0}}

/* Prompt */
.it-prompt{
  padding:12px 22px;border-bottom:1px solid rgba(124,58,255,0.06);
  display:flex;justify-content:space-between;align-items:center;
  background:rgba(0,0,0,0.25)
}
.it-prompt code{font-family:var(--ff-m);font-size:0.72rem;color:rgba(124,58,255,0.7)}
#scStat{font-family:var(--ff-m);font-size:0.63rem;color:var(--dim)}
.ok{color:#28c840 !important}.fail{color:#ff4060 !important}

/* Body */
.it-body{padding:14px 22px 16px;max-height:290px;overflow-y:auto}
.it-body::-webkit-scrollbar{width:3px}
.it-body::-webkit-scrollbar-track{background:transparent}
.it-body::-webkit-scrollbar-thumb{background:rgba(124,58,255,0.3);border-radius:3px}

/* Data rows */
.ir{
  display:flex;align-items:flex-start;gap:14px;
  padding:11px 0;border-bottom:1px solid rgba(255,255,255,0.025);
  position:relative;overflow:hidden
}
/* Row entry line */
.ir::after{
  content:'';position:absolute;bottom:0;left:0;width:0;height:1px;
  background:linear-gradient(90deg,var(--fire),transparent);
  transition:width 0.8s var(--ease)
}
.ir.lit::after{width:100%}
.ir:last-child{border-bottom:none}
.ik{
  font-family:var(--ff-m);font-size:0.67rem;color:var(--dim);
  letter-spacing:0.07em;min-width:178px;flex-shrink:0;padding-top:2px
}
.ik::before{content:'⟩ ';color:var(--fire);opacity:0.45;font-size:0.85em}
.iv{font-family:var(--ff-m);font-size:0.79rem;color:#b8c8e0;word-break:break-all;transition:color 0.4s}
.iv.loading{color:var(--dim)}
.iv.loading::after{content:'▋';animation:blink 0.75s step-end infinite;font-size:0.75rem;color:var(--fire);opacity:0.7;margin-left:3px}
.iv.loaded{color:#d4b8ff;animation:valIn 0.5s var(--ease)}
@keyframes valIn{from{opacity:0;transform:translateX(8px)}to{opacity:1;transform:none}}
.iv.hi{
  background:rgba(124,58,255,0.1);border:1px solid rgba(124,58,255,0.35);
  border-radius:3px;padding:2px 12px;color:var(--fire) !important;
  text-shadow:0 0 14px rgba(124,58,255,0.6);
  animation:ping 2.5s ease-in-out infinite
}
@keyframes ping{0%,100%{box-shadow:0 0 0 0 rgba(124,58,255,0.4)}60%{box-shadow:0 0 0 8px rgba(124,58,255,0)}}

/* Threat level bar */
.it-threat{padding:14px 22px 4px;border-top:1px solid rgba(124,58,255,0.06)}
.it-tl-label{
  display:flex;justify-content:space-between;
  font-family:var(--ff-m);font-size:0.58rem;letter-spacing:0.14em;
  text-transform:uppercase;color:var(--dim);margin-bottom:8px
}
.it-tl-label span{color:var(--fire)}
.tbar{height:4px;background:rgba(255,255,255,0.04);border-radius:4px;overflow:hidden;position:relative}
.tbar-fill{
  height:100%;width:0;border-radius:4px;
  background:linear-gradient(90deg,rgba(124,58,255,0.8),var(--fire),var(--gold));
  box-shadow:0 0 12px var(--fire);
  transition:width 2.5s cubic-bezier(0.4,0,0.2,1) 0.5s
}
.tbar-fill.go{width:73%}
/* Pulsing glow on bar */
.tbar::after{
  content:'';position:absolute;inset:0;
  background:linear-gradient(90deg,transparent,rgba(255,255,255,0.1),transparent);
  animation:barShimmer 2s ease infinite
}
@keyframes barShimmer{0%{transform:translateX(-100%)}100%{transform:translateX(100%)}}

/* Footer */
.it-foot{
  padding:9px 22px;background:rgba(124,58,255,0.03);
  border-top:1px solid rgba(124,58,255,0.06);
  display:flex;justify-content:space-between;
  font-family:var(--ff-m);font-size:0.6rem;color:var(--dim)
}

/* ── CONTACT ── */
#contact{
  padding:140px 0;background:var(--ink2);
  position:relative;overflow:hidden
}
#contact::before{
  content:'CONTACT';
  position:absolute;top:50%;left:50%;transform:translate(-50%,-50%);
  font-family:var(--ff-d);font-size:clamp(6rem,14vw,14rem);
  color:rgba(255,58,0,0.025);letter-spacing:0.1em;
  pointer-events:none;user-select:none;white-space:nowrap
}

.contact-grid{
  display:grid;grid-template-columns:1fr 1.4fr;
  gap:100px;align-items:start;margin-top:4rem
}

.c-left p{color:var(--dim2);font-size:1rem;margin-bottom:2.5rem;line-height:1.85}
.c-details{display:flex;flex-direction:column}
.cd{
  display:flex;align-items:flex-start;gap:16px;
  padding:20px 0;border-bottom:1px solid var(--b1)
}
.cd:first-child{border-top:1px solid var(--b1)}
.cd-ico{
  width:40px;height:40px;border-radius:4px;
  background:rgba(124,58,255,0.06);border:1px solid var(--b1);
  display:flex;align-items:center;justify-content:center;flex-shrink:0
}
.cd-ico svg{width:16px;height:16px;stroke:var(--fire);fill:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round}
.cd-t span{font-family:var(--ff-m);font-size:0.6rem;letter-spacing:0.16em;text-transform:uppercase;color:var(--dim);display:block;margin-bottom:3px}
.cd-t strong{color:var(--white);font-weight:500;font-size:0.92rem}
.c-note{
  margin-top:1.8rem;padding:16px 20px;
  border:1px solid rgba(124,58,255,0.12);border-radius:4px;
  background:rgba(124,58,255,0.03);
  font-family:var(--ff-m);font-size:0.68rem;color:var(--fire);letter-spacing:0.04em
}
.c-note::before{content:'// ';opacity:0.5}

/* Form */
.c-form{
  background:var(--ink);border:1px solid var(--b1);
  border-radius:12px;padding:56px 52px;
  position:relative;overflow:hidden
}
.c-form::before{
  content:'';position:absolute;top:0;left:0;right:0;height:1px;
  background:linear-gradient(90deg,transparent,var(--fire),var(--gold),transparent)
}
/* Corner accent */
.c-form::after{
  content:'';position:absolute;top:0;right:0;
  width:80px;height:80px;
  border-top:1px solid rgba(124,58,255,0.12);
  border-right:1px solid rgba(124,58,255,0.12);
  border-radius:0 12px 0 0
}
.fg{display:grid;grid-template-columns:1fr 1fr;gap:20px}
.fi{display:flex;flex-direction:column;gap:8px;margin-bottom:22px}
.fi label{font-family:var(--ff-m);font-size:0.62rem;letter-spacing:0.16em;text-transform:uppercase;color:var(--dim2)}
.fi input,.fi textarea{
  background:rgba(0,0,0,0.3);
  border:1px solid rgba(255,255,255,0.06);
  border-radius:4px;padding:14px 18px;
  color:var(--white);font-family:var(--ff-b);font-size:16px;
  width:100%;transition:all 0.25s var(--snap);
  -webkit-appearance:none;caret-color:var(--fire)
}
.fi input:focus,.fi textarea:focus{
  outline:none;border-color:rgba(124,58,255,0.35);
  background:rgba(255,58,0,0.025);
  box-shadow:0 0 0 3px rgba(124,58,255,0.06)
}
.fi textarea{resize:vertical;min-height:140px}
.fsub{
  width:100%;padding:18px;
  background:var(--fire);color:var(--white);
  border-radius:4px;border:none;
  font-family:var(--ff-m);font-size:0.8rem;
  font-weight:600;letter-spacing:0.16em;text-transform:uppercase;
  transition:all 0.3s var(--ease);cursor:pointer;
  position:relative;overflow:hidden;
  box-shadow:0 0 30px rgba(124,58,255,0.25)
}
.fsub::before{
  content:'';position:absolute;top:0;left:-100%;right:100%;bottom:0;
  background:rgba(255,255,255,0.15);
  transition:left 0.4s var(--ease),right 0.4s var(--ease)
}
.fsub:hover{transform:translateY(-2px);box-shadow:0 16px 50px rgba(124,58,255,0.35)}
.fsub:hover::before{left:0;right:0}
.fsub:disabled{opacity:0.5;transform:none;cursor:not-allowed}

/* ── SUCCESS OVERLAY ── */
#sov{
  position:fixed;inset:0;background:rgba(3,6,10,0.96);
  backdrop-filter:blur(20px);-webkit-backdrop-filter:blur(20px);
  display:flex;align-items:center;justify-content:center;
  z-index:99997;opacity:0;pointer-events:none;transition:opacity 0.4s
}
#sov.on{opacity:1;pointer-events:all}
.sm{
  background:var(--ink2);border:1px solid var(--b3);
  border-radius:16px;padding:70px 60px;text-align:center;
  max-width:460px;width:90%;
  box-shadow:0 0 120px rgba(124,58,255,0.15),0 0 240px rgba(124,58,255,0.05);
  transform:scale(0.85) translateY(28px);
  transition:transform 0.5s cubic-bezier(0.175,0.885,0.32,1.275)
}
#sov.on .sm{transform:scale(1) translateY(0)}
.sm-ring{
  width:92px;height:92px;border-radius:50%;
  border:2px solid var(--fire);
  margin:0 auto 28px;
  display:flex;align-items:center;justify-content:center;
  font-size:2.6rem;color:var(--fire);
  box-shadow:0 0 50px rgba(124,58,255,0.3)
}
.sm h3{font-family:var(--ff-d);font-size:2rem;letter-spacing:0.08em;color:var(--white);margin-bottom:12px}
.sm p{color:var(--dim2);margin-bottom:32px}

/* ── FOOTER ── */
footer{
  background:var(--ink);
  border-top:1px solid var(--b1);
  padding:100px 0 48px
}
.foot-grid{
  display:grid;grid-template-columns:1.6fr 1fr 1fr;
  gap:80px;margin-bottom:70px;
  padding-bottom:70px;border-bottom:1px solid var(--b1)
}
.foot-logo{
  font-family:var(--ff-d);font-size:2.2rem;letter-spacing:0.08em;
  color:var(--white);margin-bottom:16px;display:flex;align-items:center;gap:8px
}
.foot-logo em{font-style:normal;color:var(--fire);text-shadow:0 0 20px var(--gf)}
.foot-brand p{color:var(--dim2);font-size:0.92rem;max-width:300px;line-height:1.8}
.foot-col h5{
  font-family:var(--ff-m);font-size:0.63rem;letter-spacing:0.22em;
  text-transform:uppercase;color:var(--dim);margin-bottom:1.4rem
}
.foot-col ul{display:flex;flex-direction:column;gap:12px}
.foot-col a{
  color:var(--dim2);font-size:0.9rem;
  transition:color 0.25s,padding-left 0.25s;
  display:flex;align-items:center;gap:0
}
.foot-col a:hover{color:var(--fire);padding-left:8px}
.foot-bottom{
  display:flex;justify-content:space-between;align-items:center;
  flex-wrap:wrap;gap:16px
}
.foot-copy{font-family:var(--ff-m);font-size:0.62rem;color:rgba(61,84,104,0.6);letter-spacing:0.08em}
.foot-right{font-family:var(--ff-m);font-size:0.62rem;color:var(--dim)}
.foot-right span{color:var(--fire)}

/* ── SCROLL REVEAL ── */
.rv{opacity:0;transform:translateY(40px);transition:opacity 0.9s var(--ease),transform 0.9s var(--ease)}
.rv.in{opacity:1;transform:translateY(0)}
.rv.d1{transition-delay:0.1s}.rv.d2{transition-delay:0.2s}
.rv.d3{transition-delay:0.3s}.rv.d4{transition-delay:0.4s}
.rv.d5{transition-delay:0.5s}

/* ── SCROLL WORM ── */
.sworm{
  position:absolute;bottom:36px;left:50%;transform:translateX(-50%);
  display:flex;flex-direction:column;align-items:center;gap:8px;
  font-family:var(--ff-m);font-size:0.58rem;letter-spacing:0.22em;
  text-transform:uppercase;color:var(--dim);z-index:10;
  animation:fadeUp 1s 1.2s both
}
.sw-o{width:22px;height:38px;border:1.5px solid var(--dim);border-radius:11px;display:flex;justify-content:center;padding-top:5px}
.sw-i{width:3px;height:8px;background:var(--fire);border-radius:2px;box-shadow:0 0 6px var(--fire);animation:worm 2s ease-in-out infinite}
@keyframes worm{0%,100%{transform:translateY(0);opacity:1}80%{transform:translateY(16px);opacity:0}}

/* ── KEYFRAMES ── */
@keyframes fadeUp{from{opacity:0;transform:translateY(30px)}to{opacity:1;transform:translateY(0)}}
@keyframes fadeIn{from{opacity:0}to{opacity:1}}

/* ── RESPONSIVE ── */
@media(max-width:1100px){
  .hero-grid{grid-template-columns:1fr;gap:60px}
  .hero-r{display:none}
  .hero-h1{font-size:clamp(3rem,8vw,5.5rem)}
  .intel-layout{grid-template-columns:1fr;gap:60px}
  .foot-grid{grid-template-columns:1fr 1fr}
}
@media(max-width:900px){
  .svc-layout{grid-template-columns:1fr}
  .team-cards{grid-template-columns:1fr}
  .contact-grid{grid-template-columns:1fr;gap:60px}
  .hero-stats{flex-wrap:wrap}
  .hs{min-width:45%}
}
@media(max-width:768px){
  section{padding:90px 0 !important}
  .nl{display:none}
  .hbtn{display:flex}
  .mdr{display:flex}
  .fg{grid-template-columns:1fr}
  .c-form{padding:36px 28px}
  .foot-grid{grid-template-columns:1fr;gap:48px}
  .foot-bottom{flex-direction:column;text-align:center}
  body{cursor:auto}
  #cur{display:none}
  button,a{cursor:pointer}
}
@media(max-width:520px){
  .hero-stats{flex-direction:column}
  .hs{width:100%}
  .sec-title-xl{font-size:clamp(2.5rem,10vw,4rem)}
}

/* 3D TILT GLOW */
.tc, .sc {
  transform-style: preserve-3d;
  will-change: transform;
}
.tc::before {
  content: '';
  position: absolute; inset: 0; border-radius: 12px;
  background: radial-gradient(circle at var(--gx,50%) var(--gy,50%), rgba(124,58,255,0.12), transparent 60%);
  opacity: 0; transition: opacity 0.3s; z-index: 0; pointer-events: none;
}
.tc:hover::before { opacity: 1; }
.sc::after {
  content: '';
  position: absolute; inset: 0;
  background: radial-gradient(circle at var(--gx,50%) var(--gy,50%), rgba(124,58,255,0.08), transparent 55%);
  opacity: 0; transition: opacity 0.3s; pointer-events: none;
}
.sc:hover::after { opacity: 1; }

/* MAGNETIC BTN smooth */
.btn, .fsub, .nl-cta {
  will-change: transform;
  transition: transform 0.15s ease, box-shadow 0.3s, color 0.3s, border-color 0.3s !important;
}

/* WAVEFORM */
.wave-wrap {
  margin-top: 28px;
  border: 1px solid rgba(124,58,255,0.15);
  border-radius: 8px;
  overflow: hidden;
  background: rgba(0,0,0,0.3);
  position: relative;
}
.wave-header {
  display: flex; justify-content: space-between; align-items: center;
  padding: 10px 18px;
  border-bottom: 1px solid rgba(124,58,255,0.08);
  font-family: var(--ff-m); font-size: 0.62rem;
  letter-spacing: 0.14em; text-transform: uppercase;
}
.wave-header .wh-l { color: var(--dim2); }
.wave-header .wh-r { color: var(--fire); display: flex; align-items: center; gap: 6px; }
.wave-blink { width: 5px; height: 5px; border-radius: 50%; background: var(--fire); animation: tbl 1s ease infinite; }
#waveCanvas { display: block; width: 100%; height: 120px; }


/* ── MATRIX RAIN ── */
#matrixCanvas{
  position:absolute;inset:0;width:100%;height:100%;
  z-index:0;opacity:0.18;pointer-events:none
}

/* ── WEBGL CANVAS ── */
#webglCanvas{
  position:absolute;top:0;right:0;bottom:0;left:0;width:100%;height:100%;
  z-index:1;pointer-events:none;opacity:0.9
}

/* ── CLICK RIPPLE ── */
.ripple{
  position:fixed;border-radius:50%;pointer-events:none;z-index:9995;
  border:2px solid var(--fire);
  transform:translate(-50%,-50%) scale(0);
  animation:rippleOut 0.9s cubic-bezier(0.4,0,0.2,1) forwards
}
@keyframes rippleOut{
  0%{transform:translate(-50%,-50%) scale(0);opacity:1}
  100%{transform:translate(-50%,-50%) scale(4);opacity:0}
}
.ripple2{
  position:fixed;border-radius:50%;pointer-events:none;z-index:9994;
  background:radial-gradient(circle,rgba(124,58,255,0.15),transparent 70%);
  transform:translate(-50%,-50%) scale(0);
  animation:rippleOut2 1.2s cubic-bezier(0.4,0,0.2,1) forwards
}
@keyframes rippleOut2{
  0%{transform:translate(-50%,-50%) scale(0);opacity:1}
  100%{transform:translate(-50%,-50%) scale(6);opacity:0}
}

/* ── SVG PATH DRAW ── */
.svg-draw{
  position:absolute;top:0;left:0;pointer-events:none;z-index:3;
  opacity:0.25
}
.svg-draw path,.svg-draw line,.svg-draw polyline{
  stroke-dasharray:2000;
  stroke-dashoffset:2000;
  animation:drawPath 3s cubic-bezier(0.4,0,0.2,1) 1.5s forwards
}
@keyframes drawPath{to{stroke-dashoffset:0}}

/* ── SCROLL WIPE SECTIONS ── */
.section-wipe{
  clip-path:inset(0 100% 0 0);
  transition:clip-path 1.1s cubic-bezier(0.16,1,0.3,1)
}
.section-wipe.in{clip-path:inset(0 0% 0 0)}

/* ── SOUND INDICATOR ── */
#soundBtn{
  position:fixed;bottom:32px;left:32px;z-index:500;
  width:48px;height:48px;border-radius:50%;
  background:var(--ink3);border:1px solid rgba(124,58,255,0.3);
  color:var(--dim2);display:flex;align-items:center;justify-content:center;
  font-size:1.1rem;cursor:pointer;
  transition:all 0.3s;box-shadow:0 0 20px rgba(124,58,255,0.1)
}
#soundBtn:hover{border-color:var(--fire);color:var(--fire);box-shadow:0 0 30px rgba(124,58,255,0.3)}
#soundBtn.active{color:var(--fire);border-color:var(--fire);box-shadow:0 0 20px rgba(124,58,255,0.4)}

/* ── SECTION REVEAL OVERRIDE for wipe ── */
.rv.wipe{
  opacity:1 !important;transform:none !important;
  clip-path:inset(0 100% 0 0);
  transition:clip-path 1.1s cubic-bezier(0.16,1,0.3,1)
}
.rv.wipe.in{clip-path:inset(0 0% 0 0)}

</style>
</head>
<body>

<!-- CURSOR -->
<div id="cur">
  <div class="cur-d"></div>
  <div class="cur-r"></div>
</div>

<!-- PRELOADER -->
<div id="pre">
  <div class="pre-big">RH²</div>
  <div class="pre-line"></div>
  <div class="pre-sub">Initializing secure channel</div>
  <div class="pre-pct" id="prePct">0%</div>
</div>

<!-- SUCCESS -->
<div id="sov" role="dialog" aria-modal="true">
  <div class="sm">
    <div class="sm-ring">✓</div>
    <h3>TRANSMISSION SECURED</h3>
    <p>Message encrypted and delivered to RH²-Systems servers.</p>
    <button class="fsub" id="closeSov" style="max-width:200px;margin:auto;display:block;">ACKNOWLEDGE</button>
  </div>
</div>

<!-- SCROLL TOP -->
<button id="stt" aria-label="Back to top">↑</button>

<!-- SOUND TOGGLE -->
<button id="soundBtn" aria-label="Toggle UI sounds" title="Toggle sounds">🔇</button>

<!-- ════════ HEADER ════════ -->
<header id="hdr">
  <div class="W">
    <nav>
      <a href="#" class="logo">RH²-<span class="logo-fire">Systems</span><span class="logo-dot"></span></a>
      <ul class="nl">
        <li><a href="#services" data-n="01">Services</a></li>
        <li><a href="#team" data-n="02">Team</a></li>
        <li><a href="#intelligence" data-n="03">Intel</a></li>
        <li><a href="#contact" class="nl-cta">Contact</a></li>
      </ul>
      <button class="hbtn" id="hbtn" aria-label="Menu" aria-expanded="false">
        <span></span><span></span><span></span>
      </button>
    </nav>
  </div>
</header>

<!-- MOBILE DRAWER -->
<nav class="mdr" id="mdr">
  <a href="#services" class="ml">Services</a>
  <a href="#team" class="ml">Team</a>
  <a href="#intelligence" class="ml">Intel</a>
  <a href="#contact" class="ml">Contact</a>
</nav>

<!-- ════════ HERO ════════ -->
<section class="hero">
  <canvas id="matrixCanvas" aria-hidden="true"></canvas>
  <canvas id="webglCanvas" aria-hidden="true"></canvas>
  <canvas id="heroCanvas" aria-hidden="true"></canvas>
  <div class="hero-split" aria-hidden="true"></div>
  <!-- SVG decorative path draw -->
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
      <!-- LEFT -->
      <div class="hero-l">
        <div class="hero-badge">
          <span class="bdot"></span>
          SYSTEM OPERATIONAL · <span id="utcClock">00:00:00 UTC</span>
        </div>

        <h1 class="hero-h1">
          <div class="w1"><span>OFFENSIVE</span></div>
          <div class="w1"><span class="fire-word">SECURITY.</span></div>
          <div class="w1"><span id="typeEl"></span><span class="tb-cursor" aria-hidden="true"></span></div>
        </h1>

        <p class="hero-desc">Advanced penetration testing, red team operations, and secure engineering for high-risk enterprise infrastructure worldwide.</p>

        <div class="hero-btns">
          <a href="#contact" class="btn btn-fire">
            <svg viewBox="0 0 24 24" width="16" height="16" stroke="currentColor" fill="none" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg>
            Initiate Confidential Audit
          </a>
          <a href="#services" class="btn btn-ghost">
            Explore Capabilities
            <svg viewBox="0 0 24 24" width="14" height="14" stroke="currentColor" fill="none" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="9 18 15 12 9 6"/></svg>
          </a>
        </div>

        <div class="hero-stats">
          <div class="hs"><div class="hs-n">150+</div><div class="hs-l">Engagements</div></div>
          <div class="hs"><div class="hs-n">100%</div><div class="hs-l">Confidentiality</div></div>
          <div class="hs"><div class="hs-n">24/7</div><div class="hs-l">Support</div></div>
          <div class="hs"><div class="hs-n">0</div><div class="hs-l">Breaches</div></div>
        </div>
      </div>

      <!-- RIGHT — TERMINAL -->
      <div class="hero-r">
        <div class="term-big">
          <div class="tb-chrome">
            <div class="tb-dots">
              <div class="tb-dot tbd1"></div>
              <div class="tb-dot tbd2"></div>
              <div class="tb-dot tbd3"></div>
            </div>
            <span class="tb-title">rh2sys — active_session</span>
            <div class="tb-live"><span class="tbl"></span>LIVE</div>
          </div>
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

  <div class="sworm" aria-hidden="true">
    <div class="sw-o"><div class="sw-i"></div></div>
    Scroll
  </div>
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
    <!-- duplicate for loop -->
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

<!-- ════════ SERVICES ════════ -->
<section id="services">
  <div class="W">
    <div class="sec-head rv wipe">
      <div class="sec-eyebrow">01 — Capabilities</div>
      <div class="sec-title-xl">
        <span class="filled">CORE</span><br>
        <span class="outline">SECURITY</span><br>
        <span class="filled">SERVICES<sup>03</sup></span>
      </div>
    </div>

    <div class="svc-layout">
      <!-- Pen Testing -->
      <div class="sc rv">
        <div class="sc-wm">01</div>
        <div class="sc-inner">
          <div class="sc-icon">
            <svg viewBox="0 0 24 24"><circle cx="11" cy="11" r="8"/><line x1="21" y1="21" x2="16.65" y2="16.65"/></svg>
          </div>
          <div class="sc-tag">SVC_001</div>
          <h3>Penetration Testing</h3>
          <p>Manual and automated assessments of Web, Mobile, API, and Cloud infrastructure aligned with OWASP Top 10 and NIST frameworks.</p>
          <div class="sc-arrow">
            Engage
            <svg viewBox="0 0 24 24"><line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/></svg>
          </div>
        </div>
      </div>
      <!-- Red Team -->
      <div class="sc rv d2">
        <div class="sc-wm">02</div>
        <div class="sc-inner">
          <div class="sc-icon">
            <svg viewBox="0 0 24 24"><polygon points="13 2 3 14 12 14 11 22 21 10 12 10 13 2"/></svg>
          </div>
          <div class="sc-tag">SVC_002</div>
          <h3>Red Team Operations</h3>
          <p>Adversary simulation replicating nation-state APT tactics to test your detection and response capabilities in real-time scenarios.</p>
          <div class="sc-arrow">
            Engage
            <svg viewBox="0 0 24 24"><line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/></svg>
          </div>
        </div>
      </div>
      <!-- Secure Eng -->
      <div class="sc rv d4">
        <div class="sc-wm">03</div>
        <div class="sc-inner">
          <div class="sc-icon">
            <svg viewBox="0 0 24 24"><polyline points="16 18 22 12 16 6"/><polyline points="8 6 2 12 8 18"/></svg>
          </div>
          <div class="sc-tag">SVC_003</div>
          <h3>Secure Engineering</h3>
          <p>DevSecOps integration, Zero Trust architecture design, and source code review to embed security into the DNA of your software.</p>
          <div class="sc-arrow">
            Engage
            <svg viewBox="0 0 24 24"><line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/></svg>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ════════ TEAM ════════ -->
<section id="team">
  <div class="W">
    <div class="team-head rv wipe">
      <div class="rv">
        <div class="sec-eyebrow">02 — Leadership</div>
        <div class="sec-title-xl">
          <span class="filled">THE</span><br>
          <span class="outline">OPERATORS</span>
        </div>
      </div>
      <p style="color:var(--dim2);max-width:340px;font-size:0.98rem;line-height:1.85" class="rv d2">Built by engineers who understand both the attack vector and the defense mechanism.</p>
    </div>

    <div class="team-cards">
      <a href="https://rh-systems.github.io/Raj-Hridoy/" target="_blank" rel="noopener noreferrer" class="tc rv d1">
        <div class="tc-top">
          <div class="tc-av">RH</div>
          <div class="tc-info">
            <h3>Raj Hridoy</h3>
            <span class="tc-role">Cybersecurity Engineer</span>
          </div>
        </div>
        <div class="tc-body">
          <p>Specializing in secure software architecture and complex vulnerability analysis. Raj bridges high-level development with low-level security protocols.</p>
          <div class="tc-skills">
            <span class="sk">Secure Arch</span>
            <span class="sk">Python / Go</span>
            <span class="sk">Cloud Security</span>
            <span class="sk">DevSecOps</span>
          </div>
          <div class="tc-cta">
            View Profile
            <svg viewBox="0 0 24 24"><line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/></svg>
          </div>
        </div>
      </a>

      <a href="https://rh-systems.github.io/Riyad-Hasan/" target="_blank" rel="noopener noreferrer" class="tc rv d2">
        <div class="tc-top">
          <div class="tc-av">RH</div>
          <div class="tc-info">
            <h3>Riyad Hasan</h3>
            <span class="tc-role">Ethical Hacker</span>
          </div>
        </div>
        <div class="tc-body">
          <p>Focused on advanced threat modeling and penetration testing. Riyad specializes in breaking systems to make them unbreakable through adversarial analysis.</p>
          <div class="tc-skills">
            <span class="sk">PenTesting</span>
            <span class="sk">Network Forensics</span>
            <span class="sk">Red Teaming</span>
            <span class="sk">Exploit Dev</span>
          </div>
          <div class="tc-cta">
            View Profile
            <svg viewBox="0 0 24 24"><line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/></svg>
          </div>
        </div>
      </a>
    </div>
  </div>
</section>

<!-- ════════ INTEL ════════ -->
<section id="intelligence">
  <div class="W">
    <div class="rv" style="text-align:center;margin-bottom:0">
      <div class="sec-eyebrow" style="justify-content:center">03 — Telemetry</div>
      <div class="sec-title-xl" style="text-align:center">
        <span class="filled">NETWORK</span>
        <span class="outline"> INTEL</span>
      </div>
      <p style="color:var(--dim2);max-width:500px;margin:1rem auto 0;font-size:0.98rem">Real-time analysis of your active connection — demonstrating reconnaissance techniques used in live security assessments.</p>
    </div>

    <div class="intel-layout">
      <div class="rv d1">
        <p>Every security assessment begins here — mapping your digital footprint before a single exploit is staged. This is what attackers see before you even know they're watching.</p>
        <div class="intel-facts">
          <div class="if-row">
            <div class="if-ico"><svg viewBox="0 0 24 24"><path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"/><circle cx="12" cy="10" r="3"/></svg></div>
            <div class="if-text"><span>Location</span><strong>Rajshahi Division, Bangladesh</strong></div>
          </div>
          <div class="if-row">
            <div class="if-ico"><svg viewBox="0 0 24 24"><circle cx="12" cy="12" r="10"/><polyline points="12 6 12 12 16 14"/></svg></div>
            <div class="if-text"><span>Availability</span><strong>24 / 7 Incident Support</strong></div>
          </div>
          <div class="if-row">
            <div class="if-ico"><svg viewBox="0 0 24 24"><rect x="3" y="11" width="18" height="11" rx="2"/><path d="M7 11V7a5 5 0 0 1 10 0v4"/></svg></div>
            <div class="if-text"><span>Encryption</span><strong>End-to-end · TLS 1.3 · AES-256</strong></div>
          </div>
        </div>

        <!-- LIVE THREAT WAVEFORM -->
        <div class="wave-wrap rv d2">
          <div class="wave-header">
            <span class="wh-l">Live Threat Activity</span>
            <span class="wh-r"><span class="wave-blink"></span>Real-time Feed</span>
          </div>
          <canvas id="waveCanvas" aria-hidden="true"></canvas>
        </div>
      </div>

      <div class="intel-term rv d2">
        <!-- HUD corners -->
        <div class="it-c1"></div><div class="it-c2"></div>
        <div class="it-c3"></div><div class="it-c4"></div>
        <!-- Scan beams -->
        <div class="scan-beam" aria-hidden="true"></div>
        <div class="scan-v" aria-hidden="true"></div>
        <!-- Chrome bar -->
        <div class="it-chrome">
          <div class="it-dots">
            <div class="it-dot itd1"></div>
            <div class="it-dot itd2"></div>
            <div class="it-dot itd3"></div>
          </div>
          <span class="it-title">rh2sys_recon v4.2 — target: visitor</span>
          <div class="it-live"><span class="itl"></span>LIVE SCAN</div>
        </div>
        <!-- HUD status row -->
        <div class="it-hud-row" aria-hidden="true">
          <div class="hud-seg"><span class="hud-blink"></span>ENC: <span class="hv">AES-256</span></div>
          <div class="hud-seg">PROTO: <span class="hv">TLS 1.3</span></div>
          <div class="hud-seg">MODE: <span class="hv">PASSIVE RECON</span></div>
          <div class="hud-seg">SIG: <span class="hv" id="scStat">INIT...</span></div>
        </div>
        <!-- Prompt -->
        <div class="it-prompt">
          <code>$ ./recon --passive --stealth --target=visitor</code>
        </div>
        <!-- Data rows -->
        <div class="it-body" id="itBody">
          <div class="ir"><span class="ik">IP Address</span><span class="iv loading" id="intel-ip">Scanning...</span></div>
          <div class="ir"><span class="ik">Country</span><span class="iv loading" id="intel-country">Resolving...</span></div>
          <div class="ir"><span class="ik">City / Region</span><span class="iv loading" id="intel-city">Resolving...</span></div>
          <div class="ir"><span class="ik">ISP / Network</span><span class="iv loading" id="intel-isp">Querying ASN...</span></div>
          <div class="ir"><span class="ik">Timezone</span><span class="iv loading" id="intel-timezone">Calculating...</span></div>
          <div class="ir"><span class="ik">Browser Agent</span><span class="iv" id="intel-browser">Detecting...</span></div>
          <div class="ir"><span class="ik">Operating System</span><span class="iv" id="intel-os">Detecting...</span></div>
          <div class="ir"><span class="ik">Screen / DPI</span><span class="iv" id="intel-screen">Detecting...</span></div>
        </div>
        <!-- Threat level bar -->
        <div class="it-threat">
          <div class="it-tl-label">Exposure Risk Level <span id="threatPct">0%</span></div>
          <div class="tbar"><div class="tbar-fill" id="threatBar"></div></div>
        </div>
        <!-- Footer -->
        <div class="it-foot">
          <span>RH²-SYS RECON ENGINE · PASSIVE MODE · ENCRYPTED</span>
          <span id="iTs"></span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ════════ CONTACT ════════ -->
<section id="contact">
  <div class="W">
    <div class="rv">
      <div class="sec-eyebrow">04 — Contact</div>
      <div class="sec-title-xl">
        <span class="filled">SECURE</span><br>
        <span class="outline">CONSULTATION</span>
      </div>
    </div>

    <div class="contact-grid">
      <div class="rv d1">
        <p>Ready to fortify your infrastructure? Reach out for a confidential discussion about your security posture and threat exposure.</p>
        <div class="c-details">
          <div class="cd">
            <div class="cd-ico"><svg viewBox="0 0 24 24"><path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"/><circle cx="12" cy="10" r="3"/></svg></div>
            <div class="cd-t"><span>Location</span><strong>Rajshahi Division, Bangladesh</strong></div>
          </div>
          <div class="cd">
            <div class="cd-ico"><svg viewBox="0 0 24 24"><circle cx="12" cy="12" r="10"/><polyline points="12 6 12 12 16 14"/></svg></div>
            <div class="cd-t"><span>Availability</span><strong>24 / 7 Incident Support</strong></div>
          </div>
          <div class="cd">
            <div class="cd-ico"><svg viewBox="0 0 24 24"><rect x="3" y="11" width="18" height="11" rx="2"/><path d="M7 11V7a5 5 0 0 1 10 0v4"/></svg></div>
            <div class="cd-t"><span>Channels</span><strong>Encrypted comms available on request</strong></div>
          </div>
        </div>
        <div class="c-note">All submissions are end-to-end encrypted via Firebase.</div>
      </div>

      <div class="c-form rv d2">
        <form id="cForm" novalidate>
          <div class="fg">
            <div class="fi">
              <label for="fn">Full Name / Organization</label>
              <input type="text" id="fn" name="name" placeholder="Acme Corp / Jane Doe" required autocomplete="name">
            </div>
            <div class="fi">
              <label for="fe">Work Email</label>
              <input type="email" id="fe" name="email" placeholder="security@company.com" required autocomplete="email">
            </div>
          </div>
          <div class="fi">
            <label for="fm">Project Scope / Details</label>
            <textarea id="fm" name="message" rows="5" placeholder="Describe your infrastructure and security goals..." required></textarea>
          </div>
          <button type="submit" class="fsub" id="submitBtn">TRANSMIT ENCRYPTED REQUEST</button>
        </form>
      </div>
    </div>
  </div>
</section>

<!-- ════════ FOOTER ════════ -->
<footer>
  <div class="W">
    <div class="foot-grid">
      <div class="foot-brand">
        <div class="foot-logo">RH²-<em>Systems</em></div>
        <p>Enterprise-grade cybersecurity and offensive security operations for high-risk infrastructure worldwide. 100% confidentiality guaranteed.</p>
      </div>
      <div class="foot-col">
        <h5>Services</h5>
        <ul>
          <li><a href="#services">Penetration Testing</a></li>
          <li><a href="#services">Red Team Operations</a></li>
          <li><a href="#services">Secure Engineering</a></li>
        </ul>
      </div>
      <div class="foot-col">
        <h5>Company</h5>
        <ul>
          <li><a href="#team">Our Team</a></li>
          <li><a href="#intelligence">Intel Scan</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </div>
    </div>
    <div class="foot-bottom">
      <div class="foot-copy">© 2026 RH²-SYSTEMS · ALL RIGHTS RESERVED · CONFIDENTIALITY GUARANTEED</div>
      <div class="foot-right">Rajshahi, Bangladesh · <span>Offensive Security</span></div>
    </div>
  </div>
</footer>

<script>
/* ── PRELOADER ── */
(function(){
  let p=0;
  const el=document.getElementById('prePct');
  const iv=setInterval(()=>{
    p+=Math.random()*22;
    if(p>=100){p=100;clearInterval(iv)}
    el.textContent=Math.floor(p)+'%';
  },60);
  window.addEventListener('load',()=>{
    setTimeout(()=>document.getElementById('pre').classList.add('out'),1400);
  });
})();

/* ── CURSOR ── */
(function(){
  if(window.matchMedia('(max-width:768px)').matches)return;
  const c=document.getElementById('cur');
  const dot=c.querySelector('.cur-d');
  const ring=c.querySelector('.cur-r');
  let mx=0,my=0,rx=0,ry=0;
  document.addEventListener('mousemove',e=>{mx=e.clientX;my=e.clientY});
  (function anim(){
    rx+=(mx-rx)*0.1;ry+=(my-ry)*0.1;
    dot.style.cssText=`left:${mx}px;top:${my}px`;
    ring.style.cssText=`left:${rx}px;top:${ry}px`;
    requestAnimationFrame(anim);
  })();
  document.querySelectorAll('a,button,.sc,.tc,.btn').forEach(el=>{
    el.addEventListener('mouseenter',()=>document.body.classList.add('hov'));
    el.addEventListener('mouseleave',()=>document.body.classList.remove('hov'));
  });
})();

/* ── HEADER ── */
window.addEventListener('scroll',()=>{
  document.getElementById('hdr').classList.toggle('stuck',window.scrollY>10);
  document.getElementById('stt').classList.toggle('on',window.scrollY>500);
});
document.getElementById('stt').addEventListener('click',()=>window.scrollTo({top:0,behavior:'smooth'}));

/* ── MOBILE NAV ── */
const hbtn=document.getElementById('hbtn');
const mdr=document.getElementById('mdr');
hbtn.addEventListener('click',()=>{
  const on=mdr.classList.toggle('on');
  hbtn.classList.toggle('x',on);
  hbtn.setAttribute('aria-expanded',on);
  document.body.style.overflow=on?'hidden':'';
});
document.querySelectorAll('.ml').forEach(a=>a.addEventListener('click',()=>{
  mdr.classList.remove('on');hbtn.classList.remove('x');
  hbtn.setAttribute('aria-expanded','false');
  document.body.style.overflow='';
}));

/* ── REVEAL ── */
new IntersectionObserver(
  entries=>entries.forEach(e=>{if(e.isIntersecting)e.target.classList.add('in')}),
  {threshold:0.06}
).observe||(()=>{});
const io=new IntersectionObserver(
  entries=>entries.forEach(e=>{if(e.isIntersecting)e.target.classList.add('in')}),
  {threshold:0.06}
);
document.querySelectorAll('.rv').forEach(el=>io.observe(el));

/* ── TYPEWRITER ── */
(function(){
  const words=['ENGINEERED.','UNBREAKABLE.','ADVERSARIAL.','RELENTLESS.'];
  const el=document.getElementById('typeEl');
  let wi=0,ci=0,del=false;
  (function tick(){
    const w=words[wi];
    el.textContent=del?w.substring(0,--ci):w.substring(0,++ci);
    let d=del?20:60;
    if(!del&&ci===w.length){d=2000;del=true}
    if(del&&ci===0){del=false;wi=(wi+1)%words.length}
    setTimeout(tick,d);
  })();
})();

/* ── UTC CLOCK ── */
(function(){
  function upd(){
    const t=new Date();
    document.getElementById('utcClock').textContent=
      [t.getUTCHours(),t.getUTCMinutes(),t.getUTCSeconds()]
      .map(n=>String(n).padStart(2,'0')).join(':')+' UTC';
  }
  upd();setInterval(upd,1000);
})();

/* ── PARTICLE CANVAS ── */
(function(){
  const cv=document.getElementById('heroCanvas');
  if(!cv)return;
  const ctx=cv.getContext('2d');
  const DPR=Math.min(window.devicePixelRatio||1,2);
  let W,H,pts=[];
  function resize(){
    W=cv.parentElement.offsetWidth;H=cv.parentElement.offsetHeight;
    cv.width=W*DPR;cv.height=H*DPR;
    cv.style.width=W+'px';cv.style.height=H+'px';
    ctx.scale(DPR,DPR);build();
  }
  function build(){
    pts=[];
    const n=Math.floor(W*H/9000);
    for(let i=0;i<n;i++)pts.push({
      x:Math.random()*W,y:Math.random()*H,
      vx:(Math.random()-0.5)*0.5,vy:(Math.random()-0.5)*0.5,
      r:Math.random()*1.4+0.4
    });
  }
  let mx=null,my=null;
  window.addEventListener('mousemove',e=>{mx=e.clientX;my=e.clientY});
  function draw(){
    ctx.clearRect(0,0,W,H);
    pts.forEach(p=>{
      p.x+=p.vx;p.y+=p.vy;
      if(p.x<0||p.x>W)p.vx*=-1;
      if(p.y<0||p.y>H)p.vy*=-1;
      if(mx!==null){
        const dx=p.x-mx,dy=p.y-my,d=Math.sqrt(dx*dx+dy*dy);
        if(d<100){p.x+=dx/d*1.2;p.y+=dy/d*1.2}
      }
      ctx.beginPath();ctx.arc(p.x,p.y,p.r,0,Math.PI*2);
      ctx.fillStyle='rgba(124,58,255,0.7)';ctx.fill();
    });
    for(let a=0;a<pts.length;a++){
      for(let b=a+1;b<pts.length;b++){
        const dx=pts[a].x-pts[b].x,dy=pts[a].y-pts[b].y;
        const d2=dx*dx+dy*dy,max=(W/6)*(H/6);
        if(d2<max){
          ctx.strokeStyle=`rgba(124,58,255,${(1-d2/max)*0.3})`;
          ctx.lineWidth=0.7;ctx.beginPath();
          ctx.moveTo(pts[a].x,pts[a].y);ctx.lineTo(pts[b].x,pts[b].y);ctx.stroke();
        }
      }
    }
    requestAnimationFrame(draw);
  }
  window.addEventListener('resize',resize);
  resize();draw();
})();


/* ── TEXT SCRAMBLE ── */
class Scramble {
  constructor(el) {
    this.el = el;
    this.orig = el.textContent;
    this.chars = '!<>-_\/[]{}—=+*^?#ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789';
    this.running = false;
  }
  run() {
    if (this.running) return;
    this.running = true;
    let iter = 0;
    const total = this.orig.length;
    const iv = setInterval(() => {
      this.el.textContent = this.orig.split('').map((ch, i) => {
        if (ch === ' ') return ' ';
        if (i < iter) return ch;
        return this.chars[Math.floor(Math.random() * this.chars.length)];
      }).join('');
      iter += 0.5;
      if (iter >= total) { this.el.textContent = this.orig; this.running = false; clearInterval(iv); }
    }, 30);
  }
}
// Apply to all section titles on scroll reveal
(function() {
  const targets = document.querySelectorAll('.sec-title-xl .filled, .sec-title-xl .outline');
  const scramblers = new Map();
  targets.forEach(el => scramblers.set(el, new Scramble(el)));
  const so = new IntersectionObserver(entries => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        const s = scramblers.get(e.target);
        if (s) setTimeout(() => s.run(), 100);
      }
    });
  }, { threshold: 0.5 });
  targets.forEach(el => so.observe(el));
})();

/* ── 3D TILT CARDS ── */
(function() {
  if (window.matchMedia('(max-width:768px)').matches) return;
  document.querySelectorAll('.tc, .sc').forEach(card => {
    card.addEventListener('mousemove', e => {
      const r = card.getBoundingClientRect();
      const x = e.clientX - r.left;
      const y = e.clientY - r.top;
      const cx = r.width / 2, cy = r.height / 2;
      const rotX = ((y - cy) / cy) * -10;
      const rotY = ((x - cx) / cx) * 10;
      const glowX = Math.round((x / r.width) * 100);
      const glowY = Math.round((y / r.height) * 100);
      card.style.transform = `perspective(900px) rotateX(${rotX}deg) rotateY(${rotY}deg) translateY(-6px) scale(1.02)`;
      card.style.setProperty('--gx', glowX + '%');
      card.style.setProperty('--gy', glowY + '%');
    });
    card.addEventListener('mouseleave', () => {
      card.style.transform = '';
    });
  });
})();

/* ── MAGNETIC BUTTONS ── */
(function() {
  if (window.matchMedia('(max-width:768px)').matches) return;
  document.querySelectorAll('.btn, .fsub, .nl-cta').forEach(btn => {
    btn.addEventListener('mousemove', e => {
      const r = btn.getBoundingClientRect();
      const x = e.clientX - r.left - r.width / 2;
      const y = e.clientY - r.top - r.height / 2;
      btn.style.transform = `translate(${x * 0.35}px, ${y * 0.5}px)`;
    });
    btn.addEventListener('mouseleave', () => {
      btn.style.transform = '';
      btn.style.transition = 'transform 0.5s cubic-bezier(0.175,0.885,0.32,1.275)';
      setTimeout(() => btn.style.transition = '', 500);
    });
  });
})();

/* ── PARALLAX HERO LAYERS ── */
(function() {
  if (window.matchMedia('(max-width:768px)').matches) return;
  const orbs = document.querySelectorAll('.orb-p');
  const heroVert = document.querySelector('.hero-vert');
  window.addEventListener('scroll', () => {
    const sy = window.scrollY;
    orbs.forEach((o, i) => {
      const speed = (i + 1) * 0.15;
      o.style.transform = `translateY(${sy * speed}px)`;
    });
    if (heroVert) heroVert.style.transform = `translateY(calc(-50% + ${sy * 0.2}px))`;
  });
  document.addEventListener('mousemove', e => {
    const cx = window.innerWidth / 2, cy = window.innerHeight / 2;
    const dx = (e.clientX - cx) / cx;
    const dy = (e.clientY - cy) / cy;
    orbs.forEach((o, i) => {
      const d = (i + 1) * 18;
      o.style.transform = `translate(${dx * d}px, ${dy * d}px)`;
    });
  });
})();

/* ── WAVEFORM GRAPH ── */
(function() {
  const canvas = document.getElementById('waveCanvas');
  if (!canvas) return;
  const ctx = canvas.getContext('2d');
  const DPR = Math.min(window.devicePixelRatio || 1, 2);
  let W, H, t = 0;
  const waves = [
    { amp: 22, freq: 0.018, speed: 0.032, color: 'rgba(124,58,255,0.7)', width: 2 },
    { amp: 14, freq: 0.028, speed: 0.048, color: 'rgba(168,85,247,0.5)', width: 1.5 },
    { amp: 8,  freq: 0.042, speed: 0.065, color: 'rgba(232,121,249,0.4)', width: 1 },
    { amp: 18, freq: 0.012, speed: 0.022, color: 'rgba(56,189,248,0.35)', width: 1.5 },
  ];
  // Spike data
  const spikes = Array.from({length: 28}, (_, i) => ({
    x: (i / 27),
    h: Math.random() * 0.6 + 0.1,
    hTarget: Math.random() * 0.6 + 0.1,
    speed: Math.random() * 0.04 + 0.01
  }));

  function resize() {
    W = canvas.offsetWidth; H = canvas.offsetHeight;
    canvas.width = W * DPR; canvas.height = H * DPR;
    canvas.style.width = W + 'px'; canvas.style.height = H + 'px';
    ctx.scale(DPR, DPR);
  }

  function draw() {
    ctx.clearRect(0, 0, W, H);
    t += 0.016;

    // Draw sine waves
    waves.forEach(w => {
      ctx.beginPath();
      ctx.strokeStyle = w.color;
      ctx.lineWidth = w.width;
      ctx.shadowColor = w.color;
      ctx.shadowBlur = 8;
      for (let x = 0; x <= W; x += 2) {
        const y = H / 2 + Math.sin(x * w.freq + t * w.speed * 60) * w.amp
                        + Math.sin(x * w.freq * 2.1 + t * w.speed * 40) * (w.amp * 0.3);
        x === 0 ? ctx.moveTo(x, y) : ctx.lineTo(x, y);
      }
      ctx.stroke();
      ctx.shadowBlur = 0;
    });

    // Draw bar spikes at bottom
    spikes.forEach(s => {
      s.h += (s.hTarget - s.h) * s.speed;
      if (Math.abs(s.h - s.hTarget) < 0.01) s.hTarget = Math.random() * 0.65 + 0.08;
      const bx = s.x * W;
      const bh = s.h * (H * 0.38);
      const by = H - bh;
      const grad = ctx.createLinearGradient(0, by, 0, H);
      grad.addColorStop(0, 'rgba(124,58,255,0.9)');
      grad.addColorStop(0.5, 'rgba(168,85,247,0.6)');
      grad.addColorStop(1, 'rgba(124,58,255,0.1)');
      ctx.fillStyle = grad;
      ctx.shadowColor = 'rgba(124,58,255,0.6)';
      ctx.shadowBlur = 6;
      ctx.fillRect(bx - 2, by, 4, bh);
      ctx.shadowBlur = 0;
    });

    requestAnimationFrame(draw);
  }

  window.addEventListener('resize', resize);
  resize(); draw();
})();

/* ── INTEL SCAN ── */
(function(){
  let rowsDone=0;
  function sv(id,val,isIp){
    const el=document.getElementById(id);
    if(!el)return;
    el.textContent=val||'Unknown';
    el.classList.remove('loading');
    el.classList.add('loaded');
    if(isIp)el.classList.add('hi');
    // Light up the row
    const row=el.closest('.ir');
    if(row)setTimeout(()=>row.classList.add('lit'),80);
    // Animate threat bar as data comes in
    rowsDone++;
    const pct=Math.min(Math.round((rowsDone/5)*73),73);
    const bar=document.getElementById('threatBar');
    const lbl=document.getElementById('threatPct');
    if(bar){bar.style.width=pct+'%';bar.classList.add('go')}
    if(lbl)lbl.textContent=pct+'%';
  }
  function fail(){
    ['intel-ip','intel-country','intel-city','intel-isp','intel-timezone'].forEach(id=>sv(id,'Unavailable'));
    const s=document.getElementById('scStat');
    if(s)s.innerHTML='<span class="fail">FAILED</span>';
  }
  const ua=navigator.userAgent;
  let br='Unknown',os='Unknown';
  if(/SamsungBrowser/i.test(ua))br='Samsung Internet';
  else if(/OPR|Opera/i.test(ua))br='Opera';
  else if(/Trident/i.test(ua))br='Internet Explorer';
  else if(/Edg\//i.test(ua))br='Microsoft Edge';
  else if(/Firefox\/\d/i.test(ua))br='Mozilla Firefox';
  else if(/Chrome\/\d/i.test(ua))br='Google Chrome';
  else if(/Safari\/\d/i.test(ua))br='Apple Safari';
  if(/Android/i.test(ua))os='Android';
  else if(/iPhone|iPad|iPod/i.test(ua))os='iOS';
  else if(/Windows NT 10/i.test(ua))os='Windows 10/11';
  else if(/Windows/i.test(ua))os='Windows';
  else if(/Mac OS X/i.test(ua))os='macOS';
  else if(/Linux/i.test(ua))os='Linux';
  const bEl=document.getElementById('intel-browser');
  const oEl=document.getElementById('intel-os');
  const sEl=document.getElementById('intel-screen');
  if(bEl){bEl.textContent=br;bEl.classList.add('loaded')}
  if(oEl){oEl.textContent=os;oEl.classList.add('loaded')}
  if(sEl){sEl.textContent=`${screen.width}×${screen.height} @${window.devicePixelRatio||1}x`;sEl.classList.add('loaded')}
  const ts=document.getElementById('iTs');
  if(ts)ts.textContent=new Date().toISOString().replace('T',' ').split('.')[0]+' UTC';
  const ctrl=new AbortController();
  setTimeout(()=>ctrl.abort(),8000);
  fetch('https://ipwho.is/',{signal:ctrl.signal})
    .then(r=>r.json()).then(d=>{
      if(!d.success)throw 0;
      sv('intel-ip',d.ip,true);
      sv('intel-country',`${d.country} (${d.country_code||''})`);
      sv('intel-city',`${d.city||'—'}, ${d.region||'—'}`);
      sv('intel-isp',d.connection?.isp||d.connection?.org||d.org||'Unknown');
      sv('intel-timezone',d.timezone?.id||d.timezone||'Unknown');
      const s=document.getElementById('scStat');
      if(s){s.textContent='COMPLETE';s.classList.add('ok')}
    }).catch(()=>{
      fetch('https://ipapi.co/json/',{signal:ctrl.signal})
        .then(r=>r.json()).then(d=>{
          if(d.error)throw 0;
          sv('intel-ip',d.ip,true);
          sv('intel-country',`${d.country_name} (${d.country_code})`);
          sv('intel-city',`${d.city||'—'}, ${d.region||'—'}`);
          sv('intel-isp',d.org||'Unknown');
          sv('intel-timezone',d.timezone||'Unknown');
          const s=document.getElementById('scStat');
          if(s){s.textContent='COMPLETE';s.classList.add('ok')}
        }).catch(()=>{
          fetch('https://ipinfo.io/json',{signal:ctrl.signal})
            .then(r=>r.json()).then(d=>{
              sv('intel-ip',d.ip,true);
              sv('intel-country',d.country||'Unknown');
              sv('intel-city',`${d.city||'—'}, ${d.region||'—'}`);
              sv('intel-isp',d.org||'Unknown');
              sv('intel-timezone',d.timezone||'Unknown');
              const s=document.getElementById('scStat');
              if(s){s.textContent='COMPLETE';s.classList.add('ok')}
            }).catch(fail);
        });
    });
})();

/* ══════════════════════════════════════════
   FINAL FORM — 6 ULTIMATE UPGRADES
   ══════════════════════════════════════════ */

/* ── 1. MATRIX RAIN ── */
(function(){
  const cv=document.getElementById('matrixCanvas');
  if(!cv)return;
  const ctx=cv.getContext('2d');
  const DPR=Math.min(window.devicePixelRatio||1,2);
  const chars='ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789@#$%^&*()_+-=[]{}|;:,.<>?アイウエオカキクケコサシスセソタチツテトナニヌネノ';
  let W,H,cols,drops=[];
  function resize(){
    W=cv.offsetWidth;H=cv.offsetHeight;
    cv.width=W*DPR;cv.height=H*DPR;
    cv.style.width=W+'px';cv.style.height=H+'px';
    ctx.scale(DPR,DPR);
    cols=Math.floor(W/16);
    drops=Array.from({length:cols},()=>Math.random()*-100);
  }
  function draw(){
    ctx.fillStyle='rgba(3,6,10,0.08)';
    ctx.fillRect(0,0,W,H);
    drops.forEach((y,i)=>{
      const ch=chars[Math.floor(Math.random()*chars.length)];
      const x=i*16;
      // Head char bright
      ctx.fillStyle='rgba(168,85,247,0.95)';
      ctx.font='bold 13px monospace';
      ctx.fillText(ch,x,y*16);
      // Trail
      ctx.fillStyle='rgba(124,58,255,0.45)';
      ctx.font='11px monospace';
      ctx.fillText(chars[Math.floor(Math.random()*chars.length)],x,(y-1)*16);
      ctx.fillStyle='rgba(124,58,255,0.2)';
      ctx.fillText(chars[Math.floor(Math.random()*chars.length)],x,(y-2)*16);
      if(y*16>H&&Math.random()>0.975) drops[i]=0;
      drops[i]+=0.5;
    });
  }
  window.addEventListener('resize',resize);
  resize();
  setInterval(draw,40);
})();

/* ── 2. WEBGL THREE.JS 3D OBJECT ── */
(function(){
  if(!window.THREE)return;
  const cv=document.getElementById('webglCanvas');
  if(!cv)return;
  const renderer=new THREE.WebGLRenderer({canvas:cv,alpha:true,antialias:true});
  renderer.setPixelRatio(Math.min(window.devicePixelRatio,2));
  renderer.setClearColor(0x000000,0);
  const scene=new THREE.Scene();
  const camera=new THREE.PerspectiveCamera(60,1,0.1,1000);
  camera.position.z=4.5;

  function resize(){
    const W=cv.offsetWidth,H=cv.offsetHeight;
    renderer.setSize(W,H,false);
    camera.aspect=W/H;camera.updateProjectionMatrix();
  }

  // Outer icosahedron wireframe
  const icoGeo=new THREE.IcosahedronGeometry(1.8,1);
  const icoMat=new THREE.MeshBasicMaterial({
    color:0x7c3aff,wireframe:true,transparent:true,opacity:0.25
  });
  const ico=new THREE.Mesh(icoGeo,icoMat);
  scene.add(ico);

  // Inner solid icosahedron
  const innerGeo=new THREE.IcosahedronGeometry(1.1,0);
  const innerMat=new THREE.MeshPhongMaterial({
    color:0x3b0764,emissive:0x7c3aff,emissiveIntensity:0.3,
    transparent:true,opacity:0.7,shininess:100,
    wireframe:false
  });
  const inner=new THREE.Mesh(innerGeo,innerMat);
  scene.add(inner);

  // Orbiting ring 1
  const ring1Geo=new THREE.TorusGeometry(2.4,0.008,8,80);
  const ring1Mat=new THREE.MeshBasicMaterial({color:0xa855f7,transparent:true,opacity:0.5});
  const ring1=new THREE.Mesh(ring1Geo,ring1Mat);
  ring1.rotation.x=Math.PI/3;
  scene.add(ring1);

  // Orbiting ring 2
  const ring2Geo=new THREE.TorusGeometry(2.8,0.005,8,80);
  const ring2Mat=new THREE.MeshBasicMaterial({color:0xe879f9,transparent:true,opacity:0.3});
  const ring2=new THREE.Mesh(ring2Geo,ring2Mat);
  ring2.rotation.x=Math.PI/5;ring2.rotation.z=Math.PI/4;
  scene.add(ring2);

  // Particle cloud
  const pGeo=new THREE.BufferGeometry();
  const pCount=280;
  const pPos=new Float32Array(pCount*3);
  for(let i=0;i<pCount*3;i++) pPos[i]=(Math.random()-0.5)*7;
  pGeo.setAttribute('position',new THREE.BufferAttribute(pPos,3));
  const pMat=new THREE.PointsMaterial({color:0x7c3aff,size:0.04,transparent:true,opacity:0.7});
  const particles=new THREE.Points(pGeo,pMat);
  scene.add(particles);

  // Lights
  const aLight=new THREE.AmbientLight(0x7c3aff,0.4);
  scene.add(aLight);
  const pLight=new THREE.PointLight(0xa855f7,2,10);
  pLight.position.set(3,3,3);scene.add(pLight);
  const pLight2=new THREE.PointLight(0xe879f9,1.5,10);
  pLight2.position.set(-3,-2,2);scene.add(pLight2);

  let mx=0,my=0;
  document.addEventListener('mousemove',e=>{
    mx=(e.clientX/window.innerWidth-0.5)*2;
    my=(e.clientY/window.innerHeight-0.5)*2;
  });

  let t=0;
  function animate(){
    requestAnimationFrame(animate);
    t+=0.008;
    ico.rotation.y+=0.004;
    ico.rotation.x+=0.002;
    inner.rotation.y-=0.006;
    inner.rotation.z+=0.003;
    ring1.rotation.z+=0.006;
    ring2.rotation.y+=0.004;
    particles.rotation.y+=0.001;
    // Mouse parallax
    scene.rotation.y+=(mx*0.3-scene.rotation.y)*0.05;
    scene.rotation.x+=(-my*0.2-scene.rotation.x)*0.05;
    // Pulse emissive
    innerMat.emissiveIntensity=0.2+Math.sin(t*2)*0.15;
    pLight.intensity=1.5+Math.sin(t*3)*0.8;
    renderer.render(scene,camera);
  }
  window.addEventListener('resize',resize);
  resize();animate();
  // Position canvas inside hero only
  cv.style.right='0';cv.style.left='auto';cv.style.width='55%';
})();

/* ── 3. SCROLL-DRIVEN CLIP-PATH WIPES ── */
(function(){
  const wipes=document.querySelectorAll('.rv.wipe');
  const wo=new IntersectionObserver(entries=>{
    entries.forEach(e=>{
      if(e.isIntersecting) e.target.classList.add('in');
    });
  },{threshold:0.08});
  wipes.forEach(el=>wo.observe(el));

  // Section bg wipe overlays
  document.querySelectorAll('section').forEach((sec,i)=>{
    const overlay=document.createElement('div');
    overlay.style.cssText=`
      position:absolute;inset:0;z-index:99;pointer-events:none;
      background:var(--ink);
      clip-path:inset(0 0 0 0);
      transition:clip-path 1.2s cubic-bezier(0.16,1,0.3,1) ${i*0.05}s
    `;
    overlay.classList.add('sec-wipe-overlay');
    sec.style.position='relative';
    sec.style.overflow='hidden';
    sec.appendChild(overlay);
  });
  const so=new IntersectionObserver(entries=>{
    entries.forEach(e=>{
      if(e.isIntersecting){
        const ov=e.target.querySelector('.sec-wipe-overlay');
        if(ov) ov.style.clipPath='inset(0 0 100% 0)';
      }
    });
  },{threshold:0.05});
  document.querySelectorAll('section').forEach(s=>so.observe(s));
})();

/* ── 4. CLICK RIPPLE EXPLOSION ── */
(function(){
  document.addEventListener('click',e=>{
    // Skip if clicking interactive elements
    if(e.target.closest('a,button,input,textarea')) return;
    const size=Math.max(window.innerWidth,window.innerHeight)*0.5;
    // Ring ripple
    const r=document.createElement('div');
    r.className='ripple';
    r.style.cssText=`left:${e.clientX}px;top:${e.clientY}px;width:${size}px;height:${size}px`;
    document.body.appendChild(r);
    // Glow ripple
    const r2=document.createElement('div');
    r2.className='ripple2';
    r2.style.cssText=`left:${e.clientX}px;top:${e.clientY}px;width:${size*1.5}px;height:${size*1.5}px`;
    document.body.appendChild(r2);
    // Inner fast ripple
    const r3=document.createElement('div');
    r3.className='ripple';
    r3.style.cssText=`left:${e.clientX}px;top:${e.clientY}px;width:${size*0.4}px;height:${size*0.4}px;border-color:var(--gold);animation-duration:0.5s`;
    document.body.appendChild(r3);
    setTimeout(()=>{r.remove();r2.remove();r3.remove();},1300);
    // Sound
    if(window._sfx&&window._sfx.enabled) window._sfx.click();
  });
})();

/* ── 5. UI TERMINAL SOUND EFFECTS ── */
(function(){
  const AudioCtx=window.AudioContext||window.webkitAudioContext;
  if(!AudioCtx)return;
  let ctx=null;
  let enabled=false;
  const btn=document.getElementById('soundBtn');

  function getCtx(){
    if(!ctx) ctx=new AudioCtx();
    return ctx;
  }

  function beep(freq=440,dur=0.08,vol=0.05,type='square',delay=0){
    try{
      const ac=getCtx();
      const osc=ac.createOscillator();
      const gain=ac.createGain();
      osc.connect(gain);gain.connect(ac.destination);
      osc.type=type;osc.frequency.setValueAtTime(freq,ac.currentTime+delay);
      gain.gain.setValueAtTime(0,ac.currentTime+delay);
      gain.gain.linearRampToValueAtTime(vol,ac.currentTime+delay+0.01);
      gain.gain.exponentialRampToValueAtTime(0.001,ac.currentTime+delay+dur);
      osc.start(ac.currentTime+delay);
      osc.stop(ac.currentTime+delay+dur+0.01);
    }catch(e){}
  }

  window._sfx={
    enabled:false,
    click(){ beep(800,0.06,0.04,'square');beep(1200,0.04,0.02,'square',0.05); },
    hover(){ beep(600,0.03,0.015,'sine'); },
    scan(){ 
      [0,0.08,0.16,0.24].forEach((d,i)=>beep(200+i*180,0.07,0.03,'sawtooth',d));
    },
    success(){
      beep(523,0.1,0.05,'sine');beep(659,0.1,0.05,'sine',0.12);
      beep(784,0.2,0.05,'sine',0.24);
    },
    glitch(){
      for(let i=0;i<5;i++) beep(Math.random()*800+100,0.03,0.02,'square',i*0.04);
    },
    type(){ beep(300+Math.random()*200,0.02,0.01,'square'); }
  };

  if(btn){
    btn.addEventListener('click',()=>{
      enabled=!enabled;
      window._sfx.enabled=enabled;
      btn.textContent=enabled?'🔊':'🔇';
      btn.classList.toggle('active',enabled);
      if(enabled){ getCtx();window._sfx.scan(); }
    });
  }

  // Attach sounds to interactions
  document.querySelectorAll('a,button').forEach(el=>{
    el.addEventListener('mouseenter',()=>{ if(window._sfx.enabled) window._sfx.hover(); });
    el.addEventListener('click',()=>{ if(window._sfx.enabled) window._sfx.click(); });
  });

  // Typewriter sound
  const typeOrig=window._typeCallback;
  document.addEventListener('keydown',()=>{ if(window._sfx.enabled) window._sfx.type(); });

  // Scan complete sound
  const origFail=window._sfx.fail;
  const scStatObs=new MutationObserver(()=>{
    const el=document.getElementById('scStat');
    if(el&&el.textContent==='COMPLETE'&&window._sfx.enabled) window._sfx.success();
  });
  const scEl=document.getElementById('scStat');
  if(scEl) scStatObs.observe(scEl,{childList:true,characterData:true,subtree:true});

  // Preloader done sound
  const preEl=document.getElementById('pre');
  if(preEl){
    new MutationObserver(()=>{
      if(preEl.classList.contains('out')&&window._sfx.enabled) window._sfx.success();
    }).observe(preEl,{attributes:true,attributeFilter:['class']});
  }
})();

</script>

<!-- FIREBASE -->
<script type="module">
import{initializeApp}from"https://www.gstatic.com/firebasejs/12.9.0/firebase-app.js";
import{getFirestore,collection,addDoc}from"https://www.gstatic.com/firebasejs/12.9.0/firebase-firestore.js";
const app=initializeApp({
  apiKey:"AIzaSyBl4bO6hNumDov3d26YNFj1y7Id498rBTU",
  authDomain:"rh2-systems.firebaseapp.com",
  projectId:"rh2-systems",
  storageBucket:"rh2-systems.firebasestorage.app",
  messagingSenderId:"492917852953",
  appId:"1:492917852953:web:9fc6ff86f6fcd2fc965388"
});
const db=getFirestore(app);
const ov=document.getElementById('sov');
document.getElementById('closeSov').addEventListener('click',()=>ov.classList.remove('on'));
ov.addEventListener('click',e=>{if(e.target===ov)ov.classList.remove('on')});
const form=document.getElementById('cForm');
const btn=document.getElementById('submitBtn');
form.addEventListener('submit',async e=>{
  e.preventDefault();
  const name=document.getElementById('fn').value.trim();
  const email=document.getElementById('fe').value.trim();
  const message=document.getElementById('fm').value.trim();
  if(!name||!email||!message)return;
  btn.textContent='ENCRYPTING...';btn.disabled=true;
  try{
    await addDoc(collection(db,'messages'),{name,email,message,timestamp:new Date(),source:'rh2-systems.com'});
    form.reset();ov.classList.add('on');
  }catch(err){
    alert('Error: '+err.message);
  }finally{
    btn.textContent='TRANSMIT ENCRYPTED REQUEST';btn.disabled=false;
  }
});
</script>
</body>
</html>
