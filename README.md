
<html lang="en" >
<head>
  <meta charset="UTF-8" />
  <title>Feshr - Connect with Power... Connect With Infinity...</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <!-- Google Fonts: Merriweather for headings, Open Sans for body, Lora for footer and other text -->
  <link href="https://fonts.googleapis.com/css2?family=Lora&family=Merriweather:wght@700&family=Open+Sans&display=swap" rel="stylesheet" />
  <style>
    /* Reset */
    *, *::before, *::after {
      box-sizing: border-box;
    }
    body {
      margin: 0;
      font-family: 'Open Sans', sans-serif;
      background: linear-gradient(135deg, #fafafa 0%, #f5f7fa 100%);
      color: #1d1d1f;
      -webkit-font-smoothing: antialiased;
      -moz-osx-font-smoothing: grayscale;
      overflow-x: hidden;
      scroll-behavior: smooth;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
    }

    /* Header */
    header {
      position: fixed;
      top: 0; left: 0; right: 0;
      background: rgba(255 255 255 / 0.95);
      backdrop-filter: saturate(180%) blur(20px);
      border-bottom: 1px solid #ddd;
      box-shadow: 0 2px 8px rgba(0,0,0,0.05);
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 1rem 2rem;
      z-index: 10000;
    }
   .logo {
      font-family: 'Merriweather', serif;
      font-weight: 700;
      font-size: 1.2rem; /* or your preferred size */
      letter-spacing: 0.12em;
      user-select: none;
      cursor: default;
      background: linear-gradient(90deg, #005bb5, #0071e3, #0099e6);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      color: transparent;
      text-transform: uppercase;
      text-shadow: 0 2px 5px rgba(0,0,0,0.1);
      /* DO NOT include background-color, box-shadow, border-radius, or padding here */
    }

    .menu-toggle {
      width: 28px;
      height: 22px;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      cursor: pointer;
      z-index: 11000;
    }
    .menu-toggle div {
      height: 3.5px;
      background: #0071e3;
      border-radius: 2px;
      transition: all 0.4s ease;
    }
    .menu-toggle.active div:nth-child(1) {
      transform: rotate(45deg) translate(5px, 5px);
    }
    .menu-toggle.active div:nth-child(2) {
      opacity: 0;
    }
    .menu-toggle.active div:nth-child(3) {
      transform: rotate(-45deg) translate(5px, -5px);
    }

    /* Dropdown menu */
    nav.dropdown-menu {
      position: fixed;
      top: 60px;
      left: 0;
      width: 100%;
      background: rgba(255 255 255 / 0.98);
      box-shadow: 0 12px 40px rgba(0,0,0,0.12);
      display: none;
      flex-wrap: wrap;
      padding: 1rem 2rem;
      gap: 1rem;
      justify-content: center;
      z-index: 10500;
      border-radius: 0 0 18px 18px;
      backdrop-filter: saturate(180%) blur(20px);
    }
    nav.dropdown-menu.active {
      display: flex;
    }
    nav.dropdown-menu a {
      flex: 1 1 30%;
      text-align: center;
      padding: 0.75rem 0;
      font-weight: 700;
      font-size: 1.1rem;
      color: #0071e3;
      border-radius: 12px;
      text-decoration: none;
      user-select: none;
      transition: background-color 0.3s ease, color 0.3s ease;
      word-break: break-word;
    }
    nav.dropdown-menu a:hover,
    nav.dropdown-menu a:focus {
      background-color: #0071e3;
      color: white;
      outline: none;
      box-shadow: 0 4px 12px rgba(0,113,227,0.4);
    }

    /* Main padding */
    main {
      padding-top: 80px;
      max-width: 1100px;
      margin: 0 auto;
      padding-left: 1rem;
      padding-right: 1rem;
      flex-grow: 1;
    }

    .hero {
      position: relative;
      text-align: center;
      margin-bottom: 6rem;
      padding: 6rem 1rem 4rem;
      overflow: visible;
      color: #1d1d1f;
    }
    #hero-content h1 {
      font-family: 'Merriweather', serif;
      font-weight: 700;
      font-size: 1.2rem; /* Reduced section heading size */
      letter-spacing: 0.12em;
      background: linear-gradient(270deg, #005bb5, #0071e3, #0099e6);
      background-size: 300% 100%;
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      color: transparent;
      animation: colorShift 8s ease infinite alternate;
      margin-bottom: 0.5rem;
      line-height: 1.05;
      text-transform: uppercase;
      text-shadow: 0 2px 6px rgba(0,0,0,0.15);
      transition: background-position 8s ease;
    }
    #hero-content p {
      font-family: 'Lora', serif;
      font-size: 1rem;
      color: #4a4a4a;
      max-width: 400px;
      margin: 0 auto 2rem;
      font-weight: 400;
      
      letter-spacing: 0.03em;
      line-height: 1.6;
      /* Allow wrapping and prevent overflow */
      white-space: normal;
      overflow-wrap: break-word;
      word-break: break-word;
      max-width: 100%;
      min-height: 4.5em; /* reserve vertical space */
    }
   #hero-content button {
  background: linear-gradient(135deg, #005bb5, #0071e3);
  border: none;
  color: white;
  padding: 0.4rem 1.6rem;
  font-size: 0.85rem;
  font-weight: 700;
  border-radius: 16px;
  cursor: pointer;
  box-shadow: 0 4px 12px rgba(0, 113, 227, 0.3);
  transition: background 0.4s ease, box-shadow 0.4s ease, transform 0.3s ease;
  user-select: none;
  letter-spacing: 0.04em;
  font-family: 'Merriweather', serif;
  min-width: 130px;
  display: inline-block;
  text-align: center;
  /* Soft inner shadow for subtle depth */
  box-shadow:
    inset 0 -3px 6px rgba(255, 255, 255, 0.2),
    0 4px 12px rgba(0, 113, 227, 0.3);
}

#hero-content button:hover,
#hero-content button:focus {
  background: linear-gradient(135deg, #0071e3, #0099e6);
  box-shadow:
    inset 0 -3px 6px rgba(255, 255, 255, 0.3),
    0 6px 20px rgba(0, 113, 227, 0.5);
  transform: translateY(-3px) scale(1.05);
  outline: none;
}



    /* Features Image Grid with Overlay */
    .features {
      display: grid;
      grid-template-columns: repeat(auto-fit,minmax(320px,1fr));
      gap: 2.5rem;
      margin-bottom: 6rem;
    }
    .feature-image-card {
      position: relative;
      border-radius: 18px;
      overflow: hidden;
      box-shadow: 0 20px 40px rgba(0,0,0,0.07);
      cursor: pointer;
      transition: box-shadow 0.4s ease, transform 0.4s ease;
      outline-offset: 4px;
      background: #fff;
    }
    .feature-image-card:focus,
    .feature-image-card:hover {
      box-shadow: 0 32px 64px rgba(0,0,0,0.15);
      transform: translateY(-12px);
      outline: none;
    }
    .feature-image-card img {
      width: 100%;
      height: 220px;
      object-fit: cover;
      display: block;
      transition: transform 0.5s ease;
    }
    .feature-image-card:hover img,
    .feature-image-card:focus img {
      transform: scale(1.05);
    }
    .feature-image-card .overlay {
      position: absolute;
      bottom: 0;
      left: 0;
      right: 0;
      padding: 1.5rem 1.5rem 2rem;
      background: linear-gradient(180deg, transparent 0%, rgba(0, 113, 227, 0.85) 90%);
      color: white;
      opacity: 0;
      transition: opacity 0.4s ease;
      display: flex;
      flex-direction: column;
      justify-content: flex-end;
      height: 100%;
      border-radius: 0 0 18px 18px;
    }
    .feature-image-card:hover .overlay,
    .feature-image-card:focus .overlay {
      opacity: 1;
    }
    .feature-image-card h3 {
      margin: 0 0 0.5rem;
      font-family: 'Merriweather', serif;
      font-weight: 700;
      font-size: 1.6rem;
      line-height: 1.2;
    }
    .feature-image-card p {
      margin: 0;
      font-family: 'Lora', serif;
      font-size: 1rem;
      line-height: 1.4;
      font-weight: 400;
    }

    /* Wave Background */
    .wave {
      position: fixed;
      bottom: 0;
      left: 0;
      width: 100%;
      height: 160px;
      background: url('https://svgshare.com/i/_U9.svg') no-repeat bottom center;
      background-size: cover;
      pointer-events: none;
      opacity: 0.15;
      z-index: 0;
    }

    /* Footer: subtle, minimal, blending with background */
    footer {
      background: transparent;
      padding: 0.5rem 2rem;
      font-size: 0.65rem;
      color: #999999;
      font-family: 'Lora', serif;
      user-select: none;
      text-align: center;
      margin-top: auto;
      box-shadow: none;
    }
    footer .footer-container {
      max-width: 1100px;
      margin: 0 auto;
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 1rem;
    }
    footer nav {
      display: flex;
      flex-wrap: wrap;
      gap: 1rem;
    }
    footer nav a {
      color: #999999;
      text-decoration: none;
      font-weight: 400;
      transition: color 0.3s ease;
    }
    footer nav a:hover,
    footer nav a:focus {
      color: #0071e3;
      outline: none;
      text-decoration: underline;
    }
    footer p.copyright {
      flex-basis: 100%;
      margin-top: 0.5rem;
      color: #bbbbbb;
      font-weight: 400;
      letter-spacing: 0.02em;
    }

    /* Responsive */
    @media (max-width: 768px) {
      .features {
        grid-template-columns: 1fr 1fr;
      }
      footer .footer-container {
        flex-direction: column;
        align-items: center;
        gap: 0.5rem;
      }
      footer nav {
        justify-content: center;
      }
    }
    @media (max-width: 480px) {
      .features {
        grid-template-columns: 1fr;
      }
      
      header {
        padding: 1rem;
      }
    }

    /* Smooth gradient color shift for hero heading */
    @keyframes colorShift {
      0% {background-position:0% 50%;}
      50% {background-position:100% 50%;}
      100% {background-position:0% 50%;}
    }
  </style>
</head>
<body>

<header>
  <div class="logo" aria-label="Feshr Logo">Feshr</div>
  <div class="menu-toggle" id="menuToggle" aria-label="Toggle navigation menu" role="button" tabindex="0" aria-expanded="false" aria-controls="navMenu">
    <div></div><div></div><div></div>
  </div>
  <nav class="dropdown-menu" id="navMenu" aria-hidden="true">
    <a href="#home">Home</a>
    <a href="#about">About</a>
    <a href="#services">Services</a>
    <a href="#portfolio">Portfolio</a>
    <a href="#blog">Blog</a>
    <a href="#testimonials">Testimonials</a>
    <a href="#contact">Contact</a>
    <a href="#privacy">Privacy Policy</a>
    <a href="#terms">Terms of Service</a>
  </nav>
</header>

<main>
  <section class="hero" id="home" tabindex="0">
    <div id="hero-content">
      <h1>Creativity</h1>
      <p id="typing-text" aria-live="polite" aria-atomic="true"></p>
      <button id="exploreBtn" type="button" aria-label="Explore Now">See More...</button>
    </div>
  </section>

  <section class="features" aria-label="Features built by Feshr">
    <article class="feature-image-card" tabindex="0" aria-label="Web Design Feature">
      <img src="https://images.unsplash.com/photo-1504384308090-c894fdcc538d?auto=format&fit=crop&w=600&q=80" alt="Creative web design workspace" />
      <div class="overlay">
        <h3>Web Design</h3>
        <p>Creative, responsive, and user-centered designs that captivate your audience.</p>
      </div>
    </article>
    <article class="feature-image-card" tabindex="0" aria-label="Web Development Feature">
      <img src="https://images.unsplash.com/photo-1498050108023-c5249f4df085?auto=format&fit=crop&w=600&q=80" alt="Developers coding on laptops" />
      <div class="overlay">
        <h3>Web Development</h3>
        <p>Robust, scalable websites built with the latest technologies for optimal performance.</p>
      </div>
    </article>
  </section>
  <p>
    <section class="hero" id="home" tabindex="0">
    <div id="hero-content">
      <h1>Connect With Power</h1>
      <p>Much more to behold than grasp...</p>
      <button id="exploreBtn" type="button" aria-label="Explore Now">Now</button>
    </div>
  </section><p>
  <section class="features" aria-label="Features built by Feshr">
    <article class="feature-image-card" tabindex="0" aria-label="Web Design Feature">
      <img src="https://images.unsplash.com/photo-1504384308090-c894fdcc538d?auto=format&fit=crop&w=600&q=80" alt="Creative web design workspace" />
      <div class="overlay">
        <h3>Web Design</h3>
        <p>Creative, responsive, and user-centered designs that captivate your audience.</p>
      </div>
    </article>
    <article class="feature-image-card" tabindex="0" aria-label="Web Development Feature">
      <img src="https://images.unsplash.com/photo-1498050108023-c5249f4df085?auto=format&fit=crop&w=600&q=80" alt="Developers coding on laptops" />
      <div class="overlay">
        <h3>Web Development</h3>
        <p>Robust, scalable websites built with the latest technologies for optimal performance.</p>
      </div>
    </article></section>
 <p> 
  <section class="hero" id="home" tabindex="0">
    <div id="hero-content">
      <h1>Connect With Power</h1>
      <p>Much more to behold than grasp...</p>
      <button id="exploreBtn" type="button" aria-label="Explore Now">Now</button>
    </div>
  </section>

<div class="wave" aria-hidden="true"></div>

<footer>
  <div class="footer-container">
    <nav aria-label="Footer navigation">
      <a href="#home">Home</a>
      <a href="#about">About</a>
      <a href="#services">Services</a>
      <a href="#portfolio">Portfolio</a>
      <a href="#blog">Blog</a>
      <a href="#testimonials">Testimonials</a>
      <a href="#contact">Contact</a>
      <a href="#privacy">Privacy Policy</a>
      <a href="#terms">Terms of Service</a>
    </nav>
    <p class="copyright">&copy; 2025 Feshr. All rights reserved.</p>
  </div>
</footer>

<script>
  const menuToggle = document.getElementById('menuToggle');
  const navMenu = document.getElementById('navMenu');
  const exploreBtn = document.getElementById('exploreBtn');

  function toggleMenu() {
    const expanded = menuToggle.getAttribute('aria-expanded') === 'true';
    menuToggle.setAttribute('aria-expanded', String(!expanded));
    navMenu.classList.toggle('active');
    menuToggle.classList.toggle('active');
    navMenu.setAttribute('aria-hidden', String(expanded));
  }

  menuToggle.addEventListener('click', toggleMenu);
  menuToggle.addEventListener('keydown', e => {
    if (e.key === 'Enter' || e.key === ' ') {
      e.preventDefault();
      toggleMenu();
    }
  });

  document.addEventListener('click', e => {
    if (!navMenu.contains(e.target) && !menuToggle.contains(e.target) && navMenu.classList.contains('active')) {
      toggleMenu();
    }
  });

  exploreBtn.addEventListener('click', () => {
    document.querySelector('.features').scrollIntoView({ behavior: 'smooth' });
  });

  const typingText = document.getElementById('typing-text');

const textSets = [
  [
    "In a world where...\nEveryone needs to be creative...\nthe mind is the source of all power.",
    "In you is something powerful...",
    "As far as you can behold...\nwith the power of your mind, \nFar and beyond to grasp...",
    "as far as your eyes can see...",
    "For Creativity...",
    "Is As Far Your Eyes Can See!!!"
  ],
  [
    "Creativity flows like a river...",
    "The mind unlocks endless possibilities...",
    "Power lies within your imagination...",
    "Reach beyond horizons...",
    "See what others cannot see...",
    "And create the unseen."
  ],
  [
    "Every idea starts with a spark...",
    "The mind is the ultimate power source...",
    "Within you is infinite potential...",
    "Look beyond the obvious...",
    "Grasp the intangible...",
    "And make it real."
  ]
];

const lines = textSets[Math.floor(Math.random() * textSets.length)];

let lineIndex = 0;
let charIndex = 0;
let typingSpeed = 135;
let erasingSpeed = 60;
let delayBetweenLines = 1800;

function type() {
  if (charIndex < lines[lineIndex].length) {
    let currentChar = lines[lineIndex].charAt(charIndex);
    if (currentChar === '\n') {
      typingText.innerHTML += '<br>';
    } else {
      typingText.innerHTML += currentChar;
    }
    charIndex++;
    setTimeout(type, typingSpeed);
  } else {
    if (lineIndex === lines.length - 1) {
      return;
    }
    setTimeout(erase, delayBetweenLines);
  }
}

function erase() {
  if (charIndex > 0) {
    let currentText = typingText.innerHTML;
    if (currentText.endsWith('<br>')) {
      typingText.innerHTML = currentText.slice(0, -4);
    } else {
      typingText.innerHTML = currentText.slice(0, -1);
    }
    charIndex--;
    setTimeout(erase, erasingSpeed);
  } else {
    lineIndex++;
    setTimeout(type, typingSpeed);
  }
}

document.addEventListener('DOMContentLoaded', () => {
  setTimeout(type, 800);
});

</script>

