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
  --border: rgba(255,255,255,0.09);
  --border-accent: rgba(0,210,140,0.45);
  --accent: #00D28C;
  --accent-bright: #00FFAA;
  --accent-dim: rgba(0,210,140,0.10);
  --accent2: #3B82F6;
  --accent2-dim: rgba(59,130,246,0.10);
  --text-primary: #F0F4FF;
  --text-secondary: #A8B4CC;
  --text-muted: #5A6680;
  --mono: 'IBM Plex Mono', monospace;
  --sans: 'Inter', sans-serif;
  --display: 'Syne', sans-serif;
  --radius: 10px;
  --radius-sm: 6px;
  --glow-green: 0 0 40px rgba(0,210,140,0.14);
}

html { scroll-behavior: smooth; }
body {
  background: var(--bg);
  color: var(--text-primary);
  font-family: var(--sans);
  font-size: 17px;
  font-weight: 400;
  line-height: 1.7;
  overflow-x: hidden;
  cursor: none;
  padding-top: 80px;
}

body::before {
  content: ''; position: fixed; inset: 0;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.85' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.025'/%3E%3C/svg%3E");
  pointer-events: none; z-index: 0;
}

.cursor-dot { width: 8px; height: 8px; background: var(--accent); border-radius: 50%; position: fixed; pointer-events: none; z-index: 9999; transform: translate(-50%,-50%); }
.cursor-ring { width: 32px; height: 32px; border: 1px solid rgba(0,210,140,0.5); border-radius: 50%; position: fixed; pointer-events: none; z-index: 9998; transform: translate(-50%,-50%); transition: width 0.3s, height 0.3s, border-color 0.3s; }
.scroll-progress { position: fixed; top: 0; left: 0; height: 2px; z-index: 200; background: linear-gradient(90deg, var(--accent), var(--accent2)); width: 0%; }

/* NAV */
nav { position: fixed; top: 0; left: 0; right: 0; height: 80px; z-index: 100; display: flex; justify-content: space-between; align-items: center; padding: 0 4rem; border-bottom: 1px solid var(--border); background: rgba(6,8,12,0.92); backdrop-filter: blur(24px); }
.nav-logo { font-family: var(--mono); font-size: 14px; color: var(--accent); letter-spacing: 0.08em; text-decoration: none; font-weight: 500; display: flex; align-items: center; gap: 0.5rem; }
.nav-logo-dot { width: 6px; height: 6px; border-radius: 50%; background: var(--accent); animation: pulse 2s infinite; }
.nav-links { display: flex; gap: 1.5rem; list-style: none; align-items: center; }
.nav-links a { font-family: var(--mono); font-size: 12px; color: var(--text-secondary); text-decoration: none; letter-spacing: 0.14em; text-transform: uppercase; transition: color 0.2s; position: relative; }
.nav-links a::after { content: ''; position: absolute; bottom: -3px; left: 0; width: 0; height: 1px; background: var(--accent); transition: width 0.25s; }
.nav-links a:hover { color: var(--accent); }
.nav-links a:hover::after { width: 100%; }
/* CV pill in nav */
.nav-cv { color: var(--text-secondary) !important; border: 1px solid var(--border) !important; padding: 0.42rem 0.9rem !important; border-radius: var(--radius-sm) !important; display: inline-flex !important; align-items: center !important; gap: 0.35rem !important; transition: all 0.25s !important; font-size: 11px !important; letter-spacing: 0.1em !important; white-space: nowrap; }
.nav-cv::after { display: none !important; }
.nav-cv:hover { color: var(--accent) !important; border-color: var(--border-accent) !important; background: var(--accent-dim) !important; }
/* CTA pill in nav */
.nav-cta { color: var(--accent) !important; border: 1px solid var(--border-accent) !important; padding: 0.45rem 1.1rem; border-radius: var(--radius-sm); background: var(--accent-dim) !important; transition: all 0.25s !important; }
.nav-cta:hover { background: rgba(0,210,140,0.18) !important; box-shadow: var(--glow-green) !important; }
.nav-hamburger { display: none; flex-direction: column; gap: 5px; cursor: pointer; padding: 4px; }
.nav-hamburger span { display: block; width: 22px; height: 2px; background: var(--text-secondary); border-radius: 2px; transition: 0.3s; }

/* THEME TOGGLE */
.theme-toggle { position: fixed; top: 80px; right: 24px; z-index: 999; display: flex; align-items: center; gap: 0.6rem; background: rgba(12,15,22,0.97); border: 1px solid var(--border-accent); padding: 0.55rem 1rem 0.55rem 0.75rem; border-radius: 40px; font-family: var(--mono); font-size: 12px; color: var(--accent); letter-spacing: 0.1em; cursor: pointer; backdrop-filter: blur(12px); transition: all 0.3s; box-shadow: 0 0 20px rgba(0,210,140,0.1), inset 0 1px 0 rgba(255,255,255,0.05); }
.theme-toggle:hover { box-shadow: 0 0 32px rgba(0,210,140,0.25); border-color: var(--accent); }
.theme-toggle-icon { width: 18px; height: 18px; border-radius: 50%; background: conic-gradient(var(--accent) 180deg, transparent 180deg); border: 1px solid rgba(0,210,140,0.5); flex-shrink: 0; transition: transform 0.5s; }
.theme-toggle:hover .theme-toggle-icon { transform: rotate(180deg); }

