<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Find Your Next Destination</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <!-- Google Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Open+Sans:wght@700&display=swap" rel="stylesheet" />
  <style>
    /* 1. Global box-sizing for layout consistency */
    *, *::before, *::after {
      box-sizing: border-box;
    }
    html, body {
      height: 100%;
      margin: 0;
      padding: 0;
      overflow-x: hidden; /* Prevent horizontal scroll */
      font-family: 'Poppins', sans-serif;
      color: #222;
      background: linear-gradient(
        45deg,
        #ffffff 0%,
        #f0f0f0 20%,
        #e0e0e0 40%,
        #d0d0d0 60%,
        #c0c0c0 80%,
        #ffffff 100%
      );
      background-size: 300% 300%;
      background-position: 0% 50%;
      animation:
        bg-move-x 15s ease-in-out infinite alternate,
        bg-move-y 25s ease-in-out infinite alternate,
        bg-hue-rotate 30s linear infinite;
      display: flex;
      justify-content: center;
      align-items: center;
      text-align: center;
      min-height: 100vh;
    }
    @keyframes bg-move-x {
      0% { background-position: 0% 50%; }
      100% { background-position: 100% 50%; }
    }
    @keyframes bg-move-y {
      0% { background-position: 50% 0%; }
      100% { background-position: 50% 100%; }
    }
    @keyframes bg-hue-rotate {
      0% { filter: hue-rotate(0deg); }
      100% { filter: hue-rotate(360deg); }
    }
    /* 2. Main Content Container */
    .container {
      max-width: 900px;
      width: 100%;
      padding: 4rem 2rem;
      background: rgba(255,255,255,0.85);
      border-radius: 15px;
      box-shadow: 0 8px 30px rgba(0,0,0,0.1);
      backdrop-filter: blur(12px);
      animation: fadeInUp 1.5s ease forwards;
      transition: transform 0.3s ease;
      cursor: default;
      box-sizing: border-box;
    }
    .container:hover {
      transform: translateY(-10px);
      cursor: pointer;
    }
    .animated-gradient-text {
      font-family: 'Open Sans', sans-serif;
      font-weight: 700;
      font-size: clamp(2rem, 5vw, 4rem);
      letter-spacing: 0.04em;
      background: conic-gradient(
        from 0deg,
        red, orange, yellow, green, blue, indigo, violet, red
      );
      background-size: 200% 200%;
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      animation:
        rainbow-x 20s ease-in-out infinite alternate,
        rainbow-y 35s ease-in-out infinite alternate,
        rainbow-hue 40s linear infinite;
      user-select: none;
      backface-visibility: hidden;
      will-change: transform;
      margin: 0 0 1rem 0;
    }
    @keyframes rainbow-x {
      0% { background-position-x: 0%; }
      100% { background-position-x: 100%; }
    }
    @keyframes rainbow-y {
      0% { background-position-y: 0%; }
      100% { background-position-y: 100%; }
    }
    @keyframes rainbow-hue {
      0% { filter: hue-rotate(0deg); }
      100% { filter: hue-rotate(360deg); }
    }
    p.lead {
      font-size: clamp(1.1rem, 2vw, 1.4rem);
      margin-bottom: 3rem;
      max-width: 600px;
      color: #6c643c;
      line-height: 1.6;
      margin-left: auto;
      margin-right: auto;
    }
    .btn-primary {
      background: linear-gradient(90deg, #bf9a6d, #d9bf93);
      border: none;
      color: #5c4428;
      padding: 1.2rem 3rem;
      font-size: 1.2rem;
      border-radius: 50px;
      cursor: pointer;
      box-shadow: 0 8px 15px rgba(191, 154, 109, 0.5);
      transition: all 0.3s ease;
    }
    .btn-primary:hover {
      background: linear-gradient(90deg, #d9bf93, #bf9a6d);
      box-shadow: 0 12px 20px rgba(217, 191, 147, 0.7);
      transform: translateY(-3px);}
    .wave {
      position: fixed;
      bottom: 0;
      left: 0;
      width: 100%;
      height: 150px;
      background: url('https://svgshare.com/i/_U9.svg') no-repeat bottom center;
      background-size: cover;
      pointer-events: none;
      opacity: 0.3;
    }
    @keyframes fadeInUp {
      0% {
        opacity: 0;
        transform: translateY(30px);
      }
      100% {
        opacity: 1;
        transform: translateY(0);
      }
    }
    /* Responsive adjustments for mobile */
    @media (max-width: 600px) {
      .container {
        padding: 1rem 0.5rem;
        max-width: 98vw;
      }
    }
  </style>
</head>
<body>
  <main>
    <div class="container" id="content">
      <h1 class="animated-gradient-text">Find Your Next Destination</h1>
      <p class="lead">
        Connect with Infinity...
      </p>
      <button class="btn-primary" id="nextBtn" type="button">Explore Now</button>
    </div>
    <div class="wave" aria-hidden="true"></div>
  </main>
  <script>
    // XML Data
    const xmlData = 
      <page>
        <title>Find Your Next Destination</title>
        <description>Connect with Infinity...</description>
        <cta>
          <text>Explore Now</text>
          <link>nextpage.html</link>
        </cta>
      </page>;

    // Load content from XML
    function loadContentFromXML() {
      const parser = new DOMParser();
      const xmlDoc = parser.parseFromString(xmlData, "application/xml");
      const title = xmlDoc.querySelector('title').textContent;
      const desc = xmlDoc.querySelector('description').textContent;
      const ctaText = xmlDoc.querySelector('cta > text').textContent;
      const ctaLink = xmlDoc.querySelector('cta > link').textContent;

      document.querySelector('h1.animated-gradient-text').textContent = title;
      document.querySelector('.lead').textContent = desc;
      const btn = document.getElementById('nextBtn');
      btn.textContent = ctaText;
      btn.dataset.link = ctaLink;
    }

    // Initialize content
    loadContentFromXML();

    // Button click event
    document.getElementById('nextBtn').addEventListener('click', () => {
      const link = document.getElementById('nextBtn').dataset.link || 'nextpage.html';
      window.location.href = link;
    });
  </script>
</body>
</html>
