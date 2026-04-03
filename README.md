:root {
    --bg-dark: #0f172a;       /* Deep Midnight */
    --bg-card: #1e293b;       /* Slate Blue/Gray */
    --accent: #38bdf8;        /* Data Blue */
    --accent-glow: #0ea5e9;   /* Hover Glow */
    --text-main: #f1f5f9;     /* Off-White */
    --text-dim: #94a3b8;      /* Muted Slate */
    --code-font: 'Fira Code', monospace;
}

body {
    background-color: var(--bg-dark);
    color: var(--text-main);
    font-family: 'Inter', -apple-system, sans-serif;
    line-height: 1.6;
    margin: 0;
}

/* Header & Navigation */
header {
    background: rgba(15, 23, 42, 0.8);
    backdrop-filter: blur(10px);
    border-bottom: 1px solid rgba(255, 255, 255, 0.1);
    padding: 1.2rem 0;
    position: sticky;
    top: 0;
    z-index: 100;
}

nav {
    max-width: 1100px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    padding: 0 20px;
}

.logo {
    font-family: var(--code-font);
    font-weight: 700;
    color: var(--accent);
    letter-spacing: -1px;
}

nav ul {
    display: flex;
    list-style: none;
    gap: 30px;
    margin: 0;
}

nav ul li a {
    color: var(--text-dim);
    text-decoration: none;
    font-size: 0.9rem;
    transition: color 0.3s;
}

nav ul li a:hover {
    color: var(--accent);
}

/* Hero Section */
#hero {
    padding: 120px 20px;
    text-align: center;
    max-width: 800px;
    margin: 0 auto;
}

#hero h1 {
    font-size: 3.5rem;
    margin-bottom: 10px;
    background: linear-gradient(to right, #fff, var(--accent));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
}

#hero p {
    color: var(--text-dim);
    font-family: var(--code-font);
    font-size: 1.1rem;
}

/* Grids & Cards */
.skill-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 15px;
    margin-top: 30px;
}

.skill-card {
    background: var(--bg-card);
    border: 1px solid rgba(255, 255, 255, 0.05);
    padding: 25px;
    border-radius: 12px;
    transition: transform 0.3s, border-color 0.3s;
    text-align: left;
}

.skill-card:hover {
    transform: translateY(-5px);
    border-color: var(--accent);
}

.project-item {
    background: linear-gradient(145deg, #1e293b, #0f172a);
    border: 1px solid rgba(255, 255, 255, 0.05);
    padding: 30px;
    margin-bottom: 25px;
    border-radius: 16px;
}

.project-item h3 {
    color: var(--accent);
    margin-top: 0;
}

/* Typography & Accents */
h2 {
    font-size: 2rem;
    border-left: 4px solid var(--accent);
    padding-left: 15px;
    margin-bottom: 40px;
}

footer {
    border-top: 1px solid rgba(255, 255, 255, 0.05);
    padding: 60px 20px;
    text-align: center;
    color: var(--text-dim);
    font-size: 0.85rem;
}
