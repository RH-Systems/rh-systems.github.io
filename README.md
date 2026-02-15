<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>RH²-Systems | Enterprise Cybersecurity & Offensive Security</title>

<meta name="description" content="RH²-Systems delivers enterprise-grade cybersecurity consulting, penetration testing, and red teaming.">
<meta name="keywords" content="Cybersecurity, Pentesting, Red Team, Zero Trust, SOC 2">
<meta name="author" content="RH²-Systems">
<meta name="theme-color" content="#050c18">

<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&family=JetBrains+Mono:wght@400;700&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

<style>
/* --- VARIABLES --- */
:root {
    --bg-dark: #050c18;
    --bg-dark-2: #0f172a;
    --accent: #3b82f6; /* Bright Blue */
    --accent-glow: #60a5fa;
    --cyan: #06b6d4;
    --text-main: #f1f5f9;
    --text-muted: #94a3b8;
    --white: #ffffff;
    --glass: rgba(15, 23, 42, 0.85);
    --border: rgba(255, 255, 255, 0.1);
    --card-bg: rgba(30, 41, 59, 0.7);
}

/* --- BASE --- */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Inter', sans-serif;
    scroll-behavior: smooth;
}

body {
    background: var(--bg-dark);
    color: var(--text-main);
    line-height: 1.6;
    overflow-x: hidden;
}

/* Scrollbar */
::-webkit-scrollbar { width: 8px; }
::-webkit-scrollbar-track { background: var(--bg-dark); }
::-webkit-scrollbar-thumb { background: var(--accent); border-radius: 4px; }

.container {
    width: 90%;
    max-width: 1200px;
    margin: auto;
    padding: 0 15px;
    position: relative;
    z-index: 2;
}

/* --- NAVIGATION --- */
header {
    position: fixed;
    top: 0;
    width: 100%;
    background: var(--glass);
    backdrop-filter: blur(15px);
    -webkit-backdrop-filter: blur(15px);
    border-bottom: 1px solid var(--border);
    z-index: 1000;
    transition: all 0.4s ease;
}

header.scrolled {
    padding: 10px 0;
    background: rgba(5, 12, 24, 0.95);
    box-shadow: 0 10px 30px rgba(0,0,0,0.5);
}

nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 80px;
    transition: height 0.4s;
}

header.scrolled nav { height: 60px; }

.logo {
    font-weight: 800;
    font-size: 24px;
    color: var(--white);
    letter-spacing: -0.5px;
    display: flex;
    align-items: center;
    gap: 8px;
}

.logo i { color: var(--accent); }
.logo span { color: var(--accent); }

.nav-links {
    display: flex;
    gap: 35px;
    list-style: none;
}

.nav-links a {
    text-decoration: none;
    font-weight: 500;
    font-size: 15px;
    color: var(--text-muted);
    transition: all 0.3s;
    position: relative;
}

.nav-links a::after {
    content: '';
    position: absolute;
    width: 0;
    height: 2px;
    bottom: -5px;
    left: 0;
    background: var(--accent);
    transition: width 0.3s;
}

.nav-links a:hover { color: var(--white); }
.nav-links a:hover::after { width: 100%; }

/* Mobile Menu */
.menu-toggle {
    display: none;
    cursor: pointer;
    font-size: 24px;
    color: var(--white);
}

/* --- HERO SECTION --- */
.hero {
    position: relative;
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    overflow: hidden;
    padding-top: 80px;
}

/* Canvas Background */
#networkCanvas {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 1;
}

.hero-overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: radial-gradient(circle at center, transparent 0%, var(--bg-dark) 90%);
    z-index: 1;
    pointer-events: none;
}

.hero-content {
    position: relative;
    z-index: 3;
    max-width: 850px;
}

