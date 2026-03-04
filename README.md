<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Kings Of Dragons</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700;800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style id="dynamic-styles">
        body { font-family: 'Inter', sans-serif; }
        
        /* ===== ANIMAÇÕES ===== */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        @keyframes slideInLeft {
            from { opacity: 0; transform: translateX(-80px); }
            to { opacity: 1; transform: translateX(0); }
        }
        
        @keyframes slideInRight {
            from { opacity: 0; transform: translateX(80px); }
            to { opacity: 1; transform: translateX(0); }
        }
        
        @keyframes slideInUp {
            from { opacity: 0; transform: translateY(50px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-15px); }
            100% { transform: translateY(0px); }
        }
        
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }
        
        @keyframes glow {
            0% { box-shadow: 0 0 5px #facc15, 0 0 10px #facc15, 0 0 15px #facc15; }
            50% { box-shadow: 0 0 20px #facc15, 0 0 30px #facc15, 0 0 40px #facc15; }
            100% { box-shadow: 0 0 5px #facc15, 0 0 10px #facc15, 0 0 15px #facc15; }
        }
        
        @keyframes neonPulse {
            0% { filter: drop-shadow(0 0 2px #facc15) drop-shadow(0 0 5px #facc15) drop-shadow(0 0 10px #facc15); opacity: 0.8; }
            50% { filter: drop-shadow(0 0 5px #facc15) drop-shadow(0 0 15px #facc15) drop-shadow(0 0 30px #facc15); opacity: 1; }
            100% { filter: drop-shadow(0 0 2px #facc15) drop-shadow(0 0 5px #facc15) drop-shadow(0 0 10px #facc15); opacity: 0.8; }
        }
        
        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }
        
        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }
        
        @keyframes shimmer {
            0% { background-position: -200% 0; }
            100% { background-position: 200% 0; }
        }
        
        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }
        
        @keyframes modalPop {
            0% { opacity: 0; transform: scale(0.8); }
            100% { opacity: 1; transform: scale(1); }
        }
        
        @keyframes copySuccess {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); background-color: #22c55e; }
            100% { transform: scale(1); }
        }
        
        /* Classes de Animação */
        .fade-in { animation: fadeIn 1s ease forwards; }
        .slide-left { animation: slideInLeft 1s ease forwards; }
        .slide-right { animation: slideInRight 1s ease forwards; }
        .slide-up { animation: slideInUp 1s ease forwards; }
        .float { animation: float 4s ease-in-out infinite; }
        .float-slow { animation: float 6s ease-in-out infinite; }
        .pulse { animation: pulse 2s ease-in-out infinite; }
        .glow { animation: glow 2s ease-in-out infinite; }
        .neon-pulse { animation: neonPulse 2s ease-in-out infinite; }
        .rotate-slow { animation: rotate 10s linear infinite; }
        .bounce { animation: bounce 2s ease infinite; }
        .modal-pop { animation: modalPop 0.3s ease-out forwards; }
        .copy-success { animation: copySuccess 0.5s ease forwards; }
        
        /* Logo KOD com imagem */
        .logo-kod-img {
            height: 50px;
            width: auto;
            transition: all 0.3s ease;
        }
        .logo-kod-img:hover {
            transform: scale(1.05);
            filter: drop-shadow(0 0 10px #facc15);
        }
        
        /* Ícone do servidor */
        .server-icon {
            width: 64px;
            height: 64px;
            border-radius: 16px;
            object-fit: cover;
            border: 2px solid #facc15;
            transition: all 0.3s ease;
        }
        .server-icon:hover {
            transform: scale(1.1);
            box-shadow: 0 0 20px #facc15;
        }
        
        /* Botão de copiar IP */
        .copy-ip-btn {
            transition: all 0.3s ease;
            cursor: pointer;
        }
        .copy-ip-btn.copied {
            background-color: #22c55e !important;
        }
        
        /* Imagem com efeito neon */
        .neon-image {
            position: relative;
            border-radius: 24px;
            overflow: hidden;
            animation: neonPulse 2s ease-in-out infinite;
        }
        .neon-image::before {
            content: '';
            position: absolute;
            top: -2px;
            left: -2px;
            right: -2px;
            bottom: -2px;
            background: linear-gradient(45deg, #facc15, #ff0, #facc15, #ff0);
            border-radius: 26px;
            z-index: -1;
            animation: rotate 4s linear infinite;
            opacity: 0.7;
        }
        .neon-image::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(45deg, transparent, rgba(250,204,21,0.3), transparent);
            border-radius: 24px;
            animation: shimmer 3s linear infinite;
        }
        .neon-image img {
            position: relative;
            z-index: 1;
            transition: all 0.3s ease;
            border: 2px solid transparent;
        }
        .neon-image:hover img { transform: scale(1.02); }
        
        /* Hover Animations */
        .hover-scale { transition: transform 0.3s ease; }
        .hover-scale:hover { transform: scale(1.05); }
        .hover-rotate { transition: transform 0.3s ease; }
        .hover-rotate:hover { transform: rotate(5deg); }
        .hover-glow { transition: all 0.3s ease; }
        .hover-glow:hover { filter: drop-shadow(0 0 10px currentColor); }
        
        /* Cards de Download com animação */
        .download-card {
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            opacity: 0;
            animation: slideInUp 0.8s ease forwards;
            position: relative;
            overflow: hidden;
        }
        .download-card:nth-child(1) { animation-delay: 0.1s; }
        .download-card:nth-child(2) { animation-delay: 0.3s; }
        .download-card:nth-child(3) { animation-delay: 0.5s; }
        .download-card:nth-child(4) { animation-delay: 0.7s; }
        .download-card:hover {
            transform: translateY(-15px) scale(1.02);
            box-shadow: 0 20px 30px -10px rgba(250, 204, 21, 0.4);
        }
        .download-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255,255,255,0.1), transparent);
            transform: rotate(45deg);
            transition: transform 0.6s;
        }
        .download-card:hover::before { transform: rotate(45deg) translate(50%, 50%); }
        .download-card i { transition: all 0.3s ease; }
        .download-card:hover i {
            transform: scale(1.2) rotate(5deg);
            animation: pulse 1s ease infinite;
        }
        
        /* Botões com animação */
        .btn-download {
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
            z-index: 1;
        }
        .btn-download::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.3);
            transform: translate(-50%, -50%);
            transition: width 0.6s, height 0.6s;
            z-index: -1;
        }
        .btn-download:hover::before { width: 300px; height: 300px; }
        .btn-download:active { transform: scale(0.95); }
        .btn-download i { transition: transform 0.3s ease; }
        .btn-download:hover i { transform: translateX(5px); }
        
        /* Regras Cards com animação */
        .rule-card {
            transition: all 0.4s ease;
            opacity: 0;
            animation: slideInLeft 0.8s ease forwards;
            position: relative;
            overflow: hidden;
            backdrop-filter: blur(5px);
            cursor: pointer;
        }
        .rule-card:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: 0 20px 30px -10px rgba(250, 204, 21, 0.3);
        }
        .rule-card::after {
            content: '';
            position: absolute;
            top: -100%;
            left: -100%;
            width: 300%;
            height: 300%;
            background: linear-gradient(45deg, transparent, rgba(250, 204, 21, 0.1), transparent);
            transform: rotate(45deg);
            transition: transform 0.8s;
        }
        .rule-card:hover::after { transform: rotate(45deg) translate(50%, 50%); }
        
        /* Header animado */
        header {
            transition: all 0.3s ease;
            animation: slideInUp 0.8s ease;
        }
        header:hover {
            background-color: rgba(0, 0, 0, 0.9);
            backdrop-filter: blur(10px);
        }
        nav a {
            position: relative;
            transition: color 0.3s ease;
            cursor: pointer;
        }
        nav a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: #facc15;
            transition: width 0.3s ease;
        }
        nav a:hover::after { width: 100%; }
        
        /* Hero Section animado */
        .hero-content {
            opacity: 0;
            animation: slideInLeft 1.2s ease forwards;
        }
        .hero-image {
            opacity: 0;
            animation: slideInRight 1.2s ease forwards;
        }
        
        /* Títulos animados */
        h2 span {
            display: inline-block;
            animation: float 3s ease-in-out infinite;
            text-shadow: 0 0 10px currentColor;
        }
        h3 {
            position: relative;
            display: inline-block;
        }
        h3::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 50px;
            height: 3px;
            background: #facc15;
            transition: width 0.3s ease;
        }
        h3:hover::after { width: 100px; }
        
        /* Footer animado */
        footer {
            transition: all 0.3s ease;
            animation: fadeIn 1.5s ease;
        }
        footer:hover { letter-spacing: 1px; }
        
        /* Animações de background */
        .bg-gradient-animated {
            background-size: 200% 200%;
            animation: gradientShift 10s ease infinite;
        }
        
        /* Scroll suave */
        html { scroll-behavior: smooth; }
        
        /* Modal */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-color: rgba(0, 0, 0, 0.8);
            backdrop-filter: blur(5px);
            z-index: 1000;
            display: none;
            justify-content: center;
            align-items: center;
        }
        .modal-content {
            background: linear-gradient(135deg, #1a1a1a, #2d2d2d);
            border: 2px solid #facc15;
            border-radius: 30px;
            padding: 30px;
            max-width: 500px;
            width: 90%;
            position: relative;
            box-shadow: 0 0 50px rgba(250,204,21,0.3);
            animation: modalPop 0.3s ease-out;
        }
        .modal-close {
            position: absolute;
            top: 15px;
            right: 15px;
            width: 30px;
            height: 30px;
            border-radius: 50%;
            background: #facc15;
            color: black;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .modal-close:hover {
            transform: rotate(90deg);
            background: #ff0;
        }
        .modal-icon {
            font-size: 50px;
            color: #facc15;
            margin-bottom: 20px;
            text-align: center;
        }
        .modal-title {
            font-size: 28px;
            font-weight: 800;
            color: #facc15;
            margin-bottom: 15px;
            text-align: center;
        }
        .modal-description {
            color: #e0e0e0;
            line-height: 1.6;
            margin-bottom: 20px;
        }
        .modal-punishment {
            background: rgba(250,204,21,0.1);
            border-left: 4px solid #facc15;
            padding: 15px;
            border-radius: 10px;
            margin-top: 20px;
        }
        .modal-punishment h4 {
            color: #facc15;
            font-weight: 700;
            margin-bottom: 5px;
        }
        .modal-punishment p { color: #b0b0b0; }
        
        /* Toast de notificação */
        .toast-notification {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: #22c55e;
            color: white;
            padding: 12px 24px;
            border-radius: 50px;
            font-weight: 600;
            box-shadow: 0 5px 20px rgba(34, 197, 94, 0.3);
            z-index: 9999;
            animation: slideInUp 0.3s ease forwards;
        }
        
        /* Preview de cores animado */
        .color-preview {
            width: 30px;
            height: 30px;
            border-radius: 50%;
            border: 2px solid #fff;
            display: inline-block;
            margin-left: 10px;
            vertical-align: middle;
            transition: all 0.3s ease;
            animation: pulse 2s ease infinite;
        }
        .color-preview:hover {
            transform: scale(1.2);
            box-shadow: 0 0 15px currentColor;
        }
        
        /* Loading animation */
        .loading-spinner {
            width: 40px;
            height: 40px;
            border: 4px solid rgba(255,255,255,0.1);
            border-radius: 50%;
            border-top-color: currentColor;
            animation: rotate 1s linear infinite;
        }
        
        /* Efeito de brilho no texto */
        .shimmer-text {
            background: linear-gradient(90deg, transparent, currentColor, transparent);
            background-size: 200% 100%;
            animation: shimmer 3s infinite;
            -webkit-background-clip: text;
            background-clip: text;
        }
        
        /* Card de Recrutamento */
        .recruitment-card {
            transition: all 0.4s ease;
            opacity: 0;
            animation: slideInUp 0.8s ease forwards;
            position: relative;
            overflow: hidden;
            cursor: pointer;
        }
        .recruitment-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 30px -10px rgba(250, 204, 21, 0.4);
        }
        .recruitment-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(250,204,21,0.2), transparent);
            transform: rotate(45deg);
            transition: transform 0.6s;
        }
        .recruitment-card:hover::before { transform: rotate(45deg) translate(50%, 50%); }
        
        .discord-button {
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }
        .discord-button:hover {
            transform: scale(1.05);
            box-shadow: 0 0 30px rgba(114, 137, 218, 0.5);
        }
        .discord-button i { transition: transform 0.3s ease; }
        .discord-button:hover i { transform: rotate(360deg); }
        
        /* Card de Servidor */
        .server-card {
            transition: all 0.3s ease;
            background: linear-gradient(135deg, rgba(250,204,21,0.1), rgba(0,0,0,0.3));
            border: 1px solid rgba(250,204,21,0.3);
        }
        .server-card:hover {
            transform: translateY(-5px);
            border-color: #facc15;
            box-shadow: 0 10px 20px -5px rgba(250,204,21,0.3);
        }
        
        /* Card de Membro */
        .member-card {
            transition: all 0.3s ease;
            background: rgba(39, 39, 42, 0.6);
            border: 1px solid #3f3f46;
        }
        .member-card:hover {
            transform: translateY(-5px);
            border-color: #facc15;
            box-shadow: 0 10px 20px -5px rgba(250,204,21,0.3);
        }
        .member-avatar {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            border: 3px solid #facc15;
            transition: all 0.3s ease;
        }
        .member-avatar:hover {
            transform: scale(1.1);
            box-shadow: 0 0 20px #facc15;
        }

        /* Estilo para elementos editáveis */
        [contenteditable="true"] {
            border: 1px dashed #facc15;
            padding: 4px 8px;
            border-radius: 4px;
            transition: all 0.3s ease;
        }
        [contenteditable="true"]:hover {
            background: rgba(250,204,21,0.1);
        }
        [contenteditable="true"]:focus {
            outline: none;
            border-color: #facc15;
            background: rgba(250,204,21,0.2);
        }
        
        /* Admin input style */
        .admin-input {
            background: #1f1f1f;
            border: 1px solid #333;
            color: white;
            padding: 8px 12px;
            border-radius: 8px;
            width: 100%;
            transition: all 0.3s ease;
        }
        .admin-input:focus {
            border-color: #facc15;
            outline: none;
            box-shadow: 0 0 10px rgba(250,204,21,0.3);
        }
        .admin-section {
            background: rgba(0,0,0,0.3);
            border-radius: 12px;
            padding: 20px;
            margin-bottom: 20px;
            border: 1px solid #333;
        }
    </style>
