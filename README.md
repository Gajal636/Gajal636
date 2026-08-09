<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gajal Gupta - Animated Portfolio</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: #333;
            min-height: 100vh;
            overflow-x: hidden;
        }

        .navbar {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            padding: 1rem 2rem;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
            z-index: 1000;
            animation: slideDown 0.8s ease-out;
        }

        .nav-content {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 24px;
            font-weight: 700;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .nav-links {
            display: flex;
            gap: 2rem;
            list-style: none;
        }

        .nav-links a {
            text-decoration: none;
            color: #333;
            font-weight: 500;
            transition: all 0.3s ease;
            position: relative;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
            margin-top: 80px;
        }

        .hero {
            background: white;
            border-radius: 20px;
            padding: 4rem;
            margin-bottom: 3rem;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.2);
            animation: scaleIn 0.8s ease-out;
            text-align: center;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: slideDown 0.8s ease-out;
        }

        .hero-subtitle {
            font-size: 1.5rem;
            color: #666;
            margin-bottom: 2rem;
            animation: fadeIn 1s ease-out;
        }

        .wave-text {
            display: inline-block;
            font-size: 2rem;
        }

        .wave-text span {
            display: inline-block;
            animation: wave 0.6s ease-in-out infinite;
            margin: 0 2px;
        }

        .wave-text span:nth-child(1) { animation-delay: 0s; }
        .wave-text span:nth-child(2) { animation-delay: 0.1s; }
        .wave-text span:nth-child(3) { animation-delay: 0.2s; }
        .wave-text span:nth-child(4) { animation-delay: 0.3s; }
        .wave-text span:nth-child(5) { animation-delay: 0.4s; }

        .contact-buttons {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
            margin-top: 2rem;
            animation: fadeIn 1.5s ease-out;
        }

        .btn {
            padding: 0.8rem 1.5rem;
            border: none;
            border-radius: 50px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
        }

        .btn-primary {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            box-shadow: 0 4px 15px rgba(102, 126, 234, 0.4);
        }

        .btn-primary:hover {
            transform: translateY(-4px);
            box-shadow: 0 8px 25px rgba(102, 126, 234, 0.6);
        }

        .btn-secondary {
            background: white;
            color: #667eea;
            border: 2px solid #667eea;
        }

        .btn-secondary:hover {
            background: #667eea;
            color: white;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            margin-bottom: 3rem;
        }

        .stat-card {
            background: white;
            border-radius: 15px;
            padding: 2rem;
            text-align: center;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            animation: scaleIn 0.6s ease-out;
            transition: all 0.3s ease;
        }

        .stat-card:nth-child(1) { animation-delay: 0.2s; }
        .stat-card:nth-child(2) { animation-delay: 0.3s; }
        .stat-card:nth-child(3) { animation-delay: 0.4s; }
        .stat-card:nth-child(4) { animation-delay: 0.5s; }

        .stat-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(102, 126, 234, 0.2);
        }

        .stat-number {
            font-size: 2.5rem;
            font-weight: 700;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 0.5rem;
        }

        .stat-label {
            font-size: 1rem;
            color: #666;
            font-weight: 600;
        }

        .tech-section {
            background: white;
            border-radius: 20px;
            padding: 3rem;
            margin-bottom: 3rem;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.1);
            animation: slideUp 0.8s ease-out;
        }

        .section-title {
            font-size: 2.5rem;
            margin-bottom: 2rem;
            color: #333;
            text-align: center;
            animation: slideDown 0.8s ease-out;
        }

        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 1.5rem;
            margin-bottom: 2rem;
        }

        .tech-badge {
            background: linear-gradient(135deg, #f8f9ff 0%, #f0f4ff 100%);
            border: 2px solid #e8ebff;
            border-radius: 12px;
            padding: 1.5rem;
            text-align: center;
            animation: float 3s ease-in-out infinite;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .tech-badge:nth-child(1) { animation-delay: 0s; }
        .tech-badge:nth-child(2) { animation-delay: 0.15s; }
        .tech-badge:nth-child(3) { animation-delay: 0.3s; }
        .tech-badge:nth-child(4) { animation-delay: 0.45s; }
        .tech-badge:nth-child(5) { animation-delay: 0.6s; }
        .tech-badge:nth-child(6) { animation-delay: 0.75s; }
        .tech-badge:nth-child(7) { animation-delay: 0.9s; }
        .tech-badge:nth-child(8) { animation-delay: 1.05s; }

        .tech-badge:hover {
            transform: translateY(-15px) scale(1.05);
            border-color: #667eea;
            box-shadow: 0 15px 40px rgba(102, 126, 234, 0.2);
        }

        .tech-icon {
            font-size: 2.5rem;
            margin-bottom: 0.5rem;
        }

        .tech-name {
            font-weight: 600;
            color: #333;
            font-size: 0.9rem;
        }

        .projects-section {
            background: white;
            border-radius: 20px;
            padding: 3rem;
            margin-bottom: 3rem;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.1);
            animation: slideUp 0.8s ease-out;
        }

        .project-card {
            background: linear-gradient(135deg, #f8f9ff 0%, #f0f4ff 100%);
            border: 2px solid #e8ebff;
            border-radius: 15px;
            padding: 2rem;
            margin-bottom: 2rem;
            animation: slideUp 0.8s ease-out;
            animation-fill-mode: both;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
            animation: shimmer 3s infinite;
        }

        .project-card:nth-child(1) { animation-delay: 0.1s; }
        .project-card:nth-child(2) { animation-delay: 0.2s; }
        .project-card:nth-child(3) { animation-delay: 0.3s; }

        .project-card:hover {
            transform: translateX(10px);
            border-color: #667eea;
            box-shadow: 0 15px 40px rgba(102, 126, 234, 0.2);
        }

        .project-title {
            font-size: 1.5rem;
            font-weight: 700;
            color: #333;
            margin-bottom: 0.5rem;
            position: relative;
            z-index: 1;
        }

        .project-tech {
            color: #667eea;
            font-size: 0.9rem;
            font-weight: 600;
            margin-bottom: 1rem;
            position: relative;
            z-index: 1;
        }

        .project-desc {
            color: #666;
            line-height: 1.6;
            margin-bottom: 1rem;
            position: relative;
            z-index: 1;
        }

        .project-features {
            list-style: none;
            margin: 1rem 0;
            position: relative;
            z-index: 1;
        }

        .project-features li {
            padding: 0.3rem 0;
            color: #666;
        }

        .project-features li::before {
            content: '✓ ';
            color: #4caf50;
            font-weight: bold;
            margin-right: 0.5rem;
        }

        .live-link {
            display: inline-block;
            margin-top: 1rem;
            padding: 0.6rem 1.2rem;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            text-decoration: none;
            border-radius: 25px;
            font-weight: 600;
            transition: all 0.3s ease;
            position: relative;
            z-index: 2;
        }

        .live-link:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 20px rgba(102, 126, 234, 0.4);
        }

        .footer {
            background: rgba(255, 255, 255, 0.95);
            padding: 2rem;
            text-align: center;
            border-radius: 20px;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.1);
            animation: fadeIn 2s ease-out;
        }

        .footer-text {
            color: #666;
            margin-bottom: 1rem;
        }

        .footer-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            flex-wrap: wrap;
            margin-bottom: 2rem;
        }

        .footer-links a {
            color: #667eea;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
        }

        .footer-links a:hover {
            transform: translateY(-3px);
            color: #764ba2;
        }

        /* Animations */
        @keyframes slideDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes slideUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
        }

        @keyframes scaleIn {
            from {
                opacity: 0;
                transform: scale(0.9);
            }
            to {
                opacity: 1;
                transform: scale(1);
            }
        }

        @keyframes float {
            0%, 100% {
                transform: translateY(0px);
            }
            50% {
                transform: translateY(-15px);
            }
        }

        @keyframes wave {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-20px);
            }
        }

        @keyframes shimmer {
            0% {
                left: -100%;
            }
            100% {
                left: 100%;
            }
        }

        @keyframes pulse {
            0%, 100% {
                box-shadow: 0 0 0 0 rgba(102, 126, 234, 0.7);
            }
            50% {
                box-shadow: 0 0 0 10px rgba(102, 126, 234, 0);
            }
        }

        @media (max-width: 768px) {
            .hero {
                padding: 2rem;
            }

            .hero h1 {
                font-size: 2rem;
            }

            .hero-subtitle {
                font-size: 1rem;
            }

            .nav-links {
                gap: 1rem;
                font-size: 0.9rem;
            }

            .contact-buttons {
                flex-direction: column;
            }

            .btn {
                width: 100%;
                justify-content: center;
            }

            .tech-grid {
                grid-template-columns: repeat(3, 1fr);
            }

            .stats-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }
    </style>
