<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Matt Aferzon Portfolio</title>
  <link rel="stylesheet" type="text/css" href="main.css" />
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
          <a href="Matthew_Aferzon_Resume.pdf" target="_blank" download><i class="fas fa-file-download"></i> Resume</a>
          <a href="https://www.linkedin.com/in/matt-aferzon-399a661a1/" target="_blank"><i class="fab fa-linkedin"></i> LinkedIn</a>
          <a href="mailto:matthewaferzon@gmail.com" target="_blank"> <i class="fas fa-envelope"></i> Email</a>
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
