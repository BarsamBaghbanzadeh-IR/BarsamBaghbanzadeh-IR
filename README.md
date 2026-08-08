# Let me create the complete HTML file
html_content = '''<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>برسام باغبان‌زاده | Barsam Baghbanzadeh</title>
    <link href="https://fonts.googleapis.com/css2?family=Vazirmatn:wght@100;300;400;500;700;900&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --persian-blue: #1a3a5c;
            --persian-gold: #d4af37;
            --persian-teal: #008080;
            --persian-red: #c41e3a;
            --persian-cream: #f5f5dc;
            --persian-dark: #0a1628;
            --persian-light: #e8f4f8;
            --gradient-primary: linear-gradient(135deg, #1a3a5c 0%, #008080 100%);
            --gradient-gold: linear-gradient(135deg, #d4af37 0%, #f4d03f 100%);
            --gradient-elegant: linear-gradient(135deg, #0a1628 0%, #1a3a5c 50%, #008080 100%);
            --shadow-elegant: 0 20px 60px rgba(26, 58, 92, 0.15);
            --shadow-gold: 0 10px 40px rgba(212, 175, 55, 0.3);
        }

        body {
            font-family: 'Vazirmatn', sans-serif;
            background: var(--persian-cream);
            color: var(--persian-dark);
            overflow-x: hidden;
            line-height: 1.8;
        }

        /* Persian Geometric Pattern Background */
        .pattern-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            opacity: 0.03;
            pointer-events: none;
            z-index: 0;
            background-image: url("data:image/svg+xml,%3Csvg width='100' height='100' viewBox='0 0 100 100' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M50 10 L90 50 L50 90 L10 50 Z' fill='none' stroke='%231a3a5c' stroke-width='0.5'/%3E%3Cpath d='M50 20 L80 50 L50 80 L20 50 Z' fill='none' stroke='%231a3a5c' stroke-width='0.5'/%3E%3Cpath d='M50 30 L70 50 L50 70 L30 50 Z' fill='none' stroke='%231a3a5c' stroke-width='0.5'/%3E%3C/svg%3E");
        }

        /* Navigation */
        .navbar {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 20px 5%;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            z-index: 1000;
            box-shadow: 0 2px 20px rgba(0,0,0,0.05);
            transition: all 0.3s ease;
        }

        .nav-container {
            max-width: 1400px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 24px;
            font-weight: 900;
            background: var(--gradient-primary);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .logo-icon {
            width: 40px;
            height: 40px;
            background: var(--gradient-primary);
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 20px;
        }

        .nav-links {
            display: flex;
            gap: 30px;
            list-style: none;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--persian-dark);
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
            background: var(--gradient-gold);
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .lang-switcher {
            display: flex;
            gap: 10px;
            align-items: center;
        }

        .lang-btn {
            padding: 8px 16px;
            border: 2px solid var(--persian-blue);
            background: transparent;
            color: var(--persian-blue);
            border-radius: 25px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s ease;
            font-family: 'Vazirmatn', sans-serif;
        }

        .lang-btn:hover, .lang-btn.active {
            background: var(--gradient-primary);
            color: white;
            border-color: transparent;
            box-shadow: var(--shadow-elegant);
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            padding: 100px 5%;
            background: var(--gradient-elegant);
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url("data:image/svg+xml,%3Csvg width='200' height='200' viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M100 20 L180 100 L100 180 L20 100 Z' fill='none' stroke='%23d4af37' stroke-width='0.5' opacity='0.1'/%3E%3Ccircle cx='100' cy='100' r='60' fill='none' stroke='%23d4af37' stroke-width='0.5' opacity='0.1'/%3E%3C/svg%3E");
            opacity: 0.3;
            animation: rotate 60s linear infinite;
        }

        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        .hero-content {
            max-width: 1200px;
            text-align: center;
            color: white;
            position: relative;
            z-index: 1;
            animation: fadeInUp 1s ease;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .hero-badge {
            display: inline-block;
            padding: 10px 30px;
            background: rgba(212, 175, 55, 0.2);
            border: 2px solid var(--persian-gold);
            border-radius: 50px;
            color: var(--persian-gold);
            font-weight: 600;
            margin-bottom: 30px;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% { box-shadow: 0 0 0 0 rgba(212, 175, 55, 0.4); }
            50% { box-shadow: 0 0 0 20px rgba(212, 175, 55, 0); }
        }

        .hero h1 {
            font-size: 72px;
            font-weight: 900;
            margin-bottom: 20px;
            line-height: 1.2;
            text-shadow: 0 4px 20px rgba(0,0,0,0.3);
        }

        .hero-subtitle {
            font-size: 24px;
            margin-bottom: 40px;
            opacity: 0.9;
            font-weight: 300;
        }

        .hero-stats {
            display: flex;
            justify-content: center;
            gap: 60px;
            margin-top: 60px;
            flex-wrap: wrap;
        }

        .stat-item {
            text-align: center;
        }

        .stat-number {
            font-size: 48px;
            font-weight: 900;
            color: var(--persian-gold);
            display: block;
        }

        .stat-label {
            font-size: 14px;
            opacity: 0.8;
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        .cta-buttons {
            display: flex;
            gap: 20px;
            justify-content: center;
            margin-top: 50px;
            flex-wrap: wrap;
        }

        .btn-primary, .btn-secondary {
            padding: 18px 40px;
            border-radius: 50px;
            font-size: 16px;
            font-weight: 700;
            text-decoration: none;
            transition: all 0.3s ease;
            display: inline-flex;
            align-items: center;
            gap: 10px;
            cursor: pointer;
            border: none;
            font-family: 'Vazirmatn', sans-serif;
        }

        .btn-primary {
            background: var(--gradient-gold);
            color: var(--persian-dark);
            box-shadow: var(--shadow-gold);
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 50px rgba(212, 175, 55, 0.5);
        }

        .btn-secondary {
            background: rgba(255, 255, 255, 0.1);
            color: white;
            border: 2px solid white;
            backdrop-filter: blur(10px);
        }

        .btn-secondary:hover {
            background: white;
            color: var(--persian-dark);
            transform: translateY(-3px);
        }

        /* Sections */
        section {
            padding: 100px 5%;
            position: relative;
            z-index: 1;
        }

        .section-header {
            text-align: center;
            margin-bottom: 80px;
        }

        .section-badge {
            display: inline-block;
            padding: 8px 20px;
            background: var(--gradient-primary);
            color: white;
            border-radius: 25px;
            font-size: 14px;
            font-weight: 600;
            margin-bottom: 20px;
        }

        .section-title {
            font-size: 48px;
            font-weight: 900;
            color: var(--persian-dark);
            margin-bottom: 20px;
        }

        .section-subtitle {
            font-size: 18px;
            color: var(--persian-blue);
            max-width: 600px;
            margin: 0 auto;
        }

        /* Features Grid */
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            max-width: 1400px;
            margin: 0 auto;
        }

        .feature-card {
            background: white;
            padding: 40px;
            border-radius: 20px;
            box-shadow: var(--shadow-elegant);
            transition: all 0.4s ease;
            position: relative;
            overflow: hidden;
        }

        .feature-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 4px;
            background: var(--gradient-gold);
            transform: scaleX(0);
            transition: transform 0.4s ease;
        }

        .feature-card:hover::before {
            transform: scaleX(1);
        }

        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 30px 80px rgba(26, 58, 92, 0.25);
        }

        .feature-icon {
            width: 80px;
            height: 80px;
            background: var(--gradient-primary);
            border-radius: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 36px;
            color: white;
            margin-bottom: 25px;
            transition: all 0.3s ease;
        }

        .feature-card:hover .feature-icon {
            transform: rotate(10deg) scale(1.1);
        }

        .feature-title {
            font-size: 24px;
            font-weight: 700;
            margin-bottom: 15px;
            color: var(--persian-dark);
        }

        .feature-desc {
            color: var(--persian-blue);
            line-height: 1.8;
        }

        /* Projects */
        .projects-section {
            background: white;
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 40px;
            max-width: 1400px;
            margin: 0 auto;
        }

        .project-card {
            background: var(--persian-cream);
            border-radius: 20px;
            overflow: hidden;
            box-shadow: var(--shadow-elegant);
            transition: all 0.4s ease;
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 30px 80px rgba(26, 58, 92, 0.3);
        }

        .project-image {
            height: 250px;
            background: var(--gradient-elegant);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 80px;
            color: white;
            position: relative;
            overflow: hidden;
        }

        .project-image::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url("data:image/svg+xml,%3Csvg width='100' height='100' viewBox='0 0 100 100' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M50 10 L90 50 L50 90 L10 50 Z' fill='none' stroke='white' stroke-width='0.5' opacity='0.2'/%3E%3C/svg%3E");
        }

        .project-content {
            padding: 30px;
        }

        .project-title {
            font-size: 24px;
            font-weight: 700;
            margin-bottom: 15px;
            color: var(--persian-dark);
        }

        .project-desc {
            color: var(--persian-blue);
            margin-bottom: 20px;
            line-height: 1.8;
        }

        .project-tags {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
            margin-bottom: 20px;
        }

        .tag {
            padding: 6px 15px;
            background: var(--gradient-primary);
            color: white;
            border-radius: 15px;
            font-size: 12px;
            font-weight: 600;
        }

        .project-link {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            color: var(--persian-teal);
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
        }

        .project-link:hover {
            gap: 15px;
            color: var(--persian-gold);
        }

        /* About Section */
        .about-section {
            background: var(--gradient-elegant);
            color: white;
        }

        .about-content {
            max-width: 1000px;
            margin: 0 auto;
            text-align: center;
        }

        .about-text {
            font-size: 20px;
            line-height: 2;
            margin-bottom: 40px;
            opacity: 0.95;
        }

        .about-highlights {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-top: 60px;
        }

        .highlight-item {
            background: rgba(255, 255, 255, 0.1);
            padding: 30px;
            border-radius: 15px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .highlight-icon {
            font-size: 40px;
            color: var(--persian-gold);
            margin-bottom: 15px;
        }

        .highlight-title {
            font-size: 20px;
            font-weight: 700;
            margin-bottom: 10px;
        }

        /* Contact Section */
        .contact-section {
            background: var(--persian-cream);
        }

        .contact-container {
            max-width: 800px;
            margin: 0 auto;
            text-align: center;
        }

        .contact-links {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin-top: 50px;
            flex-wrap: wrap;
        }

        .contact-btn {
            width: 80px;
            height: 80px;
            background: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 32px;
            color: var(--persian-blue);
            box-shadow: var(--shadow-elegant);
            transition: all 0.3s ease;
            text-decoration: none;
        }

        .contact-btn:hover {
            transform: translateY(-10px) rotate(10deg);
            background: var(--gradient-primary);
            color: white;
            box-shadow: 0 20px 60px rgba(26, 58, 92, 0.4);
        }

        /* Footer */
        footer {
            background: var(--persian-dark);
            color: white;
            padding: 60px 5% 30px;
            text-align: center;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
        }

        .footer-text {
            font-size: 18px;
            margin-bottom: 20px;
            opacity: 0.8;
        }

        .footer-links {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin: 30px 0;
            flex-wrap: wrap;
        }

        .footer-links a {
            color: white;
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .footer-links a:hover {
            color: var(--persian-gold);
        }

        .copyright {
            margin-top: 40px;
            padding-top: 30px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            opacity: 0.6;
            font-size: 14px;
        }

        /* Animations */
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s ease;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 42px;
            }

            .hero-subtitle {
                font-size: 18px;
            }

            .nav-links {
                display: none;
            }

            .hero-stats {
                gap: 30px;
            }

            .stat-number {
                font-size: 36px;
            }

            .section-title {
                font-size: 36px;
            }
        }

        /* Scrollbar */
        ::-webkit-scrollbar {
            width: 12px;
        }

        ::-webkit-scrollbar-track {
            background: var(--persian-cream);
        }

        ::-webkit-scrollbar-thumb {
            background: var(--gradient-primary);
            border-radius: 10px;
        }

        ::-webkit-scrollbar-thumb:hover {
            background: var(--gradient-gold);
        }

        /* Loading Animation */
        .loader {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--gradient-elegant);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 9999;
            transition: opacity 0.5s ease;
        }

        .loader.hidden {
            opacity: 0;
            pointer-events: none;
        }

        .loader-content {
            text-align: center;
            color: white;
        }

        .loader-spinner {
            width: 60px;
            height: 60px;
            border: 4px solid rgba(255, 255, 255, 0.1);
            border-top-color: var(--persian-gold);
            border-radius: 50%;
            animation: spin 1s linear infinite;
            margin: 0 auto 20px;
        }

        @keyframes spin {
            to { transform: rotate(360deg); }
        }
    </style>
</head>
<body>
    <!-- Loading Screen -->
    <div class="loader" id="loader">
        <div class="loader-content">
            <div class="loader-spinner"></div>
            <p data-lang="fa">در حال بارگذاری...</p>
            <p data-lang="en" style="display:none;">Loading...</p>
        </div>
    </div>

    <!-- Pattern Background -->
    <div class="pattern-bg"></div>

    <!-- Navigation -->
    <nav class="navbar">
        <div class="nav-container">
            <div class="logo">
                <div class="logo-icon">
                    <i class="fas fa-code"></i>
                </div>
                <span data-lang="fa">برسام</span>
                <span data-lang="en" style="display:none;">Barsam</span>
            </div>
            <ul class="nav-links">
                <li><a href="#home" data-lang="fa">خانه</a><a href="#home" data-lang="en" style="display:none;">Home</a></li>
                <li><a href="#features" data-lang="fa">توانمندی‌ها</a><a href="#features" data-lang="en" style="display:none;">Features</a></li>
                <li><a href="#projects" data-lang="fa">پروژه‌ها</a><a href="#projects" data-lang="en" style="display:none;">Projects</a></li>
                <li><a href="#about" data-lang="fa">درباره من</a><a href="#about" data-lang="en" style="display:none;">About</a></li>
                <li><a href="#contact" data-lang="fa">تماس</a><a href="#contact" data-lang="en" style="display:none;">Contact</a></li>
            </ul>
            <div class="lang-switcher">
                <button class="lang-btn active" onclick="switchLanguage('fa')">فا</button>
                <button class="lang-btn" onclick="switchLanguage('en')">EN</button>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="hero-content">
            <div class="hero-badge" data-lang="fa">
                <i class="fas fa-star"></i> از سرزمین ایران
            </div>
            <div class="hero-badge" data-lang="en" style="display:none;">
                <i class="fas fa-star"></i> From the Land of Iran
            </div>
            <h1 data-lang="fa">برسام باغبان‌زاده</h1>
            <h1 data-lang="en" style="display:none;">Barsam Baghbanzadeh</h1>
            <p class="hero-subtitle" data-lang="fa">توسعه‌دهنده و پژوهشگر هوش مصنوعی | ۱۴ ساله</p>
            <p class="hero-subtitle" data-lang="en" style="display:none;">AI Developer & Researcher | 14 Years Old</p>
            
            <div class="hero-stats">
                <div class="stat-item">
                    <span class="stat-number" data-count="15">0</span>
                    <span class="stat-label" data-lang="fa">پروژه</span>
                    <span class="stat-label" data-lang="en" style="display:none;">Projects</span>
                </div>
                <div class="stat-item">
                    <span class="stat-number" data-count="1000">0</span>
                    <span class="stat-label" data-lang="fa">ساعت کدنویسی</span>
                    <span class="stat-label" data-lang="en" style="display:none;">Hours Coding</span>
                </div>
                <div class="stat-item">
                    <span class="stat-number" data-count="5">0</span>
                    <span class="stat-label" data-lang="fa">زبان برنامه‌نویسی</span>
                    <span class="stat-label" data-lang="en" style="display:none;">Programming Languages</span>
                </div>
            </div>

            <div class="cta-buttons">
                <a href="#projects" class="btn-primary" data-lang="fa">
                    <i class="fas fa-rocket"></i> مشاهده پروژه‌ها
                </a>
                <a href="#projects" class="btn-primary" data-lang="en" style="display:none;">
                    <i class="fas fa-rocket"></i> View Projects
                </a>
                <a href="https://github.com/BarsamBaghbanzadeh-IR/BarsamBaghbanzadeh-IR" target="_blank" class="btn-secondary">
                    <i class="fab fa-github"></i> GitHub
                </a>
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section id="features">
        <div class="section-header fade-in">
            <span class="section-badge" data-lang="fa">توانمندی‌ها</span>
            <span class="section-badge" data-lang="en" style="display:none;">Expertise</span>
            <h2 class="section-title" data-lang="fa">حوزه‌های تخصصی</h2>
            <h2 class="section-title" data-lang="en" style="display:none;">Areas of Expertise</h2>
            <p class="section-subtitle" data-lang="fa">تمرکز بر تکنولوژی‌های پیشرفته و نوآورانه</p>
            <p class="section-subtitle" data-lang="en" style="display:none;">Focus on advanced and innovative technologies</p>
        </div>

        <div class="features-grid">
            <div class="feature-card fade-in">
                <div class="feature-icon">
                    <i class="fas fa-brain"></i>
                </div>
                <h3 class="feature-title" data-lang="fa">هوش مصنوعی</h3>
                <h3 class="feature-title" data-lang="en" style="display:none;">Artificial Intelligence</h3>
                <p class="feature-desc" data-lang="fa">توسعه مدل‌های یادگیری ماشین و شبکه‌های عصبی عمیق برای حل مسائل پیچیده</p>
                <p class="feature-desc" data-lang="en" style="display:none;">Developing machine learning models and deep neural networks for complex problem solving</p>
            </div>

            <div class="feature-card fade-in">
                <div class="feature-icon">
                    <i class="fas fa-network-wired"></i>
                </div>
                <h3 class="feature-title" data-lang="fa">یادگیری فدرال</h3>
                <h3 class="feature-title" data-lang="en" style="display:none;">Federated Learning</h3>
                <p class="feature-desc" data-lang="fa">آموزش مدل‌های هوش مصنوعی با حفظ حریم خصوصی داده‌ها</p>
                <p class="feature-desc" data-lang="en" style="display:none;">Training AI models while preserving data privacy</p>
            </div>

            <div class="feature-card fade-in">
                <div class="feature-icon">
                    <i class="fas fa-shield-alt"></i>
                </div>
                <h3 class="feature-title" data-lang="fa">امنیت سایبری</h3>
                <h3 class="feature-title" data-lang="en" style="display:none;">Cybersecurity</h3>
                <p class="feature-desc" data-lang="fa">پیاده‌سازی سیستم‌های امن و رمزنگاری پیشرفته</p>
                <p class="feature-desc" data-lang="en" style="display:none;">Implementing secure systems and advanced encryption</p>
            </div>

            <div class="feature-card fade-in">
                <div class="feature-icon">
                    <i class="fas fa-database"></i>
                </div>
                <h3 class="feature-title" data-lang="fa">علم داده</h3>
                <h3 class="feature-title" data-lang="en" style="display:none;">Data Science</h3>
                <p class="feature-desc" data-lang="fa">تحلیل داده‌های بزرگ و استخراج الگوهای معنادار</p>
                <p class="feature-desc" data-lang="en" style="display:none;">Big data analysis and meaningful pattern extraction</p>
            </div>

            <div class="feature-card fade-in">
                <div class="feature-icon">
                    <i class="fas fa-heartbeat"></i>
                </div>
                <h3 class="feature-title" data-lang="fa">سلامت دیجیتال</h3>
                <h3 class="feature-title" data-lang="en" style="display:none;">Digital Health</h3>
                <p class="feature-desc" data-lang="fa">کاربرد هوش مصنوعی در پزشکی و تشخیص بیماری</p>
                <p class="feature-desc" data-lang="en" style="display:none;">AI applications in medicine and disease diagnosis</p>
            </div>

            <div class="feature-card fade-in">
                <div class="feature-icon">
                    <i class="fas fa-code"></i>
                </div>
                <h3 class="feature-title" data-lang="fa">توسعه وب</h3>
                <h3 class="feature-title" data-lang="en" style="display:none;">Web Development</h3>
                <p class="feature-desc" data-lang="fa">طراحی و توسعه وب‌سایت‌های مدرن و واکنش‌گرا</p>
                <p class="feature-desc" data-lang="en" style="display:none;">Design and development of modern responsive websites</p>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section class="projects-section" id="projects">
        <div class="section-header fade-in">
            <span class="section-badge" data-lang="fa">نمونه کارها</span>
            <span class="section-badge" data-lang="en" style="display:none;">Portfolio</span>
            <h2 class="section-title" data-lang="fa">پروژه‌های برجسته</h2>
            <h2 class="section-title" data-lang="en" style="display:none;">Featured Projects</h2>
            <p class="section-subtitle" data-lang="fa">مجموعه‌ای از پروژه‌های نوآورانه و پیشرفته</p>
            <p class="section-subtitle" data-lang="en" style="display:none;">A collection of innovative and advanced projects</p>
        </div>

        <div class="projects-grid">
            <div class="project-card fade-in">
                <div class="project-image">
                    <i class="fas fa-heart"></i>
                </div>
                <div class="project-content">
                    <h3 class="project-title" data-lang="fa">سیستم تشخیص بیماری قلبی</h3>
                    <h3 class="project-title" data-lang="en" style="display:none;">Cardiac Disease Detection System</h3>
                    <p class="project-desc" data-lang="fa">مدل هوش مصنوعی برای پیش‌بینی بیماری‌های قلبی با دقت بالا</p>
                    <p class="project-desc" data-lang="en" style="display:none;">AI model for high-accuracy cardiac disease prediction</p>
                    <div class="project-tags">
                        <span class="tag">Python</span>
                        <span class="tag">TensorFlow</span>
                        <span class="tag">ML</span>
                    </div>
                    <a href="#" class="project-link" data-lang="fa">
                        مشاهده پروژه <i class="fas fa-arrow-left"></i>
                    </a>
                    <a href="#" class="project-link" data-lang="en" style="display:none;">
                        View Project <i class="fas fa-arrow-right"></i>
                    </a>
                </div>
            </div>

            <div class="project-card fade-in">
                <div class="project-image">
                    <i class="fas fa-image"></i>
                </div>
                <div class="project-content">
                    <h3 class="project-title" data-lang="fa">پردازش تصویر پزشکی</h3>
                    <h3 class="project-title" data-lang="en" style="display:none;">Medical Image Processing</h3>
                    <p class="project-desc" data-lang="fa">شبکه عصبی کانولوشنی برای تحلیل تصاویر پزشکی</p>
                    <p class="project-desc" data-lang="en" style="display:none;">Convolutional neural network for medical image analysis</p>
                    <div class="project-tags">
                        <span class="tag">CNN</span>
                        <span class="tag">PyTorch</span>
                        <span class="tag">CV</span>
                    </div>
                    <a href="#" class="project-link" data-lang="fa">
                        مشاهده پروژه <i class="fas fa-arrow-left"></i>
                    </a>
                    <a href="#" class="project-link" data-lang="en" style="display:none;">
                        View Project <i class="fas fa-arrow-right"></i>
                    </a>
                </div>
            </div>

            <div class="project-card fade-in">
                <div class="project-image">
                    <i class="fas fa-lock"></i>
                </div>
                <div class="project-content">
                    <h3 class="project-title" data-lang="fa">سیستم حریم خصوصی تفاضلی</h3>
                    <h3 class="project-title" data-lang="en" style="display:none;">Differential Privacy System</h3>
                    <p class="project-desc" data-lang="fa">پیاده‌سازی مکانیزم‌های حفظ حریم خصوصی در یادگیری ماشین</p>
                    <p class="project-desc" data-lang="en" style="display:none;">Implementing privacy-preserving mechanisms in machine learning</p>
                    <div class="project-tags">
                        <span class="tag">Privacy</span>
                        <span class="tag">Security</span>
                        <span class="tag">FL</span>
                    </div>
                    <a href="#" class="project-link" data-lang="fa">
                        مشاهده پروژه <i class="fas fa-arrow-left"></i>
                    </a>
                    <a href="#" class="project-link" data-lang="en" style="display:none;">
                        View Project <i class="fas fa-arrow-right"></i>
                    </a>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section class="about-section" id="about">
        <div class="about-content fade-in">
            <span class="section-badge" data-lang="fa">درباره من</span>
            <span class="section-badge" data-lang="en" style="display:none;">About Me</span>
            <h2 class="section-title" style="color: white;" data-lang="fa">از سرزمین پارس</h2>
            <h2 class="section-title" style="color: white;" data-lang="en" style="display:none;">From the Land of Persia</h2>
            
            <p class="about-text" data-lang="fa">
                من برسام باغبان‌زاده هستم، ۱۴ ساله از ایران. سرزمینی با تاریخ غنی و فرهنگ هزاران ساله. 
                علاقه‌مند به هوش مصنوعی و تکنولوژی‌های نوین هستم و تلاش می‌کنم با استفاده از دانش و مهارت‌هایم، 
                راه‌حل‌های نوآورانه برای مسائل پیچیده ارائه دهم.
            </p>
            <p class="about-text" data-lang="en" style="display:none;">
                I am Barsam Baghbanzadeh, 14 years old from Iran. A land with rich history and thousands of years of culture. 
                I am passionate about artificial intelligence and modern technologies, striving to provide innovative solutions 
                for complex problems using my knowledge and skills.
            </p>

            <div class="about-highlights">
                <div class="highlight-item">
                    <div class="highlight-icon">
                        <i class="fas fa-graduation-cap"></i>
                    </div>
                    <h3 class="highlight-title" data-lang="fa">یادگیری مستمر</h3>
                    <h3 class="highlight-title" data-lang="en" style="display:none;">Continuous Learning</h3>
                    <p data-lang="fa">همیشه در حال یادگیری تکنولوژی‌های جدید</p>
                    <p data-lang="en" style="display:none;">Always learning new technologies</p>
                </div>

                <div class="highlight-item">
                    <div class="highlight-icon">
                        <i class="fas fa-lightbulb"></i>
                    </div>
                    <h3 class="highlight-title" data-lang="fa">نوآوری</h3>
                    <h3 class="highlight-title" data-lang="en" style="display:none;">Innovation</h3>
                    <p data-lang="fa">ایده‌های خلاقانه و راه‌حل‌های نوین</p>
                    <p data-lang="en" style="display:none;">Creative ideas and novel solutions</p>
                </div>

                <div class="highlight-item">
                    <div class="highlight-icon">
                        <i class="fas fa-globe"></i>
                    </div>
                    <h3 class="highlight-title" data-lang="fa">دیدگاه جهانی</h3>
                    <h3 class="highlight-title" data-lang="en" style="display:none;">Global Perspective</h3>
                    <p data-lang="fa">درک مسائل از دیدگاه بین‌المللی</p>
                    <p data-lang="en" style="display:none;">Understanding issues from international perspective</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="contact-section" id="contact">
        <div class="section-header fade-in">
            <span class="section-badge" data-lang="fa">ارتباط</span>
            <span class="section-badge" data-lang="en" style="display:none;">Contact</span>
            <h2 class="section-title" data-lang="fa">با من در ارتباط باشید</h2>
            <h2 class="section-title" data-lang="en" style="display:none;">Get In Touch</h2>
            <p class="section-subtitle" data-lang="fa">برای همکاری و پروژه‌های جدید</p>
            <p class="section-subtitle" data-lang="en" style="display:none;">For collaboration and new projects</p>
        </div>

        <div class="contact-container fade-in">
            <div class="contact-links">
                <a href="https://github.com/BarsamBaghbanzadeh-IR/BarsamBaghbanzadeh-IR" target="_blank" class="contact-btn" title="GitHub">
                    <i class="fab fa-github"></i>
                </a>
                <a href="mailto:contact@example.com" class="contact-btn" title="Email">
                    <i class="fas fa-envelope"></i>
                </a>
                <a href="#" class="contact-btn" title="LinkedIn">
                    <i class="fab fa-linkedin-in"></i>
                </a>
                <a href="#" class="contact-btn" title="Twitter">
                    <i class="fab fa-twitter"></i>
                </a>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <p class="footer-text" data-lang="fa">
                ساخته شده با ❤️ در ایران
            </p>
            <p class="footer-text" data-lang="en" style="display:none;">
                Made with ❤️ in Iran
            </p>
            
            <div class="footer-links">
                <a href="#home" data-lang="fa">خانه</a>
                <a href="#home" data-lang="en" style="display:none;">Home</a>
                <a href="#features" data-lang="fa">توانمندی‌ها</a>
                <a href="#features" data-lang="en" style="display:none;">Features</a>
                <a href="#projects" data-lang="fa">پروژه‌ها</a>
                <a href="#projects" data-lang="en" style="display:none;">Projects</a>
                <a href="#contact" data-lang="fa">تماس</a>
                <a href="#contact" data-lang="en" style="display:none;">Contact</a>
            </div>

            <p class="copyright">
                &copy; 2024 Barsam Baghbanzadeh. All rights reserved.
            </p>
        </div>
    </footer>

    <script>
        // Loading Screen
        window.addEventListener('load', () => {
            setTimeout(() => {
                document.getElementById('loader').classList.add('hidden');
            }, 1000);
        });

        // Language Switcher
        function switchLanguage(lang) {
            const elements = document.querySelectorAll('[data-lang]');
            elements.forEach(el => {
                if (el.getAttribute('data-lang') === lang) {
                    el.style.display = '';
                } else {
                    el.style.display = 'none';
                }
            });

            // Update active button
            document.querySelectorAll('.lang-btn').forEach(btn => {
                btn.classList.remove('active');
            });
            event.target.classList.add('active');

            // Update direction
            document.documentElement.dir = lang === 'fa' ? 'rtl' : 'ltr';
            document.documentElement.lang = lang;
        }

        // Scroll Animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, observerOptions);

        document.querySelectorAll('.fade-in').forEach(el => {
            observer.observe(el);
        });

        // Counter Animation
        function animateCounter(el) {
            const target = parseInt(el.getAttribute('data-count'));
            const duration = 2000;
            const step = target / (duration / 16);
            let current = 0;

            const timer = setInterval(() => {
                current += step;
                if (current >= target) {
                    el.textContent = target;
                    clearInterval(timer);
                } else {
                    el.textContent = Math.floor(current);
                }
            }, 16);
        }

        // Trigger counter animation when stats are visible
        const statsObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    const counters = entry.target.querySelectorAll('.stat-number');
                    counters.forEach(counter => animateCounter(counter));
                    statsObserver.unobserve(entry.target);
                }
            });
        }, { threshold: 0.5 });

        const statsSection = document.querySelector('.hero-stats');
        if (statsSection) {
            statsObserver.observe(statsSection);
        }

        // Smooth Scroll
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Navbar Scroll Effect
        let lastScroll = 0;
        window.addEventListener('scroll', () => {
            const navbar = document.querySelector('.navbar');
            const currentScroll = window.pageYOffset;

            if (currentScroll > 100) {
                navbar.style.padding = '15px 5%';
                navbar.style.boxShadow = '0 5px 30px rgba(0,0,0,0.1)';
            } else {
                navbar.style.padding = '20px 5%';
                navbar.style.boxShadow = '0 2px 20px rgba(0,0,0,0.05)';
            }

            lastScroll = currentScroll;
        });

        // Parallax Effect
        window.addEventListener('scroll', () => {
            const scrolled = window.pageYOffset;
            const pattern = document.querySelector('.pattern-bg');
            if (pattern) {
                pattern.style.transform = `translateY(${scrolled * 0.5}px)`;
            }
        });
    </script>
</body>
</html>'''

# Save the HTML content to a file
with open('/tmp/barsam_website.html', 'w', encoding='utf-8') as f:
    f.write(html_content)

print("Website HTML created successfully!")
print(f"File size: {len(html_content)} characters")
print("\nKey Features:")
print("✓ Professional Persian-inspired design with elegant color scheme")
print("✓ Geometric patterns inspired by Persian art")
print("✓ Smooth animations and transitions")
print("✓ Full bilingual support (Persian/English)")
print("✓ Responsive design for all devices")
print("✓ Interactive elements with hover effects")
print("✓ Counter animations for statistics")
print("✓ Smooth scrolling navigation")
print("✓ Loading screen animation")
print("✓ Professional typography with Vazirmatn font")

 # Result 
Website HTML created successfully!
File size: 42865 characters

Key Features:
✓ Professional Persian-inspired design with elegant color scheme
✓ Geometric patterns inspired by Persian art
✓ Smooth animations and transitions
✓ Full bilingual support (Persian/English)
✓ Responsive design for all devices
✓ Interactive elements with hover effects
✓ Counter animations for statistics
✓ Smooth scrolling navigation
✓ Loading screen animation
✓ Professional typography with Vazirmatn font
