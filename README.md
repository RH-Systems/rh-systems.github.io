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
<link rel="icon" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 32 32'><rect width='32' height='32' fill='%2300ff88' rx='3'/><text y='23' x='3' font-size='18' font-family='monospace' fill='%23000' font-weight='900'>R²</text></svg>">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Outfit:wght@300;400;500;600&family=Share+Tech+Mono&display=swap" rel="stylesheet">
<style>
/* =============================================
   DESIGN TOKENS
============================================= */
:root {
  --bg:         #020508;
  --bg2:        #050c10;
  --bg3:        #081218;
  --bg4:        #0a1820;
  --green:      #00ff88;
  --green2:     #00cc6a;
  --red:        #ff2244;
  --orange:     #ff6600;
  --blue:       #0088ff;
  --g-green:    rgba(0,255,136,0.18);
  --g-red:      rgba(255,34,68,0.15);
  --g-blue:     rgba(0,136,255,0.12);
  --text:       #c8dde8;
  --text2:      #e8f4ff;
  --muted:      #3a5060;
  --muted2:     #6a8898;
  --border:     rgba(0,255,136,0.08);
  --border2:    rgba(0,255,136,0.22);
  --border3:    rgba(0,255,136,0.45);
  --ff-hud:     'Orbitron', sans-serif;
  --ff-body:    'Outfit', sans-serif;
  --ff-mono:    'Share Tech Mono', monospace;
  --r:          4px;
  --ease:       cubic-bezier(0.4,0,0.2,1);
}

/* =============================================
   BASE
============================================= */
*,*::before,*::after{margin:0;padding:0;box-sizing:border-box;-webkit-tap-highlight-color:transparent}
html{scroll-behavior:smooth}
body{background:var(--bg);color:var(--text);font-family:var(--ff-body);font-size:1rem;line-height:1.7;overflow-x:hidden;cursor:none}
a{text-decoration:none;color:inherit}
ul{list-style:none}
button{cursor:none;border:none;background:none;font-family:inherit}
img{display:block;max-width:100%}

/* =============================================
   CUSTOM CURSOR
============================================= */
#cursor{position:fixed;top:0;left:0;z-index:99999;pointer-events:none}
.cursor-ring{
  position:absolute;
  width:36px;height:36px;
  border:1.5px solid var(--green);
  border-radius:50%;
  transform:translate(-50%,-50%);
  transition:width 0.2s,height 0.2s,border-color 0.2s,opacity 0.2s;
  box-shadow:0 0 10px var(--g-green);
}
.cursor-dot{
  position:absolute;
  width:5px;height:5px;
  background:var(--green);
  border-radius:50%;
  transform:translate(-50%,-50%);
  box-shadow:0 0 8px var(--green);
}
body.cursor-hover .cursor-ring{width:56px;height:56px;border-color:var(--green);opacity:0.6}

/* =============================================
   NOISE + SCANLINES
============================================= */
body::before{
  content:'';position:fixed;inset:0;
  background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.85' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E");
  opacity:0.028;pointer-events:none;z-index:9997
}
body::after{
  content:'';position:fixed;inset:0;
  background:repeating-linear-gradient(0deg,transparent,transparent 2px,rgba(0,255,136,0.012) 2px,rgba(0,255,136,0.012) 4px);
  pointer-events:none;z-index:9996;animation:scanlines 8s linear infinite
}
@keyframes scanlines{from{background-position:0 0}to{background-position:0 -400px}}

/* =============================================
   PRELOADER
============================================= */
#preloader{
  position:fixed;inset:0;z-index:99998;
  background:var(--bg);
  display:flex;flex-direction:column;align-items:center;justify-content:center;gap:32px;
  transition:opacity 0.8s var(--ease),visibility 0.8s var(--ease)
}
#preloader.out{opacity:0;visibility:hidden}
.pre-logo{
  font-family:var(--ff-hud);font-size:3.5rem;font-weight:900;
  color:var(--green);letter-spacing:0.1em;
  text-shadow:0 0 60px var(--g-green),0 0 120px rgba(0,255,136,0.08);
  animation:preLogoPulse 0.6s ease-in-out infinite alternate
}
@keyframes preLogoPulse{from{opacity:0.5;filter:blur(1px)}to{opacity:1;filter:blur(0)}}
.pre-status{font-family:var(--ff-mono);font-size:0.75rem;color:var(--muted2);letter-spacing:0.15em;text-transform:uppercase}
.pre-bar{width:260px;height:2px;background:rgba(0,255,136,0.1);border-radius:2px;overflow:hidden}
.pre-fill{height:100%;background:linear-gradient(90deg,var(--green2),var(--green));box-shadow:0 0 12px var(--green);animation:preFill 1.4s var(--ease) forwards}
@keyframes preFill{from{width:0}to{width:100%}}
.pre-pct{font-family:var(--ff-mono);font-size:2rem;font-weight:700;color:var(--green);text-shadow:0 0 30px var(--g-green)}

/* =============================================
   SCROLL-TO-TOP
============================================= */
#stt{
  position:fixed;bottom:32px;right:32px;z-index:500;
  width:48px;height:48px;border-radius:50%;
  background:var(--bg3);border:1px solid var(--border2);
  color:var(--green);display:flex;align-items:center;justify-content:center;
  font-size:1.1rem;opacity:0;pointer-events:none;
  transition:opacity 0.3s,transform 0.3s,box-shadow 0.3s;
  box-shadow:0 0 20px var(--g-green);cursor:none
}
#stt.show{opacity:1;pointer-events:all}
#stt:hover{transform:translateY(-4px);box-shadow:0 0 40px var(--g-green)}

/* =============================================
   LAYOUT
============================================= */
.wrap{width:min(1280px,92%);margin:auto}
section{padding:130px 0;position:relative}

/* =============================================
   TYPOGRAPHY
============================================= */
.eyebrow{
  font-family:var(--ff-mono);font-size:0.7rem;letter-spacing:0.25em;
  text-transform:uppercase;color:var(--green);
  display:inline-flex;align-items:center;gap:12px;margin-bottom:1.2rem
}
.eyebrow::before{content:'';width:32px;height:1px;background:var(--green);box-shadow:0 0 8px var(--green)}
.eyebrow::after{content:'';width:8px;height:1px;background:var(--green);opacity:0.4}

.stitle{
  font-family:var(--ff-hud);font-size:clamp(2.2rem,4.5vw,3.6rem);
  font-weight:900;letter-spacing:0.06em;line-height:1.05;
  color:var(--text2);margin-bottom:1rem
}
.stitle .hl{color:var(--green);text-shadow:0 0 30px var(--g-green)}
.stitle .hl-red{color:var(--red);text-shadow:0 0 30px var(--g-red)}
.sdesc{color:var(--muted2);max-width:500px;font-size:0.98rem}

/* =============================================
   BUTTONS
============================================= */
.btn{
  display:inline-flex;align-items:center;gap:10px;
  padding:14px 32px;border-radius:var(--r);
  font-family:var(--ff-mono);font-size:0.78rem;
  letter-spacing:0.12em;text-transform:uppercase;
  transition:all 0.3s var(--ease);position:relative;overflow:hidden;
  cursor:none
}
.btn-g{
  background:var(--green);color:#010608;
  box-shadow:0 0 30px var(--g-green),inset 0 1px 0 rgba(255,255,255,0.2)
}
.btn-g::before{
  content:'';position:absolute;inset:0;
  background:linear-gradient(135deg,rgba(255,255,255,0.2) 0%,transparent 60%);
  opacity:0
}
.btn-g:hover{transform:translateY(-3px);box-shadow:0 16px 50px var(--g-green),0 0 60px rgba(0,255,136,0.15)}
.btn-g:hover::before{opacity:1}
.btn-o{
  background:transparent;color:var(--text2);
  border:1px solid rgba(255,255,255,0.12)
}
.btn-o:hover{border-color:var(--green);color:var(--green);box-shadow:0 0 20px var(--g-green);transform:translateY(-3px)}
.btn-sm{padding:10px 22px;font-size:0.7rem}

/* =============================================
   HEADER
============================================= */
header{
  position:fixed;top:0;left:0;right:0;z-index:1000;
  height:72px;transition:all 0.4s var(--ease)
}
header.sticky{
  background:rgba(2,5,8,0.95);
  backdrop-filter:blur(30px);-webkit-backdrop-filter:blur(30px);
  border-bottom:1px solid var(--border)
}
nav{height:100%;display:flex;align-items:center;justify-content:space-between}
.logo{
  font-family:var(--ff-hud);font-size:1.45rem;font-weight:900;
  letter-spacing:0.08em;color:var(--text2);position:relative
}
.logo em{font-style:normal;color:var(--green);text-shadow:0 0 20px var(--g-green)}
.logo-badge{
  position:absolute;top:-8px;right:-28px;
  font-family:var(--ff-mono);font-size:0.48rem;
  letter-spacing:0.12em;color:var(--green);
  background:rgba(0,255,136,0.08);border:1px solid rgba(0,255,136,0.25);
  border-radius:2px;padding:2px 5px
}

.navlinks{display:flex;align-items:center;gap:32px}
.navlinks a{
  font-family:var(--ff-mono);font-size:0.7rem;
  letter-spacing:0.1em;text-transform:uppercase;color:var(--muted2);
  transition:color 0.25s;position:relative;padding-bottom:2px
}
.navlinks a::after{
  content:'';position:absolute;bottom:0;left:0;right:100%;
  height:1px;background:var(--green);
  transition:right 0.3s var(--ease)
}
.navlinks a:hover{color:var(--green)}
.navlinks a:hover::after{right:0}