</head>
<body class="bg-gradient-to-br from-black via-zinc-900 to-black text-white bg-gradient-animated">

<!-- HEADER -->
<header id="mainHeader" class="border-b border-zinc-800 backdrop-blur-md bg-black/40 sticky top-0 z-50">
    <div class="max-w-7xl mx-auto px-6 py-4 flex justify-between items-center">
        <!-- LOGO KOD -->
        <img src="https://cdn.discordapp.com/attachments/1476804123880849438/1476804185121886281/ChatGPT_Image_27_de_fev._de_2026_01_28_20.png?ex=69a90c13&is=69a7ba93&hm=3c3354ce9d3901e590aacc74438f71ca9904268a53bcc9027a5a1d6482681be0&" alt="The Kings Of Dragons Logo" class="logo-kod-img float-slow" id="siteLogo">
        
        <nav class="hidden md:flex gap-8 text-sm font-semibold">
            <a onclick="scrollToSection('inicio')" class="hover:text-yellow-400 transition">Início</a>
            <a onclick="scrollToSection('regras')" class="hover:text-yellow-400 transition">Regras</a>
            <a onclick="scrollToSection('recrutamento')" class="hover:text-yellow-400 transition">Recrutamento</a>
            <a onclick="scrollToSection('servidores')" class="hover:text-yellow-400 transition">Servidores</a>
            <a onclick="scrollToSection('informacoes')" class="hover:text-yellow-400 transition">Informações</a>
            <a onclick="scrollToSection('download')" class="hover:text-yellow-400 transition">Downloads</a>
        </nav>
    </div>
</header>

<!-- HERO -->
<section id="inicio" class="max-w-7xl mx-auto px-6 py-20 grid md:grid-cols-2 gap-12 items-center">
    <div class="hero-content">
        <h2 id="heroTitulo" class="text-5xl font-extrabold leading-tight mb-6">
            The <span id="heroSpan" class="text-yellow-400">Kings Of Dragons</span><br>
            Farm & PvP 
        </h2>
        <p id="heroTexto" class="text-zinc-400 mb-8 text-lg">
            Somos um clã focado em Farm e PvP, com organização e estrutura avançada. 
            Aqui você encontra ferramentas exclusivas, treinos intensivos e uma comunidade dedicada 
            a dominar os servidores mais competitivos. Seja para farmar recursos ou para batalhas 
            épicas, a KOD é o seu lugar.
        </p>
    </div>
    <div class="hero-image neon-image">
        <img src="welcome.png" class="rounded-3xl shadow-2xl border border-zinc-800 hover-scale" alt="Welcome KOD" id="heroImage">
    </div>
</section>

<!-- REGRAS -->
<section id="regras" class="bg-zinc-900/50 border-t border-zinc-800 py-20">
    <div class="max-w-6xl mx-auto px-6">
        <h3 id="regrasTitulo" class="text-4xl font-extrabold mb-12 text-center relative">Regras do Clã KOD</h3>
        
        <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6" id="regrasContainer">
            <!-- Regras serão geradas dinamicamente -->
        </div>
    </div>
</section>

<!-- RECRUTAMENTO -->
<section id="recrutamento" class="py-20">
    <div class="max-w-6xl mx-auto px-6">
        <h3 id="recrutamentoTitulo" class="text-4xl font-extrabold mb-12 text-center relative">Junte-se ao Clã KOD</h3>
        
        <div class="grid md:grid-cols-2 gap-8">
            <!-- Card de Informações -->
            <div class="recruitment-card bg-zinc-800/60 p-8 rounded-3xl border border-zinc-700">
                <div class="text-6xl mb-6 text-yellow-400 text-center"><i class="fas fa-users float"></i></div>
                <h4 class="text-2xl font-bold mb-4 text-center text-yellow-400">Estamos Recrutando!</h4>
                <p class="text-zinc-400 mb-6 text-center" id="recrutamentoTexto">
                    Procuramos jogadores dedicados para Farm e PvP, com espírito de equipe e vontade de evoluir. 
                    Se você tem perfil competitivo e quer fazer parte de uma comunidade organizada, venha para a KOD!
                </p>
                
                <div class="space-y-4 mb-8">
                    <div class="flex items-center gap-3 text-zinc-300"><i class="fas fa-check-circle text-yellow-400"></i><span>Mínimo de 16 anos</span></div>
                    <div class="flex items-center gap-3 text-zinc-300"><i class="fas fa-check-circle text-yellow-400"></i><span>Disponibilidade para farm e treinos de PvP</span></div>
                    <div class="flex items-center gap-3 text-zinc-300"><i class="fas fa-check-circle text-yellow-400"></i><span>Microfone e Discord obrigatórios</span></div>
                    <div class="flex items-center gap-3 text-zinc-300"><i class="fas fa-check-circle text-yellow-400"></i><span>Experiência em Farm e PvP (1.8.9 ou superior)</span></div>
                    <div class="flex items-center gap-3 text-zinc-300"><i class="fas fa-check-circle text-yellow-400"></i><span>Trabalho em equipe e dedicação</span></div>
                </div>
            </div>
            
            <!-- Card do Discord -->
            <div class="recruitment-card bg-gradient-to-br from-[#5865F2] to-[#404EED] p-8 rounded-3xl shadow-2xl">
                <div class="text-6xl mb-6 text-white text-center"><i class="fab fa-discord bounce"></i></div>
                <h4 class="text-2xl font-bold mb-4 text-center text-white">Entre no nosso Discord</h4>
                <p class="text-white/90 mb-8 text-center">Acesse nosso servidor no Discord para participar do processo seletivo e conhecer a comunidade.</p>
                
                <div class="bg-white/10 rounded-xl p-4 mb-8 text-center">
                    <span class="text-white font-mono text-xl" id="discordText">discord.gg/KA54ZfFqdX</span>
                </div>
                
                <a href="https://discord.gg/KA54ZfFqdX" target="_blank" class="discord-button block w-full bg-white text-[#5865F2] font-bold text-center px-6 py-4 rounded-xl transition transform hover:scale-105 text-lg" id="discordLink">
                    <i class="fab fa-discord mr-2"></i> Entrar no Discord
                </a>
                
                <p class="text-white/70 text-sm mt-6 text-center">Ao entrar, leia as regras e abra um ticket para iniciar seu recrutamento.</p>
            </div>
        </div>
    </div>
</section>

<!-- SERVIDORES -->
<section id="servidores" class="bg-zinc-900/50 border-t border-zinc-800 py-20">
    <div class="max-w-6xl mx-auto px-6">
        <h3 id="servidoresTitulo" class="text-4xl font-extrabold mb-12 text-center relative">Servidores que Jogamos</h3>
        
        <div id="servidoresGrid" class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
            <!-- Cards serão gerados dinamicamente -->
        </div>
    </div>
</section>

<!-- INFORMAÇÕES - HIERARQUIA -->
<section id="informacoes" class="py-20">
    <div class="max-w-6xl mx-auto px-6">
        <h3 id="hierarquiaTitulo" class="text-4xl font-extrabold mb-12 text-center relative">Hierarquia do Clã</h3>
        
        <div id="hierarquiaGrid" class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
            <!-- Cards serão gerados dinamicamente -->
        </div>
    </div>
</section>

