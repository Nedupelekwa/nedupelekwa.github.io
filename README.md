<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<meta name="referrer" content="no-referrer" />
<script>if (window.top !== window.self) { window.top.location = window.self.location; }</script>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;500;600;700;800&family=IBM+Plex+Mono:wght@300;400;500&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet" />
<style>
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

:root {
  --bg: #06080C;
  --bg-card: #0C0F16;
  --border: rgba(255,255,255,0.07);
  --border-accent: rgba(0,210,140,0.4);
  --accent: #00D28C;
  --accent-bright: #00FFAA;
  --accent-dim: rgba(0,210,140,0.08);
  --accent2: #3B82F6;
  --accent2-dim: rgba(59,130,246,0.08);
  --text-primary: #F0F4FF;
  --text-secondary: #8A96B0;
  --text-muted: #424C65;
  --mono: 'IBM Plex Mono', monospace;
  --sans: 'Inter', sans-serif;
  --display: 'Syne', sans-serif;
  --radius: 10px;
  --radius-sm: 6px;
  --glow-green: 0 0 40px rgba(0,210,140,0.12);
}

html { scroll-behavior: smooth; }
body {
  background: var(--bg);
  color: var(--text-primary);
  font-family: var(--sans);
  font-weight: 400;
  line-height: 1.7;
  overflow-x: hidden;
  cursor: none;
  padding-top: 80px; /* THIS fixes the overlap */
}

body::before {
  content: ''; position: fixed; inset: 0;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.85' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.025'/%3E%3C/svg%3E");
  pointer-events: none; z-index: 0;
}

/* ── CURSOR ── */
.cursor-dot { width: 8px; height: 8px; background: var(--accent); border-radius: 50%; position: fixed; pointer-events: none; z-index: 9999; transform: translate(-50%,-50%); }
.cursor-ring { width: 32px; height: 32px; border: 1px solid rgba(0,210,140,0.5); border-radius: 50%; position: fixed; pointer-events: none; z-index: 9998; transform: translate(-50%,-50%); transition: width 0.3s, height 0.3s, border-color 0.3s; }

/* ── SCROLL PROGRESS ── */
.scroll-progress { position: fixed; top: 0; left: 0; height: 2px; z-index: 200; background: linear-gradient(90deg, var(--accent), var(--accent2)); width: 0%; }

/* ── NAV ── */
nav {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  height: 80px; /* fixed height */
  z-index: 100;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 4rem; /* remove top/bottom padding */
  border-bottom: 1px solid var(--border);
  background: rgba(6,8,12,0.9);
  backdrop-filter: blur(24px);
}
.nav-logo { font-family: var(--mono); font-size: 13px; color: var(--accent); letter-spacing: 0.1em; text-decoration: none; font-weight: 500; display: flex; align-items: center; gap: 0.5rem; }
.nav-logo-dot { width: 6px; height: 6px; border-radius: 50%; background: var(--accent); animation: pulse 2s infinite; }
.nav-links { display: flex; gap: 2rem; list-style: none; align-items: center; }
.nav-links a { font-family: var(--mono); font-size: 11px; color: var(--text-secondary); text-decoration: none; letter-spacing: 0.14em; text-transform: uppercase; transition: color 0.2s; position: relative; }
.nav-links a::after { content: ''; position: absolute; bottom: -3px; left: 0; width: 0; height: 1px; background: var(--accent); transition: width 0.25s; }
.nav-links a:hover { color: var(--accent); }
.nav-links a:hover::after { width: 100%; }
.nav-cta { color: var(--accent) !important; border: 1px solid var(--border-accent) !important; padding: 0.45rem 1.1rem; border-radius: var(--radius-sm); background: var(--accent-dim) !important; transition: all 0.25s !important; }
.nav-cta:hover { background: rgba(0,210,140,0.16) !important; box-shadow: var(--glow-green) !important; }
.nav-hamburger { display: none; flex-direction: column; gap: 5px; cursor: pointer; padding: 4px; }
.nav-hamburger span { display: block; width: 22px; height: 2px; background: var(--text-secondary); border-radius: 2px; transition: 0.3s; }

/* ── THEME TOGGLE ── */
.theme-toggle {
  position: fixed; top: 80px; right: 24px; z-index: 999;
  display: flex; align-items: center; gap: 0.6rem;
  background: rgba(12,15,22,0.95);
  border: 1px solid var(--border-accent);
  padding: 0.55rem 1rem 0.55rem 0.75rem;
  border-radius: 40px;
  font-family: var(--mono); font-size: 11px; color: var(--accent);
  letter-spacing: 0.1em; cursor: pointer;
  backdrop-filter: blur(12px);
  transition: all 0.3s;
  box-shadow: 0 0 20px rgba(0,210,140,0.1), inset 0 1px 0 rgba(255,255,255,0.05);
}
.theme-toggle:hover { box-shadow: 0 0 32px rgba(0,210,140,0.25); border-color: var(--accent); }
.theme-toggle-icon { width: 18px; height: 18px; border-radius: 50%; background: conic-gradient(var(--accent) 180deg, transparent 180deg); border: 1px solid rgba(0,210,140,0.5); flex-shrink: 0; transition: transform 0.5s; }
.theme-toggle:hover .theme-toggle-icon { transform: rotate(180deg); }

/* ── HERO ── */
.hero { min-height: 100vh; display: flex; align-items: center; padding: 0 6rem; position: relative; overflow: hidden; }
.hero-grid-bg { position: absolute; inset: 0; background-image: linear-gradient(rgba(255,255,255,0.04) 1px, transparent 1px), linear-gradient(90deg, rgba(255,255,255,0.04) 1px, transparent 1px); background-size: 72px 72px; mask-image: radial-gradient(ellipse 80% 70% at 50% 50%, black 10%, transparent 75%); pointer-events: none; }
.hero-glow { position: absolute; top: 10%; left: 0; width: 700px; height: 600px; background: radial-gradient(ellipse, rgba(0,210,140,0.09) 0%, transparent 65%); pointer-events: none; }
.hero-glow-2 { position: absolute; bottom: 5%; right: 0; width: 600px; height: 500px; background: radial-gradient(ellipse, rgba(59,130,246,0.07) 0%, transparent 65%); pointer-events: none; }

