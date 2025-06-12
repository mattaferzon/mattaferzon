<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Your Portfolio</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Manrope:wght@300;400;600&display=swap');

    :root {
      --bg-color: #0a192f;
      --bg-color-2: #112240;
      --accent-color: #60a5fa;
      --text-color: #e5ffee;
      --muted-color: #e5ffee;
      --border-color: #112240;
      --header-border-color: #60a5fa;
      --selected-filter-bg: #60a5fa;
      --selected-filter-text: #0a192f;
    }

    [data-theme="light"] {
      --bg-color: #b8d0e8;
      --bg-color-2: #60a5fa;
      --accent-color: #112240;
      --text-color: #1a3b2f;
      --muted-color: #1a3b2f;
      --border-color: #b8d0e8;
      --header-border-color: #112240;
      --selected-filter-bg: #112240;
      --selected-filter-text: #f1e7dc;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: 'Manrope', sans-serif;
      background: var(--bg-color);
      color: var(--text-color);
      line-height: 1.6;
      transition: background 0.3s, color 0.3s;
    }

    header {
      background-color: var(--bg-color-2);
      padding: 20px 40px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      border-bottom: 1px solid var(--border-color);
    }

    header h1 {
      font-size: 1.8rem;
      color: var(--accent-color);
      font-weight: 700;
    }

    nav a {
      color: var(--accent-color);
      margin-left: 20px;
      text-decoration: none;
      font-weight: 600;
      position: relative;
      transition: color 0.3s;
    }

    nav a:hover {
      color: var(--text-color);
    }

    .toggle-theme {
      cursor: pointer;
      background: none;
      border: 2px solid var(--header-border-color);
      color: var(--accent-color);
      padding: 6px 10px;
      border-radius: 6px;
      margin-left: 20px;
      transition: background 0.3s ease, color 0.3s ease;
    }

    .toggle-theme:hover {
      background: var(--selected-filter-bg);
      color: var(--selected-filter-text);
    }

    .toggle-theme::before {
      content: '🌙';
    }

    [data-theme="light"] .toggle-theme::before {
      content: '☀️';
    }

    .content {
      padding: 40px;
      max-width: 1000px;
      margin: auto;
      transition: opacity 0.4s ease;
    }

    .hidden {
      display: none;
    }

    .home-container {
      background: var(--bg-color-2);
      border: 2px solid var(--accent-color);
      border-radius: 12px;
      padding: 20px;
      display: flex;
      flex-wrap: wrap;
      gap: 55px;
      align-items: center;
    }

    .home-text {
      flex: 1;
    }

    .profile-pic {
      width: 35%;
      border-radius: 10px;
      border: 2px solid var(--bg-color);
      flex-shrink: 0;
    }

    h2 {
      color: var(--accent-color);
      margin-bottom: 20px;
      font-size: 2rem;
    }

    p {
      color: var(--muted-color);
      margin-bottom: 20px;
      font-size: 1rem;
    }

    .resume-links {
      margin-top: 15px;
    }

    .resume-links a {
      color: var(--accent-color);
      border: 2px solid var(--accent-color);
      color: var(--accent-color);
      padding: 2px 6px;
      border-radius: 5px;
      margin-right: 20px;
      text-decoration: none;
      text-align: center;
      font-weight: 600;
      transition: color 0.3s ease;
    }

    .resume-links a:hover {
      background: var(--selected-filter-bg);
      color: var(--selected-filter-text);
    }

    .resume-links i {
      margin-right: 0px;
    }

    .filter-bar {
      margin-bottom: 20px;
    }

    .filter-bar button {
      background: none;
      border: 2px solid var(--accent-color);
      color: var(--accent-color);
      padding: 6px 12px;
      border-radius: 5px;
      margin-right: 10px;
      cursor: pointer;
      transition: background 0.3s ease, color 0.3s ease;
    }

    .filter-bar button:hover,
    .filter-bar button.active {
      background: var(--selected-filter-bg);
      color: var(--selected-filter-text);
    }

    .portfolio-item {
      background: var(--bg-color-2);
      border: 2px solid var(--accent-color);
      border-radius: 12px;
      padding: 20px;
      margin-bottom: 30px;
      display: flex;
      align-items: center;
      cursor: pointer;
      transition: transform 0.3s ease, box-shadow 0.3s ease;
    }

    .portfolio-item:hover {
      transform: translateY(-5px);
      box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
    }

    .portfolio-item img {
      width: 140px;
      height: 100px;
      object-fit: cover;
      border-radius: 10px;
      margin-right: 20px;
    }

    .portfolio-item h3 {
      color: var(--accent-color);
      font-size: 1.3rem;
      margin-bottom: 6px;
    }

    .portfolio-item p {
      color: var(--muted-color);
      font-size: 0.9rem;
    }

    .portfolio-details {
      background: var(--bg-color-2);
      padding: 30px;
      border-radius: 12px;
    }

    .portfolio-details a {
      display: inline-block;
      margin-top: 20px;
      font-weight: 600;
      color: var(--accent-color);
      text-decoration: underline;
    }

    @media (max-width: 700px) {
      .portfolio-item {
        flex-direction: column;
        text-align: center;
      }

      .portfolio-item img {
        margin-bottom: 15px;
        margin-right: 0;
      }

      .home-container {
        flex-direction: column;
        text-align: center;
      }
    }

    
  </style>
  <script src="https://kit.fontawesome.com/a076d05399.js" crossorigin="anonymous"></script>
