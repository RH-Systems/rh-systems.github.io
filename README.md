<!DOCTYPE html>
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
:root {
    --bg-dark: #050c18;
    --bg-dark-2: #0f172a;
    --accent: #3b82f6;
    --accent-glow: #60a5fa;
    --cyan: #06b6d4;
    --text-main: #f1f5f9;
    --text-muted: #94a3b8;
    --white: #ffffff;
    --glass: rgba(15, 23, 42, 0.85);
    --border: rgba(255, 255, 255, 0.1);
    --card-bg: rgba(30, 41, 59, 0.7);
}
* { margin:0; padding:0; box-sizing:border-box; font-family:'Inter', sans-serif; scroll-behavior:smooth; }
body { background: var(--bg-dark); color: var(--text-main); overflow-x:hidden; line-height:1.6; }
::-webkit-scrollbar { width:8px; }
::-webkit-scrollbar-track { background: var(--bg-dark); }
::-webkit-scrollbar-thumb { background: var(--accent); border-radius:4px; }

.container { width:90%; max-width:1200px; margin:auto; padding:0 15px; position:relative; z-index:2; }

header { position:fixed; top:0; width:100%; background: var(--glass); backdrop-filter: blur(15px); -webkit-backdrop-filter: blur(15px); border-bottom:1px solid var(--border); z-index:1000; transition: all 0.4s ease; }
header.scrolled { padding:10px 0; background: rgba(5,12,24,0.95); box-shadow:0 10px 30px rgba(0,0,0,0.5); }
nav { display:flex; justify-content:space-between; align-items:center; height:80px; transition: height 0.4s; }
header.scrolled nav { height:60px; }
.logo { font-weight:800; font-size:24px; color: var(--white); display:flex; align-items:center; gap:8px; letter-spacing:-0.5px; }
.logo i { color: var(--accent); }
.logo span { color: var(--accent); }
.nav-links { display:flex; gap:35px; list-style:none; }
.nav-links a { text-decoration:none; font-weight:500; font-size:15px; color: var(--text-muted); position:relative; transition:0.3s; }
.nav-links a::after { content:''; position:absolute; width:0; height:2px; bottom:-5px; left:0; background: var(--accent); transition:width 0.3s; }
.nav-links a:hover { color: var(--white); }
.nav-links a:hover::after { width:100%; }
.menu-toggle { display:none; cursor:pointer; font-size:24px; color: var(--white); }

