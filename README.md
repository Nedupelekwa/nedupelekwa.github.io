<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My Portfolio</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      line-height: 1.6;
      background: #0f172a;
      color: #f1f5f9;
    }header {
  background: #020617;
  padding: 20px;
  position: sticky;
  top: 0;
}

nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

nav h1 {
  margin: 0;
  color: #38bdf8;
}

nav ul {
  list-style: none;
  display: flex;
  gap: 20px;
  margin: 0;
  padding: 0;
}

nav ul li a {
  color: #f1f5f9;
  text-decoration: none;
}

section {
  padding: 60px 20px;
  max-width: 1000px;
  margin: auto;
}

.hero {
  text-align: center;
  padding: 100px 20px;
}

.hero h2 {
  font-size: 2.5rem;
  margin-bottom: 10px;
}

.btn {
  display: inline-block;
  margin-top: 20px;
  padding: 10px 20px;
  background: #38bdf8;
  color: #020617;
  text-decoration: none;
  border-radius: 5px;
}

.projects {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 20px;
}

.card {
  background: #020617;
  padding: 20px;
  border-radius: 10px;
}

footer {
  text-align: center;
  padding: 20px;
  background: #020617;
}

  </style>
</head>
<body><header>
  <nav>
    <h1>MyPortfolio</h1>
    <ul>
      <li><a href="#about">About</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>
</header><section class="hero">
  <h2>Hello, I'm Chinedu 👋</h2>
  <p>Aspiring Data Analyst | Cloud Enthusiast | Tech Learner</p>
  <a href="#projects" class="btn">View My Work</a>
</section><section id="about">
  <h2>About Me</h2>
  <p>
    I am passionate about data, cloud computing, and solving real-world problems with technology.
    I am currently learning tools like Excel, SQL, Azure, and Python to build impactful solutions.
  </p>
</section><section id="projects">
  <h2>Projects</h2>
  <div class="projects">
    <div class="card">
      <h3>Sales Data Analysis</h3>
      <p>Analyzed sales data using Excel to uncover trends and insights.</p>
    </div>
    <div class="card">
      <h3>Azure Data Project</h3>
      <p>Built a cloud-based data solution using Azure services.</p>
    </div>
    <div class="card">
      <h3>SQL Database Project</h3>
      <p>Designed and queried a relational database for business insights.</p>
    </div>
  </div>
</section><section id="contact">
  <h2>Contact Me</h2>
  <p>Email: youremail@example.com</p>
  <p>LinkedIn: linkedin.com/in/yourprofile</p>
</section><footer>
  <p>© 2026 Chinedu Elekwa. All rights reserved.</p>
</footer></body>
</html>
