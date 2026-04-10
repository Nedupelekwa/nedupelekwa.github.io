<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Chinedu Elekwa Promise | Data Analyst</title>

<meta name="referrer" content="no-referrer" />

<script>
  if (window.top !== window.self) {
    window.top.location = window.self.location;
  }
</script>

<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;500;600;700;800&family=IBM+Plex+Mono:wght@300;400;500&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet" />

<style>
/* ===================== ROOT THEME SYSTEM ===================== */
:root {
  --bg:#080A0E;
  --bg-card:#0E1117;
  --text:#ffffff;
  --muted:#AAB4C8;
  --accent:#00D28C;
  --accent2:#3B82F6;
  --border:rgba(255,255,255,0.08);
}

body.light {
  --bg:#F7F8FC;
  --bg-card:#FFFFFF;
  --text:#0B0F19;
  --muted:#4B5565;
  --border:rgba(0,0,0,0.08);
}

/* ===================== BASE ===================== */
*{margin:0;padding:0;box-sizing:border-box}
body{
  background:var(--bg);
  color:var(--text);
  font-family:Inter;
  overflow-x:hidden;
  transition:0.3s ease;
}

section{padding:6rem 4rem}

/* ===================== NAV ===================== */
nav{
  position:fixed;top:0;left:0;right:0;
  display:flex;justify-content:space-between;
  padding:1rem 3rem;
  background:rgba(10,12,18,0.8);
  backdrop-filter:blur(10px);
  z-index:100;
}
.nav-links{display:flex;gap:1.5rem;list-style:none}
.nav-links a{color:var(--muted);text-decoration:none;font-size:12px}

/* THEME TOGGLE */
.theme-toggle{
  cursor:pointer;
  border:1px solid var(--border);
  padding:6px 10px;
  border-radius:6px;
  color:#fff; /* REQUIRED FIX */
}

/* ===================== HERO ===================== */
.hero{
  min-height:100vh;
  display:flex;
  align-items:center;
  padding:8rem 4rem 4rem;
}

/* FIX MOBILE LAYOUT ISSUE */
.hero-inner{
  display:flex;
  align-items:center;
  justify-content:space-between;
  gap:3rem;
  width:100%;
}

/* IMPORTANT FIX: prevents photo dropping too far */
.hero-photo-col{flex-shrink:0}

.hero-photo{
  width:280px;height:280px;
  border-radius:50%;
  object-fit:cover;
  border:2px solid var(--accent);
}

/* ===================== SKILLS ===================== */
.skills{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(240px,1fr));
  gap:1rem;
}

/* ===================== CASE STUDY MODE ===================== */
.case-toggle{
  background:var(--bg-card);
  border:1px solid var(--border);
  padding:1rem;
  cursor:pointer;
  margin-bottom:1rem;
}

.case-content{
  display:none;
  padding:1rem;
  border-left:2px solid var(--accent);
  margin-bottom:2rem;
}

/* ===================== LIVE DASHBOARD ===================== */
.dashboard-grid{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(300px,1fr));
  gap:1.5rem;
}

iframe{
  width:100%;
  height:250px;
  border:1px solid var(--border);
  border-radius:10px;
}

/* ===================== RECRUITER TRAP ===================== */
.recruiter-trap{
  display:none;
  background:#0b1220;
  padding:2rem;
  border:1px dashed var(--accent);
  margin-top:2rem;
}

/* show only if enabled */
.recruiter-trap.show{display:block}

/* ===================== MOBILE FIX ===================== */
@media(max-width:900px){
  .hero-inner{
    flex-direction:column-reverse;
    text-align:center;
  }

  .hero-photo{
    width:200px;height:200px;
    margin-bottom:1rem;
  }
}
</style>
</head>

<body>

<!-- NAV -->
<nav>
  <div style="color:var(--accent)">Chinedu Portfolio</div>

  <ul class="nav-links">
    <li><a href="#skills">Skills</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#dashboard">Live Data</a></li>
  </ul>

  <div style="display:flex;gap:10px;align-items:center;">
    <div class="theme-toggle" onclick="toggleTheme()">☀ / ☾</div>
  </div>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-inner">

    <div>
      <h1 style="font-size:3rem">Chinedu Elekwa</h1>
      <p style="color:var(--muted)">Data Analyst | Analytics Engineer</p>
    </div>

    <div class="hero-photo-col">
      <img src="images/My-photo.jpeg" class="hero-photo">
    </div>

  </div>
</section>

<!-- SKILLS -->
<section id="skills">
  <h2>My Technical Expertise</h2>
  <div class="skills">
    <div>Statistical Analytics</div>
    <div>Dashboard Design</div>
    <div>Python Analytics</div>
    <div>Data Modeling</div>
  </div>
</section>

<!-- CASE STUDY MODE -->
<section>
  <h2>Case Study Mode</h2>

  <div class="case-toggle" onclick="toggleCase(this)">
    FMCG Production Analytics (Click to expand)
  </div>
  <div class="case-content">
    Built a production analytics pipeline improving efficiency by 95%.
  </div>

  <div class="case-toggle" onclick="toggleCase(this)">
    Business Intelligence Dashboard
  </div>
  <div class="case-content">
    Delivered insights that improved decision-making by leadership.
  </div>
</section>

<!-- LIVE DASHBOARD -->
<section id="dashboard">
  <h2>Live Dashboard Embeds</h2>

  <div class="dashboard-grid">
    <iframe src="https://public.tableau.com"></iframe>
    <iframe src="https://app.powerbi.com"></iframe>
  </div>
</section>

<!-- RECRUITER TRAP -->
<section>
  <button onclick="document.querySelector('.recruiter-trap').classList.toggle('show')">
    Recruiter Mode
  </button>

  <div class="recruiter-trap">
    <h3>ATS Keywords</h3>
    <p>SQL, Python, Power BI, Data Modeling, FMCG Analytics, Forecasting</p>
  </div>
</section>

<script>

/* ================= THEME TOGGLE ================= */
function toggleTheme(){
  document.body.classList.toggle('light');
}

/* ================= CASE STUDY ================= */
function toggleCase(el){
  const content = el.nextElementSibling;
  content.style.display = content.style.display === "block" ? "none" : "block";
}

/* ================= MOBILE FIX (safety enhancement) ================= */
window.addEventListener("resize", ()=>{
  document.querySelector(".hero-photo-col").style.order = "2";
});

</script>

</body>
</html>
