<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=5.0">
<title>RH²-Systems | Enterprise Cybersecurity & Offensive Security</title>
<meta name="description" content="RH²-Systems delivers enterprise-grade penetration testing, red teaming, and secure infrastructure auditing for high-risk environments.">
<meta name="author" content="RH²-Systems">
<link rel="canonical" href="https://rh2-systems.com/">

<!-- Open Graph -->
<meta property="og:title" content="RH²-Systems | Enterprise Cybersecurity">
<meta property="og:description" content="Advanced penetration testing, red team operations, and secure engineering for high-risk enterprise infrastructure.">
<meta property="og:type" content="website">
<meta property="og:url" content="https://rh2-systems.com/">

<!-- Fonts: Distinctive display + mono pairing -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;700&family=Syne:wght@700;800&family=IBM+Plex+Mono:wght@400;700&display=swap" rel="stylesheet">

<style>
/* ═══════════════════════════════════════════════
   DESIGN TOKENS
═══════════════════════════════════════════════ */
:root {
  --bg:        #03070f;
  --bg-card:   #080f1e;
  --bg-glass:  rgba(8,15,30,0.75);
  --accent:    #00e5ff;
  --accent2:   #ff2d55;
  --glow:      rgba(0,229,255,0.35);
  --glow2:     rgba(255,45,85,0.3);
  --text:      #e8edf5;
  --muted:     #5a6a80;
  --border:    rgba(0,229,255,0.12);
  --border-hi: rgba(0,229,255,0.5);
  --ff-head:   'Syne', sans-serif;
  --ff-body:   'Space Grotesk', sans-serif;
  --ff-mono:   'IBM Plex Mono', monospace;
}

/* ═══════════════════════════════════════════════
   RESET & BASE
═══════════════════════════════════════════════ */
*, *::before, *::after { margin:0; padding:0; box-sizing:border-box; -webkit-tap-highlight-color:transparent; }
html { scroll-behavior:smooth; }
body {
  background: var(--bg);
  color: var(--text);
  font-family: var(--ff-body);
  font-size: 1rem;
  line-height: 1.7;
  overflow-x: hidden;
}

/* Dot-grid texture overlay */
body::before {
  content:'';
  position:fixed; inset:0;
  background-image: radial-gradient(rgba(0,229,255,0.06) 1px, transparent 1px);
  background-size: 40px 40px;
  pointer-events:none;
  z-index:0;
}

a { text-decoration:none; color:inherit; }
img { display:block; max-width:100%; }
button { font-family:var(--ff-body); cursor:pointer; border:none; background:none; }

/* ═══════════════════════════════════════════════
   TYPOGRAPHY
═══════════════════════════════════════════════ */
h1, h2, h3, h4 { font-family:var(--ff-head); font-weight:800; letter-spacing:-0.03em; line-height:1.1; }

.section-label {
  font-family: var(--ff-mono);
  font-size: 0.72rem;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  color: var(--accent);
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 1rem;
}
.section-label::before {
  content: '';
  display: inline-block;
  width: 28px; height: 1px;
  background: var(--accent);
  box-shadow: 0 0 8px var(--accent);
}

.section-title {
  font-size: clamp(2rem, 4vw, 3rem);
  background: linear-gradient(135deg, #fff 40%, #5a7a99);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  margin-bottom: 1rem;
}

/* ═══════════════════════════════════════════════
   LAYOUT
═══════════════════════════════════════════════ */
.container { width:min(1200px, 90%); margin:auto; padding:0 20px; }
section { padding: 110px 0; position:relative; z-index:1; }

/* ═══════════════════════════════════════════════
   HEADER / NAV
═══════════════════════════════════════════════ */
header {
  position: fixed; top:0; left:0; right:0; z-index:1000;
  height: 72px;
  background: rgba(3,7,15,0.88);
  backdrop-filter: blur(20px);
  -webkit-backdrop-filter: blur(20px);
  border-bottom: 1px solid var(--border);
}
nav {
  height:100%;
  display:flex; justify-content:space-between; align-items:center;
}
.logo {
  font-family: var(--ff-head);
  font-size: 1.4rem;
  font-weight: 800;
  letter-spacing: -0.04em;
}
.logo em { font-style:normal; color: var(--accent); text-shadow:0 0 14px var(--glow); }

.nav-links { display:flex; gap:36px; list-style:none; }
.nav-links a {
  font-family: var(--ff-mono);
  font-size: 0.72rem;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: var(--muted);
  transition: color 0.25s;
}
.nav-links a:hover { color: var(--accent); }

/* CTA in nav */
.nav-cta {
  font-family: var(--ff-mono) !important;
  font-size: 0.72rem !important;
  padding: 8px 18px;
  border: 1px solid var(--accent) !important;
  border-radius: 3px;
  color: var(--accent) !important;
  transition: background 0.25s, box-shadow 0.25s !important;
}
.nav-cta:hover { background: rgba(0,229,255,0.08) !important; box-shadow: 0 0 14px var(--glow) !important; }

.menu-toggle {
  display:none;
  font-size:1.6rem;
  color: var(--text);
  user-select:none;
  padding:4px;
}

/* ═══════════════════════════════════════════════
   HERO
═══════════════════════════════════════════════ */
.hero {
  min-height: 100vh;
  min-height: 100dvh;
  display:flex; align-items:center; justify-content:center;
  text-align:center;
  padding-top: 72px;
  overflow:hidden;
  position:relative;
}
#networkCanvas {
  position:absolute; inset:0;
  width:100%; height:100%;
  z-index:1;
  opacity:0.55;
  pointer-events:none;
}
/* Red sweep vignette */
.hero::after {
  content:'';
  position:absolute; inset:0;
  background: radial-gradient(ellipse 70% 60% at 50% 110%, rgba(255,45,85,0.08), transparent 70%),
              radial-gradient(ellipse 60% 50% at 80% 20%, rgba(0,229,255,0.05), transparent 60%);
  pointer-events:none;
  z-index:1;
}
.hero-content {
  position:relative; z-index:2;
  max-width: 860px; width:100%;
}
.status-badge {
  display:inline-flex; align-items:center; gap:10px;
  padding: 6px 16px;
  border: 1px solid var(--border-hi);
  border-radius: 2px;
  background: rgba(0,229,255,0.05);
  font-family: var(--ff-mono);
  font-size: 0.7rem;
  letter-spacing:0.18em;
  color: var(--accent);
  text-transform:uppercase;
  margin-bottom:2rem;
  box-shadow: 0 0 20px var(--glow);
}
.status-dot {
  width: 7px; height: 7px;
  background: var(--accent);
  border-radius: 50%;
  animation: statusPulse 2s ease-in-out infinite;
  box-shadow: 0 0 8px var(--accent);
}
@keyframes statusPulse {
  0%,100% { opacity:1; transform:scale(1); }
  50%      { opacity:0.3; transform:scale(0.75); }
}