.badge {
    display: inline-block;
    padding: 6px 16px;
    background: rgba(59, 130, 246, 0.1);
    border: 1px solid rgba(59, 130, 246, 0.3);
    color: var(--accent-glow);
    border-radius: 50px;
    font-size: 0.85rem;
    font-weight: 600;
    margin-bottom: 25px;
    animation: float 3s ease-in-out infinite;
}

.hero h1 {
    font-size: 4rem;
    font-weight: 800;
    line-height: 1.1;
    margin-bottom: 25px;
    letter-spacing: -1.5px;
    background: linear-gradient(to right, #fff 20%, #94a3b8 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
}

/* Typewriter Cursor */
.typewriter {
    color: var(--accent);
    border-right: 4px solid var(--accent);
    padding-right: 5px;
    animation: blink 0.75s step-end infinite;
}

.hero p {
    font-size: 1.25rem;
    color: var(--text-muted);
    margin-bottom: 45px;
    max-width: 650px;
    margin-left: auto;
    margin-right: auto;
    line-height: 1.8;
}

/* Animated Button */
.btn {
    position: relative;
    display: inline-block;
    padding: 16px 40px;
    background: var(--accent);
    color: white;
    border-radius: 8px;
    font-weight: 600;
    text-decoration: none;
    overflow: hidden;
    transition: all 0.3s;
    box-shadow: 0 0 20px rgba(59, 130, 246, 0.3);
    border: 1px solid transparent;
}

.btn::before {
    content: '';
    position: absolute;
    top: 0;
    left: -100%;
    width: 100%;
    height: 100%;
    background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
    transition: 0.5s;
}

.btn:hover {
    transform: translateY(-3px);
    box-shadow: 0 0 30px rgba(59, 130, 246, 0.6);
    background: var(--accent-hover);
}

.btn:hover::before { left: 100%; }

/* --- SERVICES & CARDS --- */
section { padding: 120px 0; }

.section-title h2 {
    font-size: 2.5rem;
    color: var(--white);
    margin-bottom: 15px;
}

.grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 30px;
}

.card {
    background: var(--card-bg);
    padding: 40px;
    border-radius: 16px;
    border: 1px solid var(--border);
    backdrop-filter: blur(10px);
    transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
    position: relative;
    z-index: 1;
    overflow: hidden;
}

/* Card Glow Effect */
.card::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: radial-gradient(800px circle at var(--mouse-x) var(--mouse-y), rgba(255, 255, 255, 0.06), transparent 40%);
    z-index: 2;
    opacity: 0;
    transition: opacity 0.5s;
    pointer-events: none;
}

.card:hover::before { opacity: 1; }

.card:hover {
    transform: translateY(-10px);
    border-color: rgba(59, 130, 246, 0.5);
    box-shadow: 0 20px 40px -5px rgba(0, 0, 0, 0.3);
}

.card-icon {
    font-size: 24px;
    color: var(--accent);
    margin-bottom: 25px;
    background: rgba(59, 130, 246, 0.1);
    width: 60px;
    height: 60px;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 12px;
    border: 1px solid rgba(59, 130, 246, 0.2);
    transition: 0.3s;
}

.card:hover .card-icon {
    background: var(--accent);
    color: white;
    box-shadow: 0 0 20px rgba(59, 130, 246, 0.5);
}

.card h3 {
    font-size: 1.4rem;
    margin-bottom: 15px;
    color: var(--white);
}

.card p { color: var(--text-muted); font-size: 1rem; }

/* --- STATS COUNTER --- */
.stats-container {
    margin-top: 100px;
    padding: 60px;
    background: rgba(15, 23, 42, 0.6);
    border: 1px solid var(--border);
    border-radius: 20px;
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
    gap: 40px;
    backdrop-filter: blur(10px);
    position: relative;
    overflow: hidden;
}

/* Scanning Line Animation */
.stats-container::after {
    content: '';
    position: absolute;
    top: 0;
    left: -100%;
    width: 50%;
    height: 100%;
    background: linear-gradient(90deg, transparent, rgba(59, 130, 246, 0.05), transparent);
    animation: scan 4s infinite linear;
}

