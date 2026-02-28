

<html lang="en">
    <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CHINEDU ELEKWA — Data Analyst Portfolio</title>
    <style>
        /* ========================================
           EDMOTION STARTER PORTFOLIO TEMPLATE
           Clean, simple, and beginner-friendly.

           HOW TO CUSTOMIZE:
           1. Change colors in :root below
           2. Replace [Your Name], text, and images
           3. Update project cards with your work
           4. Adjust skills to match your toolkit
           ======================================== */

        :root {
            --primary: #0f766e;       /* Teal — professional and data-y */
            --primary-light: #ccfbf1;
            --accent: #f59e0b;        /* Amber for highlights */
            --dark: #1e293b;
            --gray: #64748b;
            --light: #f8fafc;
            --white: #ffffff;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            line-height: 1.6;
            color: var(--dark);
        }

        /* ---------- NAVIGATION ---------- */
        nav {
            background: var(--white);
            padding: 1rem 2rem;
            box-shadow: 0 1px 3px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 100;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        nav .logo {
            font-weight: 700;
            font-size: 1.2rem;
            color: var(--primary);
            text-decoration: none;
        }

        nav .nav-links {
            display: flex;
            gap: 2rem;
            list-style: none;
        }

        nav .nav-links a {
            text-decoration: none;
            color: var(--gray);
            font-weight: 500;
            transition: color 0.2s;
        }

        nav .nav-links a:hover {
            color: var(--primary);
        }

        /* ---------- HERO SECTION ---------- */
        .hero {
            text-align: center;
            padding: 6rem 2rem 4rem;
            background: linear-gradient(135deg, var(--light) 0%, var(--primary-light) 100%);
        }

        .hero img {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            object-fit: cover;
            margin-bottom: 1.5rem;
            border: 3px solid var(--primary);
        }

        .hero h1 {
            font-size: 2.5rem;
            margin-bottom: 0.5rem;
        }

        .hero .tagline {
            font-size: 1.2rem;
            color: var(--gray);
            max-width: 650px;
            margin: 0 auto 1.5rem;
        }

        .hero .toolkit-preview {
            display: flex;
            justify-content: center;
            gap: 0.5rem;
            flex-wrap: wrap;
        }

        .hero .toolkit-preview span {
            background: var(--white);
            color: var(--primary);
            padding: 0.3rem 0.8rem;
            border-radius: 15px;
            font-size: 0.85rem;
            font-weight: 500;
            border: 1px solid var(--primary);
        }

        /* ---------- SECTIONS ---------- */
        section {
            max-width: 900px;
            margin: 0 auto;
            padding: 4rem 2rem;
        }

        section h2 {
            font-size: 1.8rem;
            margin-bottom: 1.5rem;
            color: var(--dark);
            border-bottom: 3px solid var(--primary);
            display: inline-block;
            padding-bottom: 0.3rem;
        }

        section p {
            color: var(--gray);
            font-size: 1.05rem;
            margin-bottom: 1rem;
        }

        /* ---------- PROJECTS ---------- */
        .project-card {
            border: 1px solid #e2e8f0;
            border-radius: 10px;
            margin-bottom: 2rem;
            overflow: hidden;
            transition: box-shadow 0.2s, transform 0.2s;
        }

        .project-card:hover {
            box-shadow: 0 6px 20px rgba(0,0,0,0.08);
            transform: translateY(-2px);
        }

        .project-visual {
            width: 100%;
            max-height: 350px;
            object-fit: cover;
            background: var(--light);
            border-bottom: 1px solid #e2e8f0;
        }

        .project-content {
            padding: 1.5rem;
        }

        .project-content h3 {
            font-size: 1.3rem;
            margin-bottom: 0.4rem;
        }

        .project-finding {
            font-size: 1rem;
            color: var(--dark);
            font-weight: 500;
            margin-bottom: 0.5rem;
            padding-left: 0.8rem;
            border-left: 3px solid var(--accent);
        }

        .project-description {
            font-size: 0.95rem;
            color: var(--gray);
            margin-bottom: 1rem;
        }

        .project-tools {
            display: flex;
            gap: 0.5rem;
            flex-wrap: wrap;
            margin-bottom: 1rem;
        }

        .project-tools span {
            background: var(--primary-light);
            color: var(--primary);
            padding: 0.2rem 0.6rem;
            border-radius: 12px;
            font-size: 0.8rem;
            font-weight: 500;
        }

        .project-link {
            color: var(--primary);
            text-decoration: none;
            font-weight: 600;
        }

        .project-link:hover {
            text-decoration: underline;
        }

        /* ---------- TOOLKIT SECTION ---------- */
        .toolkit-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 1.5rem;
            margin-top: 1rem;
        }

        .toolkit-category {
            background: var(--light);
            padding: 1.2rem;
            border-radius: 8px;
        }

        .toolkit-category h4 {
            font-size: 0.85rem;
            text-transform: uppercase;
            letter-spacing: 0.05em;
            color: var(--primary);
            margin-bottom: 0.6rem;
        }

        .toolkit-category ul {
            list-style: none;
        }

        .toolkit-category li {
            color: var(--dark);
            font-size: 0.95rem;
            padding: 0.2rem 0;
        }

        /* ---------- CONTACT ---------- */
        .contact-links {
            display: flex;
            gap: 1.5rem;
            margin-top: 1rem;
            flex-wrap: wrap;
        }

        .contact-links a {
            color: var(--primary);
            text-decoration: none;
            font-weight: 500;
            font-size: 1.05rem;
        }

        .contact-links a:hover {
            text-decoration: underline;
        }

        /* ---------- FOOTER ---------- */
        footer {
            text-align: center;
            padding: 2rem;
            color: var(--gray);
            font-size: 0.9rem;
            border-top: 1px solid #e2e8f0;
        }

        footer .edmotion {
            color: var(--primary);
            font-weight: 600;
        }

        /* ---------- RESPONSIVE ---------- */
        @media (max-width: 600px) {
            .hero h1 {
                font-size: 1.8rem;
            }

            nav .nav-links {
                gap: 1rem;
                font-size: 0.9rem;
            }

            section {
                padding: 3rem 1.5rem;
            }
        }
    </style>
