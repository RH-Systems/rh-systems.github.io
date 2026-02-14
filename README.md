<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>RH²-Systems</title>
<meta name="description" content="RH²-Systems: Cybersecurity, Programming & Tech Solutions by Raj Hridoy & Riyad Hasan">
<link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
<style>
  /* Reset & Base */
  * { margin:0; padding:0; box-sizing:border-box; font-family: 'Roboto', sans-serif; }
  body { background: #0d1117; color: #c9d1d9; scroll-behavior: smooth; }
  a { color: inherit; text-decoration: none; }
  section { padding: 80px 20px; }
  h1,h2,h3 { margin-bottom: 20px; }
  
  /* Hero */
  .hero { display:flex; flex-direction:column; justify-content:center; align-items:center; height:100vh; text-align:center; background: linear-gradient(135deg,#0f2027,#203a43,#2c5364); animation: gradientBG 10s ease infinite; color: #00f0ff; }
  .hero h1 { font-size:3rem; margin-bottom:10px; }
  .hero p { font-size:1.2rem; margin-bottom:20px; }
  .hero button { padding:10px 25px; margin:5px; border:none; cursor:pointer; background:#00f0ff; color:#0d1117; font-weight:bold; border-radius:5px; transition: 0.3s; }
  .hero button:hover { transform: scale(1.1); background:#00c0cc; }

  @keyframes gradientBG {
    0% { background-position:0% 50%; }
    50% { background-position:100% 50%; }
    100% { background-position:0% 50%; }
  }

  /* About */
  .about { display:flex; flex-wrap:wrap; justify-content:center; gap:40px; text-align:center; }
  .person { width:250px; padding:20px; background:#161b22; border-radius:10px; transition:0.5s; opacity:0; transform:translateY(50px); animation: fadeIn 1s forwards; }
  .person:nth-child(1){ animation-delay:0.2s; }
  .person:nth-child(2){ animation-delay:0.4s; }
  @keyframes fadeIn { to { opacity:1; transform:translateY(0); } }
  .person img { width:150px; border-radius:50%; margin-bottom:15px; }

  /* Services */
  .services { display:flex; flex-wrap:wrap; justify-content:center; gap:30px; text-align:center; }
  .service { width:220px; padding:20px; background:#161b22; border-radius:10px; transition:0.3s; }
  .service:hover { transform: translateY(-10px); background:#0a1f2b; }
  .service h3 { margin-bottom:10px; color:#00f0ff; }

  /* Portfolio */
  .portfolio { display:flex; flex-wrap:wrap; justify-content:center; gap:30px; }
  .project { width:250px; height:150px; background:#161b22; border-radius:10px; position:relative; overflow:hidden; cursor:pointer; transition:0.3s; }
  .project:hover { transform:scale(1.05); }
  .project span { position:absolute; bottom:0; left:0; width:100%; background:rgba(0,0,0,0.8); color:#00f0ff; text-align:center; padding:10px; transform:translateY(100%); transition:0.3s; }
  .project:hover span { transform:translateY(0); }

  /* Contact */
  .contact form { max-width:500px; margin:auto; display:flex; flex-direction:column; gap:15px; }
  .contact input, .contact textarea { padding:10px; border-radius:5px; border:none; background:#161b22; color:#c9d1d9; resize:none; }
  .contact button { padding:10px; border:none; border-radius:5px; background:#00f0ff; color:#0d1117; cursor:pointer; font-weight:bold; transition:0.3s; }
  .contact button:hover { transform:scale(1.05); background:#00c0cc; }

  /* Footer */
  footer { padding:30px; text-align:center; background:#0a0f14; }
  footer a { margin:0 10px; color:#00f0ff; }
  
  /* Responsive */
  @media(max-width:768px){ .about,.services,.portfolio{ flex-direction:column; align-items:center; } }
</style>
</head>
<body>

<!-- Hero -->
<section class="hero">
  <h1>RH²-Systems</h1>
  <p>Securing your digital world & building innovative tech solutions</p>
  <div>
    <button onclick="document.getElementById('contact').scrollIntoView({behavior:'smooth'})">Contact Us</button>
    <button onclick="document.getElementById('services').scrollIntoView({behavior:'smooth'})">View Services</button>
  </div>
</section>

<!-- About -->
<section class="about">
  <div class="person">
    <img src="https://via.placeholder.com/150" alt="Raj Hridoy">
    <h3>Raj Hridoy</h3>
    <p>Cybersecurity & Programming Expert. Ethical hacking, web development, and tech innovation.</p>
  </div>
  <div class="person">
    <img src="https://via.placeholder.com/150" alt="Riyad Hasan">
    <h3>Riyad Hasan</h3>
    <p>Cybersecurity & Tech Specialist. Programming, penetration testing, and system security.</p>
  </div>
</section>

<!-- Services -->
<section id="services" class="services">
  <div class="service"><h3>Cybersecurity Audits</h3><p>Comprehensive security analysis to protect your systems.</p></div>
  <div class="service"><h3>Pen Testing</h3><p>Ethical hacking to identify vulnerabilities before attackers do.</p></div>
  <div class="service"><h3>Web Development</h3><p>High-end websites and applications tailored to your needs.</p></div>
  <div class="service"><h3>Custom Tech Solutions</h3><p>Innovative software & tools to improve your workflow and security.</p></div>
</section>

<!-- Portfolio -->
<section class="portfolio">
  <div class="project"><span>Project 1: Web App</span></div>
  <div class="project"><span>Project 2: Security Audit</span></div>
  <div class="project"><span>Project 3: Custom Software</span></div>
</section>

<!-- Contact -->
<section id="contact" class="contact">
  <h2>Contact</h2>
  <p>Raj Hridoy: <a href="mailto:rajhridoy100az@gmail.com">rajhridoy100az@gmail.com</a></p>
  <p>Riyad Hasan: <a href="mailto:reyadhasan100az@gmail.com">reyadhasan100az@gmail.com</a></p>
  <form>
    <input type="text" placeholder="Your Name" required>
    <input type="email" placeholder="Your Email" required>
    <textarea rows="5" placeholder="Your Message" required></textarea>
    <button type="submit">Send Message</button>
  </form>
</section>

<!-- Footer -->
<footer>
  &copy; 2026 RH²-Systems | <a href="#services">Services</a> <a href="#contact">Contact</a> <a href="#about">About</a>
</footer>

</body>
</html>