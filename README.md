<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>RH²-Systems | Enterprise Cybersecurity & Offensive Security</title>

<meta name="description" content="RH²-Systems delivers enterprise-grade cybersecurity consulting, penetration testing, red teaming, and secure software engineering.">
<meta name="keywords" content="Enterprise Cybersecurity, Penetration Testing, Red Team, Secure Development, Zero Trust, ISO 27001">
<meta name="author" content="RH²-Systems">
<meta name="theme-color" content="#050c18">

<meta property="og:title" content="RH²-Systems | Enterprise Cybersecurity">
<meta property="og:description" content="Advanced offensive security, infrastructure auditing, and secure system engineering for modern enterprises.">
<meta property="og:type" content="website">

<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

<style>
/* --- VARIABLES --- */
:root {
    --bg-dark: #050c18;
    --bg-dark-2: #0f172a;
    --accent: #2563eb;
    --accent-hover: #1d4ed8;
    --text-main: #1e293b;
    --text-light: #64748b;
    --white: #ffffff;
    --glass: rgba(255, 255, 255, 0.95);
    --border: rgba(0, 0, 0, 0.08);
}

/* --- RESET & BASE --- */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Inter', sans-serif;
    scroll-behavior: smooth;
}

body {
    background: #f8fafc;
    color: var(--text-main);
    line-height: 1.6;
    overflow-x: hidden;
}

.container {
    width: 90%;
    max-width: 1200px;
    margin: auto;
    padding: 0 15px;
}

/* --- NAVIGATION --- */
header {
    position: fixed;
    top: 0;
    width: 100%;
    background: var(--glass);
    backdrop-filter: blur(12px);
    -webkit-backdrop-filter: blur(12px);
    border-bottom: 1px solid var(--border);
    z-index: 1000;
    transition: 0.3s;
}

nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 80px;
}

.logo {
    font-weight: 800;
    font-size: 24px;
    color: var(--bg-dark);
    letter-spacing: -0.5px;
}

.logo span {
    color: var(--accent);
}

.nav-links {
    display: flex;
    gap: 35px;
    list-style: none;
}

.nav-links a {
    text-decoration: none;
    font-weight: 600;
    font-size: 15px;
    color: var(--text-main);
    transition: color 0.3s;
}

.nav-links a:hover {
    color: var(--accent);
}

/* Mobile Menu Toggle */
.menu-toggle {
    display: none;
    cursor: pointer;
    font-size: 24px;
    color: var(--bg-dark);
}

/* --- HERO SECTION --- */
.hero {
    position: relative;
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    background-color: var(--bg-dark);
    background-image: 
        radial-gradient(at 0% 0%, rgba(37, 99, 235, 0.15) 0px, transparent 50%),
        radial-gradient(at 100% 100%, rgba(37, 99, 235, 0.15) 0px, transparent 50%);
    color: var(--white);
    padding-top: 80px;
    overflow: hidden;
}

/* Grid Pattern Overlay */
.hero::before {
    content: "";
    position: absolute;
    width: 100%;
    height: 100%;
    background-image: linear-gradient(rgba(255, 255, 255, 0.03) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255, 255, 255, 0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    opacity: 0.5;
}

.hero-content {
    position: relative;
    z-index: 2;
    max-width: 800px;
    animation: fadeUp 1s ease-out;
}

.hero h1 {
    font-size: 3.5rem;
    font-weight: 800;
    line-height: 1.2;
    margin-bottom: 25px;
    letter-spacing: -1px;
}

.hero p {
    font-size: 1.15rem;
    color: #94a3b8;
    margin-bottom: 40px;
    max-width: 650px;
    margin-left: auto;
    margin-right: auto;
}

.btn {
    display: inline-block;
    padding: 16px 36px;
    background: var(--accent);
    color: white;
    border-radius: 6px;
    font-weight: 600;
    text-decoration: none;
    transition: all 0.3s;
    box-shadow: 0 4px 20px rgba(37, 99, 235, 0.3);
}

.btn:hover {
    transform: translateY(-2px);
    background: var(--accent-hover);
    box-shadow: 0 8px 25px rgba(37, 99, 235, 0.4);
}

/* --- SECTIONS COMMON --- */
section {
    padding: 100px 0;
}

.section-title {
    text-align: center;
    margin-bottom: 70px;
}

.section-title h2 {
    font-size: 2.5rem;
    font-weight: 800;
    color: var(--bg-dark);
    margin-bottom: 15px;
}

.section-title p {
    color: var(--text-light);
    max-width: 600px;
    margin: auto;
}

/* --- SERVICES GRID --- */
.grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 30px;
}

.card {
    background: white;
    padding: 40px;
    border-radius: 12px;
    border: 1px solid var(--border);
    transition: 0.3s;
    position: relative;
    overflow: hidden;
}

.card:hover {
    transform: translateY(-5px);
    box-shadow: 0 20px 40px -5px rgba(0, 0, 0, 0.1);
    border-color: var(--accent);
}

.card h3 {
    font-size: 1.25rem;
    margin-bottom: 15px;
    color: var(--bg-dark);
}