</head>
<body>
  <header>
    <h1>Matthew Aferzon</h1>
    <nav>
      <a href="#" onclick="showTab('home')">Home</a>
      <a href="#" onclick="showTab('portfolio')">Portfolio</a>
      <button class="toggle-theme" onclick="toggleTheme()"></button>
    </nav>
  </header>

  <div class="content" id="home">
    <h2>About Me</h2>
    <div class="home-container">
      <div class="home-text">
        <p>Hi, I'm Matt! I’m a marketing and design generalist with experience across industries ranging from Series A startups to large global firms. My work includes web page design, branded flyers and graphics, internal dashboards, social media content, campaign/CRM management, data analysis, and much more. I consider myself a lifelong learner and am always excited to pick up new skills. I have contributed to teams in tech, finance, e-commerce, and professional services, blending visual design with strategic insight to drive communication and business goals. Outside of work, I enjoy staying active at the rock climbing gym, exploring UI/UX design, hunting for treasures at the thrift store, and immersing myself in music.</p>
        <div class="resume-links">
          <a href="Matthew_Aferzon_Resume.pdf" download><i class="fas fa-file-download"></i> Resume</a>
          <a href="https://www.linkedin.com/in/matt-aferzon-399a661a1/" target="_blank"><i class="fab fa-linkedin"></i> LinkedIn</a>
          <a href="mailto:matthewaferzon@gmail.com"><i class="fas fa-envelope"></i> Email</a>
        </div>
      </div>
      <img src="LinkedIn Headshot.jpeg" alt="Headshot" class="profile-pic">
    </div>
  </div>

  <div class="content hidden" id="portfolio">
    <h2>My Work</h2>
    <div class="filter-bar">
      <button onclick="filterProjects('all')" id="filter-all">All</button>
      <button onclick="filterProjects('design')" id="filter-design">Design</button>
      <button onclick="filterProjects('development')" id="filter-development">Development</button>
      <button onclick="filterProjects('writing')" id="filter-writing">Writing</button>
      <button onclick="filterProjects('data')" id="filter-data">Data</button>
    </div>
    <div class="portfolio-item" data-category="design" onclick="showTab('project1')">
      <img src="thumbnail1.jpg" alt="Project 1 Thumbnail">
      <div>
        <h3>Design Project</h3>
        <p>Short description of a design-focused project.</p>
      </div>
    </div>
    <div class="portfolio-item" data-category="development" onclick="showTab('project2')">
      <img src="thumbnail2.jpg" alt="Project 2 Thumbnail">
      <div>
        <h3>Development Project</h3>
        <p>Short description of a development-focused project.</p>
      </div>
    </div>
  </div>

  <div class="content hidden" id="project1">
    <div class="portfolio-details">
      <h2>Design Project</h2>
      <p>Detailed page for the design project, including process, results, and visuals.</p>
      <a href="#portfolio" onclick="showTab('portfolio')">← Back to Portfolio</a>
    </div>
  </div>

  <div class="content hidden" id="project2">
    <div class="portfolio-details">
      <h2>Development Project</h2>
      <p>Detailed page for the development project, including tools, code, and outcomes.</p>
      <a href="#portfolio" onclick="showTab('portfolio')">← Back to Portfolio</a>
    </div>
  </div>

  <script>
    function showTab(tabId) {
      document.querySelectorAll('.content').forEach(function(section) {
        section.classList.add('hidden');
      });
      document.getElementById(tabId).classList.remove('hidden');
    }

    function toggleTheme() {
      const currentTheme = document.documentElement.getAttribute('data-theme');
      document.documentElement.setAttribute('data-theme', currentTheme === 'light' ? 'dark' : 'light');
    }

    function filterProjects(category) {
      const items = document.querySelectorAll('.portfolio-item');
      const buttons = document.querySelectorAll('.filter-bar button');

      buttons.forEach(btn => btn.classList.remove('active'));
      document.getElementById('filter-' + category).classList.add('active');

      items.forEach(item => {
        if (category === 'all' || item.getAttribute('data-category') === category) {
          item.style.display = 'flex';
        } else {
          item.style.display = 'none';
        }
      });
    }

    document.documentElement.setAttribute('data-theme', 'dark');
  </script>
</body>
</html>