.hero h1 {
  font-size: clamp(2.6rem, 6vw, 5rem);
  line-height: 1.05;
  margin-bottom: 1.5rem;
  color: #fff;
}
.hero h1 .line2 {
  background: linear-gradient(90deg, var(--accent), #4de8ff);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}
.typewriter-cursor {
  display:inline-block;
  width: 3px; height: 0.85em;
  background: var(--accent);
  animation: blink 0.85s step-end infinite;
  vertical-align: middle;
  margin-left: 3px;
  box-shadow: 0 0 6px var(--accent);
}
@keyframes blink { 0%,100% { opacity:1; } 50% { opacity:0; } }

.hero-sub {
  max-width: 560px;
  margin: 0 auto 2.5rem;
  color: var(--muted);
  font-size: 1.1rem;
}
.hero-actions { display:flex; gap:16px; justify-content:center; flex-wrap:wrap; }

/* ═══════════════════════════════════════════════
   BUTTONS
═══════════════════════════════════════════════ */
.btn {
  display: inline-flex; align-items:center; justify-content:center;
  gap: 8px;
  padding: 14px 34px;
  border-radius: 3px;
  font-family: var(--ff-mono);
  font-size: 0.78rem;
  letter-spacing: 0.1em;
  font-weight: 700;
  text-transform: uppercase;
  transition: transform 0.25s, box-shadow 0.25s;
  cursor: pointer;
  -webkit-appearance: none;
}
.btn-primary {
  background: var(--accent);
  color: #020a12;
  box-shadow: 0 0 20px var(--glow);
}
.btn-primary:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 28px var(--glow);
}
.btn-outline {
  background: transparent;
  color: var(--text);
  border: 1px solid rgba(255,255,255,0.15);
}
.btn-outline:hover {
  border-color: var(--accent);
  color: var(--accent);
  transform: translateY(-3px);
}

/* ═══════════════════════════════════════════════
   SERVICES
═══════════════════════════════════════════════ */
#services { background: var(--bg); }
.services-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(min(100%, 290px), 1fr));
  gap: 1px;
  margin-top: 3.5rem;
  border: 1px solid var(--border);
  border-radius: 8px;
  overflow: hidden;
}
.service-card {
  background: var(--bg-card);
  padding: 36px 32px;
  transition: background 0.3s;
  position: relative;
  overflow: hidden;
}
.service-card::before {
  content:'';
  position:absolute; top:0; left:0;
  width:100%; height:2px;
  background: linear-gradient(90deg, transparent, var(--accent), transparent);
  opacity:0;
  transition: opacity 0.3s;
}
.service-card:hover { background: #0a1424; }
.service-card:hover::before { opacity:1; }

.svc-num {
  font-family: var(--ff-mono);
  font-size: 0.65rem;
  letter-spacing: 0.2em;
  color: var(--accent);
  margin-bottom: 1.2rem;
  opacity: 0.6;
}
.service-card h3 {
  font-size: 1.15rem;
  color: #fff;
  margin-bottom: 0.75rem;
}
.service-card p { color: var(--muted); font-size: 0.93rem; }

/* ═══════════════════════════════════════════════
   TEAM
═══════════════════════════════════════════════ */
#team { background: var(--bg-card); }
.team-grid {
  display:grid;
  grid-template-columns: repeat(auto-fit, minmax(min(100%, 340px), 1fr));
  gap: 28px;
  margin-top: 3.5rem;
}
.profile-card {
  border: 1px solid var(--border);
  border-radius: 10px;
  overflow:hidden;
  background: var(--bg);
  transition: border-color 0.3s, box-shadow 0.3s;
  display:flex; flex-direction:column;
}
.profile-card:hover {
  border-color: var(--border-hi);
  box-shadow: 0 0 30px rgba(0,229,255,0.1);
}
.profile-head {
  padding: 36px 28px;
  background: linear-gradient(145deg, #060d1a, #03070f);
  border-bottom: 1px solid var(--border);
  display:flex; align-items:center; gap:20px;
}
.avatar {
  width: 72px; height: 72px;
  border-radius: 50%;
  border: 2px solid var(--accent);
  background: var(--bg-card);
  display:flex; align-items:center; justify-content:center;
  font-family: var(--ff-head);
  font-size: 1.3rem;
  color: var(--accent);
  flex-shrink:0;
  box-shadow: 0 0 18px var(--glow);
}
.profile-meta h3 { font-size: 1.4rem; color:#fff; margin-bottom:4px; }
.profile-meta span { font-family:var(--ff-mono); font-size:0.72rem; color:var(--muted); letter-spacing:0.1em; }
.profile-body { padding: 24px 28px; flex:1; }
.profile-body p { color:var(--muted); font-size:0.93rem; margin-bottom:1.2rem; }
.skill-tags { display:flex; flex-wrap:wrap; gap:8px; }
.tag {
  font-family:var(--ff-mono);
  font-size:0.68rem;
  padding: 4px 10px;
  border-radius:2px;
  border: 1px solid var(--border);
  color: var(--muted);
  letter-spacing:0.08em;
}

/* ═══════════════════════════════════════════════
   STATS / METHODOLOGY
═══════════════════════════════════════════════ */
#methodology { background: var(--bg); }
.stats-bar {
  display:flex; justify-content:space-around; flex-wrap:wrap;
  gap:30px;
  margin-top: 3.5rem;
  padding: 50px 40px;
  border: 1px solid var(--border);
  border-radius: 8px;
  background: var(--bg-card);
  position:relative; overflow:hidden;
}
.stats-bar::before {
  content:'';
  position:absolute; top:0; left:0; right:0;
  height: 1px;
  background: linear-gradient(90deg, transparent, var(--accent), transparent);
}
.stat-item { text-align:center; }
.stat-item .num {
  font-family: var(--ff-head);
  font-size: clamp(2.5rem, 5vw, 3.5rem);
  color: var(--accent);
  line-height:1;
  margin-bottom: 8px;
  text-shadow: 0 0 30px var(--glow);
}
.stat-item p { color: var(--muted); font-size:0.9rem; }

/* ═══════════════════════════════════════════════
   NETWORK INTELLIGENCE SCAN
═══════════════════════════════════════════════ */
#intelligence { background: var(--bg-card); }
.intel-wrapper {
  max-width: 820px;
  margin: 3.5rem auto 0;
  position:relative;
}

/* Terminal chrome */
.intel-chrome {
  display:flex; align-items:center; gap:10px;
  padding: 14px 22px;
  background: #050c1a;
  border: 1px solid var(--border);
  border-bottom:none;
  border-radius: 8px 8px 0 0;
}
.chrome-dots { display:flex; gap:7px; }
.chrome-dot {
  width:12px; height:12px;
  border-radius:50%;
}
.chrome-dot.red   { background: var(--accent2); }
.chrome-dot.yellow{ background: #ffd60a; }
.chrome-dot.green { background: #30d158; }
.chrome-title {
  margin-left: 12px;
  font-family: var(--ff-mono);
  font-size: 0.72rem;
  color: var(--muted);
  letter-spacing:0.1em;
  flex:1;
}
.live-indicator {
  display:flex; align-items:center; gap:7px;
  font-family:var(--ff-mono); font-size:0.68rem;
  color:var(--accent);
}
.live-dot {
  width:8px; height:8px;
  border-radius:50%;
  background: var(--accent);
  animation: livePulse 1.4s ease-in-out infinite;
}
@keyframes livePulse {
  0%,100% { box-shadow:0 0 0 0 var(--glow); }
  50%      { box-shadow:0 0 0 6px transparent; }
}

/* Main intel panel */
.intel-panel {
  border: 1px solid var(--border);
  border-radius: 0 0 8px 8px;
  background: #020810;
  overflow:hidden;
  position:relative;
}
/* Horizontal scan line animation */
.scan-beam {
  position:absolute; left:0; right:0; top:0;
  height: 2px;
  background: linear-gradient(90deg, transparent 0%, var(--accent) 50%, transparent 100%);
  opacity: 0.6;
  animation: beamSweep 3.5s linear infinite;
  pointer-events:none;
  z-index:5;
}
@keyframes beamSweep {
  0%   { top:0;    opacity:0; }
  5%   { opacity:0.6; }
  95%  { opacity:0.6; }
  100% { top:100%; opacity:0; }
}

/* Command prompt header inside panel */
.intel-prompt {
  padding: 16px 24px 12px;
  border-bottom: 1px solid rgba(0,229,255,0.08);
  display:flex; justify-content:space-between; align-items:center;
}
.intel-prompt code {
  font-family:var(--ff-mono); font-size:0.78rem;
  color: var(--accent); opacity:0.8;
}
.scan-status {
  font-family:var(--ff-mono); font-size:0.68rem;
  color: var(--muted);
  display:flex; align-items:center; gap:8px;
}
.scan-status .ok { color:#30d158; }
.scan-status .err { color:var(--accent2); }

/* Data rows */
.intel-body {
  padding: 20px 24px 24px;
  display:flex; flex-direction:column; gap:0;
  max-height: 340px;
  overflow-y: auto;
}
.intel-body::-webkit-scrollbar { width:5px; }
.intel-body::-webkit-scrollbar-track { background:transparent; }
.intel-body::-webkit-scrollbar-thumb { background:rgba(0,229,255,0.25); border-radius:3px; }

.intel-row {
  display:flex; align-items:flex-start;
  padding: 12px 0;
  border-bottom: 1px solid rgba(255,255,255,0.04);
  gap:16px;
}
.intel-row:last-child { border-bottom:none; }
.intel-key {
  font-family: var(--ff-mono);
  font-size: 0.73rem;
  color: var(--muted);
  letter-spacing:0.06em;
  min-width: 170px;
  flex-shrink:0;
  padding-top:1px;
}
.intel-key::before { content:'> '; color:var(--accent); opacity:0.5; }
.intel-val {
  font-family: var(--ff-mono);
  font-size: 0.85rem;
  color: #d0e4f0;
  word-break:break-all;
  transition: color 0.3s;
}
.intel-val.loading {
  color: var(--muted);
  position:relative;
}
.intel-val.loading::after {
  content:'█';
  animation: cursorBlink 0.9s step-end infinite;
  font-size:0.7rem;
  color: var(--accent);
  opacity:0.7;
  margin-left:4px;
}
@keyframes cursorBlink { 0%,100%{opacity:1} 50%{opacity:0} }
.intel-val.loaded { color: #7de8f5; }
.intel-val.static { color:#d0e4f0; }

/* IP badge highlight */
.ip-highlight {
  background: rgba(0,229,255,0.07);
  border: 1px solid rgba(0,229,255,0.2);
  border-radius:3px;
  padding:2px 10px;
  color: var(--accent) !important;
}

/* Panel footer */
.intel-footer {
  padding: 10px 24px;
  background: rgba(0,229,255,0.03);
  border-top: 1px solid rgba(0,229,255,0.06);
  font-family:var(--ff-mono);
  font-size:0.65rem;
  color:var(--muted);
  display:flex; justify-content:space-between;
}

/* ═══════════════════════════════════════════════
   CONTACT
═══════════════════════════════════════════════ */
#contact { background: var(--bg); }
.contact-layout {
  display:grid;
  grid-template-columns: 1fr 1.2fr;
  gap:60px;
  align-items:start;
  margin-top:3.5rem;
}
.contact-info p { color:var(--muted); margin-bottom:1.5rem; }
.contact-detail {
  display:flex; align-items:center; gap:12px;
  font-family:var(--ff-mono); font-size:0.8rem;
  color: var(--muted);
  padding: 12px 0;
  border-bottom: 1px solid rgba(255,255,255,0.04);
}
.contact-detail span { color:var(--accent); }

/* Form card */
.form-card {
  background: var(--bg-card);
  border: 1px solid var(--border);
  border-radius: 8px;
  padding: 40px;
  position:relative; overflow:hidden;
}
.form-card::before {
  content:'';
  position:absolute; top:0; left:0; right:0; height:1px;
  background: linear-gradient(90deg, transparent, var(--accent), transparent);
}
.field { display:flex; flex-direction:column; gap:7px; margin-bottom:18px; }
.field label {
  font-family:var(--ff-mono); font-size:0.68rem;
  letter-spacing:0.12em; color:var(--muted); text-transform:uppercase;
}
.field input, .field textarea {
  background: rgba(0,0,0,0.35);
  border: 1px solid rgba(255,255,255,0.08);
  border-radius:4px;
  padding:13px 16px;
  color: var(--text);
  font-family:var(--ff-body);
  font-size:0.95rem;
  width:100%;
  transition: border-color 0.25s, background 0.25s;
  -webkit-appearance:none;
  appearance:none;
  font-size:16px; /* prevent iOS zoom */
}
.field input:focus, .field textarea:focus {
  outline:none;
  border-color: var(--border-hi);
  background: rgba(0,229,255,0.04);
}
.field textarea { resize:vertical; min-height:130px; }
.btn-submit {
  width:100%;
  padding:16px;
  background: var(--accent);
  color:#020a12;
  border-radius:4px;
  font-family:var(--ff-mono);
  font-size:0.78rem;
  font-weight:700;
  letter-spacing:0.15em;
  text-transform:uppercase;
  transition: box-shadow 0.25s, transform 0.25s, opacity 0.25s;
  cursor:pointer;
  border:none;
  box-shadow:0 0 20px var(--glow);
}
.btn-submit:hover { transform:translateY(-2px); box-shadow:0 8px 28px var(--glow); }
.btn-submit:disabled { opacity:0.6; cursor:not-allowed; }

/* ═══════════════════════════════════════════════
   SUCCESS OVERLAY
═══════════════════════════════════════════════ */
#successOverlay {
  position:fixed; inset:0;
  background: rgba(3,7,15,0.92);
  backdrop-filter:blur(12px);
  -webkit-backdrop-filter:blur(12px);
  display:flex; justify-content:center; align-items:center;
  z-index:9999;
  opacity:0; pointer-events:none;
  transition: opacity 0.35s ease;
}
#successOverlay.active { opacity:1; pointer-events:all; }
.success-box {
  background:var(--bg-card);
  border:1px solid var(--border-hi);
  box-shadow:0 0 60px rgba(0,229,255,0.2);
  padding:48px 40px;
  text-align:center;
  border-radius:10px;
  max-width:420px; width:90%;
  transform:scale(0.85);
  transition: transform 0.4s cubic-bezier(0.175,0.885,0.32,1.275);
}
#successOverlay.active .success-box { transform:scale(1); }
.check-ring {
  width:80px; height:80px; border-radius:50%;
  border:2px solid var(--accent);
  margin:0 auto 24px;
  display:flex; align-items:center; justify-content:center;
  font-size:2.2rem;
  box-shadow:0 0 24px var(--glow);
  color:var(--accent);
}
.success-box h3 { font-size:1.4rem; color:#fff; margin-bottom:10px; }
.success-box p { color:var(--muted); margin-bottom:24px; }

/* ═══════════════════════════════════════════════
   FOOTER
═══════════════════════════════════════════════ */
footer {
  background:var(--bg-card);
  border-top:1px solid var(--border);
  padding:70px 0 36px;
  text-align:center;
}
.footer-logo {
  font-family:var(--ff-head);
  font-size:1.8rem;
  font-weight:800;
  color:#fff; margin-bottom:10px;
}
.footer-logo em { font-style:normal; color:var(--accent); }
footer > .container > p { color:var(--muted); font-size:0.9rem; margin-bottom:4px; }
.copyright {
  font-family:var(--ff-mono);
  font-size:0.7rem;
  color:rgba(90,106,128,0.6);
  margin-top:24px;
  letter-spacing:0.08em;
}

/* ═══════════════════════════════════════════════
   FADE-UP ANIMATION
═══════════════════════════════════════════════ */
.fade-up {
  opacity:0;
  transform:translateY(32px);
  transition: opacity 0.75s ease, transform 0.75s ease;
}
.fade-up.visible { opacity:1; transform:translateY(0); }

/* Stagger children */
.fade-up:nth-child(2) { transition-delay:0.1s; }
.fade-up:nth-child(3) { transition-delay:0.2s; }
.fade-up:nth-child(4) { transition-delay:0.3s; }

/* ═══════════════════════════════════════════════
   RESPONSIVE
═══════════════════════════════════════════════ */
@media (max-width:900px) {
  .contact-layout { grid-template-columns:1fr; gap:40px; }
}
@media (max-width:768px) {
  section { padding:70px 0; }
  .container { padding:0 20px; }

  /* Mobile nav */
  .nav-links {
    position:fixed;
    top:72px; left:0; right:0;
    height:calc(100dvh - 72px);
    background:rgba(3,7,15,0.98);
    backdrop-filter:blur(20px);
    -webkit-backdrop-filter:blur(20px);
    flex-direction:column;
    align-items:center; justify-content:center;
    gap:36px;
    transform:translateY(-120%);
    transition:transform 0.38s cubic-bezier(0.4,0,0.2,1);
    overflow-y:auto;
  }
  .nav-links.open { transform:translateY(0); }
  .nav-links a { font-size:1.1rem !important; }
  .nav-cta { padding:12px 28px !important; }
  .menu-toggle { display:block; }

  .hero-actions { flex-direction:column; align-items:center; }
  .hero-actions .btn { width:100%; max-width:300px; }

  .stats-bar { flex-direction:column; text-align:center; padding:36px 24px; }
  .intel-key { min-width:130px; font-size:0.7rem; }
  .intel-val { font-size:0.82rem; }
  .form-card { padding:28px 22px; }

  .intel-row { flex-direction:column; gap:4px; }
  .intel-key { min-width:auto; }
}
@media (max-width:480px) {
  .hero h1 { font-size:2.2rem; }
  .services-grid { grid-template-columns:1fr; }
}
</style>
</head>
<body>

<!-- ══════════════════════════════════════════════════
     SUCCESS OVERLAY
══════════════════════════════════════════════════ -->
<div id="successOverlay" role="dialog" aria-modal="true" aria-label="Submission confirmed">
  <div class="success-box">
    <div class="check-ring" aria-hidden="true">✓</div>
    <h3>Transmission Secured</h3>
    <p>Your message has been encrypted and delivered to RH²-Systems servers.</p>
    <button class="btn-submit" id="closeSuccess" style="max-width:200px;margin:auto;">Acknowledge</button>
  </div>
</div>

<!-- ══════════════════════════════════════════════════
     HEADER
══════════════════════════════════════════════════ -->
<header>
  <div class="container">
    <nav role="navigation" aria-label="Main navigation">
      <div class="logo">RH²-<em>Systems</em></div>

      <!-- Hamburger -->
      <button class="menu-toggle" id="menuBtn" aria-label="Toggle navigation menu" aria-expanded="false">☰</button>

      <ul class="nav-links" id="navLinks" role="list">
        <li><a href="#services">Services</a></li>
        <li><a href="#team">Team</a></li>
        <li><a href="#methodology">Methodology</a></li>
        <li><a href="#intelligence">Intel Scan</a></li>
        <li><a href="#contact" class="nav-cta">Contact</a></li>
      </ul>
    </nav>
  </div>
</header>

<!-- ══════════════════════════════════════════════════
     HERO
══════════════════════════════════════════════════ -->
<section class="hero" aria-label="Hero">
  <canvas id="networkCanvas" aria-hidden="true"></canvas>

  <div class="container hero-content fade-up">
    <div class="status-badge" aria-label="System status: secure">
      <span class="status-dot" aria-hidden="true"></span>
      SYSTEM STATUS: SECURE
    </div>

    <h1>
      Offensive Security.<br>
      <span class="line2" id="typewriterText" aria-live="polite"></span><span class="typewriter-cursor" aria-hidden="true"></span>
    </h1>

    <p class="hero-sub">Advanced penetration testing, red team operations, and secure engineering for high-risk enterprise infrastructure.</p>

    <div class="hero-actions">
      <a href="#contact" class="btn btn-primary">Initiate Confidential Audit</a>
      <a href="#services" class="btn btn-outline">Explore Capabilities</a>
    </div>
  </div>
</section>

<!-- ══════════════════════════════════════════════════
     SERVICES
══════════════════════════════════════════════════ -->
<section id="services" aria-labelledby="services-heading">
  <div class="container">
    <div class="fade-up">
      <span class="section-label">01 — Capabilities</span>
      <h2 class="section-title" id="services-heading">Core Security Services</h2>
      <p style="color:var(--muted)">Full-spectrum offensive security tailored for modern threat landscapes.</p>
    </div>

    <div class="services-grid">
      <div class="service-card fade-up">
        <div class="svc-num">SVC_001</div>
        <h3>Penetration Testing</h3>
        <p>Manual and automated assessments of Web, Mobile, API, and Cloud infrastructure aligned with OWASP Top 10 and NIST frameworks.</p>
      </div>
      <div class="service-card fade-up">
        <div class="svc-num">SVC_002</div>
        <h3>Red Team Operations</h3>
        <p>Adversary simulation replicating nation-state APT tactics to test your detection and response capabilities in real-time scenarios.</p>
      </div>
      <div class="service-card fade-up">
        <div class="svc-num">SVC_003</div>
        <h3>Secure Engineering</h3>
        <p>DevSecOps integration, Zero Trust architecture design, and source code review to embed security into the DNA of your software.</p>
      </div>
      <div class="service-card fade-up">
        <div class="svc-num">SVC_004</div>
        <h3>Incident Response</h3>
        <p>Continuous threat monitoring, log analysis, and rapid breach containment to detect and remediate security incidents before they escalate.</p>
      </div>
      <div class="service-card fade-up">
        <div class="svc-num">SVC_005</div>
        <h3>Threat Modeling</h3>
        <p>Identify and prioritize potential attack vectors and system weaknesses before adversaries exploit them using structured risk analysis.</p>
      </div>
      <div class="service-card fade-up">
        <div class="svc-num">SVC_006</div>
        <h3>Architecture Review</h3>
        <p>Comprehensive evaluation of system design, trust boundaries, and defensive controls to expose structural weaknesses before they become exploitable.</p>
      </div>
    </div>
  </div>
</section>

<!-- ══════════════════════════════════════════════════
     TEAM
══════════════════════════════════════════════════ -->
<section id="team" aria-labelledby="team-heading">
  <div class="container">
    <div class="fade-up">
      <span class="section-label">02 — Leadership</span>
      <h2 class="section-title" id="team-heading">Engineering &amp; Command</h2>
      <p style="color:var(--muted)">Built by engineers who understand both the attack vector and the defense mechanism.</p>
    </div>

    <div class="team-grid">
      <a href="https://rh-systems.github.io/Raj-Hridoy/" class="profile-card fade-up" aria-label="Raj Hridoy — Lead Architect">
        <div class="profile-head">
          <div class="avatar" aria-hidden="true">RH</div>
          <div class="profile-meta">
            <h3>Raj Hridoy</h3>
            <span>Cybersecurity Engineer</span>
          </div>
        </div>
        <div class="profile-body">
          <p>Specializing in secure software architecture and complex vulnerability analysis. Raj bridges high-level development with low-level security protocols.</p>
          <div class="skill-tags" aria-label="Skills">
            <span class="tag">Secure Arch</span>
            <span class="tag">Python / Go</span>
            <span class="tag">Cloud Security</span>
            <span class="tag">DevSecOps</span>
          </div>
        </div>
      </a>

      <a href="https://rh-systems.github.io/Riyad-Hasan/" class="profile-card fade-up" aria-label="Riyad Hasan — Offensive Specialist">
        <div class="profile-head">
          <div class="avatar" aria-hidden="true">RH</div>
          <div class="profile-meta">
            <h3>Riyad Hasan</h3>
            <span>Ethical Hacker</span>
          </div>
        </div>
        <div class="profile-body">
          <p>Focused on advanced threat modeling and penetration testing. Riyad specializes in breaking systems to make them unbreakable through adversarial analysis.</p>
          <div class="skill-tags" aria-label="Skills">
            <span class="tag">PenTesting</span>
            <span class="tag">Network Forensics</span>
            <span class="tag">Red Teaming</span>
            <span class="tag">Exploit Dev</span>
          </div>
        </div>
      </a>
    </div>
  </div>
</section>

<!-- ══════════════════════════════════════════════════
     METHODOLOGY / STATS
══════════════════════════════════════════════════ -->
<section id="methodology" aria-labelledby="methodology-heading">
  <div class="container">
    <div class="fade-up">
      <span class="section-label">03 — Methodology</span>
      <h2 class="section-title" id="methodology-heading">The RH² Standard</h2>
      <p style="color:var(--muted)">Measurable, repeatable, and fully confidential security assessments.</p>
    </div>
    <div class="stats-bar fade-up" role="list">
      <div class="stat-item" role="listitem">
        <div class="num" aria-label="150 plus">150+</div>
        <p>Engagements Delivered</p>
      </div>
      <div class="stat-item" role="listitem">
        <div class="num">100%</div>
        <p>Confidentiality Record</p>
      </div>
      <div class="stat-item" role="listitem">
        <div class="num">24/7</div>
        <p>Incident Support</p>
      </div>
      <div class="stat-item" role="listitem">
        <div class="num" aria-label="0 breaches">0</div>
        <p>Client Data Breaches</p>
      </div>
    </div>
  </div>
</section>

<!-- ══════════════════════════════════════════════════
     NETWORK INTELLIGENCE SCAN
══════════════════════════════════════════════════ -->
<section id="intelligence" aria-labelledby="intel-heading">
  <div class="container">
    <div class="fade-up" style="text-align:center">
      <span class="section-label" style="justify-content:center">04 — Telemetry</span>
      <h2 class="section-title" id="intel-heading">Network Intelligence Scan</h2>
      <p style="color:var(--muted);max-width:520px;margin:auto">Real-time analysis of your active connection — demonstrating the kind of reconnaissance performed during a security assessment.</p>
    </div>

    <div class="intel-wrapper fade-up" role="region" aria-label="Network intelligence scan results">
      <!-- Terminal window chrome -->
      <div class="intel-chrome" aria-hidden="true">
        <div class="chrome-dots">
          <div class="chrome-dot red"></div>
          <div class="chrome-dot yellow"></div>
          <div class="chrome-dot green"></div>
        </div>
        <span class="chrome-title">rh2sys_telemetry — bash</span>
        <div class="live-indicator">
          <div class="live-dot"></div>
          LIVE
        </div>
      </div>

      <!-- Main panel -->
      <div class="intel-panel">
        <div class="scan-beam" aria-hidden="true"></div>

        <div class="intel-prompt" aria-hidden="true">
          <code>$ ./network_scan --target=self --verbose</code>
          <div class="scan-status">
            <span id="scanStatusText">Scanning...</span>
          </div>
        </div>

        <div class="intel-body" role="table" aria-label="Scan results">
          <!-- IP -->
          <div class="intel-row" role="row">
            <span class="intel-key" role="rowheader">IP Address</span>
            <span class="intel-val loading" id="intel-ip" role="cell" aria-live="polite">Initiating scan...</span>
          </div>
          <!-- Country -->
          <div class="intel-row" role="row">
            <span class="intel-key" role="rowheader">Country</span>
            <span class="intel-val loading" id="intel-country" role="cell" aria-live="polite">Resolving geolocation...</span>
          </div>
          <!-- City -->
          <div class="intel-row" role="row">
            <span class="intel-key" role="rowheader">City / Region</span>
            <span class="intel-val loading" id="intel-city" role="cell" aria-live="polite">Resolving geolocation...</span>
          </div>
          <!-- ISP -->
          <div class="intel-row" role="row">
            <span class="intel-key" role="rowheader">ISP / Network</span>
            <span class="intel-val loading" id="intel-isp" role="cell" aria-live="polite">Querying ASN database...</span>
          </div>
          <!-- Timezone -->
          <div class="intel-row" role="row">
            <span class="intel-key" role="rowheader">Timezone</span>
            <span class="intel-val loading" id="intel-timezone" role="cell" aria-live="polite">Calculating offset...</span>
          </div>
          <!-- Browser -->
          <div class="intel-row" role="row">
            <span class="intel-key" role="rowheader">Browser</span>
            <span class="intel-val static" id="intel-browser" role="cell">Detecting...</span>
          </div>
          <!-- OS -->
          <div class="intel-row" role="row">
            <span class="intel-key" role="rowheader">Operating System</span>
            <span class="intel-val static" id="intel-os" role="cell">Detecting...</span>
          </div>
          <!-- Screen -->
          <div class="intel-row" role="row">
            <span class="intel-key" role="rowheader">Screen / DPI</span>
            <span class="intel-val static" id="intel-screen" role="cell">Detecting...</span>
          </div>
        </div>

        <div class="intel-footer" aria-hidden="true">
          <span>RH²-SYS TELEMETRY v3.1 · HTTPS ENCRYPTED</span>
          <span id="intelTimestamp"></span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ══════════════════════════════════════════════════
     CONTACT
══════════════════════════════════════════════════ -->
<section id="contact" aria-labelledby="contact-heading">
  <div class="container">
    <div class="fade-up">
      <span class="section-label">05 — Contact</span>
      <h2 class="section-title" id="contact-heading">Secure Consultation</h2>
    </div>

    <div class="contact-layout">
      <!-- Info column -->
      <div class="contact-info fade-up">
        <p>Ready to fortify your infrastructure? Contact us for a confidential discussion regarding your security posture and threat exposure.</p>
        <div class="contact-detail"><span>LOCATION</span> Rajshahi Division, Bangladesh</div>
        <div class="contact-detail"><span>AVAILABILITY</span> 24 / 7 Incident Support</div>
        <div class="contact-detail"><span>CHANNELS</span> Encrypted comms available on request</div>
        <br>
        <p style="font-family:var(--ff-mono);font-size:0.78rem;color:var(--accent)">
          &gt; All submissions are end-to-end encrypted via Firebase.
        </p>
      </div>

      <!-- Form column -->
      <div class="form-card fade-up">
        <form id="contactForm" novalidate aria-label="Contact form">
          <div class="field">
            <label for="f-name">Full Name / Organization</label>
            <input type="text" id="f-name" name="name" placeholder="Acme Corp / Jane Doe" required autocomplete="name">
          </div>
          <div class="field">
            <label for="f-email">Work Email</label>
            <input type="email" id="f-email" name="email" placeholder="security@yourcompany.com" required autocomplete="email">
          </div>
          <div class="field">
            <label for="f-msg">Project Scope / Details</label>
            <textarea id="f-msg" name="message" rows="5" placeholder="Describe your infrastructure and security goals..." required></textarea>
          </div>
          <button type="submit" class="btn-submit" id="submitBtn">Transmit Encrypted Request</button>
        </form>
      </div>
    </div>
  </div>
</section>

<!-- ══════════════════════════════════════════════════
     FOOTER
══════════════════════════════════════════════════ -->
<footer>
  <div class="container">
    <div class="footer-logo">RH²-<em>Systems</em></div>
    <p>Enterprise Cybersecurity &amp; Offensive Security</p>
    <p>Rajshahi Division, Bangladesh</p>
    <div class="copyright">© 2026 RH²-Systems · All Rights Reserved · Confidentiality Guaranteed</div>
  </div>
</footer>


<!-- ══════════════════════════════════════════════════
     JAVASCRIPT
══════════════════════════════════════════════════ -->
<script>
/* ── Mobile Nav ─────────────────────────────────── */
(function() {
  const btn   = document.getElementById('menuBtn');
  const links = document.getElementById('navLinks');

  btn.addEventListener('click', () => {
    const isOpen = links.classList.toggle('open');
    btn.textContent = isOpen ? '✕' : '☰';
    btn.setAttribute('aria-expanded', isOpen);
  });

  links.querySelectorAll('a').forEach(a => {
    a.addEventListener('click', () => {
      links.classList.remove('open');
      btn.textContent = '☰';
      btn.setAttribute('aria-expanded', 'false');
    });
  });
})();

/* ── Scroll Fade-Up (IntersectionObserver) ───────── */
(function() {
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => { if (e.isIntersecting) e.target.classList.add('visible'); });
  }, { threshold: 0.08 });
  document.querySelectorAll('.fade-up').forEach(el => observer.observe(el));
})();

/* ── Typewriter Effect ──────────────────────────── */
(function() {
  const words     = ['Infrastructure Auditing', 'Secure Engineering', 'Red Team Operations', 'Exploit Development'];
  const el        = document.getElementById('typewriterText');
  let wi=0, ci=0, deleting=false;
  const TYPE_SPD  = 55, DEL_SPD = 28, PAUSE = 2200;

  function tick() {
    const word = words[wi];
    if (deleting) {
      el.textContent = word.substring(0, --ci);
    } else {
      el.textContent = word.substring(0, ++ci);
    }
    let delay = deleting ? DEL_SPD : TYPE_SPD;
    if (!deleting && ci === word.length)  { delay = PAUSE; deleting = true; }
    if ( deleting && ci === 0)            { deleting = false; wi = (wi+1) % words.length; }
    setTimeout(tick, delay);
  }
  tick();
})();

/* ── Particle Network Canvas ────────────────────── */
(function() {
  const canvas = document.getElementById('networkCanvas');
  const ctx    = canvas.getContext('2d');
  const DPR    = Math.min(window.devicePixelRatio || 1, 2);
  let W, H, particles = [];
  const mouse  = { x: null, y: null, r: 130 };

  function resize() {
    W = canvas.parentElement.offsetWidth;
    H = canvas.parentElement.offsetHeight;
    canvas.width  = W * DPR;
    canvas.height = H * DPR;
    canvas.style.width  = W + 'px';
    canvas.style.height = H + 'px';
    ctx.scale(DPR, DPR);
    init();
  }

  function init() {
    particles = [];
    const n = Math.floor((W * H) / 9500);
    for (let i=0; i<n; i++) particles.push(new Particle());
  }

  class Particle {
    constructor() { this.reset(); }
    reset() {
      this.x  = Math.random() * W;
      this.y  = Math.random() * H;
      this.vx = (Math.random()-0.5) * 0.7;
      this.vy = (Math.random()-0.5) * 0.7;
      this.r  = Math.random() * 1.8 + 0.6;
    }
    update() {
      this.x += this.vx; this.y += this.vy;
      if (this.x < 0 || this.x > W) this.vx *= -1;
      if (this.y < 0 || this.y > H) this.vy *= -1;
      // mouse repulsion
      if (mouse.x !== null) {
        const dx = this.x - mouse.x, dy = this.y - mouse.y;
        const dist = Math.sqrt(dx*dx + dy*dy);
        if (dist < mouse.r) {
          this.x += dx / dist * 1.8;
          this.y += dy / dist * 1.8;
        }
      }
    }
    draw() {
      ctx.beginPath();
      ctx.arc(this.x, this.y, this.r, 0, Math.PI*2);
      ctx.fillStyle = '#00e5ff';
      ctx.fill();
    }
  }

  function connect() {
    const maxDist2 = (W / 6) * (H / 6);
    for (let a=0; a<particles.length; a++) {
      for (let b=a+1; b<particles.length; b++) {
        const dx = particles[a].x - particles[b].x;
        const dy = particles[a].y - particles[b].y;
        const d2 = dx*dx + dy*dy;
        if (d2 < maxDist2) {
          const alpha = (1 - d2/maxDist2) * 0.45;
          ctx.strokeStyle = `rgba(0,229,255,${alpha})`;
          ctx.lineWidth = 0.8;
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

  // Events
  window.addEventListener('resize', resize);
  window.addEventListener('mousemove', e => { mouse.x = e.clientX; mouse.y = e.clientY; });
  window.addEventListener('touchmove', e => {
    if (e.touches.length) { mouse.x = e.touches[0].clientX; mouse.y = e.touches[0].clientY; }
  }, { passive: true });

  resize();
  animate();
})();

/* ── Network Intelligence Scan ──────────────────────
   Strategy:
   1. Detect browser/OS/screen immediately (no API needed)
   2. Try ipwho.is  (HTTPS, CORS-open, no key required)
   3. Fallback: ipapi.co  (HTTPS, CORS-open, free tier)
   4. Fallback: ipinfo.io (HTTPS, CORS-open, free tier)
   5. Final fallback: graceful "Unavailable" state
─────────────────────────────────────────────────── */
(function initIntelScan() {

  /* Helpers */
  function setVal(id, value, isIp) {
    const el = document.getElementById(id);
    if (!el) return;
    el.textContent = value || 'Unknown';
    el.classList.remove('loading');
    el.classList.add(isIp ? 'loaded' : 'loaded');
    if (isIp) el.classList.add('ip-highlight');
  }

  function setAllFailed() {
    const ids = ['intel-ip','intel-country','intel-city','intel-isp','intel-timezone'];
    ids.forEach(id => setVal(id, 'Data Unavailable'));
    const ss = document.getElementById('scanStatusText');
    if (ss) { ss.textContent = 'SCAN FAILED'; ss.classList.add('err'); }
  }

  /* ── 1. Instant local data (no API) ── */
  const ua = navigator.userAgent;
  let browser = 'Unknown Browser', os = 'Unknown OS';

  // Browser detection
  if      (/SamsungBrowser/i.test(ua)) browser = 'Samsung Internet';
  else if (/OPR|Opera/i.test(ua))      browser = 'Opera';
  else if (/Trident/i.test(ua))        browser = 'Internet Explorer 11';
  else if (/Edg\//i.test(ua))          browser = 'Microsoft Edge';
  else if (/Firefox\/\d/i.test(ua))    browser = 'Mozilla Firefox';
  else if (/Chrome\/\d/i.test(ua))     browser = 'Google Chrome';
  else if (/Safari\/\d/i.test(ua))     browser = 'Apple Safari';

  // OS detection
  if      (/Android/i.test(ua))        os = 'Android';
  else if (/iPhone|iPad|iPod/i.test(ua)) os = 'iOS';
  else if (/Windows NT 10/i.test(ua))  os = 'Windows 10 / 11';
  else if (/Windows/i.test(ua))        os = 'Windows';
  else if (/Mac OS X/i.test(ua))       os = 'macOS';
  else if (/Linux/i.test(ua))          os = 'Linux';
  else if (/X11/i.test(ua))            os = 'UNIX';

  // Screen
  const screenStr = `${screen.width} × ${screen.height} @ ${window.devicePixelRatio || 1}x DPI`;

  document.getElementById('intel-browser').textContent = browser;
  document.getElementById('intel-browser').classList.add('loaded');
  document.getElementById('intel-os').textContent = os;
  document.getElementById('intel-os').classList.add('loaded');
  document.getElementById('intel-screen').textContent = screenStr;
  document.getElementById('intel-screen').classList.add('loaded');

  // Timestamp
  const ts = new Date().toISOString().replace('T',' ').split('.')[0] + ' UTC';
  const tsEl = document.getElementById('intelTimestamp');
  if (tsEl) tsEl.textContent = 'SCAN INIT: ' + ts;

  /* ── 2. API chain (all HTTPS, CORS-open) ── */
  const controller = new AbortController();
  const timeout = setTimeout(() => controller.abort(), 8000); // 8s timeout

  // Primary: ipwho.is — fast, no key, HTTPS, CORS
  fetch('https://ipwho.is/', { signal: controller.signal })
    .then(r => { if (!r.ok) throw new Error('ipwho.is HTTP ' + r.status); return r.json(); })
    .then(d => {
      clearTimeout(timeout);
      if (!d.success) throw new Error('ipwho.is: ' + (d.message || 'failed'));
      setVal('intel-ip',       d.ip,                                          true);
      setVal('intel-country',  `${d.country} (${d.country_code || ''})`);
      setVal('intel-city',     `${d.city || '—'}, ${d.region || '—'}`);
      setVal('intel-isp',      d.connection?.isp || d.connection?.org || d.org || 'Unknown');
      setVal('intel-timezone', d.timezone?.id || d.timezone || 'Unknown');
      const ss = document.getElementById('scanStatusText');
      if (ss) { ss.textContent = 'SCAN COMPLETE ✓'; ss.classList.add('ok'); }
    })
    .catch(() => {
      // Fallback 1: ipapi.co — HTTPS, CORS, free tier (no key)
      fetch('https://ipapi.co/json/', { signal: controller.signal })
        .then(r => { if (!r.ok) throw new Error('ipapi.co HTTP ' + r.status); return r.json(); })
        .then(d => {
          clearTimeout(timeout);
          if (d.error) throw new Error('ipapi.co: ' + d.reason);
          setVal('intel-ip',       d.ip,                                    true);
          setVal('intel-country',  `${d.country_name} (${d.country_code})`);
          setVal('intel-city',     `${d.city || '—'}, ${d.region || '—'}`);
          setVal('intel-isp',      d.org || d.asn || 'Unknown');
          setVal('intel-timezone', d.timezone || 'Unknown');
          const ss = document.getElementById('scanStatusText');
          if (ss) { ss.textContent = 'SCAN COMPLETE ✓'; ss.classList.add('ok'); }
        })
        .catch(() => {
          // Fallback 2: ipinfo.io — HTTPS, CORS, free tier
          fetch('https://ipinfo.io/json', { signal: controller.signal })
            .then(r => { if (!r.ok) throw new Error('ipinfo.io HTTP ' + r.status); return r.json(); })
            .then(d => {
              clearTimeout(timeout);
              setVal('intel-ip',       d.ip,                                    true);
              setVal('intel-country',  d.country || 'Unknown');
              setVal('intel-city',     `${d.city || '—'}, ${d.region || '—'}`);
              setVal('intel-isp',      d.org || 'Unknown');
              setVal('intel-timezone', d.timezone || 'Unknown');
              const ss = document.getElementById('scanStatusText');
              if (ss) { ss.textContent = 'SCAN COMPLETE ✓'; ss.classList.add('ok'); }
            })
            .catch(() => {
              clearTimeout(timeout);
              setAllFailed();
            });
        });
    });
})();
</script>

<!-- ══════════════════════════════════════════════════
     FIREBASE — Contact Form
══════════════════════════════════════════════════ -->
<script type="module">
import { initializeApp }                     from "https://www.gstatic.com/firebasejs/12.9.0/firebase-app.js";
import { getFirestore, collection, addDoc }  from "https://www.gstatic.com/firebasejs/12.9.0/firebase-firestore.js";

/* ── Firebase Config ── */
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

/* ── Success overlay ── */
const overlay      = document.getElementById('successOverlay');
const closeSuccess = document.getElementById('closeSuccess');
closeSuccess.addEventListener('click', () => overlay.classList.remove('active'));
overlay.addEventListener('click', e => { if (e.target === overlay) overlay.classList.remove('active'); });

/* ── Form submission ── */
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

