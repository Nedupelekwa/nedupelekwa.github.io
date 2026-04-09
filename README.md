<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Chinedu Elekwa Promise | Data Analyst</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;500;600;700;800&family=IBM+Plex+Mono:wght@300;400;500&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet" />
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #080A0E;
    --bg-card: #0E1117;
    --bg-glass: rgba(255,255,255,0.04);
    --border: rgba(255,255,255,0.09);
    --border-accent: rgba(0,210,140,0.35);
    --accent: #00D28C;
    --accent-dim: rgba(0,210,140,0.1);
    --accent2: #3B82F6;
    --text-primary: #FFFFFF;
    --text-secondary: #B0BAD0;
    --text-muted: #5A6680;
    --mono: 'IBM Plex Mono', monospace;
    --sans: 'Inter', sans-serif;
    --display: 'Syne', sans-serif;
  }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text-primary);
    font-family: var(--sans);
    font-weight: 400;
    line-height: 1.7;
    overflow-x: hidden;
  }

  body::before {
    content: '';
    position: fixed; inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 512 512' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.03'/%3E%3C/svg%3E");
    pointer-events: none; z-index: 0;
  }

  /* ── NAV ── */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; justify-content: space-between; align-items: center;
    padding: 1.1rem 4rem;
    border-bottom: 1px solid var(--border);
    background: rgba(8,10,14,0.92);
    backdrop-filter: blur(20px);
  }
  .nav-logo { font-family: var(--mono); font-size: 13px; color: var(--accent); letter-spacing: 0.1em; text-decoration: none; font-weight: 400; }
  .nav-links { display: flex; gap: 2rem; list-style: none; align-items: center; }
  .nav-links a { font-family: var(--mono); font-size: 11px; color: var(--text-secondary); text-decoration: none; letter-spacing: 0.12em; text-transform: uppercase; transition: color 0.2s; font-weight: 400; }
  .nav-links a:hover { color: var(--accent); }
  .nav-cta { color: var(--accent) !important; border: 1px solid var(--border-accent) !important; padding: 0.4rem 1rem; border-radius: 4px; transition: background 0.2s !important; }
  .nav-cta:hover { background: var(--accent-dim) !important; }
  .nav-hamburger { display: none; flex-direction: column; gap: 5px; cursor: pointer; padding: 4px; }
  .nav-hamburger span { display: block; width: 22px; height: 2px; background: var(--text-secondary); border-radius: 2px; transition: 0.3s; }

  /* ── HERO ── */
  .hero {
    min-height: 100vh;
    display: flex; flex-direction: column; justify-content: center;
    padding: 9rem 4rem 5rem;
    position: relative; overflow: hidden;
  }
  .hero-grid-bg {
    position: absolute; inset: 0;
    background-image: linear-gradient(var(--border) 1px, transparent 1px), linear-gradient(90deg, var(--border) 1px, transparent 1px);
    background-size: 60px 60px;
    mask-image: radial-gradient(ellipse 80% 60% at 50% 50%, black 20%, transparent 80%);
    pointer-events: none;
  }
  .hero-glow { position: absolute; top: 15%; left: 5%; width: 600px; height: 500px; background: radial-gradient(ellipse, rgba(0,210,140,0.07) 0%, transparent 70%); pointer-events: none; }
  .hero-glow-2 { position: absolute; bottom: 10%; right: 5%; width: 500px; height: 400px; background: radial-gradient(ellipse, rgba(59,130,246,0.06) 0%, transparent 70%); pointer-events: none; }

  /* Hero layout: text left, photo right */
  .hero-inner {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 4rem;
    position: relative; z-index: 1;
    width: 100%;
  }
  .hero-content { flex: 1; min-width: 0; }
  .hero-photo-col { flex-shrink: 0; }

  /* Photo */
  .hero-photo-wrap {
    position: relative;
    width: 280px; height: 280px;
  }
  .hero-photo-wrap::before {
    content: '';
    position: absolute; inset: -3px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    z-index: 0;
  }
  .hero-photo-wrap::after {
    content: '';
    position: absolute; inset: 3px;
    border-radius: 50%;
    background: var(--bg);
    z-index: 1;
  }
  .hero-photo {
    position: absolute; inset: 6px;
    border-radius: 50%;
    object-fit: cover;
    object-position: center top;
    width: calc(100% - 12px);
    height: calc(100% - 12px);
    z-index: 2;
    display: block;
  }
  /* Glow ring behind photo */
  .hero-photo-glow {
    position: absolute;
    inset: -20px;
    border-radius: 50%;
    background: radial-gradient(ellipse, rgba(0,210,140,0.15) 0%, transparent 70%);
    z-index: -1;
  }

  .hero-badge { font-family: var(--mono); font-size: 11px; color: var(--accent); letter-spacing: 0.18em; text-transform: uppercase; display: flex; align-items: center; gap: 0.6rem; margin-bottom: 1.6rem; font-weight: 400; }
  .hero-badge::before { content: ''; display: inline-block; width: 7px; height: 7px; border-radius: 50%; background: var(--accent); box-shadow: 0 0 10px var(--accent); animation: pulse 2s infinite; }
  @keyframes pulse { 0%, 100% { opacity: 1; box-shadow: 0 0 10px var(--accent); } 50% { opacity: 0.5; box-shadow: 0 0 4px var(--accent); } }

  .hero-name { font-family: var(--display); font-size: clamp(3rem, 6.5vw, 6.5rem); font-weight: 800; line-height: 0.95; letter-spacing: -0.02em; margin-bottom: 0.6rem; color: #FFFFFF; }
  .hero-name .accent { color: var(--accent); }
  .hero-title { font-family: var(--display); font-size: clamp(1.1rem, 2.5vw, 1.9rem); font-weight: 500; color: var(--text-secondary); margin-bottom: 1.5rem; letter-spacing: -0.01em; }
  .hero-desc { max-width: 500px; font-size: 15px; color: var(--text-secondary); line-height: 1.85; margin-bottom: 1.5rem; font-weight: 400; }

  .hero-badges { display: flex; flex-wrap: wrap; gap: 0.5rem; margin-bottom: 2rem; }
  .hero-pill { font-family: var(--mono); font-size: 11px; color: var(--text-secondary); border: 1px solid var(--border); padding: 0.3rem 0.8rem; border-radius: 20px; letter-spacing: 0.05em; font-weight: 400; }

  .hero-actions { display: flex; gap: 1rem; align-items: center; flex-wrap: wrap; }
  .btn-primary { background: var(--accent); color: #080A0E; font-family: var(--mono); font-size: 12px; font-weight: 600; letter-spacing: 0.1em; text-transform: uppercase; padding: 0.85rem 2rem; border-radius: 4px; text-decoration: none; transition: opacity 0.2s, transform 0.2s; white-space: nowrap; }
  .btn-primary:hover { opacity: 0.85; transform: translateY(-1px); }
  .btn-secondary { font-family: var(--mono); font-size: 12px; color: var(--text-secondary); text-decoration: none; letter-spacing: 0.1em; text-transform: uppercase; display: flex; align-items: center; gap: 0.5rem; transition: color 0.2s; font-weight: 400; white-space: nowrap; }
  .btn-secondary:hover { color: #FFFFFF; }

  .hero-stats { display: flex; gap: 3rem; margin-top: 4rem; padding-top: 2rem; border-top: 1px solid var(--border); flex-wrap: wrap; }
  .stat-val { font-family: var(--display); font-size: 2rem; font-weight: 700; color: #FFFFFF; display: block; }
  .stat-label { font-family: var(--mono); font-size: 10px; color: var(--text-muted); letter-spacing: 0.1em; text-transform: uppercase; font-weight: 400; }

  /* ── SECTIONS ── */
  section { padding: 6rem 4rem; position: relative; z-index: 1; }

  .section-label { font-family: var(--mono); font-size: 11px; color: var(--accent); letter-spacing: 0.22em; text-transform: uppercase; margin-bottom: 0.85rem; display: flex; align-items: center; gap: 0.75rem; font-weight: 400; }
  .section-label::after { content: ''; height: 1px; width: 40px; background: var(--border-accent); }
  .section-title { font-family: var(--display); font-size: clamp(1.8rem, 3.5vw, 2.8rem); font-weight: 700; letter-spacing: -0.02em; margin-bottom: 0.75rem; color: #FFFFFF; }
  .section-subtitle { color: var(--text-secondary); font-size: 15px; max-width: 500px; margin-bottom: 3.5rem; font-weight: 400; line-height: 1.7; }

  /* TAGS */
  .tag { font-family: var(--mono); font-size: 11px; color: var(--text-secondary); background: rgba(255,255,255,0.05); border: 1px solid var(--border); padding: 0.25rem 0.65rem; border-radius: 3px; letter-spacing: 0.05em; font-weight: 400; }
  .tag.accent-tag { color: var(--accent); border-color: rgba(0,210,140,0.25); background: rgba(0,210,140,0.06); }
  .tag.blue-tag { color: var(--accent2); border-color: rgba(59,130,246,0.25); background: rgba(59,130,246,0.06); }

  /* ── SKILLS ── */
  #skills { background: var(--bg-card); border-top: 1px solid var(--border); border-bottom: 1px solid var(--border); }
  .skills-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); gap: 1.5px; background: var(--border); border: 1px solid var(--border); border-radius: 8px; overflow: hidden; }
  .skill-block { background: var(--bg-card); padding: 2rem; transition: background 0.2s; }
  .skill-block:hover { background: rgba(255,255,255,0.04); }
  .skill-block-icon { font-size: 20px; margin-bottom: 0.85rem; }
  .skill-block-title { font-family: var(--display); font-size: 0.95rem; font-weight: 600; margin-bottom: 0.75rem; color: #FFFFFF; }
  .skill-tags { display: flex; flex-wrap: wrap; gap: 0.4rem; }

  /* ── PROJECTS ── */
  .projects-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 1.5rem; }
  .project-card { background: var(--bg-card); border: 1px solid var(--border); border-radius: 10px; overflow: hidden; position: relative; transition: border-color 0.25s, transform 0.25s; }
  .project-card::before { content: ''; position: absolute; top: 0; left: 0; right: 0; height: 2px; background: linear-gradient(90deg, var(--accent), var(--accent2)); opacity: 0; transition: opacity 0.25s; }
  .project-card:hover { border-color: rgba(255,255,255,0.15); transform: translateY(-4px); }
  .project-card:hover::before { opacity: 1; }
  .project-img { width: 100%; height: 190px; object-fit: cover; border-bottom: 1px solid var(--border); display: block; }
  .project-img-placeholder { width: 100%; height: 190px; background: rgba(255,255,255,0.025); border-bottom: 1px solid var(--border); display: flex; align-items: center; justify-content: center; font-family: var(--mono); font-size: 11px; color: var(--text-muted); letter-spacing: 0.12em; }
  .project-body { padding: 1.75rem; }
  .project-number { font-family: var(--mono); font-size: 11px; color: var(--text-muted); margin-bottom: 0.85rem; display: flex; justify-content: space-between; align-items: center; }
  .project-type { font-family: var(--mono); font-size: 10px; color: var(--accent); border: 1px solid rgba(0,210,140,0.25); padding: 0.2rem 0.6rem; border-radius: 2px; letter-spacing: 0.08em; }
  .project-title { font-family: var(--display); font-size: 1.15rem; font-weight: 700; margin-bottom: 0.6rem; letter-spacing: -0.01em; color: #FFFFFF; }
  .project-desc { font-size: 14px; color: var(--text-secondary); line-height: 1.8; margin-bottom: 1.25rem; font-weight: 400; }
  .project-stack { display: flex; flex-wrap: wrap; gap: 0.4rem; margin-bottom: 1.25rem; }
  .project-link { font-family: var(--mono); font-size: 11px; color: var(--accent2); text-decoration: none; letter-spacing: 0.08em; display: inline-flex; align-items: center; gap: 0.4rem; transition: color 0.2s; text-transform: uppercase; border: 1px solid rgba(59,130,246,0.3); padding: 0.45rem 0.9rem; border-radius: 4px; font-weight: 500; }
  .project-link:hover { color: var(--accent); border-color: var(--border-accent); }

  /* ── TIMELINE ── */
  .timeline { position: relative; padding-left: 2rem; }
  .timeline::before { content: ''; position: absolute; left: 0; top: 8px; bottom: 0; width: 1px; background: var(--border); }
  .timeline-item { position: relative; padding-bottom: 3rem; padding-left: 2rem; }
  .timeline-item:last-child { padding-bottom: 0; }
  .timeline-dot { position: absolute; left: -2.4rem; top: 8px; width: 8px; height: 8px; border-radius: 50%; background: var(--accent); box-shadow: 0 0 12px rgba(0,210,140,0.5); }
  .timeline-date { font-family: var(--mono); font-size: 11px; color: var(--text-muted); letter-spacing: 0.12em; text-transform: uppercase; margin-bottom: 0.4rem; font-weight: 400; }
  .timeline-role { font-family: var(--display); font-size: 1.15rem; font-weight: 700; margin-bottom: 0.2rem; color: #FFFFFF; }
  .timeline-company { font-family: var(--mono); font-size: 12px; color: var(--accent); margin-bottom: 0.9rem; font-weight: 400; }
  .timeline-bullets { list-style: none; }
  .timeline-bullets li { font-size: 14px; color: var(--text-secondary); padding: 0.28rem 0 0.28rem 1.2rem; position: relative; font-weight: 400; line-height: 1.65; }
  .timeline-bullets li::before { content: '—'; position: absolute; left: 0; color: var(--text-muted); font-family: var(--mono); font-size: 11px; }

  /* ── CERTIFICATIONS ── */
  #certifications { background: var(--bg-card); border-top: 1px solid var(--border); border-bottom: 1px solid var(--border); }
  .cert-group-label { font-family: var(--mono); font-size: 11px; letter-spacing: 0.18em; text-transform: uppercase; margin-bottom: 1.5rem; padding-bottom: 0.75rem; border-bottom: 1px solid var(--border); font-weight: 500; }
  .cert-group-label.green { color: var(--accent); }
  .cert-group-label.blue { color: var(--accent2); }
  .cert-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(210px, 1fr)); gap: 1.25rem; margin-bottom: 3rem; }
  .cert-card { background: var(--bg); border: 1px solid var(--border); border-radius: 8px; overflow: hidden; transition: transform 0.25s, border-color 0.25s; }
  .cert-card:hover { transform: translateY(-4px); border-color: rgba(255,255,255,0.14); }
  .cert-stripe { height: 3px; background: linear-gradient(90deg, var(--accent), var(--accent2)); }
  .cert-stripe.blue { background: linear-gradient(90deg, var(--accent2), #8b5cf6); }
  .cert-body { padding: 1.35rem; }
  .cert-icon { font-size: 20px; margin-bottom: 0.85rem; }
  .cert-title { font-family: var(--display); font-size: 0.88rem; font-weight: 700; margin-bottom: 0.45rem; line-height: 1.4; color: #FFFFFF; }
  .cert-issuer { font-family: var(--mono); font-size: 11px; color: var(--accent); letter-spacing: 0.08em; font-weight: 400; }
  .cert-issuer.blue { color: var(--accent2); }

  /* ── RECOGNITIONS ── */
  .rec-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); gap: 1.5rem; }
  .rec-card { background: var(--bg-card); border: 1px solid var(--border); border-radius: 10px; padding: 2rem; position: relative; transition: transform 0.25s, border-color 0.25s; overflow: hidden; }
  .rec-card::before { content: ''; position: absolute; top: 0; left: 0; right: 0; height: 2px; background: linear-gradient(90deg, var(--accent), var(--accent2)); }
  .rec-card:hover { transform: translateY(-4px); border-color: rgba(255,255,255,0.14); }
  .rec-icon { font-size: 26px; margin-bottom: 0.85rem; }
  .rec-title { font-family: var(--display); font-size: 1rem; font-weight: 700; margin-bottom: 0.6rem; color: #FFFFFF; }
  .rec-desc { font-size: 14px; color: var(--text-secondary); line-height: 1.75; font-weight: 400; }

  /* ── CONTACT ── */
  #contact { text-align: center; }
  .contact-wrapper { max-width: 620px; margin: 0 auto; }
  .contact-email { font-family: var(--display); font-size: clamp(1.3rem, 3.5vw, 2rem); font-weight: 700; color: #FFFFFF; text-decoration: none; display: inline-block; margin: 2rem 0; border-bottom: 2px solid var(--accent); padding-bottom: 0.3rem; transition: color 0.2s; word-break: break-all; }
  .contact-email:hover { color: var(--accent); }
  .socials { display: flex; justify-content: center; gap: 0.75rem; margin-top: 2rem; flex-wrap: wrap; }
  .social-link { font-family: var(--mono); font-size: 11px; color: var(--text-secondary); text-decoration: none; letter-spacing: 0.1em; text-transform: uppercase; transition: color 0.2s, border-color 0.2s; display: flex; align-items: center; gap: 0.4rem; border: 1px solid var(--border); padding: 0.65rem 1.1rem; border-radius: 4px; font-weight: 500; }
  .social-link:hover { color: var(--accent); border-color: var(--border-accent); }

  /* ── FOOTER ── */
  footer { padding: 2rem 4rem; border-top: 1px solid var(--border); display: flex; justify-content: space-between; align-items: center; }
  footer p { font-family: var(--mono); font-size: 11px; color: var(--text-muted); letter-spacing: 0.08em; font-weight: 400; }

  /* ── REVEAL ── */
  .reveal { opacity: 0; transform: translateY(20px); transition: opacity 0.65s ease, transform 0.65s ease; }
  .reveal.visible { opacity: 1; transform: none; }

  /* ── MOBILE NAV OVERLAY ── */
  .mobile-nav {
    display: none;
    position: fixed; top: 0; left: 0; right: 0; bottom: 0; z-index: 200;
    background: rgba(8,10,14,0.98);
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 2.5rem;
  }
  .mobile-nav.open { display: flex; }
  .mobile-nav a { font-family: var(--mono); font-size: 18px; color: var(--text-secondary); text-decoration: none; letter-spacing: 0.15em; text-transform: uppercase; transition: color 0.2s; font-weight: 400; }
  .mobile-nav a:hover { color: var(--accent); }
  .mobile-nav-close { position: absolute; top: 1.25rem; right: 1.5rem; font-family: var(--mono); font-size: 22px; color: var(--text-muted); cursor: pointer; background: none; border: none; line-height: 1; }

  /* ── RESPONSIVE ── */
  @media (max-width: 900px) {
    nav { padding: 1rem 1.5rem; }
    .nav-links { display: none; }
    .nav-hamburger { display: flex; }

    .hero { padding: 7rem 1.5rem 4rem; }
    .hero-inner {
      flex-direction: column-reverse;
      align-items: center;
      text-align: center;
      gap: 2.5rem;
    }
    .hero-content { width: 100%; }
    .hero-photo-col { width: 100%; display: flex; justify-content: center; }
    .hero-photo-wrap { width: 200px; height: 200px; }
    .hero-badge { justify-content: center; }
    .hero-badges { justify-content: center; }
    .hero-actions { justify-content: center; }
    .hero-desc { margin: 0 auto 1.5rem; }
    .hero-stats { justify-content: center; gap: 2rem; }

    section { padding: 4rem 1.5rem; }

    .skills-grid { grid-template-columns: 1fr; }
    .projects-grid { grid-template-columns: 1fr; }
    .cert-grid { grid-template-columns: repeat(auto-fit, minmax(160px, 1fr)); }
    .rec-grid { grid-template-columns: 1fr; }

    footer { flex-direction: column; gap: 0.75rem; text-align: center; padding: 1.5rem; }

    .socials { gap: 0.5rem; }
    .social-link { font-size: 10px; padding: 0.55rem 0.9rem; }

    .contact-email { font-size: clamp(1.1rem, 5vw, 1.5rem); }
  }

  @media (max-width: 480px) {
    .hero-stats { flex-direction: column; align-items: center; gap: 1.25rem; }
    .stat-val { font-size: 1.8rem; }
    .hero-name { font-size: clamp(2.5rem, 13vw, 4rem); }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a href="#" class="nav-logo">[ chinedu.elekwa ]</a>
  <ul class="nav-links">
    <li><a href="#skills">Skills</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#experience">Experience</a></li>
    <li><a href="#certifications">Certs</a></li>
    <li><a href="#recognitions">Recognition</a></li>
    <li><a href="#contact" class="nav-cta">Hire Me</a></li>
  </ul>
  <div class="nav-hamburger" onclick="document.querySelector('.mobile-nav').classList.add('open')">
    <span></span><span></span><span></span>
  </div>
</nav>

<!-- MOBILE NAV OVERLAY -->
<div class="mobile-nav">
  <button class="mobile-nav-close" onclick="document.querySelector('.mobile-nav').classList.remove('open')">✕</button>
  <a href="#skills" onclick="document.querySelector('.mobile-nav').classList.remove('open')">Skills</a>
  <a href="#projects" onclick="document.querySelector('.mobile-nav').classList.remove('open')">Projects</a>
  <a href="#experience" onclick="document.querySelector('.mobile-nav').classList.remove('open')">Experience</a>
  <a href="#certifications" onclick="document.querySelector('.mobile-nav').classList.remove('open')">Certifications</a>
  <a href="#recognitions" onclick="document.querySelector('.mobile-nav').classList.remove('open')">Recognition</a>
  <a href="#contact" onclick="document.querySelector('.mobile-nav').classList.remove('open')" style="color:var(--accent)">Hire Me</a>
</div>

<!-- HERO -->
<section class="hero" id="hero">
  <div class="hero-grid-bg"></div>
  <div class="hero-glow"></div>
  <div class="hero-glow-2"></div>

  <div class="hero-inner">
    <!-- TEXT -->
    <div class="hero-content">
      <div class="hero-badge">Open to new opportunities · Lagos, Nigeria</div>
      <h1 class="hero-name">Chinedu<br><span class="accent">Elekwa</span></h1>
      <p class="hero-title">Data Analyst & Aspiring Analytics Engineer</p>
      <p class="hero-desc">
        Building scalable data solutions and turning raw data into strategic insights. I bring the precision of a mathematician, the clarity of an educator, and the impact-focus of a business analyst to every problem I solve.
      </p>
      <div class="hero-badges">
        <span class="hero-pill">SQL</span>
        <span class="hero-pill">Python</span>
        <span class="hero-pill">Power BI</span>
        <span class="hero-pill">Looker Studio</span>
        <span class="hero-pill">Data Modeling</span>
        <span class="hero-pill">SAP</span>
        <span class="hero-pill">MS PowerPoint</span>
      </div>
      <div class="hero-actions">
        <a href="#projects" class="btn-primary">Explore My Work →</a>
        <a href="#contact" class="btn-secondary">Get in touch ↗</a>
      </div>
      <div class="hero-stats">
        <div><span class="stat-val">5+</span><span class="stat-label">Years in Data</span></div>
        <div><span class="stat-val">95%</span><span class="stat-label">Analytics Efficiency</span></div>
        <div><span class="stat-val">4+</span><span class="stat-label">Certifications</span></div>
        <div><span class="stat-val">100+</span><span class="stat-label">Analysts Mentored</span></div>
      </div>
    </div>

    <!-- PHOTO -->
    <div class="hero-photo-col">
      <div class="hero-photo-wrap">
        <div class="hero-photo-glow"></div>
        <img class="hero-photo" src="data:image/jpeg;base64,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" alt="Chinedu Elekwa Promise" />
      </div>
    </div>
  </div>
</section>

<!-- SKILLS -->
<section id="skills">
  <div class="section-label">Technical Arsenal</div>
  <h2 class="section-title">What I Work With</h2>
  <p class="section-subtitle reveal">From spreadsheets to cloud — every layer of the data workflow.</p>
  <div class="skills-grid reveal">
    <div class="skill-block">
      <div class="skill-block-icon">⬡</div>
      <div class="skill-block-title">Languages & Querying</div>
      <div class="skill-tags">
        <span class="tag accent-tag">SQL</span><span class="tag accent-tag">Python</span>
        <span class="tag">Data Cleaning</span><span class="tag">Statistical Analysis</span><span class="tag">Mathematics</span>
      </div>
    </div>
    <div class="skill-block">
      <div class="skill-block-icon">◎</div>
      <div class="skill-block-title">Visualization & BI</div>
      <div class="skill-tags">
        <span class="tag accent-tag">Power BI</span><span class="tag accent-tag">Looker Studio</span>
        <span class="tag">DAX</span><span class="tag">Dashboard Design</span><span class="tag">MS PowerPoint</span>
      </div>
    </div>
    <div class="skill-block">
      <div class="skill-block-icon">▣</div>
      <div class="skill-block-title">Spreadsheets & Productivity</div>
      <div class="skill-tags">
        <span class="tag accent-tag">MS Excel</span><span class="tag accent-tag">Google Sheets</span>
        <span class="tag">Google Forms</span><span class="tag">Google Workspace</span>
      </div>
    </div>
    <div class="skill-block">
      <div class="skill-block-icon">◈</div>
      <div class="skill-block-title">ERP & Operations</div>
      <div class="skill-tags">
        <span class="tag accent-tag">SAP</span>
        <span class="tag">Production Planning</span><span class="tag">Inventory Management</span><span class="tag">FMCG Supply Chain</span>
      </div>
    </div>
    <div class="skill-block">
      <div class="skill-block-icon">◯</div>
      <div class="skill-block-title">Cloud & Platforms</div>
      <div class="skill-tags">
        <span class="tag accent-tag">Google Cloud</span>
        <span class="tag">BigQuery</span><span class="tag">Looker Studio</span><span class="tag">Google Drive</span>
      </div>
    </div>
    <div class="skill-block">
      <div class="skill-block-icon">◫</div>
      <div class="skill-block-title">Soft Skills & Leadership</div>
      <div class="skill-tags">
        <span class="tag">Data Mentorship</span><span class="tag">Report Writing</span>
        <span class="tag">Stakeholder Comms</span><span class="tag">Teaching</span><span class="tag">Growth Mindset</span>
      </div>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section id="projects">
  <div class="section-label">Selected Work</div>
  <h2 class="section-title">Projects</h2>
  <p class="section-subtitle reveal">Real analytics work across FMCG, education, and edtech.</p>
  <div class="projects-grid">

    <div class="project-card reveal">
      <div class="project-img-placeholder">[ FMCG Production Analytics ]</div>
      <div class="project-body">
        <div class="project-number"><span>01</span><span class="project-type">Production Analytics</span></div>
        <div class="project-title">FMCG Production Data Pipeline</div>
        <div class="project-desc">Designed and deployed a data collection and analytics system at Frutta Juice & Services Ltd tracking output, downtime, waste, and material usage — boosting analytics efficiency to 95%.</div>
        <div class="project-stack">
          <span class="tag accent-tag">Google Sheets</span><span class="tag accent-tag">Google Forms</span>
          <span class="tag">SAP</span><span class="tag">MS PowerPoint</span>
        </div>
        <a href="https://nedupelekwa.github.io" target="_blank" class="project-link">View Portfolio ↗</a>
      </div>
    </div>

    <div class="project-card reveal">
      <img src="images/Business-dashboard.jpg" alt="Power BI Business Dashboard" class="project-img" onerror="this.style.display='none';this.nextElementSibling.style.display='flex'">
      <div class="project-img-placeholder" style="display:none">[ Power BI Business Dashboard ]</div>
      <div class="project-body">
        <div class="project-number"><span>02</span><span class="project-type">Business Intelligence</span></div>
        <div class="project-title">Power BI Business Dashboard</div>
        <div class="project-desc">End-to-end sales analytics dashboard revealing key business trends. Key finding: +24.5% YoY Sales growth from 2021 to 2022, enabling strategic leadership decisions.</div>
        <div class="project-stack">
          <span class="tag accent-tag">Power BI</span><span class="tag accent-tag">DAX</span>
          <span class="tag">Power Query</span><span class="tag">MS Excel</span>
        </div>
        <a href="https://github.com/Nedupelekwa/POWERBI-BUSINESS-DASHBOARD" target="_blank" class="project-link">View on GitHub ↗</a>
      </div>
    </div>

    <div class="project-card reveal">
      <div class="project-img-placeholder">[ Student Performance Analysis ]</div>
      <div class="project-body">
        <div class="project-number"><span>03</span><span class="project-type">Education Analytics</span></div>
        <div class="project-title">Student Performance Analysis System</div>
        <div class="project-desc">Built and maintained a student performance database. Used Excel to analyse results, identify at-risk students, and produce data-backed reports for school leadership and parents.</div>
        <div class="project-stack">
          <span class="tag accent-tag">MS Excel</span>
          <span class="tag">Google Sheets</span><span class="tag">Data Reporting</span>
        </div>
        <a href="https://nedupelekwa.github.io" target="_blank" class="project-link">View Portfolio ↗</a>
      </div>
    </div>

  </div>
</section>

<!-- EXPERIENCE -->
<section id="experience" style="background: var(--bg-card); border-top: 1px solid var(--border); border-bottom: 1px solid var(--border);">
  <div class="section-label">Career History</div>
  <h2 class="section-title">Experience</h2>
  <p class="section-subtitle reveal">Where I've built things that matter.</p>
  <div class="timeline reveal">

    <div class="timeline-item">
      <div class="timeline-dot"></div>
      <div class="timeline-date">Sept 2025 — Present</div>
      <div class="timeline-role">Data Analyst Intern</div>
      <div class="timeline-company">edMotion Technologies · Remote</div>
      <ul class="timeline-bullets">
        <li>Working on data analytics projects in the edtech space, applying SQL and Python to derive insights</li>
        <li>Contributing to data-driven product decisions and reporting workflows</li>
      </ul>
    </div>

    <div class="timeline-item">
      <div class="timeline-dot"></div>
      <div class="timeline-date">Sept 2025 — Present</div>
      <div class="timeline-role">DATA Volunteer Mentor</div>
      <div class="timeline-company">ALX Africa Data Programs · Remote</div>
      <ul class="timeline-bullets">
        <li>Mentoring aspiring data professionals across Africa in analytics, Python, and data science</li>
        <li>Served as Session Moderator at the Virtual Global Data & AI Tech Conference (GDAI) 2025</li>
        <li>Recognised as Ambassador by DataGlobal Hub for contributions to the data community</li>
      </ul>
    </div>

    <div class="timeline-item">
      <div class="timeline-dot"></div>
      <div class="timeline-date">2023 — 2025</div>
      <div class="timeline-role">Production Planner / Production Data Analyst</div>
      <div class="timeline-company">Frutta Juice and Services Limited · Lagos, Nigeria</div>
      <ul class="timeline-bullets">
        <li>Built a Google Forms & Sheets pipeline tracking output, downtime, waste and material usage — increasing analytics efficiency to 95%</li>
        <li>Managed production inventory end-to-end on SAP from raw materials to warehouse transfer</li>
        <li>Developed production and material plans to ensure continuous operations</li>
        <li>Produced professional stakeholder production reports using PowerPoint</li>
      </ul>
    </div>

    <div class="timeline-item">
      <div class="timeline-dot"></div>
      <div class="timeline-date">Jan 2023 — Sept 2024</div>
      <div class="timeline-role">Mathematics Educator / Data Analyst</div>
      <div class="timeline-company">Cedec International Secondary School · Lagos, Nigeria</div>
      <ul class="timeline-bullets">
        <li>Built and maintained a student performance database; analysed results with Excel to track progress</li>
        <li>Produced data-backed performance reports for school leadership and parents</li>
        <li>Managed customer relationships and provided mentorship to students</li>
      </ul>
    </div>

    <div class="timeline-item">
      <div class="timeline-dot" style="background: var(--text-muted); box-shadow: none;"></div>
      <div class="timeline-date">2020 — 2021 · 2013 — 2014</div>
      <div class="timeline-role">Mathematics Educator</div>
      <div class="timeline-company">Great Divine College & Divine Victory Schools · Lagos, Nigeria</div>
      <ul class="timeline-bullets">
        <li>Taught Mathematics at secondary school level — building the analytical foundations that underpin my data career</li>
      </ul>
    </div>

  </div>
</section>

<!-- CERTIFICATIONS -->
<section id="certifications">
  <div class="section-label">Credentials</div>
  <h2 class="section-title">Certifications</h2>
  <p class="section-subtitle reveal">Verified expertise across cloud, analytics, and data science.</p>

  <div class="cert-group-label green reveal">Career Certifications</div>
  <div class="cert-grid reveal">
    <div class="cert-card"><div class="cert-stripe"></div><div class="cert-body"><div class="cert-icon">☁</div><div class="cert-title">Google Cloud Data Analyst Certificate</div><div class="cert-issuer">Google Cloud</div></div></div>
    <div class="cert-card"><div class="cert-stripe"></div><div class="cert-body"><div class="cert-icon">◈</div><div class="cert-title">Data Analytics, Python Programming & Data Science</div><div class="cert-issuer">ALX Africa</div></div></div>
    <div class="cert-card"><div class="cert-stripe"></div><div class="cert-body"><div class="cert-icon">◎</div><div class="cert-title">Associate Data Analyst Certificate</div><div class="cert-issuer">DataCamp</div></div></div>
    <div class="cert-card"><div class="cert-stripe"></div><div class="cert-body"><div class="cert-icon">◯</div><div class="cert-title">Data Literacy Certificate</div><div class="cert-issuer">DataCamp</div></div></div>
    <div class="cert-card"><div class="cert-stripe"></div><div class="cert-body"><div class="cert-icon">▣</div><div class="cert-title">Google Workspace — Calendar, Drive, Docs, Sheets, Slides</div><div class="cert-issuer">Google via Coursera</div></div></div>
  </div>

  <div class="cert-group-label blue reveal">Professional & Soft Skills</div>
  <div class="cert-grid reveal">
    <div class="cert-card"><div class="cert-stripe blue"></div><div class="cert-body"><div class="cert-icon">◫</div><div class="cert-title">ALX Professional Foundations</div><div class="cert-issuer blue">ALX Africa</div></div></div>
    <div class="cert-card"><div class="cert-stripe blue"></div><div class="cert-body"><div class="cert-icon">⬡</div><div class="cert-title">Jobberman Soft Skills Training</div><div class="cert-issuer blue">Jobberman · 2021</div></div></div>
  </div>
</section>

<!-- RECOGNITIONS -->
<section id="recognitions" style="background: var(--bg-card); border-top: 1px solid var(--border); border-bottom: 1px solid var(--border);">
  <div class="section-label">Recognition</div>
  <h2 class="section-title">Awards & Volunteer Service</h2>
  <p class="section-subtitle reveal">Giving back to the African data community.</p>
  <div class="rec-grid reveal">
    <div class="rec-card">
      <div class="rec-icon">🌍</div>
      <div class="rec-title">DATA Volunteer Mentor — ALX Africa</div>
      <div class="rec-desc">Supporting the next generation of data professionals across Africa through hands-on mentorship in analytics, Python programming, and data science since September 2025.</div>
    </div>
    <div class="rec-card">
      <div class="rec-icon">🎙</div>
      <div class="rec-title">GDAI 2025 Session Moderator</div>
      <div class="rec-desc">Recognised by DataGlobal Hub with a Certificate of Recognition for Volunteer Service as Session Moderator at the Virtual Global Data & AI Tech Conference (GDAI) 2025.</div>
    </div>
    <div class="rec-card">
      <div class="rec-icon">◈</div>
      <div class="rec-title">Ambassador — DataGlobal Hub</div>
      <div class="rec-desc">Appointed as Ambassador at DataGlobal Hub, representing and advocating for the growth of the data and AI community in Nigeria and across Africa.</div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="contact-wrapper">
    <div class="section-label" style="justify-content: center;">Let's Talk</div>
    <h2 class="section-title reveal">Open to the Right<br>Opportunity</h2>
    <p class="section-subtitle reveal" style="margin: 0 auto 1rem; text-align: center; max-width: 420px;">
      Whether it's a full-time role, a freelance project, or just a conversation about data — reach out.
    </p>
    <a href="mailto:chinedupelekwa@gmail.com" class="contact-email reveal">chinedupelekwa@gmail.com</a>
    <div class="socials reveal">
      <a href="https://www.linkedin.com/in/chinedu-elekwa/" target="_blank" class="social-link">↗ LinkedIn</a>
      <a href="https://nedupelekwa.github.io" target="_blank" class="social-link">↗ GitHub</a>
      <a href="https://tinyurl.com/bdhbn9zt" target="_blank" class="social-link">↗ Website</a>
      <a href="tel:+2347033130747" class="social-link">↗ +234 703 313 0747</a>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <p>© 2026 Chinedu Elekwa Promise. All rights reserved.</p>
  <p>Built like a Data Product · Lagos, Nigeria</p>
</footer>

<script>
  const reveals = document.querySelectorAll('.reveal');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((e, i) => {
      if (e.isIntersecting) {
        setTimeout(() => e.target.classList.add('visible'), i * 70);
        observer.unobserve(e.target);
      }
    });
  }, { threshold: 0.08 });
  reveals.forEach(el => observer.observe(el));
</script>
</body>
</html>
