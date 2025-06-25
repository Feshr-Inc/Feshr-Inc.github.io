
<html lang="en" >
<head>
  <meta charset="UTF-8" />
  <title>Feshr Inc. - Connect with Power... Connect With Infinity...</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <!-- Google Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Montserrat:wght@900&family=Poppins:wght@400;600&family=Raleway:wght@400;600&display=swap" rel="stylesheet" />
  <style>
    /* Reset */
    *, *::before, *::after {
      box-sizing: border-box;
    }
    body {
      margin: 0;
      font-family: 'Poppins', sans-serif;
      background: linear-gradient(135deg, #fcfdfe 0%, #e9f3fb 100%);
      color: #1d1d1f;
      -webkit-font-smoothing: antialiased;
      -moz-osx-font-smoothing: grayscale;
      overflow-x: hidden;
      scroll-behavior: smooth;
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
      font-family: 'Playfair Display', serif;
      font-weight: 700;
      font-size: 2rem;
      letter-spacing: 0.1em;
      user-select: none;
      cursor: default;
      background: linear-gradient(90deg, #005bb5, #0071e3, #0099e6);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      color: transparent;
      text-shadow: 0 2px 5px rgba(0,0,0,0.1);
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
    }
    nav.dropdown-menu a:hover,
    nav.dropdown-menu a:focus {
      background-color: #0071e3;
      color: white;
      outline: none;
      box-shadow: 0 4px 12px rgba(0,113,227,0.4);
    }

    /* Main padding to avoid header overlap */
    main {
      padding-top: 80px;
      max-width: 1100px;
      margin: 0 auto;
      padding-left: 1rem;
      padding-right: 1rem;
    }

    /* Hero Section */
    .hero {
      position: relative;
      text-align: center;
      margin-bottom: 6rem;
      padding: 6rem 1rem 4rem;
      overflow: hidden;
      color: #1d1d1f;
    }
    /* Animated gradient background */
    .hero::before {
      content: "";
      position: absolute;top: -50%;
      left: -50%;
      width: 200%;
      height: 200%;
      background: linear-gradient(270deg, #005bb5, #0071e3, #0099e6, #005bb5);
      background-size: 800% 800%;
      animation: gradientShift 30s ease infinite;
      filter: blur(100px);
      opacity: 0.4;
      z-index: -1;
      border-radius: 50%;
    }

    /* Hero content animations */
    #hero-content * {
      opacity: 0;
      animation-fill-mode: forwards;
      animation-timing-function: ease-in-out;
    }
    #hero-content h1 {
      font-family: 'Montserrat', sans-serif;
      font-weight: 900;
      font-size: clamp(3rem, 8vw, 6rem);
      letter-spacing: -0.02em;
      background: linear-gradient(270deg, #005bb5, #0071e3, #0099e6);
      background-size: 300% 100%;
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      animation-name: fadeSlideIn;
      animation-duration: 800ms;
      animation-delay: 500ms;
      margin-bottom: 0.5rem;
      line-height: 1.05;
      text-transform: uppercase;
      text-shadow: 0 2px 4px rgba(0,0,0,0.15);
    }
    #hero-content p {
      font-family: 'Raleway', sans-serif;
      font-size: clamp(1rem, 2vw, 1.5rem);
      color: #4a4a4a;
      max-width: 400px;
      margin: 0 auto 2rem;
      font-weight: 600;
      font-style: italic;
      letter-spacing: 0.05em;
      animation-name: fadeSlideIn;
      animation-duration: 800ms;
      animation-delay: 900ms;
    }
    #hero-content button {
      background: linear-gradient(90deg, #0071e3, #0099e6);
      border: none;
      color: white;
      padding: 1.25rem 3.5rem;
      font-size: 1.25rem;
      font-weight: 700;
      border-radius: 9999px;
      cursor: pointer;
      box-shadow: 0 12px 30px rgba(0, 113, 227, 0.5);
      transition: all 0.3s ease;
      user-select: none;
      animation-name: fadeSlideIn;
      animation-duration: 800ms;
      animation-delay: 1300ms;
    }
    #hero-content button:hover,
    #hero-content button:focus {
      background: linear-gradient(90deg, #005bb5, #0071e3);
      box-shadow: 0 16px 40px rgba(0, 91, 181, 0.7);
      transform: translateY(-5px);
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
      font-family: 'Montserrat', sans-serif;
      font-weight: 700;
      font-size: 1.6rem;
      line-height: 1.2;
    }
    .feature-image-card p {
      margin: 0;
      font-size: 1rem;
      line-height: 1.4;
      font-weight: 500;
    }/* Wave Background */
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

    /* Footer */
    footer {
      background: #f5f5f7;
      border-top: 1px solid #d2d2d7;
      padding: 3rem 2rem;
      font-size: 0.9rem;
      color: #6e6e73;
      font-family: 'Poppins', sans-serif;
      user-select: none;
    }
    footer .footer-container {
      max-width: 1100px;
      margin: 0 auto;
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      gap: 2rem;
    }
    footer nav {
      display: flex;
      flex-wrap: wrap;
      gap: 1.5rem;
    }
    footer nav a {
      color: #6e6e73;
      text-decoration: none;
      transition: color 0.3s ease;
      font-weight: 600;
    }
    footer nav a:hover,
    footer nav a:focus {
      color: #0071e3;
      outline: none;
    }
    footer p.copyright {
      flex-basis: 100%;
      text-align: center;
      margin-top: 1rem;
      color: #a1a1a6;
    }

    /* Responsive */
    @media (max-width: 768px) {
      .features {
        grid-template-columns: 1fr 1fr;
      }
      footer .footer-container {
        flex-direction: column;
        align-items: center;
        gap: 1rem;
      }
      footer nav {
        justify-content: center;
      }
    }
    @media (max-width: 480px) {
      .features {
        grid-template-columns: 1fr;
      }
      #hero-content h1 {
        font-size: clamp(2rem, 10vw, 4rem);
      }
      #hero-content p {
        font-size: 1rem;
      }
      header {
        padding: 1rem;
      }
    }

    /* Animations */
    @keyframes gradientShift {
      0% {background-position:0% 50%;}
      50% {background-position:100% 50%;}
      100% {background-position:0% 50%;}
    }
    @keyframes fadeSlideIn {
      0% {
        opacity: 0;
        transform: translateY(20px);
      }
      100% {
        opacity: 1;
        transform: translateY(0);
      }
    }
  </style>
