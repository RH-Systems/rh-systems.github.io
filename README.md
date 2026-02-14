<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>RH²-Systems</title>

<!-- Google Fonts -->
<link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&family=Source+Code+Pro:wght@400;700&display=swap" rel="stylesheet">

<style>
/* Reset & base */
* {margin:0; padding:0; box-sizing:border-box;}
body {font-family:'Roboto', sans-serif; background:#0d1117; color:#c9d1d9; scroll-behavior:smooth;}
a {text-decoration:none; color:inherit;}
ul {list-style:none;}

/* Navbar */
.navbar {position:fixed; top:0; width:100%; display:flex; justify-content:space-between; align-items:center; padding:20px 50px; background:rgba(22,27,34,0.9); z-index:100;}
.navbar .logo {font-size:1.8rem; color:#00f0ff; font-weight:bold;}
.navbar ul {display:flex; gap:20px;}
.navbar a {padding:8px 15px; transition:0.3s;}
.navbar a:hover {background:#00c0cc; color:#0d1117; border-radius:5px;}

/* Hero */
.hero {height:100vh; display:flex; flex-direction:column; justify-content:center; align-items:center; text-align:center; background:linear-gradient(135deg,#0f2027,#203a43,#2c5364); background-size:200% 200%; animation:gradientBG 15s ease infinite; color:#00f0ff;}
.hero h1 {font-size:3rem; margin-bottom:10px;}
.hero p {font-size:1.2rem; margin-bottom:20px;}
.btn {padding:10px 25px; margin:5px; border:none; border-radius:5px; background:#00f0ff; color:#0d1117; font-weight:bold; cursor:pointer; transition:0.3s;}
.btn:hover {transform:scale(1.05); background:#00c0cc;}
@keyframes gradientBG {0%{background-position:0% 50%;}50%{background-position:100% 50%;}100%{background-position:0% 50%;}}

/* Sections */
section {padding:100px 20px; min-height:80vh; display:flex; flex-direction:column; justify-content:center; align-items:center; text-align:center;}
h2 {font-size:2.5rem; margin-bottom:20px; color:#00f0ff;}
.fade-in {opacity:0; transform:translateY(50px); animation:fadeIn 1s forwards;}
@keyframes fadeIn {to{opacity:1; transform:translateY(0);}}

/* About */
.about p {margin:10px 0; line-height:1.5;}

/* Services */
.services, .portfolio {display:flex; flex-wrap:wrap; justify-content:center; gap:30px; margin-top:20px;}
.service, .project {width:250px; padding:20px; background:#161b22; border-radius:10px; transition:0.3s; cursor:pointer;}
.service:hover, .project:hover {transform:translateY(-10px); background:#0a1f2b;}
.service h3, .project h3 {margin-bottom:10px; color:#00f0ff;}

/* Portfolio overlay */
.project span {display:block; margin-top:10px; font-size:0.9rem; color:#c9d1d9;}

/* Contact */
.contact form {max-width:500px; width:100%; display:flex; flex-direction:column; gap:15px; margin-top:20px;}
.contact input, .contact textarea {padding:10px; border-radius:5px; border:none; background:#161b22; color:#c9d1d9; resize:none;}
.contact button {padding:10px; border:none; border-radius:5px; background:#00f0ff; color:#0d1117; cursor:pointer; font-weight:bold; transition:0.3s;}
.contact button:hover {transform:scale(1.05); background:#00c0cc;}

/* Footer */
footer {padding:30px; text-align:center; background:#0a0f14; margin-top:20px;}

/* Responsive */
@media(max-width:768px){.navbar ul{flex-direction:column; gap:10px;}.services,.portfolio{flex-direction:column; align-items:center;}}
</style>
</head>

<body>

<!-- Navbar -->
<nav class="navbar">
  <div class="logo">RH²-Systems</div>
  <ul>
    <li><a href="#home">Home</a></li>
    <li><a href="#about">About</a></li>
    <li><a href="#services">Services</a></li>
    <li><a href="#portfolio">Portfolio</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<!-- Hero -->
<section id="home" class="hero fade-in">
  <h1>RH²-Systems</h1>
  <p>Securing your digital world & building innovative tech solutions</p>
  <a href="#contact" class="btn">Contact Us</a>
  <a href="#services" class="btn">View Services</a>
</section>

<!-- About -->
<section id="about" class="about fade-in">
  <h2>About Us</h2>
  <p><strong>Raj Hridoy</strong> – Cybersecurity & Programming Expert. Ethical hacking, web development, and tech innovation.</p>
  <p><strong>Riyad Hasan</strong> – Cybersecurity & Tech Specialist. Pen testing, programming, and system security.</p>
</section>

<!-- Services -->
<section id="services" class="fade-in">
  <h2>Our Services</h2>
  <div class="services">
    <div class="service"><h3>Cybersecurity</h3><p>Security audits & consulting</p></div>
    <div class="service"><h3>Ethical Hacking</h3><p>Pen testing & vulnerability assessment</p></div>
    <div class="service"><h3>Web Development</h3><p>Custom websites and apps</p></div>
    <div class="service"><h3>Tech Solutions</h3><p>Custom software & system solutions</p></div>
  </div>
</section>

<!-- Portfolio -->
<section id="portfolio" class="fade-in">
  <h2>Portfolio</h2>
  <div class="portfolio">
    <div class="project"><h3>Project 1</h3><span>Website Design</span></div>
    <div class="project"><h3>Project 2</h3><span>Security Audit</span></div>
    <div class="project"><h3>Project 3</h3><span>Custom App</span></div>
  </div>
</section>

<!-- Contact -->
<section id="contact" class="fade-in">
  <h2>Contact Us</h2>
  <p>Raj Hridoy: rajhridoy100az@gmail.com</p>
  <p>Riyad Hasan: reyadhasan100az@gmail.com</p>
  <form action="https://formspree.io/f/yourFormID" method="POST">
    <input type="text" name="name" placeholder="Your Name" required>
    <input type="email" name="email" placeholder="Your Email" required>
    <textarea name="message" placeholder="Your Message" required></textarea>
    <button type="submit" class="btn">Send Message</button>
  </form>
</section>

<!-- Footer -->
<footer>
  &copy; 2026 RH²-Systems
</footer>

<!-- JS -->
<script>
// Fade-in sections
const faders = document.querySelectorAll('.fade-in');
const appearOptions = {threshold:0.1, rootMargin:"0px"};
const appearOnScroll = new IntersectionObserver(function(entries, observer){
  entries.forEach(entry => {
    if(!entry.isIntersecting) return;
    entry.target.style.opacity=1;
    entry.target.style.transform='translateY(0)';
    observer.unobserve(entry.target);
  });
}, appearOptions);
faders.forEach(fader => appearOnScroll.observe(fader));
</script>
</body>
</html>