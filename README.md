<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Share your feedback with us – secure, fast, and easy.">
    <title>FormCraft • Your Voice Matters</title>

    <!-- Fonts & Icons -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,400;14..32,500;14..32,600;14..32,700;14..32,800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <style>
        :root {
            --primary: #4f46e5;
            --primary-dark: #4338ca;
            --primary-light: #818cf8;
            --primary-bg: #eef2ff;
            --accent: #f59e0b;
            --text-dark: #1e293b;
            --text-medium: #475569;
            --white: #ffffff;
            --bg: #f8fafc;
            --card-bg: #ffffff;
            --border: #e2e8f0;
            --shadow-lg: 0 20px 50px -12px rgba(0,0,0,0.12);
            --radius-lg: 24px;
            --transition: 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }

        * { box-sizing: border-box; margin: 0; padding: 0; }
        html { scroll-behavior: smooth; }
        body {
            font-family: 'Inter', sans-serif;
            background: var(--bg);
            background-image: radial-gradient(circle, #e2e8f0 1px, transparent 1px);
            background-size: 28px 28px;
            color: var(--text-dark);
            line-height: 1.6;
            -webkit-font-smoothing: antialiased;
        }

        /* Navigation */
        .navbar {
            position: sticky; top: 0; z-index: 100;
            background: rgba(255,255,255,0.85); backdrop-filter: blur(18px);
            border-bottom: 1px solid var(--border);
        }
        .navbar-inner {
            max-width: 1100px; margin: 0 auto;
            display: flex; align-items: center; justify-content: space-between;
            height: 64px; padding: 0 1.5rem;
        }
        .nav-logo {
            display: flex; align-items: center; gap: 10px;
            font-weight: 700; font-size: 1.25rem; color: var(--primary);
            text-decoration: none; letter-spacing: -0.3px;
        }
        .nav-logo .logo-icon {
            width: 38px; height: 38px;
            background: linear-gradient(135deg, var(--primary), var(--primary-light));
            border-radius: 10px; display: flex; align-items: center; justify-content: center;
            color: white; font-size: 1rem; box-shadow: 0 4px 12px rgba(79,70,229,0.3);
        }
        .nav-links {
            display: flex; list-style: none; gap: 2rem; align-items: center;
        }
        .nav-links a {
            text-decoration: none; color: var(--text-medium); font-weight: 500;
            font-size: 0.95rem; transition: color var(--transition);
            position: relative;
        }
        .nav-links a:hover { color: var(--primary); }
        .nav-links a::after {
            content: ''; position: absolute; bottom: -4px; left: 0;
            width: 0; height: 2px; background: var(--primary);
            transition: width var(--transition); border-radius: 1px;
        }
        .nav-links a:hover::after { width: 100%; }
        .btn-nav {
            background: var(--primary); color: white !important;
            padding: 0.55rem 1.4rem; border-radius: 50px; font-weight: 600;
            font-size: 0.9rem; box-shadow: 0 4px 14px rgba(79,70,229,0.3);
            transition: all var(--transition);
        }
        .btn-nav:hover { background: var(--primary-dark); transform: translateY(-1px); box-shadow: 0 6px 20px rgba(79,70,229,0.4); }
        .btn-nav::after { display: none !important; }
        .nav-toggle {
            display: none; background: none; border: none;
            font-size: 1.5rem; cursor: pointer; color: var(--text-dark);
        }

        /* Hero */
        .hero {
            padding: 4rem 1.5rem 3rem; max-width: 700px; margin: 0 auto; text-align: center;
        }
        .hero-badge {
            display: inline-block; background: var(--primary-bg);
            color: var(--primary); font-weight: 600; font-size: 0.85rem;
            padding: 0.4rem 1.2rem; border-radius: 50px; margin-bottom: 1.5rem;
            letter-spacing: 0.3px;
        }
        .hero h1 {
            font-size: clamp(2rem, 5vw, 2.8rem); font-weight: 800;
            letter-spacing: -0.6px; line-height: 1.15; margin-bottom: 1rem;
        }
        .hero h1 .highlight {
            background: linear-gradient(135deg, var(--primary), #7c3aed);
            -webkit-background-clip: text; -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        .hero p {
            color: var(--text-medium); font-size: 1.1rem;
            max-width: 520px; margin: 0 auto 1.5rem;
        }
        .typewriter {
            display: inline-block; border-right: 3px solid var(--primary);
            padding-right: 5px; animation: blink 0.8s infinite;
            font-weight: 600; color: var(--primary-dark);
        }
        @keyframes blink { 50% { border-color: transparent; } }

        /* Buttons */
        .btn {
            display: inline-flex; align-items: center; gap: 8px;
            padding: 0.8rem 2rem; border-radius: 50px; font-weight: 600;
            font-size: 1rem; text-decoration: none; transition: all var(--transition);
            border: none; cursor: pointer;
        }
        .btn-primary {
            background: var(--primary); color: white;
            box-shadow: 0 8px 20px rgba(79,70,229,0.3);
        }
        .btn-primary:hover { background: var(--primary-dark); transform: translateY(-2px); box-shadow: 0 12px 28px rgba(79,70,229,0.35); }
        .btn-outline {
            background: transparent; color: var(--primary); border: 2px solid var(--primary);
        }
        .btn-outline:hover { background: var(--primary); color: white; }

        /* Counter Section */
        .counters {
            display: flex; justify-content: center; gap: 3rem;
            flex-wrap: wrap; padding: 2rem 1.5rem;
        }
        .counter-item {
            text-align: center; min-width: 120px;
        }
        .counter-number {
            font-size: 2.5rem; font-weight: 800; color: var(--primary);
            background: var(--primary-bg); border-radius: var(--radius-lg);
            padding: 0.5rem 1rem; display: inline-block; margin-bottom: 0.25rem;
        }
        .counter-label {
            font-size: 0.9rem; color: var(--text-medium); font-weight: 500;
        }

        /* Features */
        .features {
            display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 1.5rem; max-width: 1000px; margin: 0 auto; padding: 2rem 1.5rem;
        }
        .feature-card {
            background: var(--card-bg); border-radius: var(--radius-lg);
            padding: 1.5rem; box-shadow: 0 4px 12px rgba(0,0,0,0.04);
            border: 1px solid var(--border); transition: transform var(--transition);
        }
        .feature-card:hover { transform: translateY(-5px); }
        .feature-icon {
            font-size: 1.8rem; color: var(--primary); margin-bottom: 0.8rem;
            background: var(--primary-bg); width: 48px; height: 48px;
            border-radius: 12px; display: flex; align-items: center; justify-content: center;
        }
        .feature-card h3 { font-size: 1.1rem; margin-bottom: 0.4rem; }
        .feature-card p { font-size: 0.9rem; color: var(--text-medium); }

        /* Footer */
        .footer {
            text-align: center; padding: 2rem 1.5rem;
            color: var(--text-light); font-size: 0.85rem;
            border-top: 1px solid var(--border);
            background: rgba(255,255,255,0.5);
            margin-top: 2rem;
        }
        .footer a { color: var(--primary); text-decoration: none; font-weight: 500; }
        .footer-heart { color: #ef4444; animation: pulse 1.5s infinite; display: inline-block; }
        @keyframes pulse { 0%,100% { transform: scale(1); } 50% { transform: scale(1.25); } }

        /* Responsive */
        @media (max-width: 768px) {
            .nav-links { display: none; }
            .nav-toggle { display: block; }
            .nav-links.mobile-open {
                display: flex; flex-direction: column; position: absolute;
                top: 64px; left: 0; right: 0;
                background: rgba(255,255,255,0.97); backdrop-filter: blur(18px);
                padding: 1.5rem; gap: 1.2rem;
                border-bottom: 1px solid var(--border); box-shadow: var(--shadow-lg);
                z-index: 99;
            }
            .counters { gap: 1.5rem; }
            .counter-number { font-size: 2rem; }
        }
    </style>
</head>
<body>
    <nav class="navbar" aria-label="Main navigation">
        <div class="navbar-inner">
            <a href="index.html" class="nav-logo">
                <span class="logo-icon"><i class="fa-solid fa-clipboard-list"></i></span>
                FormCraft
            </a>
            <button class="nav-toggle" id="navToggle" aria-label="Toggle menu" aria-expanded="false">
                <i class="fa-solid fa-bars"></i>
            </button>
            <ul class="nav-links" id="navLinks">
                <li><a href="index.html">Home</a></li>
                <li><a href="form.html">Survey</a></li>
                <li><a href="#features">Features</a></li>
                <li><a href="form.html" class="btn-nav">Give Feedback</a></li>
            </ul>
        </div>
    </nav>

    <main>
        <section class="hero">
            <span class="hero-badge">📋 Integrated with Google Forms</span>
            <h1>
                Make Your Voice <br><span class="highlight">Heard</span>
            </h1>
            <p>
                We're building something better. Share your thoughts in just 2 minutes and
                <span class="typewriter" id="typewriter"></span>
            </p>
            <a href="form.html" class="btn btn-primary">
                <i class="fa-solid fa-pen-to-square"></i> Start the Survey
            </a>
        </section>

        <div class="counters">
            <div class="counter-item">
                <div class="counter-number" id="counterResponses">0</div>
                <div class="counter-label">Responses Collected</div>
            </div>
            <div class="counter-item">
                <div class="counter-number" id="counterTime">0</div>
                <div class="counter-label">Avg. Seconds</div>
            </div>
            <div class="counter-item">
                <div class="counter-number">100%</div>
                <div class="counter-label">Secure</div>
            </div>
        </div>

        <section id="features" class="features">
            <div class="feature-card">
                <div class="feature-icon"><i class="fa-solid fa-shield-halved"></i></div>
                <h3>Privacy First</h3>
                <p>Your data stays encrypted and never leaves Google's secure servers.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon"><i class="fa-solid fa-bolt"></i></div>
                <h3>Lightning Fast</h3>
                <p>Complete the form in under a minute. No sign‑up required.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon"><i class="fa-solid fa-mobile-screen"></i></div>
                <h3>Works Everywhere</h3>
                <p>Perfect on phone, tablet, or desktop. Responsive by design.</p>
            </div>
        </section>
    </main>

    <footer class="footer">
        <p>Made with <span class="footer-heart">❤️</span> • Hosted on GitHub Pages • © <span id="year"></span></p>
    </footer>

    <script>
        // ── Mobile menu toggle ──
        const toggle = document.getElementById('navToggle');
        const navLinks = document.getElementById('navLinks');
        toggle.addEventListener('click', () => {
            const isOpen = navLinks.classList.toggle('mobile-open');
            toggle.setAttribute('aria-expanded', isOpen);
            const icon = toggle.querySelector('i');
            icon.className = isOpen ? 'fa-solid fa-xmark' : 'fa-solid fa-bars';
        });
        document.querySelectorAll('#navLinks a').forEach(link => link.addEventListener('click', () => {
            if (navLinks.classList.contains('mobile-open')) {
                navLinks.classList.remove('mobile-open');
                toggle.setAttribute('aria-expanded', 'false');
                toggle.querySelector('i').className = 'fa-solid fa-bars';
            }
        }));

        // ── Typewriter effect ──
        const words = ['shape our roadmap.', 'improve the product.', 'make a difference. 🚀'];
        let wordIdx = 0, charIdx = 0, isDeleting = false;
        const el = document.getElementById('typewriter');
        function typeLoop() {
            const current = words[wordIdx];
            if (!isDeleting) {
                el.textContent = current.substring(0, charIdx + 1);
                charIdx++;
                if (charIdx === current.length) {
                    isDeleting = true;
                    setTimeout(typeLoop, 1800);
                    return;
                }
            } else {
                el.textContent = current.substring(0, charIdx - 1);
                charIdx--;
                if (charIdx === 0) {
                    isDeleting = false;
                    wordIdx = (wordIdx + 1) % words.length;
                }
            }
            setTimeout(typeLoop, isDeleting ? 50 : 100);
        }
        typeLoop();

        // ── Animated counters (increment until target) ──
        function animateCounter(id, target, duration = 1500, suffix = '') {
            const el = document.getElementById(id);
            let start = 0;
            const step = (timestamp) => {
                if (!start) start = timestamp;
                const progress = Math.min((timestamp - start) / duration, 1);
                el.textContent = Math.floor(progress * target) + suffix;
                if (progress < 1) requestAnimationFrame(step);
            };
            requestAnimationFrame(step);
        }
        animateCounter('counterResponses', 1247, 1800);
        animateCounter('counterTime', 57, 1600, 's');

        // ── Year ──
        document.getElementById('year').textContent = new Date().getFullYear();
    </script>
</body>
</html>