<!-- DOWNLOAD -->
<section id="download" class="py-20">
    <div class="max-w-6xl mx-auto px-6 text-center">
        <h3 id="downloadTitulo" class="text-4xl font-extrabold mb-4 relative">Downloads Oficial</h3>
        <p id="downloadTexto" class="text-zinc-400 mb-12">Downloads de nossa Textura e Modpacks Oficiais!</p>
        
        <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-6" id="downloadsContainer">
            <!-- Cards serão gerados dinamicamente -->
        </div>
    </div>
</section>

<!-- FOOTER -->
<footer id="mainFooter" class="border-t border-zinc-800 py-10 text-center text-zinc-500 text-sm">
    © 2026 The Kings Of Dragons - Todos os direitos reservados
</footer>

<!-- MODAL DE REGRAS -->
<div id="modalOverlay" class="modal-overlay" onclick="fecharModal()">
    <div class="modal-content" onclick="event.stopPropagation()">
        <div class="modal-close" onclick="fecharModal()"><i class="fas fa-times"></i></div>
        <div id="modalIcon" class="modal-icon"><i class="fas fa-heart"></i></div>
        <h3 id="modalTitle" class="modal-title">Título da Regra</h3>
        <div id="modalDescription" class="modal-description">Descrição detalhada da regra.</div>
        <div class="modal-punishment">
            <h4><i class="fas fa-exclamation-triangle mr-2"></i> Punição:</h4>
            <p id="modalPunishment">Descrição da punição para quem violar esta regra.</p>
        </div>
        <div class="mt-6 text-center">
            <button onclick="fecharModal()" class="bg-yellow-500 hover:bg-yellow-400 text-black font-bold px-6 py-2 rounded-xl transition">Entendi</button>
        </div>
    </div>
</div>

