<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Portfolio — Analytics Engineer</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=IBM+Plex+Mono:wght@300;400;500&family=Inter:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  /* ========== VARIABLES ========== */
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

  /* ========== RESET ========== */
  * { margin:0; padding:0; box-sizing:border-box; }
  body { background: var(--bg); color: var(--text-primary); font-family: var(--sans); line-height: 1.7; overflow-x:hidden; }

  /* ========== NAVIGATION ========== */
  nav {
    position: fixed; top:0; left:0; right:0; z-index:100;
    display:flex; justify-content:space-between; align-items:center;
    padding:1rem 4rem; border-bottom:1px solid var(--border);
    background: rgba(8,10,14,0.85); backdrop-filter:blur(20px);
  }
  .nav-logo { font-family: var(--mono); font-size: 13px; color: var(--accent); text-decoration:none; letter-spacing:0.08em; }
  .nav-links { display:flex; gap:2rem; list-style:none; }
  .nav-links a { font-family:var(--mono); font-size:12px; color:var(--text-secondary); text-decoration:none; text-transform:uppercase; transition:color 0.3s; }
  .nav-links a:hover { color: var(--accent); }
  .nav-cta { font-family:var(--mono); font-size:12px; color:var(--accent); border:1px solid var(--border-accent); padding:0.4rem 1rem; border-radius:4px; transition:all 0.3s; text-decoration:none; }
  .nav-cta:hover { background: var(--accent-dim); }

  /* ========== HERO ========== */
  .hero {
    min-height: 100vh; display:flex; flex-direction:column; justify-content:center; padding:8rem 4rem;
    position:relative; overflow:hidden;
  }
  .hero-badge { font-family:var(--mono); font-size:11px; color:var(--accent); margin-bottom:1.5rem; display:flex; align-items:center; gap:0.6rem; text-transform:uppercase; letter-spacing:0.15em; }
  .hero-badge::before { content:''; display:inline-block; width:6px; height:6px; border-radius:50%; background: var(--accent); box-shadow:0 0 10px var(--accent); animation:pulse 2s infinite; }
  @keyframes pulse {0%,100%{opacity:1}50%{opacity:0.4}}

  .hero-name { font-family:var(--display); font-size:clamp(3rem,8vw,7rem); font-weight:800; line-height:0.95; margin-bottom:0.5rem; }
  .hero-name .accent { color: var(--accent); }

  .hero-title { font-family:var(--display); font-size:clamp(1.5rem,3vw,2rem); font-weight:500; color:var(--text-secondary); margin-bottom:2rem; }
  .hero-desc { max-width:600px; font-size:15px; color:var(--text-secondary); line-height:1.7; margin-bottom:3rem; }

  .hero-actions { display:flex; gap:1rem; flex-wrap:wrap; }
  .btn-primary { background: var(--accent); color: var(--bg); font-family: var(--mono); font-size: 12px; font-weight:500; letter-spacing:0.1em; text-transform:uppercase; padding:0.8rem 2rem; border-radius:4px; text-decoration:none; transition: all 0.3s; }
  .btn-primary:hover { opacity:0.9; transform:translateY(-2px); }
  .btn-secondary { font-family: var(--mono); font-size:12px; color:var(--text-secondary); text-decoration:none; text-transform:uppercase; display:flex; align-items:center; gap:0.5rem; transition:color 0.3s; }
  .btn-secondary:hover { color: var(--text-primary); }

  /* ========== SECTIONS ========== */
  section { padding:6rem 4rem; }
  .section-title { font-family:var(--display); font-size:clamp(2rem,4vw,3rem); font-weight:700; margin-bottom:1rem; }
  .section-subtitle { color:var(--text-secondary); font-size:15px; max-width:600px; margin-bottom:3rem; }

  /* ========== SKILLS ========== */
  .skills-grid { display:grid; grid-template-columns:repeat(auto-fit,minmax(260px,1fr)); gap:1.5rem; }
  .skill-block { background: var(--bg-card); padding:2rem; border-radius:8px; transition: all 0.3s; }
  .skill-block:hover { background: var(--bg-glass); transform:translateY(-3px); }
  .skill-block-title { font-family: var(--display); font-size:1rem; font-weight:600; margin-bottom:0.5rem; }
  .skill-tags { display:flex; flex-wrap:wrap; gap:0.4rem; }
  .tag { font-family:var(--mono); font-size:11px; color:var(--text-secondary); background: rgba(255,255,255,0.04); border:1px solid var(--border); padding:0.25rem 0.6rem; border-radius:4px; }

  /* ========== PROJECTS ========== */
  .projects-grid { display:grid; grid-template-columns:repeat(auto-fit,minmax(340px,1fr)); gap:2rem; }
  .project-card { background: var(--bg-card); border:1px solid var(--border); border-radius:10px; padding:2rem; position:relative; transition:all 0.3s; }
  .project-card:hover { transform:translateY(-3px); border-color:rgba(255,255,255,0.15); }
  .project-title { font-family:var(--display); font-size:1.25rem; font-weight:700; margin-bottom:0.75rem; }
  .project-desc { font-size:14px; color:var(--text-secondary); line-height:1.7; margin-bottom:1rem; }

  /* ========== TIMELINE ========== */
  .timeline { position:relative; padding-left:2rem; }
  .timeline::before { content:''; position:absolute; left:0; top:0; bottom:0; width:2px; background:var(--border); }
  .timeline-item { position:relative; padding-bottom:3rem; padding-left:2rem; }
  .timeline-dot { position:absolute; left:-6px; top:0; width:12px; height:12px; border-radius:50%; background:var(--accent); }
  .timeline-role { font-family:var(--display); font-size:1.1rem; font-weight:700; margin-bottom:0.25rem; }
  .timeline-company { font-family:var(--mono); font-size:13px; color:var(--accent); margin-bottom:1rem; }

  /* ========== CONTACT ========== */
  #contact { text-align:center; }
  .contact-email { font-family:var(--display); font-size:clamp(1.5rem,4vw,2.5rem); font-weight:700; color:var(--text-primary); text-decoration:none; border-bottom:2px solid var(--accent); padding-bottom:0.25rem; display:inline-block; margin:2rem 0; }
  .contact-email:hover { color: var(--accent); }

  /* ========== REVEAL ANIMATION ========== */
  .reveal { opacity:0; transform:translateY(30px); transition: all 0.6s ease; }
  .reveal.visible { opacity:1; transform:translateY(0); }

  /* ========== RESPONSIVE ========== */
  @media (max-width:768px){
    nav { padding:1rem 1.5rem; }
    section { padding:4rem 1.5rem; }
    .projects-grid, .skills-grid { grid-template-columns:1fr; }
  }
