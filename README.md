<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Chinedu Elekwa Promise | Data Analyst</title>
<meta name="referrer" content="no-referrer" />
<script>
  // Prevent this page from being framed by another page (fixes GitHub Pages iframe bleed)
  if (window.top !== window.self) { window.top.location = window.self.location; }
</script>
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

  /* Hero layout: photo right, text left */
  .hero-inner {
  display: flex;
  align-items: center;
  justify-content: flex-start; /* change */
  gap: 3rem; /* slightly tighter */
};
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
  /* Glow ring behind photo */
  .hero-photo-glow {
    position: absolute;
    inset: -20px;
    border-radius: 50%;
    background: radial-gradient(ellipse, rgba(0,210,140,0.15) 0%, transparent 70%);
    z-index: -1;
  }
  /* Photo placeholder — swap this div for <img class="hero-photo" src="YOUR_IMAGE"> when ready */
  .hero-photo-placeholder {
    position: absolute; inset: 6px;
    border-radius: 50%;
    background: rgba(0,210,140,0.05);
    border: 2px dashed rgba(0,210,140,0.25);
    display: flex; align-items: center; justify-content: center;
    z-index: 2;
  }
  .hero-photo-placeholder span {
    font-family: var(--mono); font-size: 11px; color: var(--accent);
    letter-spacing: 0.08em; text-align: center; line-height: 1.7; opacity: 0.55;
  }
  /* Real photo class (use this when you have your image ready) */
  .hero-photo {
    position: absolute; inset: 6px; border-radius: 50%;
    object-fit: cover; object-position: center top;
    width: calc(100% - 12px); height: calc(100% - 12px);
    z-index: 2; display: block;
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
      <h1 class="hero-name">Chinedu<br><span class="accent">Elekwa</span></h1>
      <div class="hero-badge">Open to new opportunities · Lagos, Nigeria</div>
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
        <img src="images/My-photo.jpeg" alt="Chinedu Elekwa" class="hero-photo">
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