.hbg{display:none;flex-direction:column;gap:5px;padding:6px;cursor:none}
.hbg span{display:block;width:26px;height:2px;background:var(--text);border-radius:2px;transition:all 0.3s var(--ease)}
.hbg.on span:nth-child(1){transform:translateY(7px) rotate(45deg);background:var(--green)}
.hbg.on span:nth-child(2){opacity:0;transform:scaleX(0)}
.hbg.on span:nth-child(3){transform:translateY(-7px) rotate(-45deg);background:var(--green)}

.mob-drawer{
  display:none;position:fixed;
  top:72px;left:0;right:0;bottom:0;
  background:rgba(2,5,8,0.98);backdrop-filter:blur(30px);-webkit-backdrop-filter:blur(30px);
  flex-direction:column;align-items:center;justify-content:center;gap:44px;
  opacity:0;pointer-events:none;transform:translateY(-10px);
  transition:opacity 0.35s,transform 0.35s;z-index:999
}
.mob-drawer.on{opacity:1;pointer-events:all;transform:translateY(0)}
.mob-drawer a{
  font-family:var(--ff-hud);font-size:2rem;font-weight:700;
  letter-spacing:0.12em;color:var(--text2);transition:color 0.25s,text-shadow 0.25s
}
.mob-drawer a:hover{color:var(--green);text-shadow:0 0 30px var(--g-green)}

/* =============================================
   HERO
============================================= */
.hero{
  min-height:100dvh;display:flex;align-items:center;justify-content:center;
  text-align:center;padding-top:72px;overflow:hidden;position:relative
}

/* HEX GRID BG */
#hexCanvas{position:absolute;inset:0;width:100%;height:100%;opacity:0.35;pointer-events:none;z-index:0}

/* CORNER BRACKETS */
.corner{position:absolute;width:50px;height:50px;pointer-events:none}
.corner svg{width:100%;height:100%}
.c-tl{top:90px;left:20px}
.c-tr{top:90px;right:20px;transform:scaleX(-1)}
.c-bl{bottom:20px;left:20px;transform:scaleY(-1)}
.c-br{bottom:20px;right:20px;transform:scale(-1)}

/* GLOW ORBS */
.orb{position:absolute;border-radius:50%;pointer-events:none;filter:blur(1px)}
.orb-a{width:600px;height:600px;top:50%;left:50%;transform:translate(-50%,-50%);background:radial-gradient(circle,rgba(0,255,136,0.06),transparent 65%)}
.orb-b{width:400px;height:400px;bottom:-100px;right:-100px;background:radial-gradient(circle,rgba(255,34,68,0.06),transparent 65%)}
.orb-c{width:300px;height:300px;top:100px;left:-100px;background:radial-gradient(circle,rgba(0,136,255,0.05),transparent 65%)}

.hero-inner{position:relative;z-index:2;max-width:1000px;width:100%;padding:0 24px}

/* LIVE STATUS ROW */
.hero-status{
  display:inline-flex;align-items:center;gap:20px;
  margin-bottom:2.5rem;font-family:var(--ff-mono);font-size:0.68rem;letter-spacing:0.16em;
  flex-wrap:wrap;justify-content:center
}
.status-chip{
  display:flex;align-items:center;gap:8px;
  padding:6px 16px;border-radius:99px;
  background:rgba(0,255,136,0.05);border:1px solid rgba(0,255,136,0.2);
  color:var(--green);box-shadow:0 0 20px rgba(0,255,136,0.1)
}
.pdot{width:7px;height:7px;border-radius:50%;background:var(--green);box-shadow:0 0 8px var(--green);animation:pd 2s ease infinite}
@keyframes pd{0%,100%{opacity:1;transform:scale(1)}50%{opacity:0.25;transform:scale(0.5)}}
.status-divider{width:1px;height:18px;background:var(--muted);opacity:0.4}
.status-threat{color:var(--red);opacity:0.8}

/* HERO HEADLINE */
.hero-h1{
  font-family:var(--ff-hud);font-weight:900;
  font-size:clamp(3rem,8.5vw,7.5rem);
  line-height:0.95;letter-spacing:0.04em;
  color:var(--text2);margin-bottom:1.8rem;
  position:relative
}
.hero-h1 .l1{display:block;animation:fadeUp 0.9s 0.4s both}
.hero-h1 .l2{
  display:block;
  background:linear-gradient(90deg,var(--green) 0%,#00ffaa 40%,var(--green) 80%);
  background-size:200% auto;
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
  text-shadow:none;
  animation:fadeUp 0.9s 0.55s both,gradShift 4s linear infinite
}
@keyframes gradShift{to{background-position:200% center}}
.hero-h1 .l3{
  display:block;font-size:0.5em;letter-spacing:0.3em;
  color:var(--red);text-shadow:0 0 40px var(--g-red);
  animation:fadeUp 0.9s 0.7s both
}

/* GLITCH on .l1 */
.hero-h1 .l1{animation:fadeUp 0.9s 0.4s both}
.hero-h1 .l1:hover{animation:glitch 0.4s steps(2) forwards}
@keyframes glitch{
  0%{text-shadow:none;transform:none}
  20%{text-shadow:-3px 0 var(--red),3px 0 var(--blue);transform:translateX(-2px)}
  40%{text-shadow:3px 0 var(--red),-3px 0 var(--blue);transform:translateX(2px)}
  60%{text-shadow:-2px 0 var(--green);transform:translateX(-1px)}
  80%{text-shadow:2px 0 var(--red);transform:translateX(1px)}
  100%{text-shadow:none;transform:none}
}

.hero-sub{
  max-width:580px;margin:0 auto 3rem;
  color:var(--muted2);font-size:1.08rem;
  animation:fadeUp 0.9s 0.85s both
}
.hero-btns{display:flex;gap:16px;justify-content:center;flex-wrap:wrap;animation:fadeUp 0.9s 1s both}

/* SCROLL WORM */
.scroll-worm{
  position:absolute;bottom:36px;left:50%;transform:translateX(-50%);
  display:flex;flex-direction:column;align-items:center;gap:8px;
  font-family:var(--ff-mono);font-size:0.6rem;letter-spacing:0.2em;
  text-transform:uppercase;color:var(--muted);z-index:2;
  animation:fadeUp 0.9s 1.4s both
}
.worm-outer{width:22px;height:36px;border:1.5px solid var(--muted);border-radius:11px;display:flex;justify-content:center;padding-top:5px}
.worm-inner{width:3px;height:8px;background:var(--green);border-radius:2px;box-shadow:0 0 6px var(--green);animation:worm 2s ease-in-out infinite}
@keyframes worm{0%,100%{transform:translateY(0);opacity:1}80%{transform:translateY(14px);opacity:0}}

/* =============================================
   SERVICES
============================================= */
#services{background:var(--bg)}

/* Diagonal separator */
#services::before{
  content:'';position:absolute;top:0;left:0;right:0;
  height:120px;
  background:linear-gradient(180deg,var(--bg2) 0%,transparent 100%);
  clip-path:polygon(0 0,100% 0,100% 40%,0 100%)
}

.svc-head{display:grid;grid-template-columns:1fr 1fr;gap:40px;align-items:end;margin-bottom:70px}

.svc-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:1px;background:var(--border);border:1px solid var(--border);border-radius:10px;overflow:hidden}

.sc{
  background:var(--bg2);padding:44px 36px;
  position:relative;overflow:hidden;
  transition:background 0.35s var(--ease);
  group:true
}
.sc::after{
  content:'';position:absolute;
  bottom:0;left:0;right:0;height:0;
  background:linear-gradient(to top,rgba(0,255,136,0.04),transparent);
  transition:height 0.4s var(--ease)
}
.sc:hover{background:#081420}
.sc:hover::after{height:100%}

/* Top accent bar */
.sc-bar{
  position:absolute;top:0;left:0;right:100%;height:2px;
  background:linear-gradient(90deg,var(--green),transparent);
  transition:right 0.5s var(--ease)
}
.sc:hover .sc-bar{right:0}

/* Icon */
.sc-icon{
  width:56px;height:56px;border-radius:8px;
  background:rgba(0,255,136,0.04);
  border:1px solid var(--border);
  display:flex;align-items:center;justify-content:center;
  margin-bottom:1.8rem;
  transition:border-color 0.3s,box-shadow 0.3s,background 0.3s;
  position:relative;z-index:1
}
.sc:hover .sc-icon{
  border-color:rgba(0,255,136,0.3);
  box-shadow:0 0 24px var(--g-green);
  background:rgba(0,255,136,0.06)
}
.sc-icon svg{width:26px;height:26px;stroke:var(--green);fill:none;stroke-width:1.6;stroke-linecap:round;stroke-linejoin:round}

.sc-num{font-family:var(--ff-mono);font-size:0.6rem;letter-spacing:0.22em;color:var(--muted);margin-bottom:0.9rem;position:relative;z-index:1}
.sc h3{font-family:var(--ff-hud);font-size:1.15rem;font-weight:700;letter-spacing:0.06em;color:var(--text2);margin-bottom:0.9rem;position:relative;z-index:1}
.sc p{color:var(--muted2);font-size:0.89rem;line-height:1.75;position:relative;z-index:1}

/* =============================================
   THREAT COUNTER
============================================= */
.threat-band{
  background:var(--bg3);
  border-top:1px solid var(--border);border-bottom:1px solid var(--border);
  padding:0;overflow:hidden;position:relative
}
.threat-band::before{
  content:'';position:absolute;top:0;left:0;right:0;height:1px;
  background:linear-gradient(90deg,transparent,var(--green),transparent)
}
.threat-ticker{
  display:flex;align-items:center;gap:0;
  animation:tickerRoll 30s linear infinite;
  white-space:nowrap
}
@keyframes tickerRoll{from{transform:translateX(0)}to{transform:translateX(-50%)}}
.tt-item{
  display:inline-flex;align-items:center;gap:10px;
  padding:16px 40px;
  font-family:var(--ff-mono);font-size:0.72rem;letter-spacing:0.12em;
  color:var(--muted2);border-right:1px solid var(--border)
}
.tt-item .dot{width:6px;height:6px;border-radius:50%}
.dot-g{background:var(--green);box-shadow:0 0 8px var(--green)}
.dot-r{background:var(--red);box-shadow:0 0 8px var(--red)}
.dot-o{background:var(--orange);box-shadow:0 0 8px var(--orange)}
.tt-val{color:var(--green);font-weight:700}
.tt-val.red{color:var(--red)}
.tt-val.org{color:var(--orange)}

/* =============================================
   STATS
============================================= */
#methodology{background:var(--bg2);overflow:hidden;position:relative}
#methodology::before{
  content:'';position:absolute;top:50%;left:-200px;transform:translateY(-50%);
  width:500px;height:500px;border-radius:50%;
  background:radial-gradient(circle,rgba(0,255,136,0.04),transparent 70%);
  pointer-events:none
}

