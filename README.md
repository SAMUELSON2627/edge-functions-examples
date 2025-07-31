<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Roblox Elite - Executores e Scripts Premium</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #8a2be2;
            --secondary: #5e17eb;
            --accent: #ff6b6b;
            --dark: #0f0c24;
            --darker: #080616;
            --card-bg: rgba(30, 25, 60, 0.6);
            --card-border: rgba(138, 43, 226, 0.3);
            --text: #f0f0f5;
            --text-secondary: #b0b0d0;
            --modal-bg: rgba(15, 10, 35, 0.95);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }

        body {
            background: linear-gradient(135deg, var(--darker), var(--dark));
            color: var(--text);
            min-height: 100vh;
            overflow-x: hidden;
            position: relative;
        }

        body::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                radial-gradient(circle at 20% 30%, rgba(138, 43, 226, 0.15) 0%, transparent 40%),
                radial-gradient(circle at 80% 70%, rgba(255, 107, 107, 0.15) 0%, transparent 40%);
            z-index: -1;
            animation: bgPulse 20s infinite alternate;
        }

        /* Partículas animadas */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }

        .particle {
            position: absolute;
            border-radius: 50%;
            background: rgba(138, 43, 226, 0.5);
            animation: float 15s infinite linear;
        }

        /* Header com efeito de vidro */
        header {
            background: rgba(15, 10, 35, 0.7);
            backdrop-filter: blur(10px);
            padding: 20px 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 5px 30px rgba(0, 0, 0, 0.3);
            border-bottom: 1px solid var(--card-border);
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 15px;
            animation: fadeInDown 1s ease;
        }

        .logo-icon {
            font-size: 2.5rem;
            color: var(--accent);
        }

        .logo-text {
            font-size: 1.8rem;
            font-weight: 800;
            background: linear-gradient(90deg, var(--accent), var(--primary));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }

        .nav-links {
            display: flex;
            gap: 25px;
        }

        .nav-link {
            position: relative;
            padding: 10px 0;
            font-weight: 500;
            color: var(--text-secondary);
            text-decoration: none;
            transition: all 0.3s ease;
        }

        .nav-link:hover {
            color: var(--text);
        }

        .nav-link::after {
            content: "";
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--accent);
            transition: width 0.3s ease;
        }

        .nav-link:hover::after {
            width: 100%;
        }

        .hero {
            text-align: center;
            padding: 80px 20px 120px;
            max-width: 900px;
            margin: 0 auto;
            position: relative;
        }

        .hero-title {
            font-size: 4rem;
            font-weight: 800;
            margin-bottom: 20px;
            background: linear-gradient(90deg, var(--accent), var(--primary));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            animation: fadeInUp 1s ease, textGlow 3s infinite alternate;
        }

        .hero-subtitle {
            font-size: 1.4rem;
            color: var(--text-secondary);
            margin-bottom: 40px;
            animation: fadeInUp 1s ease 0.2s forwards;
            opacity: 0;
        }

        .tabs {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-bottom: 50px;
            flex-wrap: wrap;
            animation: fadeInUp 1s ease 0.4s forwards;
            opacity: 0;
        }

        .tab-btn {
            background: var(--card-bg);
            border: 1px solid var(--card-border);
            padding: 15px 30px;
            border-radius: 50px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
            font-size: 1.1rem;
            color: var(--text);
        }

        .tab-btn:hover {
            background: rgba(138, 43, 226, 0.3);
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(138, 43, 226, 0.3);
        }

        .tab-btn.active {
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            box-shadow: 0 5px 15px rgba(138, 43, 226, 0.4);
            transform: translateY(-3px);
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 20px;
        }

        .content-section {
            display: none;
            animation: fadeIn 0.8s ease;
        }

        .content-section.active {
            display: block;
        }

        .section-title {
            font-size: 2.5rem;
            margin: 40px 0 30px;
            position: relative;
            display: inline-block;
            padding-bottom: 10px;
        }

        .section-title::after {
            content: "";
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 4px;
            background: linear-gradient(90deg, var(--accent), var(--primary));
            border-radius: 2px;
            transform: scaleX(0);
            transform-origin: left;
            animation: titleUnderline 1s ease 0.5s forwards;
        }

        .cards-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
            gap: 30px;
            margin-bottom: 80px;
        }

        .card {
            background: var(--card-bg);
            border: 1px solid var(--card-border);
            border-radius: 20px;
            padding: 25px;
            transition: all 0.4s ease;
            backdrop-filter: blur(10px);
            position: relative;
            overflow: hidden;
            opacity: 0;
            transform: translateY(30px);
            animation: cardAppear 0.6s ease forwards;
        }

        .card:nth-child(1) { animation-delay: 0.1s; }
        .card:nth-child(2) { animation-delay: 0.2s; }
        .card:nth-child(3) { animation-delay: 0.3s; }
        .card:nth-child(4) { animation-delay: 0.4s; }
        .card:nth-child(5) { animation-delay: 0.5s; }
        .card:nth-child(6) { animation-delay: 0.6s; }
        .card:nth-child(7) { animation-delay: 0.7s; }
        .card:nth-child(8) { animation-delay: 0.8s; }

        .card::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: linear-gradient(90deg, var(--accent), var(--primary));
            transform: scaleX(0);
            transform-origin: left;
            transition: transform 0.5s ease;
        }

        .card:hover {
            transform: translateY(-15px) rotate(1deg);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.4);
            border-color: rgba(138, 43, 226, 0.5);
        }

        .card:hover::before {
            transform: scaleX(1);
        }

        .card-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }

        .card-title {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--text);
        }

        .card-status {
            font-size: 0.9rem;
            padding: 6px 15px;
            border-radius: 20px;
            font-weight: 600;
        }

        .status-updated {
            background: rgba(0, 200, 83, 0.2);
            color: #00c853;
            box-shadow: 0 0 10px rgba(0, 200, 83, 0.3);
        }

        .status-outdated {
            background: rgba(255, 82, 82, 0.2);
            color: #ff5252;
        }

        .status-featured {
            background: rgba(255, 193, 7, 0.2);
            color: #ffc107;
            box-shadow: 0 0 10px rgba(255, 193, 7, 0.3);
            animation: pulse 2s infinite;
        }

        .card-description {
            margin-bottom: 25px;
            color: var(--text-secondary);
            line-height: 1.6;
            min-height: 80px;
        }

        .card-link {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            color: white;
            text-align: center;
            padding: 14px 0;
            border-radius: 12px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
            cursor: pointer;
        }

        .card-link:hover {
            transform: scale(1.05);
            box-shadow: 0 8px 20px rgba(138, 43, 226, 0.5);
        }

        .card-link::after {
            content: "";
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.3), transparent);
            transition: 0.6s;
        }

        .card-link:hover::after {
            left: 100%;
        }

        .featured {
            border: 2px solid var(--accent);
            box-shadow: 0 0 30px rgba(255, 107, 107, 0.4);
            animation: featuredPulse 3s infinite;
        }

        .featured .card-title {
            color: var(--accent);
        }

        /* Modal de Script */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.8);
            backdrop-filter: blur(10px);
            z-index: 1000;
            justify-content: center;
            align-items: center;
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .modal.active {
            display: flex;
            opacity: 1;
        }

        .modal-content {
            background: var(--modal-bg);
            border-radius: 20px;
            width: 90%;
            max-width: 800px;
            max-height: 90vh;
            overflow: hidden;
            box-shadow: 0 0 50px rgba(138, 43, 226, 0.5);
            transform: translateY(50px);
            transition: transform 0.4s ease;
            display: flex;
            flex-direction: column;
        }

        .modal.active .modal-content {
            transform: translateY(0);
        }

        .modal-header {
            padding: 20px;
            background: rgba(30, 25, 60, 0.8);
            border-bottom: 1px solid var(--card-border);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .modal-title {
            font-size: 1.8rem;
            font-weight: 700;
            background: linear-gradient(90deg, var(--accent), var(--primary));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }

        .close-modal {
            background: none;
            border: none;
            color: var(--text);
            font-size: 1.8rem;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .close-modal:hover {
            color: var(--accent);
            transform: rotate(90deg);
        }

        .modal-body {
            padding: 25px;
            flex: 1;
            overflow-y: auto;
        }

        .script-content {
            background: rgba(10, 5, 25, 0.7);
            border-radius: 10px;
            padding: 20px;
            font-family: 'Courier New', monospace;
            font-size: 0.9rem;
            line-height: 1.6;
            white-space: pre-wrap;
            max-height: 400px;
            overflow-y: auto;
            margin-bottom: 25px;
        }

        .script-actions {
            display: flex;
            gap: 15px;
        }

        .btn {
            padding: 12px 25px;
            border-radius: 10px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            border: none;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .btn-primary {
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            color: white;
            flex: 1;
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(138, 43, 226, 0.4);
        }

        .btn-secondary {
            background: rgba(255, 255, 255, 0.1);
            color: var(--text);
        }

        .btn-secondary:hover {
            background: rgba(255, 255, 255, 0.2);
        }

        footer {
            background: rgba(10, 5, 25, 0.8);
            backdrop-filter: blur(10px);
            padding: 60px 20px 30px;
            margin-top: 80px;
            border-top: 1px solid rgba(138, 43, 226, 0.2);
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
        }

        .footer-section h3 {
            font-size: 1.5rem;
            margin-bottom: 20px;
            position: relative;
            padding-bottom: 10px;
        }

        .footer-section h3::after {
            content: "";
            position: absolute;
            bottom: 0;
            left: 0;
            width: 50px;
            height: 3px;
            background: var(--accent);
        }

        .footer-links {
            display: flex;
            flex-direction: column;
            gap: 12px;
        }

        .footer-link {
            color: var(--text-secondary);
            text-decoration: none;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .footer-link:hover {
            color: var(--accent);
            transform: translateX(5px);
        }

        .social-icons {
            display: flex;
            gap: 20px;
            margin-top: 20px;
        }

        .social-icon {
            width: 45px;
            height: 45px;
            border-radius: 50%;
            background: var(--card-bg);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.3rem;
            transition: all 0.3s ease;
            color: var(--text);
        }

        .social-icon:hover {
            background: var(--primary);
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(138, 43, 226, 0.4);
        }

        .copyright {
            text-align: center;
            padding-top: 40px;
            color: var(--text-secondary);
            font-size: 0.9rem;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            margin-top: 40px;
        }

        /* Animações */
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes fadeInDown {
            from { opacity: 0; transform: translateY(-30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes textGlow {
            0% { text-shadow: 0 0 10px rgba(138, 43, 226, 0.5); }
            100% { text-shadow: 0 0 20px rgba(138, 43, 226, 0.8), 0 0 30px rgba(255, 107, 107, 0.6); }
        }

        @keyframes bgPulse {
            0% { background-size: 100% 100%; }
            100% { background-size: 150% 150%; }
        }

        @keyframes float {
            0% { transform: translateY(0) rotate(0deg); opacity: 0; }
            10% { opacity: 1; }
            90% { opacity: 1; }
            100% { transform: translateY(-1000px) rotate(720deg); opacity: 0; }
        }

        @keyframes titleUnderline {
            from { transform: scaleX(0); }
            to { transform: scaleX(1); }
        }

        @keyframes cardAppear {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes pulse {
            0% { box-shadow: 0 0 0 0 rgba(255, 193, 7, 0.4); }
            70% { box-shadow: 0 0 0 10px rgba(255, 193, 7, 0); }
            100% { box-shadow: 0 0 0 0 rgba(255, 193, 7, 0); }
        }

        @keyframes featuredPulse {
            0% { box-shadow: 0 0 20px rgba(255, 107, 107, 0.4); }
            50% { box-shadow: 0 0 40px rgba(255, 107, 107, 0.6); }
            100% { box-shadow: 0 0 20px rgba(255, 107, 107, 0.4); }
        }

        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        @media (max-width: 768px) {
            .hero-title {
                font-size: 2.8rem;
            }
            
            .cards-grid {
                grid-template-columns: 1fr;
            }
            
            .nav-links {
                display: none;
            }
            
            .modal-content {
                width: 95%;
            }
            
            .script-actions {
                flex-direction: column;
            }
        }
    </style>
</head>
<body>
    <!-- Partículas animadas -->
    <div class="particles" id="particles"></div>
    
    <header>
        <div class="logo">
            <i class="fas fa-robot logo-icon"></i>
            <div class="logo-text">ROBLOX ELITE</div>
        </div>
        <div class="nav-links">
            <a href="#" class="nav-link">Home</a>
            <a href="#" class="nav-link">Executores</a>
            <a href="#" class="nav-link">Scripts</a>
            <a href="#" class="nav-link">Tutoriais</a>
            <a href="#" class="nav-link">Contato</a>
        </div>
    </header>

    <div class="hero">
        <h1 class="hero-title">EXECUTORES & SCRIPTS PREMIUM</h1>
        <p class="hero-subtitle">Acesse a melhor coleção de executores e scripts atualizados para Roblox</p>
        
        <div class="tabs">
            <button class="tab-btn active" data-tab="executors">Executores</button>
            <button class="tab-btn" data-tab="universal">Scripts Universais</button>
            <button class="tab-btn" data-tab="games">Scripts para Jogos</button>
            <button class="tab-btn" data-tab="events">Scripts para Eventos</button>
        </div>
    </div>

    <div class="container">
        <!-- Executores Section -->
        <section id="executors" class="content-section active">
            <h2 class="section-title">Executores Premium</h2>
            
            <div class="cards-grid">
                <div class="card">
                    <div class="card-header">
                        <div class="card-title">Delta-683</div>
                        <div class="card-status status-updated">ATUALIZADO ✔</div>
                    </div>
                    <div class="card-description">
                        Executor estável e confiável com suporte para a maioria dos scripts.
                    </div>
                    <a href="https://www.mediafire.com/file/scp0om4fyjwpbh8/Delta-2.683.775-01.apk/file" target="_blank" class="card-link">
                        <i class="fas fa-download"></i> BAIXAR AGORA
                    </a>
                </div>
                
                <div class="card">
                    <div class="card-header">
                        <div class="card-title">Cryptic-683</div>
                        <div class="card-status status-updated">ATUALIZADO ✔</div>
                    </div>
                    <div class="card-description">
                        Executor focado em segurança e privacidade.
                    </div>
                    <a href="https://www.mediafire.com/file/w4f7a2ezsa0sio3/Cryptic+2.683.775+APK.apk/file" target="_blank" class="card-link">
                        <i class="fas fa-download"></i> BAIXAR AGORA
                    </a>
                </div>
                
                <div class="card featured">
                    <div class="card-header">
                        <div class="card-title">ArceusX:1,7.5</div>
                        <div class="card-status status-featured">DESTAQUE ★</div>
                    </div>
                    <div class="card-description">
                        Versão atualizada do popular executor ArceusX. Compatível com a maioria dos scripts.
                    </div>
                    <a href="https://www.mediafire.com/file/1t0fuzh63it641m/Roblox_Arceus_X_NEO_1.7.5.apk/file" target="_blank" class="card-link">
                        <i class="fas fa-crown"></i> BAIXAR PREMIUM
                    </a>
                </div>
                
                <div class="card">
                    <div class="card-header">
                        <div class="card-title">Codex-683</div>
                        <div class="card-status status-updated">ATUALIZADO ✔</div>
                    </div>
                    <div class="card-description">
                        Executor avançado com recursos de depuração integrados.
                    </div>
                    <a href="https://www.mediafire.com/file/nlm86ppvpds7yad/Codex__v2.680.apk/file" target="_blank" class="card-link">
                        <i class="fas fa-download"></i> BAIXAR AGORA
                    </a>
                </div>
                
                <div class="card">
                    <div class="card-header">
                        <div class="card-title">Trigon-679</div>
                        <div class="card-status status-updated">ATUALIZADO ✔</div>
                    </div>
                    <div class="card-description">
                        Executor poderoso com excelente compatibilidade e desempenho.
                    </div>
                    <a href="https://www.mediafire.com/file/gzf3ji8b6iewf3f/Trigon_2.679.apk/file" target="_blank" class="card-link">
                        <i class="fas fa-download"></i> BAIXAR AGORA
                    </a>
                </div>
            </div>
        </section>
        
        <!-- Universal Scripts Section -->
        <section id="universal" class="content-section">
            <h2 class="section-title">Scripts Universais</h2>
            
            <div class="cards-grid">
                <div class="card featured">
                    <div class="card-header">
                        <div class="card-title">Infinite Yield</div>
                        <div class="card-status status-featured">TOP 1 ★</div>
                    </div>
                    <div class="card-description">
                        O script mais completo para administração e moderação em qualquer jogo.
                    </div>
                    <div class="card-link" data-script="loadstring(game:HttpGet('https://raw.githubusercontent.com/DarkNetworks/Infinite-Yield/main/latest.lua'))()">
                        <i class="fas fa-copy"></i> VER SCRIPT
                    </div>
                </div>
                
                <div class="card">
                    <div class="card-header">
                        <div class="card-title">Orca</div>
                        <div class="card-status status-updated">ATUALIZADO ✔</div>
                    </div>
                    <div class="card-description">
                        Script universal com diversas ferramentas e utilitários para jogos.
                    </div>
                    <div class="card-link" data-script="loadstring(game:HttpGet('https://raw.githubusercontent.com/richie0866/orca/master/public/latest.lua'))()">
                        <i class="fas fa-copy"></i> VER SCRIPT
                    </div>
                </div>
                
                <div class="card">
                    <div class="card-header">
                        <div class="card-title">Project Pastel</div>
                        <div class="card-status status-updated">NOVO ✨</div>
                    </div>
                    <div class="card-description">
                        Interface elegante com centenas de comandos para qualquer jogo Roblox.
                    </div>
                    <div class="card-link" data-script="loadstring(game:HttpGet('https://raw.githubusercontent.com/NUTellaVING/ProjectPastel/main/Loader.lua'))()">
                        <i class="fas fa-copy"></i> VER SCRIPT
                    </div>
                </div>
                
                <div class="card">
                    <div class="card-header">
                        <div class="card-title">Dark Dex</div>
                        <div class="card-status status-updated">PODEROSO ⚡</div>
                    </div>
                    <div class="card-description">
                        Ferramenta avançada para explorar e manipular o ambiente do jogo.
                    </div>
                    <div class="card-link" data-script="loadstring(game:HttpGet('https://pastebin.com/raw/Abcd1234'))()">
                        <i class="fas fa-copy"></i> VER SCRIPT
                    </div>
                </div>
            </div>
        </section>
        
        <!-- Game Scripts Section -->
        <section id="games" class="content-section">
            <h2 class="section-title">Scripts para Jogos</h2>
            
            <div class="cards-grid">
                <div class="card featured">
                    <div class="card-header">
                        <div class="card-title">Blade Ball</div>
                        <div class="card-status status-featured">DESTAQUE ★</div>
                    </div>
                    <div class="card-description">
                        Autododge, autoparry e outras vantagens para dominar no Blade Ball.
                    </div>
                    <div class="card-link" data-script="loadstring(game:HttpGet('https://raw.githubusercontent.com/luascriptsROBLOX/BladeBallXera/main/XeraUltron'))()">
                        <i class="fas fa-copy"></i> VER SCRIPT
                    </div>
                </div>
                
                <div class="card">
                    <div class="card-header">
                        <div class="card-title">Blox Fruits</div>
                        <div class="card-status status-updated">FARM ⚡</div>
                    </div>
                    <div class="card-description">
                        Auto farm, teleporte e outras vantagens para Blox Fruits.
                    </div>
                    <div class="card-link" data-script="loadstring(game:HttpGet('https://raw.githubusercontent.com/BasementHub/BH-Blox-fruit/main/W-Azure-V3'))()">
                        <i class="fas fa-copy"></i> VER SCRIPT
                    </div>
                </div>
                
                <div class="card">
                    <div class="card-header">
                        <div class="card-title">Arsenal</div>
                        <div class="card-status status-updated">AIMBOT 🎯</div>
                    </div>
                    <div class="card-description">
                        Aimbot, ESP, wallhack e outras vantagens para Arsenal.
                    </div>
                    <div class="card-link" data-script="loadstring(game:HttpGet('https://raw.githubusercontent.com/Theyfwdan/Theyfwdan/main/ExpressHubPaidVersion'))()">
                        <i class="fas fa-copy"></i> VER SCRIPT
                    </div>
                </div>
                
                <div class="card">
                    <div class="card-header">
                        <div class="card-title">Pet Simulator</div>
                        <div class="card-status status-updated">AUTO FARM 🤖</div>
                    </div>
                    <div class="card-description">
                        Autofarm de moedas, ovos e outros recursos em Pet Simulator.
                    </div>
                    <div class="card-link" data-script="loadstring(game:HttpGet('https://raw.githubusercontent.com/RenceeeX/PetsGo/main/RenceeXHub'))()">
                        <i class="fas fa-copy"></i> VER SCRIPT
                    </div>
                </div>
                
                <div class="card">
                    <div class="card-header">
                        <div class="card-title">Driving Empire</div>
                        <div class="card-status status-updated">MOEDAS 💰</div>
                    </div>
                    <div class="card-description">
                        Farm automático de moedas e recursos em Driving Empire.
                    </div>
                    <div class="card-link" data-script="loadstring(game:HttpGet('https://raw.githubusercontent.com/CasperFlyModz/discord.gg-rips/main/DrivingEmpire.lua'))()">
                        <i class="fas fa-copy"></i> VER SCRIPT
                    </div>
                </div>
                
                <div class="card">
                    <div class="card-header">
                        <div class="card-title">Toilet Tower Defense</div>
                        <div class="card-status status-updated">AUTO UPGRADE ⬆️</div>
                    </div>
                    <div class="card-description">
                        Autoplay, auto upgrade e outras vantagens para TTD.
                    </div>
                    <div class="card-link" data-script="loadstring(game:HttpGet('https://raw.githubusercontent.com/LOLking123456/TTD/main/ToiletDefense'))()">
                        <i class="fas fa-copy"></i> VER SCRIPT
                    </div>
                </div>
            </div>
        </section>
        
        <!-- Event Scripts Section -->
        <section id="events" class="content-section">
            <h2 class="section-title">Scripts para Eventos</h2>
            
            <div class="cards-grid">
                <div class="card featured">
                    <div class="card-header">
                        <div class="card-title">UGC Santa Suit</div>
                        <div class="card-status status-featured">EXCLUSIVO 🎅</div>
                    </div>
                    <div class="card-description">
                        Obtenha automaticamente todos os itens do evento de Natal UGC.
                    </div>
                    <div class="card-link" data-script="loadstring(game:HttpGet('https://raw.githubusercontent.com/ToraScript/Script/main/SantaSuit'))()">
                        <i class="fas fa-copy"></i> VER SCRIPT
                    </div>
                </div>
                
                <div class="card">
                    <div class="card-header">
                        <div class="card-title">Sonic Winter</div>
                        <div class="card-status status-updated">EVENTO ❄️</div>
                    </div>
                    <div class="card-description">
                        Complete automaticamente o evento de inverno do Sonic.
                    </div>
                    <div class="card-link" data-script="loadstring(game:HttpGet('https://raw.githubusercontent.com/ToraScript/Script/main/SonicWinter'))()">
                        <i class="fas fa-copy"></i> VER SCRIPT
                    </div>
                </div>
                
                <div class="card">
                    <div class="card-header">
                        <div class="card-title">Royale High Winter</div>
                        <div class="card-status status-updated">RECOMPENSAS 🎁</div>
                    </div>
                    <div class="card-description">
                        Farm automático de recompensas no evento de inverno do Royale High.
                    </div>
                    <div class="card-link" data-script="loadstring(game:HttpGet('https://raw.githubusercontent.com/ToraScript/Script/main/RoyaleHighWinter'))()">
                        <i class="fas fa-copy"></i> VER SCRIPT
                    </div>
                </div>
            </div>
        </section>
    </div>

    <!-- Modal para exibir scripts -->
    <div class="modal" id="scriptModal">
        <div class="modal-content">
            <div class="modal-header">
                <h3 class="modal-title" id="modalScriptTitle">Nome do Script</h3>
                <button class="close-modal" id="closeModal">&times;</button>
            </div>
            <div class="modal-body">
                <div class="script-content" id="scriptContent">
                    Carregando script...
                </div>
                <div class="script-actions">
                    <button class="btn btn-primary" id="copyScript">
                        <i class="fas fa-copy"></i> Copiar Script
                    </button>
                    <button class="btn btn-secondary" id="closeModalBtn">
                        <i class="fas fa-times"></i> Fechar
                    </button>
                </div>
            </div>
        </div>
    </div>

    <footer>
        <div class="footer-content">
            <div class="footer-section">
                <h3>Roblox Elite</h3>
                <p>Sua fonte premium de executores e scripts para Roblox. Atualizado diariamente por nossa equipe.</p>
                <div class="social-icons">
                    <a href="#" class="social-icon"><i class="fab fa-discord"></i></a>
                    <a href="#" class="social-icon"><i class="fab fa-youtube"></i></a>
                    <a href="#" class="social-icon"><i class="fab fa-twitter"></i></a>
                    <a href="#" class="social-icon"><i class="fab fa-tiktok"></i></a>
                </div>
            </div>
            
            <div class="footer-section">
                <h3>Links Rápidos</h3>
                <div class="footer-links">
                    <a href="#" class="footer-link"><i class="fas fa-chevron-right"></i> Executores</a>
                    <a href="#" class="footer-link"><i class="fas fa-chevron-right"></i> Scripts</a>
                    <a href="#" class="footer-link"><i class="fas fa-chevron-right"></i> Tutoriais</a>
                    <a href="#" class="footer-link"><i class="fas fa-chevron-right"></i> Atualizações</a>
                    <a href="#" class="footer-link"><i class="fas fa-chevron-right"></i> Suporte</a>
                </div>
            </div>
            
            <div class="footer-section">
                <h3>Recursos</h3>
                <div class="footer-links">
                    <a href="#" class="footer-link"><i class="fas fa-chevron-right"></i> Como Instalar</a>
                    <a href="#" class="footer-link"><i class="fas fa-chevron-right"></i> Perguntas Frequentes</a>
                    <a href="#" class="footer-link"><i class="fas fa-chevron-right"></i> Discord</a>
                    <a href="#" class="footer-link"><i class="fas fa-chevron-right"></i> Termos de Uso</a>
                    <a href="#" class="footer-link"><i class="fas fa-chevron-right"></i> Política de Privacidade</a>
                </div>
            </div>
        </div>
        
        <div class="copyright">
            © 2023 Roblox Elite. Todos os direitos reservados. Este site não é afiliado à Roblox Corporation.
        </div>
    </footer>

    <script>
        // Criar partículas animadas
        function createParticles() {
            const particlesContainer = document.getElementById('particles');
            const particleCount = 30;
            
            for (let i = 0; i < particleCount; i++) {
                const particle = document.createElement('div');
                particle.classList.add('particle');
                
                // Tamanho e posição aleatórios
                const size = Math.random() * 10 + 5;
                const posX = Math.random() * 100;
                const posY = Math.random() * 100;
                const delay = Math.random() * 15;
                const duration = 10 + Math.random() * 20;
                
                particle.style.width = `${size}px`;
                particle.style.height = `${size}px`;
                particle.style.left = `${posX}%`;
                particle.style.top = `${posY}%`;
                particle.style.animationDelay = `${delay}s`;
                particle.style.animationDuration = `${duration}s`;
                
                // Cor aleatória
                const colors = ['#8a2be2', '#5e17eb', '#ff6b6b', '#00c853', '#ffc107'];
                const color = colors[Math.floor(Math.random() * colors.length)];
                particle.style.background = color;
                
                particlesContainer.appendChild(particle);
            }
        }
        
        // Tab switching functionality
        document.querySelectorAll('.tab-btn').forEach(button => {
            button.addEventListener('click', () => {
                // Remove active class from all buttons and sections
                document.querySelectorAll('.tab-btn').forEach(btn => btn.classList.remove('active'));
                document.querySelectorAll('.content-section').forEach(section => section.classList.remove('active'));
                
                // Add active class to clicked button
                button.classList.add('active');
                
                // Show corresponding section
                const tabId = button.getAttribute('data-tab');
                document.getElementById(tabId).classList.add('active');
                
                // Re-animate cards
                document.querySelectorAll('.card').forEach(card => {
                    card.style.animation = 'none';
                    setTimeout(() => {
                        card.style.animation = 'cardAppear 0.6s ease forwards';
                    }, 10);
                });
            });
        });
        
        // Card hover animations
        document.querySelectorAll('.card').forEach(card => {
            card.addEventListener('mouseenter', () => {
                card.style.transform = 'translateY(-15px) rotate(1deg)';
            });
            
            card.addEventListener('mouseleave', () => {
                card.style.transform = 'translateY(0) rotate(0)';
            });
        });
        
        // Modal functionality
        const modal = document.getElementById('scriptModal');
        const modalTitle = document.getElementById('modalScriptTitle');
        const scriptContent = document.getElementById('scriptContent');
        const closeModal = document.getElementById('closeModal');
        const closeModalBtn = document.getElementById('closeModalBtn');
        const copyScriptBtn = document.getElementById('copyScript');
        
        // Abrir modal ao clicar em VER SCRIPT
        document.querySelectorAll('.card-link[data-script]').forEach(link => {
            link.addEventListener('click', function() {
                const script = this.getAttribute('data-script');
                const cardTitle = this.closest('.card').querySelector('.card-title').textContent;
                
                modalTitle.textContent = cardTitle;
                scriptContent.textContent = script;
                modal.classList.add('active');
            });
        });
        
        // Fechar modal
        closeModal.addEventListener('click', () => {
            modal.classList.remove('active');
        });
        
        closeModalBtn.addEventListener('click', () => {
            modal.classList.remove('active');
        });
        
        // Fechar modal ao clicar fora do conteúdo
        modal.addEventListener('click', (e) => {
            if (e.target === modal) {
                modal.classList.remove('active');
            }
        });
        
        // Copiar script
        copyScriptBtn.addEventListener('click', () => {
            const textarea = document.createElement('textarea');
            textarea.value = scriptContent.textContent;
            document.body.appendChild(textarea);
            textarea.select();
            document.execCommand('copy');
            document.body.removeChild(textarea);
            
            // Feedback visual
            const originalText = copyScriptBtn.innerHTML;
            copyScriptBtn.innerHTML = '<i class="fas fa-check"></i> Script Copiado!';
            
            setTimeout(() => {
                copyScriptBtn.innerHTML = originalText;
            }, 2000);
        });
        
        // Inicializar partículas
        createParticles();
        
        // Animação de rolagem suave
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });
    </script>
</body>
</html>
