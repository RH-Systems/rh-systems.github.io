<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>RH²-Systems | Enterprise Cybersecurity & Offensive Security</title>

<meta name="description" content="RH²-Systems delivers enterprise-grade penetration testing, red teaming, and secure infrastructure auditing.">
<meta name="keywords" content="Cybersecurity, Penetration Testing, Red Team, SOC 2, Zero Trust">
<meta name="author" content="RH²-Systems">
<meta name="theme-color" content="#050c18">
<meta name="robots" content="index, follow">
<link rel="canonical" href="https://example.com/">

<!-- Open Graph -->
<meta property="og:title" content="RH²-Systems | Enterprise Cybersecurity">
<meta property="og:description" content="Advanced offensive security & secure engineering services.">
<meta property="og:type" content="website">

<!-- Twitter -->
<meta name="twitter:card" content="summary_large_image">

<!-- Basic CSP (adjust if hosted with backend) -->
<meta http-equiv="Content-Security-Policy" content="default-src 'self' https://fonts.googleapis.com https://fonts.gstatic.com; style-src 'self' 'unsafe-inline' https://fonts.googleapis.com; font-src https://fonts.gstatic.com; script-src 'self' 'unsafe-inline';">

<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;800&family=JetBrains+Mono:wght@700&display=swap" rel="stylesheet">

<style>
:root{
--bg:#050c18;
--bg2:#0f172a;
--accent:#3b82f6;
--text:#f1f5f9;
--muted:#94a3b8;
--border:rgba(255,255,255,0.08);
}
*{margin:0;padding:0;box-sizing:border-box;font-family:'Inter',sans-serif}
body{background:var(--bg);color:var(--text);line-height:1.6;overflow-x:hidden}
.container{width:90%;max-width:1200px;margin:auto}
section{padding:100px 0}
h1,h2,h3{font-weight:800}
a{text-decoration:none;color:inherit}

header{
position:fixed;width:100%;top:0;background:rgba(5,12,24,0.9);
backdrop-filter:blur(12px);border-bottom:1px solid var(--border);z-index:1000;
}
nav{display:flex;justify-content:space-between;align-items:center;height:70px}
.logo{font-weight:800;font-size:22px}
.logo span{color:var(--accent)}
.nav-links{display:flex;gap:30px;list-style:none}
.nav-links a{color:var(--muted);font-weight:600;font-size:14px}
.nav-links a:hover{color:var(--text)}
.menu-toggle{display:none;cursor:pointer}

.hero{
position:relative;min-height:100vh;display:flex;align-items:center;
text-align:center;padding-top:80px;overflow:hidden;
}
#networkCanvas{position:absolute;top:0;left:0;width:100%;height:100%;z-index:1}
.hero-content{position:relative;z-index:2;max-width:800px;margin:auto}
.hero h1{font-size:3.2rem;margin-bottom:20px}
.typewriter{color:var(--accent);border-right:3px solid var(--accent)}
.hero p{color:var(--muted);margin-bottom:40px}
.btn{
display:inline-block;padding:14px 32px;background:var(--accent);
border-radius:6px;font-weight:600
}

.grid{
display:grid;grid-template-columns:repeat(auto-fit,minmax(280px,1fr));
gap:30px;margin-top:40px
}
.card{
background:var(--bg2);padding:30px;border-radius:12px;
border:1px solid var(--border)
}
.card h3{margin-bottom:10px}
.card p{color:var(--muted);font-size:15px}

.section-title{text-align:center;margin-bottom:40px}
.section-title p{color:var(--muted)}

.stats{display:flex;justify-content:space-around;flex-wrap:wrap;gap:40px;margin-top:40px}
.stat{text-align:center}
.stat h3{font-size:2.5rem;font-family:'JetBrains Mono',monospace}

footer{
background:var(--bg2);padding:60px 0;text-align:center;color:var(--muted)
}

.fade-in{animation:fade 1.2s ease forwards;opacity:0}
@keyframes fade{to{opacity:1}}

@media(max-width:768px){
.nav-links{position:fixed;top:70px;left:0;width:100%;background:var(--bg);
flex-direction:column;padding:30px;transform:translateY(-150%);
transition:0.3s}
.nav-links.active{transform:translateY(0)}
.menu-toggle{display:block}
.hero h1{font-size:2.3rem}
}

@media (prefers-reduced-motion: reduce){
*{animation:none !important}
}
</style>
</head>

<body>

<header>
<div class="container">
<nav>
<div class="logo">RH²-<span>Systems</span></div>
<div class="menu-toggle" id="menu">☰</div>
<ul class="nav-links">
<li><a href="#services">Services</a></li>
<li><a href="#methodology">Methodology</a></li>
<li><a href="#about">Leadership</a></li>
<li><a href="#contact">Contact</a></li>
</ul>
</nav>
</div>
</header>