.card p {
    color: var(--text-light);
    font-size: 0.95rem;
}

.card-icon {
    font-size: 24px;
    color: var(--accent);
    margin-bottom: 20px;
    background: #eff6ff;
    width: 50px;
    height: 50px;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 8px;
}

/* --- STATS --- */
.stats-container {
    margin-top: 80px;
    padding: 50px;
    background: var(--bg-dark);
    border-radius: 16px;
    color: white;
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
    gap: 40px;
    text-align: center;
}

.stat h3 {
    font-size: 3rem;
    font-weight: 800;
    color: var(--accent);
    margin-bottom: 10px;
}

.stat p {
    font-size: 0.9rem;
    opacity: 0.8;
    text-transform: uppercase;
    letter-spacing: 1px;
}

/* --- LEADERSHIP --- */
.team-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 40px;
    max-width: 900px;
    margin: auto;
}

.team-card {
    background: white;
    padding: 40px;
    border-radius: 12px;
    text-align: center;
    border: 1px solid var(--border);
}

.team-avatar {
    width: 80px;
    height: 80px;
    background: #e2e8f0;
    border-radius: 50%;
    margin: 0 auto 20px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 24px;
    color: var(--text-light);
}

.team-card h3 {
    color: var(--bg-dark);
    margin-bottom: 5px;
}

.role {
    color: var(--accent);
    font-size: 0.9rem;
    font-weight: 600;
    margin-bottom: 15px;
    display: block;
}

/* --- CONTACT --- */
.cta {
    background: linear-gradient(135deg, var(--bg-dark) 0%, var(--bg-dark-2) 100%);
    color: white;
    padding: 80px 0;
}

.contact-wrapper {
    background: white;
    padding: 60px;
    border-radius: 16px;
    box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.1);
    max-width: 700px;
    margin: 0 auto;
    margin-top: -150px; /* Overlap effect */
    position: relative;
    z-index: 10;
}

.contact-form .input-group {
    margin-bottom: 20px;
}

.contact-form label {
    display: block;
    margin-bottom: 8px;
    font-size: 0.9rem;
    font-weight: 600;
    color: var(--bg-dark);
}

.contact-form input,
.contact-form textarea {
    width: 100%;
    padding: 14px;
    border: 1px solid #cbd5e1;
    border-radius: 6px;
    font-size: 15px;
    transition: 0.3s;
}

.contact-form input:focus,
.contact-form textarea:focus {
    outline: none;
    border-color: var(--accent);
    box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.1);
}

.submit-btn {
    width: 100%;
    padding: 16px;
    background: var(--bg-dark);
    color: white;
    border: none;
    border-radius: 6px;
    font-weight: 700;
    cursor: pointer;
    transition: 0.3s;
}

.submit-btn:hover {
    background: var(--accent);
}

/* --- FOOTER --- */
footer {
    background: #0f172a;
    color: #94a3b8;
    padding: 180px 0 50px; /* Extra top padding for overlap */
    text-align: center;
    font-size: 0.9rem;
}

/* --- ANIMATIONS --- */
@keyframes fadeUp {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
}

.reveal {
    opacity: 0;
    transform: translateY(30px);
    transition: all 0.8s ease-out;
}

.reveal.active {
    opacity: 1;
    transform: translateY(0);
}

/* --- RESPONSIVE --- */
@media (max-width: 768px) {
    .menu-toggle { display: block; }
    
    .nav-links {
        position: fixed;
        top: 80px;
        left: 0;
        width: 100%;
        background: white;
        flex-direction: column;
        padding: 30px;
        gap: 20px;
        border-bottom: 1px solid var(--border);
        transform: translateY(-150%);
        transition: 0.3s;
        box-shadow: 0 10px 20px rgba(0,0,0,0.05);
    }
    
    .nav-links.active { transform: translateY(0); }
    
    .hero h1 { font-size: 2.5rem; }
    
    .contact-wrapper {
        margin-top: 0;
        padding: 30px;
    }
    
    footer { padding-top: 80px; }
    
    .stats-container { flex-direction: column; gap: 40px; }
}
</style>
</head>

<body>

<header>
    <div class="container">
        <nav>
            <div class="logo">RH²-<span>Systems</span></div>
            <div class="menu-toggle" id="mobile-menu">
                <i class="fas fa-bars"></i>
            </div>
            <ul class="nav-links">
                <li><a href="#services" onclick="closeMenu()">Services</a></li>
                <li><a href="#methodology" onclick="closeMenu()">Methodology</a></li>
                <li><a href="#about" onclick="closeMenu()">Leadership</a></li>
                <li><a href="#contact" class="btn" style="padding: 10px 20px; box-shadow:none;">Contact</a></li>
            </ul>
        </nav>
    </div>
</header>

<section class="hero">
    <div class="container hero-content">
        <h1>Offensive Security.<br>Defensive Resilience.</h1>
        <p>We deliver advanced penetration testing, red teaming, and secure engineering for high-risk digital environments. Secure your infrastructure before they find the gaps.</p>
        <a href="#contact" class="btn">Request Confidential Assessment</a>
    </div>
</section>