<!-- PAINEL ADMIN (ACESSO VIA #KOD.admin) -->
<div id="adminPanel" class="hidden fixed inset-0 bg-black/95 z-[1001] overflow-auto p-4 md:p-10">
    <div class="max-w-6xl mx-auto bg-zinc-900 p-6 md:p-10 rounded-3xl border border-zinc-700">
        <h2 class="text-3xl font-extrabold mb-8 text-yellow-400 flex items-center gap-3">
            <i class="fas fa-cog rotate-slow"></i> Painel Administrativo - The Kings Of Dragons
        </h2>
        
        <!-- TABS -->
        <div class="flex flex-wrap gap-2 mb-8 border-b border-zinc-700 pb-2">
            <button onclick="showTab('textos')" class="tab-btn active bg-yellow-500 text-black px-4 py-2 rounded-xl font-bold hover-scale">Textos</button>
            <button onclick="showTab('cores')" class="tab-btn bg-zinc-800 text-white px-4 py-2 rounded-xl font-bold hover-scale">Cores</button>
            <button onclick="showTab('downloads')" class="tab-btn bg-zinc-800 text-white px-4 py-2 rounded-xl font-bold hover-scale">Downloads</button>
            <button onclick="showTab('regras')" class="tab-btn bg-zinc-800 text-white px-4 py-2 rounded-xl font-bold hover-scale">Regras</button>
            <button onclick="showTab('servidores')" class="tab-btn bg-zinc-800 text-white px-4 py-2 rounded-xl font-bold hover-scale">Servidores</button>
            <button onclick="showTab('hierarquia')" class="tab-btn bg-zinc-800 text-white px-4 py-2 rounded-xl font-bold hover-scale">Hierarquia</button>
            <button onclick="showTab('avancado')" class="tab-btn bg-zinc-800 text-white px-4 py-2 rounded-xl font-bold hover-scale">Avançado</button>
        </div>
        
        <!-- TAB TEXTOS -->
        <div id="tab-textos" class="tab-content">
            <div class="grid md:grid-cols-2 gap-6">
                <div class="admin-section">
                    <h4 class="text-yellow-400 font-bold mb-4">Logo e Hero</h4>
                    <label class="block mb-2 font-semibold text-sm">URL da Logo</label>
                    <input id="editLogoUrl" class="admin-input mb-4" value="https://cdn.discordapp.com/attachments/1476804123880849438/1476804185121886281/ChatGPT_Image_27_de_fev._de_2026_01_28_20.png?ex=69a90c13&is=69a7ba93&hm=3c3354ce9d3901e590aacc74438f71ca9904268a53bcc9027a5a1d6482681be0&">
                    
                    <label class="block mb-2 font-semibold text-sm">Título Hero</label>
                    <input id="editHeroTitulo" class="admin-input mb-4" value="The Kings Of Dragons - Farm & PvP">
                    
                    <label class="block mb-2 font-semibold text-sm">Texto Hero</label>
                    <textarea id="editHeroTexto" class="admin-input mb-4" rows="3">Somos um clã focado em Farm e PvP, com organização e estrutura avançada. Aqui você encontra ferramentas exclusivas, treinos intensivos e uma comunidade dedicada a dominar os servidores mais competitivos. Seja para farmar recursos ou para batalhas épicas, a KOD é o seu lugar.</textarea>
                    
                    <label class="block mb-2 font-semibold text-sm">URL Imagem Hero</label>
                    <input id="editHeroImage" class="admin-input mb-4" value="welcome.png">
                </div>
                
                <div class="admin-section">
                    <h4 class="text-yellow-400 font-bold mb-4">Títulos das Seções</h4>
                    <label class="block mb-2 font-semibold text-sm">Título Regras</label>
                    <input id="editRegrasTitulo" class="admin-input mb-4" value="Regras do Clã KOD">
                    
                    <label class="block mb-2 font-semibold text-sm">Título Recrutamento</label>
                    <input id="editRecrutamentoTitulo" class="admin-input mb-4" value="Junte-se ao Clã KOD">
                    
                    <label class="block mb-2 font-semibold text-sm">Texto Recrutamento</label>
                    <textarea id="editRecrutamentoTexto" class="admin-input mb-4" rows="3">Procuramos jogadores dedicados para Farm e PvP, com espírito de equipe e vontade de evoluir. Se você tem perfil competitivo e quer fazer parte de uma comunidade organizada, venha para a KOD!</textarea>
                    
                    <label class="block mb-2 font-semibold text-sm">Título Servidores</label>
                    <input id="editServidoresTitulo" class="admin-input mb-4" value="Servidores que Jogamos">
                    
                    <label class="block mb-2 font-semibold text-sm">Título Hierarquia</label>
                    <input id="editHierarquiaTitulo" class="admin-input mb-4" value="Hierarquia do Clã">
                    
                    <label class="block mb-2 font-semibold text-sm">Título Download</label>
                    <input id="editDownloadTitulo" class="admin-input mb-4" value="Downloads Oficial">
                    
                    <label class="block mb-2 font-semibold text-sm">Texto Download</label>
                    <input id="editDownloadTexto" class="admin-input mb-4" value="Downloads de nossa Textura e Modpacks Oficiais!">
                    
                    <label class="block mb-2 font-semibold text-sm">Footer Text</label>
                    <input id="editFooterTexto" class="admin-input mb-4" value="© 2026 The Kings Of Dragons - Todos os direitos reservados">
                </div>
            </div>
        </div>
        
        <!-- TAB CORES -->
        <div id="tab-cores" class="tab-content hidden">
            <div class="grid md:grid-cols-3 gap-6">
                <div class="admin-section">
                    <h4 class="text-yellow-400 font-bold mb-4">Cores Principais</h4>
                    <label class="block mb-2 font-semibold text-sm">Cor Principal</label>
                    <input type="color" id="editCorPrincipal" class="w-full h-12 mb-4 rounded-xl cursor-pointer" value="#facc15">
                    
                    <label class="block mb-2 font-semibold text-sm">Cor do Texto</label>
                    <input type="color" id="editCorTexto" class="w-full h-12 mb-4 rounded-xl cursor-pointer" value="#ffffff">
                    
                    <label class="block mb-2 font-semibold text-sm">Cor de Fundo</label>
                    <input type="color" id="editCorFundo" class="w-full h-12 mb-4 rounded-xl cursor-pointer" value="#000000">
                </div>
                
                <div class="admin-section">
                    <h4 class="text-yellow-400 font-bold mb-4">Cores dos Cards</h4>
                    <label class="block mb-2 font-semibold text-sm">Cor dos Cards</label>
                    <input type="color" id="editCorCard" class="w-full h-12 mb-4 rounded-xl cursor-pointer" value="#27272a">
                    
                    <label class="block mb-2 font-semibold text-sm">Cor das Bordas</label>
                    <input type="color" id="editCorBorda" class="w-full h-12 mb-4 rounded-xl cursor-pointer" value="#3f3f46">
                    
                    <label class="block mb-2 font-semibold text-sm">Cor Hover</label>
                    <input type="color" id="editCorHover" class="w-full h-12 mb-4 rounded-xl cursor-pointer" value="#eab308">
                </div>
                
                <div class="admin-section">
                    <h4 class="text-yellow-400 font-bold mb-4">Gradiente</h4>
                    <label class="block mb-2 font-semibold text-sm">Gradiente Início</label>
                    <input type="color" id="editGradientStart" class="w-full h-12 mb-2 rounded-xl cursor-pointer" value="#000000">
                    
                    <label class="block mb-2 font-semibold text-sm">Gradiente Meio</label>
                    <input type="color" id="editGradientMid" class="w-full h-12 mb-2 rounded-xl cursor-pointer" value="#18181b">
                    
                    <label class="block mb-2 font-semibold text-sm">Gradiente Fim</label>
                    <input type="color" id="editGradientEnd" class="w-full h-12 mb-4 rounded-xl cursor-pointer" value="#000000">
                </div>
            </div>
        </div>
        
        <!-- TAB DOWNLOADS -->
        <div id="tab-downloads" class="tab-content hidden">
            <div class="grid md:grid-cols-2 gap-6">
                <div class="admin-section">
                    <h4 class="text-yellow-400 font-bold mb-4">Modpack 1.8.9</h4>
                    <label class="block mb-2 text-sm">Título</label>
                    <input id="editDownload1Titulo" class="admin-input mb-2" value="Modpack FPS 1.8.9">
                    <label class="block mb-2 text-sm">Descrição</label>
                    <input id="editDownload1Texto" class="admin-input mb-2" value="Otimização máxima para PvP">
                    <label class="block mb-2 text-sm">Ícone (classe FontAwesome)</label>
                    <input id="editDownload1Icon" class="admin-input mb-2" value="fa-cube">
                    <label class="block mb-2 text-sm">Link MediaFire</label>
                    <input id="editLinkMod189" class="admin-input mb-4" placeholder="https://mediafire.com/...">
                    
                    <h4 class="text-yellow-400 font-bold mb-4 mt-6">Modpack 1.20.1</h4>
                    <label class="block mb-2 text-sm">Título</label>
                    <input id="editDownload2Titulo" class="admin-input mb-2" value="Modpack FPS 1.20.1">
                    <label class="block mb-2 text-sm">Descrição</label>
                    <input id="editDownload2Texto" class="admin-input mb-2" value="Performance para versões modernas">
                    <label class="block mb-2 text-sm">Ícone (classe FontAwesome)</label>
                    <input id="editDownload2Icon" class="admin-input mb-2" value="fa-cubes">
                    <label class="block mb-2 text-sm">Link MediaFire</label>
                    <input id="editLinkMod1201" class="admin-input mb-4" placeholder="https://mediafire.com/...">
                </div>
                
                <div class="admin-section">
                    <h4 class="text-yellow-400 font-bold mb-4">Modpack 1.21.8</h4>
                    <label class="block mb-2 text-sm">Título</label>
                    <input id="editDownload3Titulo" class="admin-input mb-2" value="Modpack FPS 1.21.8">
                    <label class="block mb-2 text-sm">Descrição</label>
                    <input id="editDownload3Texto" class="admin-input mb-2" value="Última versão otimizada">
                    <label class="block mb-2 text-sm">Ícone (classe FontAwesome)</label>
                    <input id="editDownload3Icon" class="admin-input mb-2" value="fa-cube">
                    <label class="block mb-2 text-sm">Link MediaFire</label>
                    <input id="editLinkMod1218" class="admin-input mb-4" placeholder="https://mediafire.com/...">
                    
                    <h4 class="text-yellow-400 font-bold mb-4 mt-6">Texture Pack</h4>
                    <label class="block mb-2 text-sm">Título</label>
                    <input id="editDownload4Titulo" class="admin-input mb-2" value="Textura PvP 1.8.9">
                    <label class="block mb-2 text-sm">Descrição</label>
                    <input id="editDownload4Texto" class="admin-input mb-2" value="Pack oficial do clã KOD">
                    <label class="block mb-2 text-sm">Ícone (classe FontAwesome)</label>
                    <input id="editDownload4Icon" class="admin-input mb-2" value="fa-paint-brush">
                    <label class="block mb-2 text-sm">Link MediaFire</label>
                    <input id="editLinkTexture" class="admin-input mb-4" placeholder="https://mediafire.com/...">
                </div>
            </div>
        </div>
        
        <!-- TAB REGRAS -->
        <div id="tab-regras" class="tab-content hidden">
            <div class="grid md:grid-cols-2 gap-6">
                <div>
                    <div class="admin-section">
                        <h4 class="text-yellow-400 font-bold mb-4">Regra 1 - Respeito</h4>
                        <label class="block mb-2 text-sm">Título</label>
                        <input id="editRule1Titulo" class="admin-input mb-2" value="🤝 Respeito">
                        <label class="block mb-2 text-sm">Descrição Curta</label>
                        <input id="editRule1Texto" class="admin-input mb-2" value="Respeite todos os membros. Toxicidade zero.">
                        <label class="block mb-2 text-sm">Descrição Detalhada</label>
                        <textarea id="editRule1Desc" class="admin-input mb-2" rows="3">Seja educado com todos os membros do clã. Não tolere brigas, xingamentos ou qualquer tipo de desrespeito. Mantenha um ambiente saudável e amigável para todos.</textarea>
                        <label class="block mb-2 text-sm">Punição</label>
                        <input id="editRule1Pun" class="admin-input mb-2" value="Banimento de 7 dias no Discord e Kick do clã">
                        <label class="block mb-2 text-sm">Ícone</label>
                        <input id="editRule1Icon" class="admin-input mb-2" value="fa-heart">
                    </div>
                    
                    <div class="admin-section">
                        <h4 class="text-yellow-400 font-bold mb-4">Regra 2 - Sem Cheats</h4>
                        <label class="block mb-2 text-sm">Título</label>
                        <input id="editRule2Titulo" class="admin-input mb-2" value="🚫 Sem Cheats">
                        <label class="block mb-2 text-sm">Descrição Curta</label>
                        <input id="editRule2Texto" class="admin-input mb-2" value="Proibido uso de hacks ou exploits.">
                        <label class="block mb-2 text-sm">Descrição Detalhada</label>
                        <textarea id="editRule2Desc" class="admin-input mb-2" rows="3">É estritamente proibido o uso de qualquer tipo de hack, mod maligno, x-ray, kill aura, ou exploit de bugs. Isso prejudica a experiência de todos e não será tolerado.</textarea>
                        <label class="block mb-2 text-sm">Punição</label>
                        <input id="editRule2Pun" class="admin-input mb-2" value="Banimento permanente do clã e Discord">
                        <label class="block mb-2 text-sm">Ícone</label>
                        <input id="editRule2Icon" class="admin-input mb-2" value="fa-shield-alt">
                    </div>
                    
                    <div class="admin-section">
                        <h4 class="text-yellow-400 font-bold mb-4">Regra 3 - Organização</h4>
                        <label class="block mb-2 text-sm">Título</label>
                        <input id="editRule3Titulo" class="admin-input mb-2" value="📋 Organização">
                        <label class="block mb-2 text-sm">Descrição Curta</label>
                        <input id="editRule3Texto" class="admin-input mb-2" value="Siga as orientações da liderança.">
                        <label class="block mb-2 text-sm">Descrição Detalhada</label>
                        <textarea id="editRule3Desc" class="admin-input mb-2" rows="3">Siga as orientações dos líderes e staff. Mantenha seus itens organizados, participe dos eventos e respeite a hierarquia do clã.</textarea>
                        <label class="block mb-2 text-sm">Punição</label>
                        <input id="editRule3Pun" class="admin-input mb-2" value="Advertência seguida de rebaixamento">
                        <label class="block mb-2 text-sm">Ícone</label>
                        <input id="editRule3Icon" class="admin-input mb-2" value="fa-sitemap">
                    </div>
                </div>
                
                <div>
                    <div class="admin-section">
                        <h4 class="text-yellow-400 font-bold mb-4">Regra 4 - Discord</h4>
                        <label class="block mb-2 text-sm">Título</label>
                        <input id="editRule4Titulo" class="admin-input mb-2" value="💬 Discord">
                        <label class="block mb-2 text-sm">Descrição Curta</label>
                        <input id="editRule4Texto" class="admin-input mb-2" value="Mantenha o Discord organizado e respeitoso.">
                        <label class="block mb-2 text-sm">Descrição Detalhada</label>
                        <textarea id="editRule4Desc" class="admin-input mb-2" rows="3">Use os canais corretos para cada assunto. Não envie spam, não use caps lock excessivamente, não poste conteúdo NSFW. Respeite os canais de voz e não faça flood.</textarea>
                        <label class="block mb-2 text-sm">Punição</label>
                        <input id="editRule4Pun" class="admin-input mb-2" value="Mute de 24h a banimento do Discord">
                        <label class="block mb-2 text-sm">Ícone</label>
                        <input id="editRule4Icon" class="admin-input mb-2" value="fa-discord">
                    </div>
                    
                    <div class="admin-section">
                        <h4 class="text-yellow-400 font-bold mb-4">Regra 5 - Fair Play</h4>
                        <label class="block mb-2 text-sm">Título</label>
                        <input id="editRule5Titulo" class="admin-input mb-2" value="⚔️ Fair Play">
                        <label class="block mb-2 text-sm">Descrição Curta</label>
                        <input id="editRule5Texto" class="admin-input mb-2" value="Jogue limpo e respeite os adversários.">
                        <label class="block mb-2 text-sm">Descrição Detalhada</label>
                        <textarea id="editRule5Desc" class="admin-input mb-2" rows="3">Respeite seus oponentes em batalhas. Não use tactics desleais, não xingue adversários, não atrapalhe eventos do clã. Vitória com honra é a única vitória verdadeira.</textarea>
                        <label class="block mb-2 text-sm">Punição</label>
                        <input id="editRule5Pun" class="admin-input mb-2" value="Suspensão de eventos e treinos">
                        <label class="block mb-2 text-sm">Ícone</label>
                        <input id="editRule5Icon" class="admin-input mb-2" value="fa-trophy">
                    </div>
                    
                    <div class="admin-section">
                        <h4 class="text-yellow-400 font-bold mb-4">Regra 6 - Atividade</h4>
                        <label class="block mb-2 text-sm">Título</label>
                        <input id="editRule6Titulo" class="admin-input mb-2" value="⏰ Atividade">
                        <label class="block mb-2 text-sm">Descrição Curta</label>
                        <input id="editRule6Texto" class="admin-input mb-2" value="Mantenha-se ativo no clã e no Discord.">
                        <label class="block mb-2 text-sm">Descrição Detalhada</label>
                        <textarea id="editRule6Desc" class="admin-input mb-2" rows="3">É necessário manter atividade mínima no servidor e no Discord. Avise quando for ficar ausente por mais de 7 dias. Participe dos eventos e treinos sempre que possível.</textarea>
                        <label class="block mb-2 text-sm">Punição</label>
                        <input id="editRule6Pun" class="admin-input mb-2" value="Remoção do clã por inatividade prolongada">
                        <label class="block mb-2 text-sm">Ícone</label>
                        <input id="editRule6Icon" class="admin-input mb-2" value="fa-clock">
                    </div>
                </div>
            </div>
        </div>
        
        <!-- TAB SERVIDORES -->
        <div id="tab-servidores" class="tab-content hidden">
            <div class="mb-4 flex flex-wrap justify-between items-center gap-4">
                <h4 class="font-bold text-yellow-400 text-xl">Gerenciar Servidores (com ícones e IP)</h4>
                <button onclick="adicionarServidor()" class="bg-green-600 hover:bg-green-500 px-4 py-2 rounded-xl font-bold text-sm flex items-center gap-2">
                    <i class="fas fa-plus"></i> Adicionar Servidor
                </button>
            </div>
            <div id="servidoresAdminContainer" class="space-y-4"></div>
        </div>
        
        <!-- TAB HIERARQUIA -->
        <div id="tab-hierarquia" class="tab-content hidden">
            <div class="mb-4 flex flex-wrap justify-between items-center gap-4">
                <h4 class="font-bold text-yellow-400 text-xl">Gerenciar Membros</h4>
                <button onclick="adicionarMembro()" class="bg-green-600 hover:bg-green-500 px-4 py-2 rounded-xl font-bold text-sm flex items-center gap-2">
                    <i class="fas fa-plus"></i> Adicionar Membro
                </button>
            </div>
            <div id="membrosAdminContainer" class="space-y-4"></div>
        </div>
        
        <!-- TAB AVANÇADO -->
        <div id="tab-avancado" class="tab-content hidden">
            <div class="grid md:grid-cols-2 gap-6">
                <div class="admin-section">
                    <h4 class="text-yellow-400 font-bold mb-4">Configurações Avançadas</h4>
                    
                    <label class="block mb-2 font-semibold text-sm">Fonte Principal</label>
                    <select id="editFont" class="admin-input mb-4">
                        <option value="'Inter', sans-serif">Inter</option>
                        <option value="'Poppins', sans-serif">Poppins</option>
                        <option value="'Montserrat', sans-serif">Montserrat</option>
                        <option value="'Roboto', sans-serif">Roboto</option>
                        <option value="'Open Sans', sans-serif">Open Sans</option>
                    </select>
                    
                    <label class="block mb-2 font-semibold text-sm">Velocidade Animações</label>
                    <select id="editAnimationSpeed" class="admin-input mb-4">
                        <option value="1">Normal</option>
                        <option value="0.7">Rápida</option>
                        <option value="1.5">Lenta</option>
                    </select>
                    
                    <label class="block mb-2 font-semibold text-sm">Opacidade do Header</label>
                    <input type="range" id="editHeaderOpacity" min="0" max="1" step="0.1" class="w-full mb-4" value="0.4">
                    
                    <label class="block mb-2 font-semibold text-sm">Borda Arredondada (px)</label>
                    <input type="number" id="editBorderRadius" class="admin-input mb-4" value="24">
                </div>
                
                <div class="admin-section">
                    <h4 class="text-yellow-400 font-bold mb-4">Efeitos Especiais</h4>
                    
                    <div class="space-y-2">
                        <label class="flex items-center gap-2 cursor-pointer">
                            <input type="checkbox" id="enableGlow" checked class="w-4 h-4"> Habilitar Glow
                        </label>
                        <label class="flex items-center gap-2 cursor-pointer">
                            <input type="checkbox" id="enableFloat" checked class="w-4 h-4"> Habilitar Float
                        </label>
                        <label class="flex items-center gap-2 cursor-pointer">
                            <input type="checkbox" id="enablePulse" checked class="w-4 h-4"> Habilitar Pulse
                        </label>
                    </div>
                    
                    <label class="block mb-2 font-semibold text-sm mt-4">Link do Discord</label>
                    <input id="editDiscordLink" class="admin-input mb-4" value="https://discord.gg/KA54ZfFqdX">
                    
                    <label class="block mb-2 font-semibold text-sm">Texto do Discord</label>
                    <input id="editDiscordText" class="admin-input mb-4" value="discord.gg/KA54ZfFqdX">
                </div>
            </div>
        </div>
        
        <!-- BOTÕES -->
        <div class="flex flex-wrap gap-4 mt-8">
            <button onclick="salvarAlteracoes()" class="bg-green-600 hover:bg-green-500 px-8 py-3 rounded-2xl font-bold flex items-center gap-2 transition">
                <i class="fas fa-save"></i> Salvar Tudo
            </button>
            <button onclick="fecharAdmin()" class="bg-red-600 hover:bg-red-500 px-8 py-3 rounded-2xl font-bold flex items-center gap-2 transition">
                <i class="fas fa-times"></i> Fechar
            </button>
            <button onclick="resetarCores()" class="bg-blue-600 hover:bg-blue-500 px-8 py-3 rounded-2xl font-bold flex items-center gap-2 transition">
                <i class="fas fa-undo"></i> Resetar Cores
            </button>
            <button onclick="exportarConfig()" class="bg-purple-600 hover:bg-purple-500 px-8 py-3 rounded-2xl font-bold flex items-center gap-2 transition">
                <i class="fas fa-download"></i> Exportar Config
            </button>
            <button onclick="importarConfig()" class="bg-indigo-600 hover:bg-indigo-500 px-8 py-3 rounded-2xl font-bold flex items-center gap-2 transition">
                <i class="fas fa-upload"></i> Importar Config
            </button>
        </div>
        
        <p class="text-zinc-500 text-sm mt-6 border-t border-zinc-800 pt-4">
            <i class="fas fa-info-circle mr-2"></i> Acesso restrito - Use <span class="text-yellow-400 font-mono">#KOD.admin</span> na URL
        </p>
    </div>
</div>

<script>
// Variáveis globais
let currentTab = 'textos';
let regrasData = {};

// Dados iniciais das regras
const regrasIniciais = {
    1: { titulo: "🤝 Respeito", descricao: "Seja educado com todos os membros do clã. Não tolere brigas, xingamentos ou qualquer tipo de desrespeito. Mantenha um ambiente saudável e amigável para todos.", punicao: "Banimento de 7 dias no Discord e Kick do clã", icone: "fa-heart", descCurta: "Respeite todos os membros. Toxicidade zero." },
    2: { titulo: "🚫 Sem Cheats", descricao: "É estritamente proibido o uso de qualquer tipo de hack, mod maligno, x-ray, kill aura, ou exploit de bugs. Isso prejudica a experiência de todos e não será tolerado.", punicao: "Banimento permanente do clã e Discord", icone: "fa-shield-alt", descCurta: "Proibido uso de hacks ou exploits." },
    3: { titulo: "📋 Organização", descricao: "Siga as orientações dos líderes e staff. Mantenha seus itens organizados, participe dos eventos e respeite a hierarquia do clã.", punicao: "Advertência seguida de rebaixamento", icone: "fa-sitemap", descCurta: "Siga as orientações da liderança." },
    4: { titulo: "💬 Discord", descricao: "Use os canais corretos para cada assunto. Não envie spam, não use caps lock excessivamente, não poste conteúdo NSFW. Respeite os canais de voz e não faça flood.", punicao: "Mute de 24h a banimento do Discord", icone: "fa-discord", descCurta: "Mantenha o Discord organizado e respeitoso." },
    5: { titulo: "⚔️ Fair Play", descricao: "Respeite seus oponentes em batalhas. Não use tactics desleais, não xingue adversários, não atrapalhe eventos do clã. Vitória com honra é a única vitória verdadeira.", punicao: "Suspensão de eventos e treinos", icone: "fa-trophy", descCurta: "Jogue limpo e respeite os adversários." },
    6: { titulo: "⏰ Atividade", descricao: "É necessário manter atividade mínima no servidor e no Discord. Avise quando for ficar ausente por mais de 7 dias. Participe dos eventos e treinos sempre que possível.", punicao: "Remoção do clã por inatividade prolongada", icone: "fa-clock", descCurta: "Mantenha-se ativo no clã e no Discord." }
};

// Função para mostrar notificação toast
function showToast(message, type = 'success') {
    const toast = document.createElement('div');
    toast.className = `toast-notification ${type === 'error' ? 'bg-red-500' : 'bg-green-500'}`;
    toast.innerHTML = `<i class="fas fa-${type === 'error' ? 'exclamation-circle' : 'check-circle'} mr-2"></i> ${message}`;
    document.body.appendChild(toast);
    
    setTimeout(() => {
        toast.remove();
    }, 3000);
}

// Função para copiar IP
function copiarIP(ip, button) {
    navigator.clipboard.writeText(ip).then(() => {
        button.classList.add('copy-success');
        const originalText = button.innerHTML;
        button.innerHTML = '<i class="fas fa-check mr-2"></i>Copiado!';
        
        showToast('IP copiado para área de transferência!');
        
        setTimeout(() => {
            button.classList.remove('copy-success');
            button.innerHTML = originalText;
        }, 2000);
    }).catch(err => {
        console.error('Erro ao copiar: ', err);
        showToast('Erro ao copiar o IP. Tente novamente.', 'error');
    });
}

// Funções de scroll
function scrollToSection(sectionId) {
    const element = document.getElementById(sectionId);
    if (element) element.scrollIntoView({ behavior: 'smooth' });
}

// Funções do modal
function abrirModal(regraId) {
    const regra = regrasData[regraId];
    if (!regra) return;
    
    document.getElementById('modalIcon').innerHTML = `<i class="fas ${regra.icone}"></i>`;
    document.getElementById('modalTitle').innerText = regra.titulo;
    document.getElementById('modalDescription').innerText = regra.descricao;
    document.getElementById('modalPunishment').innerText = regra.punicao;
    
    document.getElementById('modalOverlay').style.display = 'flex';
    document.body.style.overflow = 'hidden';
}

function fecharModal() {
    document.getElementById('modalOverlay').style.display = 'none';
    document.body.style.overflow = 'auto';
}

// Funções admin
function showTab(tabName) {
    document.querySelectorAll('.tab-content').forEach(tab => tab.classList.add('hidden'));
    document.getElementById(`tab-${tabName}`).classList.remove('hidden');
    
    document.querySelectorAll('.tab-btn').forEach(btn => {
        btn.classList.remove('bg-yellow-500', 'text-black');
        btn.classList.add('bg-zinc-800', 'text-white');
    });
    
    event.target.classList.remove('bg-zinc-800', 'text-white');
    event.target.classList.add('bg-yellow-500', 'text-black');
    
    currentTab = tabName;
    if (tabName === 'servidores') renderServidoresAdmin();
    if (tabName === 'hierarquia') renderMembrosAdmin();
}

function abrirAdmin() {
    document.getElementById('adminPanel').classList.remove('hidden');
    document.body.style.overflow = 'hidden';
    carregarValoresNoPainel();
}

function fecharAdmin() {
    document.getElementById('adminPanel').classList.add('hidden');
    document.body.style.overflow = 'auto';
    window.location.hash = '';
}

function carregarValoresNoPainel() {
    // Logo e textos
    document.getElementById('editLogoUrl').value = document.getElementById('siteLogo')?.src || '';
    document.getElementById('editHeroTitulo').value = document.getElementById('heroTitulo').innerText.replace('Kings Of Dragons', '').trim();
    document.getElementById('editHeroTexto').value = document.getElementById('heroTexto').innerText;
    document.getElementById('editHeroImage').value = document.getElementById('heroImage')?.src.split('/').pop() || 'welcome.png';
    
    // Títulos das seções
    document.getElementById('editRegrasTitulo').value = document.getElementById('regrasTitulo').innerText;
    document.getElementById('editRecrutamentoTitulo').value = document.getElementById('recrutamentoTitulo').innerText;
    document.getElementById('editRecrutamentoTexto').value = document.getElementById('recrutamentoTexto').innerText;
    document.getElementById('editServidoresTitulo').value = document.getElementById('servidoresTitulo').innerText;
    document.getElementById('editHierarquiaTitulo').value = document.getElementById('hierarquiaTitulo').innerText;
    document.getElementById('editDownloadTitulo').value = document.getElementById('downloadTitulo').innerText;
    document.getElementById('editDownloadTexto').value = document.getElementById('downloadTexto').innerText;
    document.getElementById('editFooterTexto').value = document.getElementById('mainFooter').innerText;
    
    // Discord
    document.getElementById('editDiscordLink').value = document.getElementById('discordLink')?.href || 'https://discord.gg/KA54ZfFqdX';
    document.getElementById('editDiscordText').value = document.getElementById('discordText')?.innerText || 'discord.gg/KA54ZfFqdX';
    
    // Downloads
    const downloadCards = document.querySelectorAll('#downloadsContainer .download-card');
    if (downloadCards.length >= 4) {
        document.getElementById('editDownload1Titulo').value = downloadCards[0]?.querySelector('h4')?.innerText || '';
        document.getElementById('editDownload1Texto').value = downloadCards[0]?.querySelector('p')?.innerText || '';
        document.getElementById('editLinkMod189').value = downloadCards[0]?.querySelector('a')?.href || '';
        
        document.getElementById('editDownload2Titulo').value = downloadCards[1]?.querySelector('h4')?.innerText || '';
        document.getElementById('editDownload2Texto').value = downloadCards[1]?.querySelector('p')?.innerText || '';
        document.getElementById('editLinkMod1201').value = downloadCards[1]?.querySelector('a')?.href || '';
        
        document.getElementById('editDownload3Titulo').value = downloadCards[2]?.querySelector('h4')?.innerText || '';
        document.getElementById('editDownload3Texto').value = downloadCards[2]?.querySelector('p')?.innerText || '';
        document.getElementById('editLinkMod1218').value = downloadCards[2]?.querySelector('a')?.href || '';
        
        document.getElementById('editDownload4Titulo').value = downloadCards[3]?.querySelector('h4')?.innerText || '';
        document.getElementById('editDownload4Texto').value = downloadCards[3]?.querySelector('p')?.innerText || '';
        document.getElementById('editLinkTexture').value = downloadCards[3]?.querySelector('a')?.href || '';
    }
    
    // Regras
    for (let i = 1; i <= 6; i++) {
        const rule = regrasData[i] || regrasIniciais[i];
        document.getElementById(`editRule${i}Titulo`).value = rule.titulo;
        document.getElementById(`editRule${i}Texto`).value = rule.descCurta;
        document.getElementById(`editRule${i}Desc`).value = rule.descricao;
        document.getElementById(`editRule${i}Pun`).value = rule.punicao;
        document.getElementById(`editRule${i}Icon`).value = rule.icone;
    }
}

function adicionarServidor() {
    const container = document.getElementById('servidoresAdminContainer');
    const div = document.createElement('div');
    div.className = 'server-admin-item bg-zinc-800 p-4 rounded-xl border border-zinc-700';
    div.innerHTML = `
        <div class="flex gap-4 items-start">
            <div class="flex-1 space-y-2">
                <input type="text" placeholder="Nome do Servidor" class="server-name admin-input" value="Novo Servidor">
                <input type="text" placeholder="URL do Ícone" class="server-icon-url admin-input" value="https://via.placeholder.com/64">
                <input type="text" placeholder="IP do Servidor" class="server-ip admin-input" value="jogar.novoservidor.com">
                <input type="text" placeholder="Versão" class="server-version admin-input" value="1.8.9">
                <input type="text" placeholder="Tipo (PvP/Farm)" class="server-type admin-input" value="PvP">
            </div>
            <button onclick="this.parentElement.parentElement.remove()" class="bg-red-600 hover:bg-red-500 text-white px-3 py-1 rounded-lg text-sm">Remover</button>
        </div>
    `;
    container.appendChild(div);
}

function adicionarMembro() {
    const container = document.getElementById('membrosAdminContainer');
    const div = document.createElement('div');
    div.className = 'membro-admin-item bg-zinc-800 p-4 rounded-xl border border-zinc-700';
    div.innerHTML = `
        <div class="flex gap-4 items-start">
            <div class="flex-1 space-y-2">
                <input type="text" placeholder="Nick" class="membro-nick admin-input" value="Jogador">
                <input type="text" placeholder="Cargo" class="membro-cargo admin-input" value="Membro">
                <input type="text" placeholder="URL da Skin (cabeça)" class="membro-skin admin-input" value="https://mc-heads.net/avatar/steve">
            </div>
            <button onclick="this.parentElement.parentElement.remove()" class="bg-red-600 hover:bg-red-500 text-white px-3 py-1 rounded-lg text-sm">Remover</button>
        </div>
    `;
    container.appendChild(div);
}

function renderizarDownloads(downloads) {
    const container = document.getElementById('downloadsContainer');
    container.innerHTML = '';
    
    const downloadItems = [
        { titulo: downloads.titulo1 || "Modpack FPS 1.8.9", desc: downloads.desc1 || "Otimização máxima para PvP", icon: downloads.icon1 || "fa-cube", link: downloads.link1 || "#" },
        { titulo: downloads.titulo2 || "Modpack FPS 1.20.1", desc: downloads.desc2 || "Performance para versões modernas", icon: downloads.icon2 || "fa-cubes", link: downloads.link2 || "#" },
        { titulo: downloads.titulo3 || "Modpack FPS 1.21.8", desc: downloads.desc3 || "Última versão otimizada", icon: downloads.icon3 || "fa-cube", link: downloads.link3 || "#" },
        { titulo: downloads.titulo4 || "Textura PvP 1.8.9", desc: downloads.desc4 || "Pack oficial do clã KOD", icon: downloads.icon4 || "fa-paint-brush", link: downloads.link4 || "#" }
    ];
    
    downloadItems.forEach((item, index) => {
        const card = document.createElement('div');
        card.className = 'download-card bg-zinc-800/60 p-6 rounded-2xl border border-zinc-700';
        card.innerHTML = `
            <div class="text-5xl mb-4 text-yellow-400"><i class="fas ${item.icon} ${index === 1 ? 'bounce' : index === 2 ? 'float' : index === 3 ? 'pulse' : 'rotate-slow'}"></i></div>
            <h4 class="font-bold text-xl mb-2">${item.titulo}</h4>
            <p class="text-zinc-400 text-sm mb-4">${item.desc}</p>
            <a href="${item.link}" target="_blank" class="btn-download inline-block bg-yellow-500 hover:bg-yellow-400 text-black font-semibold px-6 py-2 rounded-xl transition">
                <i class="fas fa-download mr-2"></i>Baixar
            </a>
        `;
        container.appendChild(card);
    });
}

function renderizarRegras() {
    const container = document.getElementById('regrasContainer');
    container.innerHTML = '';
    
    const icons = ['fa-heart', 'fa-shield-alt', 'fa-sitemap', 'fa-discord', 'fa-trophy', 'fa-clock'];
    
    for (let i = 1; i <= 6; i++) {
        const regra = regrasData[i] || regrasIniciais[i];
        const card = document.createElement('div');
        card.className = 'rule-card bg-zinc-800/60 p-6 rounded-2xl border border-zinc-700';
        card.setAttribute('onclick', `abrirModal(${i})`);
        card.innerHTML = `
            <div class="text-4xl mb-3 text-yellow-400"><i class="fas ${regra.icone}"></i></div>
            <h4 class="font-bold text-xl mb-2 text-yellow-400">${regra.titulo}</h4>
            <p class="text-zinc-400 text-sm">${regra.descCurta}</p>
        `;
        container.appendChild(card);
    }
}

function renderizarServidores(servidoresLista) {
    const grid = document.getElementById('servidoresGrid');
    grid.innerHTML = '';
    
    if (!servidoresLista || servidoresLista.length === 0) {
        servidoresLista = [
            { nome: "PvP Legends", icone: "https://via.placeholder.com/64", ip: "pvp.legends.com", versao: "1.8.9", tipo: "PvP" },
            { nome: "Farm World", icone: "https://via.placeholder.com/64", ip: "farm.world.net", versao: "1.20.1", tipo: "Farm" },
            { nome: "KOD Arena", icone: "https://via.placeholder.com/64", ip: "arena.kod.com", versao: "1.21.8", tipo: "PvP/Farm" }
        ];
    }
    
    servidoresLista.forEach(s => {
        const card = document.createElement('div');
        card.className = 'server-card bg-zinc-800/60 p-6 rounded-2xl border border-zinc-700 text-center';
        card.innerHTML = `
            <img src="${s.icone}" alt="${s.nome}" class="server-icon mx-auto mb-4" onerror="this.src='https://via.placeholder.com/64'">
            <h4 class="font-bold text-xl mb-2">${s.nome}</h4>
            <p class="text-zinc-400 mb-2">Versão: ${s.versao}</p>
            <p class="text-zinc-400 mb-4">Tipo: ${s.tipo}</p>
            <button onclick="copiarIP('${s.ip}', this)" class="copy-ip-btn inline-block bg-yellow-500 hover:bg-yellow-400 text-black font-semibold px-4 py-2 rounded-xl transition">
                <i class="fas fa-copy mr-2"></i>Jogar Agora
            </button>
        `;
        grid.appendChild(card);
    });
}

function renderizarMembros(membrosLista) {
    const grid = document.getElementById('hierarquiaGrid');
    grid.innerHTML = '';
    
    if (!membrosLista || membrosLista.length === 0) {
        membrosLista = [
            { nick: "DragonKing", cargo: "Líder", skin: "https://mc-heads.net/avatar/DragonKing" },
            { nick: "KnightRider", cargo: "Staff", skin: "https://mc-heads.net/avatar/KnightRider" },
            { nick: "FarmMaster", cargo: "Membro", skin: "https://mc-heads.net/avatar/FarmMaster" }
        ];
    }
    
    membrosLista.forEach(m => {
        const card = document.createElement('div');
        card.className = 'member-card bg-zinc-800/60 p-6 rounded-2xl border border-zinc-700 text-center';
        card.innerHTML = `
            <img src="${m.skin}" alt="${m.nick}" class="member-avatar mx-auto mb-4" onerror="this.src='https://mc-heads.net/avatar/steve'">
            <h4 class="font-bold text-xl mb-2">${m.nick}</h4>
            <p class="text-yellow-400 font-semibold">${m.cargo}</p>
        `;
        grid.appendChild(card);
    });
}

function renderServidoresAdmin() {
    const container = document.getElementById('servidoresAdminContainer');
    container.innerHTML = '';
    
    const servidores = JSON.parse(localStorage.getItem('kodServidores') || '[]');
    if (servidores.length === 0) {
        // Adicionar um servidor padrão
        adicionarServidor();
    } else {
        servidores.forEach(s => {
            const div = document.createElement('div');
            div.className = 'server-admin-item bg-zinc-800 p-4 rounded-xl border border-zinc-700';
            div.innerHTML = `
                <div class="flex gap-4 items-start">
                    <div class="flex-1 space-y-2">
                        <input type="text" placeholder="Nome do Servidor" class="server-name admin-input" value="${s.nome || ''}">
                        <input type="text" placeholder="URL do Ícone" class="server-icon-url admin-input" value="${s.icone || ''}">
                        <input type="text" placeholder="IP do Servidor" class="server-ip admin-input" value="${s.ip || ''}">
                        <input type="text" placeholder="Versão" class="server-version admin-input" value="${s.versao || ''}">
                        <input type="text" placeholder="Tipo (PvP/Farm)" class="server-type admin-input" value="${s.tipo || ''}">
                    </div>
                    <button onclick="this.parentElement.parentElement.remove()" class="bg-red-600 hover:bg-red-500 text-white px-3 py-1 rounded-lg text-sm">Remover</button>
                </div>
            `;
            container.appendChild(div);
        });
    }
}

function renderMembrosAdmin() {
    const container = document.getElementById('membrosAdminContainer');
    container.innerHTML = '';
    
    const membros = JSON.parse(localStorage.getItem('kodMembros') || '[]');
    if (membros.length === 0) {
        // Adicionar membros padrão
        adicionarMembro();
        adicionarMembro();
        adicionarMembro();
    } else {
        membros.forEach(m => {
            const div = document.createElement('div');
            div.className = 'membro-admin-item bg-zinc-800 p-4 rounded-xl border border-zinc-700';
            div.innerHTML = `
                <div class="flex gap-4 items-start">
                    <div class="flex-1 space-y-2">
                        <input type="text" placeholder="Nick" class="membro-nick admin-input" value="${m.nick || ''}">
                        <input type="text" placeholder="Cargo" class="membro-cargo admin-input" value="${m.cargo || ''}">
                        <input type="text" placeholder="URL da Skin (cabeça)" class="membro-skin admin-input" value="${m.skin || ''}">
                    </div>
                    <button onclick="this.parentElement.parentElement.remove()" class="bg-red-600 hover:bg-red-500 text-white px-3 py-1 rounded-lg text-sm">Remover</button>
                </div>
            `;
            container.appendChild(div);
        });
    }
}

function salvarAlteracoes() {
    try {
        // Salvar textos
        document.getElementById('siteLogo').src = document.getElementById('editLogoUrl').value;
        
        const heroTitulo = document.getElementById('editHeroTitulo').value;
        document.getElementById('heroTitulo').innerHTML = heroTitulo.replace('KOD', '<span id="heroSpan" class="text-yellow-400">KOD</span>');
        
        document.getElementById('heroTexto').innerText = document.getElementById('editHeroTexto').value;
        document.getElementById('heroImage').src = document.getElementById('editHeroImage').value;
        
        // Títulos das seções
        document.getElementById('regrasTitulo').innerText = document.getElementById('editRegrasTitulo').value;
        document.getElementById('recrutamentoTitulo').innerText = document.getElementById('editRecrutamentoTitulo').value;
        document.getElementById('recrutamentoTexto').innerText = document.getElementById('editRecrutamentoTexto').value;
        document.getElementById('servidoresTitulo').innerText = document.getElementById('editServidoresTitulo').value;
        document.getElementById('hierarquiaTitulo').innerText = document.getElementById('editHierarquiaTitulo').value;
        document.getElementById('downloadTitulo').innerText = document.getElementById('editDownloadTitulo').value;
        document.getElementById('downloadTexto').innerText = document.getElementById('editDownloadTexto').value;
        document.getElementById('mainFooter').innerText = document.getElementById('editFooterTexto').value;
        
        // Discord
        const discordLink = document.getElementById('editDiscordLink').value;
        const discordText = document.getElementById('editDiscordText').value;
        document.getElementById('discordLink').href = discordLink;
        document.getElementById('discordText').innerText = discordText;
        
        // Downloads
        const downloads = {
            titulo1: document.getElementById('editDownload1Titulo').value,
            desc1: document.getElementById('editDownload1Texto').value,
            icon1: document.getElementById('editDownload1Icon').value,
            link1: document.getElementById('editLinkMod189').value,
            titulo2: document.getElementById('editDownload2Titulo').value,
            desc2: document.getElementById('editDownload2Texto').value,
            icon2: document.getElementById('editDownload2Icon').value,
            link2: document.getElementById('editLinkMod1201').value,
            titulo3: document.getElementById('editDownload3Titulo').value,
            desc3: document.getElementById('editDownload3Texto').value,
            icon3: document.getElementById('editDownload3Icon').value,
            link3: document.getElementById('editLinkMod1218').value,
            titulo4: document.getElementById('editDownload4Titulo').value,
            desc4: document.getElementById('editDownload4Texto').value,
            icon4: document.getElementById('editDownload4Icon').value,
            link4: document.getElementById('editLinkTexture').value
        };
        renderizarDownloads(downloads);
        localStorage.setItem('kodDownloads', JSON.stringify(downloads));
        
        // Regras
        for (let i = 1; i <= 6; i++) {
            regrasData[i] = {
                titulo: document.getElementById(`editRule${i}Titulo`).value,
                descCurta: document.getElementById(`editRule${i}Texto`).value,
                descricao: document.getElementById(`editRule${i}Desc`).value,
                punicao: document.getElementById(`editRule${i}Pun`).value,
                icone: document.getElementById(`editRule${i}Icon`).value
            };
        }
        renderizarRegras();
        localStorage.setItem('kodRegras', JSON.stringify(regrasData));
        
        // Servidores
        const servidores = Array.from(document.querySelectorAll('.server-admin-item')).map(item => ({
            nome: item.querySelector('.server-name')?.value || '',
            icone: item.querySelector('.server-icon-url')?.value || 'https://via.placeholder.com/64',
            ip: item.querySelector('.server-ip')?.value || '#',
            versao: item.querySelector('.server-version')?.value || '',
            tipo: item.querySelector('.server-type')?.value || ''
        }));
        renderizarServidores(servidores);
        localStorage.setItem('kodServidores', JSON.stringify(servidores));
        
        // Membros
        const membros = Array.from(document.querySelectorAll('.membro-admin-item')).map(item => ({
            nick: item.querySelector('.membro-nick')?.value || '',
            cargo: item.querySelector('.membro-cargo')?.value || '',
            skin: item.querySelector('.membro-skin')?.value || 'https://mc-heads.net/avatar/steve'
        }));
        renderizarMembros(membros);
        localStorage.setItem('kodMembros', JSON.stringify(membros));
        
        // Cores
        const cores = {
            principal: document.getElementById('editCorPrincipal').value,
            texto: document.getElementById('editCorTexto').value,
            card: document.getElementById('editCorCard').value,
            borda: document.getElementById('editCorBorda').value,
            hover: document.getElementById('editCorHover').value,
            gradStart: document.getElementById('editGradientStart').value,
            gradMid: document.getElementById('editGradientMid').value,
            gradEnd: document.getElementById('editGradientEnd').value
        };
        
        aplicarCores(cores);
        localStorage.setItem('kodCores', JSON.stringify(cores));
        
        // Avançado
        const font = document.getElementById('editFont').value;
        document.body.style.fontFamily = font;
        
        const borderRadius = document.getElementById('editBorderRadius').value;
        document.querySelectorAll('.rounded-3xl, .rounded-2xl, .modal-content').forEach(el => {
            el.style.borderRadius = borderRadius + 'px';
        });
        
        const headerOpacity = document.getElementById('editHeaderOpacity').value;
        document.getElementById('mainHeader').style.backgroundColor = `rgba(0,0,0,${headerOpacity})`;
        
        // Efeitos
        const efeitos = {
            glow: document.getElementById('enableGlow').checked,
            float: document.getElementById('enableFloat').checked,
            pulse: document.getElementById('enablePulse').checked
        };
        localStorage.setItem('kodEfeitos', JSON.stringify(efeitos));
        
        showToast('✅ Todas as alterações foram salvas com sucesso!');
    } catch (error) {
        console.error('Erro ao salvar:', error);
        showToast('❌ Erro ao salvar alterações', 'error');
    }
}

function aplicarCores(cores) {
    let styleTag = document.getElementById('dynamic-styles') || document.createElement('style');
    styleTag.id = 'dynamic-styles';
    styleTag.innerHTML = `
        body { 
            font-family: 'Inter', sans-serif; 
            color: ${cores.texto || '#ffffff'};
        }
        .text-yellow-400, .text-yellow-400 *, #heroSpan { color: ${cores.principal || '#facc15'} !important; }
        .bg-yellow-400, .bg-yellow-500 { background-color: ${cores.principal || '#facc15'} !important; }
        .hover\\:bg-yellow-400:hover { background-color: ${cores.hover || '#eab308'} !important; }
        .bg-zinc-800\\/60, .bg-zinc-800 { background-color: ${cores.card || '#27272a'}; }
        .border-zinc-700, .border-zinc-800 { border-color: ${cores.borda || '#3f3f46'}; }
        body { background: linear-gradient(to bottom right, ${cores.gradStart || '#000000'}, ${cores.gradMid || '#18181b'}, ${cores.gradEnd || '#000000'}); }
        
        nav a::after, h3::after { background: ${cores.principal || '#facc15'}; }
        .modal-content { border-color: ${cores.principal || '#facc15'}; }
        .modal-close { background: ${cores.principal || '#facc15'}; }
        .member-avatar { border-color: ${cores.principal || '#facc15'}; }
        .server-icon { border-color: ${cores.principal || '#facc15'}; }
    `;
    document.head.appendChild(styleTag);
}

function resetarCores() {
    document.getElementById('editCorPrincipal').value = '#facc15';
    document.getElementById('editCorTexto').value = '#ffffff';
    document.getElementById('editCorFundo').value = '#000000';
    document.getElementById('editCorCard').value = '#27272a';
    document.getElementById('editCorBorda').value = '#3f3f46';
    document.getElementById('editCorHover').value = '#eab308';
    document.getElementById('editGradientStart').value = '#000000';
    document.getElementById('editGradientMid').value = '#18181b';
    document.getElementById('editGradientEnd').value = '#000000';
    
    const cores = {
        principal: '#facc15',
        texto: '#ffffff',
        card: '#27272a',
        borda: '#3f3f46',
        hover: '#eab308',
        gradStart: '#000000',
        gradMid: '#18181b',
        gradEnd: '#000000'
    };
    
    aplicarCores(cores);
    localStorage.setItem('kodCores', JSON.stringify(cores));
    showToast('✅ Cores resetadas para o padrão');
}

function exportarConfig() {
    const config = {
        textos: {
            heroTitulo: document.getElementById('editHeroTitulo').value,
            heroTexto: document.getElementById('editHeroTexto').value,
            regrasTitulo: document.getElementById('editRegrasTitulo').value,
            recrutamentoTitulo: document.getElementById('editRecrutamentoTitulo').value,
            recrutamentoTexto: document.getElementById('editRecrutamentoTexto').value,
            servidoresTitulo: document.getElementById('editServidoresTitulo').value,
            hierarquiaTitulo: document.getElementById('editHierarquiaTitulo').value,
            downloadTitulo: document.getElementById('editDownloadTitulo').value,
            downloadTexto: document.getElementById('editDownloadTexto').value,
            footerTexto: document.getElementById('editFooterTexto').value
        },
        cores: {
            principal: document.getElementById('editCorPrincipal').value,
            texto: document.getElementById('editCorTexto').value,
            card: document.getElementById('editCorCard').value,
            borda: document.getElementById('editCorBorda').value,
            hover: document.getElementById('editCorHover').value,
            gradStart: document.getElementById('editGradientStart').value,
            gradMid: document.getElementById('editGradientMid').value,
            gradEnd: document.getElementById('editGradientEnd').value
        },
        downloads: {
            titulo1: document.getElementById('editDownload1Titulo').value,
            desc1: document.getElementById('editDownload1Texto').value,
            icon1: document.getElementById('editDownload1Icon').value,
            link1: document.getElementById('editLinkMod189').value,
            titulo2: document.getElementById('editDownload2Titulo').value,
            desc2: document.getElementById('editDownload2Texto').value,
            icon2: document.getElementById('editDownload2Icon').value,
            link2: document.getElementById('editLinkMod1201').value,
            titulo3: document.getElementById('editDownload3Titulo').value,
            desc3: document.getElementById('editDownload3Texto').value,
            icon3: document.getElementById('editDownload3Icon').value,
            link3: document.getElementById('editLinkMod1218').value,
            titulo4: document.getElementById('editDownload4Titulo').value,
            desc4: document.getElementById('editDownload4Texto').value,
            icon4: document.getElementById('editDownload4Icon').value,
            link4: document.getElementById('editLinkTexture').value
        },
        regras: regrasData,
        servidores: Array.from(document.querySelectorAll('.server-admin-item')).map(item => ({
            nome: item.querySelector('.server-name')?.value || '',
            icone: item.querySelector('.server-icon-url')?.value || '',
            ip: item.querySelector('.server-ip')?.value || '',
            versao: item.querySelector('.server-version')?.value || '',
            tipo: item.querySelector('.server-type')?.value || ''
        })),
        membros: Array.from(document.querySelectorAll('.membro-admin-item')).map(item => ({
            nick: item.querySelector('.membro-nick')?.value || '',
            cargo: item.querySelector('.membro-cargo')?.value || '',
            skin: item.querySelector('.membro-skin')?.value || ''
        }))
    };
    
    const dataStr = JSON.stringify(config, null, 2);
    const dataUri = 'data:application/json;charset=utf-8,'+ encodeURIComponent(dataStr);
    
    const exportFileDefaultName = 'kod-config.json';
    const linkElement = document.createElement('a');
    linkElement.setAttribute('href', dataUri);
    linkElement.setAttribute('download', exportFileDefaultName);
    linkElement.click();
    
    showToast('✅ Configuração exportada com sucesso!');
}

function importarConfig() {
    const input = document.createElement('input');
    input.type = 'file';
    input.accept = '.json';
    
    input.onchange = e => {
        const file = e.target.files[0];
        const reader = new FileReader();
        
        reader.onload = event => {
            try {
                const config = JSON.parse(event.target.result);
                
                // Aplicar configurações
                if (config.textos) {
                    document.getElementById('editHeroTitulo').value = config.textos.heroTitulo || '';
                    document.getElementById('editHeroTexto').value = config.textos.heroTexto || '';
                    document.getElementById('editRegrasTitulo').value = config.textos.regrasTitulo || '';
                    document.getElementById('editRecrutamentoTitulo').value = config.textos.recrutamentoTitulo || '';
                    document.getElementById('editRecrutamentoTexto').value = config.textos.recrutamentoTexto || '';
                    document.getElementById('editServidoresTitulo').value = config.textos.servidoresTitulo || '';
                    document.getElementById('editHierarquiaTitulo').value = config.textos.hierarquiaTitulo || '';
                    document.getElementById('editDownloadTitulo').value = config.textos.downloadTitulo || '';
                    document.getElementById('editDownloadTexto').value = config.textos.downloadTexto || '';
                    document.getElementById('editFooterTexto').value = config.textos.footerTexto || '';
                }
                
                if (config.cores) {
                    document.getElementById('editCorPrincipal').value = config.cores.principal || '#facc15';
                    document.getElementById('editCorTexto').value = config.cores.texto || '#ffffff';
                    document.getElementById('editCorCard').value = config.cores.card || '#27272a';
                    document.getElementById('editCorBorda').value = config.cores.borda || '#3f3f46';
                    document.getElementById('editCorHover').value = config.cores.hover || '#eab308';
                    document.getElementById('editGradientStart').value = config.cores.gradStart || '#000000';
                    document.getElementById('editGradientMid').value = config.cores.gradMid || '#18181b';
                    document.getElementById('editGradientEnd').value = config.cores.gradEnd || '#000000';
                }
                
                if (config.downloads) {
                    document.getElementById('editDownload1Titulo').value = config.downloads.titulo1 || '';
                    document.getElementById('editDownload1Texto').value = config.downloads.desc1 || '';
                    document.getElementById('editDownload1Icon').value = config.downloads.icon1 || 'fa-cube';
                    document.getElementById('editLinkMod189').value = config.downloads.link1 || '';
                    document.getElementById('editDownload2Titulo').value = config.downloads.titulo2 || '';
                    document.getElementById('editDownload2Texto').value = config.downloads.desc2 || '';
                    document.getElementById('editDownload2Icon').value = config.downloads.icon2 || 'fa-cubes';
                    document.getElementById('editLinkMod1201').value = config.downloads.link2 || '';
                    document.getElementById('editDownload3Titulo').value = config.downloads.titulo3 || '';
                    document.getElementById('editDownload3Texto').value = config.downloads.desc3 || '';
                    document.getElementById('editDownload3Icon').value = config.downloads.icon3 || 'fa-cube';
                    document.getElementById('editLinkMod1218').value = config.downloads.link3 || '';
                    document.getElementById('editDownload4Titulo').value = config.downloads.titulo4 || '';
                    document.getElementById('editDownload4Texto').value = config.downloads.desc4 || '';
                    document.getElementById('editDownload4Icon').value = config.downloads.icon4 || 'fa-paint-brush';
                    document.getElementById('editLinkTexture').value = config.downloads.link4 || '';
                }
                
                if (config.regras) {
                    regrasData = config.regras;
                    for (let i = 1; i <= 6; i++) {
                        if (regrasData[i]) {
                            document.getElementById(`editRule${i}Titulo`).value = regrasData[i].titulo || '';
                            document.getElementById(`editRule${i}Texto`).value = regrasData[i].descCurta || '';
                            document.getElementById(`editRule${i}Desc`).value = regrasData[i].descricao || '';
                            document.getElementById(`editRule${i}Pun`).value = regrasData[i].punicao || '';
                            document.getElementById(`editRule${i}Icon`).value = regrasData[i].icone || '';
                        }
                    }
                }
                
                if (config.servidores && config.servidores.length > 0) {
                    const container = document.getElementById('servidoresAdminContainer');
                    container.innerHTML = '';
                    config.servidores.forEach(s => {
                        const div = document.createElement('div');
                        div.className = 'server-admin-item bg-zinc-800 p-4 rounded-xl border border-zinc-700';
                        div.innerHTML = `
                            <div class="flex gap-4 items-start">
                                <div class="flex-1 space-y-2">
                                    <input type="text" placeholder="Nome do Servidor" class="server-name admin-input" value="${s.nome || ''}">
                                    <input type="text" placeholder="URL do Ícone" class="server-icon-url admin-input" value="${s.icone || ''}">
                                    <input type="text" placeholder="IP do Servidor" class="server-ip admin-input" value="${s.ip || ''}">
                                    <input type="text" placeholder="Versão" class="server-version admin-input" value="${s.versao || ''}">
                                    <input type="text" placeholder="Tipo (PvP/Farm)" class="server-type admin-input" value="${s.tipo || ''}">
                                </div>
                                <button onclick="this.parentElement.parentElement.remove()" class="bg-red-600 hover:bg-red-500 text-white px-3 py-1 rounded-lg text-sm">Remover</button>
                            </div>
                        `;
                        container.appendChild(div);
                    });
                }
                
                if (config.membros && config.membros.length > 0) {
                    const container = document.getElementById('membrosAdminContainer');
                    container.innerHTML = '';
                    config.membros.forEach(m => {
                        const div = document.createElement('div');
                        div.className = 'membro-admin-item bg-zinc-800 p-4 rounded-xl border border-zinc-700';
                        div.innerHTML = `
                            <div class="flex gap-4 items-start">
                                <div class="flex-1 space-y-2">
                                    <input type="text" placeholder="Nick" class="membro-nick admin-input" value="${m.nick || ''}">
                                    <input type="text" placeholder="Cargo" class="membro-cargo admin-input" value="${m.cargo || ''}">
                                    <input type="text" placeholder="URL da Skin (cabeça)" class="membro-skin admin-input" value="${m.skin || ''}">
                                </div>
                                <button onclick="this.parentElement.parentElement.remove()" class="bg-red-600 hover:bg-red-500 text-white px-3 py-1 rounded-lg text-sm">Remover</button>
                            </div>
                        `;
                        container.appendChild(div);
                    });
                }
                
                showToast('✅ Configuração importada com sucesso!');
            } catch (error) {
                console.error('Erro ao importar:', error);
                showToast('❌ Erro ao importar configuração', 'error');
            }
        };
        
        reader.readAsText(file);
    };
    
    input.click();
}

function carregarDadosSalvos() {
    // Carregar regras
    const regrasSalvas = localStorage.getItem('kodRegras');
    if (regrasSalvas) {
        regrasData = JSON.parse(regrasSalvas);
    } else {
        regrasData = { ...regrasIniciais };
    }
    renderizarRegras();
    
    // Carregar servidores
    const servidoresSalvos = localStorage.getItem('kodServidores');
    if (servidoresSalvos) {
        renderizarServidores(JSON.parse(servidoresSalvos));
    } else {
        renderizarServidores([]);
    }
    
    // Carregar membros
    const membrosSalvos = localStorage.getItem('kodMembros');
    if (membrosSalvos) {
        renderizarMembros(JSON.parse(membrosSalvos));
    } else {
        renderizarMembros([]);
    }
    
    // Carregar downloads
    const downloadsSalvos = localStorage.getItem('kodDownloads');
    if (downloadsSalvos) {
        renderizarDownloads(JSON.parse(downloadsSalvos));
    } else {
        renderizarDownloads({});
    }
    
    // Carregar cores
    const coresSalvas = localStorage.getItem('kodCores');
    if (coresSalvas) {
        aplicarCores(JSON.parse(coresSalvas));
    }
}

// Event listeners
document.addEventListener('keydown', e => { 
    if (e.key === 'Escape') {
        fecharModal();
        if (!document.getElementById('adminPanel').classList.contains('hidden')) {
            fecharAdmin();
        }
    }
});

window.onload = () => {
    carregarDadosSalvos();
    // Verificar se a URL contém #KOD.admin para abrir o painel
    if (window.location.hash === '#KOD.admin') {
        abrirAdmin();
    }
};

window.addEventListener('hashchange', () => {
    if (window.location.hash === '#KOD.admin') {
        abrirAdmin();
    } else {
        // Se mudar a hash e não for #KOD.admin, fecha o painel se estiver aberto
        if (!document.getElementById('adminPanel').classList.contains('hidden')) {
            fecharAdmin();
        }
    }
});

// Fechar modal ao clicar fora
document.getElementById('modalOverlay').addEventListener('click', fecharModal);
</script>

</body>
</html>
