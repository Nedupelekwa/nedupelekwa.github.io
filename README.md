<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Chinedu Elekwa — Data Analyst</title>
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

  /* NOISE OVERLAY */
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
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1.25rem 4rem;
    border-bottom: 1px solid var(--border);
    background: rgba(8,10,14,0.85);
    backdrop-filter: blur(20px);
  }

  .nav-logo {
    font-family: var(--mono);
    font-size: 13px;
    color: var(--accent);
    letter-spacing: 0.08em;
    text-decoration: none;
  }

  .nav-links {
    display: flex;
    gap: 2.5rem;
    list-style: none;
  }

  .nav-links a {
    font-family: var(--mono);
    font-size: 12px;
    color: var(--text-secondary);
    text-decoration: none;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    transition: color 0.2s;
  }

  .nav-links a:hover { color: var(--accent); }

  .nav-cta {
    font-family: var(--mono);
    font-size: 12px;
    color: var(--accent) !important;
    border: 1px solid var(--border-accent);
    padding: 0.45rem 1rem;
    border-radius: 4px;
    transition: background 0.2s !important;
  }

  .nav-cta:hover { background: var(--accent-dim) !important; }

  /* HERO */
  .hero {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 10rem 4rem 6rem;
    position: relative;
    overflow: hidden;
  }

  .hero-grid-bg {
    position: absolute;
    inset: 0;
    background-image:
      linear-gradient(var(--border) 1px, transparent 1px),
      linear-gradient(90deg, var(--border) 1px, transparent 1px);
    background-size: 60px 60px;
    mask-image: radial-gradient(ellipse 80% 60% at 50% 50%, black 20%, transparent 80%);
    pointer-events: none;
  }

  .hero-glow {
    position: absolute;
    top: 20%; left: 10%;
    width: 700px; height: 500px;
    background: radial-gradient(ellipse, rgba(0,210,140,0.06) 0%, transparent 70%);
    pointer-events: none;
  }

  .hero-glow-2 {
    position: absolute;
    bottom: 10%; right: 5%;
    width: 500px; height: 400px;
    background: radial-gradient(ellipse, rgba(59,130,246,0.05) 0%, transparent 70%);
    pointer-events: none;
  }

  .hero-badge {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--accent);
    letter-spacing: 0.15em;
    text-transform: uppercase;
    display: flex;
    align-items: center;
    gap: 0.6rem;
    margin-bottom: 1.8rem;
  }

  .hero-badge::before {
    content: '';
    display: inline-block;
    width: 6px; height: 6px;
    border-radius: 50%;
    background: var(--accent);
    box-shadow: 0 0 8px var(--accent);
    animation: pulse 2s infinite;
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.4; }
  }

  .hero-name {
    font-family: var(--display);
    font-size: clamp(3.5rem, 8vw, 7.5rem);
    font-weight: 800;
    line-height: 0.95;
    letter-spacing: -0.02em;
    margin-bottom: 0.5rem;
  }

  .hero-name .accent { color: var(--accent); }

  .hero-title {
    font-family: var(--display);
    font-size: clamp(1.4rem, 3vw, 2.4rem);
    font-weight: 500;
    color: var(--text-secondary);
    margin-bottom: 2rem;
    letter-spacing: -0.01em;
  }

  .hero-desc {
    max-width: 520px;
    font-size: 15px;
    color: var(--text-secondary);
    line-height: 1.8;
    margin-bottom: 3rem;
  }

  .hero-actions {
    display: flex;
    gap: 1rem;
    align-items: center;
  }

  .btn-primary {
    background: var(--accent);
    color: #080A0E;
    font-family: var(--mono);
    font-size: 12px;
    font-weight: 500;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    padding: 0.85rem 2rem;
    border-radius: 4px;
    text-decoration: none;
    transition: opacity 0.2s, transform 0.2s;
  }

  .btn-primary:hover { opacity: 0.85; transform: translateY(-1px); }

  .btn-secondary {
    font-family: var(--mono);
    font-size: 12px;
    color: var(--text-secondary);
    text-decoration: none;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    display: flex;
    align-items: center;
    gap: 0.5rem;
    transition: color 0.2s;
  }

  .btn-secondary:hover { color: var(--text-primary); }

  .hero-stats {
    display: flex;
    gap: 3.5rem;
    margin-top: 5rem;
    padding-top: 2.5rem;
    border-top: 1px solid var(--border);
    position: relative;
    z-index: 1;
  }

  .stat-val {
    font-family: var(--display);
    font-size: 2.2rem;
    font-weight: 700;
    color: var(--text-primary);
    display: block;
  }

  .stat-label {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--text-muted);
    letter-spacing: 0.1em;
    text-transform: uppercase;
  }

  /* SECTION LAYOUT */
  section {
    padding: 7rem 4rem;
    position: relative;
    z-index: 1;
  }

  .section-label {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--accent);
    letter-spacing: 0.2em;
    text-transform: uppercase;
    margin-bottom: 1rem;
    display: flex;
    align-items: center;
    gap: 0.75rem;
  }

  .section-label::after {
    content: '';
    height: 1px;
    width: 40px;
    background: var(--border-accent);
  }

  .section-title {
    font-family: var(--display);
    font-size: clamp(2rem, 4vw, 3rem);
    font-weight: 700;
    letter-spacing: -0.02em;
    margin-bottom: 1rem;
  }

  .section-subtitle {
    color: var(--text-secondary);
    font-size: 15px;
    max-width: 500px;
    margin-bottom: 4rem;
  }

  /* SKILLS */
  #skills { background: var(--bg-card); border-top: 1px solid var(--border); border-bottom: 1px solid var(--border); }

  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
    gap: 1.5px;
    background: var(--border);
    border: 1px solid var(--border);
    border-radius: 8px;
    overflow: hidden;
  }

  .skill-block {
    background: var(--bg-card);
    padding: 2rem;
    transition: background 0.2s;
    position: relative;
  }

  .skill-block:hover { background: var(--bg-glass); }

  .skill-block-icon {
    font-size: 22px;
    margin-bottom: 1rem;
  }

  .skill-block-title {
    font-family: var(--display);
    font-size: 1rem;
    font-weight: 600;
    margin-bottom: 0.75rem;
  }

  .skill-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 0.4rem;
  }

  .tag {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--text-secondary);
    background: rgba(255,255,255,0.04);
    border: 1px solid var(--border);
    padding: 0.25rem 0.65rem;
    border-radius: 3px;
    letter-spacing: 0.05em;
  }

  .tag.accent-tag {
    color: var(--accent);
    border-color: rgba(0,210,140,0.2);
    background: rgba(0,210,140,0.05);
  }

  /* PROJECTS */
  .projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(340px, 1fr));
    gap: 1.5rem;
  }

  .project-card {
    background: var(--bg-card);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 2rem;
    position: relative;
    overflow: hidden;
    transition: border-color 0.25s, transform 0.25s;
    cursor: default;
  }

  .project-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent), var(--accent2));
    opacity: 0;
    transition: opacity 0.25s;
  }

  .project-card:hover {
    border-color: rgba(255,255,255,0.12);
    transform: translateY(-3px);
  }

  .project-card:hover::before { opacity: 1; }

  .project-number {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--text-muted);
    margin-bottom: 1.25rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .project-type {
    font-family: var(--mono);
    font-size: 10px;
    color: var(--accent);
    border: 1px solid rgba(0,210,140,0.25);
    padding: 0.2rem 0.6rem;
    border-radius: 2px;
    letter-spacing: 0.08em;
  }

  .project-title {
    font-family: var(--display);
    font-size: 1.25rem;
    font-weight: 700;
    margin-bottom: 0.75rem;
    letter-spacing: -0.01em;
  }

  .project-desc {
    font-size: 14px;
    color: var(--text-secondary);
    line-height: 1.75;
    margin-bottom: 1.5rem;
  }

  .project-stack {
    display: flex;
    flex-wrap: wrap;
    gap: 0.4rem;
    margin-bottom: 1.5rem;
  }

  .project-link {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--text-secondary);
    text-decoration: none;
    letter-spacing: 0.08em;
    display: inline-flex;
    align-items: center;
    gap: 0.4rem;
    transition: color 0.2s;
    text-transform: uppercase;
  }

  .project-link:hover { color: var(--accent); }

  /* EXPERIENCE TIMELINE */
  .timeline {
    position: relative;
    padding-left: 2rem;
  }

  .timeline::before {
    content: '';
    position: absolute;
    left: 0; top: 8px; bottom: 0;
    width: 1px;
    background: var(--border);
  }

  .timeline-item {
    position: relative;
    padding-bottom: 3.5rem;
    padding-left: 2rem;
  }

  .timeline-item:last-child { padding-bottom: 0; }

  .timeline-dot {
    position: absolute;
    left: -2.4rem;
    top: 8px;
    width: 8px; height: 8px;
    border-radius: 50%;
    background: var(--accent);
    box-shadow: 0 0 10px rgba(0,210,140,0.4);
  }

  .timeline-date {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--text-muted);
    letter-spacing: 0.1em;
    text-transform: uppercase;
    margin-bottom: 0.5rem;
  }

  .timeline-role {
    font-family: var(--display);
    font-size: 1.2rem;
    font-weight: 700;
    margin-bottom: 0.25rem;
  }

  .timeline-company {
    font-family: var(--mono);
    font-size: 13px;
    color: var(--accent);
    margin-bottom: 1rem;
  }

  .timeline-bullets {
    list-style: none;
    padding: 0;
  }

  .timeline-bullets li {
    font-size: 14px;
    color: var(--text-secondary);
    padding: 0.3rem 0;
    padding-left: 1.2rem;
    position: relative;
  }

  .timeline-bullets li::before {
    content: '—';
    position: absolute;
    left: 0;
    color: var(--text-muted);
    font-family: var(--mono);
    font-size: 12px;
  }

  /* CONTACT */
  #contact { text-align: center; }

  .contact-wrapper {
    max-width: 640px;
    margin: 0 auto;
  }

  .contact-email {
    font-family: var(--display);
    font-size: clamp(1.5rem, 4vw, 2.5rem);
    font-weight: 700;
    color: var(--text-primary);
    text-decoration: none;
    display: inline-block;
    margin: 2rem 0;
    border-bottom: 2px solid var(--accent);
    padding-bottom: 0.25rem;
    transition: color 0.2s;
    word-break: break-all;
  }

  .contact-email:hover { color: var(--accent); }

  .socials {
    display: flex;
    justify-content: center;
    gap: 1.5rem;
    margin-top: 2rem;
  }

  .social-link {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--text-muted);
    text-decoration: none;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    transition: color 0.2s;
    display: flex;
    align-items: center;
    gap: 0.4rem;
  }

  .social-link:hover { color: var(--accent); }

  /* FOOTER */
  footer {
    padding: 2rem 4rem;
    border-top: 1px solid var(--border);
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  footer p {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--text-muted);
    letter-spacing: 0.08em;
  }

  /* SCROLL ANIMATIONS */
  .reveal {
    opacity: 0;
    transform: translateY(24px);
    transition: opacity 0.6s ease, transform 0.6s ease;
  }

  .reveal.visible {
    opacity: 1;
    transform: none;
  }

  /* RESPONSIVE */
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
  <a href="#" class="nav-logo">[ chinedu.elekwa ]</a>
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
  <div class="hero-badge">Open to new opportunities · Lagos, Nigeria</div>
  <h1 class="hero-name">Chinedu<br><span class="accent">Elekwa</span></h1>
  <p class="hero-title">Data Analyst · FMCG & EdTech</p>
  <p class="hero-desc">
    I bring the precision of a mathematician, the clarity of an educator, and the impact-focus 
    of a business analyst to every problem I solve. From production floors to executive dashboards — 
    I transform raw data into decisions that move organisations forward.
  </p>
  <div class="hero-actions">
    <a href="#projects" class="btn-primary">View Projects →</a>
    <a href="#contact" class="btn-secondary">Get in touch ↗</a>
  </div>
  <div class="hero-stats">
    <div>
      <span class="stat-val">5+</span>
      <span class="stat-label">Years in Data & Analytics</span>
    </div>
    <div>
      <span class="stat-val">95%</span>
      <span class="stat-label">Data Collection Efficiency Gained</span>
    </div>
    <div>
      <span class="stat-val">4+</span>
      <span class="stat-label">Certifications Earned</span>
    </div>
    <div>
      <span class="stat-val">100+</span>
      <span class="stat-label">Analysts Mentored via ALX</span>
    </div>
  </div>