.stat { text-align: center; position: relative; z-index: 2; }

.stat h3 {
    font-size: 3.5rem;
    font-weight: 800;
    color: var(--white);
    margin-bottom: 5px;
    font-family: 'JetBrains Mono', monospace;
    text-shadow: 0 0 20px rgba(59, 130, 246, 0.3);
}

.stat p { color: var(--accent); font-weight: 600; letter-spacing: 1px; text-transform: uppercase; }

/* --- METHODOLOGY --- */
.step-number {
    font-size: 4rem;
    font-weight: 900;
    color: rgba(255,255,255,0.03);
    position: absolute;
    top: 10px;
    right: 20px;
    line-height: 1;
}

/* --- LEADERSHIP --- */
.team-card {
    background: var(--card-bg);
    border: 1px solid var(--border);
    text-align: center;
    padding: 50px 30px;
    transition: 0.3s;
}

.team-avatar {
    width: 100px;
    height: 100px;
    background: linear-gradient(135deg, #1e293b, #0f172a);
    border: 2px solid var(--accent);
    border-radius: 50%;
    margin: 0 auto 25px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 32px;
    color: var(--accent);
    box-shadow: 0 0 25px rgba(59, 130, 246, 0.2);
}

/* --- CONTACT --- */
.contact-section { position: relative; padding-bottom: 0; }

.cta-box {
    background: linear-gradient(135deg, var(--accent), #2563eb);
    border-radius: 20px;
    padding: 80px 40px;
    text-align: center;
    position: relative;
    overflow: hidden;
}

.cta-box h2 { color: white; font-size: 2.5rem; margin-bottom: 20px; }
.cta-box p { color: rgba(255,255,255,0.9); margin-bottom: 40px; font-size: 1.2rem; }

.form-floater {
    background: white;
    padding: 50px;
    border-radius: 16px;
    max-width: 700px;
    margin: -100px auto 0; /* Overlap */
    position: relative;
    z-index: 10;
    box-shadow: 0 25px 50px rgba(0,0,0,0.2);
}

.form-group { margin-bottom: 20px; position: relative; }

.form-group input, .form-group textarea {
    width: 100%;
    padding: 15px;
    border: 2px solid #e2e8f0;
    border-radius: 8px;
    font-size: 16px;
    background: #f8fafc;
    transition: 0.3s;
    color: #334155;
}

.form-group input:focus, .form-group textarea:focus {
    outline: none;
    border-color: var(--accent);
    background: white;
}

/* --- ANIMATIONS & KEYFRAMES --- */
@keyframes float {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-10px); }
}

@keyframes blink { 50% { border-color: transparent; } }

@keyframes scan {
    0% { left: -100%; }
    100% { left: 200%; }
}

/* Scroll Reveal Classes */
.reveal {
    opacity: 0;
    transform: translateY(40px);
    transition: all 0.8s cubic-bezier(0.5, 0, 0, 1);
}

.reveal.active { opacity: 1; transform: translateY(0); }

/* Staggered Delays for Grid Items */
.grid .reveal:nth-child(1) { transition-delay: 0.1s; }
.grid .reveal:nth-child(2) { transition-delay: 0.2s; }
.grid .reveal:nth-child(3) { transition-delay: 0.3s; }
.grid .reveal:nth-child(4) { transition-delay: 0.4s; }

/* --- RESPONSIVE --- */
@media (max-width: 768px) {
    .menu-toggle { display: block; }
    
    .nav-links {
        position: fixed;
        top: 80px;
        left: 0;
        width: 100%;
        background: var(--bg-dark);
        flex-direction: column;
        padding: 40px;
        border-bottom: 1px solid var(--border);
        transform: translateY(-150%);
    }
    
    .nav-links.active { transform: translateY(0); }
    
    .hero h1 { font-size: 2.8rem; }
    
    .stats-container { gap: 40px; }
    
    .form-floater { width: 90%; padding: 30px; }
}
</style>
</head>

