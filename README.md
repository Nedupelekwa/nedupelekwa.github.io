<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Chinedu Elekwa Promise — Analytics Engineer</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;500;600;700;800&family=IBM+Plex+Mono:wght@300;400;500&family=Inter:wght@300;400;500&display=swap" rel="stylesheet" />
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  :root {
    --bg: #080A0E;
    --bg-card: #0E1117;
    --bg-glass: rgba(255,255,255,0.03);
    --border: rgba(255,255,255,0.07);
    --border-accent: rgba(0,210,140,0.3);
    --accent: #00D28C;
    --accent-dim: rgba(0,210,140,0.08);
    --accent2: #3B82F6;
    --text-primary: #F0F2F5;
    --text-secondary: #7A8499;
    --text-muted: #3E4659;
    --mono: 'IBM Plex Mono', monospace;
    --sans: 'Inter', sans-serif;
    --display: 'Syne', sans-serif;
  }
  html { scroll-behavior: smooth; }
  body { background: var(--bg); color: var(--text-primary); font-family: var(--sans); font-weight: 300; line-height: 1.7; overflow-x: hidden; }
  body::before {
    content: ''; position: fixed; inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 512 512' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
    pointer-events: none; z-index: 0;
  }

  /* NAVIGATION */
  nav { position: fixed; top: 0; left: 0; right: 0; z-index: 100; display: flex; justify-content: space-between; align-items: center; padding: 1.25rem 4rem; border-bottom: 1px solid var(--border); background: rgba(8,10,14,0.85); backdrop-filter: blur(20px); }
  .nav-logo { font-family: var(--mono); font-size: 13px; color: var(--accent); letter-spacing: 0.08em; text-decoration: none; }
  .nav-links { display: flex; gap: 2.5rem; list-style: none; }
  .nav-links a { font-family: var(--mono); font-size: 12px; color: var(--text-secondary); text-decoration: none; letter-spacing: 0.1em; text-transform: uppercase; transition: color 0.2s; }
  .nav-links a:hover { color: var(--accent); }
  .nav-cta { font-family: var(--mono); font-size: 12px; color: var(--accent) !important; border: 1px solid var(--border-accent); padding: 0.45rem 1rem; border-radius: 4px; transition: background 0.2s !important; }
  .nav-cta:hover { background: var(--accent-dim) !important; }

  /* HERO */
  .hero { min-height: 100vh; display: flex; flex-direction: column; justify-content: center; padding: 10rem 4rem 6rem; position: relative; overflow: hidden; }
  .hero-grid-bg, .hero-glow, .hero-glow-2 { position: absolute; pointer-events: none; }
  .hero-grid-bg { inset: 0; background-image: linear-gradient(var(--border) 1px, transparent 1px), linear-gradient(90deg, var(--border) 1px, transparent 1px); background-size: 60px 60px; mask-image: radial-gradient(ellipse 80% 60% at 50% 50%, black 20%, transparent 80%); }
  .hero-glow { top: 20%; left: 10%; width: 700px; height: 500px; background: radial-gradient(ellipse, rgba(0,210,140,0.06) 0%, transparent 70%); }
  .hero-glow-2 { bottom: 10%; right: 5%; width: 500px; height: 400px; background: radial-gradient(ellipse, rgba(59,130,246,0.05) 0%, transparent 70%); }
  .hero-badge { font-family: var(--mono); font-size: 11px; color: var(--accent); letter-spacing: 0.15em; text-transform: uppercase; display: flex; align-items: center; gap: 0.6rem; margin-bottom: 1.8rem; }
  .hero-badge::before { content: ''; display: inline-block; width: 6px; height: 6px; border-radius: 50%; background: var(--accent); box-shadow: 0 0 8px var(--accent); animation: pulse 2s infinite; }
  @keyframes pulse { 0%,100%{opacity:1}50%{opacity:0.4} }
  .hero-name { font-family: var(--display); font-size: clamp(3.5rem, 8vw, 7.5rem); font-weight: 800; line-height: 0.95; letter-spacing: -0.02em; margin-bottom: 0.5rem; }
  .hero-name .accent { color: var(--accent); }
  .hero-title { font-family: var(--display); font-size: clamp(1.4rem, 3vw, 2.4rem); font-weight: 500; color: var(--text-secondary); margin-bottom: 2rem; letter-spacing: -0.01em; }
  .hero-desc { max-width: 520px; font-size: 15px; color: var(--text-secondary); line-height: 1.8; margin-bottom: 3rem; }
  .hero-actions { display: flex; gap: 1rem; align-items: center; }
  .btn-primary { background: var(--accent); color: #080A0E; font-family: var(--mono); font-size: 12px; font-weight: 500; letter-spacing: 0.1em; text-transform: uppercase; padding: 0.85rem 2rem; border-radius: 4px; text-decoration: none; transition: opacity 0.2s, transform 0.2s; }
  .btn-primary:hover { opacity: 0.85; transform: translateY(-1px); }
  .btn-secondary { font-family: var(--mono); font-size: 12px; color: var(--text-secondary); text-decoration: none; letter-spacing: 0.1em; text-transform: uppercase; display: flex; align-items: center; gap: 0.5rem; transition: color 0.2s; }
  .btn-secondary:hover { color: var(--text-primary); }
  .hero-stats { display: flex; gap: 3.5rem; margin-top: 5rem; padding-top: 2.5rem; border-top: 1px solid var(--border); position: relative; z-index: 1; }
  .stat-val { font-family: var(--display); font-size: 2.2rem; font-weight: 700; color: var(--text-primary); display: block; }
  .stat-label { font-family: var(--mono); font-size: 11px; color: var(--text-muted); letter-spacing: 0.1em; text-transform: uppercase; }

  section { padding: 7rem 4rem; position: relative; z-index: 1; }
  .section-label { font-family: var(--mono); font-size: 11px; color: var(--accent); letter-spacing: 0.2em; text-transform: uppercase; margin-bottom: 1rem; display: flex; align-items: center; gap: 0.75rem; }
  .section-label::after { content: ''; height: 1px; width: 40px; background: var(--border-accent); }
  .section-title { font-family: var(--display); font-size: clamp(2rem, 4vw, 3rem); font-weight: 700; letter-spacing: -0.02em; margin-bottom: 1rem; }
  .section-subtitle { color: var(--text-secondary); font-size: 15px; max-width: 500px; margin-bottom: 4rem; }

  /* SKILLS */
  #skills { background: var(--bg-card); border-top: 1px solid var(--border); border-bottom: 1px solid var(--border); }
  .skills-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); gap: 1.5px; background: var(--border); border: 1px solid var(--border); border-radius: 8px; overflow: hidden; }
  .skill-block { background: var(--bg-card); padding: 2rem; transition: background 0.2s; position: relative; }
  .skill-block:hover { background: var(--bg-glass); }
  .skill-block-title { font-family: var(--display); font-size: 1rem; font-weight: 600; margin-bottom: 0.75rem; }
  .skill-tags { display: flex; flex-wrap: wrap; gap: 0.4rem; }
  .tag { font-family: var(--mono); font-size: 11px; color: var(--text-secondary); background: rgba(255,255,255,0.04); border: 1px solid var(--border); padding: 0.25rem 0.65rem; border-radius: 3px; letter-spacing: 0.05em; }
  .tag.accent-tag { color: var(--accent); border-color: rgba(0,210,140,0.2); background: rgba(0,210,140,0.05); }

  /* PROJECTS GRID */
  .projects-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(340px, 1fr)); gap: 1.5rem; }
  .project-card { background: var(--bg-card); border: 1px solid var(--border); border-radius: 8px; padding: 2rem; position: relative; overflow: hidden; transition: border-color 0.25s, transform 0.25s; }
  .project-card:hover { border-color: rgba(255,255,255,0.12); transform: translateY(-3px); }
  .project-number { font-family: var(--mono); font-size: 11px; color: var(--text-muted); margin-bottom: 1.25rem; display: flex; justify-content: space-between; align-items: center; }
  .project-title { font-family: var(--display); font-size: 1.25rem; font-weight: 700; margin-bottom: 0.75rem; letter-spacing: -0.01em; }
  .project-desc { font-size: 14px; color: var(--text-secondary); line-height: 1.75; margin-bottom: 1.5rem; }
  .project-stack { display: flex; flex-wrap: wrap; gap: 0.4rem; margin-bottom: 1.5rem; }

  /* EXPERIENCE TIMELINE */
  .timeline { position: relative; padding-left: 2rem; }
  .timeline::before { content: ''; position: absolute; left: 0; top: 8px; bottom: 0; width: 1px; background: var(--border); }
  .timeline-item { position: relative; padding-bottom: 3.5rem; padding-left: 2rem; }
  .timeline-dot { position: absolute; left: -2.4rem; top: 8px; width: 8px; height: 8px; border-radius: 50%; background: var(--accent); box-shadow: 0 0 10px rgba(0,210,140,0.4); }
  .timeline-date { font-family: var(--mono); font-size: 11px; color: var(--text-muted); letter-spacing: 0.1em; text-transform: uppercase; margin-bottom: 0.5rem; }
  .timeline-role { font-family: var(--display); font-size: 1.2rem; font-weight: 700; margin-bottom: 0.25rem; }
  .timeline-company { font-family: var(--mono); font-size: 13px; color: var(--accent); margin-bottom: 1rem; }

  /* CONTACT */
  #contact { text-align: center; }
  .contact-wrapper { max-width: 640px; margin: 0 auto; }
  .contact-email { font-family: var(--display); font-size: clamp(1.5rem, 4vw, 2.5rem); font-weight: 700; color: var(--text-primary); text-decoration: none; display: inline-block; margin: 2rem 0; border-bottom: 2px solid var(--accent); padding-bottom: 0.25rem; transition: color 0.2s; word-break: break-all; }
  .contact-email:hover { color: var(--accent); }
  .socials { display: flex; justify-content: center; gap: 1.5rem; margin-top: 2rem; }
  .social-link { font-family: var(--mono); font-size: 11px; color: var(--text-muted); text-decoration: none; letter-spacing: 0.12em; text-transform: uppercase; transition: color 0.2s; display: flex; align-items: center; gap: 0.4rem; }
  .social-link:hover { color: var(--accent); }

  /* FOOTER */
  footer { padding: 2rem 4rem; border-top: 1px solid var(--border); display: flex; justify-content: space-between; align-items: center; }
  footer p { font-family: var(--mono); font-size: 11px; color: var(--text-muted); letter-spacing: 0.08em; }

  @media (max-width: 768px) {
    nav { padding: 1.25rem 1.5rem; }
    .nav-links { display: none; }
    .hero, section { padding-left: 1.5rem; padding-right: 1.5rem; }
    .hero-stats { gap: 2rem; flex-wrap: wrap; }
    footer { flex-direction: column; gap: 0.75rem; text-align: center; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a href="#" class="nav-logo">Chinedu Elekwa Promise</a>
  <ul class="nav-links">
    <li><a href="#skills">Skills</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#experience">Experience</a></li>
    <li><a href="#contact" class="nav-cta">Hire Me</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero" id="hero">
  <div class="hero-grid-bg"></div>
  <div class="hero-glow"></div>
  <div class="hero-glow-2"></div>
  <div class="hero-badge">Available for new opportunities</div>
  <h1 class="hero-name">Chinedu<br><span class="accent">Promise</span></h1>
  <p class="hero-title">Data Analyst & Aspiring Analytics Engineer</p>
  <p class="hero-desc">
    I turn raw data into actionable insights. Specializing in building scalable analytics pipelines, crafting executive-level dashboards, and finding signals in complex datasets.
  </p>
  <div class="hero-actions">
    <a href="#projects" class="btn-primary">View Projects →</a>
    <a href="#contact" class="btn-secondary">Get in touch ↗</a>
  </div>
  <div class="hero-stats">
    <div><span class="stat-val">5+</span><span class="stat-label">Years Experience</span></div>
    <div><span class="stat-val">20+</span><span class="stat-label">Projects Completed</span></div>
    <div><span class="stat-val">10M+</span><span class="stat-label">Rows Processed Daily</span></div>
    <div><span class="stat-val">4</span><span class="stat-label">Industries Served</span></div>
  </div>
</section>

<!-- SKILLS -->
<section id="skills">
  <div class="section-label">Technical Arsenal</div>
  <h2 class="section-title">What I Work With</h2>
  <p class="section-subtitle reveal">From ingestion to insight — every layer of the modern data stack.</p>
  <div class="skills-grid reveal">
    <div class="skill-block"><div class="skill-block-title">Data Modeling & Transformation</div>
      <div class="skill-tags"><span class="tag accent-tag">dbt</span><span class="tag accent-tag">SQL</span><span class="tag">Data Vault 2.0</span></div></div>
    <div class="skill-block"><div class="skill-block-title">Warehouses & Databases</div>
      <div class="skill-tags"><span class="tag accent-tag">BigQuery</span><span class="tag accent-tag">Snowflake
