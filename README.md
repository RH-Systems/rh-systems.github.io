<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>RH²-Systems | Enterprise Cybersecurity & Offensive Security Engineering</title>

<meta name="description" content="RH²-Systems delivers enterprise-grade cybersecurity consulting, penetration testing, red teaming, and secure software engineering for high-risk digital environments.">
<meta name="keywords" content="Enterprise Cybersecurity, Penetration Testing, Red Team, Secure Development, Infrastructure Audit, Zero Trust">
<meta name="author" content="RH²-Systems">
<meta name="theme-color" content="#050c18">

<!-- Open Graph -->
<meta property="og:title" content="RH²-Systems | Enterprise Cybersecurity">
<meta property="og:description" content="Advanced offensive security, infrastructure auditing, and secure system engineering for modern enterprises.">
<meta property="og:type" content="website">

<!-- Structured Data -->
<script type="application/ld+json">
{
 "@context": "https://schema.org",
 "@type": "Organization",
 "name": "RH²-Systems",
 "url": "https://yourdomain.com",
 "description": "Enterprise cybersecurity consulting and secure engineering solutions."
}
</script>

<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700;800;900&display=swap" rel="stylesheet">

<style>
:root{
--bg-dark:#050c18;
--bg-dark-2:#0b1f3a;
--accent:#0066ff;
--light:#f4f7fb;
--text-light:#cbd5e1;
--white:#ffffff;
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
color:#111827;
line-height:1.7;
}

.container{
width:90%;
max-width:1200px;
margin:auto;
}

header{
position:sticky;
top:0;
width:100%;
background:rgba(255,255,255,0.92);
backdrop-filter:blur(10px);
border-bottom:1px solid rgba(0,0,0,0.05);
z-index:1000;
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
transition:0.3s;
}

nav a:hover{
color:var(--accent);
}

.hero{
min-height:100vh;
display:flex;
align-items:center;
justify-content:center;
text-align:center;
color:white;
background:
radial-gradient(circle at 20% 20%, rgba(0,102,255,0.15), transparent 40%),
linear-gradient(135deg,var(--bg-dark),var(--bg-dark-2));
padding-top:100px;
}

.hero h1{
font-size:58px;
font-weight:900;
margin-bottom:20px;
}

.hero p{
max-width:750px;
margin:auto;
opacity:0.9;
font-size:19px;
}

.btn{
display:inline-block;
margin-top:35px;
padding:16px 40px;
background:var(--accent);
color:white;
border-radius:8px;
font-weight:700;
text-decoration:none;
transition:0.3s;
box-shadow:0 12px 35px rgba(0,102,255,0.4);
}

.btn:hover{
transform:translateY(-3px);
background:#0047cc;
}

section{
padding:120px 0;
}

.section-title{
text-align:center;
margin-bottom:70px;
}

.section-title h2{
font-size:42px;
font-weight:900;
color:#0b1f3a;
margin-bottom:15px;
}

.section-title p{
color:#6b7280;
}

.grid{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(280px,1fr));
gap:40px;
}

.card{
background:white;
padding:45px;
border-radius:16px;
box-shadow:0 20px 40px rgba(0,0,0,0.06);
border:1px solid rgba(0,0,0,0.05);
transition:0.3s;
}

.card:hover{
transform:translateY(-8px);
box-shadow:0 30px 60px rgba(0,0,0,0.12);
}

.card h3{
margin-bottom:15px;
font-weight:800;
color:#0b1f3a;
}

.card p{
color:#6b7280;
}

.stats{
display:flex;
justify-content:center;
gap:70px;
flex-wrap:wrap;
margin-top:60px;
}

.stat{
text-align:center;
}

.stat h3{
font-size:40px;
font-weight:900;
color:var(--accent);
}

.cta{
background:linear-gradient(135deg,var(--bg-dark),var(--bg-dark-2));
color:white;
text-align:center;
padding:120px 0;
}

