<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Chinedu Elekwa Promise | Data Analyst</title>
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

  body {
    background: var(--bg);
    color: var(--text-primary);
    font-family: var(--sans);
    font-weight: 300;
    line-height: 1.7;
    overflow-x: hidden;
  }

  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 512 512' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 0;
  }

  /* NAV */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; justify-content: space-between; align-items: center;
    padding: 1.25rem 4rem;
    border-bottom: 1px solid var(--border);
    background: rgba(8,10,14,0.85);
    backdrop-filter: blur(20px);
  }
  .nav-logo { font-family: var(--mono); font-size: 13px; color: var(--accent); letter-spacing: 0.08em; text-decoration: none; }
  .nav-links { display: flex; gap: 2rem; list-style: none; }
  .nav-links a { font-family: var(--mono); font-size: 12px; color: var(--text-secondary); text-decoration: none; letter-spacing: 0.1em; text-transform: uppercase; transition: color 0.2s; }
  .nav-links a:hover { color: var(--accent); }
  .nav-cta { color: var(--accent) !important; border: 1px solid var(--border-accent); padding: 0.45rem 1rem; border-radius: 4px; transition: background 0.2s !important; }
  .nav-cta:hover { background: var(--accent-dim) !important; }

  .hero-photo-full {
  width: 350px;
  height: 350px;
  border-radius: 50%;
  border: 6px solid var(--accent);
  object-fit: cover;
  box-shadow: 0 0 50px rgba(34,197,94,0.5), 0 0 80px rgba(56,189,248,0.3);
  transition: transform 0.4s, box-shadow 0.4s;
}

.hero-photo-full:hover {
  transform: scale(1.05);
  box-shadow: 0 0 70px rgba(34,197,94,0.7), 0 0 100px rgba(56,189,248,0.5);
}

