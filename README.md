<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ariel Arias - CV Interactivo</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #0a0e27 0%, #1a1a2e 100%);
            color: #e0e0e0;
            overflow-x: hidden;
        }

        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 0;
            pointer-events: none;
        }

        .particle {
            position: absolute;
            width: 2px;
            height: 2px;
            background: rgba(97, 218, 251, 0.5);
            border-radius: 50%;
            animation: float linear infinite;
        }

        @keyframes float {
            0% {
                transform: translateY(100vh) translateX(0);
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

        header {
            text-align: center;
            padding: 60px 20px;
            position: relative;
            overflow: hidden;
        }

        .header-glow {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 300px;
            height: 300px;
            background: radial-gradient(circle, rgba(97, 218, 251, 0.3) 0%, transparent 70%);
            animation: pulse 4s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% {
                transform: translate(-50%, -50%) scale(1);
                opacity: 0.5;
            }
            50% {
                transform: translate(-50%, -50%) scale(1.2);
                opacity: 0.8;
            }
        }

        h1 {
            font-size: 3.5em;
            font-weight: 700;
            background: linear-gradient(135deg, #61dafb 0%, #a855f7 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 10px;
            animation: slideInDown 1s ease-out;
            position: relative;
            z-index: 1;
        }

        @keyframes slideInDown {
            from {
                opacity: 0;
                transform: translateY(-50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .subtitle {
            font-size: 1.3em;
            color: #61dafb;
            margin-bottom: 20px;
            animation: fadeIn 1.5s ease-out;
            position: relative;
            z-index: 1;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
        }

        .section {
            background: rgba(26, 26, 46, 0.6);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(97, 218, 251, 0.2);
            border-radius: 20px;
            padding: 40px;
            margin: 30px 0;
            position: relative;
            overflow: hidden;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            animation: slideInUp 0.8s ease-out;
        }

        @keyframes slideInUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .section:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 40px rgba(97, 218, 251, 0.3);
        }

        .section::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 2px;
            background: linear-gradient(90deg, transparent, #61dafb, transparent);
            animation: scan 3s linear infinite;
        }

        @keyframes scan {
            0% {
                left: -100%;
            }
            100% {
                left: 100%;
            }
        }

        h2 {
            font-size: 2em;
            color: #61dafb;
            margin-bottom: 25px;
            display: flex;
            align-items: center;
            gap: 15px;
        }

        h2::before {
            content: '';
            width: 4px;
            height: 30px;
            background: linear-gradient(180deg, #61dafb 0%, #a855f7 100%);
            border-radius: 2px;
        }

        .about-text {
            font-size: 1.1em;
            line-height: 1.8;
            color: #c0c0c0;
        }

        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }

        .tech-item {
            background: rgba(97, 218, 251, 0.1);
            border: 1px solid rgba(97, 218, 251, 0.3);
            border-radius: 15px;
            padding: 25px;
            text-align: center;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .tech-item::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            background: rgba(97, 218, 251, 0.2);
            border-radius: 50%;
            transform: translate(-50%, -50%);
            transition: width 0.5s ease, height 0.5s ease;
        }

        .tech-item:hover::before {
            width: 200%;
            height: 200%;
        }

        .tech-item:hover {
            transform: scale(1.05);
            border-color: #61dafb;
            box-shadow: 0 0 20px rgba(97, 218, 251, 0.4);
        }

        .tech-icon {
            font-size: 2.5em;
            margin-bottom: 10px;
            position: relative;
            z-index: 1;
        }

        .tech-name {
            font-weight: 600;
            color: #61dafb;
            position: relative;
            z-index: 1;
        }

        .contact-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }

        .contact-item {
            background: linear-gradient(135deg, rgba(97, 218, 251, 0.1) 0%, rgba(168, 85, 247, 0.1) 100%);
            border: 1px solid rgba(97, 218, 251, 0.3);
            border-radius: 15px;
            padding: 25px;
            text-align: center;
            transition: all 0.3s ease;
            cursor: pointer;
            text-decoration: none;
            color: inherit;
            display: block;
        }

        .contact-item:hover {
            transform: translateY(-5px);
            border-color: #61dafb;
            box-shadow: 0 10px 30px rgba(97, 218, 251, 0.3);
        }

        .contact-icon {
            font-size: 2.5em;
            margin-bottom: 15px;
            color: #61dafb;
        }

        .contact-label {
            font-weight: 600;
            color: #61dafb;
            margin-bottom: 8px;
        }

        .contact-value {
            color: #c0c0c0;
            font-size: 0.95em;
        }

        .skills-bar {
            margin: 20px 0;
        }

        .skill-name {
            color: #61dafb;
            font-weight: 600;
            margin-bottom: 10px;
            display: flex;
            justify-content: space-between;
        }

        .skill-progress {
            background: rgba(97, 218, 251, 0.1);
            height: 10px;
            border-radius: 10px;
            overflow: hidden;
            position: relative;
        }

        .skill-fill {
            height: 100%;
            background: linear-gradient(90deg, #61dafb 0%, #a855f7 100%);
            border-radius: 10px;
            position: relative;
            animation: fillBar 2s ease-out;
        }

        @keyframes fillBar {
            from {
                width: 0;
            }
        }

        .skill-fill::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.3), transparent);
            animation: shimmer 2s infinite;
        }

        @keyframes shimmer {
            0% {
                transform: translateX(-100%);
            }
            100% {
                transform: translateX(100%);
            }
        }

        footer {
            text-align: center;
            padding: 40px 20px;
            color: #61dafb;
            font-style: italic;
        }

        @media (max-width: 768px) {
            h1 {
                font-size: 2.5em;
            }
            
            .section {
                padding: 25px;
            }
            
            .tech-grid, .contact-grid {
                grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            }
        }
    </style>
</head>
<body>
    <div class="particles" id="particles"></div>

    <div class="container">
        <header>
            <div class="header-glow"></div>
            <h1>ARIEL ARIAS</h1>
            <p class="subtitle">Ingeniero de Computación | Desarrollador Full Stack</p>
        </header>

        <div class="section">
            <h2>🚀 Sobre Mí</h2>
            <p class="about-text">
                Estudiante apasionado de Ingeniería de Computación con enfoque en desarrollo de software, 
                aplicaciones web y automatización. Me especializo en crear soluciones innovadoras que 
                combinan diseño elegante con funcionalidad robusta. Busco constantemente aprender nuevas 
                tecnologías y enfrentar desafíos que impulsen mi crecimiento profesional.
            </p>
        </div>

        <div class="section">
            <h2>💻 Stack Tecnológico</h2>
            <div class="tech-grid">
                <div class="tech-item">
                    <div class="tech-icon">🌐</div>
                    <div class="tech-name">HTML5</div>
                </div>
                <div class="tech-item">
                    <div class="tech-icon">🎨</div>
                    <div class="tech-name">CSS3</div>
                </div>
                <div class="tech-item">
                    <div class="tech-icon">⚛️</div>
                    <div class="tech-name">React</div>
                </div>
                <div class="tech-item">
                    <div class="tech-icon">🐍</div>
                    <div class="tech-name">Python</div>
                </div>
                <div class="tech-item">
                    <div class="tech-icon">☕</div>
                    <div class="tech-name">Java</div>
                </div>
            </div>
        </div>

        <div class="section">
            <h2>📊 Competencias</h2>
            <div class="skills-bar">
                <div class="skill-name">
                    <span>Desarrollo Web</span>
                    <span>90%</span>
                </div>
                <div class="skill-progress">
                    <div class="skill-fill" style="width: 90%"></div>
                </div>
            </div>
            <div class="skills-bar">
                <div class="skill-name">
                    <span>Python</span>
                    <span>85%</span>
                </div>
                <div class="skill-progress">
                    <div class="skill-fill" style="width: 85%"></div>
                </div>
            </div>
            <div class="skills-bar">
                <div class="skill-name">
                    <span>React</span>
                    <span>80%</span>
                </div>
                <div class="skill-progress">
                    <div class="skill-fill" style="width: 80%"></div>
                </div>
            </div>
            <div class="skills-bar">
                <div class="skill-name">
                    <span>Java</span>
                    <span>75%</span>
                </div>
                <div class="skill-progress">
                    <div class="skill-fill" style="width: 75%"></div>
                </div>
            </div>
        </div>

        <div class="section">
            <h2>📬 Contacto</h2>
            <div class="contact-grid">
                <a href="mailto:ariearia@espol.edu.ec" class="contact-item">
                    <div class="contact-icon">📧</div>
                    <div class="contact-label">Email</div>
                    <div class="contact-value">ariearia@espol.edu.ec</div>
                </a>
                <a href="https://www.linkedin.com/in/arielarias" target="_blank" class="contact-item">
                    <div class="contact-icon">💼</div>
                    <div class="contact-label">LinkedIn</div>
                    <div class="contact-value">/in/arielarias</div>
                </a>
                <a href="https://wa.me/593932665565" target="_blank" class="contact-item">
                    <div class="contact-icon">📱</div>
                    <div class="contact-label">WhatsApp</div>
                    <div class="contact-value">+593 93 266 5565</div>
                </a>
            </div>
        </div>

        <footer>
            "Construyendo el futuro, una línea de código a la vez"
        </footer>
    </div>

    <script>
        // Crear partículas animadas
        const particlesContainer = document.getElementById('particles');
        for (let i = 0; i < 50; i++) {
            const particle = document.createElement('div');
            particle.className = 'particle';
            particle.style.left = Math.random() * 100 + '%';
            particle.style.animationDuration = (Math.random() * 10 + 10) + 's';
            particle.style.animationDelay = Math.random() * 5 + 's';
            particlesContainer.appendChild(particle);
        }

        // Animación de entrada en secciones al hacer scroll
        const sections = document.querySelectorAll('.section');
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -100px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        sections.forEach(section => {
            observer.observe(section);
        });
    </script>
</body>
</html>
