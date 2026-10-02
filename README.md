<!DOCTYPE html>
<html lang="hi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Arti Mandal | Portfolio</title>
    
    <!-- Fonts & Icons -->
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700&family=Playfair+Display:ital,wght@0,600;1,400&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">

    <style>
        :root {
            --bg-base: #0f0a1c;
            --plum-deep: #1d1235;
            --rose-accent: #e5989b;
            --rose-gold: #b5838d;
            --champagne: #ffcdb2;
            --violet-glow: #6d597a;
            --text-main: #f7ede2;
            --text-muted: #b8a9c9;
            --glass-surface: rgba(255, 255, 255, 0.05);
            --glass-border: rgba(229, 152, 155, 0.2);
            --glass-hover: rgba(229, 152, 155, 0.12);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Plus Jakarta Sans', sans-serif;
            background-color: var(--bg-base);
            color: var(--text-main);
            min-height: 100vh;
            overflow-x: hidden;
            position: relative;
        }

        /* Ambient Glowing Background Orbs */
        .ambient-glow {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 0;
            overflow: hidden;
        }

        .glow-orb {
            position: absolute;
            border-radius: 50%;
            filter: blur(100px);
            opacity: 0.35;
            animation: pulseOrb 12s infinite alternate ease-in-out;
        }

        .orb-1 {
            width: 450px;
            height: 450px;
            background: radial-gradient(circle, #b5838d, transparent 70%);
            top: -100px;
            left: -100px;
        }

        .orb-2 {
            width: 500px;
            height: 500px;
            background: radial-gradient(circle, #6d597a, transparent 70%);
            bottom: 10%;
            right: -120px;
            animation-duration: 16s;
        }

        .orb-3 {
            width: 350px;
            height: 350px;
            background: radial-gradient(circle, #e5989b, transparent 70%);
            top: 50%;
            left: 40%;
            opacity: 0.2;
        }

        @keyframes pulseOrb {
            0% { transform: scale(1) translate(0, 0); }
            100% { transform: scale(1.15) translate(30px, 40px); }
        }

        /* Floating Sparkles */
        .sparkle-field {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        .sparkle {
            position: absolute;
            border-radius: 50%;
            background: var(--champagne);
            box-shadow: 0 0 10px var(--rose-accent);
            animation: rise 9s infinite linear;
        }

        @keyframes rise {
            0% { transform: translateY(105vh) scale(0.4); opacity: 0; }
            40% { opacity: 0.8; }
            80% { opacity: 0.6; }
            100% { transform: translateY(-10vh) scale(1); opacity: 0; }
        }

        /* Navigation */
        nav {
            position: sticky;
            top: 0;
            width: 100%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1.2rem 8%;
            background: rgba(15, 10, 28, 0.7);
            backdrop-filter: blur(15px);
            border-bottom: 1px solid var(--glass-border);
            z-index: 100;
        }

        .logo {
            font-family: 'Playfair Display', serif;
            font-size: 1.7rem;
            font-weight: 600;
            letter-spacing: 1px;
            background: linear-gradient(120deg, #ffcdb2, #e5989b);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--text-muted);
            font-size: 0.95rem;
            font-weight: 500;
            transition: color 0.3s ease, transform 0.3s ease;
        }

        .nav-links a:hover {
            color: var(--champagne);
            transform: translateY(-2px);
        }

        main {
            position: relative;
            z-index: 2;
        }

        section {
            padding: 5rem 10%;
        }

        .reveal {
            opacity: 0;
            transform: translateY(40px);
            transition: all 0.85s cubic-bezier(0.16, 1, 0.3, 1);
        }

        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* Hero */
        .hero {
            min-height: 85vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 2rem 1rem;
        }

        .tagline {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            font-size: 0.85rem;
            text-transform: uppercase;
            letter-spacing: 2px;
            color: var(--champagne);
            background: rgba(229, 152, 155, 0.12);
            padding: 6px 18px;
            border-radius: 40px;
            border: 1px solid var(--glass-border);
            margin-bottom: 1.5rem;
        }

        .hero h1 {
            font-family: 'Playfair Display', serif;
            font-size: 4rem;
            font-weight: 600;
            margin-bottom: 1rem;
            background: linear-gradient(135deg, #ffffff 30%, #e5989b 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .hero p {
            max-width: 620px;
            font-size: 1.15rem;
            color: var(--text-muted);
            line-height: 1.7;
            margin-bottom: 2.5rem;
        }

        .social-bar {
            display: flex;
            gap: 1.2rem;
            flex-wrap: wrap;
            justify-content: center;
        }

        .social-link {
            width: 48px;
            height: 48px;
            border-radius: 50%;
            background: var(--glass-surface);
            border: 1px solid var(--glass-border);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--champagne);
            text-decoration: none;
            font-size: 1.2rem;
            transition: all 0.35s ease;
        }

        .social-link:hover {
            transform: translateY(-5px) scale(1.1);
            background: var(--rose-accent);
            color: var(--bg-base);
            box-shadow: 0 8px 25px rgba(229, 152, 155, 0.4);
            border-color: var(--rose-accent);
        }

        .section-header {
            text-align: center;
            margin-bottom: 3.5rem;
        }

        .section-header h2 {
            font-family: 'Playfair Display', serif;
            font-size: 2.5rem;
            font-weight: 600;
            color: #ffffff;
            margin-bottom: 0.5rem;
        }

        .section-header p {
            color: var(--text-muted);
            font-size: 0.95rem;
        }

        /* Skills */
        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 1.6rem;
            max-width: 900px;
            margin: 0 auto;
        }

        .skill-box {
            background: var(--glass-surface);
            border: 1px solid var(--glass-border);
            border-radius: 20px;
            padding: 2rem 1rem;
            text-align: center;
            transition: all 0.35s ease;
            backdrop-filter: blur(10px);
        }

        .skill-box:hover {
            background: var(--glass-hover);
            transform: translateY(-8px);
            border-color: var(--rose-accent);
            box-shadow: 0 12px 30px rgba(181, 131, 141, 0.2);
        }

        .skill-box i {
            font-size: 2.4rem;
            margin-bottom: 1rem;
            color: var(--rose-accent);
        }

        .skill-box h4 {
            font-size: 1rem;
            font-weight: 600;
            color: var(--text-main);
        }

        /* Projects */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 2.2rem;
        }

        .project-card {
            background: var(--glass-surface);
            border: 1px solid var(--glass-border);
            border-radius: 24px;
            overflow: hidden;
            backdrop-filter: blur(10px);
            display: flex;
            flex-direction: column;
            transition: all 0.4s ease;
        }

        .project-card:hover {
            transform: translateY(-10px);
            border-color: var(--rose-accent);
            box-shadow: 0 15px 35px rgba(229, 152, 155, 0.18);
        }

        .project-thumb {
            height: 180px;
            background: linear-gradient(135deg, rgba(109, 89, 122, 0.6), rgba(181, 131, 141, 0.3));
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3.5rem;
            color: var(--champagne);
            border-bottom: 1px solid var(--glass-border);
        }

        .project-details {
            padding: 1.8rem;
            display: flex;
            flex-direction: column;
            flex-grow: 1;
        }

        .project-details h3 {
            font-family: 'Playfair Display', serif;
            font-size: 1.35rem;
            margin-bottom: 0.7rem;
            color: var(--champagne);
        }

        .project-details p {
            font-size: 0.92rem;
            line-height: 1.6;
            color: var(--text-muted);
            margin-bottom: 1.8rem;
            flex-grow: 1;
        }

        .project-actions {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
        }

        .project-btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 6px;
            padding: 10px 18px;
            background: transparent;
            color: var(--text-main);
            border: 1px solid var(--rose-accent);
            border-radius: 30px;
            text-decoration: none;
            font-size: 0.85rem;
            font-weight: 500;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .project-btn.primary {
            background: var(--rose-accent);
            color: var(--bg-base);
        }

        .project-btn:hover {
            background: var(--rose-accent);
            color: var(--bg-base);
            box-shadow: 0 6px 20px rgba(229, 152, 155, 0.3);
        }

        /* ENHANCED ATM MODAL */
        .atm-modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(10, 6, 20, 0.88);
            backdrop-filter: blur(12px);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 1000;
            opacity: 0;
            pointer-events: none;
            transition: opacity 0.3s ease;
        }

        .atm-modal-overlay.active {
            opacity: 1;
            pointer-events: auto;
        }

        .atm-terminal {
            background: #171026;
            border: 1px solid var(--rose-accent);
            width: 92%;
            max-width: 480px;
            border-radius: 24px;
            padding: 2rem;
            box-shadow: 0 25px 60px rgba(0,0,0,0.7);
        }

        .atm-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1.2rem;
            border-bottom: 1px solid var(--glass-border);
            padding-bottom: 0.8rem;
        }

        .atm-header h3 {
            font-family: 'Playfair Display', serif;
            color: var(--champagne);
            font-size: 1.2rem;
        }

        .close-atm {
            background: none;
            border: none;
            color: var(--text-muted);
            font-size: 1.2rem;
            cursor: pointer;
            transition: color 0.2s;
        }

        .close-atm:hover {
            color: var(--rose-accent);
        }

        .atm-screen {
            background: #0b0714;
            border: 1px solid var(--glass-border);
            border-radius: 14px;
            padding: 1.2rem;
            min-height: 180px;
            max-height: 240px;
            overflow-y: auto;
            margin-bottom: 1.2rem;
            display: flex;
            flex-direction: column;
            justify-content: center;
            text-align: center;
        }

        .atm-screen::-webkit-scrollbar {
            width: 5px;
        }
        .atm-screen::-webkit-scrollbar-thumb {
            background: var(--glass-border);
            border-radius: 10px;
        }

        .atm-screen p {
            color: var(--text-muted);
            font-size: 0.9rem;
            margin-bottom: 0.8rem;
        }

        .atm-screen input {
            background: var(--glass-surface);
            border: 1px solid var(--rose-accent);
            color: white;
            padding: 10px 15px;
            border-radius: 8px;
            text-align: center;
            font-size: 1.1rem;
            outline: none;
            width: 85%;
            margin: 0 auto;
        }

        .statement-list {
            text-align: left;
            width: 100%;
            font-size: 0.85rem;
        }

        .statement-item {
            display: flex;
            justify-content: space-between;
            padding: 6px 0;
            border-bottom: 1px dashed rgba(255,255,255,0.1);
        }

        .atm-controls {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 10px;
        }

        .atm-btn {
            background: var(--glass-surface);
            border: 1px solid var(--glass-border);
            color: var(--text-main);
            padding: 10px;
            border-radius: 10px;
            cursor: pointer;
            font-weight: 500;
            font-size: 0.85rem;
            transition: all 0.2s;
        }

        .atm-btn:hover {
            background: var(--rose-accent);
            color: var(--bg-base);
            border-color: var(--rose-accent);
        }

        .atm-btn.full {
            grid-column: span 2;
            background: rgba(229, 152, 155, 0.15);
        }

        /* Footer */
        footer {
            text-align: center;
            padding: 3rem 1rem;
            border-top: 1px solid var(--glass-border);
            color: var(--text-muted);
            font-size: 0.85rem;
            background: rgba(15, 10, 28, 0.5);
            backdrop-filter: blur(10px);
        }

        footer span {
            color: var(--rose-accent);
        }

        @media (max-width: 768px) {
            .hero h1 { font-size: 2.8rem; }
            .nav-links { display: none; }
            section { padding: 4rem 6%; }
        }
    </style>
</head>
<body>

    <!-- Soft Ambient Lights -->
    <div class="ambient-glow">
        <div class="glow-orb orb-1"></div>
        <div class="glow-orb orb-2"></div>
        <div class="glow-orb orb-3"></div>
    </div>

    <!-- Floating Elegant Sparkles -->
    <div class="sparkle-field" id="sparkleField"></div>

    <!-- Header -->
    <nav>
        <div class="logo">Arti Mandal</div>
        <ul class="nav-links">
            <li><a href="#about">About</a></li>
            <li><a href="#skills">Skills</a></li>
            <li><a href="#projects">Projects</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>

    <main>
        <!-- Hero Section -->
        <section class="hero reveal" id="about">
            <span class="tagline"><i class="fa-regular fa-gem"></i> Developer & Designer</span>
            <h1>Arti Mandal</h1>
            <p>Crafting robust backends and polished digital experiences with elegant logic, seamless design, and modern code.</p>
            
            <div class="social-bar" id="contact">
                <a href="https://wa.me/9001725419" target="_blank" class="social-link" title="WhatsApp"><i class="fa-brands fa-whatsapp"></i></a>
                <a href="https://www.instagram.com/aar_ti94?stkn=MXAyem53YnJzeG8ybg==" target="_blank" class="social-link" title="Instagram"><i class="fa-brands fa-instagram"></i></a>
                <a href="https://www.linkedin.com/in/arti-mandal-a03195311/" target="_blank" class="social-link" title="LinkedIn"><i class="fa-brands fa-linkedin-in"></i></a>
                <a href="https://github.com/aarti896" target="_blank" class="social-link" title="GitHub"><i class="fa-brands fa-github"></i></a>
                <a href="mailto:aartimandal089@gmail.com" class="social-link" title="Email"><i class="fa-regular fa-envelope"></i></a>
            </div>
        </section>

        <!-- Skills Section -->
        <section id="skills">
            <div class="section-header reveal">
                <h2>Technical Toolkit</h2>
                <p>Core technologies I work with</p>
            </div>
            
            <div class="skills-container">
                <div class="skill-box reveal"><i class="fa-brands fa-html5"></i><h4>HTML5</h4></div>
                <div class="skill-box reveal"><i class="fa-brands fa-css3-alt"></i><h4>CSS3</h4></div>
                <div class="skill-box reveal"><i class="fa-brands fa-js"></i><h4>JavaScript</h4></div>
                <div class="skill-box reveal"><i class="fa-brands fa-java"></i><h4>Java</h4></div>
                <div class="skill-box reveal"><i class="fa-solid fa-database"></i><h4>MySQL</h4></div>
                <div class="skill-box reveal"><i class="fa-solid fa-basket-shopping"></i><h4>E-Commerce</h4></div>
            </div>
        </section>

        <!-- Projects Section -->
        <section id="projects">
            <div class="section-header reveal">
                <h2>Featured Projects</h2>
                <p>Curated work and development cases</p>
            </div>

            <div class="projects-grid">
                
                <!-- ATM Management System with Enhanced Simulator -->
                <div class="project-card reveal">
                    <div class="project-thumb">
                        <i class="fa-solid fa-building-columns"></i>
                    </div>
                    <div class="project-details">
                        <h3>ATM Management System</h3>
                        <p>Advanced Java banking console with PIN authentication, balance checking, quick cash withdrawal, mini statements, and PIN changing features.</p>
                        <div class="project-actions">
                            <button class="project-btn primary" onclick="openAtmModal()">
                                Try Live ATM <i class="fa-solid fa-play"></i>
                            </button>
                            <a href="https://github.com/aarti896" target="_blank" class="project-btn">
                                GitHub <i class="fa-solid fa-arrow-up-right-from-square"></i>
                            </a>
                        </div>
                    </div>
                </div>

                <!-- Project Card 2 -->
                <div class="project-card reveal">
                    <div class="project-thumb">
                        <i class="fa-solid fa-laptop-code"></i>
                    </div>
                    <div class="project-details">
                        <h3>Interactive Web App</h3>
                        <p>A responsive and modern web application engineered using modern JavaScript, custom styling, and smooth user interactions.</p>
                        <div class="project-actions">
                            <a href="https://github.com/aarti896" target="_blank" class="project-btn">
                                Explore <i class="fa-solid fa-arrow-up-right-from-square"></i>
                            </a>
                        </div>
                    </div>
                </div>

                <!-- Project Card 3 -->
                <div class="project-card reveal">
                    <div class="project-thumb">
                        <i class="fa-solid fa-server"></i>
                    </div>
                    <div class="project-details">
                        <h3>Database Management</h3>
                        <p>Custom relational database models powered by MySQL and Java, designed for high reliability, security, and structured queries.</p>
                        <div class="project-actions">
                            <a href="https://github.com/aarti896" target="_blank" class="project-btn">
                                Explore <i class="fa-solid fa-arrow-up-right-from-square"></i>
                            </a>
                        </div>
                    </div>
                </div>

            </div>
        </section>
    </main>

    <!-- FULL-FEATURED ATM SIMULATOR MODAL -->
    <div class="atm-modal-overlay" id="atmModal">
        <div class="atm-terminal">
            <div class="atm-header">
                <h3><i class="fa-solid fa-building-columns"></i> Advanced ATM System</h3>
                <button class="close-atm" onclick="closeAtmModal()"><i class="fa-solid fa-xmark"></i></button>
            </div>
            
            <div class="atm-screen" id="atmScreen"></div>
            <div class="atm-controls" id="atmControls"></div>
        </div>
    </div>

    <!-- Footer -->
    <footer>
        <p>Curated by <span>Aarti Mandal</span> &bull; 2026</p>
    </footer>

    <!-- Interactive Scripts -->
    <script>
        // Scroll Animation Observer
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('active');
                }
            });
        }, { threshold: 0.15 });

        document.querySelectorAll('.reveal').forEach((el) => observer.observe(el));

        // Background Sparkles Generator
        const field = document.getElementById('sparkleField');
        for (let i = 0; i < 25; i++) {
            const dot = document.createElement('div');
            dot.classList.add('sparkle');
            const size = Math.random() * 4 + 2;
            dot.style.width = `${size}px`;
            dot.style.height = `${size}px`;
            dot.style.left = `${Math.random() * 100}%`;
            dot.style.animationDuration = `${Math.random() * 6 + 6}s`;
            dot.style.animationDelay = `${Math.random() * 5}s`;
            field.appendChild(dot);
        }

        // --- ENHANCED ATM LOGIC ---
        let atmState = {
            step: 'pin',
            balance: 10000,
            correctPin: '1234',
            inputVal: '',
            newPinInput: '',
            transactions: [
                { type: 'Initial Deposit', amount: 10000, date: '02 Oct 2026' }
            ]
        };

        const atmModal = document.getElementById('atmModal');
        const atmScreen = document.getElementById('atmScreen');
        const atmControls = document.getElementById('atmControls');

        function openAtmModal() {
            atmModal.classList.add('active');
            resetAtm();
        }

        function closeAtmModal() {
            atmModal.classList.remove('active');
        }

        function resetAtm() {
            atmState.step = 'pin';
            atmState.inputVal = '';
            atmState.newPinInput = '';
            renderAtm();
        }

        function renderAtm() {
            if (atmState.step === 'pin') {
                atmScreen.innerHTML = `
                    <p>Welcome! Please enter your 4-digit PIN.<br><small style="color:var(--rose-accent)">(Default PIN: 1234)</small></p>
                    <input type="password" id="atmInput" maxlength="4" placeholder="••••" value="${atmState.inputVal}">
                `;
                atmControls.innerHTML = `
                    <button class="atm-btn full" onclick="handlePinSubmit()">Enter PIN</button>
                `;
            } else if (atmState.step === 'menu') {
                atmScreen.innerHTML = `
                    <p style="color:var(--champagne); font-weight:600; font-size:1rem;">Main Menu</p>
                    <p>Select your banking transaction:</p>
                `;
                atmControls.innerHTML = `
                    <button class="atm-btn" onclick="atmState.step='balance'; renderAtm();">Check Balance</button>
                    <button class="atm-btn" onclick="atmState.step='deposit'; atmState.inputVal=''; renderAtm();">Deposit Cash</button>
                    <button class="atm-btn" onclick="atmState.step='withdraw_choice'; renderAtm();">Withdraw Cash</button>
                    <button class="atm-btn" onclick="atmState.step='statement'; renderAtm();">Mini Statement</button>
                    <button class="atm-btn" onclick="atmState.step='pin_change'; atmState.inputVal=''; atmState.newPinInput=''; renderAtm();">Change PIN</button>
                    <button class="atm-btn" onclick="resetAtm()">Logout</button>
                `;
            } else if (atmState.step === 'balance') {
                atmScreen.innerHTML = `
                    <p>Account Holder: <strong>Arti Mandal</strong></p>
                    <p>Total Available Balance:</p>
                    <h2 style="color:var(--champagne); font-size:1.9rem; margin:8px 0;">₹${atmState.balance.toLocaleString()}</h2>
                `;
                atmControls.innerHTML = `
                    <button class="atm-btn full" onclick="atmState.step='menu'; renderAtm();">Back to Menu</button>
                `;
            } else if (atmState.step === 'deposit') {
                atmScreen.innerHTML = `
                    <p>Enter amount to deposit:</p>
                    <input type="number" id="atmInput" placeholder="₹ Amount" value="${atmState.inputVal}">
                `;
                atmControls.innerHTML = `
                    <button class="atm-btn" onclick="processDeposit()">Confirm</button>
                    <button class="atm-btn" onclick="atmState.step='menu'; renderAtm();">Cancel</button>
                `;
            } else if (atmState.step === 'withdraw_choice') {
                atmScreen.innerHTML = `
                    <p>Select Withdrawal Method:</p>
                `;
                atmControls.innerHTML = `
                    <button class="atm-btn" onclick="atmState.step='fast_cash'; renderAtm();">Fast Cash</button>
                    <button class="atm-btn" onclick="atmState.step='custom_withdraw'; atmState.inputVal=''; renderAtm();">Enter Amount</button>
                    <button class="atm-btn full" onclick="atmState.step='menu'; renderAtm();">Back to Menu</button>
                `;
            } else if (atmState.step === 'fast_cash') {
                atmScreen.innerHTML = `
                    <p>Select Fast Cash Amount:</p>
                `;
                atmControls.innerHTML = `
                    <button class="atm-btn" onclick="processWithdraw(500)">₹500</button>
                    <button class="atm-btn" onclick="processWithdraw(1000)">₹1,000</button>
                    <button class="atm-btn" onclick="processWithdraw(5000)">₹5,000</button>
                    <button class="atm-btn" onclick="processWithdraw(10000)">₹10,000</button>
                    <button class="atm-btn full" onclick="atmState.step='withdraw_choice'; renderAtm();">Back</button>
                `;
            } else if (atmState.step === 'custom_withdraw') {
                atmScreen.innerHTML = `
                    <p>Enter custom amount to withdraw:</p>
                    <input type="number" id="atmInput" placeholder="₹ Amount" value="${atmState.inputVal}">
                `;
                atmControls.innerHTML = `
                    <button class="atm-btn" onclick="processCustomWithdraw()">Confirm</button>
                    <button class="atm-btn" onclick="atmState.step='withdraw_choice'; renderAtm();">Back</button>
                `;
            } else if (atmState.step === 'statement') {
                let listHtml = atmState.transactions.slice(-4).reverse().map(t => `
                    <div class="statement-item">
                        <span>${t.type} (${t.date})</span>
                        <span style="color:${t.type.includes('Deposit') || t.type.includes('Initial') ? '#a3d9a5' : '#e5989b'}">
                            ${t.type.includes('Deposit') || t.type.includes('Initial') ? '+' : '-'}₹${t.amount}
                        </span>
                    </div>
                `).join('');

                atmScreen.innerHTML = `
                    <p style="margin-bottom:5px; color:var(--champagne);"><strong>Mini Statement (Last Transactions)</strong></p>
                    <div class="statement-list">${listHtml || '<p>No transactions yet.</p>'}</div>
                `;
                atmControls.innerHTML = `
                    <button class="atm-btn full" onclick="atmState.step='menu'; renderAtm();">Back to Menu</button>
                `;
            } else if (atmState.step === 'pin_change') {
                atmScreen.innerHTML = `
                    <p>Enter New 4-Digit PIN:</p>
                    <input type="password" id="atmNewPin" maxlength="4" placeholder="••••">
                `;
                atmControls.innerHTML = `
                    <button class="atm-btn full" onclick="processPinChange()">Update PIN</button>
                    <button class="atm-btn full" onclick="atmState.step='menu'; renderAtm();" style="background:transparent; margin-top:5px;">Cancel</button>
                `;
            }
        }

        function handlePinSubmit() {
            const input = document.getElementById('atmInput').value;
            if (input === atmState.correctPin) {
                atmState.step = 'menu';
                renderAtm();
            } else {
                alert('Incorrect PIN! Try 1234');
            }
        }

        function processDeposit() {
            const val = parseFloat(document.getElementById('atmInput').value);
            if (val > 0) {
                atmState.balance += val;
                atmState.transactions.push({ type: 'Deposit', amount: val, date: '02 Oct 2026' });
                alert(`Successfully deposited ₹${val}!`);
                atmState.step = 'menu';
                renderAtm();
            } else {
                alert('Please enter a valid amount.');
            }
        }

        function processWithdraw(amount) {
            if (amount <= atmState.balance) {
                atmState.balance -= amount;
                atmState.transactions.push({ type: 'Withdrawal', amount: amount, date: '02 Oct 2026' });
                alert(`Successfully withdrawn ₹${amount}!`);
                atmState.step = 'menu';
                renderAtm();
            } else {
                alert('Insufficient Balance!');
            }
        }

        function processCustomWithdraw() {
            const val = parseFloat(document.getElementById('atmInput').value);
            if (val > 0 && val <= atmState.balance) {
                processWithdraw(val);
            } else {
                alert('Invalid amount or insufficient balance.');
            }
        }

        function processPinChange() {
            const newPin = document.getElementById('atmNewPin').value;
            if (newPin.length === 4 && !isNaN(newPin)) {
                atmState.correctPin = newPin;
                alert('PIN successfully updated!');
                atmState.step = 'menu';
                renderAtm();
            } else {
                alert('Please enter a valid 4-digit numeric PIN.');
            }
        }
    </script>
</body>
</html>