<body>

<div class="hero-overlay"></div>
<canvas id="networkCanvas"></canvas>

<header id="navbar">
    <div class="container">
        <nav>
            <div class="logo"><i class="fas fa-shield-halved"></i> RH²-<span>Systems</span></div>
            <div class="menu-toggle" id="mobile-menu">
                <i class="fas fa-bars"></i>
            </div>
            <ul class="nav-links">
                <li><a href="#services" onclick="closeMenu()">Services</a></li>
                <li><a href="#methodology" onclick="closeMenu()">Methodology</a></li>
                <li><a href="#about" onclick="closeMenu()">Leadership</a></li>
                <li><a href="#contact" class="btn" style="padding: 10px 24px; margin-left:10px;">Contact</a></li>
            </ul>
        </nav>
    </div>
</header>

<section class="hero">
    <div class="container hero-content">
        <div class="badge fade-in">2026 Enterprise Security Verified</div>
        <h1>Offensive Security.<br><span class="typewriter" id="typewriter"></span></h1>
        <p class="fade-in">We deliver advanced penetration testing, red teaming, and secure engineering for high-risk digital environments. Secure your infrastructure before they find the gaps.</p>
        <a href="#contact" class="btn fade-in">Request Confidential Audit</a>
    </div>
</section>

<section id="services">
    <div class="container">
        <div class="section-title reveal">
            <h2>Core Capabilities</h2>
            <p>Aligned with Zero-Trust Architecture, ISO 27001, and SOC 2.</p>
        </div>

        <div class="grid" id="service-grid">
            <div class="card reveal">
                <div class="card-icon"><i class="fas fa-bug"></i></div>
                <h3>Penetration Testing</h3>
                <p>Manual and automated attack simulation across web apps, APIs, mobile, and internal networks.</p>
            </div>
            <div class="card reveal">
                <div class="card-icon"><i class="fas fa-user-secret"></i></div>
                <h3>Red Team Operations</h3>
                <p>Full-scope adversary emulation designed to test your SOC detection capabilities and response.</p>
            </div>
            <div class="card reveal">
                <div class="card-icon"><i class="fas fa-network-wired"></i></div>
                <h3>Infrastructure Auditing</h3>
                <p>Deep-dive configuration reviews of Cloud (AWS/Azure) and On-Premise environments.</p>
            </div>
            <div class="card reveal">
                <div class="card-icon"><i class="fas fa-code-branch"></i></div>
                <h3>Secure Engineering</h3>
                <p>DevSecOps integration, secure code reviews, and architectural consulting for the SDLC.</p>
            </div>
        </div>

        <div class="stats-container reveal" id="stats-section">
            <div class="stat">
                <h3 data-target="150">0</h3>
                <p>Engagements</p>
            </div>
            <div class="stat">
                <h3 data-target="100">0</h3>
                <p>Confidentiality %</p>
            </div>
            <div class="stat">
                <h3 data-target="0">24/7</h3>
                <p>Response Ops</p>
            </div>
        </div>
    </div>
</section>

<section id="methodology">
    <div class="container">
        <div class="section-title reveal">
            <h2>Methodology</h2>
            <p>A structured, intelligence-driven framework.</p>
        </div>

        <div class="grid">
            <div class="card reveal">
                <span class="step-number">01</span>
                <h3>Reconnaissance</h3>
                <p>OSINT gathering and threat modeling to map your digital footprint and potential entry points.</p>
            </div>
            <div class="card reveal">
                <span class="step-number">02</span>
                <h3>Exploitation</h3>
                <p>Controlled execution of attack vectors to validate vulnerabilities, filtering out false positives.</p>
            </div>
            <div class="card reveal">
                <span class="step-number">03</span>
                <h3>Remediation</h3>
                <p>Detailed technical reports with prioritized mitigation strategies for engineering teams.</p>
            </div>
        </div>
    </div>
