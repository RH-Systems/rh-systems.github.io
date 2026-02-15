<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>RH²-Systems | Cyber Security & Software Engineering</title>
<meta name="description" content="RH²-Systems provides professional cybersecurity consulting, ethical hacking, penetration testing, and modern software engineering solutions.">

<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&display=swap" rel="stylesheet">

<style>

/* ===== GLOBAL ===== */

:root{
--primary:#0b1f3a;
--accent:#0056ff;
--light:#f4f7fb;
--dark:#1a1a1a;
--gray:#6b7280;
}

*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:'Inter',sans-serif;
scroll-behavior:smooth;
}

body{
background:var(--light);
color:var(--dark);
line-height:1.6;
}

.container{
width:90%;
max-width:1200px;
margin:auto;
}

/* ===== NAVIGATION ===== */

header{
/* position:fixed;          ← removed */
width:100%;
background:white;
box-shadow:0 2px 8px rgba(0,0,0,0.05);
/* z-index:1000;            ← removed */
}

nav{
display:flex;
justify-content:space-between;
align-items:center;
padding:20px 0;
}

.logo{
font-weight:700;
font-size:20px;
color:var(--primary);
}

nav ul{
list-style:none;
display:flex;
gap:30px;
}

nav a{
text-decoration:none;
color:var(--dark);
font-weight:500;
transition:0.3s;
}

nav a:hover{
color:var(--accent);
}

/* ===== HERO ===== */

.hero{
padding:180px 0 120px;   /* ← you may want to reduce this padding now */
background:var(--primary);
color:white;
text-align:center;
}

.hero h1{
font-size:42px;
margin-bottom:20px;
}

.hero p{
font-size:18px;
max-width:700px;
margin:auto;
opacity:0.9;
}

.btn{
display:inline-block;
margin-top:30px;
padding:14px 28px;
background:var(--accent);
color:white;
border-radius:6px;
text-decoration:none;
font-weight:600;
transition:0.3s;
}

.btn:hover{
background:#003bb3;
}

/* ===== SECTIONS ===== */

section{
padding:100px 0;
}

.section-title{
text-align:center;
margin-bottom:60px;
}

.section-title h2{
font-size:32px;
margin-bottom:10px;
color:var(--primary);
}

.section-title p{
color:var(--gray);
}

/* ===== GRID ===== */

.grid{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(280px,1fr));
gap:40px;
}

.card{
background:white;
padding:35px;
border-radius:8px;
box-shadow:0 4px 12px rgba(0,0,0,0.05);
transition:0.3s;
}

.card:hover{
transform:translateY(-6px);
box-shadow:0 8px 20px rgba(0,0,0,0.08);
}

.card h3{
margin-bottom:15px;
color:var(--primary);
}

/* ===== CONTACT ===== */

.contact-box{
background:white;
padding:50px;
border-radius:8px;
box-shadow:0 4px 12px rgba(0,0,0,0.05);
max-width:700px;
margin:auto;
}

.contact-box input,
.contact-box textarea{
width:100%;
padding:12px;
margin-bottom:15px;
border:1px solid #ddd;
border-radius:6px;
}

.contact-box button{
width:100%;
padding:14px;
background:var(--accent);
color:white;
border:none;
border-radius:6px;
font-weight:600;
cursor:pointer;
transition:0.3s;
}

.contact-box button:hover{
background:#003bb3;
}

/* ===== FOOTER ===== */

footer{
background:var(--primary);
color:white;
padding:40px 0;
text-align:center;
margin-top:60px;
}

footer p{
opacity:0.8;
}

/* ===== RESPONSIVE ===== */

@media(max-width:768px){
nav ul{
gap:15px;
}
.hero h1{
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

<!-- HERO -->
<section class="hero" id="home">
<div class="container">
<h1>Enterprise Cyber Security & Software Engineering</h1>
<p>RH²-Systems delivers professional penetration testing, ethical hacking, system security audits, and scalable modern software solutions for businesses and organizations.</p>
<a href="#contact" class="btn">Request Consultation</a>
</div>
</section>

<!-- SERVICES -->
<section id="services">
<div class="container">
<div class="section-title">
<h2>Our Services</h2>
<p>Professional solutions tailored for modern digital infrastructure.</p>
</div>

<div class="grid">
<div class="card">
<h3>Penetration Testing</h3>
<p>Comprehensive vulnerability assessment and controlled exploitation to identify security weaknesses.</p>
</div>

<div class="card">
<h3>Security Auditing</h3>
<p>In-depth review of infrastructure, applications, and systems to ensure compliance and resilience.</p>
</div>

<div class="card">
<h3>Secure Web Development</h3>
<p>Modern, scalable, and secure web applications engineered with industry best practices.</p>
</div>

<div class="card">
<h3>Custom Software Solutions</h3>
<p>Business-grade systems tailored to operational and security requirements.</p>
</div>
</div>
</div>
</section>

<!-- ABOUT -->
<section id="about">
<div class="container">
<div class="section-title">
<h2>About RH²-Systems</h2>
<p>Security-driven engineering with professional standards.</p>
</div>

<div class="grid">
<div class="card">
<h3>Raj Hridoy</h3>
<p>Cybersecurity Engineer & Software Developer specializing in secure architecture and vulnerability analysis.</p>
</div>

<div class="card">
<h3>Riyad Hasan</h3>
<p>Ethical Hacker & Technology Specialist focused on system defense, threat modeling, and penetration testing.</p>
</div>
</div>
</div>
</section>

<!-- CONTACT -->
<section id="contact">
<div class="container">
<div class="section-title">
<h2>Contact Us</h2>
<p>Start a secure conversation today.</p>
</div>

<div class="contact-box">
<form action="https://formspree.io/f/yourFormID" method="POST">
<input type="text" name="name" placeholder="Full Name" required>
<input type="email" name="email" placeholder="Email Address" required>
<textarea name="message" rows="5" placeholder="Your Message" required></textarea>
<button type="submit">Send Message</button>
</form>

<p style="margin-top:20px;font-size:14px;color:#6b7280;">
Direct Email: rajhridoy100az@gmail.com | reyadhasan100az@gmail.com
</p>
</div>
</div>
</section>

<footer>
<p>© 2026 RH²-Systems. All rights reserved.</p>
</footer>

</body>
</html>