</style>
</head>
<body>

<nav>
  <a href="#" class="nav-logo">PORTFOLIO</a>
  <ul class="nav-links">
    <li><a href="#skills">Skills</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <a href="#contact" class="nav-cta">Hire Me</a>
</nav>

<section class="hero">
  <div class="hero-badge">Hello, I am</div>
  <h1 class="hero-name reveal">Chinedu <span class="accent">Promise</span></h1>
  <div class="hero-title reveal">Analytics Engineer & Data Enthusiast</div>
  <p class="hero-desc reveal">I help businesses turn data into actionable insights, improving efficiency and driving growth.</p>
  <div class="hero-actions reveal">
    <a href="#projects" class="btn-primary">View Projects</a>
    <a href="#contact" class="btn-secondary">Get in Touch</a>
  </div>
</section>

<!-- Additional sections for Skills, Projects, Timeline, Contact go here, each element using class="reveal" -->

<script>
  // Scroll Reveal JS
  const reveals = document.querySelectorAll('.reveal');
  const observer = new IntersectionObserver(entries => {
    entries.forEach(entry => {
      if(entry.isIntersecting){
        entry.target.classList.add('visible');
        observer.unobserve(entry.target);
      }
    });
  }, { threshold: 0.2 });
  reveals.forEach(el => observer.observe(el));
</script>

</body>
</html>