<section class="hero">
<canvas id="networkCanvas"></canvas>
<div class="container hero-content fade-in">
<h1>Offensive Security.<br><span class="typewriter" id="typewriter"></span></h1>
<p>Enterprise penetration testing, red team operations, and secure engineering for high-risk infrastructure.</p>
<a href="#contact" class="btn">Request Confidential Audit</a>
</div>
</section>

<section id="services">
<div class="container">
<div class="section-title">
<h2>Core Services</h2>
<p>Advanced offensive security tailored for enterprise environments.</p>
</div>
<div class="grid">
<div class="card">
<h3>Penetration Testing</h3>
<p>Comprehensive web, API, mobile and infrastructure assessments aligned with OWASP & NIST standards.</p>
</div>
<div class="card">
<h3>Red Team Operations</h3>
<p>Full-scope adversary simulation replicating nation-state and APT tactics.</p>
</div>
<div class="card">
<h3>Secure Engineering</h3>
<p>Architecture review, Zero Trust implementation, and DevSecOps integration.</p>
</div>
</div>
</div>
</section>

<section id="methodology">
<div class="container">
<div class="section-title">
<h2>Methodology</h2>
<p>Structured. Measurable. Repeatable.</p>
</div>
<div class="grid">
<div class="card"><h3>Reconnaissance</h3><p>Threat surface mapping & asset enumeration.</p></div>
<div class="card"><h3>Exploitation</h3><p>Controlled vulnerability validation & lateral movement testing.</p></div>
<div class="card"><h3>Reporting</h3><p>Executive-level risk analysis with remediation roadmap.</p></div>
</div>
</div>
</section>

<section id="about">
<div class="container">
<div class="section-title">
<h2>Leadership</h2>
<p>Security professionals with offensive and defensive expertise.</p>
</div>
<div class="stats">
<div class="stat"><h3>150+</h3><p>Assessments</p></div>
<div class="stat"><h3>98%</h3><p>Client Retention</p></div>
<div class="stat"><h3>24/7</h3><p>Incident Support</p></div>
</div>
</div>
</section>

<section id="contact">
<div class="container">
<div class="section-title">
<h2>Contact</h2>
<p>Confidential security consultation.</p>
</div>
<div class="card">
<form>
<input type="text" placeholder="Full Name" required style="width:100%;padding:12px;margin-bottom:15px">
<input type="email" placeholder="Email Address" required style="width:100%;padding:12px;margin-bottom:15px">
<textarea placeholder="Your Message" rows="5" required style="width:100%;padding:12px;margin-bottom:15px"></textarea>
<button class="btn" type="submit">Submit</button>
</form>
</div>
</div>
</section>

<footer>
<div class="container">
<p>© 2026 RH²-Systems. Enterprise Cybersecurity.</p>
<p>Rajshahi Division, Bangladesh</p>
</div>
</footer>

<script>
/* Mobile Menu */
document.getElementById("menu").onclick=function(){
document.querySelector(".nav-links").classList.toggle("active");
};

/* Optimized Canvas */
const canvas=document.getElementById("networkCanvas");
const ctx=canvas.getContext("2d");
let dpr=window.devicePixelRatio||1;
function resize(){
canvas.width=window.innerWidth*dpr;
canvas.height=window.innerHeight*dpr;
canvas.style.width=window.innerWidth+"px";
canvas.style.height=window.innerHeight+"px";
ctx.scale(dpr,dpr);
}
resize();
window.addEventListener("resize",resize);

let particles=[];
const MAX_PARTICLES=100;

class Particle{
constructor(){
this.x=Math.random()*window.innerWidth;
this.y=Math.random()*window.innerHeight;
this.dx=(Math.random()-0.5)*0.7;
this.dy=(Math.random()-0.5)*0.7;
}
draw(){
ctx.beginPath();
ctx.arc(this.x,this.y,2,0,Math.PI*2);
ctx.fillStyle="#3b82f6";
ctx.fill();
}
update(){
this.x+=this.dx;
this.y+=this.dy;
if(this.x<0||this.x>window.innerWidth)this.dx*=-1;
if(this.y<0||this.y>window.innerHeight)this.dy*=-1;
this.draw();
}
}

function init(){
particles=[];
for(let i=0;i<MAX_PARTICLES;i++)particles.push(new Particle());
}
init();

function animate(){
ctx.clearRect(0,0,canvas.width,canvas.height);
particles.forEach(p=>p.update());
requestAnimationFrame(animate);
}
animate();

/* Typewriter */
const words=["Penetration Testing","Red Team Operations","Infrastructure Auditing","Secure Engineering"];
let i=0,j=0,deleting=false;
function type(){
let el=document.getElementById("typewriter");
if(!deleting&&j<=words[i].length){
el.textContent=words[i].substring(0,j++);
}else if(deleting&&j>=0){
el.textContent=words[i].substring(0,j--);
}
if(j===words[i].length){deleting=true;setTimeout(type,1200);return;}
if(j===0&&deleting){deleting=false;i=(i+1)%words.length;}
setTimeout(type,deleting?40:80);
}
type();
</script>

</body>
</html>