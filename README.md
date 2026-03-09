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
<link rel="icon" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 32 32'><rect width='32' height='32' fill='%2300e5ff' rx='4'/><text y='24' x='4' font-size='20' font-family='monospace' fill='%23020a12' font-weight='900'>R²</text></svg>">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=DM+Sans:wght@300;400;500;600&family=JetBrains+Mono:wght@400;700&display=swap" rel="stylesheet">

<style>
/* ═══════════════════════════════════════
   TOKENS
═══════════════════════════════════════ */
:root {
  --bg:        #04080f;
  --bg2:       #070d1a;
  --bg3:       #0a1120;
  --glass:     rgba(7,13,26,0.82);
  --cyan:      #00e5ff;
  --red:       #ff2d55;
  --gold:      #f5c518;
  --glow-c:    rgba(0,229,255,0.28);
  --glow-r:    rgba(255,45,85,0.22);
  --text:      #dde8f0;
  --muted:     #4e6070;
  --muted2:    #7a90a4;
  --border:    rgba(0,229,255,0.09);
  --border-hi: rgba(0,229,255,0.4);

  --ff-display: 'Bebas Neue', sans-serif;
  --ff-body:    'DM Sans', sans-serif;
  --ff-mono:    'JetBrains Mono', monospace;

  --radius: 6px;
  --transition: 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}

/* ═══════════════════════════════════════
   RESET
═══════════════════════════════════════ */
*, *::before, *::after { margin:0; padding:0; box-sizing:border-box; -webkit-tap-highlight-color:transparent; }
html { scroll-behavior: smooth; }
body {
  background: var(--bg);
  color: var(--text);
  font-family: var(--ff-body);
  font-size: 1rem;
  line-height: 1.7;
  overflow-x: hidden;
}
a { text-decoration: none; color: inherit; }
img { display: block; max-width: 100%; }
ul { list-style: none; }
button { cursor: pointer; border: none; background: none; font-family: inherit; }

/* Noise texture overlay */
body::after {
  content: '';
  position: fixed; inset: 0;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='1'/%3E%3C/svg%3E");
  opacity: 0.025;
  pointer-events: none;
  z-index: 9998;
}

/* Preloader */
#preloader {
  position: fixed; inset: 0;
  background: var(--bg);
  z-index: 9999;
  display: flex; align-items: center; justify-content: center;
  flex-direction: column; gap: 20px;
  transition: opacity 0.6s ease, visibility 0.6s ease;
}
#preloader.hidden { opacity: 0; visibility: hidden; }
.loader-logo {
  font-family: var(--ff-display);
  font-size: 3rem;
  letter-spacing: 0.12em;
  color: var(--cyan);
  text-shadow: 0 0 40px var(--glow-c);
  animation: logoPulse 1s ease-in-out infinite alternate;
}
@keyframes logoPulse { from { opacity:0.4; } to { opacity:1; } }
.loader-bar {
  width: 180px; height: 2px;
  background: rgba(0,229,255,0.12);
  border-radius: 2px;
  overflow: hidden;
}
.loader-fill {
  height: 100%;
  background: var(--cyan);
  box-shadow: 0 0 12px var(--cyan);
  animation: loaderFill 1.2s ease forwards;
}
@keyframes loaderFill { from { width:0; } to { width:100%; } }

/* ═══════════════════════════════════════
   SCROLL-TO-TOP
═══════════════════════════════════════ */
#scrollTop {
  position: fixed; bottom: 28px; right: 28px; z-index: 500;
  width: 44px; height: 44px; border-radius: 50%;
  background: var(--bg3);
  border: 1px solid var(--border-hi);
  color: var(--cyan);
  display: flex; align-items: center; justify-content: center;
  font-size: 1.1rem;
  opacity: 0; pointer-events: none;
  transition: opacity 0.3s, transform 0.3s, box-shadow 0.3s;
  box-shadow: 0 0 16px var(--glow-c);
}
#scrollTop.visible { opacity: 1; pointer-events: all; }
#scrollTop:hover { transform: translateY(-3px); box-shadow: 0 0 28px var(--glow-c); }

/* ═══════════════════════════════════════
   LAYOUT
═══════════════════════════════════════ */
.container { width: min(1240px, 92%); margin: auto; }
section { padding: 120px 0; position: relative; }

/* ═══════════════════════════════════════
   TYPOGRAPHY
═══════════════════════════════════════ */
.label {
  font-family: var(--ff-mono);
  font-size: 0.68rem;
  letter-spacing: 0.22em;
  text-transform: uppercase;
  color: var(--cyan);
  display: inline-flex; align-items: center; gap: 10px;
  margin-bottom: 1rem;
}
.label::before {
  content: '';
  width: 24px; height: 1px;
  background: var(--cyan);
  box-shadow: 0 0 8px var(--cyan);
}

.section-title {
  font-family: var(--ff-display);
  font-size: clamp(2.6rem, 5vw, 4rem);
  letter-spacing: 0.04em;
  line-height: 1;
  color: #fff;
  margin-bottom: 0.8rem;
}
.section-title span { color: var(--cyan); }
.section-sub { color: var(--muted2); max-width: 520px; }

/* ═══════════════════════════════════════
   BUTTONS
═══════════════════════════════════════ */
.btn {
  display: inline-flex; align-items: center; gap: 10px;
  padding: 13px 30px; border-radius: var(--radius);
  font-family: var(--ff-mono);
  font-size: 0.75rem; font-weight: 700;
  letter-spacing: 0.1em; text-transform: uppercase;
  transition: var(--transition);
  position: relative; overflow: hidden;
  cursor: pointer;
}
.btn-primary {
  background: var(--cyan); color: #030810;
  box-shadow: 0 0 24px var(--glow-c), inset 0 1px 0 rgba(255,255,255,0.25);
}
.btn-primary::before {
  content: '';
  position: absolute; inset: 0;
  background: linear-gradient(135deg, rgba(255,255,255,0.15), transparent 60%);
}
.btn-primary:hover { transform: translateY(-3px); box-shadow: 0 12px 40px var(--glow-c); }
.btn-ghost {
  background: transparent; color: var(--text);
  border: 1px solid rgba(255,255,255,0.12);
}
.btn-ghost:hover { border-color: var(--cyan); color: var(--cyan); transform: translateY(-3px); }
.btn-sm { padding: 9px 20px; font-size: 0.68rem; }

/* ═══════════════════════════════════════
   HEADER
═══════════════════════════════════════ */
header {
  position: fixed; top: 0; left: 0; right: 0; z-index: 1000;
  height: 70px;
  transition: background 0.4s, border-color 0.4s;
}
header.scrolled {
  background: rgba(4,8,15,0.92);
  backdrop-filter: blur(24px);
  -webkit-backdrop-filter: blur(24px);
  border-bottom: 1px solid var(--border);
}
nav {
  height: 100%;
  display: flex; align-items: center; justify-content: space-between;
}

.logo {
  font-family: var(--ff-display);
  font-size: 1.55rem;
  letter-spacing: 0.06em;
  color: #fff;
  position: relative;
}
.logo em { font-style: normal; color: var(--cyan); text-shadow: 0 0 18px var(--glow-c); }
.logo::after {
  content: '';
  position: absolute; bottom: -2px; left: 0; right: 0; height: 1px;
  background: linear-gradient(90deg, var(--cyan), transparent);
  opacity: 0.4;
}

.nav-links {
  display: flex; align-items: center; gap: 34px;
}
.nav-links a {
  font-family: var(--ff-mono);
  font-size: 0.7rem; letter-spacing: 0.1em;
  text-transform: uppercase; color: var(--muted2);
  transition: color 0.25s;
  position: relative;
}
.nav-links a::after {
  content: ''; position: absolute; bottom: -3px; left: 0; right: 0;
  height: 1px; background: var(--cyan);
  transform: scaleX(0); transition: transform 0.25s;
}
.nav-links a:hover { color: var(--cyan); }
.nav-links a:hover::after { transform: scaleX(1); }

.nav-cta-wrap { margin-left: 8px; }