@media (max-width: 768px) {
  .hero-photo-full {
    width: 220px;
    height: 220px;
  }

  .hero-name {
    font-size: 2rem;
  }

  .hero-title {
    font-size: 1rem;
  }
}

  /* HERO */
  .hero { min-height: 100vh; display: flex; flex-direction: column; justify-content: center; padding: 10rem 4rem 6rem; position: relative; overflow: hidden; }
  .hero-grid-bg { position: absolute; inset: 0; background-image: linear-gradient(var(--border) 1px, transparent 1px), linear-gradient(90deg, var(--border) 1px, transparent 1px); background-size: 60px 60px; mask-image: radial-gradient(ellipse 80% 60% at 50% 50%, black 20%, transparent 80%); pointer-events: none; }
  .hero-glow { position: absolute; top: 20%; left: 10%; width: 700px; height: 500px; background: radial-gradient(ellipse, rgba(0,210,140,0.06) 0%, transparent 70%); pointer-events: none; }
  .hero-glow-2 { position: absolute; bottom: 10%; right: 5%; width: 500px; height: 400px; background: radial-gradient(ellipse, rgba(59,130,246,0.05) 0%, transparent 70%); pointer-events: none; }

  .hero-badge { font-family: var(--mono); font-size: 11px; color: var(--accent); letter-spacing: 0.15em; text-transform: uppercase; display: flex; align-items: center; gap: 0.6rem; margin-bottom: 1.8rem; }
  .hero-badge::before { content: ''; display: inline-block; width: 6px; height: 6px; border-radius: 50%; background: var(--accent); box-shadow: 0 0 8px var(--accent); animation: pulse 2s infinite; }
  @keyframes pulse { 0%, 100% { opacity: 1; } 50% { opacity: 0.4; } }

  .hero-name { font-family: var(--display); font-size: clamp(3.5rem, 8vw, 7.5rem); font-weight: 800; line-height: 0.95; letter-spacing: -0.02em; margin-bottom: 0.5rem; }
  .hero-name .accent { color: var(--accent); }
  .hero-title { font-family: var(--display); font-size: clamp(1.4rem, 3vw, 2.4rem); font-weight: 500; color: var(--text-secondary); margin-bottom: 2rem; letter-spacing: -0.01em; }
  .hero-desc { max-width: 520px; font-size: 15px; color: var(--text-secondary); line-height: 1.8; margin-bottom: 1.5rem; }

  .hero-badges { display: flex; flex-wrap: wrap; gap: 0.5rem; margin-bottom: 2.5rem; }
  .hero-pill { font-family: var(--mono); font-size: 11px; color: var(--text-secondary); border: 1px solid var(--border); padding: 0.3rem 0.8rem; border-radius: 20px; letter-spacing: 0.05em; }

  .hero-actions { display: flex; gap: 1rem; align-items: center; }
  .btn-primary { background: var(--accent); color: #080A0E; font-family: var(--mono); font-size: 12px; font-weight: 500; letter-spacing: 0.1em; text-transform: uppercase; padding: 0.85rem 2rem; border-radius: 4px; text-decoration: none; transition: opacity 0.2s, transform 0.2s; }
  .btn-primary:hover { opacity: 0.85; transform: translateY(-1px); }
  .btn-secondary { font-family: var(--mono); font-size: 12px; color: var(--text-secondary); text-decoration: none; letter-spacing: 0.1em; text-transform: uppercase; display: flex; align-items: center; gap: 0.5rem; transition: color 0.2s; }
  .btn-secondary:hover { color: var(--text-primary); }

  .hero-stats { display: flex; gap: 3.5rem; margin-top: 5rem; padding-top: 2.5rem; border-top: 1px solid var(--border); position: relative; z-index: 1; }
  .stat-val { font-family: var(--display); font-size: 2.2rem; font-weight: 700; color: var(--text-primary); display: block; }
  .stat-label { font-family: var(--mono); font-size: 11px; color: var(--text-muted); letter-spacing: 0.1em; text-transform: uppercase; }

.hero-name-wrapper {
  display: flex;
  align-items: center;
  gap: 1rem; /* space between photo and name */
  margin-bottom: 0.5rem;
}

.hero-photo {
  width: 80px;         /* adjust size as needed */
  height: 80px;
  border-radius: 50%;  /* makes it circular */
  object-fit: cover;   /* ensures it fills the circle */
  border: 2px solid var(--accent); /* optional accent border */
}

  /* SECTIONS */
  section { padding: 7rem 4rem; position: relative; z-index: 1; }
  .section-label { font-family: var(--mono); font-size: 11px; color: var(--accent); letter-spacing: 0.2em; text-transform: uppercase; margin-bottom: 1rem; display: flex; align-items: center; gap: 0.75rem; }
  .section-label::after { content: ''; height: 1px; width: 40px; background: var(--border-accent); }
  .section-title { font-family: var(--display); font-size: clamp(2rem, 4vw, 3rem); font-weight: 700; letter-spacing: -0.02em; margin-bottom: 1rem; }
  .section-subtitle { color: var(--text-secondary); font-size: 15px; max-width: 500px; margin-bottom: 4rem; }

  /* TAGS */
  .tag { font-family: var(--mono); font-size: 11px; color: var(--text-secondary); background: rgba(255,255,255,0.04); border: 1px solid var(--border); padding: 0.25rem 0.65rem; border-radius: 3px; letter-spacing: 0.05em; }
  .tag.accent-tag { color: var(--accent); border-color: rgba(0,210,140,0.2); background: rgba(0,210,140,0.05); }
  .tag.blue-tag { color: var(--accent2); border-color: rgba(59,130,246,0.2); background: rgba(59,130,246,0.05); }

  /* SKILLS */
  #skills { background: var(--bg-card); border-top: 1px solid var(--border); border-bottom: 1px solid var(--border); }
  .skills-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); gap: 1.5px; background: var(--border); border: 1px solid var(--border); border-radius: 8px; overflow: hidden; }
  .skill-block { background: var(--bg-card); padding: 2rem; transition: background 0.2s; }
  .skill-block:hover { background: var(--bg-glass); }
  .skill-block-icon { font-size: 22px; margin-bottom: 1rem; }
  .skill-block-title { font-family: var(--display); font-size: 1rem; font-weight: 600; margin-bottom: 0.75rem; }
  .skill-tags { display: flex; flex-wrap: wrap; gap: 0.4rem; }

  /* PROJECTS */
  .projects-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 1.5rem; }
  .project-card { background: var(--bg-card); border: 1px solid var(--border); border-radius: 8px; overflow: hidden; position: relative; transition: border-color 0.25s, transform 0.25s; }
  .project-card::before { content: ''; position: absolute; top: 0; left: 0; right: 0; height: 2px; background: linear-gradient(90deg, var(--accent), var(--accent2)); opacity: 0; transition: opacity 0.25s; }
  .project-card:hover { border-color: rgba(255,255,255,0.12); transform: translateY(-3px); }
  .project-card:hover::before { opacity: 1; }

  .project-img-placeholder { width: 100%; height: 180px; background: rgba(255,255,255,0.02); border-bottom: 1px solid var(--border); display: flex; align-items: center; justify-content: center; font-family: var(--mono); font-size: 11px; color: var(--text-muted); letter-spacing: 0.1em; }
  .project-body { padding: 1.75rem; }
  .project-number { font-family: var(--mono); font-size: 11px; color: var(--text-muted); margin-bottom: 1rem; display: flex; justify-content: space-between; align-items: center; }
  .project-type { font-family: var(--mono); font-size: 10px; color: var(--accent); border: 1px solid rgba(0,210,140,0.25); padding: 0.2rem 0.6rem; border-radius: 2px; letter-spacing: 0.08em; }
  .project-title { font-family: var(--display); font-size: 1.2rem; font-weight: 700; margin-bottom: 0.6rem; letter-spacing: -0.01em; }
  .project-desc { font-size: 14px; color: var(--text-secondary); line-height: 1.75; margin-bottom: 1.25rem; }
  .project-stack { display: flex; flex-wrap: wrap; gap: 0.4rem; margin-bottom: 1.25rem; }
  .project-link { font-family: var(--mono); font-size: 11px; color: var(--accent2); text-decoration: none; letter-spacing: 0.08em; display: inline-flex; align-items: center; gap: 0.4rem; transition: color 0.2s; text-transform: uppercase; border: 1px solid rgba(59,130,246,0.3); padding: 0.45rem 0.9rem; border-radius: 4px; }
  .project-link:hover { color: var(--accent); border-color: var(--border-accent); }

  /* TIMELINE */
  .timeline { position: relative; padding-left: 2rem; }
  .timeline::before { content: ''; position: absolute; left: 0; top: 8px; bottom: 0; width: 1px; background: var(--border); }
  .timeline-item { position: relative; padding-bottom: 3.5rem; padding-left: 2rem; }
  .timeline-item:last-child { padding-bottom: 0; }
  .timeline-dot { position: absolute; left: -2.4rem; top: 8px; width: 8px; height: 8px; border-radius: 50%; background: var(--accent); box-shadow: 0 0 10px rgba(0,210,140,0.4); }
  .timeline-date { font-family: var(--mono); font-size: 11px; color: var(--text-muted); letter-spacing: 0.1em; text-transform: uppercase; margin-bottom: 0.5rem; }
  .timeline-role { font-family: var(--display); font-size: 1.2rem; font-weight: 700; margin-bottom: 0.25rem; }
  .timeline-company { font-family: var(--mono); font-size: 13px; color: var(--accent); margin-bottom: 1rem; }
  .timeline-bullets { list-style: none; }
  .timeline-bullets li { font-size: 14px; color: var(--text-secondary); padding: 0.3rem 0 0.3rem 1.2rem; position: relative; }
  .timeline-bullets li::before { content: '—'; position: absolute; left: 0; color: var(--text-muted); font-family: var(--mono); font-size: 12px; }

  /* CERTIFICATIONS */
  #certifications { background: var(--bg-card); border-top: 1px solid var(--border); border-bottom: 1px solid var(--border); }
  .cert-group-label { font-family: var(--mono); font-size: 11px; letter-spacing: 0.15em; text-transform: uppercase; margin-bottom: 1.5rem; padding-bottom: 0.75rem; border-bottom: 1px solid var(--border); }
  .cert-group-label.green { color: var(--accent); }
  .cert-group-label.blue { color: var(--accent2); }
  .cert-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 1.25rem; margin-bottom: 3.5rem; }
  .cert-card { background: var(--bg); border: 1px solid var(--border); border-radius: 8px; overflow: hidden; transition: transform 0.25s, border-color 0.25s; }
  .cert-card:hover { transform: translateY(-4px); border-color: rgba(255,255,255,0.12); }
  .cert-stripe { height: 3px; background: linear-gradient(90deg, var(--accent), var(--accent2)); }
  .cert-stripe.blue { background: linear-gradient(90deg, var(--accent2), #8b5cf6); }
  .cert-body { padding: 1.5rem; }
  .cert-icon { font-size: 22px; margin-bottom: 1rem; }
  .cert-title { font-family: var(--display); font-size: 0.9rem; font-weight: 700; margin-bottom: 0.5rem; line-height: 1.35; }
  .cert-issuer { font-family: var(--mono); font-size: 11px; color: var(--accent); letter-spacing: 0.08em; }
  .cert-issuer.blue { color: var(--accent2); }

  /* RECOGNITIONS */
  .rec-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 1.5rem; }
  .rec-card { background: var(--bg-card); border: 1px solid var(--border); border-radius: 8px; padding: 2rem; position: relative; transition: transform 0.25s, border-color 0.25s; overflow: hidden; }
  .rec-card::before { content: ''; position: absolute; top: 0; left: 0; right: 0; height: 2px; background: linear-gradient(90deg, var(--accent), var(--accent2)); }
  .rec-card:hover { transform: translateY(-3px); border-color: rgba(255,255,255,0.12); }
  .rec-icon { font-size: 28px; margin-bottom: 1rem; }
  .rec-title { font-family: var(--display); font-size: 1.05rem; font-weight: 700; margin-bottom: 0.6rem; }
  .rec-desc { font-size: 14px; color: var(--text-secondary); line-height: 1.7; }

  /* CONTACT */
  #contact { text-align: center; }
  .contact-wrapper { max-width: 640px; margin: 0 auto; }
  .contact-email { font-family: var(--display); font-size: clamp(1.4rem, 4vw, 2.2rem); font-weight: 700; color: var(--text-primary); text-decoration: none; display: inline-block; margin: 2rem 0; border-bottom: 2px solid var(--accent); padding-bottom: 0.25rem; transition: color 0.2s; word-break: break-all; }
  .contact-email:hover { color: var(--accent); }
  .socials { display: flex; justify-content: center; gap: 1rem; margin-top: 2rem; flex-wrap: wrap; }
  .social-link { font-family: var(--mono); font-size: 11px; color: var(--text-muted); text-decoration: none; letter-spacing: 0.1em; text-transform: uppercase; transition: color 0.2s; display: flex; align-items: center; gap: 0.4rem; border: 1px solid var(--border); padding: 0.6rem 1.2rem; border-radius: 4px; }
  .social-link:hover { color: var(--accent); border-color: var(--border-accent); }

  /* FOOTER */
  footer { padding: 2rem 4rem; border-top: 1px solid var(--border); display: flex; justify-content: space-between; align-items: center; }
  footer p { font-family: var(--mono); font-size: 11px; color: var(--text-muted); letter-spacing: 0.08em; }

  /* REVEAL */
  .reveal { opacity: 0; transform: translateY(24px); transition: opacity 0.6s ease, transform 0.6s ease; }
  .reveal.visible { opacity: 1; transform: none; }

  /* RESPONSIVE */
  @media (max-width: 768px) {
    nav { padding: 1.25rem 1.5rem; }
    .nav-links { display: none; }
    .hero, section { padding-left: 1.5rem; padding-right: 1.5rem; }
    .hero-stats { gap: 2rem; flex-wrap: wrap; }
    footer { flex-direction: column; gap: 0.75rem; text-align: center; padding: 1.5rem; }
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
</nav>

<!-- HERO -->
<section class="hero" id="hero" style="position: relative; display: flex; align-items: center; justify-content: center; height: 100vh; overflow: hidden; text-align: center; color: white;">

  <!-- BACKGROUND EFFECTS -->
  <div class="hero-glow" style="position: absolute; width: 100%; height: 100%; background: radial-gradient(circle, rgba(34,197,94,0.2) 0%, transparent 70%); top:0; left:0; z-index:1;"></div>
  <div class="hero-glow-2" style="position: absolute; width: 100%; height: 100%; background: radial-gradient(circle, rgba(56,189,248,0.15) 0%, transparent 70%); top:0; left:0; z-index:2;"></div>

  <!-- HERO CONTENT -->
  <div style="position: relative; z-index: 3; display: flex; flex-direction: column; align-items: center; gap: 1.5rem;">

    <!-- BIG PHOTO -->
    <div style="position: relative;">
      <img src="images/My-photo.jpg" alt="Chinedu Elekwa" class="hero-photo-full">
    </div>

    <!-- NAME + TITLE OVER PHOTO -->
    <h1 class="hero-name" style="font-size: 3rem; margin-top: 1rem;">
      Chinedu <span class="accent">Elekwa</span>
    </h1>
    <p class="hero-title" style="font-size: 1.3rem; max-width: 600px; line-height: 1.5;">
      Data Analyst & Aspiring Analytics Engineer  
      <br>Turning raw data into insights that drive impact.
    </p>

    <!-- BADGES -->
    <div class="hero-badges" style="display: flex; flex-wrap: wrap; gap: 0.75rem; justify-content: center; margin-top: 1rem;">
      <span class="hero-pill">SQL</span>
      <span class="hero-pill">Python</span>
      <span class="hero-pill">Power BI</span>
      <span class="hero-pill">Looker Studio</span>
      <span class="hero-pill">Data Modeling</span>
      <span class="hero-pill">SAP</span>
      <span class="hero-pill">Power Point</span>
    </div>

    <!-- ACTION BUTTONS -->
    <div class="hero-actions" style="display: flex; gap: 1rem; margin-top: 2rem;">
      <a href="#projects" class="btn-primary">Explore My Work →</a>
      <a href="#contact" class="btn-secondary">Get in Touch ↗</a>
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
        <div class="project-desc">Designed and deployed a data collection and analytics system at Frutta Juice & Services Ltd tracking output, downtime, waste, and material usage — boosting analytics efficiency to 95% and enabling real-time production decisions.</div>
        <div class="project-stack">
          <span class="tag accent-tag">Google Sheets</span><span class="tag accent-tag">Google Forms</span>
          <span class="tag">SAP</span><span class="tag">MS PowerPoint</span>
        </div>
        <a href="https://nedupelekwa.github.io" target="_blank" class="project-link">View Portfolio ↗</a>
      </div>
    </div>

    <div class="project-card reveal">
  <img src="images/Business-dashboard.jpg" alt="Business Dashboard" class="project-img">
      <div class="project-body">
        <div class="project-number"><span>02</span><span class="project-type">Business Intelligence</span></div>
        <div class="project-title">POWERBI-BUSINESS-DASHBOARD</div>
        <div class="project-desc">Key finding: +24.5 % YoY Sales from 2021 to 2022</div>
        <div class="project-stack">
          <span class="tag accent-tag">Power BI</span><span class="tag accent-tag">DAX</span>
          <span class="tag">Power Query</span><span class="tag">MS Excel</span>
        </div>
        <a href="https://github.com/Nedupelekwa/POWERBI-BUSINESS-DASHBOARD" target="_blank" class="project-link">View Portfolio ↗</a>
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
    <div class="cert-card">
      <div class="cert-stripe"></div>
      <div class="cert-body">
        <div class="cert-icon">☁</div>
        <div class="cert-title">Google Cloud Data Analyst Certificate</div>
        <div class="cert-issuer">Google Cloud</div>
      </div>
    </div>
    <div class="cert-card">
      <div class="cert-stripe"></div>
      <div class="cert-body">
        <div class="cert-icon">◈</div>
        <div class="cert-title">Data Analytics, Python Programming & Data Science</div>
        <div class="cert-issuer">ALX Africa</div>
      </div>
    </div>
    <div class="cert-card">
      <div class="cert-stripe"></div>
      <div class="cert-body">
        <div class="cert-icon">◎</div>
        <div class="cert-title">Associate Data Analyst Certificate</div>
        <div class="cert-issuer">DataCamp</div>
      </div>
    </div>
    <div class="cert-card">
      <div class="cert-stripe"></div>
      <div class="cert-body">
        <div class="cert-icon">◯</div>
        <div class="cert-title">Data Literacy Certificate</div>
        <div class="cert-issuer">DataCamp</div>
      </div>
    </div>
    <div class="cert-card">
      <div class="cert-stripe"></div>
      <div class="cert-body">
        <div class="cert-icon">▣</div>
        <div class="cert-title">Google Workspace — Calendar, Drive, Docs, Sheets, Slides</div>
        <div class="cert-issuer">Google via Coursera</div>
      </div>
    </div>
  </div>

  <div class="cert-group-label blue reveal">Professional & Soft Skills</div>
  <div class="cert-grid reveal">
    <div class="cert-card">
      <div class="cert-stripe blue"></div>
      <div class="cert-body">
        <div class="cert-icon">◫</div>
        <div class="cert-title">ALX Professional Foundations</div>
        <div class="cert-issuer blue">ALX Africa</div>
      </div>
    </div>
    <div class="cert-card">
      <div class="cert-stripe blue"></div>
      <div class="cert-body">
        <div class="cert-icon">⬡</div>
        <div class="cert-title">Jobberman Soft Skills Training</div>
        <div class="cert-issuer blue">Jobberman · 2021</div>
      </div>
    </div>
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
    <p class="section-subtitle reveal" style="margin: 0 auto 1rem; text-align: center;">
      Whether it's a full-time role, a freelance project, or just a conversation about data — reach out.
    </p>
    <a href="mailto:chinedupelekwa@gmail.com" class="contact-email reveal">chinedupelekwa@gmail.com</a>
    <div class="socials reveal">
      <a href="https://www.linkedin.com/in/chinedu-elekwa/" target="_blank" class="social-link">↗ LinkedIn</a>
      <a href="https://nedupelekwa.github.io" target="_blank" class="social-link">↗ GitHub Portfolio</a>
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
        setTimeout(() => e.target.classList.add('visible'), i * 80);
        observer.unobserve(e.target);
      }
    });
  }, { threshold: 0.1 });
  reveals.forEach(el => observer.observe(el));
</script>
</body>
</html>
