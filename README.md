<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Chinedu Elekwa Promise | Data Analyst & Analytics Engineer</title>

<style>
:root {
    --primary:#22c55e;
    --accent:#38bdf8;
    --bg:#020617;
    --card:#020617;
    --glass:rgba(15,23,42,0.7);
    --border:rgba(148,163,184,0.15);
    --text:#e2e8f0;
    --muted:#94a3b8;
}

*{margin:0;padding:0;box-sizing:border-box}

body{
    font-family:-apple-system,BlinkMacSystemFont,'Segoe UI',Roboto;
    background:radial-gradient(circle at top,#020617,#000);
    color:var(--text);
    overflow-x:hidden;
}

/* NAV */
nav{
    display:flex;justify-content:space-between;align-items:center;
    padding:1rem 2rem;
    position:sticky;top:0;
    background:rgba(2,6,23,0.85);
    backdrop-filter:blur(14px);
    border-bottom:1px solid var(--border);
}

.logo{color:var(--primary);font-weight:700;letter-spacing:.5px}

.nav-links{display:flex;gap:2rem;list-style:none}
.nav-links a{color:var(--muted);text-decoration:none;font-size:.95rem}
.nav-links a:hover{color:var(--primary)}

/* HERO */
.hero{text-align:center;padding:9rem 2rem 6rem}
.hero h1{font-size:3.2rem;margin-top:1rem;background:linear-gradient(90deg,#22c55e,#38bdf8);-webkit-background-clip:text;color:transparent}
.hero p{color:var(--muted);max-width:650px;margin:1rem auto}

.cta{
    margin-top:1.5rem;
    display:inline-block;
    padding:12px 22px;
    background:linear-gradient(90deg,#22c55e,#38bdf8);
    border-radius:8px;
    color:#000;
    font-weight:600;
    text-decoration:none;
}

.badges{margin-top:1rem}
.badges span{
    border:1px solid var(--border);
    padding:5px 10px;
    margin:4px;
    border-radius:20px;
    font-size:.8rem;
    color:var(--muted);
}

/* SECTIONS */
section{max-width:1100px;margin:auto;padding:4rem 2rem}

h2{margin-bottom:2rem;border-left:4px solid var(--primary);padding-left:10px}

/* CARD */
.card{
    background:var(--glass);
    border:1px solid var(--border);
    border-radius:14px;
    backdrop-filter:blur(14px);
    transition:.3s;
}

.card:hover{
    transform:translateY(-6px);
    box-shadow:0 10px 40px rgba(34,197,94,0.1);
}

/* PROJECTS */
.project-card{overflow:hidden}
.project-image{width:100%;height:240px;object-fit:cover}
.project-content{padding:1.5rem}

.project-tools span{
    background:#22c55e22;
    padding:5px 10px;
    border-radius:20px;
    font-size:.75rem;
    margin-right:5px;
}

.project-btn{
    display:inline-block;
    margin-top:1rem;
    padding:10px 16px;
    background:var(--accent);
    color:#000;
    border-radius:6px;
    text-decoration:none;
    font-weight:600;
}

/* GRID */
.grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(250px,1fr));gap:1.5rem}

/* EXPERIENCE */
.timeline{border-left:2px solid var(--primary);padding-left:20px}
.timeline-item{margin-bottom:2rem}

/* CERTIFICATIONS */
.cert-item{padding:0;overflow:hidden}
.cert-image{
    width:100%;
    height:180px;
    object-fit:cover;
    border-bottom:1px solid var(--border);
}
.cert-content{padding:1.2rem}
.cert-item h3{margin-bottom:.5rem}
.cert-item span{color:var(--muted);font-size:.9rem}

/* RECOGNITION */ */
.rec-item{padding:1.5rem}
.rec-item p{color:var(--muted)}

/* SKILLS */
.skill{padding:1.2rem;text-align:center;font-weight:500}

/* CONTACT */
.contact a{margin-right:1rem;color:var(--accent);text-decoration:none}

footer{text-align:center;padding:2rem;color:var(--muted)}

</style>
</head>

<body>

<nav>
<div class="logo">Chinedu Elekwa Promise</div>
<ul class="nav-links">
<li><a href="#projects">Projects</a></li>
<li><a href="#experience">Experience</a></li>
<li><a href="#certifications">Certifications</a></li>
<li><a href="#recognitions">Recognitions</a></li>
<li><a href="#skills">Skills</a></li>
<li><a href="#contact">Contact</a></li>
</ul>
</nav>

<section class="hero">
<h1>Chinedu Elekwa Promise</h1>
<p>Data Analyst & Aspiring Analytics Engineer building scalable data solutions and turning raw data into strategic insights.</p>

<div class="badges">
<span>SQL</span><span>Python</span><span>dbt</span><span>Power BI</span><span>Data Modeling</span>
</div>

<a href="#projects" class="cta">Explore My Work</a>
</section>

<section id="projects">
<h2>Projects</h2>

<div class="grid">

<div class="card project-card">
<img src="https://via.placeholder.com/800x400" class="project-image">
<div class="project-content">
<h3>End-to-End Data Pipeline</h3>
<p>Designed ETL pipelines transforming raw datasets into analytics-ready models.</p>
<div class="project-tools"><span>dbt</span><span>SQL</span><span>Snowflake</span></div>
<a href="#" class="project-btn">View Case Study</a>
</div>
</div>

<div class="card project-card">
<img src="https://via.placeholder.com/800x400" class="project-image">
<div class="project-content">
<h3>Executive Sales Dashboard</h3>
<p>Delivered real-time KPIs improving executive decision-making.</p>
<div class="project-tools"><span>Power BI</span><span>DAX</span></div>
<a href="#" class="project-btn">View Dashboard</a>
</div>
</div>

</div>
</section>

<section id="experience">
<h2>Experience</h2>
<div class="timeline">
<div class="timeline-item">
<h3>Data Analyst</h3>
<span>Company • 2024 - Present</span>
<p>Built dashboards, automated reports, and optimized SQL queries.</p>
</div>
</div>
</section>

<section id="certifications">
<h2>Certifications</h2>

<h3 style="margin-bottom:1rem;color:var(--primary)">Career Certifications</h3>
<div class="grid">
<div class="card cert-item">
<img src="https://via.placeholder.com/400x200" class="cert-image" alt="certificate">
<div class="cert-content">
<h3>Google Cloud Data Analyst Certificate</h3>
<span>Google Cloud</span>
</div>
</div>

<div class="card cert-item">
<img src="https://via.placeholder.com/400x200" class="cert-image">
<div class="cert-content">
<h3>ALX Africa Data Analytics, Python Programming & Data Science</h3>
<span>ALX Africa</span>
</div>
</div>

<div class="card cert-item">
<img src="https://via.placeholder.com/400x200" class="cert-image">
<div class="cert-content">
<h3>DataCamp Associate Data Analyst</h3>
<span>DataCamp</span>
</div>
</div>

<div class="card cert-item">
<img src="https://via.placeholder.com/400x200" class="cert-image">
<div class="cert-content">
<h3>Data Literacy Certificate</h3>
<span>Professional Certification</span>
</div>
</div>

<div class="card cert-item">
<img src="https://via.placeholder.com/400x200" class="cert-image">
<div class="cert-content">
<h3>Google Workspace (Calendar, Drive, Docs, Sheets, Slides)</h3>
<span>Google via Coursera</span>
</div>
</div>
</div>

<h3 style="margin:3rem 0 1rem;color:var(--accent)">AI & Soft Skills Certifications</h3>
<div class="grid">

<div class="card cert-item">
<img src="https://via.placeholder.com/400x200" class="cert-image">
<div class="cert-content">
<h3>ALX Professional Foundations</h3>
<span>ALX Africa</span>
</div>
</div>

<div class="card cert-item">
<img src="https://via.placeholder.com/400x200" class="cert-image">
<div class="cert-content">
<h3>Jobberman Soft Skills Training</h3>
<span>Jobberman • 2021</span>
</div>
</div>

</div>
</section>

<section id="recognitions">
<h2>Recognitions</h2>
<div class="grid">
<div class="card rec-item">
<h3>Top Analyst Award</h3>
<p>Recognized for delivering high-impact insights.</p>
</div>
<div class="card rec-item">
<h3>Mentor Excellence</h3>
<p>Helped train upcoming data analysts.</p>
</div>
</div>
</section>

<section id="skills">
<h2>Skills</h2>
<div class="grid">
<div class="card skill">SQL</div>
<div class="card skill">Python</div>
<div class="card skill">dbt</div>
<div class="card skill">Power BI</div>
<div class="card skill">Data Modeling</div>
<div class="card skill">ETL</div>
</div>
</section>

<section id="contact" class="contact">
<h2>Contact</h2>
<a href="mailto:chinedupelekwa@gmail.com">Email</a>
<a href="https://www.linkedin.com/in/chinedu-elekwa/" target="_blank">LinkedIn</a>
<a href="https://github.com/Nedupelekwa" target="_blank">GitHub</a>
</section>

<footer>
<p>© 2026 Chinedu Elekwa Promise — Built like a Data Product</p>
</footer>

</body>
</html>
