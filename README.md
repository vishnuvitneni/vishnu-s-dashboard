<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Your Name - Portfolio</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <style>
    body { margin: 0; font-family: 'Verdana', 'Geneva', 'Tahoma', 'Trebuchet MS', , sans-serif; background::backdrop; color::checkmark; transition: background 0.3s, color 0.3s;}
    header {
      background: linear-gradient(90deg, #105249 0%, #3c074d 100%);
      color: #0a9aee; padding: 48px 0 36px 0; text-align: center; position: relative;
      overflow: hidden;
    }
    header h1 { margin: 0; font-size: 2.8em; letter-spacing: 2px; }
    header p { margin: 14px 0 0 0; font-size: 1.3em; color: #c8d336; }
    .header-wave {
      position: absolute; left: 0; bottom: 0; width: 100%; height: 60px; z-index: 1;
    }
    nav {
      background: #424577; text-align: center; box-shadow: 0 2px 8px rgba(2, 29, 34, 0.04);
      position: sticky; top: 0; z-index: 10;
    }
    nav a {
      display: inline-block; color: #cadddb; text-decoration: none; padding: 16px 24px;
      transition: background 0.2s, color 0.2s;
      font-weight: 700;
      letter-spacing: 1px;
    }
    nav a:hover, nav a.active { background: #38bd9b; color: #031994; }
    .container { max-width: 1200px; margin: 39px auto; padding: 0 23px; }
    section { margin-bottom: 48px; }
    h2 { color: #075e54; margin-bottom: 18px; font-size: 2em; }
    .about { background: #812a2a; padding: 28px; border-radius: 12px; box-shadow: 0 2px 12px rgba(0,0,0,0.04);}
    .profile-img {
      width: 120px; height: 120px; border-radius: 50%; object-fit: cover; border: 4px solid #25d366;
      margin: 0 auto 18px auto; display: block; box-shadow: 0 2px 12px rgba(0,0,0,0.08);
    }
    .projects {
      display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); gap: 28px;
    }
    .project {
      background: #7690b8; border-radius: 16px; padding: 24px; box-shadow: 0 2px 12px rgba(0,0,0,0.06);
      transition: box-shadow 0.2s, transform 0.2s;
      position: relative;
      overflow: hidden;
      border-top: 4px solid #3147a5;
      display: flex; flex-direction: column; justify-content: space-between;
      min-height: 220px;
    }
    .project:hover {
      box-shadow: 0 8px 24px rgba(37,211,102,0.18);
      transform: translateY(-6px) scale(1.03);
      border-top: 4px solid #075e54;
    }
    .project-title { font-size: 1.15em; font-weight: bold; margin-bottom: 10px; color: #25d366;}
    .project-links {
      margin-top: 12px;
    }
    .project-links a {
      display: inline-block;
      background: #e74b0d;
      color: #3b0e0e;
      padding: 6px 16px;
      border-radius: 16px;
      text-decoration: none;
      margin-right: 8px;
      font-size: 0.97em;
      transition: background 0.2s;
    }
    .project-links a:hover { background: #075e54; }
    .skills-list {
      display: flex; flex-wrap: wrap; gap: 12px;
    }
    .skill {
      background: linear-gradient(90deg, #051312 0%, #492727 100%);
      color: #d5fffa; padding: 7px 18px; border-radius: 16px;
      font-size: 1em; margin-bottom: 6px; font-weight: 500; box-shadow: 0 1px 4px rgba(0,0,0,0.04);
      transition: background 0.2s;
    }
    .skill:hover { background: #1931b9; color: #c2b9be; }
    .contact-form {
      background: #744545; padding: 28px; border-radius: 18px; box-shadow: 0 2px 12px rgba(133, 68, 68, 0.04);
    }
    .contact-form label { display: block; margin-bottom: 6px; }
    .contact-form input, .contact-form textarea {
      width: 100%; padding: 12px; margin-bottom: 16px; border: 1px solid #214766; border-radius: 6;
      font-size: 1em; transition: border 0.2s;
    }
    .contact-form input:focus, .contact-form textarea:focus { border: 1.5px solid #25d366; outline: none; }
    .contact-form button {
      background: linear-gradient(90deg, #9c8a82 0%, #0b688d 100%);
      color: #f8efef; border: none; padding: 12px 28px; border-radius: 4px;
      font-size: 1em; cursor: pointer; transition: background 0.2s;
      font-weight: 600;
    }
    .contact-form button:hover { background: #8c5712; }
    .extra-features {
      background: #97c56b; padding: 28px; border-radius: 12px; margin-bottom: 48px;
      box-shadow: 0 2px 12px rgba(0,0,0,0.04);
    }
    .feature-list {
      list-style: none; padding: 0; margin: 0;
      display: flex; flex-wrap: wrap; gap: 18px;
    }
    .feature-list li {
      margin-bottom: 0; padding-left: 28px; position: relative; min-width: 180px;
      font-size: 1.07em;
    }
    .feature-list li:before {
      content: "★";
      color: #4f795e;
      position: absolute;
      left: 0;
    }
    .theme-toggle {
      background: #25d366; color: #fff; border: none; border-radius: 16px; padding: 10px 22px;
      font-size: 1em; cursor: pointer; margin-bottom: 18px; transition: background 0.2s;
      font-weight: 600;
      box-shadow: 0 1px 4px rgba(0,0,0,0.04);
    }
    .theme-toggle:hover { background: #128c7e; }
    .scroll-top-btn {
      position: fixed; bottom: 30px; right: 30px; background: #075e54; color: #fff;
      border: none; border-radius: 50%; width: 52px; height: 52px; font-size: 1.7em;
      cursor: pointer; display: none; align-items: center; justify-content: center;
      box-shadow: 0 2px 8px rgba(0,0,0,0.15);
      z-index: 1000; transition: background 0.2s;
    }
    .scroll-top-btn.show { display: flex; }
    .scroll-top-btn:hover { background: #25d366; }
    
    /* Animated gradient border for project cards */
    .project::after {
      content: "";
      position: absolute;
      inset: 0;
      border-radius: 16px;
      padding: 2px;
      background: linear-gradient(270deg, #25d366, #075e54, #25d366, #075e54);
      background-size: 400% 400%;
      z-index: 0;
      opacity: 0;
      transition: opacity 0.3s;
      pointer-events: none;
      animation: gradientMove 6s ease infinite;
    }
    .project:hover::after { opacity: 1; }
    .project > * { position: relative; z-index: 1; }
    @keyframes gradientMove {
      0% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
      100% { background-position: 0% 50%; }
    }
    /* Dark theme */
    .dark-theme {
      background: #181818 !important;
      color: #792626 !important;
    }
    .dark-theme header {
      background: linear-gradient(90deg, #232526 0%, #414345 100%);
      color: #fff;
    }
    .dark-theme nav { background: #232526; }
    .dark-theme nav a { color: #eee; }
    .dark-theme nav a:hover, .dark-theme nav a.active { background: #25d366; color: #fff; }
    .dark-theme section, .dark-theme .about, .dark-theme .project, .dark-theme .contact-form, .dark-theme .extra-features, .dark-theme .testimonial-section {
      background: #232526 !important;
      color: #2b3b24 !important;
      box-shadow: 0 2px 12px rgba(0,0,0,0.25);
    }
    .dark-theme .skill { background: #333; color: #25d366; }
    .dark-theme .feature-list li:before { color: #25d366; }
    .dark-theme .scroll-top-btn { background: #232526; color: #25d366; }
    .dark-theme .scroll-top-btn:hover { background: #25d366; color: #fff; }
    /* Animated scroll indicator */
    .scroll-indicator {
      position: fixed;
      top: 0; left: 0; height: 4px; background: linear-gradient(90deg, #25d366, #075e54);
      z-index: 9999; width: 0;
      transition: width 0.2s;
    }
    @media (max-width: 600px) {
      header h1 { font-size: 1.5em; }
      .container { padding: 0 8px; }
      .projects { grid-template-columns: 1fr; }
      .feature-list { flex-direction: column; gap: 8px; }
    }
  </style>
</head>
<body>
  <div class="scroll-indicator" id="scrollIndicator"></div>
  <header>
    <img src="![profile](https://github.com/user-attachments/assets/4cbcbdb4-a46a-40f0-a077-ac3b087db4e6)
" alt="vishnu" class="profile-img">
    <h1>vitneni vishnu</h1>
    <p>Web Developer & Designer</p>
    <svg class="header-wave" viewBox="0 0 1440 60" fill="none" xmlns="http://www.w3.org/2000/svg"><path fill="#f4f4f4" d="M0,30 C360,60 1080,0 1440,30 L1440,60 L0,60 Z"></path></svg>
  </header>
  <nav>
    <a href="#about">About</a>
    <a href="#projects">Projects</a>
    <a href="#skills">Skills</a>
    <a href="#features">Features</a>
    <a href="#testimonials">Testimonials</a>
    <a href="#contact">Contact</a>
  </nav>
  <div class="container">
    <section id="about" class="about">
      <h2>About Me</h2>
      <p>
        Hello! I'm vishnu, a passionate web developer with experience in building modern, responsive websites and web applications. I love turning ideas into reality using code and design.
      </p>
    </section>
    <section id="projects">
      <h2>Projects</h2>
      <div class="projects">
        <div class="project">
          <div class="project-title">Portfolio Website</div>
          <div>
            A personal website to showcase my work and skills. Built with HTML, CSS, and JavaScript.<br>
            <strong>Features:</strong> Responsive design, dark/light mode, animated cards, contact form.<br>
            <div class="project-links">
              <a href="https://github.com/yourusername/portfolio" target="_blank">GitHub</a>
            </div>
          </div>
        </div>
        <div class="project">
          <div class="project-title">Chat App</div>
          <div>
            Real-time chat application using Node.js and Socket.io with a modern UI.<br>
            <strong>Features:</strong> Live messaging, user authentication, emoji support, group chats.<br>
            <div class="project-links">
              <a href="https://yourchatapp.demo" target="_blank">Demo</a>
            </div>
          </div>
        </div>
        <div class="project">
          <div class="project-title">E-commerce Store</div>
          <div>
            Responsive online store with shopping cart and payment integration.<br>
            <strong>Features:</strong> Product search, secure checkout, order history, admin dashboard.<br>
            <div class="project-links">
              <a href="https://github.com/yourusername/ecommerce" target="_blank">GitHub</a>
            </div>
          </div>
        </div>
        <div class="project">
          <div class="project-title">Blog Platform</div>
          <div>
            Full-featured blogging platform with Markdown support, user authentication, and comments.<br>
            <strong>Features:</strong> Rich text editor, tags, likes, comment moderation.<br>
            <div class="project-links">
              <a href="https://yourblog.demo" target="_blank">Demo</a>
            </div>
          </div>
        </div>
        <div class="project">
          <div class="project-title">Weather Dashboard</div>
          <div>
            Weather app using OpenWeatherMap API, showing real-time weather and forecasts for any city.<br>
            <strong>Features:</strong> Search by city, 5-day forecast, animated weather icons.<br>
            <div class="project-links">
              <a href="https://github.com/yourusername/weather-dashboard" target="_blank">GitHub</a>
            </div>
          </div>
        </div>
        <div class="project">
          <div class="project-title">Task Manager</div>
          <div>
            Productivity tool to manage daily tasks, deadlines, and priorities with a drag-and-drop interface.<br>
            <strong>Features:</strong> Kanban board, reminders, progress tracking.<br>
            <div class="project-links">
              <a href="https://yourtasks.demo" target="_blank">Demo</a>
            </div>
          </div>
        </div>
        <div class="project">
          <div class="project-title">AI Image Generator</div>
          <div>
            Web app that generates images from text prompts using an AI model (DALL·E API integration).<br>
            <strong>Features:</strong> Text-to-image, gallery, download images.<br>
            <div class="project-links">
              <a href="https://github.com/yourusername/ai-image-generator" target="_blank">GitHub</a>
            </div>
          </div>
        </div>
        <div class="project">
          <div class="project-title">Expense Tracker</div>
          <div>
            Track personal expenses and visualize spending habits with interactive charts.<br>
            <strong>Features:</strong> Add/edit/delete expenses, category breakdown, monthly reports.<br>
            <div class="project-links">
              <a href="https://yourexpensetracker.demo" target="_blank">Demo</a>
            </div>
          </div>
        </div>
        <div class="project">
          <div class="project-title">Recipe Finder</div>
          <div>
            Search for recipes by ingredients and dietary preferences.<br>
            <strong>Features:</strong> API integration, favorites, nutrition info.<br>
            <div class="project-links">
              <a href="https://github.com/yourusername/recipe-finder" target="_blank">GitHub</a>
            </div>
          </div>
        </div>
        <div class="project">
          <div class="project-title">Portfolio Generator</div>
          <div>
            Tool to generate customizable portfolio templates for developers.<br>
            <strong>Features:</strong> Live preview, export to HTML/CSS, theme switcher.<br>
            <div class="project-links">
              <a href="https://yourportfoliogenerator.demo" target="_blank">Demo</a>
            </div>
          </div>
        </div>
      </div>
    </section>
    <section id="skills">
      <h2>Skills</h2>
      <div class="skills-list">
        <span class="skill">HTML</span>
        <span class="skill">CSS</span>
        <span class="skill">JavaScript</span>
        <span class="skill">React</span>
        <span class="skill">Node.js</span>
        <span class="skill">Python</span>
        <span class="skill">UI/UX Design</span>
        <span class="skill">TypeScript</span>
        <span class="skill">MongoDB</span>
        <span class="skill">Figma</span>
        <span class="skill">Next.js</span>
        <span class="skill">Tailwind CSS</span>
      </div>
    </section>
    <section id="features" class="extra-features">
      <h2>Extra Features</h2>
      <button class="theme-toggle" id="themeToggle">Toggle Dark Mode</button>
      <ul class="feature-list">
        <li>Dark/Light Theme Switcher</li>
        <li>Scroll to Top Button</li>
        <li>Testimonials Section</li>
        <li>Responsive Design</li>
        <li>Animated Project Cards</li>
        <li>Accessible Forms</li>
       
        <li>Animated Scroll Indicator</li>
        <li>Active Navigation Highlight</li>
      </ul>
   
    <section id="contact">
      <h2>Contact</h2>
      <form class="contact-form" id="contactForm">
        <label for="name">Name</label>
        <input type="text" id="name" required>
        <label for="email">Email</label>
        <input type="email" id="email" required>
        <label for="message">Message</label>
        <textarea id="message" rows="4" required></textarea>
        <button type="submit">Send</button>
        <div id="formMsg" style="margin-top:10px;color:#128c7e;"></div>
      </form>
    </section>
  </div>
  <button class="scroll-top-btn" id="scrollTopBtn" title="Scroll to top">&#8679;</button>
  <footer>
    &copy; 2025 Your Name. All rights reserved.
  </footer>
  <script>
    // Contact form handler
    document.getElementById('contactForm').addEventListener('submit', function(e) {
      e.preventDefault();
      document.getElementById('formMsg').textContent = "Thank you for reaching out!";
      this.reset();
    });

    // Theme toggle
    const themeToggle = document.getElementById('themeToggle');
    themeToggle.addEventListener('click', function() {
      document.body.classList.toggle('dark-theme');
      if(document.body.classList.contains('dark-theme')) {
        themeToggle.textContent = "Toggle Light Mode";
      } else {
        themeToggle.textContent = "Toggle Dark Mode";
      }
    });

    // Scroll to top button
    const scrollTopBtn = document.getElementById('scrollTopBtn');
    window.addEventListener('scroll', function() {
      if (window.scrollY > 300) {
        scrollTopBtn.classList.add('show');
      } else {
        scrollTopBtn.classList.remove('show');
      }
      // Scroll indicator
      const scrollIndicator = document.getElementById('scrollIndicator');
      const docHeight = document.documentElement.scrollHeight - window.innerHeight;
      const scrolled = (window.scrollY / docHeight) * 100;
      scrollIndicator.style.width = scrolled + "%";
    });
    scrollTopBtn.addEventListener('click', function() {
      window.scrollTo({ top: 0, behavior: 'smooth' });
    });

    // Navigation active link highlight
    const navLinks = document.querySelectorAll('nav a');
    window.addEventListener('scroll', () => {
      let fromTop = window.scrollY + 80;
      navLinks.forEach(link => {
        let section = document.querySelector(link.getAttribute('href'));
        if (section && section.offsetTop <= fromTop && section.offsetTop + section.offsetHeight > fromTop) {
          navLinks.forEach(l => l.classList.remove('active'));
          link.classList.add('active');
        }
      });
    });
  </script>
</body>
</html>
