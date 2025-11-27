<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Developer Portfolio</title>
    <style>
        :root {
            --primary: #3b82f6;
            --primary-hover: #2563eb;
            --dark: #1f2937;
            --light: #f9fafb;
            --text: #374151;
            --border: #e5e7eb;
            --accent: #8b5cf6;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
            line-height: 1.6;
            color: var(--text);
            background: var(--light);
        }

        header {
            background: linear-gradient(135deg, var(--dark) 0%, #111827 100%);
            color: white;
            padding: 2rem 0;
            border-bottom: 3px solid var(--primary);
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
        }

        nav {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 700;
            background: linear-gradient(135deg, var(--primary), var(--accent));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        nav ul {
            list-style: none;
            display: flex;
            gap: 2rem;
        }

        nav a {
            color: white;
            text-decoration: none;
            transition: color 0.3s;
            font-size: 0.95rem;
        }

        nav a:hover {
            color: var(--primary);
        }

        .hero {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 5rem 2rem;
            text-align: center;
            max-width: 1200px;
            margin: 0 auto;
        }

        .hero h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
            font-weight: 800;
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 2rem;
            opacity: 0.95;
        }

        .skills-badge {
            display: inline-block;
            background: rgba(255,255,255,0.2);
            padding: 0.5rem 1rem;
            border-radius: 20px;
            margin: 0.5rem;
            font-size: 0.9rem;
            border: 1px solid rgba(255,255,255,0.3);
        }

        .cta-button {
            display: inline-block;
            background: white;
            color: #667eea;
            padding: 0.75rem 2rem;
            border-radius: 6px;
            text-decoration: none;
            font-weight: 600;
            margin-top: 1.5rem;
            transition: transform 0.3s, box-shadow 0.3s;
            border: none;
            cursor: pointer;
        }

        .cta-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 16px rgba(0,0,0,0.2);
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        section {
            padding: 4rem 0;
        }

        h2 {
            font-size: 2.5rem;
            margin-bottom: 3rem;
            text-align: center;
            color: var(--dark);
            position: relative;
            padding-bottom: 1rem;
        }

        h2::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 3px;
            background: linear-gradient(90deg, var(--primary), var(--accent));
            border-radius: 2px;
        }

        /* Skills Section */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            margin-bottom: 3rem;
        }

        .skill-card {
            background: white;
            padding: 2rem;
            border-radius: 10px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.08);
            border-left: 4px solid var(--primary);
            transition: all 0.3s;
        }

        .skill-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 16px rgba(0,0,0,0.12);
            border-left-color: var(--accent);
        }

        .skill-card h3 {
            font-size: 1.3rem;
            margin-bottom: 1rem;
            color: var(--dark);
        }

        .skill-card ul {
            list-style: none;
            font-size: 0.95rem;
        }

        .skill-card li {
            padding: 0.5rem 0;
            border-bottom: 1px solid var(--border);
        }

        .skill-card li:last-child {
            border-bottom: none;
        }

        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .project-card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 2px 8px rgba(0,0,0,0.08);
            transition: all 0.3s;
        }

        .project-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 12px 24px rgba(0,0,0,0.15);
        }

        .project-image {
            width: 100%;
            height: 200px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 3rem;
            font-weight: bold;
        }

        .project-content {
            padding: 2rem;
        }

        .project-content h3 {
            font-size: 1.3rem;
            margin-bottom: 0.5rem;
            color: var(--dark);
        }

        .project-tag {
            display: inline-block;
            background: #f0f4ff;
            color: var(--primary);
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.75rem;
            font-weight: 600;
            margin: 0.5rem 0.5rem 0.5rem 0;
        }

        .project-description {
            margin: 1rem 0;
            font-size: 0.95rem;
            color: #666;
        }

        .project-links {
            display: flex;
            gap: 1rem;
            margin-top: 1rem;
        }

        .project-links a {
            color: var(--primary);
            text-decoration: none;
            font-weight: 600;
            font-size: 0.9rem;
            transition: color 0.3s;
        }

        .project-links a:hover {
            color: var(--accent);
        }

        /* Contact Section */
        .contact-section {
            background: linear-gradient(135deg, var(--dark) 0%, #111827 100%);
            color: white;
            text-align: center;
            border-radius: 10px;
            padding: 3rem;
        }

        .contact-section h2 {
            color: white;
        }

        .contact-section h2::after {
            background: linear-gradient(90deg, var(--primary), var(--accent));
        }

        .contact-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-top: 2rem;
            flex-wrap: wrap;
        }

        .contact-links a {
            color: white;
            text-decoration: none;
            padding: 0.75rem 1.5rem;
            border: 2px solid var(--primary);
            border-radius: 6px;
            transition: all 0.3s;
            font-weight: 600;
        }

        .contact-links a:hover {
            background: var(--primary);
            transform: translateY(-2px);
        }

        footer {
            background: var(--dark);
            color: white;
            text-align: center;
            padding: 2rem;
            margin-top: 3rem;
        }

        /* Responsive */
        @media (max-width: 768px) {
            nav ul {
                gap: 1rem;
                font-size: 0.85rem;
            }

            .hero h1 {
                font-size: 2rem;
            }

            h2 {
                font-size: 1.8rem;
            }

            nav {
                flex-direction: column;
                gap: 1rem;
            }

            nav ul {
                flex-direction: column;
                gap: 0.5rem;
            }
        }
    </style>
