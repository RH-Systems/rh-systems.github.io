<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>RH²-Systems | Enterprise Cybersecurity & Offensive Security</title>
<meta name="description" content="RH²-Systems delivers enterprise-grade penetration testing, red teaming, and secure infrastructure auditing.">
<meta name="author" content="RH²-Systems">
<link rel="canonical" href="https://rh2-systems.com/">

<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;800&family=JetBrains+Mono:wght@400;700&display=swap" rel="stylesheet">

<style>
    :root {
        --bg-deep: #020617;
        --bg-surface: #0f172a;
        --accent: #0ea5e9; /* Sky Blue */
        --accent-glow: rgba(14, 165, 233, 0.4);
        --text-main: #f8fafc;
        --text-muted: #94a3b8;
        --border: rgba(255, 255, 255, 0.1);
        --glass: rgba(15, 23, 42, 0.7);
    }

    /* Reset & Base */
    * { margin: 0; padding: 0; box-sizing: border-box; scroll-behavior: smooth; }
    body {
        background-color: var(--bg-deep);
        background-image: 
            linear-gradient(rgba(255, 255, 255, 0.03) 1px, transparent 1px),
            linear-gradient(90deg, rgba(255, 255, 255, 0.03) 1px, transparent 1px);
        background-size: 50px 50px;
        color: var(--text-main);
        font-family: 'Inter', sans-serif;
        overflow-x: hidden;
        line-height: 1.6;
    }

    h1, h2, h3, h4 { font-weight: 800; letter-spacing: -0.02em; }
    h2 { font-size: 2.5rem; margin-bottom: 1rem; background: linear-gradient(to right, #fff, var(--text-muted)); -webkit-background-clip: text; -webkit-text-fill-color: transparent; }
    p { color: var(--text-muted); font-size: 1.05rem; }
    a { text-decoration: none; color: inherit; transition: 0.3s; }
    .mono { font-family: 'JetBrains Mono', monospace; }

    /* Layout Utility */
    .container { width: 90%; max-width: 1200px; margin: auto; padding: 0 20px; }
    section { padding: 120px 0; position: relative; }

    /* Navigation */
    header {
        position: fixed; top: 0; width: 100%; z-index: 1000;
        background: rgba(2, 6, 23, 0.85);
        backdrop-filter: blur(12px);
        border-bottom: 1px solid var(--border);
    }
    nav { height: 80px; display: flex; justify-content: space-between; align-items: center; }
    .logo { font-size: 1.5rem; font-weight: 800; letter-spacing: -1px; }
    .logo span { color: var(--accent); }
    .nav-links { display: flex; gap: 40px; list-style: none; }
    .nav-links a { font-size: 0.9rem; font-weight: 600; text-transform: uppercase; letter-spacing: 1px; }
    .nav-links a:hover { color: var(--accent); text-shadow: 0 0 10px var(--accent-glow); }
    .menu-toggle { display: none; font-size: 1.5rem; cursor: pointer; }

    /* Hero Section */
    .hero {
        min-height: 100vh; display: flex; align-items: center; justify-content: center;
        text-align: center; position: relative; overflow: hidden;
    }
    #networkCanvas { position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: 1; opacity: 0.6; }
    .hero-content { position: relative; z-index: 2; max-width: 900px; }
    .badge {
        display: inline-block; padding: 6px 16px; border-radius: 50px;
        background: rgba(14, 165, 233, 0.1); border: 1px solid var(--accent);
        color: var(--accent); font-size: 0.8rem; font-weight: 700; margin-bottom: 25px;
        box-shadow: 0 0 15px var(--accent-glow);
    }
    .hero h1 { font-size: 4rem; line-height: 1.1; margin-bottom: 25px; }
    .hero p { max-width: 600px; margin: 0 auto 40px; font-size: 1.2rem; }
    
    .btn {
        display: inline-block; padding: 16px 40px; border-radius: 4px;
        background: var(--accent); color: #fff; font-weight: 700;
        position: relative; overflow: hidden; z-index: 1;
        transition: transform 0.3s, box-shadow 0.3s;
    }
    .btn::before {
        content: ''; position: absolute; top: 0; left: -100%; width: 100%; height: 100%;
        background: linear-gradient(90deg, transparent, rgba(255,255,255,0.4), transparent);
        transition: 0.5s; z-index: -1;
    }
    .btn:hover { transform: translateY(-3px); box-shadow: 0 10px 30px -10px var(--accent); }
    .btn:hover::before { left: 100%; }

    /* Cards & Grid */
    .grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 30px; margin-top: 50px; }
    .card {
        background: var(--bg-surface); border: 1px solid var(--border);
        padding: 40px; border-radius: 12px; transition: 0.4s;
        position: relative; overflow: hidden;
    }
    .card:hover {
        transform: translateY(-10px);
        border-color: var(--accent);
        box-shadow: 0 20px 40px -20px rgba(0,0,0,0.5);
    }
    .card h3 { margin-bottom: 15px; font-size: 1.4rem; color: #fff; }
    .card-icon { font-size: 2rem; color: var(--accent); margin-bottom: 20px; }

    /* Team Section (New) */
    .team-grid {
        display: grid; grid-template-columns: repeat(auto-fit, minmax(350px, 1fr)); gap: 40px; margin-top: 60px;
    }
    .profile-card {
        background: linear-gradient(145deg, var(--bg-surface), #0b1120);
        border: 1px solid var(--border); padding: 0;
        border-radius: 16px; overflow: hidden; transition: 0.4s;
        display: flex; flex-direction: column;
    }
    .profile-card:hover { border-color: var(--accent); box-shadow: 0 0 30px rgba(14, 165, 233, 0.15); }
    
    .profile-header {
        background: rgba(14, 165, 233, 0.05); padding: 40px 30px;
        text-align: center; border-bottom: 1px solid var(--border);
        position: relative;
    }
    .avatar-placeholder {
        width: 100px; height: 100px; background: var(--bg-deep);
        border: 2px solid var(--accent); border-radius: 50%; margin: 0 auto 20px;
        display: flex; align-items: center; justify-content: center;
        font-size: 2rem; font-weight: 800; color: var(--accent);
        box-shadow: 0 0 20px var(--accent-glow);
    }
    .profile-body { padding: 30px; }
    .role-badge { 
        font-size: 0.8rem; text-transform: uppercase; letter-spacing: 1px; 
        color: var(--accent); margin-bottom: 10px; display: block; font-weight: 700;
    }
    .profile-body h3 { font-size: 1.8rem; margin-bottom: 5px; }
    .skill-tags { display: flex; flex-wrap: wrap; gap: 10px; margin-top: 20px; }
    .tag { 
        font-size: 0.75rem; background: rgba(255,255,255,0.05); 
        padding: 5px 12px; border-radius: 4px; border: 1px solid var(--border);
    }

    /* Stats */
    .stats-container {
        display: flex; justify-content: space-around; flex-wrap: wrap; gap: 30px;
        margin-top: 50px; padding: 40px; background: var(--bg-surface);
        border-radius: 12px; border: 1px solid var(--border);
    }
    .stat-item h3 { font-size: 3rem; color: var(--accent); margin-bottom: 5px; }
    
    /* Contact Form */
    form { display: flex; flex-direction: column; gap: 20px; }
    input, textarea {
        background: rgba(0,0,0,0.3); border: 1px solid var(--border);
        padding: 15px; color: #fff; font-family: inherit; border-radius: 6px;
        width: 100%; transition: 0.3s;
    }
    input:focus, textarea:focus { outline: none; border-color: var(--accent); background: rgba(14, 165, 233, 0.05); }

    /* Footer */
    footer { 
        background: var(--bg-surface); padding: 80px 0 40px; text-align: center; border-top: 1px solid var(--border); 
        margin-top: 80px;
    }
    .footer-brand { font-size: 1.8rem; font-weight: 800; color: #fff; margin-bottom: 10px; }
    .copyright { color: var(--text-muted); font-size: 0.9rem; margin-top: 20px; }

    /* Animations */
    .fade-up { opacity: 0; transform: translateY(30px); transition: 0.8s ease-out; }
    .fade-up.visible { opacity: 1; transform: translateY(0); }
    
    .typewriter-cursor {
        display: inline-block; width: 3px; height: 1em; background: var(--accent);
        animation: blink 1s infinite; vertical-align: middle; margin-left: 5px;
    }

    @keyframes blink { 0%, 100% { opacity: 1; } 50% { opacity: 0; } }

    /* Mobile */
    @media(max-width: 768px) {
        .hero h1 { font-size: 2.5rem; }
        .nav-links {
            position: fixed; top: 80px; left: 0; width: 100%; background: var(--bg-deep);
            flex-direction: column; align-items: center; padding: 40px 0;
            border-bottom: 1px solid var(--border); transform: translateY(-150%); transition: 0.4s;
        }
        .nav-links.active { transform: translateY(0); }
        .menu-toggle { display: block; }
        .stats-container { flex-direction: column; text-align: center; }
    }
</style>
</head>

<body>

<header>
    <div class="container">
        <nav>
            <div class="logo">RH²-<span>Systems</span></div>
            <div class="menu-toggle" id="menuBtn">☰</div>
            <ul class="nav-links" id="navLinks">
                <li><a href="#services">Services</a></li>
                <li><a href="#team">Leadership</a></li>
                <li><a href="#methodology">Methodology</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </div>
</header>

<section class="hero">
    <canvas id="networkCanvas"></canvas>
    <div class="container hero-content fade-up">
        <div class="badge mono">SYSTEM STATUS: SECURE</div>
        <h1>Offensive Security.<br><span style="color:var(--accent)" id="typewriter"></span><span class="typewriter-cursor"></span></h1>
        <p>Advanced penetration testing, red team operations, and secure engineering for high-risk enterprise infrastructure.</p>
        <a href="#contact" class="btn">Initiate Confidential Audit</a>
    </div>
</section>

<section id="services">
    <div class="container">
        <div class="fade-up">
            <h2>Core Capabilities</h2>
            <p>Full-spectrum offensive security services tailored for modern threat landscapes.</p>
        </div>
        <div class="grid">
            <div class="card fade-up">
                <div class="card-icon mono">&lt;/&gt;</div>
                <h3>Penetration Testing</h3>
                <p>Manual and automated assessments of Web, Mobile, API, and Cloud infrastructure aligned with OWASP Top 10 and NIST frameworks.</p>
            </div>
            <div class="card fade-up">
                <div class="card-icon mono">#!</div>
                <h3>Red Team Operations</h3>
                <p>Adversary simulation replicating nation-state tactics (APT) to test your detection and response capabilities in real-time.</p>
            </div>
            <div class="card fade-up">
                <div class="card-icon mono">{ }</div>
                <h3>Secure Engineering</h3>
                <p>DevSecOps integration, Zero Trust architecture design, and source code review to build security into the DNA of your software.</p>
            </div>
        </div>
    </div>
</section>

<section id="team">
    <div class="container">
        <div class="fade-up">
            <h2>Leadership & Engineering</h2>
            <p>Built by engineers who understand both the attack vector and the defense mechanism.</p>
        </div>
        
        <div class="team-grid">
            <div class="profile-card fade-up">
                <div class="profile-header">
                    <div class="avatar-placeholder">RH</div>
                    <h3>Raj Hridoy</h3>
                    <p style="color: #fff; font-weight: 600;">Cybersecurity Engineer</p>
                </div>
                <div class="profile-body">
                    <span class="role-badge mono">Lead Architect</span>
                    <p>Specializing in secure software architecture and complex vulnerability analysis. Raj bridges the gap between high-level development and low-level security protocols.</p>
                    <div class="skill-tags mono">
                        <span class="tag">Secure Arch</span>
                        <span class="tag">Python/Go</span>
                        <span class="tag">Cloud Security</span>
                        <span class="tag">DevSecOps</span>
                    </div>
                </div>
            </div>

            <div class="profile-card fade-up">
                <div class="profile-header">
                    <div class="avatar-placeholder">RH</div>
                    <h3>Riyad Hasan</h3>
                    <p style="color: #fff; font-weight: 600;">Ethical Hacker</p>
                </div>
                <div class="profile-body">
                    <span class="role-badge mono">Offensive Specialist</span>
                    <p>Focused on system defense, advanced threat modeling, and penetration testing. Riyad specializes in breaking systems to make them unbreakable.</p>
                    <div class="skill-tags mono">
                        <span class="tag">PenTesting</span>
                        <span class="tag">Network Forensics</span>
                        <span class="tag">Red Teaming</span>
                        <span class="tag">Exploit Dev</span>
                    </div>
                </div>
            </div>
        </div>
    </div>
</section>

<section id="methodology" style="background: var(--bg-surface);">
    <div class="container">
        <div class="fade-up">
            <h2>The RH² Methodology</h2>
            <p>A structured approach to chaos. Measurable, repeatable, and confidential.</p>
        </div>
        <div class="stats-container fade-up">
            <div class="stat-item">
                <h3 class="mono">150+</h3>
                <p>Assessments</p>
            </div>
            <div class="stat-item">
                <h3 class="mono">100%</h3>
                <p>Confidentiality</p>
            </div>
            <div class="stat-item">
                <h3 class="mono">24/7</h3>
                <p>Incident Support</p>
            </div>
        </div>
    </div>
</section>

<section id="contact">
    <div class="container">
        <div class="grid" style="grid-template-columns: 1fr 1fr; align-items: center;">
            <div class="fade-up">
                <h2>Secure Consultation</h2>
                <p>Ready to secure your infrastructure? Contact us for a confidential discussion regarding your security posture.</p>
                <br>
                <p class="mono" style="color: var(--accent)">> Encrypted channels available upon request.</p>
            </div>
            <div class="card fade-up">
                <form>
                    <input type="text" placeholder="Full Name / Organization" required>
                    <input type="email" placeholder="Work Email" required>
                    <textarea rows="5" placeholder="Project Scope / Details" required></textarea>
                    <button type="submit" class="btn" style="width: 100%;">Transmit Request</button>
                </form>
            </div>
        </div>
    </div>
</section>

<footer>
    <div class="container">
        <div class="footer-brand">RH²-Systems</div>
        <p>Rajshahi Division, Bangladesh</p>
        <div class="copyright mono">© 2026 RH²-Systems. All Rights Reserved.</div>
    </div>
</footer>

<script>
    // 1. Mobile Menu Logic
    const menuBtn = document.getElementById('menuBtn');
    const navLinks = document.getElementById('navLinks');
    menuBtn.addEventListener('click', () => {
        navLinks.classList.toggle('active');
    });

    // 2. Scroll Animation (Intersection Observer)
    const observerOptions = { threshold: 0.1 };
    const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                entry.target.classList.add('visible');
            }
        });
    }, observerOptions);

    document.querySelectorAll('.fade-up').forEach(el => observer.observe(el));

    // 3. Typewriter Effect
    const words = ["Infrastructure Auditing", "Secure Engineering", "Red Team Operations", "Vulnerability Analysis"];
    let i = 0, j = 0, isDeleting = false;
    const typeSpeed = 50;
    const deleteSpeed = 30;
    const delayBetweenWords = 2000;

    function type() {
        const currentWord = words[i];
        const element = document.getElementById("typewriter");
        
        if (isDeleting) {
            element.textContent = currentWord.substring(0, j--);
        } else {
            element.textContent = currentWord.substring(0, j++);
        }

        let speed = isDeleting ? deleteSpeed : typeSpeed;

        if (!isDeleting && j === currentWord.length) {
            speed = delayBetweenWords;
            isDeleting = true;
        } else if (isDeleting && j === 0) {
            isDeleting = false;
            i = (i + 1) % words.length;
        }

        setTimeout(type, speed);
    }
    type();

    // 4. Advanced Network Canvas Animation
    const canvas = document.getElementById('networkCanvas');
    const ctx = canvas.getContext('2d');
    let width, height;
    let particles = [];

    // Resize handling
    function resize() {
        width = window.innerWidth;
        height = window.innerHeight;
        canvas.width = width;
        canvas.height = height;
    }
    window.addEventListener('resize', resize);
    resize();

    // Mouse interaction
    let mouse = { x: null, y: null, radius: 150 };
    window.addEventListener('mousemove', (e) => {
        mouse.x = e.x;
        mouse.y = e.y;
    });

    class Particle {
        constructor() {
            this.x = Math.random() * width;
            this.y = Math.random() * height;
            this.vx = (Math.random() - 0.5) * 1; // Velocity X
            this.vy = (Math.random() - 0.5) * 1; // Velocity Y
            this.size = Math.random() * 2 + 1;
        }

        draw() {
            ctx.beginPath();
            ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
            ctx.fillStyle = '#0ea5e9';
            ctx.fill();
        }

        update() {
            // Movement
            this.x += this.vx;
            this.y += this.vy;

            // Bounce off edges
            if (this.x < 0 || this.x > width) this.vx *= -1;
            if (this.y < 0 || this.y > height) this.vy *= -1;

            // Mouse interaction
            let dx = mouse.x - this.x;
            let dy = mouse.y - this.y;
            let distance = Math.sqrt(dx*dx + dy*dy);
            if (distance < mouse.radius) {
                if (mouse.x < this.x && this.x < width - 10) this.x += 2;
                if (mouse.x > this.x && this.x > 10) this.x -= 2;
                if (mouse.y < this.y && this.y < height - 10) this.y += 2;
                if (mouse.y > this.y && this.y > 10) this.y -= 2;
            }

            this.draw();
        }
    }

    function initParticles() {
        particles = [];
        let numberOfParticles = (width * height) / 9000;
        for (let i = 0; i < numberOfParticles; i++) {
            particles.push(new Particle());
        }
    }

    function connect() {
        let opacityValue = 1;
        for (let a = 0; a < particles.length; a++) {
            for (let b = a; b < particles.length; b++) {
                let distance = ((particles[a].x - particles[b].x) * (particles[a].x - particles[b].x)) 
                             + ((particles[a].y - particles[b].y) * (particles[a].y - particles[b].y));
                if (distance < (width/7) * (height/7)) {
                    opacityValue = 1 - (distance / 20000);
                    ctx.strokeStyle = 'rgba(14, 165, 233,' + opacityValue + ')';
                    ctx.lineWidth = 1;
                    ctx.beginPath();
                    ctx.moveTo(particles[a].x, particles[a].y);
                    ctx.lineTo(particles[b].x, particles[b].y);
                    ctx.stroke();
                }
            }
        }
    }

    function animate() {
        requestAnimationFrame(animate);
        ctx.clearRect(0, 0, width, height);
        particles.fo