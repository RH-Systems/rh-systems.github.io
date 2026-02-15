<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>RH²-Systems | Enterprise Cyber Security</title>
<meta name="description" content="RH²-Systems provides enterprise-grade cybersecurity consulting, penetration testing, and secure software engineering solutions.">

<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700;800;900&display=swap" rel="stylesheet">

<style>

/* ================= ROOT ================= */

:root{
--bg-dark:#050c18;
--bg-dark-2:#0b1f3a;
--accent:#0066ff;
--light:#f4f7fb;
--text-light:#cbd5e1;
--white:#ffffff;
}

/* ================= GLOBAL ================= */

*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:'Inter',sans-serif;
scroll-behavior:smooth;
}

body{
background:var(--light);
color:#111827;
line-height:1.7;
}

.container{
width:90%;
max-width:1200px;
margin:auto;
}

/* ================= NAVIGATION ================= */

header{
position:fixed;
top:0;
width:100%;
background:rgba(255,255,255,0.85);
backdrop-filter:blur(10px);
z-index:1000;
border-bottom:1px solid rgba(0,0,0,0.05);
}

nav{
display:flex;
justify-content:space-between;
align-items:center;
padding:18px 0;
}

.logo{
font-weight:900;
font-size:22px;
letter-spacing:-1px;
color:#0b1f3a;
}

nav ul{
list-style:none;
display:flex;
gap:28px;
}

nav a{
text-decoration:none;
font-weight:600;
color:#111827;
position:relative;
transition:0.3s;
}

nav a::after{
content:"";
position:absolute;
bottom:-4px;
left:0;
width:0;
height:2px;
background:var(--accent);
transition:0.3s;
}

nav a:hover{
color:var(--accent);
}

nav a:hover::after{
width:100%;
}

/* ================= HERO ================= */

.hero{
min-height:100vh;
display:flex;
align-items:center;
justify-content:center;
text-align:center;
color:var(--white);
background:
radial-gradient(circle at 20% 20%, rgba(0,102,255,0.15), transparent 40%),
linear-gradient(135deg,var(--bg-dark),var(--bg-dark-2));
padding-top:80px;
position:relative;
overflow:hidden;
}

.hero::before{
content:"";
position:absolute;
width:200%;
height:200%;
background-image:
linear-gradient(rgba(255,255,255,0.04) 1px, transparent 1px),
linear-gradient(90deg, rgba(255,255,255,0.04) 1px, transparent 1px);
background-size:60px 60px;
animation:moveGrid 20s linear infinite;
}

@keyframes moveGrid{
from{transform:translateY(0);}
to{transform:translateY(-60px);}
}

.hero h1{
font-size:56px;
font-weight:900;
margin-bottom:20px;
letter-spacing:-1px;
position:relative;
z-index:2;
}

.hero p{
max-width:650px;
margin:auto;
opacity:0.85;
font-size:18px;
position:relative;
z-index:2;
}

.btn{
display:inline-block;
margin-top:35px;
padding:15px 34px;
background:var(--accent);
color:white;
border-radius:6px;
font-weight:700;
text-decoration:none;
transition:0.3s;
box-shadow:0 8px 30px rgba(0,102,255,0.4);
position:relative;
z-index:2;
}

.btn:hover{
transform:translateY(-3px);
background:#0047cc;
}

/* ================= SECTIONS ================= */

section{
padding:120px 0;
}

.section-title{
text-align:center;
margin-bottom:70px;
}

.section-title h2{
font-size:38px;
font-weight:900;
margin-bottom:15px;
color:#0b1f3a;
}

.section-title p{
color:#6b7280;
}

/* ================= GRID ================= */

.grid{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(280px,1fr));
gap:40px;
}

.card{
background:white;
padding:45px;
border-radius:14px;
box-shadow:0 20px 40px rgba(0,0,0,0.06);
transition:0.4s;
border:1px solid rgba(0,0,0,0.04);
}

.card:hover{
transform:translateY(-10px);
box-shadow:0 25px 50px rgba(0,0,0,0.12);
}

.card h3{
margin-bottom:15px;
color:#0b1f3a;
font-weight:800;
}

.card p{
color:#6b7280;
}

/* ================= DARK CTA ================= */