</head>
<body>
    <header>
        <nav>
            <div class="logo">DevPortfolio</div>
            <ul>
                <li><a href="#skills">Skills</a></li>
                <li><a href="#projects">Projects</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <section class="hero">
        <h1>Creative Developer & Designer</h1>
        <p>Building games, web experiences, and intuitive interfaces</p>
        <div>
            <span class="skills-badge">🎮 Game Dev (Unity/Unreal)</span>
            <span class="skills-badge">💻 Full-Stack Web</span>
            <span class="skills-badge">🎨 UI/UX Design</span>
        </div>
        <button class="cta-button" onclick="document.getElementById('contact').scrollIntoView({behavior: 'smooth'})">Get In Touch</button>
    </section>

    <section id="skills" class="container">
        <h2>Skills & Expertise</h2>
        <div class="skills-grid">
            <div class="skill-card">
                <h3>🎮 Game Development</h3>
                <ul>
                    <li>Unity Engine</li>
                    <li>Unreal Engine 5</li>
                    <li>C# & C++</li>
                    <li>Game Physics</li>
                    <li>Gameplay Programming</li>
                    <li>VR/AR Development</li>
                </ul>
            </div>

            <div class="skill-card">
                <h3>💻 Full-Stack Web</h3>
                <ul>
                    <li>Frontend: React, Vue, TypeScript</li>
                    <li>Backend: Node.js, Python, SQL</li>
                    <li>Databases: PostgreSQL, MongoDB</li>
                    <li>APIs & REST Services</li>
                    <li>Cloud Deployment</li>
                    <li>DevOps & CI/CD</li>
                </ul>
            </div>

            <div class="skill-card">
                <h3>🎨 UI/UX Design</h3>
                <ul>
                    <li>Figma & Design Tools</li>
                    <li>User Research</li>
                    <li>Wireframing & Prototyping</li>
                    <li>Design Systems</li>
                    <li>Responsive Design</li>
                    <li>Accessibility (WCAG)</li>
                </ul>
            </div>
        </div>
    </section>

    <section id="projects" class="container">
        <h2>Featured Projects</h2>
        <div class="projects-grid">
            <div class="project-card">
                <div class="project-image">🎮</div>
                <div class="project-content">
                    <h3>Puzzle Quest</h3>
                    <div>
                        <span class="project-tag">Unity</span>
                        <span class="project-tag">C#</span>
                        <span class="project-tag">Game Dev</span>
                    </div>
                    <p class="project-description">A relaxing puzzle game with dynamic level generation and engaging UI animations.</p>
                    <div class="project-links">
                        <a href="#">View Demo</a>
                        <a href="#">GitHub</a>
                    </div>
                </div>
            </div>

            <div class="project-card">
                <div class="project-image">🌐</div>
                <div class="project-content">
                    <h3>TaskFlow Dashboard</h3>
                    <div>
                        <span class="project-tag">React</span>
                        <span class="project-tag">Node.js</span>
                        <span class="project-tag">Full-Stack</span>
                    </div>
                    <p class="project-description">Real-time project management tool with collaborative features and intuitive data visualization.</p>
                    <div class="project-links">
                        <a href="#">Live Demo</a>
                        <a href="#">GitHub</a>
                    </div>
                </div>
            </div>

            <div class="project-card">
                <div class="project-image">✨</div>
                <div class="project-content">
                    <h3>Design System v2.0</h3>
                    <div>
                        <span class="project-tag">Figma</span>
                        <span class="project-tag">Component Library</span>
                        <span class="project-tag">Design</span>
                    </div>
                    <p class="project-description">Comprehensive design system with 200+ components and accessibility-first approach for enterprise apps.</p>
                    <div class="project-links">
                        <a href="#">View System</a>
                        <a href="#">Documentation</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="contact" class="container">
        <div class="contact-section">
            <h2>Let's Collaborate</h2>
            <p style="font-size: 1.1rem; margin: 1rem 0;">I'm interested in game development, full-stack projects, and design work.</p>
            <div class="contact-links">
                <a href="mailto:hello@example.com">Email</a>
                <a href="#">GitHub</a>
                <a href="#">LinkedIn</a>
                <a href="#">Portfolio</a>
            </div>
        </div>
    </section>

    <footer>
        <p>&copy; 2025 Your Name. Built with HTML, CSS & GitHub Pages.</p>
    </footer>
</body>
</html>