/* HERO */
.hero { min-height: 100vh; display: flex; align-items: center; padding: 0 6rem; position: relative; overflow: hidden; }
.hero-grid-bg { position: absolute; inset: 0; background-image: linear-gradient(rgba(255,255,255,0.04) 1px, transparent 1px), linear-gradient(90deg, rgba(255,255,255,0.04) 1px, transparent 1px); background-size: 72px 72px; mask-image: radial-gradient(ellipse 80% 70% at 50% 50%, black 10%, transparent 75%); pointer-events: none; }
.hero-glow { position: absolute; top: 10%; left: 0; width: 700px; height: 600px; background: radial-gradient(ellipse, rgba(0,210,140,0.09) 0%, transparent 65%); pointer-events: none; }
.hero-glow-2 { position: absolute; bottom: 5%; right: 0; width: 600px; height: 500px; background: radial-gradient(ellipse, rgba(59,130,246,0.07) 0%, transparent 65%); pointer-events: none; }
.hero-inner { display: grid; grid-template-columns: 1fr 340px; align-items: center; gap: 6rem; position: relative; z-index: 1; width: 100%; max-width: 1200px; margin: 0 auto; padding-top: 2rem; }
.hero-content { min-width: 0; }
.hero-photo-col { display: flex; align-items: center; justify-content: center; }
.hero-photo-wrap { position: relative; width: 320px; height: 320px; flex-shrink: 0; }
.hero-photo-ring { position: absolute; inset: -2px; border-radius: 50%; background: conic-gradient(var(--accent), var(--accent2), #8b5cf6, var(--accent)); animation: spin 8s linear infinite; z-index: 0; }
@keyframes spin { to { transform: rotate(360deg); } }
.hero-photo-ring-mask { position: absolute; inset: 3px; border-radius: 50%; background: var(--bg); z-index: 1; }
.hero-photo-glow { position: absolute; inset: -30px; border-radius: 50%; background: radial-gradient(ellipse, rgba(0,210,140,0.18) 0%, transparent 70%); z-index: -1; animation: glowPulse 3s ease-in-out infinite; }
@keyframes glowPulse { 0%,100% { opacity:0.7; transform:scale(1); } 50% { opacity:1; transform:scale(1.08); } }
.hero-photo { position: absolute; inset: 6px; border-radius: 50%; object-fit: cover; object-position: center top; width: calc(100% - 12px); height: calc(100% - 12px); z-index: 2; display: block; }
.hero-photo-placeholder { position: absolute; inset: 6px; border-radius: 50%; background: rgba(0,210,140,0.05); border: 2px dashed rgba(0,210,140,0.2); display: flex; align-items: center; justify-content: center; z-index: 2; font-family: var(--mono); font-size: 13px; color: var(--accent); opacity: 0.5; }
.hero-photo-badge { position: absolute; bottom: 14px; right: -10px; z-index: 10; display: flex; align-items: center; gap: 0.5rem; background: rgba(12,15,22,0.96); border: 1px solid var(--border-accent); padding: 0.4rem 0.85rem; border-radius: 20px; font-family: var(--mono); font-size: 11px; color: var(--accent); letter-spacing: 0.1em; backdrop-filter: blur(10px); white-space: nowrap; }
.hero-photo-badge::before { content: ''; width: 5px; height: 5px; border-radius: 50%; background: var(--accent); animation: pulse 1.5s infinite; }
.hero-badge { font-family: var(--mono); font-size: 12px; color: var(--accent); letter-spacing: 0.2em; text-transform: uppercase; display: inline-flex; align-items: center; gap: 0.6rem; margin-bottom: 1.4rem; background: var(--accent-dim); border: 1px solid rgba(0,210,140,0.25); padding: 0.4rem 1rem; border-radius: 20px; }
.hero-badge::before { content: ''; width: 6px; height: 6px; border-radius: 50%; background: var(--accent); box-shadow: 0 0 8px var(--accent); animation: pulse 2s infinite; }
@keyframes pulse { 0%,100% { opacity:1; box-shadow:0 0 8px var(--accent); } 50% { opacity:0.5; box-shadow:0 0 3px var(--accent); } }

/* ── HERO NAME — redesigned ── */
/* "I'm" greeting line above the name */
.hero-intro-line {
  font-family: var(--mono);
  font-size: 0.95rem;
  color: var(--text-muted);
  letter-spacing: 0.2em;
  text-transform: uppercase;
  margin-bottom: 0.25rem;
  display: flex;
  align-items: center;
  gap: 0.5rem;
}
.hero-intro-line .wave {
  font-style: normal;
  font-size: 1.1rem;
  animation: waveHand 2.5s ease-in-out infinite;
  display: inline-block;
  transform-origin: 70% 80%;
}
@keyframes waveHand {
  0%,100% { transform: rotate(0deg); }
  20%      { transform: rotate(-18deg); }
  40%      { transform: rotate(16deg); }
  60%      { transform: rotate(-10deg); }
  80%      { transform: rotate(8deg); }
}

.hero-name {
  font-family: var(--display);
  line-height: 1;
  letter-spacing: 0.02em;
  margin-bottom: 0.2rem;
  color: var(--text-primary);
  text-transform: uppercase;
  position: relative;
}
/* First name: slightly smaller than before so both lines feel balanced */
.hero-name .first-name {
  display: block;
  font-size: clamp(1.8rem, 3.0vw, 4.1rem);
  font-weight: 900;
  letter-spacing: -0.02em; /* tighter = fills width better */
  line-height: 0.95;
}
.hero-name .first-name::before, .hero-name .first-name::after { content: attr(data-text); position: absolute; top: 0; left: 0; width: 100%; height: 100%; font-family: var(--display); font-size: inherit; font-weight: 800; letter-spacing: inherit; text-transform: uppercase; overflow: hidden; clip-path: inset(0 0 0 0); }
.hero-name .first-name::before { color: var(--accent); animation: glitch1 6s infinite; opacity: 0; }
.hero-name .first-name::after { color: var(--accent2); animation: glitch2 6s infinite; opacity: 0; }
@keyframes glitch1 { 0%,89%,100% { opacity:0; clip-path:inset(0 0 100% 0); transform:translate(0,0); } 90% { opacity:0.7; clip-path:inset(20% 0 40% 0); transform:translate(-4px,0); } 92% { opacity:0.5; clip-path:inset(60% 0 10% 0); transform:translate(4px,0); } 94% { opacity:0; } }
@keyframes glitch2 { 0%,91%,100% { opacity:0; clip-path:inset(0 0 100% 0); transform:translate(0,0); } 92% { opacity:0.6; clip-path:inset(10% 0 55% 0); transform:translate(5px,0); } 94% { opacity:0.4; clip-path:inset(50% 0 20% 0); transform:translate(-3px,0); } 96% { opacity:0; } }

/* Last name: shimmer gradient, slightly smaller weight for contrast */
.hero-name .last-name {
  display: block;
  font-size: clamp(1.8rem, 3vw, 3.4rem);
  font-weight: 700;
  background: linear-gradient(90deg, var(--accent) 0%, #00FFAA 20%, #fff 38%, var(--accent2) 55%, #8b5cf6 72%, var(--accent) 100%);
  background-size: 250% auto;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  animation: holoShimmer 5s linear infinite;
  position: relative;
  letter-spacing: 0.05em;
}
@keyframes holoShimmer { 0% { background-position: 0% center; } 100% { background-position: 250% center; } }
.hero-name .last-name::after { content: '_'; -webkit-text-fill-color: var(--accent); animation: blink 1.1s step-end infinite; margin-left: 4px; font-weight: 300; opacity: 0.8; }
@keyframes blink { 0%,100%{opacity:0.8} 50%{opacity:0} }
.hero-name-rule { display: block; width: 100%; height: 1px; margin: 0.6rem 0 0.9rem; background: linear-gradient(90deg, var(--accent), var(--accent2), transparent); position: relative; }
.hero-name-rule::after { content: ''; position: absolute; left: 0; top: -2px; width: 6px; height: 5px; background: var(--accent); border-radius: 1px; box-shadow: 0 0 8px var(--accent); animation: ruleDot 3s ease-in-out infinite; }
@keyframes ruleDot { 0%,100% { left: 0; opacity:1; } 50% { left: calc(100% - 6px); opacity: 0.6; } }

.hero-title { display: inline-flex; align-items: center; gap: 0; margin-bottom: 1.6rem; position: relative; }
.hero-title .t-pill { font-family: var(--mono); font-size: clamp(0.75rem, 1.1vw, 0.92rem); font-weight: 500; letter-spacing: 0.18em; text-transform: uppercase; display: inline-flex; align-items: center; gap: 0.5rem; padding: 0.5rem 1.2rem; border-radius: 40px; line-height: 1; position: relative; overflow: hidden; transition: transform 0.2s; }
.hero-title .t-pill:hover { transform: translateY(-2px); }
.hero-title .t-pill-green { background: rgba(0,210,140,0.12); border: 1px solid rgba(0,210,140,0.4); color: var(--accent); }
.hero-title .t-pill-green .t-dot { width: 5px; height: 5px; border-radius: 50%; background: var(--accent); box-shadow: 0 0 6px var(--accent); flex-shrink: 0; animation: pulse 2s infinite; }
.hero-title .t-pill-blue { background: rgba(59,130,246,0.12); border: 1px solid rgba(59,130,246,0.35); color: var(--accent2); margin-left: 0.6rem; }
.hero-title .t-pill-blue .t-dot { width: 5px; height: 5px; border-radius: 50%; background: var(--accent2); box-shadow: 0 0 6px var(--accent2); flex-shrink: 0; }
.hero-desc { max-width: 490px; font-size: 16px; color: var(--text-secondary); line-height: 1.9; margin-bottom: 2rem; border-left: 2px solid var(--border-accent); padding-left: 1.1rem; }
.hero-actions { display: flex; gap: 1rem; align-items: center; flex-wrap: wrap; margin-bottom: 3rem; }
.btn-primary { background: var(--accent); color: #060810; font-family: var(--mono); font-size: 13px; font-weight: 700; letter-spacing: 0.12em; text-transform: uppercase; padding: 0.9rem 2.1rem; border-radius: var(--radius-sm); text-decoration: none; transition: all 0.25s; position: relative; overflow: hidden; }
.btn-primary::after { content: ''; position: absolute; inset: 0; background: rgba(255,255,255,0.15); transform: translateX(-100%); transition: transform 0.35s; }
.btn-primary:hover::after { transform: translateX(0); }
.btn-primary:hover { transform: translateY(-2px); box-shadow: 0 8px 30px rgba(0,210,140,0.35); }
.btn-secondary { font-family: var(--mono); font-size: 13px; color: var(--text-secondary); text-decoration: none; letter-spacing: 0.12em; text-transform: uppercase; display: flex; align-items: center; gap: 0.5rem; border: 1px solid var(--border); padding: 0.9rem 1.6rem; border-radius: var(--radius-sm); transition: all 0.2s; }
.btn-secondary:hover { color: var(--accent); border-color: var(--border-accent); }
.hero-stats { display: flex; gap: 2.5rem; padding-top: 2rem; border-top: 1px solid var(--border); flex-wrap: wrap; }
.stat-val { font-family: var(--display); font-size: 2.4rem; font-weight: 800; color: var(--text-primary); display: block; letter-spacing: -0.02em; }
.stat-label { font-family: var(--mono); font-size: 11px; color: var(--text-muted); letter-spacing: 0.12em; text-transform: uppercase; }

/* SECTIONS */
section { padding: 7rem 6rem; position: relative; z-index: 1; }
.section-label { font-family: var(--mono); font-size: 12px; color: var(--accent); letter-spacing: 0.25em; text-transform: uppercase; margin-bottom: 0.75rem; display: flex; align-items: center; gap: 0.75rem; }
.section-label::before { content: '//'; color: var(--text-muted); }
.section-label::after { content: ''; height: 1px; flex: 0 0 40px; background: var(--border-accent); }
.section-title { font-family: var(--display); font-size: clamp(2.1rem, 3.6vw, 3.1rem); font-weight: 800; letter-spacing: -0.025em; margin-bottom: 0.75rem; color: var(--text-primary); line-height: 1.05; }
.section-subtitle { color: var(--text-secondary); font-size: 16px; max-width: 500px; margin-bottom: 3.5rem; line-height: 1.8; }
.tag { font-family: var(--mono); font-size: 12px; color: var(--text-secondary); background: rgba(255,255,255,0.06); border: 1px solid var(--border); padding: 0.28rem 0.75rem; border-radius: 4px; letter-spacing: 0.05em; transition: all 0.2s; }
.tag.accent-tag { color: var(--accent); border-color: rgba(0,210,140,0.25); background: var(--accent-dim); }
.tag.blue-tag { color: var(--accent2); border-color: rgba(59,130,246,0.25); background: var(--accent2-dim); }

/* EXPERTISE */
#expertise { background: linear-gradient(180deg, var(--bg) 0%, var(--bg-card) 100%); }
#expertise .section-subtitle { margin-bottom: 2rem; }
.expertise-ticker-wrap { overflow: hidden; position: relative; margin-bottom: 0.6rem; }
.expertise-ticker-wrap::before, .expertise-ticker-wrap::after { content: ''; position: absolute; top: 0; bottom: 0; width: 80px; z-index: 2; pointer-events: none; }
.expertise-ticker-wrap::before { left: 0; background: linear-gradient(90deg, var(--bg), transparent); }
.expertise-ticker-wrap::after { right: 0; background: linear-gradient(-90deg, var(--bg), transparent); }
.expertise-ticker { display: flex; gap: 0.75rem; width: max-content; animation: tickerScroll 28s linear infinite; }
.expertise-ticker-wrap:hover .expertise-ticker { animation-play-state: paused; }
@keyframes tickerScroll { 0% { transform: translateX(0); } 100% { transform: translateX(-50%); } }
.expertise-pill { display: inline-flex; align-items: center; gap: 0.55rem; background: var(--bg-card); border: 1px solid var(--border); border-radius: 40px; padding: 0.6rem 1.2rem; font-family: var(--mono); font-size: 13px; letter-spacing: 0.08em; color: var(--text-secondary); white-space: nowrap; transition: all 0.25s; flex-shrink: 0; }
.expertise-pill::before { content: ''; width: 4px; height: 4px; border-radius: 50%; background: var(--accent); box-shadow: 0 0 5px var(--accent); flex-shrink: 0; }
.expertise-ticker-wrap:hover .expertise-pill:hover { color: var(--accent); border-color: var(--border-accent); background: var(--accent-dim); box-shadow: var(--glow-green); }

/* SKILLS */
#skills { background: var(--bg-card); border-top: 1px solid var(--border); border-bottom: 1px solid var(--border); }
.skills-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); gap: 1px; background: var(--border); border: 1px solid var(--border); border-radius: var(--radius); overflow: hidden; }
.skill-block { background: var(--bg-card); padding: 1.1rem 1.25rem; transition: background 0.25s; position: relative; overflow: hidden; }
.skill-block::before { content: ''; position: absolute; top: 0; left: 0; right: 0; height: 2px; background: linear-gradient(90deg, var(--accent), var(--accent2)); transform: scaleX(0); transform-origin: left; transition: transform 0.35s; }
.skill-block:hover { background: rgba(255,255,255,0.04); }
.skill-block:hover::before { transform: scaleX(1); }
.skill-block-header { display: flex; align-items: center; gap: 0.5rem; margin-bottom: 0.75rem; }
.skill-block-icon { font-size: 14px; color: var(--accent); flex-shrink: 0; line-height: 1; }
.skill-block-title { font-family: var(--display); font-size: 0.82rem; font-weight: 700; color: var(--text-primary); letter-spacing: 0.01em; line-height: 1.25; }
.skill-tags { display: flex; flex-wrap: wrap; gap: 0.32rem; }
.skill-tags .tag { font-size: 11px; padding: 0.18rem 0.55rem; border-radius: 3px; }

/* PROJECTS */
#projects { background: var(--bg); }
.projects-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 1.5rem; }
.project-card { background: var(--bg-card); border: 1px solid var(--border); border-radius: var(--radius); overflow: hidden; position: relative; transition: all 0.35s; display: flex; flex-direction: column; }
.project-card:hover { border-color: rgba(0,210,140,0.28); transform: translateY(-6px); box-shadow: 0 24px 60px rgba(0,0,0,0.4), var(--glow-green); }
.project-card-top-bar { height: 2px; background: linear-gradient(90deg, var(--accent), var(--accent2), #8b5cf6); transform: scaleX(0); transform-origin: left; transition: transform 0.4s; }
.project-card:hover .project-card-top-bar { transform: scaleX(1); }
.project-img { width: 100%; height: 200px; object-fit: cover; display: block; }
.project-img-placeholder { width: 100%; height: 200px; background: linear-gradient(135deg, rgba(0,210,140,0.05), rgba(59,130,246,0.05)); display: flex; align-items: center; justify-content: center; font-family: var(--mono); font-size: 12px; color: var(--text-muted); letter-spacing: 0.15em; border-bottom: 1px solid var(--border); position: relative; overflow: hidden; }
.project-img-placeholder::before { content: ''; position: absolute; inset: 0; background-image: linear-gradient(var(--border) 1px, transparent 1px), linear-gradient(90deg, var(--border) 1px, transparent 1px); background-size: 24px 24px; opacity: 0.5; }
.project-body { padding: 1.85rem; flex: 1; display: flex; flex-direction: column; }
.project-number { font-family: var(--mono); font-size: 12px; color: var(--text-muted); margin-bottom: 0.9rem; display: flex; justify-content: space-between; align-items: center; }
.project-type { font-family: var(--mono); font-size: 11px; color: var(--accent); border: 1px solid rgba(0,210,140,0.25); background: var(--accent-dim); padding: 0.22rem 0.7rem; border-radius: 3px; letter-spacing: 0.1em; }
.project-title { font-family: var(--display); font-size: 1.3rem; font-weight: 700; margin-bottom: 0.75rem; letter-spacing: -0.01em; color: var(--text-primary); }
.project-desc { font-size: 15px; color: var(--text-secondary); line-height: 1.85; margin-bottom: 1.3rem; flex: 1; }
.project-stack { display: flex; flex-wrap: wrap; gap: 0.4rem; margin-bottom: 1.3rem; }
.project-link { font-family: var(--mono); font-size: 12px; color: var(--accent2); text-decoration: none; letter-spacing: 0.1em; display: inline-flex; align-items: center; gap: 0.4rem; transition: all 0.2s; text-transform: uppercase; border: 1px solid rgba(59,130,246,0.28); background: var(--accent2-dim); padding: 0.55rem 1.1rem; border-radius: var(--radius-sm); font-weight: 600; align-self: flex-start; }
.project-link:hover { color: var(--accent); border-color: var(--border-accent); background: var(--accent-dim); }

/* TIMELINE */
#experience { background: var(--bg-card); border-top: 1px solid var(--border); border-bottom: 1px solid var(--border); }
.timeline { position: relative; padding-left: 2rem; }
.timeline::before { content: ''; position: absolute; left: 0; top: 8px; bottom: 0; width: 1px; background: linear-gradient(180deg, var(--accent), var(--accent2), transparent); }
.timeline-item { position: relative; padding-bottom: 3.5rem; padding-left: 2.5rem; }
.timeline-item:last-child { padding-bottom: 0; }
.timeline-dot { position: absolute; left: -2.55rem; top: 6px; width: 10px; height: 10px; border-radius: 50%; background: var(--accent); border: 2px solid var(--bg-card); box-shadow: 0 0 16px rgba(0,210,140,0.6); }
.timeline-date { font-family: var(--mono); font-size: 12px; color: var(--text-muted); letter-spacing: 0.15em; text-transform: uppercase; margin-bottom: 0.5rem; }
.timeline-role { font-family: var(--display); font-size: 1.3rem; font-weight: 700; margin-bottom: 0.3rem; color: var(--text-primary); }
.timeline-company { font-family: var(--mono); font-size: 13px; color: var(--accent); margin-bottom: 1rem; }
.timeline-bullets { list-style: none; }
.timeline-bullets li { font-size: 15px; color: var(--text-secondary); padding: 0.3rem 0 0.3rem 1.4rem; position: relative; line-height: 1.75; }
.timeline-bullets li::before { content: '—'; position: absolute; left: 0; color: var(--accent); font-family: var(--mono); font-size: 11px; }

/* CERTIFICATIONS */
#certifications { background: var(--bg); border-top: 1px solid var(--border); border-bottom: 1px solid var(--border); }
.cert-group-label { font-family: var(--mono); font-size: 12px; letter-spacing: 0.2em; text-transform: uppercase; margin-bottom: 1.5rem; padding-bottom: 0.75rem; border-bottom: 1px solid var(--border); font-weight: 500; }
.cert-group-label.green { color: var(--accent); }
.cert-group-label.blue { color: var(--accent2); }
.cert-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(210px, 1fr)); gap: 1.25rem; margin-bottom: 3rem; }
.cert-card { background: var(--bg-card); border: 1px solid var(--border); border-radius: var(--radius); overflow: hidden; transition: all 0.25s; display: flex; flex-direction: column; }
.cert-card:hover { transform: translateY(-4px); border-color: rgba(0,210,140,0.25); box-shadow: var(--glow-green); }
.cert-stripe { height: 3px; background: linear-gradient(90deg, var(--accent), var(--accent2)); flex-shrink: 0; }
.cert-stripe.blue { background: linear-gradient(90deg, var(--accent2), #8b5cf6); }
.cert-preview { position: relative; width: 100%; height: 118px; overflow: hidden; background: linear-gradient(135deg, rgba(0,210,140,0.04), rgba(59,130,246,0.04)); border-bottom: 1px solid var(--border); flex-shrink: 0; cursor: pointer; }
.cert-preview img { width: 100%; height: 100%; object-fit: cover; display: block; transition: transform 0.4s ease; }
.cert-card:hover .cert-preview img { transform: scale(1.05); }
.cert-preview-placeholder { width: 100%; height: 100%; display: flex; flex-direction: column; align-items: center; justify-content: center; gap: 0.4rem; position: relative; }
.cert-preview-placeholder::before { content: ''; position: absolute; inset: 0; background-image: linear-gradient(var(--border) 1px, transparent 1px), linear-gradient(90deg, var(--border) 1px, transparent 1px); background-size: 20px 20px; opacity: 0.4; }
.cert-preview-icon { font-size: 26px; position: relative; z-index: 1; opacity: 0.45; }
.cert-preview-label { font-family: var(--mono); font-size: 10px; letter-spacing: 0.14em; text-transform: uppercase; color: var(--text-muted); position: relative; z-index: 1; }
.cert-preview-overlay { position: absolute; inset: 0; background: rgba(0,210,140,0.12); display: flex; align-items: center; justify-content: center; opacity: 0; transition: opacity 0.25s; z-index: 3; backdrop-filter: blur(2px); }
.cert-card:hover .cert-preview-overlay { opacity: 1; }
.cert-preview-overlay span { font-family: var(--mono); font-size: 11px; letter-spacing: 0.13em; text-transform: uppercase; color: var(--accent); background: rgba(6,8,12,0.9); border: 1px solid var(--border-accent); padding: 0.35rem 0.85rem; border-radius: 20px; }
.cert-body { padding: 1rem 1.1rem; flex: 1; display: flex; flex-direction: column; gap: 0.4rem; }
.cert-title { font-family: var(--display); font-size: 0.86rem; font-weight: 700; line-height: 1.4; color: var(--text-primary); flex: 1; }
.cert-issuer { font-family: var(--mono); font-size: 11px; color: var(--accent); letter-spacing: 0.08em; }
.cert-issuer.blue { color: var(--accent2); }
.cert-view-link { display: inline-flex; align-items: center; gap: 0.32rem; margin-top: 0.5rem; font-family: var(--mono); font-size: 11px; letter-spacing: 0.1em; text-transform: uppercase; color: var(--accent2); text-decoration: none; border: 1px solid rgba(59,130,246,0.25); background: var(--accent2-dim); padding: 0.28rem 0.7rem; border-radius: 4px; align-self: flex-start; transition: all 0.2s; }
.cert-view-link:hover { color: var(--accent); border-color: var(--border-accent); background: var(--accent-dim); }
.cert-view-link.green-link { color: var(--accent); border-color: rgba(0,210,140,0.25); background: var(--accent-dim); }
.cert-view-link.green-link:hover { color: var(--accent-bright); border-color: var(--accent); box-shadow: var(--glow-green); }

/* RECOGNITIONS */
.rec-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 1.5rem; }
.rec-card { background: var(--bg-card); border: 1px solid var(--border); border-radius: var(--radius); overflow: hidden; position: relative; transition: all 0.3s; display: flex; flex-direction: column; }
.rec-card::before { content: ''; position: absolute; top: 0; left: 0; right: 0; height: 2px; background: linear-gradient(90deg, var(--accent), var(--accent2)); z-index: 1; }
.rec-card:hover { transform: translateY(-5px); border-color: rgba(0,210,140,0.25); box-shadow: var(--glow-green); }
.rec-preview { position: relative; width: 100%; height: 130px; overflow: hidden; background: linear-gradient(135deg, rgba(0,210,140,0.04), rgba(59,130,246,0.04)); border-bottom: 1px solid var(--border); flex-shrink: 0; cursor: pointer; }
.rec-preview img { width: 100%; height: 100%; object-fit: cover; display: block; transition: transform 0.4s ease; }
.rec-card:hover .rec-preview img { transform: scale(1.05); }
.rec-preview-placeholder { width: 100%; height: 100%; display: flex; flex-direction: column; align-items: center; justify-content: center; gap: 0.4rem; position: relative; }
.rec-preview-placeholder::before { content: ''; position: absolute; inset: 0; background-image: linear-gradient(var(--border) 1px, transparent 1px), linear-gradient(90deg, var(--border) 1px, transparent 1px); background-size: 20px 20px; opacity: 0.4; }
.rec-preview-emoji { font-size: 34px; position: relative; z-index: 1; }
.rec-preview-overlay { position: absolute; inset: 0; background: rgba(0,210,140,0.12); display: flex; align-items: center; justify-content: center; opacity: 0; transition: opacity 0.25s; z-index: 3; backdrop-filter: blur(2px); }
.rec-card:hover .rec-preview-overlay { opacity: 1; }
.rec-preview-overlay span { font-family: var(--mono); font-size: 11px; letter-spacing: 0.13em; text-transform: uppercase; color: var(--accent); background: rgba(6,8,12,0.9); border: 1px solid var(--border-accent); padding: 0.35rem 0.85rem; border-radius: 20px; }
.rec-body { padding: 1.5rem 1.7rem 1.7rem; flex: 1; display: flex; flex-direction: column; }
.rec-title { font-family: var(--display); font-size: 1.05rem; font-weight: 700; margin-bottom: 0.65rem; color: var(--text-primary); }
.rec-desc { font-size: 15px; color: var(--text-secondary); line-height: 1.8; flex: 1; }
.rec-view-link { display: inline-flex; align-items: center; gap: 0.35rem; margin-top: 1rem; font-family: var(--mono); font-size: 11px; letter-spacing: 0.1em; text-transform: uppercase; color: var(--accent); text-decoration: none; border: 1px solid rgba(0,210,140,0.25); background: var(--accent-dim); padding: 0.3rem 0.75rem; border-radius: 4px; align-self: flex-start; transition: all 0.2s; }
.rec-view-link:hover { color: var(--accent-bright); border-color: var(--accent); box-shadow: var(--glow-green); }

/* CONTACT */
#contact { text-align: center; background: var(--bg); }
.contact-wrapper { max-width: 640px; margin: 0 auto; }
.contact-email { font-family: var(--mono); font-size: clamp(0.82rem, 1.15vw, 0.96rem); font-weight: 700; letter-spacing: 0.22em; text-transform: uppercase; color: #060810; text-decoration: none; display: inline-flex; align-items: center; gap: 0.75rem; margin: 2rem 0; padding: 1.1rem 2.6rem; border-radius: 6px; background: linear-gradient(90deg, var(--accent) 0%, #00FFAA 50%, var(--accent) 100%); background-size: 200% auto; position: relative; overflow: hidden; transition: background-position 0.5s ease, transform 0.25s, box-shadow 0.25s; box-shadow: 0 0 0 1px rgba(0,210,140,0.4), 0 4px 24px rgba(0,210,140,0.25); }
.contact-email::before { content: ''; position: absolute; inset: 0; background: rgba(255,255,255,0.12); transform: translateX(-100%) skewX(-12deg); transition: transform 0.45s ease; }
.contact-email:hover::before { transform: translateX(120%) skewX(-12deg); }
.contact-email:hover { background-position: right center; transform: translateY(-3px); box-shadow: 0 0 0 1px rgba(0,255,170,0.6), 0 10px 40px rgba(0,210,140,0.45); color: #060810; }
.contact-email .mail-icon { display: inline-flex; align-items: center; justify-content: center; width: 20px; height: 20px; background: rgba(0,0,0,0.15); border-radius: 3px; font-size: 13px; flex-shrink: 0; }
.socials { display: flex; justify-content: center; gap: 0.75rem; margin-top: 2rem; flex-wrap: wrap; }
.social-link { font-family: var(--mono); font-size: 12px; color: var(--text-secondary); text-decoration: none; letter-spacing: 0.1em; text-transform: uppercase; display: flex; align-items: center; gap: 0.4rem; border: 1px solid var(--border); padding: 0.7rem 1.2rem; border-radius: var(--radius-sm); transition: all 0.2s; }
.social-link:hover { color: var(--accent); border-color: var(--border-accent); background: var(--accent-dim); transform: translateY(-2px); }

/* FOOTER */
footer { padding: 2rem 6rem; border-top: 1px solid var(--border); display: flex; justify-content: space-between; align-items: center; background: var(--bg-card); }
footer p { font-family: var(--mono); font-size: 12px; color: var(--text-muted); letter-spacing: 0.08em; }
.footer-accent { color: var(--accent); }

/* REVEAL */
.reveal { opacity: 0; transform: translateY(24px); transition: opacity 0.7s ease, transform 0.7s ease; }
.reveal.visible { opacity: 1; transform: none; }

/* STICKY CTA */
.sticky-cta { position: fixed; bottom: 24px; left: 50%; transform: translateX(-50%); background: rgba(12,15,22,0.96); backdrop-filter: blur(16px); border: 1px solid var(--border); padding: 0.5rem 0.6rem; border-radius: 50px; display: flex; gap: 0.5rem; align-items: center; z-index: 300; opacity: 0; pointer-events: none; transition: all 0.4s; box-shadow: 0 8px 32px rgba(0,0,0,0.5); }
.sticky-cta.show { opacity: 1; pointer-events: auto; }
.sticky-cta a { font-family: var(--mono); font-size: 12px; text-decoration: none; padding: 0.5rem 1.1rem; border-radius: 30px; letter-spacing: 0.08em; transition: all 0.2s; }
.sticky-cta .primary { background: var(--accent); color: #060810; font-weight: 700; }
.sticky-cta .primary:hover { background: var(--accent-bright); }
.sticky-cta .secondary { color: var(--text-primary); border: 1px solid var(--border); }
.sticky-cta .secondary:hover { color: var(--accent); border-color: var(--border-accent); }

/* MOBILE NAV */
.mobile-nav { display: none; position: fixed; inset: 0; z-index: 200; background: rgba(6,8,12,0.98); backdrop-filter: blur(24px); flex-direction: column; align-items: center; justify-content: center; gap: 2.5rem; }
.mobile-nav.open { display: flex; }
.mobile-nav-link { font-family: var(--mono); font-size: 19px; color: var(--text-secondary); text-decoration: none; letter-spacing: 0.15em; text-transform: uppercase; transition: color 0.2s; }
.mobile-nav-link:hover { color: var(--accent); }
.mobile-nav-close { position: absolute; top: 1.25rem; right: 1.5rem; font-family: var(--mono); font-size: 22px; color: var(--text-muted); cursor: pointer; background: none; border: none; line-height: 1; }

/* ===================== LIGHT MODE ===================== */
body.light {
  --bg: #f5f7fc;
  --bg-card: #ffffff;
  --text-primary: #0b1220;
  --text-secondary: #374151;
  --text-muted: #6B7280;
  --border: rgba(0,0,0,0.09);
  --border-accent: rgba(0,160,105,0.35);
  --accent: #00935F;
  --accent-bright: #00B876;
  --accent-dim: rgba(0,147,95,0.08);
  --accent2: #1D5FD1;
  --accent2-dim: rgba(29,95,209,0.08);
  --glow-green: 0 0 32px rgba(0,147,95,0.10);
}
body.light nav { background: rgba(245,247,252,0.95); }
body.light .hero-photo-ring-mask { background: var(--bg); }
body.light .theme-toggle { background: rgba(255,255,255,0.98); color: #00614A; }
body.light .expertise-ticker-wrap::before { background: linear-gradient(90deg, var(--bg), transparent); }
body.light .expertise-ticker-wrap::after { background: linear-gradient(-90deg, var(--bg), transparent); }
body.light .sticky-cta { background: rgba(255,255,255,0.95); border-color: rgba(0,0,0,0.1); }
body.light .sticky-cta .secondary { color: var(--text-primary); border-color: var(--border); }
body.light .sticky-cta .primary { color: #ffffff; }
body.light .contact-email { color: #ffffff; }
body.light .contact-email:hover { color: #ffffff; }
body.light .btn-secondary { color: var(--text-primary); }
body.light .hero-name .last-name { background: linear-gradient(90deg, var(--accent) 0%, #00B876 20%, #0b4da8 45%, #6d28d9 65%, var(--accent) 100%); background-size: 250% auto; -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; animation: holoShimmer 5s linear infinite; }
body.light .hero-intro-line { color: var(--text-muted); }

/* RESPONSIVE */
@media (max-width: 1100px) {
  section { padding: 6rem 3rem; } nav { padding: 1rem 3rem; }
  .hero { padding: 0 3rem; } footer { padding: 2rem 3rem; }
  .hero-inner { gap: 4rem; grid-template-columns: 1fr 280px; }
  .hero-photo-wrap { width: 280px; height: 280px; }
}
@media (max-width: 960px) {
  /* hide CV link in nav on smaller screens — it's still in mobile menu */
  .nav-cv { display: none !important; }
}
@media (max-width: 860px) {
  nav { padding: 1rem 1.5rem; }
  .nav-links { display: none; }
  .nav-hamburger { display: flex; }
  .hero { padding: 0 1.5rem; align-items: flex-start; min-height: auto; }
  .hero-inner { display: flex; flex-direction: column; align-items: center; text-align: center; gap: 2.5rem; padding-top: 2rem; padding-bottom: 4rem; }
  .hero-photo-col { order: 0; }
  .hero-content { order: 1; width: 100%; }
}
  .hero-photo-wrap { width: 220px; height: 220px; }
  .hero-photo-badge { bottom: 4px; right: -4px; font-size: 10px; padding: 0.3rem 0.65rem; }
  .hero-badge { justify-content: center; }
  .hero-intro-line { justify-content: center; }
  .hero-desc { margin: 0 auto 2rem; border-left: none; padding-left: 0; border-top: 2px solid var(--border-accent); padding-top: 1rem; }
  .hero-actions { justify-content: center; }
  .hero-stats { justify-content: center; gap: 2rem; }
  .hero-title { justify-content: center; flex-wrap: wrap; }
  section { padding: 4rem 1.5rem; }
  .skills-grid { grid-template-columns: repeat(auto-fill, minmax(150px, 1fr)); }
  .projects-grid { grid-template-columns: 1fr; }
  .cert-grid { grid-template-columns: repeat(auto-fit, minmax(160px, 1fr)); }
  .rec-grid { grid-template-columns: 1fr; }
  footer { flex-direction: column; gap: 0.75rem; text-align: center; padding: 1.5rem; }
  .theme-toggle { top: auto; bottom: 80px; right: 16px; }
}
@media (max-width: 480px) {
  .hero-stats { flex-direction: column; align-items: center; gap: 1.5rem; }
  .stat-val { font-size: 2rem; }
  .hero-name .first-name { font-size: clamp(2.2rem, 11vw, 3rem); }
  .hero-name .last-name { font-size: clamp(1.5rem, 7.5vw, 2rem); }
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

<!-- ① Emoji on logo  ② CV link after logo  ③ "Let's Connect" CTA -->
<nav>
  <a href="#" class="nav-logo">
    <div class="nav-logo-dot"></div>
    👋 Hello, Welcome
  </a>
  <ul class="nav-links">
    <li><a href="#skills">Skills</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#experience">Experience</a></li>
    <li><a href="#certifications">Certs</a></li>
    <li><a href="#recognitions">Recognition</a></li>
    <li>
      <a href="https://drive.google.com/file/d/1IFWvI5BjqUNMbXyBTHfTBnDJVfLt5us7/view?usp=sharing"
         target="_blank" class="nav-cv">
        <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"
             stroke-linecap="round" stroke-linejoin="round">
          <path d="M14 2H6a2 2 0 00-2 2v16a2 2 0 002 2h12a2 2 0 002-2V8z"/>
          <polyline points="14 2 14 8 20 8"/>
          <line x1="12" y1="18" x2="12" y2="12"/>
          <line x1="9" y1="15" x2="15" y2="15"/>
        </svg>
        My CV
      </a>
    </li>
    <li><a href="#contact" class="nav-cta">Let's Connect</a></li>
  </ul>
  <div class="nav-hamburger" id="hamburger"><span></span><span></span><span></span></div>
</nav>

<div class="mobile-nav" id="mobileNav">
  <button class="mobile-nav-close" id="mobileNavClose">&#10005;</button>
  <a href="#skills" class="mobile-nav-link">Skills</a>
  <a href="#projects" class="mobile-nav-link">Projects</a>
  <a href="#experience" class="mobile-nav-link">Experience</a>
  <a href="#certifications" class="mobile-nav-link">Certifications</a>
  <a href="#recognitions" class="mobile-nav-link">Recognition</a>
  <a href="https://drive.google.com/file/d/1IFWvI5BjqUNMbXyBTHfTBnDJVfLt5us7/view?usp=sharing"
     target="_blank" class="mobile-nav-link">Download CV</a>
  <a href="#contact" class="mobile-nav-link" style="color:var(--accent)">Let's Connect</a>
</div>

<!-- HERO -->
<section class="hero" id="hero">
  <div class="hero-grid-bg"></div>
  <div class="hero-glow"></div>
  <div class="hero-glow-2"></div>
  <div class="hero-inner">
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
    <div class="hero-content">
      <div class="hero-badge">Lagos, Nigeria</div>

      <!-- ④ Name redesign: "I'm" intro + CHINEDU large + ELEKWA PROMISE shimmer, both slightly reduced -->
      <h1 class="hero-name">
        <span class="hero-intro-line"><em class="wave">👋</em> I'm</span>
        <span class="first-name" data-text="CHINEDU">CHINEDU</span>
        <span class="last-name">ELEKWA PROMISE</span>
        <span class="hero-name-rule"></span>
      </h1>

      <p class="hero-title">
        <span class="t-pill t-pill-green"><span class="t-dot"></span>Data Analyst</span>
        <span class="t-pill t-pill-blue"><span class="t-dot"></span>Business Intelligence</span>
      </p>
      <p class="hero-desc">Building scalable data solutions and turning raw data into strategic insights. I bring the precision of a mathematician, the clarity of an educator, and the impact-focus of a business analyst to every problem I solve.</p>
      <div class="hero-actions">
        <a href="#projects" class="btn-primary">Explore My Work &#8594;</a>
        <a href="#contact" class="btn-secondary">Let's Connect &#8599;</a>
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
  <div class="expertise-ticker-wrap reveal">
    <div class="expertise-ticker">
      <span class="expertise-pill">Statistical Analytics</span>
      <span class="expertise-pill">Professional Dashboard Design</span>
      <span class="expertise-pill">Digital Marketing Analytics</span>
      <span class="expertise-pill">FMCG Analytics</span>
      <span class="expertise-pill">Data Modeling</span>
      <span class="expertise-pill">Executive-style PowerPoint Reports</span>
      <span class="expertise-pill">Advanced Data Analytics &amp; Visualisation with Python</span>
      <span class="expertise-pill">Statistical Analytics</span>
      <span class="expertise-pill">Professional Dashboard Design</span>
      <span class="expertise-pill">Digital Marketing Analytics</span>
      <span class="expertise-pill">FMCG Analytics</span>
      <span class="expertise-pill">Data Modeling</span>
      <span class="expertise-pill">Executive-style PowerPoint Reports</span>
      <span class="expertise-pill">Advanced Data Analytics &amp; Visualisation with Python</span>
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
      <div class="skill-block-header"><span class="skill-block-icon">&#x2B21;</span><span class="skill-block-title">Languages &amp; Querying</span></div>
      <div class="skill-tags"><span class="tag accent-tag">SQL</span><span class="tag accent-tag">Python</span></div>
    </div>
    <div class="skill-block">
      <div class="skill-block-header"><span class="skill-block-icon">&#9678;</span><span class="skill-block-title">Visualization &amp; BI</span></div>
      <div class="skill-tags"><span class="tag accent-tag">Power BI</span><span class="tag accent-tag">Looker Studio</span><span class="tag">MS PowerPoint</span></div>
    </div>
    <div class="skill-block">
      <div class="skill-block-header"><span class="skill-block-icon">&#9635;</span><span class="skill-block-title">Spreadsheets &amp; Productivity</span></div>
      <div class="skill-tags"><span class="tag accent-tag">MS Excel</span><span class="tag accent-tag">Google Sheets</span><span class="tag accent-tag">Power Query</span><span class="tag">Google Forms</span><span class="tag">Google Workspace</span></div>
    </div>
    <div class="skill-block">
      <div class="skill-block-header"><span class="skill-block-icon">&#9672;</span><span class="skill-block-title">ERP &amp; Operations</span></div>
      <div class="skill-tags"><span class="tag accent-tag">SAP</span></div>
    </div>
    <div class="skill-block">
      <div class="skill-block-header"><span class="skill-block-icon">&#9711;</span><span class="skill-block-title">Cloud &amp; Platforms</span></div>
      <div class="skill-tags"><span class="tag accent-tag">Google Cloud</span><span class="tag">BigQuery</span></div>
    </div>
    <div class="skill-block">
      <div class="skill-block-header"><span class="skill-block-icon">&#9643;</span><span class="skill-block-title">Soft Skills &amp; Leadership</span></div>
      <div class="skill-tags"><span class="tag">Data Mentorship</span><span class="tag">Report Writing</span><span class="tag">Stakeholder Comms</span><span class="tag">Teaching</span><span class="tag">Growth Mindset</span></div>
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
      <div class="project-card-top-bar"></div>
      <div class="project-img-placeholder">[ FMCG Production Analytics ]</div>
      <div class="project-body">
        <div class="project-number"><span>01</span><span class="project-type">Case Study</span></div>
        <div class="project-title">FMCG Production Analytics System</div>
        <div class="project-desc"><strong style="color:var(--text-primary)">Problem:</strong> No visibility into production inefficiencies.<br><br><strong style="color:var(--text-primary)">Approach:</strong> Built a Google Forms + Sheets pipeline tracking output, downtime, and waste.<br><br><strong style="color:var(--text-primary)">Impact:</strong> Analytics efficiency lifted to 95% &#8212; enabling faster operational decisions.</div>
        <div class="project-stack"><span class="tag accent-tag">Google Sheets</span><span class="tag accent-tag">SAP</span><span class="tag">Reporting</span></div>
      </div>
    </div>

    <div class="project-card reveal">
  <div class="project-card-top-bar"></div>

  <img src="images/image.png" alt="RFM Queries" class="project-img"
       onerror="this.style.display='none'">

  <img src="images/RFM Dashboard.jpg" alt="RFM Dashboard" class="project-img"
       onerror="this.style.display='none'">

  <div class="project-img-placeholder" style="display:none">
    [ RFM ANALYSIS (Using SQL and PowerBi) ]
  </div>

  <div class="project-body">
    <div class="project-number">
      <span>02</span>
      <span class="project-type">Business Intelligence</span>
    </div>
    <div class="project-title">Recency Frequency Monetary (RFM) ANALYSIS</div>
    <div class="project-desc">
      This project is a comprehensive RFM (Recency, Frequency, Monetary) Customer Segmentation Analysis implemented in BigQuery. It transforms raw monthly transactional data into actionable marketing segments to help a business identify its most valuable customers and those at risk of churning.
    </div>
    <div class="project-stack">
      <span class="tag accent-tag">Google Big Query</span>
      <span class="tag accent-tag">SQL</span>
      <span class="tag">Window Functions</span>
      <span class="tag">PowerBi</span>
    </div>
    <a href="https://github.com/Nedupelekwa/RFM-ANALYSIS" target="_blank" class="project-link">
      View on GitHub &#8599;
    </a>
  </div>
</div>
    
    <div class="project-card reveal">
      <div class="project-card-top-bar"></div>
      <img src="images/Business-dashboard.jpg" alt="Power BI Business Dashboard" class="project-img" onerror="this.style.display='none';this.nextElementSibling.style.display='flex'">
      <div class="project-img-placeholder" style="display:none">[ Power BI Business Dashboard ]</div>
      <div class="project-body">
        <div class="project-number"><span>02</span><span class="project-type">Business Intelligence</span></div>
        <div class="project-title">Power BI Business Dashboard</div>
        <div class="project-desc">End-to-end sales analytics dashboard revealing key business trends. Key finding: +24.5% YoY Sales growth from 2021&#8211;2022, enabling strategic leadership decisions.</div>
        <div class="project-stack"><span class="tag accent-tag">Power BI</span><span class="tag accent-tag">DAX</span><span class="tag">Power Query</span><span class="tag">MS Excel</span></div>
        <a href="https://github.com/Nedupelekwa/POWERBI-BUSINESS-DASHBOARD" target="_blank" class="project-link">View on GitHub &#8599;</a>
      </div>
    </div>
    
    <div class="project-card reveal">
      <div class="project-card-top-bar"></div>
      <img src="images/Marketing call dashboard.jpg" alt="Marketing Call dashboard" class="project-img" onerror="this.style.display='none';this.nextElementSibling.style.display='flex'">
      <div class="project-body">
        <div class="project-number"><span>03</span><span class="project-type">Marketing Analytics</span></div>
        <div class="project-title">Marketing Call Dashboard</div>
        <div class="project-desc">Developed a comprehensive data tracking system and dashboard to monitor the efficiency of marketing call campaigns across multiple program verticals. This project manages and analyzes a dataset of over 14,000 records to identify conversion trends, communication barriers, and program-specific performance</div>
        <div class="project-stack"><span class="tag accent-tag">Dynamic filters</span><span class="tag">Google Sheets Dashboard</span><span class="tag">Data Reporting</span></div>
        <a href="https://github.com/Nedupelekwa/Marketing-Call-dashboard" target="_blank" class="project-link">View Portfolio &#8599;</a>
      </div>
    </div>

<!-- EXPERIENCE -->
<section id="experience">
  <div class="section-label">Career History</div>
  <h2 class="section-title">Experience</h2>
  <p class="section-subtitle reveal">Where I've built things that matter.</p>
  <div class="timeline reveal">
    <div class="timeline-item">
      <div class="timeline-dot"></div>
      
    <div class="timeline-item">
      <div class="timeline-dot"></div>
      <div class="timeline-date">Sept 2024 &#8212; Feb 2026</div>
      <div class="timeline-role">Production Data Analyst</div>
      <div class="timeline-company">Frutta Juice and Services Limited &middot; Lagos, Nigeria</div>
      <ul class="timeline-bullets">
        <li>Built a Google Forms &amp; Sheets pipeline tracking output, downtime, waste and material usage &#8212; increasing analytics efficiency to 95%</li>
        <li>Managed production inventory end-to-end on SAP from raw materials to warehouse transfer</li>
        <li>Developed production and material plans to ensure continuous operations</li>
        <li>Produced professional stakeholder production reports using PowerPoint</li>
      </ul>
    </div>

    <div class="timeline-date">Sept 2025 &#8212; Present</div>
      <div class="timeline-role">Data Analyst Intern</div>
      <div class="timeline-company">edMotion Technologies &middot; Remote</div>
      <ul class="timeline-bullets">
        <li>Working on data analytics projects in the edtech space, applying SQL and spreadsheet skills to derive insights</li>
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
      </ul>
    </div>
    
    <div class="timeline-item">
      <div class="timeline-dot"></div>
      <div class="timeline-date">Jan 2023 &#8212; Sept 2024</div>
      <div class="timeline-role">Mathematics Educator / Data Analyst</div>
      <div class="timeline-company">Cedec International Secondary School &middot; Lagos, Nigeria</div>
      <ul class="timeline-bullets">
        <li>Built and maintained a student performance database; analysed results with Excel to track progress</li>
        <li>Produced data-backed performance reports for school leadership and parents</li>
        <li>Managed customer relationships and provided mentorship to students</li>
      </ul>
    </div>
    <div class="timeline-item">
      <div class="timeline-dot" style="background:var(--text-muted);box-shadow:none"></div>
      <div class="timeline-date">2020 &#8212; 2021 &middot; 2013 &#8212; 2014</div>
      <div class="timeline-role">Mathematics Educator</div>
      <div class="timeline-company">Great Divine College &amp; Divine Victory Schools &middot; Lagos, Nigeria</div>
      <ul class="timeline-bullets">
        <li>Taught Mathematics at secondary school level &#8212; building the analytical foundations that underpin my data career</li>
      </ul>
    </div>
  </div>
</section>

<!-- CERTIFICATIONS -->
<section id="certifications">
  <div class="section-label">Credentials</div>
  <h2 class="section-title">Certifications and Certificates</h2>
  <p class="section-subtitle reveal">Verified expertise across cloud, analytics, and data science.</p>

  <div class="cert-group-label green reveal">Career Certifications</div>
  <div class="cert-grid reveal">
    <div class="cert-card"><div class="cert-stripe"></div><div class="cert-preview"><img src="images/Google Cloud Data Analytics Certificate.jpg" alt="Google Cloud Data Analyst Certificate" onerror="this.style.display='none';this.nextElementSibling.style.display='flex'"><div class="cert-preview-placeholder" style="display:none"><span class="cert-preview-icon">&#9729;</span><span class="cert-preview-label">Certificate Preview</span></div><div class="cert-preview-overlay"><span>View Certificate &#8599;</span></div></div><div class="cert-body"><div class="cert-title">Google Cloud Data Analyst Certificate</div><div class="cert-issuer">Google Cloud</div><a href="https://www.credly.com/badges/8978d604-f416-4365-bfc5-9bc49dc80c8a/public_url" target="_blank" class="cert-view-link green-link">View Certificate &#8599;</a></div></div>
    <div class="cert-card"><div class="cert-stripe"></div><div class="cert-preview"><img src="images/ALX Data-science-certificate-chinedu-elekwa (1).png" alt="ALX Data Science" onerror="this.style.display='none';this.nextElementSibling.style.display='flex'"><div class="cert-preview-placeholder" style="display:none"><span class="cert-preview-icon">&#9672;</span><span class="cert-preview-label">Certificate Preview</span></div><div class="cert-preview-overlay"><span>View Certificate &#8599;</span></div></div><div class="cert-body"><div class="cert-title">ALX Data Science</div><div class="cert-issuer">ALX Africa</div><a href="https://drive.google.com/file/d/1adgB-IFRJ86S7Y9c0JUY3HwL3YGZ3pPl/view?usp=drive_link" target="_blank" class="cert-view-link green-link">View Certificate &#8599;</a></div></div>
    <div class="cert-card"><div class="cert-stripe"></div><div class="cert-preview"><img src="images/Associate Data Analyst .jpg" alt="DataCamp Associate Data Analyst" onerror="this.style.display='none';this.nextElementSibling.style.display='flex'"><div class="cert-preview-placeholder" style="display:none"><span class="cert-preview-icon">&#9678;</span><span class="cert-preview-label">Certificate Preview</span></div><div class="cert-preview-overlay"><span>View Certificate &#8599;</span></div></div><div class="cert-body"><div class="cert-title">Associate Data Analyst Certificate</div><div class="cert-issuer">DataCamp</div><a href="https://www.datacamp.com/tracks/associate-data-analyst-in-sql?utm_medium=organic_social&utm_campaign=sharewidget&utm_content=trackdetailpage&utm_source=copy" target="_blank" class="cert-view-link green-link">View Certificate &#8599;</a></div></div>
    <div class="cert-card"><div class="cert-stripe"></div><div class="cert-preview"><img src="images/ALX-Data-analytics-certificate-chinedu-elekwa.png" alt="ALX Data Analytics" onerror="this.style.display='none';this.nextElementSibling.style.display='flex'"><div class="cert-preview-placeholder" style="display:none"><span class="cert-preview-icon">&#9711;</span><span class="cert-preview-label">Certificate Preview</span></div><div class="cert-preview-overlay"><span>View Certificate &#8599;</span></div></div><div class="cert-body"><div class="cert-title">ALX Data Analytics</div><div class="cert-issuer">ALX Africa</div><a href="https://drive.google.com/file/d/1mIyLDO280vdvNAHHmWQPQPjv8I8J5PaA/view?usp=drive_link" target="_blank" class="cert-view-link green-link">View Certificate &#8599;</a></div></div>
    <div class="cert-card"><div class="cert-stripe"></div><div class="cert-preview"><img src="images/ALX Python-programming-certificate-chinedu-elekwa (1).png" alt="ALX Python Programming" onerror="this.style.display='none';this.nextElementSibling.style.display='flex'"><div class="cert-preview-placeholder" style="display:none"><span class="cert-preview-icon">&#9711;</span><span class="cert-preview-label">Certificate Preview</span></div><div class="cert-preview-overlay"><span>View Certificate &#8599;</span></div></div><div class="cert-body"><div class="cert-title">ALX Python Programming</div><div class="cert-issuer">ALX Africa</div><a href="https://drive.google.com/file/d/1CGBWo5SJWcrD5WL2-5crNmJzcVIs1qVi/view?usp=drive_link" target="_blank" class="cert-view-link green-link">View Certificate &#8599;</a></div></div>
    <div class="cert-card"><div class="cert-stripe"></div><div class="cert-preview"><img src="images/Microsoft Business Analyst.jpg" alt="Microsoft Business Analyst" onerror="this.style.display='none';this.nextElementSibling.style.display='flex'"><div class="cert-preview-placeholder" style="display:none"><span class="cert-preview-icon">&#9711;</span><span class="cert-preview-label">Certificate Preview</span></div><div class="cert-preview-overlay"><span>View Certificate &#8599;</span></div></div><div class="cert-body"><div class="cert-title">Microsoft Business Analyst Professional Certificate</div><div class="cert-issuer">Microsoft via Coursera</div><a href="https://coursera.org/share/c6567e811cee90cb8fc4cfa63c8aad9c" target="_blank" class="cert-view-link green-link">View Certificate &#8599;</a></div></div>
    <div class="cert-card"><div class="cert-stripe"></div><div class="cert-preview"><img src="images/SQL for Business analysts.jpg" alt="SQL for Business Analysts" onerror="this.style.display='none';this.nextElementSibling.style.display='flex'"><div class="cert-preview-placeholder" style="display:none"><span class="cert-preview-icon">&#9711;</span><span class="cert-preview-label">Certificate Preview</span></div><div class="cert-preview-overlay"><span>View Certificate &#8599;</span></div></div><div class="cert-body"><div class="cert-title">SQL for Business Analysts</div><div class="cert-issuer">DataCamp</div><a href="https://www.datacamp.com/completed/statement-of-accomplishment/track/750b783b48ed45a69debb82aa1741067210f145f" target="_blank" class="cert-view-link green-link">View Certificate &#8599;</a></div></div>
    <div class="cert-card"><div class="cert-stripe"></div><div class="cert-preview"><img src="images/google workspace.jpg" alt="Google Workspace Certificate" onerror="this.style.display='none';this.nextElementSibling.style.display='flex'"><div class="cert-preview-placeholder" style="display:none"><span class="cert-preview-icon">&#9635;</span><span class="cert-preview-label">Certificate Preview</span></div><div class="cert-preview-overlay"><span>View Certificate &#8599;</span></div></div><div class="cert-body"><div class="cert-title">Google Workspace &#8212; Calendar, Drive, Docs, Sheets, Slides</div><div class="cert-issuer">Google via Coursera</div><a href="https://drive.google.com/drive/folders/1y6hDZvx9gvkXm_SD9oOWFSPB0vtAkHSb?usp=drive_link" target="_blank" class="cert-view-link green-link">View Certificate &#8599;</a></div></div>
  </div>

  <div class="cert-group-label blue reveal">Professional &amp; Soft Skills</div>
  <div class="cert-grid reveal">
    <div class="cert-card"><div class="cert-stripe blue"></div><div class="cert-preview"><img src="images/ALX-Professional-foundations-certificate-chinedu-elekwa (1).png" alt="ALX Professional Foundations" onerror="this.style.display='none';this.nextElementSibling.style.display='flex'"><div class="cert-preview-placeholder" style="display:none"><span class="cert-preview-icon">&#9643;</span><span class="cert-preview-label">Certificate Preview</span></div><div class="cert-preview-overlay"><span>View Certificate &#8599;</span></div></div><div class="cert-body"><div class="cert-title">ALX Professional Foundations</div><div class="cert-issuer blue">ALX Africa</div><a href="https://drive.google.com/file/d/1EulTVxF5SmHwMA63BCH7gDclpdnMFohp/view?usp=drive_link" target="_blank" class="cert-view-link">View Certificate &#8599;</a></div></div>
    <div class="cert-card"><div class="cert-stripe blue"></div><div class="cert-preview"><img src="images/Jobberman soft skills.jpg" alt="Jobberman Soft Skills Training" onerror="this.style.display='none';this.nextElementSibling.style.display='flex'"><div class="cert-preview-placeholder" style="display:none"><span class="cert-preview-icon">&#x2B21;</span><span class="cert-preview-label">Certificate Preview</span></div><div class="cert-preview-overlay"><span>View Certificate &#8599;</span></div></div><div class="cert-body"><div class="cert-title">Jobberman Soft Skills Training</div><div class="cert-issuer blue">Jobberman &middot; 2021</div><a href="https://drive.google.com/file/d/17Y-4ZJxH1PjtGGZVE4GO0IZ8D9zmm6sC/view?usp=drive_link" target="_blank" class="cert-view-link">View Certificate &#8599;</a></div></div>
    <div class="cert-card"><div class="cert-stripe blue"></div><div class="cert-preview"><img src="images/Data Literacy.jpg" alt="Data Literacy" onerror="this.style.display='none';this.nextElementSibling.style.display='flex'"><div class="cert-preview-placeholder" style="display:none"><span class="cert-preview-icon">&#x2B21;</span><span class="cert-preview-label">Certificate Preview</span></div><div class="cert-preview-overlay"><span>View Certificate &#8599;</span></div></div><div class="cert-body"><div class="cert-title">Data Literacy Certificate</div><div class="cert-issuer blue">DataCamp</div><a href="https://www.datacamp.com/skill-verification/DL0034034405845" target="_blank" class="cert-view-link">View Certificate &#8599;</a></div></div>
  </div>
</section>

<!-- RECOGNITIONS -->
<section id="recognitions" style="background:var(--bg-card);border-top:1px solid var(--border);border-bottom:1px solid var(--border)">
  <div class="section-label">Recognition</div>
  <h2 class="section-title">Awards &amp; Volunteer Service</h2>
  <div class="rec-grid reveal">
    <div class="rec-card"><div class="rec-preview"><img src="images/NYSC certificate.jpg" alt="NYSC certificate" onerror="this.style.display='none';this.nextElementSibling.style.display='flex'"><div class="rec-preview-placeholder" style="display:none"><span class="rec-preview-emoji">&#127757;</span></div><div class="rec-preview-overlay"><span>View Recognition &#8599;</span></div></div><div class="rec-body"><div class="rec-title">Certificate of Completed Service &#8212; NYSC</div><div class="rec-desc">Completed the one year compulsory national service for Nigerian graduates</div><a href="https://drive.google.com/file/d/11CL2qk2E5tD2hEfotGluMjqMLXON8gKs/view?usp=drive_link" target="_blank" class="rec-view-link">View Recognition &#8599;</a></div></div>
    <div class="rec-card"><div class="rec-preview"><img src="images/recognitions/alx-mentor.jpg" alt="ALX Africa DATA Volunteer Mentor" onerror="this.style.display='none';this.nextElementSibling.style.display='flex'"><div class="rec-preview-placeholder" style="display:none"><span class="rec-preview-emoji">&#127757;</span></div><div class="rec-preview-overlay"><span>View Recognition &#8599;</span></div></div><div class="rec-body"><div class="rec-title">DATA Volunteer Mentor &#8212; ALX Africa</div><div class="rec-desc">Supporting the next generation of data professionals across Africa through hands-on mentorship in analytics, Python programming, and data science since September 2025.</div><a href="https://tinyurl.com/bdhbn9zt" target="_blank" class="rec-view-link">View Recognition &#8599;</a></div></div>
    <div class="rec-card"><div class="rec-preview"><img src="images/Certificate of Recognition DataGlobalHub @GDAI 2025.jpg" alt="GDAI 2025 Session Moderator" onerror="this.style.display='none';this.nextElementSibling.style.display='flex'"><div class="rec-preview-placeholder" style="display:none"><span class="rec-preview-emoji">&#127897;</span></div><div class="rec-preview-overlay"><span>View Recognition &#8599;</span></div></div><div class="rec-body"><div class="rec-title">GDAI 2025 Session Moderator</div><div class="rec-desc">Recognised by DataGlobal Hub with a Certificate of Recognition for Volunteer Service as Session Moderator at the Virtual Global Data &amp; AI Tech Conference (GDAI) 2025.</div><a href="https://drive.google.com/file/d/10qfqjgp9Gb0IXXtZyjED8898NETCoEry/view?usp=drive_link" target="_blank" class="rec-view-link">View Recognition &#8599;</a></div></div>
    <div class="rec-card"><div class="rec-preview"><img src="images/Dataglobal Hub Ambassador.jpg" alt="Ambassador — DataGlobal Hub" onerror="this.style.display='none';this.nextElementSibling.style.display='flex'"><div class="rec-preview-placeholder" style="display:none"><span class="rec-preview-emoji">&#9672;</span></div><div class="rec-preview-overlay"><span>View Recognition &#8599;</span></div></div><div class="rec-body"><div class="rec-title">Ambassador &#8212; DataGlobal Hub</div><div class="rec-desc">Appointed as Ambassador at DataGlobal Hub, representing and advocating for the growth of the data and AI community in Nigeria and across Africa.</div><a href="https://drive.google.com/file/d/16gvU8oEHC-lnasKTStIUVshoT37Y4UO0/view?usp=sharing" target="_blank" class="rec-view-link">View Recognition &#8599;</a></div></div>
  </div>
</section>

<!-- WHY HIRE ME -->
<section id="recruiter" style="background:var(--bg-card);border-top:1px solid var(--border);border-bottom:1px solid var(--border)">
  <div class="section-label">Why Hire Me</div>
  <h2 class="section-title">I Don&#8217;t Just Analyze Data &#8212;<br>I Drive Decisions</h2>
  <div class="rec-grid reveal">
    <div class="rec-card"><div class="rec-body" style="padding-top:1.75rem"><div class="rec-title">&#128202; Business-First Analyst</div><div class="rec-desc">I translate raw data into decisions executives can act on immediately &#8212; not just charts, but clear, actionable intelligence.</div></div></div>
    <div class="rec-card"><div class="rec-body" style="padding-top:1.75rem"><div class="rec-title">&#9881;&#65039; End-to-End Problem Solver</div><div class="rec-desc">From data collection &#8594; cleaning &#8594; modeling &#8594; visualization &#8594; insight delivery. I own the full pipeline.</div></div></div>
    <div class="rec-card"><div class="rec-body" style="padding-top:1.75rem"><div class="rec-title">&#128640; Impact-Oriented Work</div><div class="rec-desc">Every project is tied to measurable business improvement or operational efficiency &#8212; 95% analytics uplift as proof.</div></div></div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="contact-wrapper">
    <div class="section-label" style="justify-content:center">Let&#8217;s Talk</div>
    <h2 class="section-title reveal">Open to the Right<br>Opportunity</h2>
    <p class="section-subtitle reveal" style="margin:0 auto 1rem;text-align:center;max-width:440px">Whether it&#8217;s a full-time role, a freelance project, or just a conversation about data &#8212; I&#8217;d love to hear from you.</p>
    <a href="mailto:chinedupelekwa@gmail.com" class="contact-email reveal">
      <span class="mail-icon">&#9993;</span>
      Send Me a Mail
    </a>
    <div class="socials reveal">
      <a href="https://www.linkedin.com/in/chinedu-elekwa/" target="_blank" class="social-link">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor" xmlns="http://www.w3.org/2000/svg" style="flex-shrink:0"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        LinkedIn
      </a>
      <a href="https://tinyurl.com/bdhbn9zt" target="_blank" class="social-link">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" style="flex-shrink:0"><circle cx="12" cy="12" r="10"/><path d="M8 12l3 3 5-5"/></svg>
        View My Credentials
      </a>
      <a href="https://drive.google.com/file/d/1IFWvI5BjqUNMbXyBTHfTBnDJVfLt5us7/view?usp=sharing" target="_blank" class="social-link">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" style="flex-shrink:0"><path d="M14 2H6a2 2 0 00-2 2v16a2 2 0 002 2h12a2 2 0 002-2V8z"/><polyline points="14 2 14 8 20 8"/><line x1="12" y1="18" x2="12" y2="12"/><line x1="9" y1="15" x2="15" y2="15"/></svg>
        Download My CV
      </a>
      <a href="tel:+2347033130747" class="social-link">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" style="flex-shrink:0"><path d="M22 16.92v3a2 2 0 01-2.18 2 19.79 19.79 0 01-8.63-3.07A19.5 19.5 0 013.07 9.81a19.79 19.79 0 01-3.07-8.67A2 2 0 012 1h3a2 2 0 012 1.72 12.84 12.84 0 00.7 2.81 2 2 0 01-.45 2.11L6.91 8.9a16 16 0 006.19 6.19l1.27-1.27a2 2 0 012.11-.45 12.84 12.84 0 002.81.7A2 2 0 0122 16.92z"/></svg>
        Call Me
      </a>
    </div>
  </div>
</section>

<footer>
  <p>&#169; 2026 <span class="footer-accent">Chinedu Elekwa Promise</span>. All rights reserved.</p>
  <p>Built like a <span class="footer-accent">Data Product</span> &middot; Lagos, Nigeria</p>
</footer>

<div class="sticky-cta" id="stickyCTA">
  <a href="#projects" class="secondary">View Work</a>
  <a href="#contact" class="primary">Let's Connect &#8594;</a>
</div>

<script>
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
window.addEventListener('scroll', () => {
  const pct = (window.scrollY / (document.body.scrollHeight - window.innerHeight)) * 100;
  document.getElementById('scrollProgress').style.width = pct + '%';
  document.getElementById('stickyCTA').classList.toggle('show', window.scrollY > 400);
  document.querySelector('.hero-glow').style.transform = 'translateY(' + (window.scrollY * 0.15) + 'px)';
  document.querySelector('.hero-glow-2').style.transform = 'translateY(' + (-window.scrollY * 0.1) + 'px)';
});
const obs = new IntersectionObserver((entries) => {
  entries.forEach((e, i) => { if (e.isIntersecting) { setTimeout(() => e.target.classList.add('visible'), i * 80); obs.unobserve(e.target); } });
}, { threshold: 0.07 });
document.querySelectorAll('.reveal').forEach(el => obs.observe(el));
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
document.getElementById('themeToggle').addEventListener('click', () => {
  document.body.classList.toggle('light');
  document.getElementById('themeLabel').textContent = document.body.classList.contains('light') ? 'Dark Mode' : 'Light Mode';
});
document.getElementById('hamburger').addEventListener('click', () => document.getElementById('mobileNav').classList.add('open'));
document.getElementById('mobileNavClose').addEventListener('click', () => document.getElementById('mobileNav').classList.remove('open'));
document.querySelectorAll('.mobile-nav-link').forEach(l => l.addEventListener('click', () => document.getElementById('mobileNav').classList.remove('open')));
document.querySelectorAll('.cert-preview').forEach(preview => {
  preview.addEventListener('click', () => { const link = preview.closest('.cert-card').querySelector('.cert-view-link'); if (link) window.open(link.href, '_blank'); });
});
document.querySelectorAll('.rec-preview').forEach(preview => {
  preview.addEventListener('click', () => { const link = preview.closest('.rec-card').querySelector('.rec-view-link'); if (link) window.open(link.href, '_blank'); });
});
</script>
</body>
</html>
