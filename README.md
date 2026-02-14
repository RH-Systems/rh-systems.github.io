<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>RH²-Systems</title>
<style>
/* Basic Reset & Body */
body { margin:0; font-family:'Roboto',sans-serif; background:#0d1117; color:#c9d1d9; scroll-behavior:smooth;}
section {padding:80px 20px; min-height:100vh; display:flex; flex-direction:column; justify-content:center; align-items:center; text-align:center;}
.navbar {position:fixed; top:0; width:100%; display:flex; justify-content:space-between; padding:20px; background:#161b22; z-index:100;}
.navbar a {color:#00f0ff; margin:0 10px; text-decoration:none; transition:0.3s;}
.navbar a:hover {color:#0d1117; background:#00c0cc; border-radius:5px; padding:5px 10px;}
.hero {background:linear-gradient(135deg,#0f2027,#203a43,#2c5364); width:100%; color:#00f0ff; }
.hero h1{font-size:3rem;}
.btn {padding:10px 25px; margin:5px; border:none; border-radius:5px; background:#00f0ff; color:#0d1117; font-weight:bold; cursor:pointer; transition:0.3s;}
.btn:hover{transform:scale(1.05); background:#00c0cc;}
.fade-in{opacity:0; transform:translateY(50px); animation:fadeIn 1s forwards;}
@keyframes fadeIn{to{opacity:1; transform:translateY(0);}}
.services,.portfolio{display:flex; flex-wrap:wrap; justify-content:center; gap:30px;}
.service,.project{width:220px; padding:20px; background:#161b22; border-radius:10px; transition:0.3s;}
.service:hover,.project:hover{transform:translateY(-10px); background:#0a1f2b;}
.project span{display:block; margin-top:10px;}
footer{padding:30px; text-align:center; background:#0a0f14; margin-top:20px;}
</style>
</head>
<body>

<!-- Navbar -->
<nav class="navbar">
  <div class="logo">RH²-Systems</div>
  <div>
    <a href="#home">Home</a>
    <a href="#about">About</a>
    <a href="#services">Services</a>
    <a href="#portfolio">Portfolio</a>
    <a href="#contact">Contact</a>
  </div>
</nav>

<!-- Hero Section -->
<section id="home" class="hero fade-in">
  <h1>RH²-Systems</h1>
  <p>Securing your digital world & building innovative tech solutions</p>
  <a href="#contact" class="btn">Contact Us</a>
  <a href="#services" class="btn">View Services</a>
</section>

<!-- About Section -->
<section id="about" class="fade-in">
  <h2>About Us</h2>
  <p><strong>Raj Hridoy</strong> - Cybersecurity & Programming Expert</p>
  <p><strong>Riyad Hasan</strong> - Tech & Ethical Hacking Specialist</p>
</section>

<!-- Services Section -->
<section id="services" class="fade-in">
  <h2>Our Services</h2>
  <div class="services">
    <div class="service"><h3>Cybersecurity</h3><p>Security audits & consulting</p></div>
    <div class="service"><h3>Ethical Hacking</h3><p>Pen testing & vulnerability checks</p></div>
    <div class="service"><h3>Web Development</h3><p>Custom websites & apps</p></div>
    <div class="service"><h3>Tech Solutions</h3><p>Custom software & tools</p></div>
  </div>
</section>

<!-- Portfolio Section -->
<section id="portfolio" class="fade-in">
  <h2>Portfolio</h2>
  <div class="portfolio">
    <div class="project"><h3>Project 1</h3><span>Website Design</span></div>
    <div class="project"><h3>Project 2</h3><span>Security Audit</span></div>
    <div class="project"><h3>Project 3</h3><span>Custom App</span></div>
  </div>
</section>

<!-- Contact Section -->
<section id="contact" class="fade-in">
  <h2>Contact Us</h2>
  <p>Raj Hridoy: rajhridoy100az@gmail.com</p>
  <p>Riyad Hasan: reyadhasan100az@gmail.com</p>
  <form action="https://formspree.io/f/yourFormID" method="POST">
    <input type="text" name="name" placeholder="Your Name" required><br><br>
    <input type="email" name="email" placeholder="Your Email" required><br><br>
    <textarea name="message" placeholder="Your Message" required></textarea><br><br>
    <button type="submit" class="btn">Send Message</button>
  </form>
</section>

<!-- Footer -->
<footer>
  &copy; 2026 RH²-Systems
</footer>

<script>
// Fade-in effect
const faders = document.querySelectorAll('.fade-in');
const appearOptions = {threshold:0.1, rootMargin:"0px"};
const appearOnScroll = new IntersectionObserver(function(entries, observer){
  entries.forEach(entry=>{
    if(!entry.isIntersecting) return;
    entry.target.style.opacity=1;
    entry.target.style.transform='translateY(0)';
    observer.unobserve(entry.target);
  });
}, appearOptions);
faders.forEach(fader=>appearOnScroll.observe(fader));
</script>
</body>
</html>