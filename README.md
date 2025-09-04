<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>WebGym - Seu Treinador Digital</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #6366f1;
            --primary-dark: #4f46e5;
            --secondary: #8b5cf6;
            --accent: #06d6a0;
            --bg: #0f172a;
            --card: #1e293b;
            --text: #f1f5f9;
            --text-muted: #94a3b8;
            --border: #334155;
        }

        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
            background: linear-gradient(135deg, var(--bg) 0%, #1a202c 100%);
            color: var(--text);
            line-height: 1.6;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        .hero {
            padding: 80px 0;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(99, 102, 241, 0.1) 0%, transparent 70%);
            animation: pulse 4s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); opacity: 0.5; }
            50% { transform: scale(1.1); opacity: 0.8; }
        }

        .hero-content {
            position: relative;
            z-index: 1;
        }

        .logo {
            font-size: 4rem;
            font-weight: 900;
            background: linear-gradient(45deg, var(--primary), var(--accent));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 1rem;
            animation: glow 2s ease-in-out infinite alternate;
        }

        @keyframes glow {
            from { filter: drop-shadow(0 0 20px rgba(99, 102, 241, 0.3)); }
            to { filter: drop-shadow(0 0 30px rgba(99, 102, 241, 0.6)); }
        }

        .tagline {
            font-size: 1.5rem;
            color: var(--text-muted);
            margin-bottom: 2rem;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin: 80px 0;
        }

        .feature-card {
            background: var(--card);
            border-radius: 20px;
            padding: 2rem;
            border: 1px solid var(--border);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .feature-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, transparent, rgba(99, 102, 241, 0.1), transparent);
            transform: translateX(-100%);
            transition: transform 0.6s;
        }

        .feature-card:hover::before {
            transform: translateX(100%);
        }

        .feature-card:hover {
            transform: translateY(-10px);
            border-color: var(--primary);
            box-shadow: 0 20px 40px rgba(99, 102, 241, 0.2);
        }

        .feature-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
            display: block;
        }

        .feature-title {
            font-size: 1.5rem;
            font-weight: 700;
            margin-bottom: 1rem;
            color: var(--text);
        }

        .feature-desc {
            color: var(--text-muted);
            line-height: 1.6;
        }

        .tech-stack {
            background: var(--card);
            border-radius: 20px;
            padding: 3rem;
            margin: 80px 0;
            border: 1px solid var(--border);
        }

        .section-title {
            font-size: 2.5rem;
            font-weight: 800;
            text-align: center;
            margin-bottom: 3rem;
            background: linear-gradient(45deg, var(--text), var(--accent));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 2rem;
            text-align: center;
        }

        .tech-item {
            padding: 1.5rem;
            border-radius: 15px;
            background: rgba(99, 102, 241, 0.1);
            border: 1px solid rgba(99, 102, 241, 0.3);
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .tech-item:hover {
            background: rgba(99, 102, 241, 0.2);
            transform: scale(1.05);
        }

        .cta-section {
            text-align: center;
            padding: 80px 0;
            background: linear-gradient(45deg, rgba(99, 102, 241, 0.1), rgba(139, 92, 246, 0.1));
            border-radius: 30px;
            margin: 80px 0;
            border: 1px solid var(--border);
        }

        .cta-button {
            display: inline-flex;
            align-items: center;
            gap: 10px;
            background: linear-gradient(45deg, var(--primary), var(--secondary));
            color: white;
            padding: 15px 40px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            font-size: 1.1rem;
            transition: all 0.3s ease;
            border: none;
            cursor: pointer;
            margin: 10px;
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(99, 102, 241, 0.4);
        }

        .github-stats {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 40px 0;
            flex-wrap: wrap;
        }

        .stat-badge {
            background: var(--card);
            padding: 10px 20px;
            border-radius: 25px;
            border: 1px solid var(--border);
            color: var(--text-muted);
            font-size: 0.9rem;
            transition: all 0.3s ease;
        }

        .stat-badge:hover {
            border-color: var(--primary);
            color: var(--text);
        }

        .floating-elements {
            position: fixed;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }

        .floating-circle {
            position: absolute;
            border-radius: 50%;
            background: rgba(99, 102, 241, 0.1);
            animation: float 6s ease-in-out infinite;
        }

        .circle-1 {
            width: 80px;
            height: 80px;
            top: 20%;
            left: 10%;
            animation-delay: 0s;
        }

        .circle-2 {
            width: 120px;
            height: 120px;
            top: 60%;
            right: 10%;
            animation-delay: 2s;
        }

        .circle-3 {
            width: 60px;
            height: 60px;
            top: 80%;
            left: 20%;
            animation-delay: 4s;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        .demo-section {
            margin: 80px 0;
        }

        .demo-preview {
            background: var(--card);
            border-radius: 20px;
            padding: 2rem;
            border: 1px solid var(--border);
            text-align: center;
        }

        .demo-mockup {
            width: 100%;
            max-width: 800px;
            height: 400px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            border-radius: 15px;
            margin: 0 auto;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 2rem;
            font-weight: bold;
            position: relative;
            overflow: hidden;
        }

        .demo-mockup::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
            animation: shine 2s infinite;
        }

        @keyframes shine {
            0% { left: -100%; }
            100% { left: 100%; }
        }

        .scroll-indicator {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 4px;
            background: rgba(99, 102, 241, 0.2);
            z-index: 1000;
        }

        .scroll-progress {
            height: 100%;
            background: linear-gradient(90deg, var(--primary), var(--accent));
            width: 0%;
            transition: width 0.1s;
        }

        @media (max-width: 768px) {
            .logo { font-size: 2.5rem; }
            .tagline { font-size: 1.2rem; }
            .features-grid { grid-template-columns: 1fr; }
            .hero { padding: 40px 0; }
        }
    </style>
</head>
<body>
    <div class="scroll-indicator">
        <div class="scroll-progress" id="scrollProgress"></div>
    </div>

    <div class="floating-elements">
        <div class="floating-circle circle-1"></div>
        <div class="floating-circle circle-2"></div>
        <div class="floating-circle circle-3"></div>
    </div>

    <div class="container">
        <header class="hero">
            <div class="hero-content">
                <h1 class="logo">🏋️ WebGym</h1>
                <p class="tagline">Seu Treinador de Fitness Digital Pessoal powered by AI</p>
                <p style="color: var(--text-muted); max-width: 700px; margin: 0 auto;">
                    WebGym é um treinador de fitness digital pessoal que usa inteligência artificial para ajudar você a atingir seus objetivos de saúde. A aplicação permite que você faça login com segurança, crie um perfil detalhado e, em seguida, a IA gera planos semanais de treino e dieta personalizados.
                </p>
            </div>
        </header>

        <div class="github-stats">
            <div class="stat-badge">⭐ Stars</div>
            <div class="stat-badge">🍴 Forks</div>
            <div class="stat-badge">📋 Issues</div>
            <div class="stat-badge">🔧 Pull Requests</div>
        </div>

        <section class="features-section">
            <h2 class="section-title">✨ Recursos Principais</h2>
            <div class="features-grid">
                <div class="feature-card">
                    <span class="feature-icon">🔐</span>
                    <h3 class="feature-title">Autenticação e Autorização</h3>
                    <p class="feature-desc">Registre-se e faça login com segurança. Apenas usuários autenticados podem acessar seus dados e painéis privados.</p>
                </div>
                <div class="feature-card">
                    <span class="feature-icon">🤖</span>
                    <h3 class="feature-title">Planos com IA</h3>
                    <p class="feature-desc">Após um breve onboarding, a IA, com a tecnologia do Google Gemini, gera instantaneamente um plano de treino e dieta semanal personalizado.</p>
                </div>
                <div class="feature-card">
                    <span class="feature-icon">🧙‍♂️</span>
                    <h3 class="feature-title">Assistente de Onboarding</h3>
                    <p class="feature-desc">Um formulário interativo de várias etapas que coleta informações essenciais de forma simples e intuitiva.</p>
                </div>
                <div class="feature-card">
                    <span class="feature-icon">💾</span>
                    <h3 class="feature-title">Persistência de Dados</h3>
                    <p class="feature-desc">Todos os seus dados são armazenados de forma segura em um banco de dados Supabase, acessíveis a qualquer momento.</p>
                </div>
                <div class="feature-card">
                    <span class="feature-icon">📈</span>
                    <h3 class="feature-title">Painel e Interface de Abas</h3>
                    <p class="feature-desc">Uma interface organizada que serve como seu centro de comando de fitness. Navegue facilmente entre seu painel, planos, dieta e configurações.</p>
                </div>
                <div class="feature-card">
                    <span class="feature-icon">🎨</span>
                    <h3 class="feature-title">Gerenciamento de Tema</h3>
                    <p class="feature-desc">Personalize sua experiência alternando entre o modo claro e escuro com um único clique. Sua preferência é salva e lembrada.</p>
                </div>
            </div>
        </section>

        <section class="demo-section">
            <h2 class="section-title">🎬 Demonstração</h2>
            <div class="demo-preview">
                <div class="demo-mockup">
                    <div>Preview da Aplicação WebGym</div>
                </div>
                <p style="margin-top: 1rem; color: var(--text-muted);">
                    Interface moderna e intuitiva para seu treino personalizado
                </p>
            </div>
        </section>

        <section class="tech-stack">
            <h2 class="section-title">🏗️ Arquitetura Técnica</h2>
            <p style="text-align: center; color: var(--text-muted); margin-bottom: 3rem; max-width: 800px; margin-left: auto; margin-right: auto;">
                O WebGym foi construído com uma arquitetura moderna, projetada para ser escalável e de alto desempenho. A aplicação é composta por alguns sistemas-chave que trabalham em conjunto.
            </p>
            <div class="tech-grid">
                <div class="tech-item">
                    <div style="font-size: 2rem; margin-bottom: 0.5rem;">⚛️</div>
                    <div>React</div>
                </div>
                <div class="tech-item">
                    <div style="font-size: 2rem; margin-bottom: 0.5rem;">🔥</div>
                    <div>Supabase</div>
                </div>
                <div class="tech-item">
                    <div style="font-size: 2rem; margin-bottom: 0.5rem;">🧠</div>
                    <div>Google Gemini AI</div>
                </div>
                <div class="tech-item">
                    <div style="font-size: 2rem; margin-bottom: 0.5rem;">🎨</div>
                    <div>Tailwind CSS</div>
                </div>
                <div class="tech-item">
                    <div style="font-size: 2rem; margin-bottom: 0.5rem;">📱</div>
                    <div>Responsive Design</div>
                </div>
                <div class="tech-item">
                    <div style="font-size: 2rem; margin-bottom: 0.5rem;">🔒</div>
                    <div>JWT Auth</div>
                </div>
            </div>
        </section>

        <section class="cta-section">
            <h2 style="font-size: 2.5rem; margin-bottom: 1rem;">🚀 Comece Agora!</h2>
            <p style="color: var(--text-muted); margin-bottom: 2rem; font-size: 1.2rem;">
                Transforme sua jornada fitness com IA personalizada
            </p>
            <div>
                <button class="cta-button" onclick="window.open('https://github.com', '_blank')">
                    <span>⭐</span> Star no GitHub
                </button>
                <button class="cta-button" onclick="window.open('https://github.com', '_blank')">
                    <span>🔗</span> Ver Código
                </button>
                <button class="cta-button" onclick="window.open('https://github.com', '_blank')">
                    <span>🚀</span> Demo ao Vivo
                </button>
            </div>
        </section>

        <footer style="text-align: center; padding: 40px 0; color: var(--text-muted); border-top: 1px solid var(--border);">
            <p>💪 Construído com paixão por fitness e tecnologia</p>
            <p style="margin-top: 10px;">
                <span style="color: var(--accent);">WebGym</span> - Seu companheiro de treino inteligente
            </p>
        </footer>
    </div>

    <script>
        // Scroll progress indicator
        window.addEventListener('scroll', () => {
            const scrollProgress = document.getElementById('scrollProgress');
            const totalHeight = document.body.scrollHeight - window.innerHeight;
            const progress = (window.pageYOffset / totalHeight) * 100;
            scrollProgress.style.width = progress + '%';
        });

        // Smooth scrolling and animations
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        });

        document.querySelectorAll('.feature-card, .tech-item').forEach(el => {
            el.style.opacity = '0';
            el.style.transform = 'translateY(20px)';
            el.style.transition = 'all 0.6s ease';
            observer.observe(el);
        });

        // Interactive hover effects
        document.querySelectorAll('.tech-item').forEach(item => {
            item.addEventListener('mouseenter', () => {
                item.style.transform = 'scale(1.05) rotate(2deg)';
            });
            item.addEventListener('mouseleave', () => {
                item.style.transform = 'scale(1) rotate(0deg)';
            });
        });

        // Add some interactive sparkle effects
        function createSparkle() {
            const sparkle = document.createElement('div');
            sparkle.innerHTML = '✨';
            sparkle.style.position = 'fixed';
            sparkle.style.left = Math.random() * 100 + 'vw';
            sparkle.style.top = Math.random() * 100 + 'vh';
            sparkle.style.fontSize = '20px';
            sparkle.style.pointerEvents = 'none';
            sparkle.style.zIndex = '1000';
            sparkle.style.opacity = '0';
            sparkle.style.transition = 'all 2s ease-out';
            
            document.body.appendChild(sparkle);
            
            setTimeout(() => {
                sparkle.style.opacity = '1';
                sparkle.style.transform = 'translateY(-100px)';
            }, 100);
            
            setTimeout(() => {
                document.body.removeChild(sparkle);
            }, 2000);
        }

        // Create sparkles occasionally
        setInterval(createSparkle, 3000);
    </script>
</body>
</html>