.hero { position:relative; min-height:100vh; display:flex; align-items:center; justify-content:center; text-align:center; overflow:hidden; padding-top:80px; }
#networkCanvas { position:absolute; top:0; left:0; width:100%; height:100%; z-index:1; }
.hero-overlay { position:absolute; top:0; left:0; width:100%; height:100%; background: radial-gradient(circle at center, transparent 0%, var(--bg-dark) 90%); z-index:1; pointer-events:none; }
.hero-content { position:relative; z-index:3; max-width:850px; }
.badge { display:inline-block; padding:6px 16px; background: rgba(59,130,246,0.1); border:1px solid rgba(59,130,246,0.3); color: var(--accent-glow); border-radius:50px; font-size:0.85rem; font-weight:600; margin-bottom:25px; animation: float 3s ease-in-out infinite; }
.hero h1 { font-size:4rem; font-weight:800; line-height:1.1; margin-bottom:25px; letter-spacing:-1.5px; background: linear-gradient(to right,#fff 20%,#94a3b8 100%); -webkit-background-clip:text; -webkit-text-fill-color:transparent; }
.typewriter { color: var(--accent); border-right:4px solid var(--accent); padding-right:5px; animation: blink 0.75s step-end infinite, glow 1.5s ease-in-out infinite; }
@keyframes glow { 0%,100%{ text-shadow:0 0 5px var(--accent); } 50%{ text-shadow:0 0 20px var(--accent-glow); } }
.hero p { font-size:1.25rem; color: var(--text-muted); margin-bottom:45px; max-width:650px; margin:auto; line-height:1.8; }
.btn { position:relative; display:inline-block; padding:16px 40px; background: var(--accent); color:white; border-radius:8px; font-weight:600; text-decoration:none; overflow:hidden; transition: all 0.3s; box-shadow:0 0 20px rgba(59,130,246,0.3); border:1px solid transparent; }
.btn::before { content:''; position:absolute; top:0; left:-100%; width:100%; height:100%; background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent); transition:0.5s; }
.btn:hover { transform: translateY(-3px); box-shadow:0 0 30px rgba(59,130,246,0.6); }
.btn:hover::before { left:100%; }

/* Section & Cards */
section { padding:120px 0; }
.section-title h2 { font-size:2.5rem; color: var(--white); margin-bottom:15px; }
.grid { display:grid; grid-template-columns:repeat(auto-fit, minmax(300px,1fr)); gap:30px; }
.card { background: var(--card-bg); padding:40px; border-radius:16px; border:1px solid var(--border); backdrop-filter:blur(10px); position:relative; z-index:1; overflow:hidden; transition: all 0.4s ease; }
.card::before { content:''; position:absolute; top:0; left:0; width:100%; height:100%; background: radial-gradient(800px circle at var(--mouse-x,var(--mouse-y)), rgba(255,255,255,0.06), transparent 40%); z-index:2; opacity:0; transition:0.5s; pointer-events:none; }
.card:hover::before { opacity:1; }
.card:hover { transform:translateY(-10px); border-color: rgba(59,130,246,0.5); box-shadow:0 20px 40px -5px rgba(0,0,0,0.3); }
.card-icon { font-size:24px; color: var(--accent); margin-bottom:25px; background: rgba(59,130,246,0.1); width:60px; height:60px; display:flex; align-items:center; justify-content:center; border-radius:12px; border:1px solid rgba(59,130,246,0.2); transition:0.3s; }
.card:hover .card-icon { background: var(--accent); color:white; box-shadow:0 0 20px rgba(59,130,246,0.5); }
.card h3 { font-size:1.4rem; margin-bottom:15px; color: var(--white); }
.card p { color: var(--text-muted); font-size:1rem; }

/* Stats */
.stats-container { margin-top:100px; padding:60px; background: rgba(15,23,42,0.6); border:1px solid var(--border); border-radius:20px; display:flex; justify-content:space-around; flex-wrap:wrap; gap:40px; backdrop-filter:blur(10px); position:relative; overflow:hidden; }
.stats-container::after { content:''; position:absolute; top:0; left:-100%; width:50%; height:100%; background: linear-gradient(90deg,transparent,rgba(59,130,246,0.05),transparent); animation:scan 4s infinite linear; }
.stat { text-align:center; position:relative; z-index:2; }
.stat h3 { font-size:3.5rem; font-weight:800; color: var(--white); margin-bottom:5px; font-family:'JetBrains Mono', monospace; text-shadow:0 0 20px rgba(59,130,246,0.3); }
.stat p { color: var(--accent); font-weight:600; letter-spacing:1px; text-transform:uppercase; }

/* Leadership */
.team-card { background: var(--card-bg); border:1px solid var(--border); text-align:center; padding:50px 30px; transition:0.3s; }
.team-avatar { width:100px; height:100px; background: linear-gradient(135deg,#1e293b,#0f172a); border:2px solid var(--accent); border-radius:50%; margin:0 auto 25px; display:flex; align-items:center; justify-content:center; font-size:32px; color: var(--accent); box-shadow:0 0 25px rgba(59,130,246,0.2); }

/* Contact */
.contact-section { position:relative; padding-bottom:0; }
.cta-box { background: linear-gradient(135deg,var(--accent),#2563eb); border-radius:20px; padding:80px 40px; text-align:center; position:relative; overflow:hidden; }
.cta-box h2 { color:white; font-size:2.5rem; margin-bottom:20px; }
.cta-box p { color:rgba(255,255,255,0.9); margin-bottom:40px; font-size:1.2rem; }
.form-floater { background:white; padding:50px; border-radius:16px; max-width:700px; margin:-100px auto 0; position:relative; z-index:10; box-shadow:0 25px 50px rgba(0,0,0,0.2); }
.form-group { margin-bottom:20px; position:relative; }
.form-group input, .form-group textarea { width:100%; padding:15px; border:2px solid #e2e8f0; border-radius:8px; font-size:16px; background:#f8fafc; color:#334155; transition:0.3s; }
.form-group input:focus, .form-group textarea:focus { outline:none; border-color: var(--accent); background:white; }

@keyframes float { 0%,100%{ transform:translateY(0);} 50%{ transform:translateY(-10px); } }
@keyframes blink { 50%{ border-color:transparent; } }
@keyframes scan { 0%{ left:-100%; } 100%{ left:200%; } }

@media (max-width:768px){
    .menu-toggle{display:block;}
    .nav-links{position:fixed; top:80px; left:0; width:100%; background:var(--bg-dark); flex-direction:column; padding:40px; border-bottom:1px solid var(--border); transform:translateY(-150%);}
    .nav-links.active{transform:translateY(0);}
    .hero h1{font-size:2.8rem;}
    .stats-container{gap:40px;}
    .form-floater{width:90%; padding:30px;}
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
            <div class="menu-toggle" id="mobile-menu"><i class="fas fa-bars"></i></div>
            <ul class="nav-links">
                <li><a href="#services" onclick="closeMenu()">Services</a></li>
                <li><a href="#methodology" onclick="closeMenu()">Methodology</a></li>
                <li><a href="#about" onclick="closeMenu()">Leadership</a></li>
                <li><a href="#contact" class="btn" style="padding:10px 24px;margin-left:10px;">Contact</a></li>
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

<footer style="background:var(--bg-dark-2); padding:100px 0 40px; text-align:center; color:var(--text-muted);">
    <div class="container">
        <p>© 2026 RH²-Systems. Enterprise Cybersecurity.</p>
        <p style="font-size:13px; margin-top:10px;">Rajshahi Division, Bangladesh</p>
    </div>
</footer>

<script>
/* Mobile Menu */
const menuToggle = document.getElementById('mobile-menu');
const navLinks = document.querySelector('.nav-links');
menuToggle.addEventListener('click', ()=>navLinks.classList.toggle('active'));
function closeMenu(){ navLinks.classList.remove('active'); }

/* Navbar Scroll */
const navbar = document.getElementById('navbar');
window.addEventListener('scroll', ()=>{
    if(window.scrollY>50) navbar.classList.add('scrolled');
    else navbar.classList.remove('scrolled');
});

/* Particle Canvas */
const canvas = document.getElementById('networkCanvas');
const ctx = canvas.getContext('2d');
canvas.width = window.innerWidth;
canvas.height = window.innerHeight;
let particlesArray = [];
let mouse = {x:null, y:null, radius:(canvas.height/80)*(canvas.width/80)};
window.addEventListener('mousemove', e=>{ mouse.x=e.x; mouse.y=e.y; });

class Particle{
    constructor(x,y,dX,dY,size,color){ this.x=x; this.y=y; this.directionX=dX; this.directionY=dY; this.size=size; this.color=color; }
    draw(){ ctx.beginPath(); ctx.arc(this.x,this.y,this.size,0,Math.PI*2,false); ctx.fillStyle=this.color; ctx.fill(); }
    update(){
        if(this.x>canvas.width || this.x<0) this.directionX=-this.directionX;
        if(this.y>canvas.height || this.y<0) this.directionY=-this.directionY;
        this.x+=this.directionX;
        this.y+=this.directionY;
        let dx = this.x - mouse.x;
        let dy = this.y - mouse.y;
        let distance = Math.sqrt(dx*dx + dy*dy);
        if(distance < mouse.radius){
            let angle = Math.atan2(dy, dx);
            let force = (mouse.radius - distance)/mouse.radius;
            this.x += Math.cos(angle)*force*5;
            this.y += Math.sin(angle)*force*5;
        }
        this.draw();
    }
}
function initParticles(){
    particlesArray=[];
    let number = Math.floor((canvas.height*canvas.width)/9000);
    for(let i=0;i<number;i++){
        let size = Math.random()*3+1;
        let x = Math.random()*canvas.width;
        let y = Math.random()*canvas.height;
        let directionX = (Math.random()-0.5)*1;
        let directionY = (Math.random()-0.5)*1;
        particlesArray.push(new Particle(x,y,directionX,directionY,size,'#3b82f6'));
    }
}
function animate(){
    ctx.clearRect(0,0,canvas.width,canvas.height);
    for(let i=0;i<particlesArray.length;i++){ particlesArray[i].update(); }
    connectParticles();
    requestAnimationFrame(animate);
}
function connectParticles(){
    let maxDistance = 120;
    for(let a=0;a<particlesArray.length;a++){
        for(let b=a;b<particlesArray.length;b++){
            let dx = particlesArray[a].x - particlesArray[b].x;
            let dy = particlesArray[a].y - particlesArray[b].y;
            let dist = Math.sqrt(dx*dx+dy*dy);
            if(dist<maxDistance){
                ctx.beginPath();
                ctx.strokeStyle='rgba(59,130,246,'+(1-dist/maxDistance)+')';
                ctx.lineWidth=1;
                ctx.moveTo(particlesArray[a].x,particlesArray[a].y);
                ctx.lineTo(particlesArray[b].x,particlesArray[b].y);
                ctx.stroke();
            }
        }
    }
}
initParticles(); animate();
window.addEventListener('resize', ()=>{
    canvas.width=window.innerWidth;
    canvas.height=window.innerHeight;
    initParticles();
});

/* Typewriter Effect */
const typewriterText = ["Penetration Testing", "Red Team Operations", "Infrastructure Auditing", "Secure Engineering"];
const typewriterElement = document.getElementById('typewriter');
let txtIndex = 0;
let charIndex = 0;
let typingSpeed = 100;
let deletingSpeed = 50;
let delayBetweenWords = 2000;

function type() {
    if (charIndex < typewriterText[txtIndex].length) {
        typewriterElement.textContent += typewriterText[txtIndex][charIndex];
        charIndex++;
        setTimeout(type, typingSpeed);
    } else {
        setTimeout(deleteText, delayBetweenWords);
    }
}

function deleteText() {
    if (charIndex > 0) {
        typewriterElement.textContent = typewriterText[txtIndex].substring(0, charIndex - 1);
        charIndex--;
        setTimeout(deleteText, deletingSpeed);
    } else {
        txtIndex = (txtIndex + 1) % typewriterText.length;
        setTimeout(type, typingSpeed);
    }
}

// Start the typewriter
document.addEventListener("DOMContentLoaded", type);