.stats-grid{
  display:grid;grid-template-columns:repeat(4,1fr);gap:1px;
  background:var(--border);border:1px solid var(--border);
  border-radius:12px;overflow:hidden;margin-top:4rem
}
.sg{
  background:var(--bg3);padding:48px 32px;
  text-align:center;position:relative;overflow:hidden;
  transition:background 0.3s
}
.sg:hover{background:var(--bg4)}
.sg::before{
  content:'';position:absolute;bottom:0;left:0;right:0;height:2px;
  background:linear-gradient(90deg,transparent,var(--green),transparent);
  opacity:0;transition:opacity 0.3s
}
.sg:hover::before{opacity:1}
.sg-val{
  font-family:var(--ff-hud);font-weight:900;
  font-size:clamp(2.8rem,4.5vw,4rem);
  letter-spacing:0.06em;color:var(--green);
  line-height:1;margin-bottom:10px;
  text-shadow:0 0 50px var(--g-green);
  position:relative
}
.sg-val .counter-num{display:inline-block}
.sg-label{color:var(--muted2);font-size:0.88rem;font-family:var(--ff-mono);letter-spacing:0.1em;text-transform:uppercase;font-size:0.7rem}

/* =============================================
   TEAM
============================================= */
#team{background:var(--bg);position:relative;overflow:hidden}

/* Diagonal top */
#team::before{
  content:'';position:absolute;top:0;left:0;right:0;height:80px;
  background:var(--bg2);clip-path:polygon(0 0,100% 0,100% 0,0 100%)
}

.team-intro{text-align:center;margin-bottom:64px}
.team-intro .sdesc{margin:0 auto}

.team-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:30px}

.tc{
  border:1px solid var(--border);border-radius:14px;overflow:hidden;
  background:var(--bg2);
  transition:border-color 0.35s,box-shadow 0.35s,transform 0.35s;
  position:relative
}
.tc:hover{
  border-color:var(--border3);
  box-shadow:0 0 50px rgba(0,255,136,0.08),0 30px 60px rgba(0,0,0,0.4);
  transform:translateY(-6px)
}

/* Card glow on hover */
.tc::before{
  content:'';position:absolute;inset:0;border-radius:14px;
  background:radial-gradient(ellipse 80% 60% at 50% 0%,rgba(0,255,136,0.04),transparent 60%);
  opacity:0;transition:opacity 0.35s
}
.tc:hover::before{opacity:1}

