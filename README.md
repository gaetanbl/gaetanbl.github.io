<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  
  <!-- SEO Meta Tags -->
  <title>Gaëtan Baylou--Lanot — Mechanical, Control &amp; AI Portfolio</title>
  <meta name="description" content="Portfolio of Gaëtan Baylou-Lanot, Mechanical, Control & AI Engineering student at INSA Rennes." />
  
  <!-- Open Graph / Social Media -->
  <meta property="og:title" content="Gaëtan Baylou-Lanot — Portfolio" />
  <meta property="og:description" content="Mechanical, Control & AI Engineering projects." />
  <meta property="og:type" content="website" />

  <!-- Fonts & Icons -->
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=DM+Serif+Display:ital@0;1&display=swap" rel="stylesheet" />
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css" />

  <style>
    :root {
      --bg-dark: #f8f6f1;          /* Premium Warm Cream/Beige Background */
      --bg-panel: #fcfbfa;         /* Clean Off-White for Sidebar and Panels */
      --bg-panel-hover: #f1ede4;   /* Soft warm hover state */
      --accent: #ff5d38;           /* Tech Sunset Orange */
      --accent-rgb: 255, 93, 56;
      --text-main: #1c1917;        /* Deep warm stone charcoal */
      --text-muted: #6b6661;       /* Elegant stone/taupe muted gray */
      --border-color: rgba(27, 25, 23, 0.08); /* Sophisticated subtle border */
      --font-serif: 'DM Serif Display', serif;
      --font-sans: 'Space Grotesk', sans-serif;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      background-color: var(--bg-dark);
      color: var(--text-main);
      font-family: var(--font-sans);
      -webkit-font-smoothing: antialiased;
      overflow-x: hidden;
    }

    /* Ambient soft warm background glow */
    body::before {
      content: '';
      position: fixed;
      top: -20%;
      right: -10%;
      width: 60vw;
      height: 60vw;
      background: radial-gradient(circle, rgba(255, 93, 56, 0.06) 0%, transparent 70%);
      z-index: 0;
      pointer-events: none;
    }

    /* Anchor Offset for Smooth Scroll on Mobile */
    section, .project-article {
      scroll-margin-top: 80px;
    }

    /* LEFT SIDEBAR (Desktop) */
    .sidebar {
      width: 290px;
      background-color: var(--bg-panel);
      border-right: 1px solid var(--border-color);
      height: 100vh;
      position: fixed;
      top: 0;
      left: 0;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      padding: 2.5rem 1.5rem 1.5rem 1.5rem;
      z-index: 100;
      transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    }

    .profile {
      text-align: left;
      margin-bottom: 1rem;
    }

    .profile-avatar {
      width: 90px;
      height: 90px;
      border-radius: 50%;
      object-fit: cover;
      display: block;
      margin: 0 auto 15px auto;
      border: 3px solid rgba(255, 255, 255, 0.8);
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.15);
      transition: transform 0.3s ease;
    }
    
    .profile-avatar:hover {
      transform: scale(1.05);
    }

    .profile h2 {
      font-family: var(--font-serif);
      font-size: 1.35rem;
      font-weight: 400;
      line-height: 1.2;
      margin-bottom: 0.3rem;
      color: var(--text-main);
    }

    .profile h2 em {
      font-family: var(--font-serif);
      color: var(--accent);
      font-style: italic;
    }

    .profile p {
      font-size: 0.8rem;
      color: var(--text-muted);
      font-weight: 400;
      line-height: 1.3;
    }

    /* Sidebar Navigation Links */
    .nav-links {
      list-style: none;
      display: flex;
      flex-direction: column;
      gap: 0.2rem;
      overflow-y: auto;
      max-height: calc(100vh - 280px);
      padding-right: 5px;
    }

    .nav-links::-webkit-scrollbar {
      width: 3px;
    }
    .nav-links::-webkit-scrollbar-thumb {
      background: rgba(0, 0, 0, 0.05);
      border-radius: 10px;
    }

    .nav-category-title {
      font-size: 0.72rem;
      text-transform: uppercase;
      letter-spacing: 0.12em;
      color: var(--text-muted);
      font-weight: 700;
      padding: 0.8rem 0.6rem 0.3rem 0.6rem;
      pointer-events: none;
      user-select: none;
      opacity: 0.85;
    }

    .nav-links a {
      text-decoration: none;
      color: var(--text-muted);
      font-weight: 500;
      font-size: 0.85rem;
      display: flex;
      align-items: center;
      gap: 10px;
      padding: 0.5rem 0.6rem;
      border-radius: 8px;
      transition: all 0.25s cubic-bezier(0.4, 0, 0.2, 1);
      border-left: 3px solid transparent;
    }

    .nav-links li.sub-item {
      margin-left: 0.5rem;
    }

    .nav-links li.sub-item a {
      font-size: 0.78rem;
      padding: 0.35rem 0.6rem;
      opacity: 0.9;
    }

    .nav-links a i, .nav-links a span.dot-bullet {
      font-size: 0.9rem;
      transition: transform 0.2s;
      width: 14px;
      text-align: center;
    }

    .nav-links a span.dot-bullet {
      display: inline-block;
      width: 6px;
      height: 6px;
      border-radius: 50%;
      background: var(--text-muted);
      margin-left: 4px;
      margin-right: 4px;
    }

    .nav-links a:hover, .nav-links li.active a {
      color: var(--text-main);
      background-color: var(--bg-panel-hover);
      border-left: 3px solid var(--accent);
      opacity: 1;
    }

    .nav-links li.active a span.dot-bullet {
      background: var(--accent);
      box-shadow: 0 0 8px var(--accent);
    }

    .nav-links a:hover i {
      transform: translateX(2px);
    }

    /* Sidebar Footer & Contact */
    .sidebar-footer {
      border-top: 1px solid var(--border-color);
      padding-top: 1rem;
    }

    .discreet-contact-container {
      display: flex;
      flex-direction: column;
      gap: 0.4rem;
    }

    .discreet-contact-container .eyebrow {
      margin-bottom: 0.2rem !important;
    }

    .contact-row-minimal {
      display: flex;
      flex-direction: column;
      gap: 0.4rem;
    }

    .contact-item-discreet {
      display: flex;
      align-items: center;
      gap: 8px;
      text-decoration: none;
      color: var(--text-muted);
      font-size: 0.7rem; 
      line-height: 1.3;
      transition: color 0.2s;
    }

    .contact-item-discreet:hover {
      color: var(--accent);
    }

    .contact-item-discreet i {
      color: var(--accent);
      font-size: 0.8rem;
      width: 12px;
      text-align: center;
    }

    /* Animation Highlight */
    @keyframes pulseHighlight {
      0% {
        box-shadow: 0 0 0 0 rgba(255, 93, 56, 0);
        background-color: transparent;
      }
      15% {
        box-shadow: 0 0 0 12px rgba(255, 93, 56, 0.15);
        background-color: rgba(255, 93, 56, 0.08);
        border-radius: 12px;
        transform: translateY(-2px);
      }
      30% {
        box-shadow: 0 0 0 16px rgba(255, 93, 56, 0.2);
        background-color: rgba(255, 93, 56, 0.12);
        border-radius: 12px;
        transform: translateY(-3px);
      }
      45% {
        transform: translateY(1px);
      }
      60% {
        box-shadow: 0 0 0 8px rgba(255, 93, 56, 0.08);
        background-color: rgba(255, 93, 56, 0.06);
        border-radius: 12px;
        transform: translateY(-1px);
      }
      100% {
        box-shadow: 0 0 0 0 rgba(255, 93, 56, 0);
        background-color: transparent;
        transform: translateY(0);
      }
    }

    .flash-highlight {
      animation: pulseHighlight 2s cubic-bezier(0.25, 1, 0.5, 1);
    }

    .mobile-header {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 70px;
      background: rgba(248, 246, 241, 0.9);
      backdrop-filter: blur(12px);
      -webkit-backdrop-filter: blur(12px);
      border-bottom: 1px solid var(--border-color);
      z-index: 99;
      justify-content: space-between;
      align-items: center;
      padding: 0 1.5rem;
    }

    .mobile-logo {
      font-family: var(--font-serif);
      font-size: 1.5rem;
      color: var(--text-main);
    }

    .mobile-logo em {
      color: var(--accent);
    }

    .hamburger {
      background: none;
      border: none;
      color: var(--text-main);
      font-size: 1.5rem;
      cursor: pointer;
    }

    .content-wrapper {
      margin-left: 290px;
      padding: 4rem 3.5rem; 
      max-width: 100%;     
      position: relative;
      z-index: 1;
    }

    section {
      padding: 4.5rem 0;
      border-bottom: 1px solid var(--border-color);
    }

    section:last-of-type {
      border-bottom: none;
    }

    .eyebrow {
      display: inline-block;
      font-family: var(--font-sans);
      font-size: 0.8rem;
      font-weight: 600;
      text-transform: uppercase;
      letter-spacing: 0.15em;
      color: var(--accent);
      margin-bottom: 1.5rem;
    }

    h1.hero-title {
      font-family: var(--font-serif);
      font-size: 4.5rem;
      font-weight: 400;
      line-height: 1.1;
      margin-bottom: 1.5rem;
      letter-spacing: -0.02em;
      color: var(--text-main);
    }

    h1.hero-title em {
      font-style: italic;
      color: var(--accent);
    }

    h1.hero-title .dot {
      color: var(--accent);
    }

    .hero-sub {
      font-size: 1.2rem;
      color: var(--text-muted);
      line-height: 1.6;
      max-width: 720px;
      margin-bottom: 2.5rem;
    }

    h2.section-title {
      font-family: var(--font-serif);
      font-size: 2.6rem;
      font-weight: 400;
      margin-bottom: 2.5rem;
      letter-spacing: -0.01em;
      color: var(--text-main);
    }

    h2.section-title em {
      font-style: italic;
      color: var(--accent);
    }

    p.paragraph {
      font-size: 1.05rem;
      color: var(--text-muted);
      line-height: 1.7;
      margin-bottom: 1.5rem;
    }

    .btn-container {
      display: flex;
      flex-wrap: wrap;
      gap: 1rem;
      margin-bottom: 2rem;
      align-items: center;
    }

    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      padding: 0.9rem 1.8rem;
      font-family: var(--font-sans);
      font-size: 0.95rem;
      font-weight: 600;
      text-decoration: none;
      border-radius: 9999px;
      transition: all 0.25s cubic-bezier(0.4, 0, 0.2, 1);
      gap: 10px;
    }

    .btn-primary {
      background-color: var(--text-main);
      color: var(--bg-dark);
      box-shadow: 0 4px 15px rgba(0,0,0,0.05);
    }

    .btn-primary:hover {
      background-color: var(--accent);
      color: #fff;
      transform: translateY(-2px);
      box-shadow: 0 8px 20px rgba(255, 93, 56, 0.25);
    }

    .btn-secondary {
      background-color: transparent;
      color: var(--text-main);
      border: 1.5px solid var(--text-main);
    }

    .btn-secondary:hover {
      background-color: rgba(28, 25, 23, 0.03);
      transform: translateY(-2px);
    }

    .btn-accent {
      background-color: rgba(255, 93, 56, 0.1);
      color: var(--accent);
      border: 1px solid rgba(255, 93, 56, 0.15);
    }

    .btn-accent:hover {
      background-color: rgba(255, 93, 56, 0.15);
      transform: translateY(-2px);
    }

    blockquote.prompt-info {
      border-left: 4px solid var(--accent);
      padding: 1.2rem 1.5rem;
      background-color: rgba(255, 93, 56, 0.05);
      color: var(--text-main);
      border-radius: 0 12px 12px 0;
      font-size: 1rem;
      margin-top: 2rem;
      display: flex;
      align-items: center;
      gap: 12px;
      max-width: 600px;
    }

    .projects-stack {
      display: flex;
      flex-direction: column;
      gap: 4.5rem;
    }

    .project-article {
      background-color: transparent; 
      border-bottom: 1px solid var(--border-color);
      padding-bottom: 4.5rem;
      transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
      position: relative;
    }

    .project-article:last-of-type {
      border-bottom: none;
      padding-bottom: 0;
    }

    .proj-meta-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 1.2rem;
    }

    .tag-container {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
    }

    .tag {
      background: rgba(0, 0, 0, 0.03);
      color: var(--text-muted);
      padding: 0.3rem 0.8rem;
      border-radius: 8px;
      font-size: 0.75rem;
      font-weight: 600;
      border: 1px solid var(--border-color);
    }

    .proj-year {
      font-size: 0.85rem;
      color: var(--text-muted);
      font-weight: 500;
    }

    .project-article h3 {
      font-family: var(--font-sans);
      font-size: 1.75rem;
      font-weight: 600;
      margin-bottom: 1.2rem;
      line-height: 1.3;
      color: var(--text-main);
    }

    .project-article p {
      font-size: 1.05rem;
      color: var(--text-muted);
      line-height: 1.7;
      margin-bottom: 1.8rem;
    }

    .project-img {
      width: 100%;
      max-height: 440px;
      object-fit: cover;
      border-radius: 16px;
      margin-top: 1.5rem;
      border: 1px solid var(--border-color);
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05);
    }

    /* Side-by-side Media Row Layout */
    .media-row {
      display: flex;
      gap: 15px;
      margin-top: 15px;
      width: 100%;
    }
    .media-row .project-img,
    .media-row .project-video {
      flex: 1;
      width: 50%;
      height: auto;
      object-fit: cover;
      border-radius: 8px;
    }

    figure.media-item {
      margin: 0;
      display: flex;
      flex-direction: column;
      gap: 8px;
      flex: 1;
      min-width: 0;
    }

    figure.media-item .project-img,
    figure.media-item .project-video {
      width: 100%;
      height: auto;
      object-fit: cover;
    }

    figcaption.caption {
      font-size: 0.85rem;
      color: var(--text-muted);
      text-align: center;
      font-style: italic;
      line-height: 1.4;
    }

    footer {
      padding: 3rem 0 1.5rem 0;
      margin-top: 3rem;
      border-top: 1px solid var(--border-color);
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    /* Media Queries */
    @media (max-width: 992px) {
      .sidebar {
        transform: translateX(-100%);
      }
      
      body.nav-open .sidebar {
        transform: translateX(0);
        box-shadow: 20px 0 40px rgba(0, 0, 0, 0.1);
      }

      .mobile-header {
        display: flex;
      }

      .content-wrapper {
        margin-left: 0;
        padding: 6rem 2rem 2rem 2rem;
      }

      h1.hero-title {
        font-size: 3.2rem;
      }

      .project-article {
        padding-bottom: 3.5rem;
      }
    }

    @media (max-width: 768px) {
      .media-row {
        flex-direction: column;
      }
      .media-row .project-img,
      .media-row .project-video {
        width: 100%;
      }
    }

    @media (max-width: 576px) {
      h1.hero-title {
        font-size: 2.6rem;
      }

      .btn-container {
        flex-direction: column;
      }

      .btn {
        width: 100%;
      }

      .contact-row-minimal {
        flex-direction: column;
        gap: 1rem;
      }

      footer {
        flex-direction: column;
        gap: 1rem;
        text-align: center;
      }
    }
  </style>
</head>
<body>

  <!-- ── MOBILE HEADER ── -->
  <header class="mobile-header">
    <div class="mobile-logo">G<em>B</em>.</div>
    <button class="hamburger" aria-label="Toggle navigation menu" onclick="toggleNav()">
      <i class="fa-solid fa-bars" id="hamburger-icon"></i>
    </button>
  </header>

  <!-- ── LEFT SIDEBAR ── -->
  <aside class="sidebar">
    <div class="sidebar-top">
      <div class="profile">
        <img src="https://raw.githubusercontent.com/gaetanbl/gaetanbl.github.io/833fa949a7780289bcf8465770c654755098b111/ma%20tete.png" alt="Photo de Gaëtan" class="profile-avatar">
        <h2>Gaëtan <em>Baylou-Lanot</em></h2>
        <p>Robotic - AI - physics</p>
      </div>
      <nav aria-label="Main Navigation">
        <ul class="nav-links">
          <li class="active"><a href="#introduction" onclick="closeNav()"><i class="fa-solid fa-user"></i> Introduction</a></li>
          <li><a href="#gma-internships" onclick="closeNav()"><i class="fa-solid fa-graduation-cap"></i> GMA Internships</a></li>
          
          <li class="nav-category-title">My projects:</li>
          
          <li class="sub-item"><a href="#ins-aerien" onclick="closeNav()"><span class="dot-bullet"></span> INS'Aérien Club</a></li>
          <li class="sub-item"><a href="#code-project-1" onclick="closeNav()"><span class="dot-bullet"></span> Robotics Cup C++</a></li>
          <li class="sub-item"><a href="#code-project-2" onclick="closeNav()"><span class="dot-bullet"></span> ROS2 Autonomous</a></li>
          <li class="sub-item"><a href="#ia-project-1" onclick="closeNav()"><span class="dot-bullet"></span> Supervised Vision</a></li>
          <li class="sub-item"><a href="#ia-project-2" onclick="closeNav()"><span class="dot-bullet"></span> Duckiebot RL</a></li>
          
          <li style="margin-top: 0.5rem;"><a href="#van-conversion" onclick="closeNav()"><i class="fa-solid fa-mountain-sun"></i> Personality</a></li>
        </ul>
      </nav>
    </div>
    
    <!-- Sidebar Footer -->
    <div class="sidebar-footer">
      <div class="discreet-contact-container" id="contact-minimal">
        <span class="eyebrow" style="margin-bottom: 0.2rem; font-size: 0.65rem; letter-spacing: 0.1em;">Get in Touch</span>
        <div class="contact-row-minimal">
          <a href="mailto:Gaetan.baylou--lanot@insa-rennes.fr" class="contact-item-discreet">
            <i class="fa-regular fa-envelope"></i>
            <span>Gaetan.baylou--lanot@insa-rennes.fr</span>
          </a>
          <a href="https://www.linkedin.com/in/gaetan-baylou-lanot-72931b177/" target="_blank" rel="noopener" class="contact-item-discreet">
            <i class="fa-brands fa-linkedin-in"></i>
            <span>Gaëtan Baylou-Lanot</span>
          </a>
          <a href="https://canva.link/ky3nhbgvb7r8ahv" target="_blank" rel="noopener" class="contact-item-discreet">
            <i class="fa-regular fa-file-pdf"></i>
            <span>View CV Link</span>
          </a>
        </div>
      </div>
    </div>
  </aside>

  <!-- ── MAIN CONTENT AREA ── -->
  <main class="content-wrapper">

    <!-- SECTION 1: HERO -->
    <section id="introduction">
      <div class="hero-text-block">
        <span class="eyebrow">Mechanical &amp; Control Engineering · INSA Rennes</span>
        <h1 class="hero-title">Hi, I'm <em>Gaëtan</em><span class="dot">.</span></h1>
        <p class="hero-sub">
          Welcome to my portfolio: a brief introduction and a few projects, including my best work in the fields of programming and AI.
        </p>
        
        <div class="btn-container">
          <a class="btn btn-primary" href="https://canva.link/ky3nhbgvb7r8ahv" target="_blank" rel="noopener">
            Download CV
          </a>
          <a class="btn btn-secondary" href="#contact-minimal" id="say-hello-btn">
            Say hello
          </a>
          <a class="btn btn-accent" href="#van-conversion">
            Personality
          </a>
        </div>

        <blockquote class="prompt-info">
          <i class="fa-solid fa-circle-info" style="color: var(--accent);"></i>
          <span><strong>This page is currently being modified.</strong></span>
        </blockquote>
      </div>
    </section>

    <!-- SECTION 2: PROFESSIONAL TRACKS -->
    <section id="gma-internships">
      <span class="eyebrow">Professional Tracks</span>
      <h2 class="section-title">The <em>GMA</em> Experience</h2>
      <p class="paragraph">
        Even though I am currently focusing on robotics and AI, I chose to pursue a Mechanical and Control Engineering degree (GMA) at INSA Rennes. I believe the various internships I have completed summarize quite well what GMA is about.
      </p>
      <p class="paragraph">
        At <strong>XSun</strong>, I applied finite element analysis (FEA) and materials science knowledge. At <strong>ADDLAB (Decathlon)</strong>, my focus was on advanced 3D modeling and additive manufacturing. Finally, at <strong>Metallicadour</strong> (and through my academic continuation), I mastered the operation and control theory of industrial robotic arms. 
      </p>
      <p class="paragraph">
        Additionally, my curriculum has provided me with a strong foundation in advanced math and physics, including Computational Fluid Dynamics (CFD), Noise, Vibration, and Harshness (NVH) or Partial Differential Equations (PDE) for example.
      </p>
      
      <div class="media-row">
        <figure class="media-item">
          <img class="project-img" src="https://raw.githubusercontent.com/gaetanbl/gaetanbl.github.io/72a4edc1369b97d542c935f5e171613c8af7bd76/20260511_113120%20(1).jpg" alt="Programming a Stäubli robotic arm" onerror="this.style.display='none'">
          <figcaption class="caption">4th-year project: programming a Stäubli robotic arm</figcaption>
        </figure>
        
        <figure class="media-item">
          <img class="project-img" src="https://raw.githubusercontent.com/gaetanbl/gaetanbl.github.io/b6ca105b582d8e456535b538616a6aab6c2c9eb8/Capture%20d'%C3%A9cran%202026-07-10%20231935.png" alt="XSun SX0 flight demonstration" onerror="this.style.display='none'">
          <figcaption class="caption">Internship at XSun: flight demonstration of the SX0</figcaption>
        </figure>
      </div>
    </section>

    <!-- SECTION 3: SEQUENTIAL PROJECTS -->
    <section id="projects-container" style="border-bottom: none; padding-bottom: 0;">
      <span class="eyebrow">Technical Works</span>
      <h2 class="section-title">Academic Tracks &amp; Technical Engineering Projects</h2>

      <div class="projects-stack">
        
        <!-- Project 1: INS'Aérien Club -->
        <article class="project-article" id="ins-aerien">
          <div class="proj-meta-header">
            <div class="tag-container">
              <span class="tag">FPV Drones</span>
              <span class="tag">Leadership</span>
              <span class="tag">Aviation</span>
            </div>
            <span class="proj-year">Association</span>
          </div>
          <h3>✈️ INS'Aérien Club</h3>
          <p>Founded and managed an open-access FPV drone club at INSA Rennes: creation of quick flying machine, tutoring how to fly and I have freely captured a lot of event on and outside of my school campus.</p>
          
          <div class="media-row">
            <figure class="media-item">
              <img class="project-img" src="https://raw.githubusercontent.com/gaetanbl/gaetanbl.github.io/1918aba69b07d2b2eb488313b6324177da91e821/Capture%20d'%C3%A9cran%202026-07-10%20212132d.png" alt="FPV Drone Flying" onerror="this.style.display='none'">
              <figcaption class="caption">Open event for everyone during the "Insa'lan 2024" festival</figcaption>
            </figure>
            <figure class="media-item">
              <video class="project-video" autoplay loop muted playsinline>
                <source src="https://raw.githubusercontent.com/gaetanbl/gaetanbl.github.io/1918aba69b07d2b2eb488313b6324177da91e821/Enregistrement%202026-07-10%20211746.mp4" type="video/mp4">
              </video>
              <figcaption class="caption">Repairing one of our drones after a crash</figcaption>
            </figure>
          </div>
        </article>

        <!-- Project 2: Robotics Cup C++ -->
        <article class="project-article" id="code-project-1">
          <div class="proj-meta-header">
            <div class="tag-container">
              <span class="tag">C++</span>
              <span class="tag">Embedded Systems</span>
              <span class="tag">Robotics Cup</span>
            </div>
            <span class="proj-year">Project #1</span>
          </div>
          <h3>⚙️ Robotics Cup C++</h3>
          <p>Embedded systems programming within the INSA Rennes school robotics club in C++, I have discover the pleasure of low level programmation.</p>
          
          <div class="media-row">
            <figure class="media-item">
              <img class="project-img" src="https://raw.githubusercontent.com/gaetanbl/gaetanbl.github.io/2f216488172232404a07bd31b22841a641c82970/Capture%20d'%C3%A9cran%202026-07-10%20213148.png" alt="Robotics Development Board" onerror="this.style.display='none'">
              <figcaption class="caption">End of the competition: 41st out of 122</figcaption>
            </figure>
            <figure class="media-item">
              <img class="project-img" src="https://raw.githubusercontent.com/gaetanbl/gaetanbl.github.io/2f216488172232404a07bd31b22841a641c82970/Capture%20d'%C3%A9cran%202026-07-10%20213333.png" alt="Robotics Cup Event" onerror="this.style.display='none'">
              <figcaption class="caption">Everyone working hard after just a few hours of sleep</figcaption>
            </figure>
          </div>
        </article>

        <!-- Project 3: ROS2 Autonomous -->
        <article class="project-article" id="code-project-2">
          <div class="proj-meta-header">
            <div class="tag-container">
              <span class="tag">ROS2</span>
              <span class="tag">Python</span>
              <span class="tag">Simulation</span>
            </div>
            <span class="proj-year">Project #2</span>
          </div>
<h3>🔌 ROS2 Autonomous</h3>
          <p>I have kindly asked if I can borrow a mini robot at the computer science degree (next door building) to learn autonomously how to code in ROS 2. It was my first experience with ROS.</p>

          <div class="media-row">
            <figure class="media-item">
              <img class="project-img" src="https://raw.githubusercontent.com/gaetanbl/gaetanbl.github.io/d542337f973712e144f2982fbe4898fb97f34b7d/20260711_002642.jpg" alt="Robotics Development Board" onerror="this.style.display='none'">
              <figcaption class="caption">Robot used with ROS2</figcaption>
            </figure>
            <figure class="media-item">
              <img class="project-img" src="https://raw.githubusercontent.com/gaetanbl/gaetanbl.github.io/d542337f973712e144f2982fbe4898fb97f34b7d/Capture%20d'%C3%A9cran%202026-07-11%20002404.png" alt="Robotics Cup Event" onerror="this.style.display='none'">
              <figcaption class="caption">Kinematic Model of the Four Mecanum Wheeled Mobile Robot</figcaption>
            </figure>
          </div>
        </article>

        <!-- Project 4: Supervised Vision -->
        <article class="project-article" id="ia-project-1">
          <div class="proj-meta-header">
            <div class="tag-container">
              <span class="tag">Computer Vision</span>
              <span class="tag">Google Scholar</span>
              <span class="tag">ML Pipeline</span>
            </div>
            <span class="proj-year">AI Project #1</span>
          </div>
          <h3>🧠 Supervised Vision</h3>
          <p>Implementation with a 70 hour-video tuto on google scholar an AI that have learned to reconize foods.</p>
          
          <div class="media-row">
            <figure class="media-item">
              <img class="project-img" src="https://raw.githubusercontent.com/gaetanbl/gaetanbl.github.io/9632aa617c7be56130a5a62bb2fb1d54c0959622/Capture%20d'%C3%A9cran%202026-07-10%20214526.png" alt="Supervised Vision 1" onerror="this.style.display='none'">
              <figcaption class="caption">Summary output of my second model: desactivation of the gradient in order to reduce the trainable parameters</figcaption>
            </figure>
            <figure class="media-item">
              <img class="project-img" src="https://raw.githubusercontent.com/gaetanbl/gaetanbl.github.io/d4851539b943f516efef2fa0fa530906ff71a0ee/vision.png" alt="Supervised Vision 2" onerror="this.style.display='none'">
              <figcaption class="caption">Prediction on FashionMNIST</figcaption>
            </figure>
          </div>
        </article>

        <!-- Project 5: Duckiebot RL -->
        <article class="project-article" id="ia-project-2">
          <div class="proj-meta-header">
            <div class="tag-container">
              <span class="tag">Reinforcement Learning</span>
              <span class="tag">Docker</span>
              <span class="tag">Isaac Lab</span>
              <span class="tag">Actor-Critic SAC/PPO</span>
            </div>
            <span class="proj-year">AI Project #2</span>
          </div>
          <h3>🤖 Duckiebot RL</h3>
          <p>My last intership (and the best :)), I have learned a lot of things: docker, RL, USD Isaac lab and sim, WSL, RL, Actor-Critic Methods: SAC and PPO...</p>
          
          <div class="media-row">
            <figure class="media-item">
              <video class="project-video" autoplay loop muted playsinline>
                <source src="https://raw.githubusercontent.com/gaetanbl/gaetanbl.github.io/72a4edc1369b97d542c935f5e171613c8af7bd76/20260710_115740_1%20(1).mp4" type="video/mp4">
              </video>
              <figcaption class="caption">Duckiebot line following</figcaption>
            </figure>
            <figure class="media-item">
              <img class="project-img" src="https://raw.githubusercontent.com/gaetanbl/gaetanbl.github.io/2f216488172232404a07bd31b22841a641c82970/Capture%20d'%C3%A9cran%202026-07-10%20212649.png" alt="Duckiebot simulation" onerror="this.style.display='none'">
              <figcaption class="caption">Obstacle avoidance policy training on Isaac Sim</figcaption>
            </figure>
          </div>

          <div class="media-row">
            <figure class="media-item">
              <video class="project-video" autoplay loop muted playsinline>
                <source src="https://raw.githubusercontent.com/gaetanbl/gaetanbl.github.io/d4851539b943f516efef2fa0fa530906ff71a0ee/Projet%20vid%C3%A9o%205.mp4" type="video/mp4">
              </video>
              <figcaption class="caption">First try to implement the CNN</figcaption>
            </figure>
            <figure class="media-item">
              <img class="project-img" src="https://raw.githubusercontent.com/gaetanbl/gaetanbl.github.io/9632aa617c7be56130a5a62bb2fb1d54c0959622/Capture%20d%E2%80%99%C3%A9cran%202026-07-10%20215133.png" alt="Supervised Vision 2" onerror="this.style.display='none'">
              <figcaption class="caption">Streamlit dashboard comparing runs and learning curves</figcaption>
            </figure>
          </div>
        </article>

      </div>
    </section>