</head>
<body>
    <!-- Navbar -->
    <nav class="navbar">
        <div class="nav-content">
            <div class="logo">💻 Gajal Gupta</div>
            <ul class="nav-links">
                <li><a href="#hero">Home</a></li>
                <li><a href="#tech">Tech</a></li>
                <li><a href="#projects">Projects</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </div>
    </nav>

    <div class="container">
        <!-- Hero Section -->
        <section class="hero" id="hero">
            <h1>
                <div class="wave-text">
                    <span>G</span><span>a</span><span>j</span><span>a</span><span>l</span>
                </div>
                👨‍💻
            </h1>
            <h1 style="font-size: 2.5rem;">Full-Stack Developer</h1>
            <p class="hero-subtitle">MERN Stack | Cloud & AI | Building Scalable Apps</p>

            <div class="contact-buttons">
                <a href="mailto:gajalk636@gmail.com" class="btn btn-primary">📧 Email Me</a>
                <a href="https://linkedin.com/in/gajal-gupta" class="btn btn-secondary">💼 LinkedIn</a>
                <a href="tel:+916269879267" class="btn btn-secondary">📱 Call Me</a>
            </div>
        </section>

        <!-- Stats Section -->
        <div class="stats-grid">
            <div class="stat-card">
                <div class="stat-number" id="stat1">3</div>
                <div class="stat-label">Live Projects</div>
            </div>
            <div class="stat-card">
                <div class="stat-number" id="stat2">2</div>
                <div class="stat-label">Years Experience</div>
            </div>
            <div class="stat-card">
                <div class="stat-number" id="stat3">8.96</div>
                <div class="stat-label">Diploma CGPA</div>
            </div>
            <div class="stat-card">
                <div class="stat-number" id="stat4">100</div>
                <div class="stat-label">% Dedication</div>
            </div>
        </div>

        <!-- Tech Stack Section -->
        <section class="tech-section" id="tech">
            <h2 class="section-title">💻 Tech Stack</h2>
            <div class="tech-grid">
                <div class="tech-badge">
                    <div class="tech-icon">☕</div>
                    <div class="tech-name">Java</div>
                </div>
                <div class="tech-badge">
                    <div class="tech-icon">🐍</div>
                    <div class="tech-name">Python</div>
                </div>
                <div class="tech-badge">
                    <div class="tech-icon">⚛️</div>
                    <div class="tech-name">React</div>
                </div>
                <div class="tech-badge">
                    <div class="tech-icon">📦</div>
                    <div class="tech-name">Node.js</div>
                </div>
                <div class="tech-badge">
                    <div class="tech-icon">💾</div>
                    <div class="tech-name">MongoDB</div>
                </div>
                <div class="tech-badge">
                    <div class="tech-icon">☁️</div>
                    <div class="tech-name">AWS</div>
                </div>
                <div class="tech-badge">
                    <div class="tech-icon">🔗</div>
                    <div class="tech-name">REST API</div>
                </div>
                <div class="tech-badge">
                    <div class="tech-icon">🔐</div>
                    <div class="tech-name">JWT Auth</div>
                </div>
            </div>
        </section>

        <!-- Projects Section -->
        <section class="projects-section" id="projects">
            <h2 class="section-title">🎯 Featured Projects</h2>

            <div class="project-card">
                <div class="project-title">🤖 AI-Based Content Generator</div>
                <div class="project-tech">React • Node.js • MongoDB • OpenRouter API • JWT</div>
                <div class="project-desc">MERN-based AI content generation platform with JWT authentication and OpenRouter API integration.</div>
                <ul class="project-features">
                    <li>Integrated OpenRouter API for AI capabilities</li>
                    <li>JWT-based authentication system</li>
                    <li>Responsive dashboard with user history</li>
                    <li>MongoDB integration for data storage</li>
                </ul>
            </div>

            <div class="project-card">
                <div class="project-title">💰 Personal Finance Tracker</div>
                <div class="project-tech">React • Express • MongoDB • AI Analysis</div>
                <div class="project-desc">Comprehensive financial management tool with AI-powered spending insights and transaction tracking.</div>
                <ul class="project-features">
                    <li>Real-time expense tracking & analytics</li>
                    <li>AI-powered spending analysis</li>
                    <li>Fully responsive dashboard</li>
                    <li>Secure JWT authentication</li>
                </ul>
                <a href="https://personal-finance-tracker-app.onrender.com" class="live-link" target="_blank">🔗 Live Demo</a>
            </div>

            <div class="project-card">
                <div class="project-title">✅ Smart Task Manager</div>
                <div class="project-tech">React • Node.js • REST API • MongoDB</div>
                <div class="project-desc">Efficient task management system with intuitive UI and robust backend architecture.</div>
                <ul class="project-features">
                    <li>Full CRUD operations</li>
                    <li>Clean, responsive interface</li>
                    <li>Well-designed REST APIs</li>
                    <li>MongoDB integration</li>
                </ul>
                <a href="https://smart-task-manager-app.onrender.com" class="live-link" target="_blank">🔗 Live Demo</a>
            </div>
        </section>

        <!-- Footer -->
        <section class="footer" id="contact">
            <h2 class="section-title">📬 Let's Connect!</h2>
            <p class="footer-text">Feel free to reach out for collaboration, tech discussions, or just to say hello!</p>
            <div class="footer-links">
                <a href="mailto:gajalk636@gmail.com">📧 Email</a>
                <a href="https://linkedin.com/in/gajal-gupta" target="_blank">💼 LinkedIn</a>
                <a href="tel:+916269879267">📱 Phone</a>
                <a href="https://github.com" target="_blank">🐙 GitHub</a>
            </div>
            <p class="footer-text" style="color: #999; font-size: 0.9rem;">
                Made with ❤️ by Gajal Gupta | 2024
            </p>
        </section>
    </div>

    <script>
        // Counter animation for stats
        function animateCounter(element, start, end, duration) {
            let current = start;
            const increment = (end - start) / (duration / 16);
            
            const timer = setInterval(() => {
                current += increment;
                if (current >= end) {
                    element.textContent = end;
                    clearInterval(timer);
                } else {
                    element.textContent = Math.floor(current);
                }
            }, 16);
        }

        // Trigger animations when page loads
        window.addEventListener('load', () => {
            animateCounter(document.getElementById('stat1'), 0, 3, 1000);
            animateCounter(document.getElementById('stat2'), 0, 2, 1000);
            animateCounter(document.getElementById('stat3'), 0, 8.96, 1000);
            animateCounter(document.getElementById('stat4'), 0, 100, 1000);
        });

        // Smooth scroll for nav links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({ behavior: 'smooth' });
                }
            });
        });
    </script>
</body>
</html>
