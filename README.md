<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Esmil - Rust Developer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(135deg, #0f0c29, #302b63, #24243e);
            color: #fff;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            overflow-x: hidden;
            min-height: 100vh;
        }

        /* Partículas de fondo */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            z-index: 0;
        }

        .particle {
            position: absolute;
            width: 3px;
            height: 3px;
            background: rgba(255, 255, 255, 0.5);
            border-radius: 50%;
            animation: float 15s infinite;
        }

        @keyframes float {
            0%, 100% {
                transform: translateY(0) translateX(0);
                opacity: 0;
            }
            10% {
                opacity: 1;
            }
            90% {
                opacity: 1;
            }
            100% {
                transform: translateY(-100vh) translateX(100px);
                opacity: 0;
            }
        }

        .container {
            position: relative;
            z-index: 1;
            max-width: 1200px;
            margin: 0 auto;
            padding: 40px 20px;
        }

        /* Hero Section */
        .hero {
            text-align: center;
            padding: 60px 20px;
            animation: fadeInDown 1s ease-out;
        }

        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .hero h1 {
            font-size: 4rem;
            margin-bottom: 20px;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4, #45b7d1, #f7b731);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: gradient 3s ease infinite;
            background-size: 300% 300%;
        }

        @keyframes gradient {
            0%, 100% {
                background-position: 0% 50%;
            }
            50% {
                background-position: 100% 50%;
            }
        }

        .typing-text {
            font-size: 1.5rem;
            color: #4ecdc4;
            border-right: 2px solid #4ecdc4;
            white-space: nowrap;
            overflow: hidden;
            display: inline-block;
            animation: typing 3.5s steps(40, end), blink-caret .75s step-end infinite;
        }

        @keyframes typing {
            from { width: 0 }
            to { width: 100% }
        }

        @keyframes blink-caret {
            from, to { border-color: transparent }
            50% { border-color: #4ecdc4; }
        }

        /* Cards Section */
        .cards-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin: 60px 0;
        }

        .card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 30px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: all 0.4s ease;
            animation: fadeInUp 1s ease-out;
            animation-fill-mode: both;
            position: relative;
            overflow: hidden;
        }

        .card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255, 255, 255, 0.1), transparent);
            transform: rotate(45deg);
            transition: all 0.6s ease;
        }

        .card:hover::before {
            animation: shine 1s ease;
        }

        @keyframes shine {
            0% {
                left: -50%;
            }
            100% {
                left: 150%;
            }
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .card:nth-child(1) { animation-delay: 0.1s; }
        .card:nth-child(2) { animation-delay: 0.2s; }
        .card:nth-child(3) { animation-delay: 0.3s; }

        .card:hover {
            transform: translateY(-10px) scale(1.02);
            border-color: rgba(78, 205, 196, 0.5);
            box-shadow: 0 20px 60px rgba(78, 205, 196, 0.3);
        }

        .card h2 {
            color: #4ecdc4;
            margin-bottom: 20px;
            font-size: 1.8rem;
        }

        .card-icon {
            font-size: 3rem;
            margin-bottom: 20px;
            display: inline-block;
            animation: bounce 2s infinite;
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% {
                transform: translateY(0);
            }
            40% {
                transform: translateY(-15px);
            }
            60% {
                transform: translateY(-7px);
            }
        }

        /* Skills Section */
        .skills {
            margin: 60px 0;
        }

        .skills h2 {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 40px;
            color: #4ecdc4;
        }

        .skills-container {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            justify-content: center;
        }

        .skill-badge {
            background: linear-gradient(135deg, rgba(255, 107, 107, 0.2), rgba(78, 205, 196, 0.2));
            padding: 15px 30px;
            border-radius: 50px;
            border: 2px solid rgba(78, 205, 196, 0.3);
            transition: all 0.3s ease;
            animation: fadeIn 0.5s ease-out;
            animation-fill-mode: both;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .skill-badge::after {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            background: rgba(255, 255, 255, 0.2);
            border-radius: 50%;
            transform: translate(-50%, -50%);
            transition: width 0.5s, height 0.5s;
        }

        .skill-badge:hover::after {
            width: 300px;
            height: 300px;
        }

        .skill-badge:hover {
            transform: scale(1.1) rotate(5deg);
            border-color: #4ecdc4;
            box-shadow: 0 10px 30px rgba(78, 205, 196, 0.4);
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: scale(0.5);
            }
            to {
                opacity: 1;
                transform: scale(1);
            }
        }

        .skill-badge:nth-child(1) { animation-delay: 0.1s; }
        .skill-badge:nth-child(2) { animation-delay: 0.2s; }
        .skill-badge:nth-child(3) { animation-delay: 0.3s; }
        .skill-badge:nth-child(4) { animation-delay: 0.4s; }
        .skill-badge:nth-child(5) { animation-delay: 0.5s; }
        .skill-badge:nth-child(6) { animation-delay: 0.6s; }

        /* Stats Section */
        .stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 30px;
            margin: 60px 0;
        }

        .stat-box {
            background: linear-gradient(135deg, rgba(255, 107, 107, 0.1), rgba(78, 205, 196, 0.1));
            padding: 40px;
            border-radius: 20px;
            text-align: center;
            border: 2px solid rgba(78, 205, 196, 0.2);
            position: relative;
            overflow: hidden;
            animation: slideIn 1s ease-out;
            animation-fill-mode: both;
        }

        .stat-box:nth-child(1) { animation-delay: 0.2s; }
        .stat-box:nth-child(2) { animation-delay: 0.4s; }
        .stat-box:nth-child(3) { animation-delay: 0.6s; }
        .stat-box:nth-child(4) { animation-delay: 0.8s; }

        @keyframes slideIn {
            from {
                opacity: 0;
                transform: translateX(-100px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        .stat-number {
            font-size: 3rem;
            font-weight: bold;
            color: #4ecdc4;
            margin-bottom: 10px;
            animation: countUp 2s ease-out;
        }

        @keyframes countUp {
            from {
                opacity: 0;
                transform: scale(0);
            }
            to {
                opacity: 1;
                transform: scale(1);
            }
        }

        .stat-label {
            color: #bbb;
            font-size: 1.1rem;
        }

        /* Fun Facts */
        .fun-facts {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 40px;
            margin: 60px 0;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .fun-facts h2 {
            text-align: center;
            color: #4ecdc4;
            margin-bottom: 30px;
            font-size: 2.5rem;
        }

        .fact {
            padding: 20px;
            margin: 15px 0;
            background: rgba(78, 205, 196, 0.1);
            border-left: 4px solid #4ecdc4;
            border-radius: 10px;
            animation: slideInRight 0.8s ease-out;
            animation-fill-mode: both;
            transition: all 0.3s ease;
        }

        .fact:nth-child(2) { animation-delay: 0.1s; }
        .fact:nth-child(3) { animation-delay: 0.2s; }
        .fact:nth-child(4) { animation-delay: 0.3s; }
        .fact:nth-child(5) { animation-delay: 0.4s; }
        .fact:nth-child(6) { animation-delay: 0.5s; }

        @keyframes slideInRight {
            from {
                opacity: 0;
                transform: translateX(100px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        .fact:hover {
            transform: translateX(10px);
            background: rgba(78, 205, 196, 0.2);
        }

        /* Contact Section */
        .contact {
            text-align: center;
            margin: 60px 0;
        }

        .contact h2 {
            color: #4ecdc4;
            font-size: 2.5rem;
            margin-bottom: 30px;
        }

        .contact-links {
            display: flex;
            justify-content: center;
            gap: 30px;
            flex-wrap: wrap;
        }

        .contact-btn {
            display: inline-block;
            padding: 15px 40px;
            background: linear-gradient(135deg, #ff6b6b, #4ecdc4);
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: bold;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% {
                box-shadow: 0 0 0 0 rgba(78, 205, 196, 0.7);
            }
            50% {
                box-shadow: 0 0 0 20px rgba(78, 205, 196, 0);
            }
        }

        .contact-btn:hover {
            transform: scale(1.1) rotate(-3deg);
            animation: none;
        }

        .contact-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: rgba(255, 255, 255, 0.3);
            transition: left 0.5s;
        }

        .contact-btn:hover::before {
            left: 100%;
        }

        /* Footer */
        footer {
            text-align: center;
            padding: 40px 20px;
            color: #bbb;
            animation: fadeIn 2s ease-out;
        }

        .rust-logo {
            display: inline-block;
            animation: rotate360 20s linear infinite;
        }

        @keyframes rotate360 {
            from {
                transform: rotate(0deg);
            }
            to {
                transform: rotate(360deg);
            }
        }

        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }

            .typing-text {
                font-size: 1.2rem;
            }

            .cards-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="particles" id="particles"></div>

    <div class="container">
        <!-- Hero Section -->
        <div class="hero">
            <h1>Hi, I'm Esmil 👋</h1>
            <div class="typing-text">Rust Developer | Systems Programmer</div>
        </div>

        <!-- About Cards -->
        <div class="cards-grid">
            <div class="card">
                <div class="card-icon">🦀</div>
                <h2>Rust Enthusiast</h2>
                <p>Building fast, reliable systems with the power of Rust. From low-level system tools to high-performance backend services.</p>
            </div>

            <div class="card">
                <div class="card-icon">⚡</div>
                <h2>Backend Engineer</h2>
                <p>Crafting scalable backend services with async Rust using Tokio, focusing on performance and reliability.</p>
            </div>

            <div class="card">
                <div class="card-icon">🔧</div>
                <h2>Systems Programming</h2>
                <p>Deep diving into low-level programming, memory management, and system optimization with C++ and Rust.</p>
            </div>
        </div>

        <!-- Skills Section -->
        <div class="skills">
            <h2>🛠️ Tech Stack</h2>
            <div class="skills-container">
                <div class="skill-badge">🦀 Rust</div>
                <div class="skill-badge">⚙️ C++</div>
                <div class="skill-badge">🐍 Python</div>
                <div class="skill-badge">⚡ Tokio</div>
                <div class="skill-badge">🗄️ MySQL</div>
                <div class="skill-badge">🐳 Docker</div>
                <div class="skill-badge">🐧 Linux</div>
                <div class="skill-badge">🔥 Actix-web</div>
                <div class="skill-badge">📦 PostgreSQL</div>
            </div>
        </div>

        <!-- Stats Section -->
        <div class="stats">
            <div class="stat-box">
                <div class="stat-number">500+</div>
                <div class="stat-label">Commits</div>
            </div>
            <div class="stat-box">
                <div class="stat-number">20+</div>
                <div class="stat-label">Projects</div>
            </div>
            <div class="stat-box">
                <div class="stat-number">100%</div>
                <div class="stat-label">Rust Love</div>
            </div>
            <div class="stat-box">
                <div class="stat-number">∞</div>
                <div class="stat-label">Coffee Cups</div>
            </div>
        </div>

        <!-- Fun Facts -->
        <div class="fun-facts">
            <h2>⚡ Fun Facts</h2>
            <div class="fact">🐛 My best debugging happens at 3 AM</div>
            <div class="fact">🦀 If the Rust compiler is happy, I'm happy</div>
            <div class="fact">☕ Coffee-driven development is my methodology</div>
            <div class="fact">🔥 I speak fluent "fighting with the borrow checker"</div>
            <div class="fact">💾 I still believe `unsafe` blocks are just spicy code</div>
        </div>

        <!-- Contact Section -->
        <div class="contact">
            <h2>📫 Let's Connect</h2>
            <div class="contact-links">
                <a href="https://github.com/CompileRIder" class="contact-btn">GitHub 🐙</a>
                <a href="https://www.linkedin.com/in/esmil-vicioso-mercado-7885b9388/" class="contact-btn">LinkedIn 💼</a>
                <a href="mailto:esmilviciosomercado@gmail.com" class="contact-btn">Email 📧</a>
            </div>
        </div>

        <!-- Footer -->
        <footer>
            <p>
                <span class="rust-logo">🦀</span> 
                Built with passion and a lot of coffee | Open to collaboration on interesting Rust projects
            </p>
            <p style="margin-top: 20px; color: #4ecdc4;">"In Rust we trust"</p>
        </footer>
    </div>

    <script>
        // Crear partículas
        const particlesContainer = document.getElementById('particles');
        for (let i = 0; i < 50; i++) {
            const particle = document.createElement('div');
            particle.className = 'particle';
            particle.style.left = Math.random() * 100 + '%';
            particle.style.animationDelay = Math.random() * 15 + 's';
            particle.style.animationDuration = (Math.random() * 10 + 10) + 's';
            particlesContainer.appendChild(particle);
        }
    </script>
</body>
</html>