<!-- SECTION 4: PERSONALITY (The Van conversion) -->
    <section id="van-conversion">
      <span class="eyebrow">Behind the Code</span>
      <h2 class="section-title">🚐 Personality</h2>
      
      <div class="personality-text">
        <p class="paragraph">
          This isn't my first project, but it is definitely one of the ones I'm most proud of. Over the course of three years, whenever I came home for the holidays, my grandfather and I worked together to convert a van from scratch so I could go on adventures. I am fond of sports, but what I love most is the call of the wild. Among my friends, I'm known for sleeping outside in -15°C weather or camping under a kayak to escape pouring rain.
        </p>
        <p class="paragraph">
          While my CV highlights my structured, technical side, people generally describe me as a highly sociable and cheerful person. My best memories come from these raw outdoor experiences—whether it's spending 5 days hiking around Belle-Île and interrailing across Europe with friends, or trekking alone for 4 days in the Dolomites sleeping under the stars.
        </p>
        
        <div class="media-row">
            <!-- Lien corrigé (suppression de /blob/) -->
            <figure class="media-item">
              <img class="project-img" src="https://raw.githubusercontent.com/gaetanbl/gaetanbl.github.io/72a4edc1369b97d542c935f5e171613c8af7bd76/20230624_182522%20(1).jpg" alt="Van conversion" onerror="this.style.display='none'">
              <figcaption class="caption">First step of the conversion: building the rear cabinet in 2022</figcaption>
            </figure>
            
            <figure class="media-item">
              <img class="project-img" src="https://raw.githubusercontent.com/gaetanbl/gaetanbl.github.io/9632aa617c7be56130a5a62bb2fb1d54c0959622/Capture%20d'%C3%A9cran%202026-07-10%20214248.png" alt="Van tour" onerror="this.style.display='none'">
              <figcaption class="caption">At the start of the Belle-Île tour</figcaption>
            </figure>
        </div>
      </div>
    </section>

    <footer></footer>

  </main>


  <!-- ── JAVASCRIPT ── -->
  <script>
    /* ── SAY HELLO BUTTON HIGHLIGHT ── */
    const sayHelloBtn = document.getElementById('say-hello-btn');
    if (sayHelloBtn) {
      sayHelloBtn.addEventListener('click', (e) => {
        const contactBlock = document.getElementById('contact-minimal');
        if (!contactBlock) return;
        contactBlock.classList.remove('flash-highlight');
        void contactBlock.offsetWidth; 
        contactBlock.classList.add('flash-highlight');
        contactBlock.scrollIntoView({ behavior: 'smooth', block: 'nearest' });
      });
    }

    /* ── MOBILE NAVBAR TOGGLE ── */
    function toggleNav() {
      const body = document.body;
      const icon = document.getElementById('hamburger-icon');
      
      body.classList.toggle('nav-open');
      if (body.classList.contains('nav-open')) {
        icon.className = 'fa-solid fa-xmark';
      } else {
        icon.className = 'fa-solid fa-bars';
      }
    }

    function closeNav() {
      document.body.classList.remove('nav-open');
      document.getElementById('hamburger-icon').className = 'fa-solid fa-bars';
    }

    /* ── ACTIVE NAV STATE ON SCROLL (Intersection Observer) ── */
    const targets = document.querySelectorAll('section, .project-article');
    const navItems = document.querySelectorAll('.nav-links li');

    const observerOptions = {
      root: null,
      threshold: 0.15, 
      rootMargin: "-10% 0px -60% 0px" 
    };

    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          const id = entry.target.getAttribute('id');
          if (!id) return;

          navItems.forEach(item => {
            const anchor = item.querySelector('a');
            if (anchor) {
              const href = anchor.getAttribute('href');
              if (href === `#${id}`) {
                navItems.forEach(n => n.classList.remove('active'));
                item.classList.add('active');
              }
            }
          });
        }
      });
    }, observerOptions);

    targets.forEach(target => {
      if (target.id) {
        observer.observe(target);
      }
    });
  </script>
</body>
</html>