/* DESKTOP: text left, photo right — perfectly centered via grid */
.hero-inner {
  display: grid;
  grid-template-columns: 1fr 340px;
  align-items: center;
  gap: 6rem;
  position: relative; z-index: 1;
  width: 100%; max-width: 1200px; margin: 0 auto;
  padding-top: 2rem;
}
.hero-content { min-width: 0; }
.hero-photo-col { display: flex; align-items: center; justify-content: center; }

/* ── PHOTO ── */
.hero-photo-wrap { position: relative; width: 320px; height: 320px; flex-shrink: 0; }
.hero-photo-ring { position: absolute; inset: -2px; border-radius: 50%; background: conic-gradient(var(--accent), var(--accent2), #8b5cf6, var(--accent)); animation: spin 8s linear infinite; z-index: 0; }
@keyframes spin { to { transform: rotate(360deg); } }
.hero-photo-ring-mask { position: absolute; inset: 3px; border-radius: 50%; background: var(--bg); z-index: 1; }
.hero-photo-glow { position: absolute; inset: -30px; border-radius: 50%; background: radial-gradient(ellipse, rgba(0,210,140,0.18) 0%, transparent 70%); z-index: -1; animation: glowPulse 3s ease-in-out infinite; }
@keyframes glowPulse { 0%,100% { opacity:0.7; transform:scale(1); } 50% { opacity:1; transform:scale(1.08); } }
.hero-photo { position: absolute; inset: 6px; border-radius: 50%; object-fit: cover; object-position: center top; width: calc(100% - 12px); height: calc(100% - 12px); z-index: 2; display: block; }
.hero-photo-placeholder { position: absolute; inset: 6px; border-radius: 50%; background: rgba(0,210,140,0.05); border: 2px dashed rgba(0,210,140,0.2); display: flex; align-items: center; justify-content: center; z-index: 2; font-family: var(--mono); font-size: 11px; color: var(--accent); opacity: 0.5; }
.hero-photo-badge { position: absolute; bottom: 14px; right: -10px; z-index: 10; display: flex; align-items: center; gap: 0.5rem; background: rgba(12,15,22,0.96); border: 1px solid var(--border-accent); padding: 0.4rem 0.85rem; border-radius: 20px; font-family: var(--mono); font-size: 10px; color: var(--accent); letter-spacing: 0.1em; backdrop-filter: blur(10px); white-space: nowrap; }
.hero-photo-badge::before { content: ''; width: 5px; height: 5px; border-radius: 50%; background: var(--accent); animation: pulse 1.5s infinite; }

/* ── HERO TEXT ── */
.hero-badge { font-family: var(--mono); font-size: 11px; color: var(--accent); letter-spacing: 0.2em; text-transform: uppercase; display: inline-flex; align-items: center; gap: 0.6rem; margin-bottom: 1.4rem; background: var(--accent-dim); border: 1px solid rgba(0,210,140,0.2); padding: 0.35rem 0.9rem; border-radius: 20px; }
.hero-badge::before { content: ''; width: 6px; height: 6px; border-radius: 50%; background: var(--accent); box-shadow: 0 0 8px var(--accent); animation: pulse 2s infinite; }
@keyframes pulse { 0%,100% { opacity:1; box-shadow:0 0 8px var(--accent); } 50% { opacity:0.5; box-shadow:0 0 3px var(--accent); } }

.hero-name { font-family: var(--display); font-size: clamp(3.5rem, 5.5vw, 6rem); font-weight: 800; line-height: 0.92; letter-spacing: -0.03em; margin-bottom: 0.75rem; color: #FFFFFF; }
.hero-name .accent { color: var(--accent); }
.hero-title { font-family: var(--display); font-size: clamp(1rem, 1.8vw, 1.5rem); font-weight: 500; color: var(--text-secondary); margin-bottom: 1.4rem; letter-spacing: -0.01em; }
.hero-desc { max-width: 480px; font-size: 15px; color: var(--text-secondary); line-height: 1.9; margin-bottom: 2rem; border-left: 2px solid var(--border-accent); padding-left: 1rem; }

.hero-actions { display: flex; gap: 1rem; align-items: center; flex-wrap: wrap; margin-bottom: 3rem; }
.btn-primary { background: var(--accent); color: #060810; font-family: var(--mono); font-size: 12px; font-weight: 600; letter-spacing: 0.12em; text-transform: uppercase; padding: 0.85rem 2rem; border-radius: var(--radius-sm); text-decoration: none; transition: all 0.25s; position: relative; overflow: hidden; }
.btn-primary::after { content: ''; position: absolute; inset: 0; background: rgba(255,255,255,0.15); transform: translateX(-100%); transition: transform 0.35s; }
.btn-primary:hover::after { transform: translateX(0); }
.btn-primary:hover { transform: translateY(-2px); box-shadow: 0 8px 30px rgba(0,210,140,0.35); }
.btn-secondary { font-family: var(--mono); font-size: 12px; color: var(--text-secondary); text-decoration: none; letter-spacing: 0.12em; text-transform: uppercase; display: flex; align-items: center; gap: 0.5rem; border: 1px solid var(--border); padding: 0.85rem 1.5rem; border-radius: var(--radius-sm); transition: all 0.2s; }
.btn-secondary:hover { color: var(--accent); border-color: var(--border-accent); }

.hero-stats { display: flex; gap: 2.5rem; padding-top: 2rem; border-top: 1px solid var(--border); flex-wrap: wrap; }
.stat-val { font-family: var(--display); font-size: 2.2rem; font-weight: 800; color: #FFFFFF; display: block; letter-spacing: -0.02em; }
.stat-label { font-family: var(--mono); font-size: 10px; color: var(--text-muted); letter-spacing: 0.12em; text-transform: uppercase; }

/* ── SECTIONS ── */
section { padding: 7rem 6rem; position: relative; z-index: 1; }
.section-label { font-family: var(--mono); font-size: 11px; color: var(--accent); letter-spacing: 0.25em; text-transform: uppercase; margin-bottom: 0.75rem; display: flex; align-items: center; gap: 0.75rem; }
.section-label::before { content: '//'; color: var(--text-muted); }
.section-label::after { content: ''; height: 1px; flex: 0 0 40px; background: var(--border-accent); }
.section-title { font-family: var(--display); font-size: clamp(2rem, 3.5vw, 3rem); font-weight: 800; letter-spacing: -0.025em; margin-bottom: 0.75rem; color: #FFFFFF; line-height: 1.05; }
.section-subtitle { color: var(--text-secondary); font-size: 15px; max-width: 500px; margin-bottom: 3.5rem; line-height: 1.8; }

.tag { font-family: var(--mono); font-size: 11px; color: var(--text-secondary); background: rgba(255,255,255,0.04); border: 1px solid var(--border); padding: 0.25rem 0.7rem; border-radius: 4px; letter-spacing: 0.05em; transition: all 0.2s; }
.tag.accent-tag { color: var(--accent); border-color: rgba(0,210,140,0.2); background: var(--accent-dim); }
.tag.blue-tag { color: var(--accent2); border-color: rgba(59,130,246,0.2); background: var(--accent2-dim); }

/* ── EXPERTISE ── */
#expertise { background: linear-gradient(180deg, var(--bg) 0%, var(--bg-card) 100%); }
.expertise-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(240px, 1fr)); gap: 1px; background: var(--border); border: 1px solid var(--border); border-radius: var(--radius); overflow: hidden; }
.expertise-card { background: var(--bg-card); padding: 1.5rem 1.75rem; font-family: var(--mono); font-size: 12px; letter-spacing: 0.07em; color: var(--text-secondary); transition: all 0.25s; display: flex; align-items: center; gap: 0.75rem; }
.expertise-card::before { content: '▸'; color: var(--text-muted); font-size: 10px; flex-shrink: 0; transition: color 0.25s; }
.expertise-card:hover { background: rgba(0,210,140,0.05); color: var(--accent); }
.expertise-card:hover::before { color: var(--accent); }

/* ── SKILLS ── */
#skills { background: var(--bg-card); border-top: 1px solid var(--border); border-bottom: 1px solid var(--border); }
.skills-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 1px; background: var(--border); border: 1px solid var(--border); border-radius: var(--radius); overflow: hidden; }
.skill-block { background: var(--bg-card); padding: 2rem; transition: background 0.25s; position: relative; overflow: hidden; }
.skill-block::before { content: ''; position: absolute; top: 0; left: 0; right: 0; height: 2px; background: linear-gradient(90deg, var(--accent), var(--accent2)); transform: scaleX(0); transform-origin: left; transition: transform 0.35s; }
.skill-block:hover { background: rgba(255,255,255,0.03); }
.skill-block:hover::before { transform: scaleX(1); }
.skill-block-icon { font-size: 18px; margin-bottom: 1rem; color: var(--accent); }
.skill-block-title { font-family: var(--display); font-size: 0.95rem; font-weight: 700; margin-bottom: 0.9rem; color: #FFFFFF; }
.skill-tags { display: flex; flex-wrap: wrap; gap: 0.4rem; }

/* ── PROJECTS ── */
#projects { background: var(--bg); }
.projects-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 1.5rem; }
.project-card { background: var(--bg-card); border: 1px solid var(--border); border-radius: var(--radius); overflow: hidden; position: relative; transition: all 0.35s; display: flex; flex-direction: column; }
.project-card:hover { border-color: rgba(0,210,140,0.25); transform: translateY(-6px); box-shadow: 0 24px 60px rgba(0,0,0,0.4), var(--glow-green); }
.project-card-top-bar { height: 2px; background: linear-gradient(90deg, var(--accent), var(--accent2), #8b5cf6); transform: scaleX(0); transform-origin: left; transition: transform 0.4s; }
.project-card:hover .project-card-top-bar { transform: scaleX(1); }
.project-img { width: 100%; height: 200px; object-fit: cover; display: block; }
.project-img-placeholder { width: 100%; height: 200px; background: linear-gradient(135deg, rgba(0,210,140,0.04), rgba(59,130,246,0.04)); display: flex; align-items: center; justify-content: center; font-family: var(--mono); font-size: 11px; color: var(--text-muted); letter-spacing: 0.15em; border-bottom: 1px solid var(--border); position: relative; overflow: hidden; }
.project-img-placeholder::before { content: ''; position: absolute; inset: 0; background-image: linear-gradient(var(--border) 1px, transparent 1px), linear-gradient(90deg, var(--border) 1px, transparent 1px); background-size: 24px 24px; opacity: 0.5; }
.project-body { padding: 1.75rem; flex: 1; display: flex; flex-direction: column; }
.project-number { font-family: var(--mono); font-size: 11px; color: var(--text-muted); margin-bottom: 0.85rem; display: flex; justify-content: space-between; align-items: center; }
.project-type { font-family: var(--mono); font-size: 10px; color: var(--accent); border: 1px solid rgba(0,210,140,0.2); background: var(--accent-dim); padding: 0.2rem 0.65rem; border-radius: 3px; letter-spacing: 0.1em; }
.project-title { font-family: var(--display); font-size: 1.2rem; font-weight: 700; margin-bottom: 0.7rem; letter-spacing: -0.01em; color: #FFFFFF; }
.project-desc { font-size: 14px; color: var(--text-secondary); line-height: 1.85; margin-bottom: 1.25rem; flex: 1; }
.project-stack { display: flex; flex-wrap: wrap; gap: 0.4rem; margin-bottom: 1.25rem; }
.project-link { font-family: var(--mono); font-size: 11px; color: var(--accent2); text-decoration: none; letter-spacing: 0.1em; display: inline-flex; align-items: center; gap: 0.4rem; transition: all 0.2s; text-transform: uppercase; border: 1px solid rgba(59,130,246,0.25); background: var(--accent2-dim); padding: 0.5rem 1rem; border-radius: var(--radius-sm); font-weight: 500; align-self: flex-start; }
.project-link:hover { color: var(--accent); border-color: var(--border-accent); background: var(--accent-dim); }

/* ── TIMELINE ── */
#experience { background: var(--bg-card); border-top: 1px solid var(--border); border-bottom: 1px solid var(--border); }
.timeline { position: relative; padding-left: 2rem; }
.timeline::before { content: ''; position: absolute; left: 0; top: 8px; bottom: 0; width: 1px; background: linear-gradient(180deg, var(--accent), var(--accent2), transparent); }
.timeline-item { position: relative; padding-bottom: 3.5rem; padding-left: 2.5rem; }
.timeline-item:last-child { padding-bottom: 0; }
.timeline-dot { position: absolute; left: -2.55rem; top: 6px; width: 10px; height: 10px; border-radius: 50%; background: var(--accent); border: 2px solid var(--bg-card); box-shadow: 0 0 16px rgba(0,210,140,0.6); }
.timeline-date { font-family: var(--mono); font-size: 11px; color: var(--text-muted); letter-spacing: 0.15em; text-transform: uppercase; margin-bottom: 0.5rem; }
.timeline-role { font-family: var(--display); font-size: 1.2rem; font-weight: 700; margin-bottom: 0.25rem; color: #FFFFFF; }
.timeline-company { font-family: var(--mono); font-size: 12px; color: var(--accent); margin-bottom: 1rem; }
.timeline-bullets { list-style: none; }
.timeline-bullets li { font-size: 14px; color: var(--text-secondary); padding: 0.3rem 0 0.3rem 1.4rem; position: relative; line-height: 1.7; }
.timeline-bullets li::before { content: '—'; position: absolute; left: 0; color: var(--accent); font-family: var(--mono); font-size: 11px; }

/* ── CERTIFICATIONS ── */
#certifications { background: var(--bg); border-top: 1px solid var(--border); border-bottom: 1px solid var(--border); }
.cert-group-label { font-family: var(--mono); font-size: 11px; letter-spacing: 0.2em; text-transform: uppercase; margin-bottom: 1.5rem; padding-bottom: 0.75rem; border-bottom: 1px solid var(--border); font-weight: 500; }
.cert-group-label.green { color: var(--accent); }
.cert-group-label.blue { color: var(--accent2); }
.cert-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(210px, 1fr)); gap: 1.25rem; margin-bottom: 3rem; }
.cert-card { background: var(--bg-card); border: 1px solid var(--border); border-radius: var(--radius); overflow: hidden; transition: all 0.25s; }
.cert-card:hover { transform: translateY(-4px); border-color: rgba(0,210,140,0.2); box-shadow: var(--glow-green); }
.cert-stripe { height: 3px; background: linear-gradient(90deg, var(--accent), var(--accent2)); }
.cert-stripe.blue { background: linear-gradient(90deg, var(--accent2), #8b5cf6); }
.cert-body { padding: 1.35rem; }
.cert-icon { font-size: 20px; margin-bottom: 0.85rem; }
.cert-title { font-family: var(--display); font-size: 0.88rem; font-weight: 700; margin-bottom: 0.5rem; line-height: 1.45; color: #FFFFFF; }
.cert-issuer { font-family: var(--mono); font-size: 11px; color: var(--accent); letter-spacing: 0.08em; }
.cert-issuer.blue { color: var(--accent2); }

/* ── RECOGNITIONS ── */
.rec-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 1.5rem; }
.rec-card { background: var(--bg-card); border: 1px solid var(--border); border-radius: var(--radius); padding: 2rem; position: relative; transition: all 0.3s; overflow: hidden; }
.rec-card::before { content: ''; position: absolute; top: 0; left: 0; right: 0; height: 2px; background: linear-gradient(90deg, var(--accent), var(--accent2)); }
.rec-card:hover { transform: translateY(-5px); border-color: rgba(0,210,140,0.2); box-shadow: var(--glow-green); }
.rec-icon { font-size: 28px; margin-bottom: 1rem; }
.rec-title { font-family: var(--display); font-size: 1rem; font-weight: 700; margin-bottom: 0.65rem; color: #FFFFFF; }
.rec-desc { font-size: 14px; color: var(--text-secondary); line-height: 1.8; }

/* ── CONTACT ── */
#contact { text-align: center; background: var(--bg); }
.contact-wrapper { max-width: 640px; margin: 0 auto; }
.contact-email { font-family: var(--display); font-size: clamp(1.4rem, 3.5vw, 2.1rem); font-weight: 800; color: #FFFFFF; text-decoration: none; display: inline-block; margin: 2rem 0; padding-bottom: 0.3rem; transition: color 0.2s; word-break: break-all; position: relative; }
.contact-email::after { content: ''; position: absolute; bottom: 0; left: 0; right: 0; height: 2px; background: linear-gradient(90deg, var(--accent), var(--accent2)); border-radius: 2px; }
.contact-email:hover { color: var(--accent); }
.socials { display: flex; justify-content: center; gap: 0.75rem; margin-top: 2rem; flex-wrap: wrap; }
.social-link { font-family: var(--mono); font-size: 11px; color: var(--text-secondary); text-decoration: none; letter-spacing: 0.1em; text-transform: uppercase; display: flex; align-items: center; gap: 0.4rem; border: 1px solid var(--border); padding: 0.65rem 1.1rem; border-radius: var(--radius-sm); transition: all 0.2s; }
.social-link:hover { color: var(--accent); border-color: var(--border-accent); background: var(--accent-dim); transform: translateY(-2px); }

/* ── FOOTER ── */
footer { padding: 2rem 6rem; border-top: 1px solid var(--border); display: flex; justify-content: space-between; align-items: center; background: var(--bg-card); }
footer p { font-family: var(--mono); font-size: 11px; color: var(--text-muted); letter-spacing: 0.08em; }
.footer-accent { color: var(--accent); }

/* ── REVEAL ── */
.reveal { opacity: 0; transform: translateY(24px); transition: opacity 0.7s ease, transform 0.7s ease; }
.reveal.visible { opacity: 1; transform: none; }

/* ── STICKY CTA ── */
.sticky-cta { position: fixed; bottom: 24px; left: 50%; transform: translateX(-50%); background: rgba(12,15,22,0.94); backdrop-filter: blur(16px); border: 1px solid var(--border); padding: 0.5rem 0.6rem; border-radius: 50px; display: flex; gap: 0.5rem; align-items: center; z-index: 300; opacity: 0; pointer-events: none; transition: all 0.4s; box-shadow: 0 8px 32px rgba(0,0,0,0.5); }
.sticky-cta.show { opacity: 1; pointer-events: auto; }
.sticky-cta a { font-family: var(--mono); font-size: 11px; text-decoration: none; padding: 0.5rem 1.1rem; border-radius: 30px; letter-spacing: 0.08em; transition: all 0.2s; }
.sticky-cta .primary { background: var(--accent); color: #060810; font-weight: 600; }
.sticky-cta .primary:hover { background: var(--accent-bright); }
.sticky-cta .secondary { color: var(--text-secondary); border: 1px solid var(--border); }
.sticky-cta .secondary:hover { color: var(--accent); border-color: var(--border-accent); }

/* ── MOBILE NAV ── */
.mobile-nav { display: none; position: fixed; inset: 0; z-index: 200; background: rgba(6,8,12,0.98); backdrop-filter: blur(24px); flex-direction: column; align-items: center; justify-content: center; gap: 2.5rem; }
.mobile-nav.open { display: flex; }
.mobile-nav-link { font-family: var(--mono); font-size: 18px; color: var(--text-secondary); text-decoration: none; letter-spacing: 0.15em; text-transform: uppercase; transition: color 0.2s; }
.mobile-nav-link:hover { color: var(--accent); }
.mobile-nav-close { position: absolute; top: 1.25rem; right: 1.5rem; font-family: var(--mono); font-size: 22px; color: var(--text-muted); cursor: pointer; background: none; border: none; line-height: 1; }

/* ── LIGHT MODE ── */
body.light {
  --bg: #F4F6FB; --bg-card: #FFFFFF; --text-primary: #0b1220;
  --text-secondary: #4A5568; --text-muted: #94A3B8;
  --border: rgba(0,0,0,0.07); --accent-dim: rgba(0,180,120,0.07);
  --border-accent: rgba(0,180,120,0.4);
}
body.light .hero-photo-ring-mask { background: var(--bg); }
body.light .theme-toggle { background: rgba(255,255,255,0.97); color: #0a7a55; }
body.light nav { background: rgba(244,246,251,0.93); }

/* ── RESPONSIVE ── */
@media (max-width: 1100px) {
  section { padding: 6rem 3rem; } nav { padding: 1rem 3rem; }
  .hero { padding: 0 3rem; } footer { padding: 2rem 3rem; }
  .hero-inner { gap: 4rem; grid-template-columns: 1fr 280px; }
  .hero-photo-wrap { width: 280px; height: 280px; }
}

@media (max-width: 860px) {
  nav { padding: 1rem 1.5rem; }
  .nav-links { display: none; }
  .nav-hamburger { display: flex; }

  /* MOBILE HERO — photo on top */
  .hero { padding: 0 1.5rem; align-items: flex-start; min-height: auto; }
  .hero-inner {
    display: flex; flex-direction: column;
    align-items: center; text-align: center;
    gap: 2.5rem;
    padding-top: 2rem; padding-bottom: 4rem;
  }
  .hero-photo-col { order: 0; }
  .hero-content { order: 1; width: 100%; }
  .hero-photo-wrap { width: 220px; height: 220px; }
  .hero-photo-badge { bottom: 4px; right: -4px; font-size: 9px; padding: 0.3rem 0.6rem; }
  .hero-badge { justify-content: center; }
  .hero-desc { margin: 0 auto 2rem; border-left: none; padding-left: 0; border-top: 2px solid var(--border-accent); padding-top: 1rem; }
  .hero-actions { justify-content: center; }
  .hero-stats { justify-content: center; gap: 2rem; }

  section { padding: 4rem 1.5rem; }
  .skills-grid, .projects-grid { grid-template-columns: 1fr; }
  .cert-grid { grid-template-columns: repeat(auto-fit, minmax(160px, 1fr)); }
  .rec-grid { grid-template-columns: 1fr; }
  footer { flex-direction: column; gap: 0.75rem; text-align: center; padding: 1.5rem; }
  .theme-toggle { top: auto; bottom: 80px; right: 16px; }
}

@media (max-width: 480px) {
  .hero-stats { flex-direction: column; align-items: center; gap: 1.5rem; }
  .stat-val { font-size: 1.8rem; }
  .hero-name { font-size: clamp(2.8rem, 14vw, 4rem); }
  .cursor-dot, .cursor-ring { display: none; }
  body { cursor: auto; }
}
</style>
</head>
<body>

<div class="cursor-dot" id="cursorDot"></div>
<div class="cursor-ring" id="cursorRing"></div>
<div class="scroll-progress" id="scrollProgress"></div>

<button class="theme-toggle" id="themeToggle" aria-label="Toggle theme">
  <div class="theme-toggle-icon"></div>
  <span id="themeLabel">Light Mode</span>
</button>

<nav>
  <a href="#" class="nav-logo"><div class="nav-logo-dot"></div>[ Welcome To My Portfolio Site ]</a>
  <ul class="nav-links">
    <li><a href="#skills">Skills</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#experience">Experience</a></li>
    <li><a href="#certifications">Certs</a></li>
    <li><a href="#recognitions">Recognition</a></li>
    <li><a href="#contact" class="nav-cta">Hire Me</a></li>
  </ul>
  <div class="nav-hamburger" id="hamburger"><span></span><span></span><span></span></div>
</nav>

<div class="mobile-nav" id="mobileNav">
  <button class="mobile-nav-close" id="mobileNavClose">✕</button>
  <a href="#skills" class="mobile-nav-link">Skills</a>
  <a href="#projects" class="mobile-nav-link">Projects</a>
  <a href="#experience" class="mobile-nav-link">Experience</a>
  <a href="#certifications" class="mobile-nav-link">Certifications</a>
  <a href="#recognitions" class="mobile-nav-link">Recognition</a>
  <a href="#contact" class="mobile-nav-link" style="color:var(--accent)">Hire Me</a>
</div>

<!-- HERO -->
<section class="hero" id="hero">
  <div class="hero-grid-bg"></div>
  <div class="hero-glow"></div>
  <div class="hero-glow-2"></div>

  <div class="hero-inner">

    <!-- PHOTO — right on desktop, top on mobile (via flex order) -->
    <div class="hero-photo-col">
      <div class="hero-photo-wrap">
        <div class="hero-photo-glow"></div>
        <div class="hero-photo-ring"></div>
        <div class="hero-photo-ring-mask"></div>
        <img src="images/My-photo.jpeg" alt="Chinedu Elekwa Promise" class="hero-photo"
          onerror="this.style.display='none';document.getElementById('photoPH').style.display='flex'">
        <div class="hero-photo-placeholder" id="photoPH" style="display:none"><span>Photo</span></div>
        <div class="hero-photo-badge">Open to Work</div>
      </div>
    </div>

    <!-- TEXT -->
    <div class="hero-content">
      <div class="hero-badge">Lagos, Nigeria</div>
      <h1 class="hero-name">CHINEDU<br><span class="accent">ELEKWA PROMISE</span></h1>
      <p class="hero-title">Data Analyst | Business Intelligence</p>
      <p class="hero-desc">Building scalable data solutions and turning raw data into strategic insights. I bring the precision of a mathematician, the clarity of an educator, and the impact-focus of a business analyst to every problem I solve.</p>
      <div class="hero-actions">
        <a href="#projects" class="btn-primary">Explore My Work →</a>
        <a href="#contact" class="btn-secondary">Get in touch ↗</a>
      </div>
      <div class="hero-stats">
        <div><span class="stat-val" data-target="5" data-suffix="+">0</span><span class="stat-label">Years in Data</span></div>
        <div><span class="stat-val" data-target="95" data-suffix="%">0</span><span class="stat-label">Analytics Efficiency</span></div>
        <div><span class="stat-val" data-target="4" data-suffix="+">0</span><span class="stat-label">Certifications</span></div>
        <div><span class="stat-val" data-target="100" data-suffix="+">0</span><span class="stat-label">Analysts Mentored</span></div>
      </div>
    </div>

  </div>
</section>

<!-- EXPERTISE -->
<section id="expertise">
  <div class="section-label">Core Strengths</div>
  <h2 class="section-title">My Technical Expertise</h2>
  <p class="section-subtitle reveal">Specialized capabilities that define my impact across data, analytics, and business intelligence.</p>
  <div class="expertise-grid reveal">
    <div class="expertise-card">Statistical Analytics</div>
    <div class="expertise-card">Professional Dashboard Design</div>
    <div class="expertise-card">Digital Marketing Analytics</div>
    <div class="expertise-card">FMCG Analytics</div>
    <div class="expertise-card">Data Modeling</div>
    <div class="expertise-card">Executive-style PowerPoint Reports</div>
    <div class="expertise-card">Advanced Data Analytics & Visualisation with Python</div>
  </div>
</section>

<!-- SKILLS -->
<section id="skills">
  <div class="section-label">Technical Arsenal</div>
  <h2 class="section-title">What I Work With</h2>
  <p class="section-subtitle reveal">From spreadsheets to cloud — every layer of the data workflow.</p>
  <div class="skills-grid reveal">
    <div class="skill-block"><div class="skill-block-icon">⬡</div><div class="skill-block-title">Languages & Querying</div><div class="skill-tags"><span class="tag accent-tag">SQL</span><span class="tag accent-tag">Python</span><span class="tag">Data Cleaning</span><span class="tag">Statistical Analysis</span><span class="tag">Mathematics</span></div></div>
    <div class="skill-block"><div class="skill-block-icon">◎</div><div class="skill-block-title">Visualization & BI</div><div class="skill-tags"><span class="tag accent-tag">Power BI</span><span class="tag accent-tag">Looker Studio</span><span class="tag">DAX</span><span class="tag">Dashboard Design</span><span class="tag">MS PowerPoint</span></div></div>
    <div class="skill-block"><div class="skill-block-icon">▣</div><div class="skill-block-title">Spreadsheets & Productivity</div><div class="skill-tags"><span class="tag accent-tag">MS Excel</span><span class="tag accent-tag">Google Sheets</span><span class="tag">Google Forms</span><span class="tag">Google Workspace</span></div></div>
    <div class="skill-block"><div class="skill-block-icon">◈</div><div class="skill-block-title">ERP & Operations</div><div class="skill-tags"><span class="tag accent-tag">SAP</span><span class="tag">Production Planning</span><span class="tag">Inventory Management</span><span class="tag">FMCG Supply Chain</span></div></div>
    <div class="skill-block"><div class="skill-block-icon">◯</div><div class="skill-block-title">Cloud & Platforms</div><div class="skill-tags"><span class="tag accent-tag">Google Cloud</span><span class="tag">BigQuery</span><span class="tag">Looker Studio</span><span class="tag">Google Drive</span></div></div>
    <div class="skill-block"><div class="skill-block-icon">◫</div><div class="skill-block-title">Soft Skills & Leadership</div><div class="skill-tags"><span class="tag">Data Mentorship</span><span class="tag">Report Writing</span><span class="tag">Stakeholder Comms</span><span class="tag">Teaching</span><span class="tag">Growth Mindset</span></div></div>
  </div>
</section>

<!-- PROJECTS -->
<section id="projects">
  <div class="section-label">Selected Work</div>
  <h2 class="section-title">Projects</h2>
  <p class="section-subtitle reveal">Real analytics work across FMCG, education, and edtech.</p>
  <div class="projects-grid">
    <div class="project-card reveal">
      <div class="project-card-top-bar"></div>
      <div class="project-img-placeholder">[ FMCG Production Analytics ]</div>
      <div class="project-body">
        <div class="project-number"><span>01</span><span class="project-type">Case Study</span></div>
        <div class="project-title">FMCG Production Analytics System</div>
        <div class="project-desc"><strong style="color:var(--text-primary)">Problem:</strong> No visibility into production inefficiencies.<br><br><strong style="color:var(--text-primary)">Approach:</strong> Built a Google Forms + Sheets pipeline tracking output, downtime, and waste.<br><br><strong style="color:var(--text-primary)">Impact:</strong> Analytics efficiency lifted to 95% — enabling faster operational decisions.</div>
        <div class="project-stack"><span class="tag accent-tag">Google Sheets</span><span class="tag accent-tag">SAP</span><span class="tag">Reporting</span></div>
      </div>
    </div>
    <div class="project-card reveal">
      <div class="project-card-top-bar"></div>
      <img src="images/Business-dashboard.jpg" alt="Power BI Business Dashboard" class="project-img" onerror="this.style.display='none';this.nextElementSibling.style.display='flex'">
      <div class="project-img-placeholder" style="display:none">[ Power BI Business Dashboard ]</div>
      <div class="project-body">
        <div class="project-number"><span>02</span><span class="project-type">Business Intelligence</span></div>
        <div class="project-title">Power BI Business Dashboard</div>
        <div class="project-desc">End-to-end sales analytics dashboard revealing key business trends. Key finding: +24.5% YoY Sales growth from 2021–2022, enabling strategic leadership decisions.</div>
        <div class="project-stack"><span class="tag accent-tag">Power BI</span><span class="tag accent-tag">DAX</span><span class="tag">Power Query</span><span class="tag">MS Excel</span></div>
        <a href="https://github.com/Nedupelekwa/POWERBI-BUSINESS-DASHBOARD" target="_blank" class="project-link">View on GitHub ↗</a>
      </div>
    </div>
    <div class="project-card reveal">
      <div class="project-card-top-bar"></div>
      <div class="project-img-placeholder">[ Student Performance Analysis ]</div>
      <div class="project-body">
        <div class="project-number"><span>03</span><span class="project-type">Education Analytics</span></div>
        <div class="project-title">Student Performance Analysis System</div>
        <div class="project-desc">Built and maintained a student performance database. Used Excel to analyse results, identify at-risk students, and produce data-backed reports for school leadership and parents.</div>
        <div class="project-stack"><span class="tag accent-tag">MS Excel</span><span class="tag">Google Sheets</span><span class="tag">Data Reporting</span></div>
        <a href="https://nedupelekwa.github.io" target="_blank" class="project-link">View Portfolio ↗</a>
      </div>
    </div>
  </div>
</section>

<!-- EXPERIENCE -->
<section id="experience">
  <div class="section-label">Career History</div>
  <h2 class="section-title">Experience</h2>
  <p class="section-subtitle reveal">Where I've built things that matter.</p>
  <div class="timeline reveal">
    <div class="timeline-item"><div class="timeline-dot"></div><div class="timeline-date">Sept 2025 — Present</div><div class="timeline-role">Data Analyst Intern</div><div class="timeline-company">edMotion Technologies · Remote</div><ul class="timeline-bullets"><li>Working on data analytics projects in the edtech space, applying SQL and Python to derive insights</li><li>Contributing to data-driven product decisions and reporting workflows</li></ul></div>
    <div class="timeline-item"><div class="timeline-dot"></div><div class="timeline-date">Sept 2025 — Present</div><div class="timeline-role">DATA Volunteer Mentor</div><div class="timeline-company">ALX Africa Data Programs · Remote</div><ul class="timeline-bullets"><li>Mentoring aspiring data professionals across Africa in analytics, Python, and data science</li><li>Served as Session Moderator at the Virtual Global Data & AI Tech Conference (GDAI) 2025</li><li>Recognised as Ambassador by DataGlobal Hub for contributions to the data community</li></ul></div>
    <div class="timeline-item"><div class="timeline-dot"></div><div class="timeline-date">2023 — 2025</div><div class="timeline-role">Production Planner / Production Data Analyst</div><div class="timeline-company">Frutta Juice and Services Limited · Lagos, Nigeria</div><ul class="timeline-bullets"><li>Built a Google Forms & Sheets pipeline tracking output, downtime, waste and material usage — increasing analytics efficiency to 95%</li><li>Managed production inventory end-to-end on SAP from raw materials to warehouse transfer</li><li>Developed production and material plans to ensure continuous operations</li><li>Produced professional stakeholder production reports using PowerPoint</li></ul></div>
    <div class="timeline-item"><div class="timeline-dot"></div><div class="timeline-date">Jan 2023 — Sept 2024</div><div class="timeline-role">Mathematics Educator / Data Analyst</div><div class="timeline-company">Cedec International Secondary School · Lagos, Nigeria</div><ul class="timeline-bullets"><li>Built and maintained a student performance database; analysed results with Excel to track progress</li><li>Produced data-backed performance reports for school leadership and parents</li><li>Managed customer relationships and provided mentorship to students</li></ul></div>
    <div class="timeline-item"><div class="timeline-dot" style="background:var(--text-muted);box-shadow:none"></div><div class="timeline-date">2020 — 2021 · 2013 — 2014</div><div class="timeline-role">Mathematics Educator</div><div class="timeline-company">Great Divine College & Divine Victory Schools · Lagos, Nigeria</div><ul class="timeline-bullets"><li>Taught Mathematics at secondary school level — building the analytical foundations that underpin my data career</li></ul></div>
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
<section id="recognitions" style="background:var(--bg-card);border-top:1px solid var(--border);border-bottom:1px solid var(--border)">
  <div class="section-label">Recognition</div>
  <h2 class="section-title">Awards & Volunteer Service</h2>
  <p class="section-subtitle reveal">Giving back to the African data community.</p>
  <div class="rec-grid reveal">
    <div class="rec-card"><div class="rec-icon">🌍</div><div class="rec-title">DATA Volunteer Mentor — ALX Africa</div><div class="rec-desc">Supporting the next generation of data professionals across Africa through hands-on mentorship in analytics, Python programming, and data science since September 2025.</div></div>
    <div class="rec-card"><div class="rec-icon">🎙</div><div class="rec-title">GDAI 2025 Session Moderator</div><div class="rec-desc">Recognised by DataGlobal Hub with a Certificate of Recognition for Volunteer Service as Session Moderator at the Virtual Global Data & AI Tech Conference (GDAI) 2025.</div></div>
    <div class="rec-card"><div class="rec-icon">◈</div><div class="rec-title">Ambassador — DataGlobal Hub</div><div class="rec-desc">Appointed as Ambassador at DataGlobal Hub, representing and advocating for the growth of the data and AI community in Nigeria and across Africa.</div></div>
  </div>
</section>

<!-- WHY HIRE ME -->
<section id="recruiter" style="background:var(--bg-card);border-top:1px solid var(--border);border-bottom:1px solid var(--border)">
  <div class="section-label">Why Hire Me</div>
  <h2 class="section-title">I Don't Just Analyze Data —<br>I Drive Decisions</h2>
  <p class="section-subtitle reveal">Recruiters don't hire tools. They hire thinkers, communicators, and impact-makers.</p>
  <div class="rec-grid reveal">
    <div class="rec-card"><div class="rec-icon">📊</div><div class="rec-title">Business-First Analyst</div><div class="rec-desc">I translate raw data into decisions executives can act on immediately — not just charts, but clear, actionable intelligence.</div></div>
    <div class="rec-card"><div class="rec-icon">⚙️</div><div class="rec-title">End-to-End Problem Solver</div><div class="rec-desc">From data collection → cleaning → modeling → visualization → insight delivery. I own the full pipeline.</div></div>
    <div class="rec-card"><div class="rec-icon">🚀</div><div class="rec-title">Impact-Oriented Work</div><div class="rec-desc">Every project is tied to measurable business improvement or operational efficiency — 95% analytics uplift as proof.</div></div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="contact-wrapper">
    <div class="section-label" style="justify-content:center">Let's Talk</div>
    <h2 class="section-title reveal">Open to the Right<br>Opportunity</h2>
    <p class="section-subtitle reveal" style="margin:0 auto 1rem;text-align:center;max-width:440px">Whether it's a full-time role, a freelance project, or just a conversation about data — I'd love to hear from you.</p>
    <a href="mailto:chinedupelekwa@gmail.com" class="contact-email reveal">chinedupelekwa@gmail.com</a>
    <div class="socials reveal">
      <a href="https://www.linkedin.com/in/chinedu-elekwa/" target="_blank" class="social-link">↗ LinkedIn</a>
      <a href="https://nedupelekwa.github.io" target="_blank" class="social-link">↗ GitHub</a>
      <a href="https://tinyurl.com/bdhbn9zt" target="_blank" class="social-link">↗ Website</a>
      <a href="tel:+2347033130747" class="social-link">↗ +234 703 313 0747</a>
    </div>
  </div>
</section>

<footer>
  <p>© 2026 <span class="footer-accent">Chinedu Elekwa Promise</span>. All rights reserved.</p>
  <p>Built like a <span class="footer-accent">Data Product</span> · Lagos, Nigeria</p>
</footer>

<div class="sticky-cta" id="stickyCTA">
  <a href="#projects" class="secondary">View Work</a>
  <a href="#contact" class="primary">Hire Me →</a>
</div>

<script>
/* CURSOR */
const dot = document.getElementById('cursorDot');
const ring = document.getElementById('cursorRing');
document.addEventListener('mousemove', e => {
  dot.style.left = e.clientX + 'px'; dot.style.top = e.clientY + 'px';
  ring.style.left = e.clientX + 'px'; ring.style.top = e.clientY + 'px';
});
document.querySelectorAll('a,button').forEach(el => {
  el.addEventListener('mouseenter', () => { ring.style.width='48px'; ring.style.height='48px'; ring.style.borderColor='var(--accent)'; });
  el.addEventListener('mouseleave', () => { ring.style.width='32px'; ring.style.height='32px'; ring.style.borderColor='rgba(0,210,140,0.5)'; });
});

/* SCROLL */
window.addEventListener('scroll', () => {
  const pct = (window.scrollY / (document.body.scrollHeight - window.innerHeight)) * 100;
  document.getElementById('scrollProgress').style.width = pct + '%';
  document.getElementById('stickyCTA').classList.toggle('show', window.scrollY > 400);
  document.querySelector('.hero-glow').style.transform = `translateY(${window.scrollY * 0.15}px)`;
  document.querySelector('.hero-glow-2').style.transform = `translateY(${-window.scrollY * 0.1}px)`;
});

/* REVEAL */
const obs = new IntersectionObserver((entries) => {
  entries.forEach((e, i) => {
    if (e.isIntersecting) { setTimeout(() => e.target.classList.add('visible'), i * 80); obs.unobserve(e.target); }
  });
}, { threshold: 0.07 });
document.querySelectorAll('.reveal').forEach(el => obs.observe(el));

/* COUNTER */
const runCounter = el => {
  const target = +el.getAttribute('data-target');
  const suffix = el.getAttribute('data-suffix') || '+';
  let count = 0, step = target / 70;
  const update = () => { count += step; if (count < target) { el.innerText = Math.floor(count); requestAnimationFrame(update); } else { el.innerText = target + suffix; } };
  update();
};
const cObs = new IntersectionObserver((entries) => {
  entries.forEach(e => { if (e.isIntersecting) { runCounter(e.target); cObs.unobserve(e.target); } });
}, { threshold: 0.8 });
document.querySelectorAll('.stat-val').forEach(el => cObs.observe(el));

/* THEME */
document.getElementById('themeToggle').addEventListener('click', () => {
  document.body.classList.toggle('light');
  document.getElementById('themeLabel').textContent = document.body.classList.contains('light') ? 'Dark Mode' : 'Light Mode';
});

/* MOBILE NAV */
document.getElementById('hamburger').addEventListener('click', () => document.getElementById('mobileNav').classList.add('open'));
document.getElementById('mobileNavClose').addEventListener('click', () => document.getElementById('mobileNav').classList.remove('open'));
document.querySelectorAll('.mobile-nav-link').forEach(l => l.addEventListener('click', () => document.getElementById('mobileNav').classList.remove('open')));
</script>
</body>
</html>