</head>
<body>

<header>
  <div class="logo" aria-label="Feshr Inc. Logo">Feshr Inc.</div>
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
      <h1>Innovate Beyond Limits</h1>
      <p>Crafting Digital Experiences That Inspire</p>
      <button id="exploreBtn" type="button" aria-label="Explore Now">Explore Now</button>
    </div>
  </section>

  <section class="features" aria-label="Features built by Feshr Inc.">
    <article class="feature-image-card" tabindex="0" aria-label="Web Design Feature">
      <img src="https://images.unsplash.com/photo-1504384308090-c894fdcc538d?auto=format&fit=crop&w=600&q=80" alt="Creative web design workspace" />
      <div class="overlay">
        <h3>Web Design</h3>
        <p>Creative, responsive, and user-centered designs that captivate your audience.</p>
      </div>
    </article>
    <article class="feature-image-card" tabindex="0" aria-label="Web Development Feature">
      <img src="https://images.unsplash.com/photo-1498050108023-c5249f4df085?auto=format&fit=crop&w=600&q=80" alt="Developers coding on laptops" /><div class="overlay">
        <h3>Web Development</h3>
        <p>Robust, scalable websites built with the latest technologies for optimal performance.</p>
      </div>
    </article>
    <article class="feature-image-card" tabindex="0" aria-label="SEO Optimization Feature">
      <img src="https://images.unsplash.com/photo-1519389950473-47ba0277781c?auto=format&fit=crop&w=600&q=80" alt="SEO analytics dashboard" />
      <div class="overlay">
        <h3>SEO Optimization</h3>
        <p>Boost your online visibility and drive organic traffic to your business.</p>
      </div>
    </article>
    <article class="feature-image-card" tabindex="0" aria-label="Maintenance & Support Feature">
      <img src="https://images.unsplash.com/photo-1522071820081-009f0129c71c?auto=format&fit=crop&w=600&q=80" alt="Technical support team at work" />
      <div class="overlay">
        <h3>Maintenance & Support</h3>
        <p>Reliable support and maintenance to keep your website secure and up-to-date.</p>
      </div>
    </article>
  </section>
</main>

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
    <p class="copyright">&copy; 2025 Feshr Inc. All rights reserved.</p>
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
</script>

</body>
</html>
