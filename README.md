<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Stephen Ufot | Analytics Portfolio</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&family=Fira+Code:wght@400;500&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --bg-midnight: #0a0f1a;
            --bg-card: #111827;
            --accent-cyan: #22d3ee;
            --accent-blue: #3b82f6;
            --text-primary: #f8fafc;
            --text-secondary: #94a3b8;
            --border-subtle: rgba(255, 255, 255, 0.08);
            --mono-font: 'Fira Code', monospace;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            background-color: var(--bg-midnight);
            color: var(--text-primary);
            font-family: 'Inter', sans-serif;
            line-height: 1.7;
            overflow-x: hidden;
        }

        /* --- NAVIGATION --- */
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1.5rem 10%;
            background: rgba(10, 15, 26, 0.8);
            backdrop-filter: blur(12px);
            position: sticky;
            top: 0;
            z-index: 1000;
            border-bottom: 1px solid var(--border-subtle);
        }

        .logo {
            font-family: var(--mono-font);
            font-weight: 700;
            color: var(--accent-cyan);
            font-size: 1.2rem;
            letter-spacing: -1px;
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        nav a {
            text-decoration: none;
            color: var(--text-secondary);
            font-size: 0.85rem;
            font-weight: 500;
            transition: 0.3s;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        nav a:hover {
            color: var(--accent-cyan);
        }

        /* --- HERO SECTION --- */
        #hero {
            height: 80vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 0 20px;
            background: radial-gradient(circle at center, #1e293b 0%, #0a0f1a 70%);
        }

        .status-badge {
            font-family: var(--mono-font);
            background: rgba(34, 211, 238, 0.1);
            color: var(--accent-cyan);
            padding: 5px 15px;
            border-radius: 20px;
            font-size: 0.75rem;
            margin-bottom: 20px;
            border: 1px solid rgba(34, 211, 238, 0.3);
        }

        #hero h1 {
            font-size: clamp(2.5rem, 8vw, 4.5rem);
            font-weight: 700;
            letter-spacing: -2px;
            margin-bottom: 1rem;
            background: linear-gradient(to bottom, #fff 40%, #64748b);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        #hero p {
            color: var(--text-secondary);
            font-size: 1.2rem;
            max-width: 600px;
            font-family: var(--mono-font);
        }

        /* --- CONTENT SECTIONS --- */
        section {
            padding: 100px 10%;
            max-width: 1200px;
            margin: 0 auto;
        }

        h2 {
            font-size: 1.8rem;
            margin-bottom: 3rem;
            display: flex;
            align-items: center;
            gap: 15px;
        }

        h2::after {
            content: "";
            height: 1px;
            flex-grow: 1;
            background: var(--border-subtle);
        }

        /* --- SKILLS GRID --- */
        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
        }

        .skill-card {
            background: var(--bg-card);
            border: 1px solid var(--border-subtle);
            padding: 30px;
            border-radius: 12px;
            transition: all 0.3s ease;
        }

        .skill-card:hover {
            border-color: var(--accent-cyan);
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
        }

        .skill-card h3 {
            font-family: var(--mono-font);
            font-size: 0.9rem;
            color: var(--accent-cyan);
            margin-bottom: 10px;
        }

        /* --- PROJECTS --- */
        .project-card {
            background: linear-gradient(145deg, #111827, #0a0f1a);
            border: 1px solid var(--border-subtle);
            border-radius: 16px;
            padding: 40px;
            margin-bottom: 30px;
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .project-tag {
            font-family: var(--mono-font);
            font-size: 0.7rem;
            color: var(--text-secondary);
            text-transform: uppercase;
        }

        .project-card h3 {
            font-size: 1.5rem;
            color: var(--text-primary);
        }

        /* --- FOOTER --- */
        footer {
            padding: 80px 10%;
            border-top: 1px solid var(--border-subtle);
            text-align: center;
        }

        .contact-btn {
            display: inline-block;
            padding: 15px 35px;
            background: var(--accent-cyan);
            color: var(--bg-midnight);
            text-decoration: none;
            font-weight: 700;
            border-radius: 4px;
            margin-top: 20px;
            transition: 0.3s;
        }

        .contact-btn:hover {
            background: #fff;
            transform: scale(1.05);
        }

        @media (max-width: 768px) {
            nav ul { display: none; }
            #hero h1 { font-size: 2.5rem; }
        }
    </style>
</head>
<body>

    <nav>
        <div class="logo">S_UFOT.db</div>
        <ul>
            <li><a href="#about">Philosophy</a></li>
            <li><a href="#skills">Stack</a></li>
            <li><a href="#projects">Repositories</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>

    <section id="hero">
        <div class="status-badge">● AVAILABLE FOR NEW PIPELINES</div>
        <h1>Stephen Ufot</h1>
        <p>> Turning chaotic data into scalable architecture and actionable intelligence.</p>
    </section>

    <section id="about">
        <h2>01. Philosophy</h2>
        <p style="max-width: 700px; color: var(--text-secondary);">
            I bridge the gap between raw data and business strategy. My focus is on building robust analytics engineering workflows and data models that don't just report history, but predict future operational needs.
        </p>
    </section>

    <section id="skills">
        <h2>02. Technical Stack</h2>
        <div class="skills-container">
            <div class="skill-card">
                <h3>// DATA_ENGINEERING</h3>
                <p>SQL, Python, dbt, Data Modeling, ETL/ELT Pipelines.</p>
            </div>
            <div class="skill-card">
                <h3>// ANALYTICS_BI</h3>
                <p>Power BI, Advanced Excel, DAX, Dashboard Automation.</p>
            </div>
            <div class="skill-card">
                <h3>// LOW_CODE_OPS</h3>
                <p>Power Automate, Power Apps, Dataverse Architecture.</p>
            </div>
        </div>
    </section>

    <section id="projects">
        <h2>03. Featured Repositories</h2>
        
        <div class="project-card">
            <span class="project-tag">Case Study: Operations</span>
            <h3>Production Optimization Engine</h3>
            <p style="color: var(--text-secondary);">Developed a custom analytics layer that reduced data latency by 60%, enabling real-time monitoring of production metrics and automated stakeholder reporting.</p>
        </div>

        <div class="project-card">
            <span class="project-tag">Architecture: Dataverse</span>
            <h3>Enterprise Workflow Automation</h3>
            <p style="color: var(--text-secondary);">Architected a multi-stage Power Automate solution integrated with SQL databases to eliminate manual data entry in supply chain logging.</p>
        </div>
    </section>

    <section id="contact">
        <div style="text-align: center;">
            <h2>04. Initialize Connection</h2>
            <p>Looking for a data-driven partner? Let's build something efficient.</p>
            <a href="mailto:stephen@example.com" class="contact-btn">GET IN TOUCH</a>
        </div>
    </section>

    <footer>
        <p style="font-family: var(--mono-font); font-size: 0.7rem;">
            SYSTEM_STATUS: ONLINE | &copy; 2026 | STEPHEN UFOT
        </p>
    </footer>

</body>
</html>