.hamburger {
  display: none;
  flex-direction: column; gap: 5px;
  padding: 6px; cursor: pointer;
  z-index: 1001;
}
.hamburger span {
  display: block; width: 24px; height: 2px;
  background: var(--text);
  transition: transform 0.3s, opacity 0.3s, background 0.3s;
  border-radius: 2px;
}
.hamburger.active span:nth-child(1) { transform: translateY(7px) rotate(45deg); background: var(--cyan); }
.hamburger.active span:nth-child(2) { opacity: 0; }
.hamburger.active span:nth-child(3) { transform: translateY(-7px) rotate(-45deg); background: var(--cyan); }

/* Mobile drawer */
.mobile-nav {
  display: none;
  position: fixed; top: 70px; left: 0; right: 0;
  height: calc(100dvh - 70px);
  background: rgba(4,8,15,0.98);
  backdrop-filter: blur(24px);
  -webkit-backdrop-filter: blur(24px);
  flex-direction: column; align-items: center; justify-content: center; gap: 40px;
  transform: translateY(-8px); opacity: 0; pointer-events: none;
  transition: opacity 0.3s, transform 0.3s;
  z-index: 999;
}
.mobile-nav.open { opacity: 1; transform: translateY(0); pointer-events: all; }
.mobile-nav a {
  font-family: var(--ff-display);
  font-size: 2.2rem; letter-spacing: 0.1em;
  color: var(--text); transition: color 0.25s;
}
.mobile-nav a:hover { color: var(--cyan); }

/* ═══════════════════════════════════════
   HERO
═══════════════════════════════════════ */
.hero {
  min-height: 100dvh;
  display: flex; align-items: center; justify-content: center;
  text-align: center;
  padding-top: 70px;
  overflow: hidden;
  position: relative;
}

/* Grid background */
.hero-grid {
  position: absolute; inset: 0;
  background-image:
    linear-gradient(rgba(0,229,255,0.04) 1px, transparent 1px),
    linear-gradient(90deg, rgba(0,229,255,0.04) 1px, transparent 1px);
  background-size: 60px 60px;
  mask-image: radial-gradient(ellipse 80% 80% at 50% 50%, black 20%, transparent 80%);
  pointer-events: none;
}

/* Glows */
.hero-glow-a {
  position: absolute;
  width: 700px; height: 700px;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(0,229,255,0.08), transparent 70%);
  top: 50%; left: 50%; transform: translate(-50%, -50%);
  pointer-events: none;
}
.hero-glow-b {
  position: absolute;
  width: 400px; height: 400px;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(255,45,85,0.07), transparent 70%);
  bottom: 0; right: 10%;
  pointer-events: none;
}

#networkCanvas {
  position: absolute; inset: 0;
  width: 100%; height: 100%;
  opacity: 0.4; pointer-events: none; z-index: 0;
}

.hero-content {
  position: relative; z-index: 2;
  max-width: 900px; width: 100%;
  padding: 0 24px;
}

.status-pill {
  display: inline-flex; align-items: center; gap: 10px;
  padding: 6px 18px; border-radius: 99px;
  background: rgba(0,229,255,0.06);
  border: 1px solid rgba(0,229,255,0.25);
  font-family: var(--ff-mono); font-size: 0.68rem;
  letter-spacing: 0.18em; text-transform: uppercase; color: var(--cyan);
  margin-bottom: 2rem;
  box-shadow: 0 0 24px var(--glow-c);
  animation: fadeDown 0.8s 0.3s both;
}
.pulse-dot {
  width: 7px; height: 7px; border-radius: 50%;
  background: var(--cyan);
  box-shadow: 0 0 8px var(--cyan);
  animation: pulseDot 2s ease infinite;
}
@keyframes pulseDot { 0%,100%{opacity:1;transform:scale(1);} 50%{opacity:0.3;transform:scale(0.6);} }

.hero-title {
  font-family: var(--ff-display);
  font-size: clamp(3.2rem, 8vw, 7rem);
  line-height: 0.96;
  letter-spacing: 0.04em;
  color: #fff;
  margin-bottom: 1.6rem;
  animation: fadeUp 0.9s 0.5s both;
}
.hero-title .line-accent {
  background: linear-gradient(90deg, var(--cyan) 0%, #80f0ff 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  display: block;
}
.hero-title .line-red {
  color: var(--red);
  text-shadow: 0 0 60px var(--glow-r);
  display: block;
  font-size: 0.62em;
  letter-spacing: 0.25em;
  margin-top: 4px;
}

/* Typewriter */
#typeText { color: var(--cyan); }
.cursor {
  display: inline-block; width: 3px; height: 0.8em;
  background: var(--cyan); vertical-align: middle; margin-left: 2px;
  animation: blink 0.85s step-end infinite;
}
@keyframes blink { 0%,100%{opacity:1;} 50%{opacity:0;} }

.hero-desc {
  max-width: 580px; margin: 0 auto 2.8rem;
  color: var(--muted2); font-size: 1.08rem;
  animation: fadeUp 0.9s 0.7s both;
}
.hero-actions {
  display: flex; gap: 14px; justify-content: center; flex-wrap: wrap;
  animation: fadeUp 0.9s 0.9s both;
}

/* Scroll indicator */
.scroll-hint {
  position: absolute; bottom: 32px; left: 50%; transform: translateX(-50%);
  display: flex; flex-direction: column; align-items: center; gap: 6px;
  font-family: var(--ff-mono); font-size: 0.6rem;
  letter-spacing: 0.18em; text-transform: uppercase; color: var(--muted);
  z-index: 2; animation: fadeUp 1s 1.2s both;
}
.scroll-line {
  width: 1px; height: 40px;
  background: linear-gradient(to bottom, var(--cyan), transparent);
  animation: scrollDrop 2s ease infinite;
}
@keyframes scrollDrop {
  0% { transform: scaleY(0); transform-origin: top; opacity: 1; }
  50% { transform: scaleY(1); transform-origin: top; opacity: 1; }
  51% { transform: scaleY(1); transform-origin: bottom; }
  100% { transform: scaleY(0); transform-origin: bottom; opacity: 0; }
}

/* ═══════════════════════════════════════
   SERVICES
═══════════════════════════════════════ */
#services { background: var(--bg); }

.services-intro {
  display: flex; justify-content: space-between; align-items: flex-end;
  gap: 40px; margin-bottom: 64px; flex-wrap: wrap;
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1px;
  background: var(--border);
  border: 1px solid var(--border);
  border-radius: 10px;
  overflow: hidden;
}

.svc-card {
  background: var(--bg2);
  padding: 44px 36px;
  position: relative; overflow: hidden;
  transition: background var(--transition);
}
.svc-card::before {
  content: '';
  position: absolute; top: 0; left: 0; right: 0;
  height: 2px;
  background: linear-gradient(90deg, transparent, var(--cyan), transparent);
  opacity: 0;
  transition: opacity var(--transition);
}
.svc-card:hover { background: #0b1526; }
.svc-card:hover::before { opacity: 1; }

.svc-icon {
  width: 52px; height: 52px;
  border-radius: var(--radius);
  border: 1px solid var(--border);
  display: flex; align-items: center; justify-content: center;
  margin-bottom: 1.6rem;
  background: rgba(0,229,255,0.04);
  transition: border-color var(--transition), box-shadow var(--transition);
}
.svc-card:hover .svc-icon {
  border-color: rgba(0,229,255,0.3);
  box-shadow: 0 0 20px var(--glow-c);
}
.svc-icon svg { width: 24px; height: 24px; stroke: var(--cyan); fill: none; stroke-width: 1.5; stroke-linecap: round; stroke-linejoin: round; }

.svc-num {
  font-family: var(--ff-mono); font-size: 0.62rem;
  letter-spacing: 0.2em; color: var(--muted);
  margin-bottom: 0.8rem;
}
.svc-card h3 { font-family: var(--ff-display); font-size: 1.4rem; letter-spacing: 0.05em; color: #fff; margin-bottom: 0.8rem; }
.svc-card p { color: var(--muted2); font-size: 0.9rem; line-height: 1.7; }

/* ═══════════════════════════════════════
   TEAM
═══════════════════════════════════════ */
#team {
  background: var(--bg2);
  position: relative; overflow: hidden;
}
#team::before {
  content: '';
  position: absolute; top: -200px; right: -200px;
  width: 500px; height: 500px; border-radius: 50%;
  background: radial-gradient(circle, rgba(0,229,255,0.04), transparent 70%);
  pointer-events: none;
}

.team-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(min(100%, 380px), 1fr));
  gap: 28px;
  margin-top: 3rem;
}