<section id="services">
    <div class="container">
        <div class="section-title reveal">
            <h2>Core Capabilities</h2>
            <p>Aligned with Zero-Trust Architecture, ISO 27001, and SOC 2 compliance standards.</p>
        </div>

        <div class="grid">
            <div class="card reveal">
                <div class="card-icon"><i class="fas fa-shield-alt"></i></div>
                <h3>Penetration Testing</h3>
                <p>Manual and automated attack simulation across web apps, APIs, mobile, and internal networks to identify exploitable vulnerabilities.</p>
            </div>
            <div class="card reveal">
                <div class="card-icon"><i class="fas fa-user-secret"></i></div>
                <h3>Red Team Operations</h3>
                <p>Full-scope adversary emulation designed to test your SOC detection capabilities and incident response maturity.</p>
            </div>
            <div class="card reveal">
                <div class="card-icon"><i class="fas fa-server"></i></div>
                <h3>Infrastructure Auditing</h3>
                <p>Deep-dive configuration reviews of Cloud (AWS/Azure) and On-Premise environments to harden attack surfaces.</p>
            </div>
            <div class="card reveal">
                <div class="card-icon"><i class="fas fa-code"></i></div>
                <h3>Secure Engineering</h3>
                <p>DevSecOps integration, secure code reviews, and architectural consulting to build security into the SDLC.</p>
            </div>
        </div>

        <div class="stats-container reveal">
            <div class="stat">
                <h3>150+</h3>
                <p>Engagements</p>
            </div>
            <div class="stat">
                <h3>100%</h3>
                <p>Confidentiality</p>
            </div>
            <div class="stat">
                <h3>24/7</h3>
                <p>Response Ops</p>
            </div>
        </div>
    </div>
</section>

<section id="methodology" style="background: #fff;">
    <div class="container">
        <div class="section-title reveal">
            <h2>Our Methodology</h2>
            <p>A structured, intelligence-driven framework ensuring precision and accountability.</p>
        </div>

        <div class="grid">
            <div class="card reveal">
                <h3>1. Reconnaissance</h3>
                <p>OSINT gathering and threat modeling to map your organization's digital footprint and potential entry points.</p>
            </div>
            <div class="card reveal">
                <h3>2. Exploitation</h3>
                <p>Controlled execution of attack vectors to validate vulnerabilities, filtering out false positives.</p>
            </div>
            <div class="card reveal">
                <h3>3. Remediation</h3>
                <p>Detailed technical reports with prioritized mitigation strategies for engineering teams.</p>
            </div>
        </div>
    </div>
</section>

<section id="about">
    <div class="container">
        <div class="section-title reveal">
            <h2>Leadership</h2>
            <p>Security engineering driven by precision.</p>
        </div>

        <div class="team-grid">
            <div class="team-card reveal">
                <div class="team-avatar"><i class="fas fa-user"></i></div>
                <h3>Raj Hridoy</h3>
                <span class="role">Lead Security Engineer</span>
                <p>Specializing in Zero-Trust architecture, enterprise risk mitigation, and cloud security posture management.</p>
            </div>
            <div class="team-card reveal">
                <div class="team-avatar"><i class="fas fa-user-ninja"></i></div>
                <h3>Riyad Hasan</h3>
                <span class="role">Lead Red Team Operator</span>
                <p>Expert in advanced threat simulation, social engineering, and offensive security operations.</p>
            </div>
        </div>
    </div>
</section>

<section class="cta">
    <div class="container">
        <div class="section-title" style="color: white; margin-bottom: 30px;">
            <h2 style="color: white;">Secure Your Infrastructure</h2>
            <p style="color: rgba(255,255,255,0.8);">Initiate a confidential discussion about your security requirements.</p>
        </div>
    </div>
</section>

<section id="contact" style="padding-top: 0;">
    <div class="container">
        <div class="contact-wrapper reveal">
            <form action="https://formspree.io/f/yourFormID" method="POST" class="contact-form">
                <div class="input-group">
                    <label>Full Name</label>
                    <input type="text" name="name" required>
                </div>
                <div class="input-group">
                    <label>Corporate Email</label>
                    <input type="email" name="email" required>
                </div>
                <div class="input-group">
                    <label>Security Requirement</label>
                    <textarea name="message" rows="5" required></textarea>
                </div>
                <button type="submit" class="submit-btn">Send Secure Message</button>
            </form>
        </div>
    </div>
</section>

<footer>
    <div class="container">
        <p>© 2026 RH²-Systems. Enterprise Cybersecurity & Secure Engineering.</p>
        <p style="margin-top: 10px; font-size: 13px;">Rajshahi Division, Bangladesh</p>
    </div>
</footer>

<script>
    // Mobile Menu Toggle
    const menuToggle = document.getElementById('mobile-menu');
    const navLinks = document.querySelector('.nav-links');

    menuToggle.addEventListener('click', () => {
        navLinks.classList.toggle('active');
    });

    function closeMenu() {
        navLinks.classList.remove('active');
    }

    // Scroll Animations
    const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                entry.target.classList.add('active');
            }
        });
    }, { threshold: 0.1 });

    document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
</script>

</body>
</html>