.contact-box{
background:white;
padding:60px;
border-radius:16px;
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

@media(max-width:768px){
.hero h1{font-size:36px;}
.section-title h2{font-size:30px;}
}
</style>
</head>

<body>

<header>
<div class="container">
<nav>
<div class="logo">RH²-Systems</div>
<ul>
<li><a href="#services">Services</a></li>
<li><a href="#methodology">Methodology</a></li>
<li><a href="#about">Leadership</a></li>
<li><a href="#contact">Contact</a></li>
</ul>
</nav>
</div>
</header>

<section class="hero">
<div class="container">
<h1>Offensive Security. Defensive Resilience. Enterprise Assurance.</h1>
<p>RH²-Systems delivers advanced penetration testing, red teaming, infrastructure auditing, and secure software engineering for organizations operating in high-risk digital environments.</p>
<a href="#contact" class="btn">Request Confidential Consultation</a>
</div>
</section>

<section id="services">
<div class="container">
<div class="section-title">
<h2>Core Capabilities</h2>
<p>Comprehensive cybersecurity solutions aligned with zero-trust architecture and enterprise compliance standards.</p>
</div>

<div class="grid">
<div class="card">
<h3>Penetration Testing</h3>
<p>Real-world attack simulation across web, mobile, API, and network environments.</p>
</div>
<div class="card">
<h3>Red Team Operations</h3>
<p>Adversary emulation targeting detection gaps and incident response maturity.</p>
</div>
<div class="card">
<h3>Infrastructure Auditing</h3>
<p>Cloud, on-premise, and hybrid security posture assessments with compliance alignment.</p>
</div>
<div class="card">
<h3>Secure Engineering</h3>
<p>Security-first application architecture using encryption, secure coding standards, and hardened deployment pipelines.</p>
</div>
</div>

<div class="stats">
<div class="stat">
<h3>150+</h3>
<p>Security Engagements</p>
</div>
<div class="stat">
<h3>0</h3>
<p>Critical Findings Left Unresolved</p>
</div>
<div class="stat">
<h3>24/7</h3>
<p>Security Advisory Support</p>
</div>
</div>

</div>
</section>

<section id="methodology">
<div class="container">
<div class="section-title">
<h2>Security Methodology</h2>
<p>Structured, intelligence-driven, and compliance-aligned execution framework.</p>
</div>

<div class="grid">
<div class="card">
<h3>Reconnaissance & Threat Modeling</h3>
<p>Comprehensive asset mapping and adversarial risk identification.</p>
</div>
<div class="card">
<h3>Exploitation & Impact Analysis</h3>
<p>Controlled exploitation with documented business impact assessment.</p>
</div>
<div class="card">
<h3>Remediation Strategy</h3>
<p>Actionable mitigation roadmap aligned with ISO 27001 and SOC 2 standards.</p>
</div>
<div class="card">
<h3>Executive Reporting</h3>
<p>Clear, board-level reporting for leadership and compliance stakeholders.</p>
</div>
</div>
</div>
</section>

<section id="about">
<div class="container">
<div class="section-title">
<h2>Leadership</h2>
<p>Security engineering driven by precision and accountability.</p>
</div>

<div class="grid">
<div class="card">
<h3>Raj Hridoy</h3>
<p>Cybersecurity Engineer specializing in zero-trust architecture and enterprise risk mitigation.</p>
</div>
<div class="card">
<h3>Riyad Hasan</h3>
<p>Ethical Hacker and Red Team Operator focused on advanced threat simulation.</p>
</div>
</div>
</div>
</section>

<section class="cta">
<div class="container">
<h2>Secure Your Infrastructure Before Threat Actors Do</h2>
<p>Partner with RH²-Systems for measurable security resilience.</p>
<a href="#contact" class="btn">Schedule Security Assessment</a>
</div>
</section>

<section id="contact">
<div class="container">
<div class="section-title">
<h2>Initiate a Confidential Discussion</h2>
<p>All consultations are handled with strict professional discretion.</p>
</div>

<div class="contact-box">
<form action="https://formspree.io/f/yourFormID" method="POST">
<input type="text" name="name" placeholder="Full Name" required>
<input type="email" name="email" placeholder="Corporate Email Address" required>
<textarea name="message" rows="5" placeholder="Describe your security requirements" required></textarea>
<button type="submit">Send Secure Message</button>
</form>
</div>
</div>
</section>

<footer>
<p>© 2026 RH²-Systems. Enterprise Cybersecurity & Secure Engineering.</p>
</footer>

</body>
</html>