.cta{
background:linear-gradient(135deg,var(--bg-dark),var(--bg-dark-2));
color:white;
text-align:center;
padding:110px 0;
}

.cta h2{
font-size:40px;
font-weight:900;
margin-bottom:20px;
}

.cta p{
opacity:0.85;
margin-bottom:30px;
}

/* ================= CONTACT ================= */

.contact-box{
background:white;
padding:60px;
border-radius:14px;
box-shadow:0 20px 40px rgba(0,0,0,0.06);
max-width:750px;
margin:auto;
}

.contact-box input,
.contact-box textarea{
width:100%;
padding:15px;
margin-bottom:20px;
border-radius:8px;
border:1px solid #ddd;
font-size:15px;
}

.contact-box input:focus,
.contact-box textarea:focus{
outline:none;
border-color:var(--accent);
}

.contact-box button{
width:100%;
padding:16px;
background:var(--accent);
color:white;
border:none;
border-radius:8px;
font-weight:700;
cursor:pointer;
transition:0.3s;
}

.contact-box button:hover{
background:#0047cc;
}

/* ================= FOOTER ================= */

footer{
background:#0b1f3a;
color:white;
text-align:center;
padding:50px 0;
}

footer p{
opacity:0.8;
font-size:14px;
}

/* ================= RESPONSIVE ================= */

@media(max-width:768px){
.hero h1{
font-size:36px;
}
.section-title h2{
font-size:30px;
}
}

</style>
</head>
<body>

<header>
<div class="container">
<nav>
<div class="logo">RH²-Systems</div>
<ul>
<li><a href="#home">Home</a></li>
<li><a href="#services">Services</a></li>
<li><a href="#about">About</a></li>
<li><a href="#contact">Contact</a></li>
</ul>
</nav>
</div>
</header>

<section class="hero" id="home">
<div class="container">
<h1>Enterprise Cyber Security & Secure Engineering</h1>
<p>Advanced penetration testing, infrastructure auditing, and security-driven software engineering built for modern digital environments.</p>
<a href="#contact" class="btn">Request Consultation</a>
</div>
</section>

<section id="services">
<div class="container">
<div class="section-title">
<h2>Core Security Services</h2>
<p>Professional-grade solutions aligned with modern threat landscapes.</p>
</div>

<div class="grid">
<div class="card">
<h3>Penetration Testing</h3>
<p>Real-world attack simulations to uncover exploitable vulnerabilities.</p>
</div>

<div class="card">
<h3>Security Auditing</h3>
<p>Comprehensive technical assessment aligned with compliance standards.</p>
</div>

<div class="card">
<h3>Secure Development</h3>
<p>Security-first application engineering with modern architecture.</p>
</div>

<div class="card">
<h3>Custom Systems</h3>
<p>Scalable enterprise-grade software tailored to operational security needs.</p>
</div>
</div>
</div>
</section>

<section id="about">
<div class="container">
<div class="section-title">
<h2>About RH²-Systems</h2>
<p>Security-driven engineering with uncompromising standards.</p>
</div>

<div class="grid">
<div class="card">
<h3>Raj Hridoy</h3>
<p>Cybersecurity Engineer specializing in risk assessment and secure system architecture.</p>
</div>

<div class="card">
<h3>Riyad Hasan</h3>
<p>Ethical Hacker focused on advanced threat modeling and penetration methodologies.</p>
</div>
</div>
</div>
</section>

<section class="cta">
<div class="container">
<h2>Secure Your Infrastructure Today</h2>
<p>Partner with RH²-Systems for enterprise-level cyber defense.</p>
<a href="#contact" class="btn">Schedule Security Assessment</a>
</div>
</section>

<section id="contact">
<div class="container">
<div class="section-title">
<h2>Contact Us</h2>
<p>Start a confidential security discussion.</p>
</div>

<div class="contact-box">
<form action="https://formspree.io/f/yourFormID" method="POST">
<input type="text" name="name" placeholder="Full Name" required>
<input type="email" name="email" placeholder="Email Address" required>
<textarea name="message" rows="5" placeholder="Your Message" required></textarea>
<button type="submit">Send Message</button>
</form>
</div>
</div>
</section>

<footer>
<p>© 2026 RH²-Systems. All rights reserved.</p>
</footer>

</body>
</html>