</section>

<!-- SKILLS -->
<section id="skills">
  <div class="section-label">Technical Arsenal</div>
  <h2 class="section-title">What I Work With</h2>
  <p class="section-subtitle reveal">From ingestion to insight — every layer of the modern data stack.</p>

  <div class="skills-grid reveal">
    <div class="skill-block">
      <div class="skill-block-icon">⬡</div>
      <div class="skill-block-title">Data Modeling & Transformation</div>
      <div class="skill-tags">
        <span class="tag accent-tag">dbt</span>
        <span class="tag accent-tag">SQL</span>
        <span class="tag">Data Vault 2.0</span>
        <span class="tag">Dimensional Modeling</span>
        <span class="tag">Star Schema</span>
      </div>
    </div>
    <div class="skill-block">
      <div class="skill-block-icon">◈</div>
      <div class="skill-block-title">Warehouses & Databases</div>
      <div class="skill-tags">
        <span class="tag accent-tag">BigQuery</span>
        <span class="tag accent-tag">Snowflake</span>
        <span class="tag">Redshift</span>
        <span class="tag">PostgreSQL</span>
        <span class="tag">DuckDB</span>
      </div>
    </div>
    <div class="skill-block">
      <div class="skill-block-icon">▣</div>
      <div class="skill-block-title">Orchestration & Pipelines</div>
      <div class="skill-tags">
        <span class="tag accent-tag">Apache Airflow</span>
        <span class="tag">Prefect</span>
        <span class="tag">Fivetran</span>
        <span class="tag">Airbyte</span>
        <span class="tag">dlt</span>
      </div>
    </div>
    <div class="skill-block">
      <div class="skill-block-icon">◎</div>
      <div class="skill-block-title">Visualization & BI</div>
      <div class="skill-tags">
        <span class="tag accent-tag">Looker</span>
        <span class="tag accent-tag">Tableau</span>
        <span class="tag">Power BI</span>
        <span class="tag">Metabase</span>
        <span class="tag">Evidence</span>
      </div>
    </div>
    <div class="skill-block">
      <div class="skill-block-icon">◯</div>
      <div class="skill-block-title">Programming & Analytics</div>
      <div class="skill-tags">
        <span class="tag accent-tag">Python</span>
        <span class="tag accent-tag">pandas</span>
        <span class="tag">PySpark</span>
        <span class="tag">R</span>
        <span class="tag">Jupyter</span>
        <span class="tag">Polars</span>
      </div>
    </div>
    <div class="skill-block">
      <div class="skill-block-icon">◫</div>
      <div class="skill-block-title">Infrastructure & DevOps</div>
      <div class="skill-tags">
        <span class="tag">Git</span>
        <span class="tag">Docker</span>
        <span class="tag">Terraform</span>
        <span class="tag">GitHub Actions</span>
        <span class="tag">GCP</span>
        <span class="tag">AWS</span>
      </div>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section id="projects">
  <div class="section-label">Selected Work</div>
  <h2 class="section-title">Projects</h2>
  <p class="section-subtitle reveal">A selection of analytics engineering and data analysis projects.</p>

  <div class="projects-grid">
    <div class="project-card reveal">
      <div class="project-number">
        <span>01</span>
        <span class="project-type">Analytics Engineering</span>
      </div>
      <div class="project-title">Revenue Attribution Pipeline</div>
      <div class="project-desc">
        Built a multi-touch attribution model processing 5M+ daily events. Reduced reporting lag from 24 hours to 15 minutes, enabling real-time campaign optimization for a $50M annual ad budget.
      </div>
      <div class="project-stack">
        <span class="tag accent-tag">dbt</span>
        <span class="tag accent-tag">BigQuery</span>
        <span class="tag">Airflow</span>
        <span class="tag">Looker</span>
      </div>
      <a href="#" class="project-link">View Case Study →</a>
    </div>

    <div class="project-card reveal">
      <div class="project-number">
        <span>02</span>
        <span class="project-type">Data Analysis</span>
      </div>
      <div class="project-title">Customer Churn Prediction Dashboard</div>
      <div class="project-desc">
        Designed an end-to-end analytics layer on top of an ML churn model. Created executive dashboards that visualized at-risk cohorts and resulted in a 12% reduction in monthly churn.
      </div>
      <div class="project-stack">
        <span class="tag accent-tag">Python</span>
        <span class="tag accent-tag">Snowflake</span>
        <span class="tag">Tableau</span>
        <span class="tag">scikit-learn</span>
      </div>
      <a href="#" class="project-link">View Case Study →</a>
    </div>

    <div class="project-card reveal">
      <div class="project-number">
        <span>03</span>
        <span class="project-type">Data Engineering</span>
      </div>
      <div class="project-title">ELT Data Platform Migration</div>
      <div class="project-desc">
        Led migration of a legacy ETL system to a modern ELT stack. Re-modeled 200+ tables in dbt, introduced CI/CD for data, and cut infrastructure costs by 40%.
      </div>
      <div class="project-stack">
        <span class="tag accent-tag">dbt</span>
        <span class="tag accent-tag">Fivetran</span>
        <span class="tag">Redshift → Snowflake</span>
        <span class="tag">GitHub Actions</span>
      </div>
      <a href="#" class="project-link">View Case Study →</a>
    </div>

    <div class="project-card reveal">
      <div class="project-number">
        <span>04</span>
        <span class="project-type">Business Intelligence</span>
      </div>
      <div class="project-title">Self-Serve Analytics Platform</div>
      <div class="project-desc">
        Built a governed self-serve layer in Looker allowing 150+ non-technical stakeholders to run their own analyses, reducing ad-hoc SQL requests to the data team by 70%.
      </div>
      <div class="project-stack">
        <span class="tag accent-tag">Looker</span>
        <span class="tag accent-tag">LookML</span>
        <span class="tag">BigQuery</span>
        <span class="tag">dbt</span>
      </div>
      <a href="#" class="project-link">View Case Study →</a>
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
      <div class="timeline-date">2022 — Present</div>
      <div class="timeline-role">Senior Analytics Engineer</div>
      <div class="timeline-company">Acme Corp · Full-time</div>
      <ul class="timeline-bullets">
        <li>Owns and maintains the core dbt project with 300+ models powering company-wide reporting</li>
        <li>Reduced data freshness SLA from 6 hours to 45 minutes for critical revenue metrics</li>
        <li>Mentors 3 junior analysts on SQL, dbt, and data modeling best practices</li>
      </ul>
    </div>
    <div class="timeline-item">
      <div class="timeline-dot"></div>
      <div class="timeline-date">2020 — 2022</div>
      <div class="timeline-role">Data Analyst</div>
      <div class="timeline-company">Nexus Analytics · Full-time</div>
      <ul class="timeline-bullets">
        <li>Built weekly executive reporting suite covering KPIs across marketing, product, and finance</li>
        <li>Collaborated with product team on A/B test analysis that drove 8% uplift in activation</li>
        <li>Introduced dbt to the team, replacing a tangle of unversioned SQL scripts</li>
      </ul>
    </div>
    <div class="timeline-item">
      <div class="timeline-dot" style="background: var(--text-muted); box-shadow: none;"></div>
      <div class="timeline-date">2018 — 2020</div>
      <div class="timeline-role">Business Intelligence Analyst</div>
      <div class="timeline-company">DataFlow Ltd · Full-time</div>
      <ul class="timeline-bullets">
        <li>Maintained Tableau dashboards and ad-hoc SQL analyses for sales leadership</li>
        <li>Automated monthly reporting workflows, saving 20+ analyst-hours per month</li>
      </ul>
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
    <a href="/cdn-cgi/l/email-protection#40392f353200252d21292c6e232f2d" class="contact-email reveal"><span class="__cf_email__" data-cfemail="fc8593898ebc99919d9590d29f9391">[email&#160;protected]</span></a>
    <div class="socials reveal">
      <a href="#" class="social-link">↗ LinkedIn</a>
      <a href="#" class="social-link">↗ GitHub</a>
      <a href="#" class="social-link">↗ Resume PDF</a>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <p>© 2025 Your Name. All rights reserved.</p>
  <p>Built with precision · Lagos, NG</p>
</footer>

<script data-cfasync="false" src="/cdn-cgi/scripts/5c5dd728/cloudflare-static/email-decode.min.js"></script><script>
  const reveals = document.querySelectorAll('.reveal');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((e, i) => {
      if (e.isInter