.team-card {
  border: 1px solid var(--border);
  border-radius: 12px;
  overflow: hidden;
  background: var(--bg);
  transition: border-color var(--transition), box-shadow var(--transition), transform var(--transition);
  display: flex; flex-direction: column;
}
.team-card:hover {
  border-color: var(--border-hi);
  box-shadow: 0 0 40px rgba(0,229,255,0.08);
  transform: translateY(-4px);
}

.team-header {
  padding: 40px 32px 32px;
  background: linear-gradient(150deg, #060f1e, #030810);
  border-bottom: 1px solid var(--border);
  display: flex; align-items: center; gap: 22px;
  position: relative; overflow: hidden;
}
.team-header::after {
  content: '';
  position: absolute; top: 0; right: 0;
  width: 160px; height: 160px; border-radius: 50%;
  background: radial-gradient(circle, rgba(0,229,255,0.06), transparent 70%);
}

.avatar {
  width: 76px; height: 76px; border-radius: 50%;
  border: 2px solid rgba(0,229,255,0.35);
  background: var(--bg3);
  display: flex; align-items: center; justify-content: center;
  font-family: var(--ff-display); font-size: 1.4rem; letter-spacing: 0.05em;
  color: var(--cyan); flex-shrink: 0;
  box-shadow: 0 0 24px var(--glow-c), inset 0 0 20px rgba(0,229,255,0.05);
}
.team-meta h3 { font-family: var(--ff-display); font-size: 1.7rem; letter-spacing: 0.04em; color: #fff; line-height: 1; margin-bottom: 6px; }
.team-meta .role { font-family: var(--ff-mono); font-size: 0.68rem; letter-spacing: 0.12em; text-transform: uppercase; color: var(--cyan); }

.team-body { padding: 28px 32px 32px; flex: 1; }
.team-body p { color: var(--muted2); font-size: 0.92rem; margin-bottom: 1.4rem; line-height: 1.75; }
.tags { display: flex; flex-wrap: wrap; gap: 8px; margin-bottom: 1.6rem; }
.tag {
  font-family: var(--ff-mono); font-size: 0.65rem;
  padding: 5px 12px; border-radius: 99px;
  border: 1px solid var(--border); color: var(--muted2);
  letter-spacing: 0.06em;
  transition: border-color 0.25s, color 0.25s;
}
.team-card:hover .tag { border-color: rgba(0,229,255,0.18); color: var(--text); }
.profile-link {
  display: inline-flex; align-items: center; gap: 8px;
  font-family: var(--ff-mono); font-size: 0.7rem;
  letter-spacing: 0.1em; text-transform: uppercase;
  color: var(--cyan); transition: gap 0.25s;
}
.profile-link:hover { gap: 12px; }
.profile-link svg { width: 14px; height: 14px; stroke: currentColor; fill: none; stroke-width: 2; stroke-linecap: round; stroke-linejoin: round; }

/* ═══════════════════════════════════════
   STATS STRIP
═══════════════════════════════════════ */
.stats-strip {
  background: var(--bg3);
  border-top: 1px solid var(--border);
  border-bottom: 1px solid var(--border);
  padding: 60px 0;
}
.stats-inner {
  display: flex; justify-content: space-around; flex-wrap: wrap; gap: 40px;
}
.stat {
  text-align: center; position: relative;
}
.stat::after {
  content: '';
  position: absolute; top: 50%; right: -40px; transform: translateY(-50%);
  width: 1px; height: 50px;
  background: var(--border);
}
.stat:last-child::after { display: none; }
.stat-val {
  font-family: var(--ff-display);
  font-size: clamp(3rem, 5vw, 4.5rem);
  letter-spacing: 0.04em;
  color: var(--cyan);
  line-height: 1;
  margin-bottom: 8px;
  text-shadow: 0 0 40px var(--glow-c);
}
.stat-label { color: var(--muted2); font-size: 0.88rem; }

/* ═══════════════════════════════════════
   INTEL SCAN
═══════════════════════════════════════ */
#intelligence { background: var(--bg); }

.intel-container {
  max-width: 860px;
  margin: 3.5rem auto 0;
}

/* Terminal chrome */
.term-chrome {
  display: flex; align-items: center; gap: 12px;
  padding: 14px 22px;
  background: #050c18;
  border: 1px solid var(--border); border-bottom: none;
  border-radius: 10px 10px 0 0;
}
.term-dots { display: flex; gap: 7px; }
.term-dot { width: 12px; height: 12px; border-radius: 50%; }
.d-red    { background: var(--red); }
.d-yellow { background: var(--gold); }
.d-green  { background: #30d158; }
.term-title { font-family: var(--ff-mono); font-size: 0.7rem; color: var(--muted); letter-spacing: 0.08em; flex: 1; margin-left: 8px; }
.live-badge { display: flex; align-items: center; gap: 6px; font-family: var(--ff-mono); font-size: 0.65rem; color: var(--cyan); }
.live-dot { width: 8px; height: 8px; border-radius: 50%; background: var(--cyan); animation: livePulse 1.4s ease infinite; }
@keyframes livePulse { 0%,100%{box-shadow:0 0 0 0 var(--glow-c);} 50%{box-shadow:0 0 0 5px transparent;} }

/* Panel */
.term-panel {
  border: 1px solid var(--border);
  border-radius: 0 0 10px 10px;
  background: #030911;
  overflow: hidden; position: relative;
}
.scan-beam {
  position: absolute; left: 0; right: 0; top: 0;
  height: 2px;
  background: linear-gradient(90deg, transparent 0%, var(--cyan) 50%, transparent 100%);
  opacity: 0.5;
  animation: beamSweep 4s linear infinite;
  pointer-events: none; z-index: 5;
}
@keyframes beamSweep {
  0%   { top: 0; opacity: 0; }
  5%   { opacity: 0.5; }
  95%  { opacity: 0.5; }
  100% { top: 100%; opacity: 0; }
}

.term-prompt {
  padding: 14px 24px;
  border-bottom: 1px solid rgba(0,229,255,0.07);
  display: flex; align-items: center; justify-content: space-between;
}
.term-prompt code { font-family: var(--ff-mono); font-size: 0.75rem; color: rgba(0,229,255,0.75); }
.scan-stat { font-family: var(--ff-mono); font-size: 0.65rem; color: var(--muted); }
.scan-stat .ok { color: #30d158; }
.scan-stat .err { color: var(--red); }

.term-body {
  padding: 16px 24px 20px;
  max-height: 340px; overflow-y: auto;
}
.term-body::-webkit-scrollbar { width: 4px; }
.term-body::-webkit-scrollbar-track { background: transparent; }
.term-body::-webkit-scrollbar-thumb { background: rgba(0,229,255,0.2); border-radius: 4px; }

.intel-row { display: flex; align-items: flex-start; gap: 16px; padding: 11px 0; border-bottom: 1px solid rgba(255,255,255,0.03); }
.intel-row:last-child { border-bottom: none; }
.intel-key {
  font-family: var(--ff-mono); font-size: 0.7rem; color: var(--muted);
  letter-spacing: 0.06em; min-width: 180px; flex-shrink: 0; padding-top: 1px;
}
.intel-key::before { content: '> '; color: var(--cyan); opacity: 0.45; }
.intel-val {
  font-family: var(--ff-mono); font-size: 0.82rem; color: #c5dce8;
  word-break: break-all;
}
.intel-val.loading { color: var(--muted); }
.intel-val.loading::after { content: '█'; animation: blink 0.9s step-end infinite; font-size: 0.7rem; color: var(--cyan); opacity: 0.6; margin-left: 3px; }
.intel-val.loaded { color: #7de8f5; }
.intel-val.ip-badge {
  background: rgba(0,229,255,0.07);
  border: 1px solid rgba(0,229,255,0.2);
  border-radius: 3px; padding: 2px 10px; color: var(--cyan) !important;
}

.term-footer {
  padding: 9px 24px;
  background: rgba(0,229,255,0.025);
  border-top: 1px solid rgba(0,229,255,0.06);
  display: flex; justify-content: space-between; align-items: center;
  font-family: var(--ff-mono); font-size: 0.62rem; color: var(--muted);
}

/* ═══════════════════════════════════════
   CONTACT
═══════════════════════════════════════ */
#contact { background: var(--bg2); }

.contact-grid {
  display: grid;
  grid-template-columns: 1fr 1.3fr;
  gap: 80px; align-items: start;
  margin-top: 3.5rem;
}

.contact-info p { color: var(--muted2); margin-bottom: 2rem; font-size: 1.02rem; line-height: 1.8; }

.contact-items { display: flex; flex-direction: column; gap: 0; }
.contact-item {
  display: flex; align-items: flex-start; gap: 16px;
  padding: 18px 0;
  border-bottom: 1px solid var(--border);
}
.contact-item:first-child { border-top: 1px solid var(--border); }
.ci-icon {
  width: 36px; height: 36px; border-radius: var(--radius);
  border: 1px solid var(--border);
  display: flex; align-items: center; justify-content: center; flex-shrink: 0;
  background: rgba(0,229,255,0.04);
}
.ci-icon svg { width: 16px; height: 16px; stroke: var(--cyan); fill: none; stroke-width: 2; stroke-linecap: round; stroke-linejoin: round; }
.ci-text span { display: block; font-family: var(--ff-mono); font-size: 0.62rem; letter-spacing: 0.14em; text-transform: uppercase; color: var(--muted); margin-bottom: 2px; }
.ci-text strong { color: var(--text); font-weight: 500; font-size: 0.92rem; }

.contact-note {
  margin-top: 1.8rem; padding: 16px 20px;
  background: rgba(0,229,255,0.04);
  border: 1px solid rgba(0,229,255,0.12);
  border-radius: var(--radius);
  font-family: var(--ff-mono); font-size: 0.72rem;
  color: var(--cyan); letter-spacing: 0.05em;
}

/* Form */
.form-card {
  background: var(--bg);
  border: 1px solid var(--border);
  border-radius: 12px;
  padding: 48px 44px;
  position: relative; overflow: hidden;
}
.form-card::before {
  content: '';
  position: absolute; top: 0; left: 0; right: 0; height: 1px;
  background: linear-gradient(90deg, transparent, var(--cyan), transparent);
}

.form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 18px; }

.field { display: flex; flex-direction: column; gap: 8px; margin-bottom: 20px; }
.field label {
  font-family: var(--ff-mono); font-size: 0.65rem;
  letter-spacing: 0.14em; text-transform: uppercase; color: var(--muted2);
}
.field input, .field textarea {
  background: rgba(0,0,0,0.3);
  border: 1px solid rgba(255,255,255,0.07);
  border-radius: var(--radius);
  padding: 13px 16px;
  color: var(--text); font-family: var(--ff-body); font-size: 16px;
  width: 100%;
  transition: border-color var(--transition), background var(--transition), box-shadow var(--transition);
  -webkit-appearance: none;
}
.field input:focus, .field textarea:focus {
  outline: none;
  border-color: rgba(0,229,255,0.35);
  background: rgba(0,229,255,0.03);
  box-shadow: 0 0 0 3px rgba(0,229,255,0.06);
}
.field textarea { resize: vertical; min-height: 140px; }

.submit-btn {
  width: 100%; padding: 16px;
  background: var(--cyan); color: #030810;
  border-radius: var(--radius);
  font-family: var(--ff-mono); font-size: 0.78rem;
  font-weight: 700; letter-spacing: 0.14em; text-transform: uppercase;
  transition: box-shadow 0.25s, transform 0.25s, opacity 0.25s;
  cursor: pointer; border: none;
  box-shadow: 0 0 24px var(--glow-c);
  position: relative; overflow: hidden;
}
.submit-btn::before {
  content: '';
  position: absolute; inset: 0;
  background: linear-gradient(135deg, rgba(255,255,255,0.18), transparent 60%);
}
.submit-btn:hover { transform: translateY(-2px); box-shadow: 0 10px 36px var(--glow-c); }
.submit-btn:disabled { opacity: 0.55; cursor: not-allowed; transform: none; }

/* ═══════════════════════════════════════
   SUCCESS OVERLAY
═══════════════════════════════════════ */
#successOverlay {
  position: fixed; inset: 0;
  background: rgba(4,8,15,0.94);
  backdrop-filter: blur(14px);
  -webkit-backdrop-filter: blur(14px);
  display: flex; align-items: center; justify-content: center;
  z-index: 9999;
  opacity: 0; pointer-events: none;
  transition: opacity 0.35s;
}
#successOverlay.active { opacity: 1; pointer-events: all; }

.success-modal {
  background: var(--bg2);
  border: 1px solid var(--border-hi);
  border-radius: 14px;
  padding: 56px 48px; text-align: center;
  max-width: 420px; width: 90%;
  box-shadow: 0 0 80px rgba(0,229,255,0.18);
  transform: scale(0.88) translateY(20px);
  transition: transform 0.45s cubic-bezier(0.175, 0.885, 0.32, 1.275);
}
#successOverlay.active .success-modal { transform: scale(1) translateY(0); }

.success-icon {
  width: 84px; height: 84px; border-radius: 50%;
  border: 2px solid var(--cyan);
  margin: 0 auto 24px;
  display: flex; align-items: center; justify-content: center;
  font-size: 2.4rem; color: var(--cyan);
  box-shadow: 0 0 30px var(--glow-c);
  animation: successPop 0.5s 0.3s both;
}
@keyframes successPop { from{transform:scale(0);} to{transform:scale(1);} }
.success-modal h3 { font-family: var(--ff-display); font-size: 2rem; letter-spacing: 0.06em; color: #fff; margin-bottom: 10px; }
.success-modal p { color: var(--muted2); margin-bottom: 28px; font-size: 0.95rem; }

/* ═══════════════════════════════════════
   FOOTER
═══════════════════════════════════════ */
footer {
  background: var(--bg2);
  border-top: 1px solid var(--border);
  padding: 80px 0 40px;
}
.footer-inner {
  display: grid;
  grid-template-columns: 1.4fr 1fr 1fr;
  gap: 60px;
  padding-bottom: 60px;
  border-bottom: 1px solid var(--border);
  margin-bottom: 36px;
}

.footer-brand .footer-logo {
  font-family: var(--ff-display);
  font-size: 2rem; letter-spacing: 0.06em; color: #fff;
  margin-bottom: 12px;
}
.footer-brand .footer-logo em { font-style: normal; color: var(--cyan); }
.footer-brand p { color: var(--muted2); font-size: 0.9rem; max-width: 280px; line-height: 1.7; }

.footer-col h4 {
  font-family: var(--ff-mono); font-size: 0.68rem;
  letter-spacing: 0.18em; text-transform: uppercase; color: var(--muted);
  margin-bottom: 1.2rem;
}
.footer-col ul { display: flex; flex-direction: column; gap: 10px; }
.footer-col ul a {
  color: var(--muted2); font-size: 0.9rem;
  transition: color 0.25s;
}
.footer-col ul a:hover { color: var(--cyan); }

.footer-bottom {
  display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 14px;
}
.copyright { font-family: var(--ff-mono); font-size: 0.65rem; color: rgba(78,96,112,0.6); letter-spacing: 0.08em; }
.footer-tagline { font-family: var(--ff-mono); font-size: 0.65rem; color: var(--muted); }
.footer-tagline span { color: var(--cyan); }

/* ═══════════════════════════════════════
   ANIMATIONS
═══════════════════════════════════════ */
@keyframes fadeUp   { from{opacity:0;transform:translateY(28px);} to{opacity:1;transform:translateY(0);} }
@keyframes fadeDown { from{opacity:0;transform:translateY(-16px);} to{opacity:1;transform:translateY(0);} }

.reveal {
  opacity: 0; transform: translateY(30px);
  transition: opacity 0.75s ease, transform 0.75s ease;
}
.reveal.visible { opacity: 1; transform: translateY(0); }
.reveal-delay-1 { transition-delay: 0.1s; }
.reveal-delay-2 { transition-delay: 0.2s; }
.reveal-delay-3 { transition-delay: 0.3s; }
.reveal-delay-4 { transition-delay: 0.4s; }
.reveal-delay-5 { transition-delay: 0.5s; }

/* ═══════════════════════════════════════
   RESPONSIVE
═══════════════════════════════════════ */
@media (max-width: 1024px) {
  .services-grid { grid-template-columns: repeat(2, 1fr); }
  .footer-inner { grid-template-columns: 1fr 1fr; }
}

@media (max-width: 900px) {
  .contact-grid { grid-template-columns: 1fr; gap: 50px; }
}

@media (max-width: 768px) {
  section { padding: 80px 0; }
  .hamburger { display: flex; }
  .mobile-nav { display: flex; }
  .nav-links { display: none; }

  .services-grid { grid-template-columns: 1fr; }
  .form-row { grid-template-columns: 1fr; }
  .footer-inner { grid-template-columns: 1fr; gap: 40px; }
  .footer-bottom { flex-direction: column; text-align: center; }

  .stats-inner { gap: 30px; }
  .stat::after { display: none; }

  .form-card { padding: 32px 24px; }
  .hero-actions .btn { width: 100%; max-width: 320px; }

  .intel-row { flex-direction: column; gap: 3px; }
  .intel-key { min-width: auto; }
}

@media (max-width: 480px) {
  .hero-title { font-size: 2.8rem; }
  .services-intro { flex-direction: column; }
}
</style>
</head>
<body>

<!-- PRELOADER -->
<div id="preloader" role="status" aria-label="Loading">
  <div class="loader-logo">RH²</div>
  <div class="loader-bar"><div class="loader-fill"></div></div>
</div>

<!-- SUCCESS OVERLAY -->
<div id="successOverlay" role="dialog" aria-modal="true" aria-label="Submission confirmed">
  <div class="success-modal">
    <div class="success-icon" aria-hidden="true">✓</div>
    <h3>Transmission Secured</h3>
    <p>Your message has been encrypted and delivered to RH²-Systems servers.</p>
    <button class="submit-btn" id="closeSuccess" style="max-width:200px;margin:auto;display:block;">Acknowledge</button>
  </div>
</div>

<!-- SCROLL TO TOP -->
<button id="scrollTop" aria-label="Scroll to top" title="Back to top">
  <svg viewBox="0 0 24 24" width="18" height="18" stroke="currentColor" fill="none" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="18 15 12 9 6 15"/></svg>
</button>

<!-- HEADER -->
<header id="header">
  <div class="container">
    <nav role="navigation" aria-label="Main navigation">
      <a href="#" class="logo" aria-label="RH²-Systems home">RH²-<em>Systems</em></a>

      <ul class="nav-links" role="list">
        <li><a href="#services">Services</a></li>
        <li><a href="#team">Team</a></li>
        <li><a href="#methodology">Methodology</a></li>
        <li><a href="#intelligence">Intel Scan</a></li>
        <li class="nav-cta-wrap"><a href="#contact" class="btn btn-primary btn-sm">Contact</a></li>
      </ul>

      <button class="hamburger" id="hamburger" aria-label="Toggle menu" aria-expanded="false">
        <span></span><span></span><span></span>
      </button>
    </nav>
  </div>
</header>

<!-- MOBILE NAV -->
<nav class="mobile-nav" id="mobileNav" aria-label="Mobile navigation">
  <a href="#services" class="mobile-link">Services</a>
  <a href="#team" class="mobile-link">Team</a>
  <a href="#methodology" class="mobile-link">Methodology</a>
  <a href="#intelligence" class="mobile-link">Intel Scan</a>
  <a href="#contact" class="mobile-link">Contact</a>
</nav>

<!-- HERO -->
<section class="hero" aria-label="Hero section">
  <div class="hero-grid" aria-hidden="true"></div>
  <div class="hero-glow-a" aria-hidden="true"></div>
  <div class="hero-glow-b" aria-hidden="true"></div>
  <canvas id="networkCanvas" aria-hidden="true"></canvas>

  <div class="container hero-content">
    <div class="status-pill" aria-label="System status: secure">
      <span class="pulse-dot" aria-hidden="true"></span>
      SYSTEM STATUS: SECURE
    </div>

    <h1 class="hero-title" aria-live="polite">
      OFFENSIVE<br>SECURITY.
      <span class="line-accent"><span id="typeText"></span><span class="cursor" aria-hidden="true"></span></span>
      <span class="line-red">RH²-SYSTEMS</span>
    </h1>

    <p class="hero-desc">Advanced penetration testing, red team operations, and secure engineering for high-risk enterprise infrastructure.</p>

    <div class="hero-actions">
      <a href="#contact" class="btn btn-primary">
        <svg viewBox="0 0 24 24" width="16" height="16" stroke="currentColor" fill="none" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg>
        Initiate Confidential Audit
      </a>
      <a href="#services" class="btn btn-ghost">
        Explore Capabilities
        <svg viewBox="0 0 24 24" width="15" height="15" stroke="currentColor" fill="none" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="9 18 15 12 9 6"/></svg>
      </a>
    </div>
  </div>

  <div class="scroll-hint" aria-hidden="true">
    <div class="scroll-line"></div>
    Scroll
  </div>
</section>

<!-- SERVICES -->
<section id="services" aria-labelledby="services-heading">
  <div class="container">
    <div class="services-intro">
      <div class="reveal">
        <span class="label">01 — Capabilities</span>
        <h2 class="section-title" id="services-heading">Core Security<br><span>Services</span></h2>
      </div>
      <p class="section-sub reveal reveal-delay-1">Full-spectrum offensive security tailored for modern threat landscapes and enterprise-grade infrastructure.</p>
    </div>

    <div class="services-grid">
      <!-- SVC 1 -->
      <div class="svc-card reveal">
        <div class="svc-icon" aria-hidden="true">
          <svg viewBox="0 0 24 24"><circle cx="11" cy="11" r="8"/><line x1="21" y1="21" x2="16.65" y2="16.65"/></svg>
        </div>
        <div class="svc-num">SVC_001</div>
        <h3>Penetration Testing</h3>
        <p>Manual and automated assessments of Web, Mobile, API, and Cloud infrastructure aligned with OWASP Top 10 and NIST frameworks.</p>
      </div>
      <!-- SVC 2 -->
      <div class="svc-card reveal reveal-delay-1">
        <div class="svc-icon" aria-hidden="true">
          <svg viewBox="0 0 24 24"><polygon points="13 2 3 14 12 14 11 22 21 10 12 10 13 2"/></svg>
        </div>
        <div class="svc-num">SVC_002</div>
        <h3>Red Team Operations</h3>
        <p>Adversary simulation replicating nation-state APT tactics to test your detection and response capabilities in real-time scenarios.</p>
      </div>
      <!-- SVC 3 -->
      <div class="svc-card reveal reveal-delay-2">
        <div class="svc-icon" aria-hidden="true">
          <svg viewBox="0 0 24 24"><polyline points="16 18 22 12 16 6"/><polyline points="8 6 2 12 8 18"/></svg>
        </div>
        <div class="svc-num">SVC_003</div>
        <h3>Secure Engineering</h3>
        <p>DevSecOps integration, Zero Trust architecture design, and source code review to embed security into the DNA of your software.</p>
      </div>
      <!-- SVC 4 -->
      <div class="svc-card reveal reveal-delay-3">
        <div class="svc-icon" aria-hidden="true">
          <svg viewBox="0 0 24 24"><path d="M22 12h-4l-3 9L9 3l-3 9H2"/></svg>
        </div>
        <div class="svc-num">SVC_004</div>
        <h3>Incident Response</h3>
        <p>Continuous threat monitoring, log analysis, and rapid breach containment to detect and remediate security incidents before they escalate.</p>
      </div>
      <!-- SVC 5 -->
      <div class="svc-card reveal reveal-delay-4">
        <div class="svc-icon" aria-hidden="true">
          <svg viewBox="0 0 24 24"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg>
        </div>
        <div class="svc-num">SVC_005</div>
        <h3>Threat Modeling</h3>
        <p>Identify and prioritize potential attack vectors and system weaknesses before adversaries exploit them using structured risk analysis.</p>
      </div>
      <!-- SVC 6 -->
      <div class="svc-card reveal reveal-delay-5">
        <div class="svc-icon" aria-hidden="true">
          <svg viewBox="0 0 24 24"><rect x="3" y="3" width="18" height="18" rx="2"/><line x1="9" y1="3" x2="9" y2="21"/><line x1="15" y1="3" x2="15" y2="21"/><line x1="3" y1="9" x2="21" y2="9"/><line x1="3" y1="15" x2="21" y2="15"/></svg>
        </div>
        <div class="svc-num">SVC_006</div>
        <h3>Architecture Review</h3>
        <p>Comprehensive evaluation of system design, trust boundaries, and defensive controls to expose structural weaknesses before they become exploitable.</p>
      </div>
    </div>
  </div>
</section>

<!-- STATS STRIP -->
<section id="methodology" class="stats-strip" aria-labelledby="methodology-heading">
  <div class="container">
    <div class="reveal" style="text-align:center;margin-bottom:3rem;">
      <span class="label" style="justify-content:center;">03 — Methodology</span>
      <h2 class="section-title" id="methodology-heading">The RH² <span>Standard</span></h2>
      <p class="section-sub" style="margin:auto;text-align:center;">Measurable, repeatable, and fully confidential security assessments.</p>
    </div>
    <div class="stats-inner reveal reveal-delay-1" role="list">
      <div class="stat" role="listitem">
        <div class="stat-val" aria-label="150 plus engagements">150+</div>
        <div class="stat-label">Engagements Delivered</div>
      </div>
      <div class="stat" role="listitem">
        <div class="stat-val">100%</div>
        <div class="stat-label">Confidentiality Record</div>
      </div>
      <div class="stat" role="listitem">
        <div class="stat-val">24/7</div>
        <div class="stat-label">Incident Support</div>
      </div>
      <div class="stat" role="listitem">
        <div class="stat-val" aria-label="Zero client data breaches">0</div>
        <div class="stat-label">Client Data Breaches</div>
      </div>
    </div>
  </div>
</section>

<!-- TEAM -->
<section id="team" aria-labelledby="team-heading">
  <div class="container">
    <div class="reveal" style="text-align:center;margin-bottom:0;">
      <span class="label" style="justify-content:center;">02 — Leadership</span>
      <h2 class="section-title" id="team-heading">Engineering &amp; <span>Command</span></h2>
      <p class="section-sub" style="margin:auto;text-align:center;">Built by engineers who understand both the attack vector and the defense mechanism.</p>
    </div>

    <div class="team-grid">
      <!-- Raj Hridoy -->
      <article class="team-card reveal reveal-delay-1">
        <div class="team-header">
          <div class="avatar" aria-hidden="true">RH</div>
          <div class="team-meta">
            <h3>Raj Hridoy</h3>
            <span class="role">Cybersecurity Engineer</span>
          </div>
        </div>
        <div class="team-body">
          <p>Specializing in secure software architecture and complex vulnerability analysis. Raj bridges high-level development with low-level security protocols.</p>
          <div class="tags" aria-label="Skills">
            <span class="tag">Secure Arch</span>
            <span class="tag">Python / Go</span>
            <span class="tag">Cloud Security</span>
            <span class="tag">DevSecOps</span>
          </div>
          <a href="https://rh-systems.github.io/Raj-Hridoy/" class="profile-link" target="_blank" rel="noopener noreferrer" aria-label="View Raj Hridoy's profile">
            View Profile
            <svg viewBox="0 0 24 24"><line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/></svg>
          </a>
        </div>
      </article>

      <!-- Riyad Hasan -->
      <article class="team-card reveal reveal-delay-2">
        <div class="team-header">
          <div class="avatar" aria-hidden="true">RH</div>
          <div class="team-meta">
            <h3>Riyad Hasan</h3>
            <span class="role">Ethical Hacker</span>
          </div>
        </div>
        <div class="team-body">
          <p>Focused on advanced threat modeling and penetration testing. Riyad specializes in breaking systems to make them unbreakable through adversarial analysis.</p>
          <div class="tags" aria-label="Skills">
            <span class="tag">PenTesting</span>
            <span class="tag">Network Forensics</span>
            <span class="tag">Red Teaming</span>
            <span class="tag">Exploit Dev</span>
          </div>
          <a href="https://rh-systems.github.io/Riyad-Hasan/" class="profile-link" target="_blank" rel="noopener noreferrer" aria-label="View Riyad Hasan's profile">
            View Profile
            <svg viewBox="0 0 24 24"><line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/></svg>
          </a>
        </div>
      </article>
    </div>
  </div>
</section>

<!-- INTEL SCAN -->
<section id="intelligence" aria-labelledby="intel-heading">
  <div class="container">
    <div class="reveal" style="text-align:center;">
      <span class="label" style="justify-content:center;">04 — Telemetry</span>
      <h2 class="section-title" id="intel-heading">Network <span>Intelligence</span> Scan</h2>
      <p class="section-sub" style="margin:auto 0 0;text-align:center;">Real-time analysis of your active connection — demonstrating the kind of reconnaissance performed during a security assessment.</p>
    </div>

    <div class="intel-container reveal reveal-delay-1" role="region" aria-label="Network intelligence scan results">
      <div class="term-chrome" aria-hidden="true">
        <div class="term-dots">
          <div class="term-dot d-red"></div>
          <div class="term-dot d-yellow"></div>
          <div class="term-dot d-green"></div>
        </div>
        <span class="term-title">rh2sys_telemetry — bash</span>
        <div class="live-badge"><div class="live-dot"></div>LIVE</div>
      </div>

      <div class="term-panel">
        <div class="scan-beam" aria-hidden="true"></div>

        <div class="term-prompt" aria-hidden="true">
          <code>$ ./network_scan --target=self --verbose</code>
          <div class="scan-stat"><span id="scanStatusText">Scanning...</span></div>
        </div>

        <div class="term-body" role="table" aria-label="Scan results">
          <div class="intel-row" role="row">
            <span class="intel-key" role="rowheader">IP Address</span>
            <span class="intel-val loading" id="intel-ip" role="cell" aria-live="polite">Initiating scan...</span>
          </div>
          <div class="intel-row" role="row">
            <span class="intel-key" role="rowheader">Country</span>
            <span class="intel-val loading" id="intel-country" role="cell" aria-live="polite">Resolving geolocation...</span>
          </div>
          <div class="intel-row" role="row">
            <span class="intel-key" role="rowheader">City / Region</span>
            <span class="intel-val loading" id="intel-city" role="cell" aria-live="polite">Resolving geolocation...</span>
          </div>
          <div class="intel-row" role="row">
            <span class="intel-key" role="rowheader">ISP / Network</span>
            <span class="intel-val loading" id="intel-isp" role="cell" aria-live="polite">Querying ASN database...</span>
          </div>
          <div class="intel-row" role="row">
            <span class="intel-key" role="rowheader">Timezone</span>
            <span class="intel-val loading" id="intel-timezone" role="cell" aria-live="polite">Calculating offset...</span>
          </div>
          <div class="intel-row" role="row">
            <span class="intel-key" role="rowheader">Browser</span>
            <span class="intel-val" id="intel-browser" role="cell">Detecting...</span>
          </div>
          <div class="intel-row" role="row">
            <span class="intel-key" role="rowheader">Operating System</span>
            <span class="intel-val" id="intel-os" role="cell">Detecting...</span>
          </div>
          <div class="intel-row" role="row">
            <span class="intel-key" role="rowheader">Screen / DPI</span>
            <span class="intel-val" id="intel-screen" role="cell">Detecting...</span>
          </div>
        </div>

        <div class="term-footer" aria-hidden="true">
          <span>RH²-SYS TELEMETRY v3.1 · HTTPS ENCRYPTED</span>
          <span id="intelTimestamp"></span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact" aria-labelledby="contact-heading">
  <div class="container">
    <div class="reveal">
      <span class="label">05 — Contact</span>
      <h2 class="section-title" id="contact-heading">Secure <span>Consultation</span></h2>
    </div>

    <div class="contact-grid">
      <div class="reveal reveal-delay-1">
        <p class="contact-info" style="color:var(--muted2);margin-bottom:2rem;font-size:1.02rem;line-height:1.8;">Ready to fortify your infrastructure? Contact us for a confidential discussion regarding your security posture and threat exposure.</p>

        <div class="contact-items">
          <div class="contact-item">
            <div class="ci-icon" aria-hidden="true">
              <svg viewBox="0 0 24 24"><path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"/><circle cx="12" cy="10" r="3"/></svg>
            </div>
            <div class="ci-text">
              <span>Location</span>
              <strong>Rajshahi Division, Bangladesh</strong>
            </div>
          </div>
          <div class="contact-item">
            <div class="ci-icon" aria-hidden="true">
              <svg viewBox="0 0 24 24"><circle cx="12" cy="12" r="10"/><polyline points="12 6 12 12 16 14"/></svg>
            </div>
            <div class="ci-text">
              <span>Availability</span>
              <strong>24 / 7 Incident Support</strong>
            </div>
          </div>
          <div class="contact-item">
            <div class="ci-icon" aria-hidden="true">
              <svg viewBox="0 0 24 24"><rect x="3" y="11" width="18" height="11" rx="2" ry="2"/><path d="M7 11V7a5 5 0 0 1 10 0v4"/></svg>
            </div>
            <div class="ci-text">
              <span>Channels</span>
              <strong>Encrypted comms available on request</strong>
            </div>
          </div>
        </div>

        <div class="contact-note">
          &gt; All submissions are end-to-end encrypted via Firebase.
        </div>
      </div>

      <div class="form-card reveal reveal-delay-2">
        <form id="contactForm" novalidate aria-label="Contact form">
          <div class="form-row">
            <div class="field">
              <label for="f-name">Full Name / Organization</label>
              <input type="text" id="f-name" name="name" placeholder="Acme Corp / Jane Doe" required autocomplete="name">
            </div>
            <div class="field">
              <label for="f-email">Work Email</label>
              <input type="email" id="f-email" name="email" placeholder="security@yourcompany.com" required autocomplete="email">
            </div>
          </div>
          <div class="field">
            <label for="f-msg">Project Scope / Details</label>
            <textarea id="f-msg" name="message" rows="5" placeholder="Describe your infrastructure and security goals..." required></textarea>
          </div>
          <button type="submit" class="submit-btn" id="submitBtn">
            Transmit Encrypted Request
          </button>
        </form>
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="container">
    <div class="footer-inner">
      <div class="footer-brand">
        <div class="footer-logo">RH²-<em>Systems</em></div>
        <p>Enterprise-grade cybersecurity and offensive security operations for high-risk infrastructure worldwide.</p>
      </div>
      <div class="footer-col">
        <h4>Services</h4>
        <ul>
          <li><a href="#services">Penetration Testing</a></li>
          <li><a href="#services">Red Team Operations</a></li>
          <li><a href="#services">Secure Engineering</a></li>
          <li><a href="#services">Incident Response</a></li>
          <li><a href="#services">Threat Modeling</a></li>
          <li><a href="#services">Architecture Review</a></li>
        </ul>
      </div>
      <div class="footer-col">
        <h4>Company</h4>
        <ul>
          <li><a href="#team">Our Team</a></li>
          <li><a href="#methodology">Methodology</a></li>
          <li><a href="#intelligence">Intel Scan</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </div>
    </div>
    <div class="footer-bottom">
      <div class="copyright">© 2026 RH²-Systems · All Rights Reserved · Confidentiality Guaranteed</div>
      <div class="footer-tagline">Rajshahi Division, Bangladesh · <span>Offensive Security</span></div>
    </div>
  </div>
</footer>

<!-- ══════════════════════════
     JAVASCRIPT
══════════════════════════ -->
<script>
/* PRELOADER */
window.addEventListener('load', () => {
  setTimeout(() => {
    document.getElementById('preloader').classList.add('hidden');
  }, 1300);
});

/* HEADER SCROLL */
const header = document.getElementById('header');
window.addEventListener('scroll', () => {
  header.classList.toggle('scrolled', window.scrollY > 20);
});

/* SCROLL TO TOP */
const scrollTopBtn = document.getElementById('scrollTop');
window.addEventListener('scroll', () => {
  scrollTopBtn.classList.toggle('visible', window.scrollY > 400);
});
scrollTopBtn.addEventListener('click', () => window.scrollTo({ top: 0, behavior: 'smooth' }));

/* MOBILE NAV */
const hamburger = document.getElementById('hamburger');
const mobileNav = document.getElementById('mobileNav');
hamburger.addEventListener('click', () => {
  const isOpen = mobileNav.classList.toggle('open');
  hamburger.classList.toggle('active', isOpen);
  hamburger.setAttribute('aria-expanded', isOpen);
  document.body.style.overflow = isOpen ? 'hidden' : '';
});
document.querySelectorAll('.mobile-link').forEach(a => {
  a.addEventListener('click', () => {
    mobileNav.classList.remove('open');
    hamburger.classList.remove('active');
    hamburger.setAttribute('aria-expanded', 'false');
    document.body.style.overflow = '';
  });
});

/* REVEAL ON SCROLL */
const revealObserver = new IntersectionObserver((entries) => {
  entries.forEach(e => { if (e.isIntersecting) e.target.classList.add('visible'); });
}, { threshold: 0.07 });
document.querySelectorAll('.reveal').forEach(el => revealObserver.observe(el));

/* TYPEWRITER */
(function() {
  const words = ['Infrastructure Auditing.', 'Secure Engineering.', 'Red Team Operations.', 'Exploit Development.'];
  const el = document.getElementById('typeText');
  let wi = 0, ci = 0, del = false;
  const TYPE = 55, DEL = 28, PAUSE = 2200;
  function tick() {
    const word = words[wi];
    if (del) { el.textContent = word.substring(0, --ci); }
    else { el.textContent = word.substring(0, ++ci); }
    let delay = del ? DEL : TYPE;
    if (!del && ci === word.length) { delay = PAUSE; del = true; }
    if (del && ci === 0) { del = false; wi = (wi + 1) % words.length; }
    setTimeout(tick, delay);
  }
  tick();
})();

/* PARTICLE NETWORK CANVAS */
(function() {
  const canvas = document.getElementById('networkCanvas');
  const ctx = canvas.getContext('2d');
  const DPR = Math.min(window.devicePixelRatio || 1, 2);
  let W, H, particles = [];
  const mouse = { x: null, y: null };

  function resize() {
    const parent = canvas.parentElement;
    W = parent.offsetWidth; H = parent.offsetHeight;
    canvas.width = W * DPR; canvas.height = H * DPR;
    canvas.style.width = W + 'px'; canvas.style.height = H + 'px';
    ctx.scale(DPR, DPR);
    init();
  }
  function init() {
    particles = [];
    const n = Math.floor((W * H) / 10000);
    for (let i = 0; i < n; i++) particles.push(new Particle());
  }
  class Particle {
    constructor() { this.reset(); }
    reset() {
      this.x = Math.random() * W; this.y = Math.random() * H;
      this.vx = (Math.random() - 0.5) * 0.6; this.vy = (Math.random() - 0.5) * 0.6;
      this.r = Math.random() * 1.6 + 0.5;
    }
    update() {
      this.x += this.vx; this.y += this.vy;
      if (this.x < 0 || this.x > W) this.vx *= -1;
      if (this.y < 0 || this.y > H) this.vy *= -1;
      if (mouse.x !== null) {
        const dx = this.x - mouse.x, dy = this.y - mouse.y;
        const d = Math.sqrt(dx * dx + dy * dy);
        if (d < 120) { this.x += dx / d * 1.5; this.y += dy / d * 1.5; }
      }
    }
    draw() {
      ctx.beginPath();
      ctx.arc(this.x, this.y, this.r, 0, Math.PI * 2);
      ctx.fillStyle = '#00e5ff'; ctx.fill();
    }
  }
  function connect() {
    const maxD2 = (W / 6) * (H / 6);
    for (let a = 0; a < particles.length; a++) {
      for (let b = a + 1; b < particles.length; b++) {
        const dx = particles[a].x - particles[b].x;
        const dy = particles[a].y - particles[b].y;
        const d2 = dx * dx + dy * dy;
        if (d2 < maxD2) {
          ctx.strokeStyle = `rgba(0,229,255,${(1 - d2 / maxD2) * 0.35})`;
          ctx.lineWidth = 0.7;
          ctx.beginPath();
          ctx.moveTo(particles[a].x, particles[a].y);
          ctx.lineTo(particles[b].x, particles[b].y);
          ctx.stroke();
        }
      }
    }
  }
  function animate() {
    ctx.clearRect(0, 0, W, H);
    particles.forEach(p => { p.update(); p.draw(); });
    connect();
    requestAnimationFrame(animate);
  }
  window.addEventListener('resize', resize);
  window.addEventListener('mousemove', e => { mouse.x = e.clientX; mouse.y = e.clientY; });
  window.addEventListener('touchmove', e => {
    if (e.touches.length) { mouse.x = e.touches[0].clientX; mouse.y = e.touches[0].clientY; }
  }, { passive: true });
  resize(); animate();
})();

/* INTEL SCAN */
(function() {
  function setVal(id, val, isIp) {
    const el = document.getElementById(id);
    if (!el) return;
    el.textContent = val || 'Unknown';
    el.classList.remove('loading');
    el.classList.add('loaded');
    if (isIp) el.classList.add('ip-badge');
  }
  function setFailed() {
    ['intel-ip','intel-country','intel-city','intel-isp','intel-timezone'].forEach(id => setVal(id, 'Data Unavailable'));
    const s = document.getElementById('scanStatusText');
    if (s) { s.textContent = 'SCAN FAILED'; s.classList.add('err'); }
  }

  const ua = navigator.userAgent;
  let browser = 'Unknown', os = 'Unknown OS';
  if (/SamsungBrowser/i.test(ua)) browser = 'Samsung Internet';
  else if (/OPR|Opera/i.test(ua)) browser = 'Opera';
  else if (/Trident/i.test(ua)) browser = 'Internet Explorer 11';
  else if (/Edg\//i.test(ua)) browser = 'Microsoft Edge';
  else if (/Firefox\/\d/i.test(ua)) browser = 'Mozilla Firefox';
  else if (/Chrome\/\d/i.test(ua)) browser = 'Google Chrome';
  else if (/Safari\/\d/i.test(ua)) browser = 'Apple Safari';

  if (/Android/i.test(ua)) os = 'Android';
  else if (/iPhone|iPad|iPod/i.test(ua)) os = 'iOS';
  else if (/Windows NT 10/i.test(ua)) os = 'Windows 10 / 11';
  else if (/Windows/i.test(ua)) os = 'Windows';
  else if (/Mac OS X/i.test(ua)) os = 'macOS';
  else if (/Linux/i.test(ua)) os = 'Linux';
  else if (/X11/i.test(ua)) os = 'UNIX';

  const bEl = document.getElementById('intel-browser');
  const oEl = document.getElementById('intel-os');
  const sEl = document.getElementById('intel-screen');
  if (bEl) { bEl.textContent = browser; bEl.classList.add('loaded'); }
  if (oEl) { oEl.textContent = os; oEl.classList.add('loaded'); }
  if (sEl) { sEl.textContent = `${screen.width} × ${screen.height} @ ${window.devicePixelRatio || 1}x DPI`; sEl.classList.add('loaded'); }

  const tsEl = document.getElementById('intelTimestamp');
  if (tsEl) tsEl.textContent = 'SCAN INIT: ' + new Date().toISOString().replace('T',' ').split('.')[0] + ' UTC';

  const ctrl = new AbortController();
  const to = setTimeout(() => ctrl.abort(), 8000);

  fetch('https://ipwho.is/', { signal: ctrl.signal })
    .then(r => { if (!r.ok) throw 0; return r.json(); })
    .then(d => {
      clearTimeout(to);
      if (!d.success) throw 0;
      setVal('intel-ip', d.ip, true);
      setVal('intel-country', `${d.country} (${d.country_code || ''})`);
      setVal('intel-city', `${d.city || '—'}, ${d.region || '—'}`);
      setVal('intel-isp', d.connection?.isp || d.connection?.org || d.org || 'Unknown');
      setVal('intel-timezone', d.timezone?.id || d.timezone || 'Unknown');
      const s = document.getElementById('scanStatusText');
      if (s) { s.textContent = 'SCAN COMPLETE ✓'; s.classList.add('ok'); }
    })
    .catch(() => {
      fetch('https://ipapi.co/json/', { signal: ctrl.signal })
        .then(r => { if (!r.ok) throw 0; return r.json(); })
        .then(d => {
          clearTimeout(to);
          if (d.error) throw 0;
          setVal('intel-ip', d.ip, true);
          setVal('intel-country', `${d.country_name} (${d.country_code})`);
          setVal('intel-city', `${d.city || '—'}, ${d.region || '—'}`);
          setVal('intel-isp', d.org || d.asn || 'Unknown');
          setVal('intel-timezone', d.timezone || 'Unknown');
          const s = document.getElementById('scanStatusText');
          if (s) { s.textContent = 'SCAN COMPLETE ✓'; s.classList.add('ok'); }
        })
        .catch(() => {
          fetch('https://ipinfo.io/json', { signal: ctrl.signal })
            .then(r => { if (!r.ok) throw 0; return r.json(); })
            .then(d => {
              clearTimeout(to);
              setVal('intel-ip', d.ip, true);
              setVal('intel-country', d.country || 'Unknown');
              setVal('intel-city', `${d.city || '—'}, ${d.region || '—'}`);
              setVal('intel-isp', d.org || 'Unknown');
              setVal('intel-timezone', d.timezone || 'Unknown');
              const s = document.getElementById('scanStatusText');
              if (s) { s.textContent = 'SCAN COMPLETE ✓'; s.classList.add('ok'); }
            })
            .catch(() => { clearTimeout(to); setFailed(); });
        });
    });
})();
</script>

<!-- FIREBASE CONTACT FORM -->
<script type="module">
import { initializeApp }                    from "https://www.gstatic.com/firebasejs/12.9.0/firebase-app.js";
import { getFirestore, collection, addDoc } from "https://www.gstatic.com/firebasejs/12.9.0/firebase-firestore.js";

const firebaseConfig = {
  apiKey:            "AIzaSyBl4bO6hNumDov3d26YNFj1y7Id498rBTU",
  authDomain:        "rh2-systems.firebaseapp.com",
  projectId:         "rh2-systems",
  storageBucket:     "rh2-systems.firebasestorage.app",
  messagingSenderId: "492917852953",
  appId:             "1:492917852953:web:9fc6ff86f6fcd2fc965388",
  measurementId:     "G-RRHPV2Y2S9"
};

const app = initializeApp(firebaseConfig);
const db  = getFirestore(app);

const overlay      = document.getElementById('successOverlay');
const closeSuccess = document.getElementById('closeSuccess');
closeSuccess.addEventListener('click', () => overlay.classList.remove('active'));
overlay.addEventListener('click', e => { if (e.target === overlay) overlay.classList.remove('active'); });

const form      = document.getElementById('contactForm');
const submitBtn = document.getElementById('submitBtn');

form.addEventListener('submit', async (e) => {
  e.preventDefault();
  const name    = document.getElementById('f-name').value.trim();
  const email   = document.getElementById('f-email').value.trim();
  const message = document.getElementById('f-msg').value.trim();
  if (!name || !email || !message) return;

  submitBtn.textContent = 'ENCRYPTING...';
  submitBtn.disabled = true;

  try {
    await addDoc(collection(db, 'messages'), {
      name, email, message,
      timestamp: new Date(),
      source: 'rh2-systems.com'
    });
    form.reset();
    overlay.classList.add('active');
  } catch (err) {
    console.error('Firebase error:', err);
    alert('Transmission failed: ' + err.message);
  } finally {
    submitBtn.textContent = 'Transmit Encrypted Request';
    submitBtn.disabled = false;
  }
});
</script>
</body>
</html>