</head>
<body>

    <!-- ======== NAVIGATION ======== -->
    <nav>
        <a href="#" class="logo">CHINEDU ELEKWA</a>
        <ul class="nav-links">
            <li><a href="#about">About</a></li>
            <li><a href="#projects">Projects</a></li>
            <li><a href="#toolkit">Toolkit</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>

    <!-- ======== HERO ======== -->
    <div class="hero">
        <!--
            ✏️ Replace with your photo.
            Upload a photo to your repo and use: src="photo.jpeg"
        -->
        <img src="photo.jpeg" alt="photo.jpg">
        <h1>Hi, I'm Chinedu Elekwa </h1>
        <p class="tagline">Data Analyst |I turn messy business data into clear, actionable insights</p>
        <div class="toolkit-preview">
            <span>SQL</span>
            <span>Python for visualization</span>
            <span>pandas, numpy</span>
            <span>PowerBi/Looker Studio</span>
            <span>Excel/Google Sheets</span>
        </div>
    </div>

    <!-- ======== ABOUT ======== -->
    <section id="about">
        <h2>About Me</h2>
        <p>
            I am skilled in designing Excel/Google Sheet templates and dashboards for professional business analyis. I also apply statistical and analytical proficiency into unearthening business performance and identifying key decision-making trends.

        </p>
        <p>
            I have been practicing Data Analytics in the FMCG sector for about 2 years now while working with Tech Academies as Data Analytics Mentor. These have made me an asset for businesses as a trained and highly-performing data analyst.
        </p>
    </section>

    <!-- ======== PROJECTS ======== -->
    <section id="projects">
        <h2>Projects</h2>

        <!-- PROJECT 1 -->
        <div class="project-card">
            <!--
                ✏️ Replace with your chart/visualization image.
                Save your best chart to images/ folder and reference it here.
                Example: src="Business dashboard.jpg"
            -->
            <img class="project-visual" src="Business dashboard.jpg" alt="Business dashboard.jpg">
            <div class="project-content">
                <h3>POWERBI-BUSINESS-DASHBOARD</h3>
                <!-- Lead with your key finding — this is what hooks readers -->
                <p class="project-finding">Key finding: +24.5 % YoY Sales from 2021 to 2022</p>
                <p class="project-description">
                    PowerBi Business Dashboard for B & D Company comparing sales and profit performances across different product segments and region, from 2020 to 2023
                </p>
                <div class="project-tools">
                    <span>Excel</span>
                    <span>Power Query</span>
                    <span>PowerBi</span>
                </div>
                <a class="project-link" href="https://github.com/Nedupelekwa/POWERBI-BUSINESS-DASHBOARD">View analysis on GitHub →</a>
            </div>
        </div>

        <!-- PROJECT 2 — Copy the project-card block above to add more projects -->

    </section>

    <!-- ======== TOOLKIT ======== -->
    <section id="toolkit">
        <h2>Toolkit</h2>
        <p>Technologies and tools I work with:</p>
        <div class="toolkit-grid">
            <div class="toolkit-category">
                <h4>Languages</h4>
                <ul>
                    <li>SQL</li>
                    <li>Python</li>
                </ul>
            </div>
            <div class="toolkit-category">
                <h4>Visualization</h4>
                <ul>
                    <li>PowerBi</li>
                    <li>Looker Studio</li>
                    <li>Matplotlib</li>
                    <li>Seaborn</li>
                </ul>
            </div>
            <div class="toolkit-category">
                <h4>Data Tools</h4>
                <ul>
                    <li>pandas</li>
                    <li>Excel</li>
                    <li>Jupyter Notebooks</li>
                </ul>
            </div>
            <div class="toolkit-category">
                <h4>Databases</h4>
                <ul>
                    <li>PostgreSQL</li>
                    <li>MySQL</li>
                    <li>SQLite</li>
                </ul>
            </div>
        </div>
    </section>

    <!-- ======== CONTACT ======== -->
    <section id="contact">
        <h2>Contact</h2>
        <p>Interested in working together or have questions about my analysis?</p>
        <div class="contact-links">
            <a href="mailto:chinedupelekwa@gmail.com">Email</a>
            <a href="https://github.com/Nedupelekwa">GitHub</a>
            <a href="https://www.linkedin.com/in/chinedu-elekwa">LinkedIn</a>
        </div>
    </section>

    <!-- ======== FOOTER ======== -->
    <footer>
        Built by Chinedu Elekwa · <span class="edmotion">EdMotion</span> · <span id="year"></span>
    </footer>

    <script>
        document.getElementById('year').textContent = new Date().getFullYear();
    </script>

</body>
</html>


<!-- ================ -->
git add .
git commit -m https-nedupelekwa.github.io
git push