</section>

<section id="about">
    <div class="container">
        <div class="section-title reveal">
            <h2>Leadership</h2>
        </div>

        <div class="grid" style="max-width: 800px; margin: auto;">
            <div class="card team-card reveal">
                <div class="team-avatar"><i class="fas fa-user-shield"></i></div>
                <h3>Raj Hridoy</h3>
                <p style="color:var(--accent); font-weight:600; margin-bottom:10px;">Lead Security Engineer</p>
                <p>Specializing in Zero-Trust architecture and enterprise risk mitigation.</p>
            </div>
            <div class="card team-card reveal">
                <div class="team-avatar"><i class="fas fa-user-ninja"></i></div>
                <h3>Riyad Hasan</h3>
                <p style="color:var(--accent); font-weight:600; margin-bottom:10px;">Lead Red Team Operator</p>
                <p>Expert in advanced threat simulation and social engineering.</p>
            </div>
        </div>
    </div>
</section>

<section class="contact-section">
    <div class="cta-box">
        <div class="container">
            <h2>Secure Your Infrastructure</h2>
            <p>Initiate a confidential discussion.</p>
        </div>
    </div>

    <div class="container">
        <div class="form-floater reveal" id="contact">
            <form action="https://formspree.io/f/yourFormID" method="POST">
                <div class="form-group">
                    <input type="text" name="name" placeholder="Full Name" required>
                </div>
                <div class="form-group">
                    <input type="email" name="email" placeholder="Corporate Email" required>
                </div>
                <div class="form-group">
                    <textarea name="message" rows="5" placeholder="Describe your security requirements..." required></textarea>
                </div>
                <button type="submit" class="btn" style="width:100%; border:none; cursor:pointer;">Send Secure Message</button>
            </form>
        </div>
    </div>
</section>

<footer style="background:var(--bg-dark-2); padding: 100px 0 40px; text-align:center; color:var(--text-muted);">
    <div class="container">
        <p>© 2026 RH²-Systems. Enterprise Cybersecurity.</p>
        <p style="font-size: 13px; margin-top:10px;">Rajshahi Division, Bangladesh</p>
    </div>
</footer>

<script>
    // --- 1. MOBILE MENU ---
    const menuToggle = document.getElementById('mobile-menu');
    const navLinks = document.querySelector('.nav-links');
    menuToggle.addEventListener('click', () => navLinks.classList.toggle('active'));
    function closeMenu() { navLinks.classList.remove('active'); }

    // --- 2. NAVBAR SCROLL EFFECT ---
    const navbar = document.getElementById('navbar');
    window.addEventListener('scroll', () => {
        if (window.scrollY > 50) navbar.classList.add('scrolled');
        else navbar.classList.remove('scrolled');
    });

    // --- 3. CANVAS PARTICLE NETWORK (The "Cyber" Background) ---
    const canvas = document.getElementById('networkCanvas');
    const ctx = canvas.getContext('2d');
    let particlesArray;

    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;

    let mouse = { x: null, y: null, radius: (canvas.height/80) * (canvas.width/80) };

    window.addEventListener('mousemove', (event) => {
        mouse.x = event.x;
        mouse.y = event.y;
    });

    class Particle {
        constructor(x, y, directionX, directionY, size, color) {
            this.x = x; this.y = y;
            this.directionX = directionX; this.directionY = directionY;
            this.size = size; this.color = color;
        }
        draw() {
            ctx.beginPath();
            ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2, false);
            ctx.fillStyle = '#3b82f6';
            ctx.fill();
        }
        update() {
            if (this.x > canvas.width || this.x < 0) this.directionX = -this.directionX;
            if (this.y > canvas.height || this.y < 0) this.directionY = -this.directionY;
            
            // Mouse Repulsion
 