.tc-head{
  padding:44px 36px;
  background:linear-gradient(150deg,#060f16,#030a0f);
  border-bottom:1px solid var(--border);
  display:flex;align-items:center;gap:24px;
  position:relative;overflow:hidden
}
/* Animated circuit lines top-right */
.tc-head::after{
  content:'';position:absolute;top:-20px;right:-20px;
  width:120px;height:120px;
  border:1px solid rgba(0,255,136,0.06);border-radius:50%;
  box-shadow:0 0 0 20px rgba(0,255,136,0.03),0 0 0 40px rgba(0,255,136,0.015)
}

.av{
  width:80px;height:80px;border-radius:50%;flex-shrink:0;
  background:linear-gradient(135deg,#0a1c24,var(--bg));
  border:2px solid rgba(0,255,136,0.3);
  display:flex;align-items:center;justify-content:center;
  font-family:var(--ff-hud);font-size:1.3rem;font-weight:900;
  letter-spacing:0.06em;color:var(--green);
  box-shadow:0 0 30px var(--g-green),inset 0 0 20px rgba(0,255,136,0.04);
  position:relative;z-index:1
}
.av::after{
  content:'';position:absolute;inset:-4px;border-radius:50%;
  border:1px solid rgba(0,255,136,0.12);
  animation:avRotate 8s linear infinite
}
@keyframes avRotate{from{transform:rotate(0deg);border-color:rgba(0,255,136,0.12)}50%{border-color:rgba(0,255,136,0.3)}to{transform:rotate(360deg);border-color:rgba(0,255,136,0.12)}}

.tc-meta{position:relative;z-index:1}
.tc-meta h3{font-family:var(--ff-hud);font-size:1.8rem;font-weight:900;letter-spacing:0.06em;color:var(--text2);line-height:1;margin-bottom:6px}
.tc-role{font-family:var(--ff-mono);font-size:0.68rem;letter-spacing:0.15em;text-transform:uppercase;color:var(--green)}

.tc-body{padding:32px 36px}
.tc-body p{color:var(--muted2);font-size:0.92rem;margin-bottom:1.6rem;line-height:1.8}
.tc-tags{display:flex;flex-wrap:wrap;gap:8px;margin-bottom:2rem}
.ttag{
  font-family:var(--ff-mono);font-size:0.65rem;letter-spacing:0.08em;
  padding:5px 14px;border-radius:2px;
  border:1px solid var(--border);color:var(--muted2);
  transition:border-color 0.25s,color 0.25s,background 0.25s
}
.tc:hover .ttag{border-color:rgba(0,255,136,0.16);color:var(--text)}

.tc-link{
  display:inline-flex;align-items:center;gap:8px;
  font-family:var(--ff-mono);font-size:0.7rem;letter-spacing:0.12em;text-transform:uppercase;
  color:var(--green);transition:gap 0.25s
}
.tc-link:hover{gap:14px}
.tc-link svg{width:14px;height:14px;stroke:currentColor;fill:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round}

/* =============================================
   INTEL SCAN
============================================= */
#intelligence{background:var(--bg2);position:relative;overflow:hidden}
#intelligence::before{
  content:'';position:absolute;top:50%;right:-200px;transform:translateY(-50%);
  width:500px;height:500px;border-radius:50%;
  background:radial-gradient(circle,rgba(0,136,255,0.04),transparent 70%);
  pointer-events:none
}

.intel-wrap{max-width:880px;margin:4rem auto 0}

/* HUD FRAME */
.hud-frame{
  position:relative;
  border:1px solid var(--border2);border-radius:12px;
  background:linear-gradient(180deg,#030912,#020710);
  box-shadow:0 0 60px rgba(0,255,136,0.05),inset 0 0 60px rgba(0,0,0,0.5);
  overflow:hidden
}
/* Corner accents */
.hud-frame::before,.hud-frame::after{
  content:'';position:absolute;
  width:20px;height:20px;
  border-color:var(--green);border-style:solid;
}
.hud-frame::before{top:0;left:0;border-width:2px 0 0 2px;border-radius:2px 0 0 0}
.hud-frame::after{bottom:0;right:0;border-width:0 2px 2px 0;border-radius:0 0 2px 0}

/* Extra corners via wrapper */
.hf-tr,.hf-bl{
  position:absolute;
  width:20px;height:20px;
  border-color:var(--green);border-style:solid;z-index:5;
  pointer-events:none
}
.hf-tr{top:0;right:0;border-width:2px 2px 0 0;border-radius:0 2px 0 0}
.hf-bl{bottom:0;left:0;border-width:0 0 2px 2px;border-radius:0 0 0 2px}

/* Chrome bar */
.hud-chrome{
  padding:14px 24px;
  background:rgba(0,0,0,0.4);
  border-bottom:1px solid var(--border);
  display:flex;align-items:center;gap:10px
}
.hud-dots{display:flex;gap:7px}
.hud-dot{width:11px;height:11px;border-radius:50%}
.hd-r{background:var(--red)}
.hd-y{background:#ffcc00}
.hd-g{background:#00cc55}
.hud-title{font-family:var(--ff-mono);font-size:0.7rem;color:var(--muted2);letter-spacing:0.1em;flex:1;margin-left:10px}
.hud-live{display:flex;align-items:center;gap:7px;font-family:var(--ff-mono);font-size:0.68rem;color:var(--green)}
.hld{width:8px;height:8px;border-radius:50%;background:var(--green);animation:hldp 1.4s ease infinite}
@keyframes hldp{0%,100%{box-shadow:0 0 0 0 var(--g-green)}50%{box-shadow:0 0 0 5px transparent}}

/* Scan beam */
.scan-b{
  position:absolute;left:0;right:0;top:0;height:2px;
  background:linear-gradient(90deg,transparent,var(--green),var(--green2),transparent);
  opacity:0;animation:scanB 5s linear infinite;pointer-events:none;z-index:10
}
@keyframes scanB{0%{top:0;opacity:0}4%{opacity:0.7}95%{opacity:0.7}100%{top:100%;opacity:0}}

/* Prompt */
.hud-prompt{
  padding:14px 24px;border-bottom:1px solid rgba(0,255,136,0.06);
  display:flex;justify-content:space-between;align-items:center
}
.hud-prompt code{font-family:var(--ff-mono);font-size:0.75rem;color:rgba(0,255,136,0.65)}
#scanStat{font-family:var(--ff-mono);font-size:0.65rem;color:var(--muted)}
#scanStat .ok{color:#00cc55}
#scanStat .fail{color:var(--red)}

/* Rows */
.hud-body{padding:18px 24px 22px;max-height:360px;overflow-y:auto}
.hud-body::-webkit-scrollbar{width:4px}
.hud-body::-webkit-scrollbar-track{background:transparent}
.hud-body::-webkit-scrollbar-thumb{background:rgba(0,255,136,0.18);border-radius:4px}
.irow{display:flex;align-items:flex-start;gap:16px;padding:12px 0;border-bottom:1px solid rgba(255,255,255,0.03)}
.irow:last-child{border-bottom:none}
.ikey{font-family:var(--ff-mono);font-size:0.7rem;color:var(--muted);letter-spacing:0.06em;min-width:190px;flex-shrink:0;padding-top:1px}
.ikey::before{content:'> ';color:var(--green);opacity:0.4}
.ival{font-family:var(--ff-mono);font-size:0.82rem;color:#aaccd8;word-break:break-all}
.ival.loading{color:var(--muted)}
.ival.loading::after{content:'▋';animation:blink 0.9s step-end infinite;font-size:0.75rem;color:var(--green);opacity:0.6;margin-left:3px}
@keyframes blink{0%,100%{opacity:1}50%{opacity:0}}
.ival.loaded{color:#6deeff}
.ival.ip-hi{
  background:rgba(0,255,136,0.06);border:1px solid rgba(0,255,136,0.18);
  border-radius:3px;padding:2px 12px;color:var(--green) !important
}

.hud-foot{
  padding:10px 24px;background:rgba(0,255,136,0.025);
  border-top:1px solid rgba(0,255,136,0.05);
  display:flex;justify-content:space-between;
  font-family:var(--ff-mono);font-size:0.62rem;color:var(--muted)
}

/* =============================================
   CONTACT
============================================= */
#contact{background:var(--bg)}

/* Diagonal top */
#contact::before{
  content:'';position:absolute;top:0;left:0;right:0;height:80px;
  background:var(--bg2);clip-path:polygon(0 0,100% 0,100% 0,0 100%)
}

.contact-split{
  display:grid;grid-template-columns:1fr 1.35fr;
  gap:90px;align-items:start;margin-top:3.5rem
}

.ci-left p{color:var(--muted2);font-size:1rem;margin-bottom:2.5rem;line-height:1.85}

.ci-items{display:flex;flex-direction:column}
.ci-row{
  display:flex;align-items:flex-start;gap:18px;
  padding:20px 0;border-bottom:1px solid var(--border)
}
.ci-row:first-child{border-top:1px solid var(--border)}
.ci-ico{
  width:40px;height:40px;border-radius:var(--r);
  background:rgba(0,255,136,0.04);
  border:1px solid var(--border);
  display:flex;align-items:center;justify-content:center;flex-shrink:0;
  transition:border-color 0.3s,box-shadow 0.3s
}
.ci-ico svg{width:17px;height:17px;stroke:var(--green);fill:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round}
.ci-ico:hover{border-color:var(--border2);box-shadow:0 0 16px var(--g-green)}
.ci-txt span{display:block;font-family:var(--ff-mono);font-size:0.62rem;letter-spacing:0.16em;text-transform:uppercase;color:var(--muted);margin-bottom:3px}
.ci-txt strong{color:var(--text);font-weight:500;font-size:0.92rem}

.ci-enc{
  margin-top:2rem;padding:16px 20px;
  background:rgba(0,255,136,0.03);
  border:1px solid rgba(0,255,136,0.1);border-radius:var(--r);
  font-family:var(--ff-mono);font-size:0.7rem;color:var(--green);letter-spacing:0.04em
}
.ci-enc::before{content:'> '}

/* Form */
.fc{
  background:var(--bg2);border:1px solid var(--border);
  border-radius:14px;padding:52px 48px;position:relative;overflow:hidden
}
.fc::before{
  content:'';position:absolute;top:0;left:0;right:0;height:1px;
  background:linear-gradient(90deg,transparent 0%,var(--green) 50%,transparent 100%)
}
/* Corner marks */
.fc::after{
  content:'';position:absolute;bottom:0;right:0;
  width:60px;height:60px;
  border-bottom:1px solid rgba(0,255,136,0.1);
  border-right:1px solid rgba(0,255,136,0.1);
  border-radius:0 0 14px 0
}

.frow{display:grid;grid-template-columns:1fr 1fr;gap:20px}
.field{display:flex;flex-direction:column;gap:8px;margin-bottom:22px}
.field label{font-family:var(--ff-mono);font-size:0.64rem;letter-spacing:0.16em;text-transform:uppercase;color:var(--muted2)}
.field input,.field textarea{
  background:rgba(0,0,0,0.35);
  border:1px solid rgba(255,255,255,0.06);
  border-radius:var(--r);padding:14px 18px;
  color:var(--text2);font-family:var(--ff-body);font-size:16px;
  width:100%;transition:all 0.25s var(--ease);
  -webkit-appearance:none;caret-color:var(--green)
}
.field input:focus,.field textarea:focus{
  outline:none;border-color:rgba(0,255,136,0.3);
  background:rgba(0,255,136,0.025);
  box-shadow:0 0 0 3px rgba(0,255,136,0.06)
}
.field textarea{resize:vertical;min-height:140px}

.fsub{
  width:100%;padding:17px;
  background:var(--green);color:#010608;
  border-radius:var(--r);border:none;
  font-family:var(--ff-mono);font-size:0.8rem;font-weight:700;
  letter-spacing:0.16em;text-transform:uppercase;
  transition:all 0.3s var(--ease);cursor:none;
  position:relative;overflow:hidden;
  box-shadow:0 0 30px var(--g-green)
}
.fsub::before{
  content:'';position:absolute;inset:0;
  background:linear-gradient(135deg,rgba(255,255,255,0.2) 0%,transparent 55%);opacity:0;
  transition:opacity 0.3s
}
.fsub:hover{transform:translateY(-2px);box-shadow:0 14px 50px var(--g-green)}
.fsub:hover::before{opacity:1}
.fsub:disabled{opacity:0.5;cursor:not-allowed;transform:none}

/* =============================================
   SUCCESS OVERLAY
============================================= */
#soverlay{
  position:fixed;inset:0;background:rgba(2,5,8,0.95);
  backdrop-filter:blur(18px);-webkit-backdrop-filter:blur(18px);
  display:flex;align-items:center;justify-content:center;
  z-index:99997;opacity:0;pointer-events:none;transition:opacity 0.4s
}
#soverlay.on{opacity:1;pointer-events:all}
.smodal{
  background:var(--bg2);border:1px solid var(--border3);
  border-radius:16px;padding:64px 56px;text-align:center;
  max-width:440px;width:90%;
  box-shadow:0 0 100px rgba(0,255,136,0.15),0 0 200px rgba(0,255,136,0.05);
  transform:scale(0.85) translateY(24px);
  transition:transform 0.5s cubic-bezier(0.175,0.885,0.32,1.275)
}
#soverlay.on .smodal{transform:scale(1) translateY(0)}
.s-ring{
  width:90px;height:90px;border-radius:50%;
  border:2px solid var(--green);
  margin:0 auto 28px;
  display:flex;align-items:center;justify-content:center;
  font-size:2.5rem;color:var(--green);
  box-shadow:0 0 40px var(--g-green),inset 0 0 30px rgba(0,255,136,0.05)
}
.smodal h3{font-family:var(--ff-hud);font-size:1.9rem;letter-spacing:0.08em;color:var(--text2);margin-bottom:12px}
.smodal p{color:var(--muted2);margin-bottom:32px;font-size:0.95rem}

/* =============================================
   FOOTER
============================================= */
footer{background:var(--bg2);border-top:1px solid var(--border);padding:90px 0 44px}
.foot-grid{display:grid;grid-template-columns:1.5fr 1fr 1fr;gap:70px;margin-bottom:64px;padding-bottom:64px;border-bottom:1px solid var(--border)}
.foot-logo{font-family:var(--ff-hud);font-size:2rem;font-weight:900;letter-spacing:0.08em;color:var(--text2);margin-bottom:14px}
.foot-logo em{font-style:normal;color:var(--green);text-shadow:0 0 20px var(--g-green)}
.foot-brand p{color:var(--muted2);font-size:0.9rem;max-width:300px;line-height:1.75}

.foot-sec h5{font-family:var(--ff-mono);font-size:0.65rem;letter-spacing:0.2em;text-transform:uppercase;color:var(--muted);margin-bottom:1.4rem}
.foot-sec ul{display:flex;flex-direction:column;gap:12px}
.foot-sec a{color:var(--muted2);font-size:0.9rem;transition:color 0.25s;display:flex;align-items:center;gap:8px}
.foot-sec a::before{content:'›';color:var(--green);opacity:0;transition:opacity 0.25s;font-size:1rem}
.foot-sec a:hover{color:var(--green)}
.foot-sec a:hover::before{opacity:1}

.foot-bottom{display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:14px}
.foot-copy{font-family:var(--ff-mono);font-size:0.62rem;color:rgba(58,80,96,0.7);letter-spacing:0.08em}
.foot-tag{font-family:var(--ff-mono);font-size:0.62rem;color:var(--muted)}
.foot-tag span{color:var(--green)}

/* =============================================
   ANIMATIONS
============================================= */
@keyframes fadeUp{from{opacity:0;transform:translateY(30px)}to{opacity:1;transform:translateY(0)}}
@keyframes fadeIn{from{opacity:0}to{opacity:1}}

.rev{opacity:0;transform:translateY(34px);transition:opacity 0.8s var(--ease),transform 0.8s var(--ease)}
.rev.in{opacity:1;transform:translateY(0)}
.rev.d1{transition-delay:0.1s}
.rev.d2{transition-delay:0.2s}
.rev.d3{transition-delay:0.3s}
.rev.d4{transition-delay:0.4s}
.rev.d5{transition-delay:0.5s}

/* =============================================
   RESPONSIVE
============================================= */
@media(max-width:1100px){
  .svc-grid{grid-template-columns:repeat(2,1fr)}
  .stats-grid{grid-template-columns:repeat(2,1fr)}
  .foot-grid{grid-template-columns:1fr 1fr}
}
@media(max-width:900px){
  .svc-head{grid-template-columns:1fr}
  .team-grid{grid-template-columns:1fr}
  .contact-split{grid-template-columns:1fr;gap:50px}
}
@media(max-width:768px){
  section{padding:85px 0}
  .navlinks{display:none}
  .hbg{display:flex}
  .mob-drawer{display:flex}
  .svc-grid{grid-template-columns:1fr}
  .frow{grid-template-columns:1fr}
  .fc{padding:32px 24px}
  .stats-grid{grid-template-columns:repeat(2,1fr)}
  .hero-h1{font-size:clamp(2.8rem,9vw,4.5rem)}
  .hero-btns .btn{width:100%;max-width:320px}
  .irow{flex-direction:column;gap:3px}
  .ikey{min-width:auto}
  body{cursor:auto}
  #cursor{display:none}
  button,a{cursor:pointer}
}
@media(max-width:520px){
  .stats-grid{grid-template-columns:1fr 1fr}
  .foot-grid{grid-template-columns:1fr}
}
</style>
</head>
<body>

<!-- CUSTOM CURSOR -->
<div id="cursor">
  <div class="cursor-dot"></div>
  <div class="cursor-ring"></div>
</div>

<!-- PRELOADER -->
<div id="preloader">
  <div class="pre-logo">RH²</div>
  <div class="pre-pct" id="prePct">0%</div>
  <div class="pre-bar"><div class="pre-fill"></div></div>
  <div class="pre-status">INITIALIZING SECURE CHANNEL...</div>
</div>

<!-- SUCCESS OVERLAY -->
<div id="soverlay" role="dialog" aria-modal="true" aria-label="Submission confirmed">
  <div class="smodal">
    <div class="s-ring">✓</div>
    <h3>TRANSMISSION SECURED</h3>
    <p>Your message has been encrypted and delivered to RH²-Systems servers.</p>
    <button class="fsub" id="closeS" style="max-width:200px;margin:auto;display:block;">ACKNOWLEDGE</button>
  </div>
</div>

<!-- SCROLL TO TOP -->
<button id="stt" aria-label="Scroll to top">
  <svg viewBox="0 0 24 24" width="18" height="18" stroke="currentColor" fill="none" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="18 15 12 9 6 15"/></svg>
</button>

<!-- ══════════ HEADER ══════════ -->
<header id="header">
  <div class="wrap">
    <nav role="navigation" aria-label="Main navigation">
      <a href="#" class="logo" aria-label="RH²-Systems">
        RH²-<em>Systems</em>
        <span class="logo-badge">SECURE</span>
      </a>

      <ul class="navlinks" role="list">
        <li><a href="#services">Services</a></li>
        <li><a href="#team">Team</a></li>
        <li><a href="#methodology">Methodology</a></li>
        <li><a href="#intelligence">Intel</a></li>
        <li><a href="#contact" class="btn btn-g btn-sm">Contact</a></li>
      </ul>

      <button class="hbg" id="hbg" aria-label="Toggle menu" aria-expanded="false">
        <span></span><span></span><span></span>
      </button>
    </nav>
  </div>
</header>

<!-- MOBILE NAV -->
<nav class="mob-drawer" id="mobDrawer" aria-label="Mobile navigation">
  <a href="#services" class="mdl">Services</a>
  <a href="#team" class="mdl">Team</a>
  <a href="#methodology" class="mdl">Methodology</a>
  <a href="#intelligence" class="mdl">Intel Scan</a>
  <a href="#contact" class="mdl">Contact</a>
</nav>

<!-- ══════════ HERO ══════════ -->
<section class="hero" aria-label="Hero">
  <canvas id="hexCanvas" aria-hidden="true"></canvas>
  <div class="orb orb-a" aria-hidden="true"></div>
  <div class="orb orb-b" aria-hidden="true"></div>
  <div class="orb orb-c" aria-hidden="true"></div>

  <!-- Corner brackets -->
  <div class="corner c-tl" aria-hidden="true">
    <svg viewBox="0 0 50 50" fill="none"><path d="M0 20 L0 0 L20 0" stroke="#00ff88" stroke-width="2" opacity="0.5"/></svg>
  </div>
  <div class="corner c-tr" aria-hidden="true">
    <svg viewBox="0 0 50 50" fill="none"><path d="M0 20 L0 0 L20 0" stroke="#00ff88" stroke-width="2" opacity="0.5"/></svg>
  </div>
  <div class="corner c-bl" aria-hidden="true">
    <svg viewBox="0 0 50 50" fill="none"><path d="M0 20 L0 0 L20 0" stroke="#00ff88" stroke-width="2" opacity="0.5"/></svg>
  </div>
  <div class="corner c-br" aria-hidden="true">
    <svg viewBox="0 0 50 50" fill="none"><path d="M0 20 L0 0 L20 0" stroke="#00ff88" stroke-width="2" opacity="0.5"/></svg>
  </div>

  <div class="hero-inner">
    <div class="hero-status" aria-label="Status information">
      <div class="status-chip">
        <span class="pdot" aria-hidden="true"></span>
        SYSTEM SECURE
      </div>
      <div class="status-divider" aria-hidden="true"></div>
      <span class="status-threat" aria-label="Threat level: critical">THREAT LEVEL: CRITICAL</span>
      <div class="status-divider" aria-hidden="true"></div>
      <span style="color:var(--muted2)" id="heroTime">00:00:00 UTC</span>
    </div>

    <h1 class="hero-h1">
      <span class="l1">OFFENSIVE</span>
      <span class="l2"><span id="typeText"></span><span class="cursor" aria-hidden="true"></span></span>
      <span class="l3">RH²-SYSTEMS · EST. 2022</span>
    </h1>

    <p class="hero-sub">Advanced penetration testing, red team operations, and secure engineering for high-risk enterprise infrastructure worldwide.</p>

    <div class="hero-btns">
      <a href="#contact" class="btn btn-g">
        <svg viewBox="0 0 24 24" width="16" height="16" stroke="currentColor" fill="none" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg>
        Initiate Confidential Audit
      </a>
      <a href="#services" class="btn btn-o">
        Explore Capabilities
        <svg viewBox="0 0 24 24" width="15" height="15" stroke="currentColor" fill="none" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="9 18 15 12 9 6"/></svg>
      </a>
    </div>
  </div>

  <div class="scroll-worm" aria-hidden="true">
    <div class="worm-outer"><div class="worm-inner"></div></div>
    Scroll
  </div>
</section>

<!-- ══════════ THREAT TICKER ══════════ -->
<div class="threat-band" aria-hidden="true">
  <div class="threat-ticker" id="ticker">
    <div class="tt-item"><span class="dot dot-r"></span>THREATS BLOCKED TODAY: <span class="tt-val red">2,847</span></div>
    <div class="tt-item"><span class="dot dot-g"></span>ENGAGEMENTS ACTIVE: <span class="tt-val">14</span></div>
    <div class="tt-item"><span class="dot dot-o"></span>CRITICAL VULNS PATCHED: <span class="tt-val org">392</span></div>
    <div class="tt-item"><span class="dot dot-g"></span>UPTIME: <span class="tt-val">99.99%</span></div>
    <div class="tt-item"><span class="dot dot-r"></span>ACTIVE RED TEAM OPS: <span class="tt-val red">3</span></div>
    <div class="tt-item"><span class="dot dot-g"></span>CLIENT DATA BREACHES: <span class="tt-val">0</span></div>
    <div class="tt-item"><span class="dot dot-o"></span>CVEs RESEARCHED: <span class="tt-val org">1,240+</span></div>
    <div class="tt-item"><span class="dot dot-g"></span>ENCRYPTED CHANNELS: <span class="tt-val">ACTIVE</span></div>
    <!-- duplicated for seamless loop -->
    <div class="tt-item"><span class="dot dot-r"></span>THREATS BLOCKED TODAY: <span class="tt-val red">2,847</span></div>
    <div class="tt-item"><span class="dot dot-g"></span>ENGAGEMENTS ACTIVE: <span class="tt-val">14</span></div>
    <div class="tt-item"><span class="dot dot-o"></span>CRITICAL VULNS PATCHED: <span class="tt-val org">392</span></div>
    <div class="tt-item"><span class="dot dot-g"></span>UPTIME: <span class="tt-val">99.99%</span></div>
    <div class="tt-item"><span class="dot dot-r"></span>ACTIVE RED TEAM OPS: <span class="tt-val red">3</span></div>
    <div class="tt-item"><span class="dot dot-g"></span>CLIENT DATA BREACHES: <span class="tt-val">0</span></div>
    <div class="tt-item"><span class="dot dot-o"></span>CVEs RESEARCHED: <span class="tt-val org">1,240+</span></div>
    <div class="tt-item"><span class="dot dot-g"></span>ENCRYPTED CHANNELS: <span class="tt-val">ACTIVE</span></div>
  </div>
</div>

<!-- ══════════ SERVICES ══════════ -->
<section id="services" aria-labelledby="svc-h">
  <div class="wrap">
    <div class="svc-head">
      <div class="rev">
        <span class="eyebrow">01 — Capabilities</span>
        <h2 class="stitle" id="svc-h">CORE SECURITY<br><span class="hl">SERVICES</span></h2>
      </div>
      <p class="sdesc rev d1">Full-spectrum offensive security tailored for modern threat landscapes and enterprise-grade infrastructure.</p>
    </div>

    <div class="svc-grid">
      <div class="sc rev">
        <div class="sc-bar"></div>
        <div class="sc-icon"><svg viewBox="0 0 24 24"><circle cx="11" cy="11" r="8"/><line x1="21" y1="21" x2="16.65" y2="16.65"/></svg></div>
        <div class="sc-num">SVC_001</div>
        <h3>Penetration Testing</h3>
        <p>Manual and automated assessments of Web, Mobile, API, and Cloud infrastructure aligned with OWASP Top 10 and NIST frameworks.</p>
      </div>
      <div class="sc rev d1">
        <div class="sc-bar"></div>
        <div class="sc-icon"><svg viewBox="0 0 24 24"><polygon points="13 2 3 14 12 14 11 22 21 10 12 10 13 2"/></svg></div>
        <div class="sc-num">SVC_002</div>
        <h3>Red Team Operations</h3>
        <p>Adversary simulation replicating nation-state APT tactics to test your detection and response capabilities in real-time scenarios.</p>
      </div>
      <div class="sc rev d2">
        <div class="sc-bar"></div>
        <div class="sc-icon"><svg viewBox="0 0 24 24"><polyline points="16 18 22 12 16 6"/><polyline points="8 6 2 12 8 18"/></svg></div>
        <div class="sc-num">SVC_003</div>
        <h3>Secure Engineering</h3>
        <p>DevSecOps integration, Zero Trust architecture design, and source code review to embed security into the DNA of your software.</p>
      </div>
      <div class="sc rev d3">
        <div class="sc-bar"></div>
        <div class="sc-icon"><svg viewBox="0 0 24 24"><path d="M22 12h-4l-3 9L9 3l-3 9H2"/></svg></div>
        <div class="sc-num">SVC_004</div>
        <h3>Incident Response</h3>
        <p>Continuous threat monitoring, log analysis, and rapid breach containment to detect and remediate security incidents before they escalate.</p>
      </div>
      <div class="sc rev d4">
        <div class="sc-bar"></div>
        <div class="sc-icon"><svg viewBox="0 0 24 24"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg></div>
        <div class="sc-num">SVC_005</div>
        <h3>Threat Modeling</h3>
        <p>Identify and prioritize potential attack vectors and system weaknesses before adversaries exploit them using structured risk analysis.</p>
      </div>
      <div class="sc rev d5">
        <div class="sc-bar"></div>
        <div class="sc-icon"><svg viewBox="0 0 24 24"><rect x="3" y="3" width="18" height="18" rx="2"/><line x1="9" y1="3" x2="9" y2="21"/><line x1="15" y1="3" x2="15" y2="21"/><line x1="3" y1="9" x2="21" y2="9"/><line x1="3" y1="15" x2="21" y2="15"/></svg></div>
        <div class="sc-num">SVC_006</div>
        <h3>Architecture Review</h3>
        <p>Comprehensive evaluation of system design, trust boundaries, and defensive controls to expose structural weaknesses before exploitation.</p>
      </div>
    </div>
  </div>
</section>

<!-- ══════════ STATS ══════════ -->
<section id="methodology" aria-labelledby="meth-h">
  <div class="wrap">
    <div class="rev" style="text-align:center">
      <span class="eyebrow" style="justify-content:center">03 — Methodology</span>
      <h2 class="stitle" id="meth-h" style="text-align:center">THE RH² <span class="hl">STANDARD</span></h2>
      <p class="sdesc" style="margin:0 auto;text-align:center">Measurable, repeatable, and fully confidential security assessments — every time.</p>
    </div>

    <div class="stats-grid rev d1">
      <div class="sg">
        <div class="sg-val"><span class="counter-num" data-target="150" data-suffix="+">0+</span></div>
        <div class="sg-label">Engagements Delivered</div>
      </div>
      <div class="sg">
        <div class="sg-val"><span class="counter-num" data-target="100" data-suffix="%">0%</span></div>
        <div class="sg-label">Confidentiality Record</div>
      </div>
      <div class="sg">
        <div class="sg-val" style="font-size:clamp(2rem,3.5vw,3rem)">24/7</div>
        <div class="sg-label">Incident Support</div>
      </div>
      <div class="sg">
        <div class="sg-val"><span class="counter-num" data-target="0" data-suffix="">0</span></div>
        <div class="sg-label">Client Data Breaches</div>
      </div>
    </div>
  </div>
</section>

<!-- ══════════ TEAM ══════════ -->
<section id="team" aria-labelledby="team-h">
  <div class="wrap">
    <div class="team-intro rev">
      <span class="eyebrow" style="justify-content:center">02 — Leadership</span>
      <h2 class="stitle" id="team-h">ENGINEERING &amp; <span class="hl">COMMAND</span></h2>
      <p class="sdesc">Built by engineers who understand both the attack vector and the defense mechanism.</p>
    </div>

    <div class="team-grid">
      <article class="tc rev d1">
        <div class="tc-head">
          <div class="av">RH</div>
          <div class="tc-meta">
            <h3>Raj Hridoy</h3>
            <span class="tc-role">Cybersecurity Engineer</span>
          </div>
        </div>
        <div class="tc-body">
          <p>Specializing in secure software architecture and complex vulnerability analysis. Raj bridges high-level development with low-level security protocols.</p>
          <div class="tc-tags">
            <span class="ttag">Secure Arch</span>
            <span class="ttag">Python / Go</span>
            <span class="ttag">Cloud Security</span>
            <span class="ttag">DevSecOps</span>
          </div>
          <a href="https://rh-systems.github.io/Raj-Hridoy/" class="tc-link" target="_blank" rel="noopener noreferrer" aria-label="View Raj Hridoy profile">
            View Profile
            <svg viewBox="0 0 24 24"><line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/></svg>
          </a>
        </div>
      </article>

      <article class="tc rev d2">
        <div class="tc-head">
          <div class="av">RH</div>
          <div class="tc-meta">
            <h3>Riyad Hasan</h3>
            <span class="tc-role">Ethical Hacker</span>
          </div>
        </div>
        <div class="tc-body">
          <p>Focused on advanced threat modeling and penetration testing. Riyad specializes in breaking systems to make them unbreakable through adversarial analysis.</p>
          <div class="tc-tags">
            <span class="ttag">PenTesting</span>
            <span class="ttag">Network Forensics</span>
            <span class="ttag">Red Teaming</span>
            <span class="ttag">Exploit Dev</span>
          </div>
          <a href="https://rh-systems.github.io/Riyad-Hasan/" class="tc-link" target="_blank" rel="noopener noreferrer" aria-label="View Riyad Hasan profile">
            View Profile
            <svg viewBox="0 0 24 24"><line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/></svg>
          </a>
        </div>
      </article>
    </div>
  </div>
</section>

<!-- ══════════ INTEL SCAN ══════════ -->
<section id="intelligence" aria-labelledby="intel-h">
  <div class="wrap">
    <div class="rev" style="text-align:center">
      <span class="eyebrow" style="justify-content:center">04 — Telemetry</span>
      <h2 class="stitle" id="intel-h">NETWORK <span class="hl">INTELLIGENCE</span> SCAN</h2>
      <p class="sdesc" style="margin:0 auto;text-align:center">Real-time analysis of your active connection — demonstrating reconnaissance techniques used in live assessments.</p>
    </div>

    <div class="intel-wrap rev d1" role="region" aria-label="Network intelligence scan results">
      <div class="hud-frame">
        <div class="hf-tr"></div>
        <div class="hf-bl"></div>
        <div class="scan-b" aria-hidden="true"></div>

        <div class="hud-chrome" aria-hidden="true">
          <div class="hud-dots">
            <div class="hud-dot hd-r"></div>
            <div class="hud-dot hd-y"></div>
            <div class="hud-dot hd-g"></div>
          </div>
          <span class="hud-title">rh2sys_telemetry — network_scan v3.1</span>
          <div class="hud-live"><div class="hld"></div>LIVE</div>
        </div>

        <div class="hud-prompt" aria-hidden="true">
          <code>$ ./network_scan --target=self --verbose --output=encrypted</code>
          <span id="scanStat">Scanning...</span>
        </div>

        <div class="hud-body" role="table" aria-label="Scan results">
          <div class="irow" role="row">
            <span class="ikey" role="rowheader">IP Address</span>
            <span class="ival loading" id="intel-ip" role="cell" aria-live="polite">Initiating scan...</span>
          </div>
          <div class="irow" role="row">
            <span class="ikey" role="rowheader">Country</span>
            <span class="ival loading" id="intel-country" role="cell" aria-live="polite">Resolving geolocation...</span>
          </div>
          <div class="irow" role="row">
            <span class="ikey" role="rowheader">City / Region</span>
            <span class="ival loading" id="intel-city" role="cell" aria-live="polite">Resolving geolocation...</span>
          </div>
          <div class="irow" role="row">
            <span class="ikey" role="rowheader">ISP / Network</span>
            <span class="ival loading" id="intel-isp" role="cell" aria-live="polite">Querying ASN database...</span>
          </div>
          <div class="irow" role="row">
            <span class="ikey" role="rowheader">Timezone</span>
            <span class="ival loading" id="intel-timezone" role="cell" aria-live="polite">Calculating offset...</span>
          </div>
          <div class="irow" role="row">
            <span class="ikey" role="rowheader">Browser Agent</span>
            <span class="ival" id="intel-browser" role="cell">Detecting...</span>
          </div>
          <div class="irow" role="row">
            <span class="ikey" role="rowheader">Operating System</span>
            <span class="ival" id="intel-os" role="cell">Detecting...</span>
          </div>
          <div class="irow" role="row">
            <span class="ikey" role="rowheader">Screen / DPI</span>
            <span class="ival" id="intel-screen" role="cell">Detecting...</span>
          </div>
        </div>

        <div class="hud-foot" aria-hidden="true">
          <span>RH²-SYS TELEMETRY v3.1 · HTTPS ENCRYPTED · TLS 1.3</span>
          <span id="intelTs"></span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ══════════ CONTACT ══════════ -->
<section id="contact" aria-labelledby="cont-h">
  <div class="wrap">
    <div class="rev">
      <span class="eyebrow">05 — Contact</span>
      <h2 class="stitle" id="cont-h">SECURE <span class="hl">CONSULTATION</span></h2>
    </div>

    <div class="contact-split">
      <div class="ci-left rev d1">
        <p>Ready to fortify your infrastructure? Contact us for a confidential discussion regarding your security posture and threat exposure. All communications are end-to-end encrypted.</p>

        <div class="ci-items">
          <div class="ci-row">
            <div class="ci-ico"><svg viewBox="0 0 24 24"><path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"/><circle cx="12" cy="10" r="3"/></svg></div>
            <div class="ci-txt"><span>Location</span><strong>Rajshahi Division, Bangladesh</strong></div>
          </div>
          <div class="ci-row">
            <div class="ci-ico"><svg viewBox="0 0 24 24"><circle cx="12" cy="12" r="10"/><polyline points="12 6 12 12 16 14"/></svg></div>
            <div class="ci-txt"><span>Availability</span><strong>24 / 7 Incident Support</strong></div>
          </div>
          <div class="ci-row">
            <div class="ci-ico"><svg viewBox="0 0 24 24"><rect x="3" y="11" width="18" height="11" rx="2"/><path d="M7 11V7a5 5 0 0 1 10 0v4"/></svg></div>
            <div class="ci-txt"><span>Channels</span><strong>Encrypted comms available on request</strong></div>
          </div>
        </div>

        <div class="ci-enc">All submissions are end-to-end encrypted via Firebase.</div>
      </div>

      <div class="fc rev d2">
        <form id="cForm" novalidate aria-label="Contact form">
          <div class="frow">
            <div class="field">
              <label for="fn">Full Name / Organization</label>
              <input type="text" id="fn" name="name" placeholder="Acme Corp / Jane Doe" required autocomplete="name">
            </div>
            <div class="field">
              <label for="fe">Work Email</label>
              <input type="email" id="fe" name="email" placeholder="security@yourcompany.com" required autocomplete="email">
            </div>
          </div>
          <div class="field">
            <label for="fm">Project Scope / Details</label>
            <textarea id="fm" name="message" rows="5" placeholder="Describe your infrastructure and security goals..." required></textarea>
          </div>
          <button type="submit" class="fsub" id="submitBtn">TRANSMIT ENCRYPTED REQUEST</button>
        </form>
      </div>
    </div>
  </div>
</section>

<!-- ══════════ FOOTER ══════════ -->
<footer>
  <div class="wrap">
    <div class="foot-grid">
      <div class="foot-brand">
        <div class="foot-logo">RH²-<em>Systems</em></div>
        <p>Enterprise-grade cybersecurity and offensive security operations for high-risk infrastructure worldwide. 100% confidentiality guaranteed.</p>
      </div>
      <div class="foot-sec">
        <h5>Services</h5>
        <ul>
          <li><a href="#services">Penetration Testing</a></li>
          <li><a href="#services">Red Team Operations</a></li>
          <li><a href="#services">Secure Engineering</a></li>
          <li><a href="#services">Incident Response</a></li>
          <li><a href="#services">Threat Modeling</a></li>
          <li><a href="#services">Architecture Review</a></li>
        </ul>
      </div>
      <div class="foot-sec">
        <h5>Company</h5>
        <ul>
          <li><a href="#team">Our Team</a></li>
          <li><a href="#methodology">Methodology</a></li>
          <li><a href="#intelligence">Intel Scan</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </div>
    </div>
    <div class="foot-bottom">
      <div class="foot-copy">© 2026 RH²-SYSTEMS · ALL RIGHTS RESERVED · CONFIDENTIALITY GUARANTEED</div>
      <div class="foot-tag">Rajshahi, Bangladesh · <span>Offensive Security</span></div>
    </div>
  </div>
</footer>

<!-- ══════════════════════════════════════
     JAVASCRIPT
══════════════════════════════════════ -->
<script>
/* ── PRELOADER ── */
(function(){
  let p=0;
  const pct=document.getElementById('prePct');
  const iv=setInterval(()=>{
    p+=Math.random()*18;
    if(p>=100){p=100;clearInterval(iv)}
    pct.textContent=Math.floor(p)+'%';
  },80);
  window.addEventListener('load',()=>{
    setTimeout(()=>{
      document.getElementById('preloader').classList.add('out');
    },1500);
  });
})();

/* ── CUSTOM CURSOR ── */
(function(){
  const c=document.getElementById('cursor');
  const dot=c.querySelector('.cursor-dot');
  const ring=c.querySelector('.cursor-ring');
  let mx=0,my=0,rx=0,ry=0;
  document.addEventListener('mousemove',e=>{mx=e.clientX;my=e.clientY});
  function animate(){
    rx+=(mx-rx)*0.12; ry+=(my-ry)*0.12;
    dot.style.left=mx+'px'; dot.style.top=my+'px';
    ring.style.left=rx+'px'; ring.style.top=ry+'px';
    requestAnimationFrame(animate);
  }
  animate();
  document.querySelectorAll('a,button,.sc,.tc').forEach(el=>{
    el.addEventListener('mouseenter',()=>document.body.classList.add('cursor-hover'));
    el.addEventListener('mouseleave',()=>document.body.classList.remove('cursor-hover'));
  });
})();

/* ── HEADER STICKY ── */
const hdr=document.getElementById('header');
window.addEventListener('scroll',()=>hdr.classList.toggle('sticky',window.scrollY>10));

/* ── SCROLL TO TOP ── */
const stt=document.getElementById('stt');
window.addEventListener('scroll',()=>stt.classList.toggle('show',window.scrollY>500));
stt.addEventListener('click',()=>window.scrollTo({top:0,behavior:'smooth'}));

/* ── MOBILE NAV ── */
const hbg=document.getElementById('hbg');
const mob=document.getElementById('mobDrawer');
hbg.addEventListener('click',()=>{
  const on=mob.classList.toggle('on');
  hbg.classList.toggle('on',on);
  hbg.setAttribute('aria-expanded',on);
  document.body.style.overflow=on?'hidden':'';
});
document.querySelectorAll('.mdl').forEach(a=>a.addEventListener('click',()=>{
  mob.classList.remove('on');hbg.classList.remove('on');
  hbg.setAttribute('aria-expanded','false');
  document.body.style.overflow='';
}));

/* ── SCROLL REVEAL ── */
const ro=new IntersectionObserver(entries=>{
  entries.forEach(e=>{if(e.isIntersecting)e.target.classList.add('in')});
},{threshold:0.07});
document.querySelectorAll('.rev').forEach(el=>ro.observe(el));

/* ── TYPEWRITER ── */
(function(){
  const words=['INFRASTRUCTURE.','SECURE ENGINEERING.','RED TEAM OPS.','EXPLOIT RESEARCH.'];
  const el=document.getElementById('typeText');
  let wi=0,ci=0,del=false;
  function tick(){
    const w=words[wi];
    el.textContent=del?w.substring(0,--ci):w.substring(0,++ci);
    let d=del?22:55;
    if(!del&&ci===w.length){d=2200;del=true}
    if(del&&ci===0){del=false;wi=(wi+1)%words.length}
    setTimeout(tick,d);
  }
  tick();
})();

/* ── LIVE UTC CLOCK ── */
(function(){
  function update(){
    const t=new Date();
    document.getElementById('heroTime').textContent=
      t.getUTCHours().toString().padStart(2,'0')+':'+
      t.getUTCMinutes().toString().padStart(2,'0')+':'+
      t.getUTCSeconds().toString().padStart(2,'0')+' UTC';
  }
  update(); setInterval(update,1000);
})();

/* ── HEX CANVAS ── */
(function(){
  const canvas=document.getElementById('hexCanvas');
  const ctx=canvas.getContext('2d');
  const DPR=Math.min(window.devicePixelRatio||1,2);
  let W,H,hexes=[];
  const HEX_R=30;

  function resize(){
    W=canvas.parentElement.offsetWidth;
    H=canvas.parentElement.offsetHeight;
    canvas.width=W*DPR; canvas.height=H*DPR;
    canvas.style.width=W+'px'; canvas.style.height=H+'px';
    ctx.scale(DPR,DPR);
    buildHexes();
  }

  function hexPoints(cx,cy,r){
    let pts=[];
    for(let i=0;i<6;i++){
      const a=(Math.PI/3)*i-Math.PI/6;
      pts.push([cx+r*Math.cos(a),cy+r*Math.sin(a)]);
    }
    return pts;
  }

  function buildHexes(){
    hexes=[];
    const w=HEX_R*Math.sqrt(3), h=HEX_R*2;
    const cols=Math.ceil(W/w)+2, rows=Math.ceil(H/(h*0.75))+2;
    for(let row=0;row<rows;row++){
      for(let col=0;col<cols;col++){
        const cx=col*w+(row%2?w/2:0);
        const cy=row*(h*0.75);
        hexes.push({cx,cy,a:Math.random(),da:(Math.random()-0.5)*0.008,lit:Math.random()<0.04});
      }
    }
  }

  function draw(){
    ctx.clearRect(0,0,W,H);
    hexes.forEach(h=>{
      h.a+=h.da;
      if(h.a<0||h.a>1)h.da*=-1;
      h.a=Math.max(0,Math.min(1,h.a));
      const pts=hexPoints(h.cx,h.cy,HEX_R-2);
      ctx.beginPath();
      ctx.moveTo(pts[0][0],pts[0][1]);
      pts.slice(1).forEach(p=>ctx.lineTo(p[0],p[1]));
      ctx.closePath();
      const alpha=h.lit?h.a*0.6:h.a*0.06;
      ctx.strokeStyle=h.lit?`rgba(0,255,136,${alpha})`:`rgba(0,255,136,${alpha})`;
      ctx.lineWidth=h.lit?1.5:0.6;
      ctx.stroke();
      if(h.lit){
        ctx.fillStyle=`rgba(0,255,136,${alpha*0.08})`;
        ctx.fill();
      }
    });
    requestAnimationFrame(draw);
  }

  window.addEventListener('resize',resize);
  resize(); draw();
})();

/* ── COUNTER ANIMATION ── */
(function(){
  const counters=document.querySelectorAll('.counter-num');
  const co=new IntersectionObserver(entries=>{
    entries.forEach(e=>{
      if(e.isIntersecting&&!e.target.dataset.done){
        e.target.dataset.done='1';
        const target=+e.target.dataset.target;
        const suffix=e.target.dataset.suffix||'';
        const dur=1800;
        const start=performance.now();
        function step(now){
          const pct=Math.min((now-start)/dur,1);
          const eased=1-Math.pow(1-pct,3);
          e.target.textContent=Math.round(eased*target)+suffix;
          if(pct<1)requestAnimationFrame(step);
        }
        requestAnimationFrame(step);
      }
    });
  },{threshold:0.5});
  counters.forEach(c=>co.observe(c));
})();

/* ── INTEL SCAN ── */
(function(){
  function setV(id,val,isIp){
    const el=document.getElementById(id);
    if(!el)return;
    el.textContent=val||'Unknown';
    el.classList.remove('loading');
    el.classList.add('loaded');
    if(isIp)el.classList.add('ip-hi');
  }
  function fail(){
    ['intel-ip','intel-country','intel-city','intel-isp','intel-timezone'].forEach(id=>setV(id,'Data Unavailable'));
    const s=document.getElementById('scanStat');
    if(s){s.innerHTML='<span class="fail">SCAN FAILED</span>'}
  }

  const ua=navigator.userAgent;
  let browser='Unknown',os='Unknown';
  if(/SamsungBrowser/i.test(ua))browser='Samsung Internet';
  else if(/OPR|Opera/i.test(ua))browser='Opera';
  else if(/Trident/i.test(ua))browser='Internet Explorer 11';
  else if(/Edg\//i.test(ua))browser='Microsoft Edge';
  else if(/Firefox\/\d/i.test(ua))browser='Mozilla Firefox';
  else if(/Chrome\/\d/i.test(ua))browser='Google Chrome';
  else if(/Safari\/\d/i.test(ua))browser='Apple Safari';

  if(/Android/i.test(ua))os='Android';
  else if(/iPhone|iPad|iPod/i.test(ua))os='iOS';
  else if(/Windows NT 10/i.test(ua))os='Windows 10 / 11';
  else if(/Windows/i.test(ua))os='Windows';
  else if(/Mac OS X/i.test(ua))os='macOS';
  else if(/Linux/i.test(ua))os='Linux';
  else if(/X11/i.test(ua))os='UNIX';

  const bEl=document.getElementById('intel-browser');
  const oEl=document.getElementById('intel-os');
  const sEl=document.getElementById('intel-screen');
  if(bEl){bEl.textContent=browser;bEl.classList.add('loaded')}
  if(oEl){oEl.textContent=os;oEl.classList.add('loaded')}
  if(sEl){sEl.textContent=`${screen.width} × ${screen.height} @ ${window.devicePixelRatio||1}x DPI`;sEl.classList.add('loaded')}

  const tsEl=document.getElementById('intelTs');
  if(tsEl)tsEl.textContent='INIT: '+new Date().toISOString().replace('T',' ').split('.')[0]+' UTC';

  const ctrl=new AbortController();
  const to=setTimeout(()=>ctrl.abort(),8000);

  fetch('https://ipwho.is/',{signal:ctrl.signal})
    .then(r=>{if(!r.ok)throw 0;return r.json()})
    .then(d=>{
      clearTimeout(to);if(!d.success)throw 0;
      setV('intel-ip',d.ip,true);
      setV('intel-country',`${d.country} (${d.country_code||''})`);
      setV('intel-city',`${d.city||'—'}, ${d.region||'—'}`);
      setV('intel-isp',d.connection?.isp||d.connection?.org||d.org||'Unknown');
      setV('intel-timezone',d.timezone?.id||d.timezone||'Unknown');
      const s=document.getElementById('scanStat');
      if(s)s.innerHTML='<span class="ok">SCAN COMPLETE ✓</span>';
    })
    .catch(()=>{
      fetch('https://ipapi.co/json/',{signal:ctrl.signal})
        .then(r=>{if(!r.ok)throw 0;return r.json()})
        .then(d=>{
          clearTimeout(to);if(d.error)throw 0;
          setV('intel-ip',d.ip,true);
          setV('intel-country',`${d.country_name} (${d.country_code})`);
          setV('intel-city',`${d.city||'—'}, ${d.region||'—'}`);
          setV('intel-isp',d.org||d.asn||'Unknown');
          setV('intel-timezone',d.timezone||'Unknown');
          const s=document.getElementById('scanStat');
          if(s)s.innerHTML='<span class="ok">SCAN COMPLETE ✓</span>';
        })
        .catch(()=>{
          fetch('https://ipinfo.io/json',{signal:ctrl.signal})
            .then(r=>{if(!r.ok)throw 0;return r.json()})
            .then(d=>{
              clearTimeout(to);
              setV('intel-ip',d.ip,true);
              setV('intel-country',d.country||'Unknown');
              setV('intel-city',`${d.city||'—'}, ${d.region||'—'}`);
              setV('intel-isp',d.org||'Unknown');
              setV('intel-timezone',d.timezone||'Unknown');
              const s=document.getElementById('scanStat');
              if(s)s.innerHTML='<span class="ok">SCAN COMPLETE ✓</span>';
            })
            .catch(()=>{clearTimeout(to);fail()});
        });
    });
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
  appId:"1:492917852953:web:9fc6ff86f6fcd2fc965388",
  measurementId:"G-RRHPV2Y2S9"
});
const db=getFirestore(app);

const ov=document.getElementById('soverlay');
document.getElementById('closeS').addEventListener('click',()=>ov.classList.remove('on'));
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
    console.error(err);alert('Transmission failed: '+err.message);
  }finally{
    btn.textContent='TRANSMIT ENCRYPTED REQUEST';btn.disabled=false;
  }
});
</script>
</body>
</html>
