<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>وسام سعد - خبير الذكاء الاصطناعي</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: #0a0a0a;
            color: #ffffff;
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Navigation Bar */
        .navbar {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            background: rgba(10, 10, 10, 0.95);
            backdrop-filter: blur(15px);
            padding: 1rem 2rem;
            z-index: 1000;
            border-bottom: 1px solid rgba(255, 107, 53, 0.2);
            transition: transform 0.3s ease;
        }

        .navbar.hidden {
            transform: translateY(-100%);
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .nav-logo {
            font-size: 1.5rem;
            font-weight: bold;
            color: #ff6b35;
            cursor: pointer;
        }

        .nav-links {
            display: flex;
            gap: 2rem;
            list-style: none;
        }

        .nav-links a {
            color: #ffffff;
            text-decoration: none;
            transition: color 0.3s ease;
            font-weight: 500;
        }

        .nav-links a:hover {
            color: #ff6b35;
        }

        .nav-toggle {
            display: none;
            flex-direction: column;
            cursor: pointer;
        }

        .nav-toggle span {
            width: 25px;
            height: 3px;
            background: #ff6b35;
            margin: 3px 0;
            transition: 0.3s;
        }

        /* Animated Background */
        .bg-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            background: radial-gradient(ellipse at top, #1a1a2e 0%, #16213e 40%, #0f0f23 100%);
        }

        .bg-animation::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                radial-gradient(circle at 20% 30%, rgba(255, 107, 53, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 80% 70%, rgba(247, 147, 30, 0.08) 0%, transparent 50%),
                radial-gradient(circle at 40% 80%, rgba(255, 107, 53, 0.06) 0%, transparent 50%);
            animation: pulse 4s ease-in-out infinite alternate;
        }

        @keyframes pulse {
            0% { opacity: 0.6; }
            100% { opacity: 1; }
        }

        /* Floating particles */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        .particle {
            position: absolute;
            width: 2px;
            height: 2px;
            background: #ff6b35;
            border-radius: 50%;
            opacity: 0.7;
            animation: float 8s linear infinite;
        }

        @keyframes float {
            0% {
                transform: translateY(100vh) rotate(0deg);
                opacity: 0;
            }
            10% {
                opacity: 0.7;
            }
            90% {
                opacity: 0.7;
            }
            100% {
                transform: translateY(-100px) rotate(360deg);
                opacity: 0;
            }
        }

        /* Main Container */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 80px 1rem 0;
            position: relative;
            z-index: 10;
        }

        /* Header Section */
        .header {
            text-align: center;
            padding: 3rem 1rem;
            background: linear-gradient(135deg, rgba(255, 107, 53, 0.1), rgba(26, 26, 46, 0.3));
            margin: 2rem 0;
            border-radius: 30px;
            backdrop-filter: blur(20px);
            border: 1px solid rgba(255, 107, 53, 0.2);
            position: relative;
            overflow: hidden;
        }

        .header::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: conic-gradient(from 0deg, transparent, rgba(255, 107, 53, 0.1), transparent);
            animation: rotate 20s linear infinite;
        }

        @keyframes rotate {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .header-content {
            position: relative;
            z-index: 2;
        }

        .profile-image {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            background: linear-gradient(45deg, #ff6b35, #f7931e);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2.5rem;
            color: white;
            margin: 0 auto 2rem;
            box-shadow: 0 20px 40px rgba(255, 107, 53, 0.4);
            position: relative;
            overflow: hidden;
        }

        .profile-image::before {
            content: '';
            position: absolute;
            top: -2px;
            left: -2px;
            right: -2px;
            bottom: -2px;
            background: linear-gradient(45deg, #ff6b35, #f7931e, #ff6b35);
            border-radius: 50%;
            z-index: -1;
            animation: borderGlow 3s ease-in-out infinite;
        }

        @keyframes borderGlow {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.5; }
        }

        .name {
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 1rem;
            background: linear-gradient(45deg, #ff6b35, #f7931e, #ffffff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            text-shadow: 0 0 30px rgba(255, 107, 53, 0.5);
        }

        .title {
            font-size: 1.2rem;
            color: #cccccc;
            margin-bottom: 1.5rem;
            font-weight: 300;
            line-height: 1.4;
        }

        .quote {
            font-size: 1.1rem;
            font-style: italic;
            color: #ff6b35;
            margin-bottom: 2rem;
            padding: 1rem;
            background: rgba(255, 107, 53, 0.1);
            border-radius: 15px;
            border-right: 4px solid #ff6b35;
            display: inline-block;
            max-width: 100%;
        }

        .contact-info {
            display: flex;
            justify-content: center;
            gap: 1rem;
            flex-wrap: wrap;
            margin-top: 2rem;
        }

        .contact-item {
            background: rgba(255, 107, 53, 0.1);
            padding: 0.8rem 1.5rem;
            border-radius: 25px;
            border: 1px solid rgba(255, 107, 53, 0.3);
            transition: all 0.3s ease;
            font-size: 0.9rem;
        }

        .contact-item:hover {
            background: rgba(255, 107, 53, 0.2);
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(255, 107, 53, 0.3);
        }

        /* Content Grid */
        .content-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 2rem;
            margin: 3rem 0;
        }

        .content-card {
            background: linear-gradient(135deg, rgba(255, 107, 53, 0.05), rgba(26, 26, 46, 0.8));
            border-radius: 25px;
            padding: 2rem;
            border: 1px solid rgba(255, 107, 53, 0.2);
            backdrop-filter: blur(15px);
            position: relative;
            overflow: hidden;
            transition: all 0.4s ease;
        }

        .content-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 107, 53, 0.1), transparent);
            transition: left 0.6s ease;
        }

        .content-card:hover::before {
            left: 100%;
        }

        .content-card:hover {
            transform: translateY(-10px);
            border-color: #ff6b35;
            box-shadow: 0 25px 50px rgba(255, 107, 53, 0.3);
        }

        .card-title {
            font-size: 1.8rem;
            color: #ff6b35;
            margin-bottom: 1.5rem;
            text-align: center;
            position: relative;
        }

        .card-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 3px;
            background: linear-gradient(45deg, #ff6b35, #f7931e);
            border-radius: 2px;
        }

        .card-content {
            color: #e0e0e0;
            line-height: 1.8;
            font-size: 0.95rem;
        }

        .card-content p {
            margin-bottom: 1.5rem;
        }

        .highlight-list {
            list-style: none;
            padding: 0;
        }

        .highlight-list li {
            margin-bottom: 1rem;
            padding: 1rem;
            background: rgba(255, 107, 53, 0.1);
            border-radius: 10px;
            border-right: 4px solid #ff6b35;
            transition: all 0.3s ease;
            font-size: 0.9rem;
        }

        .highlight-list li:hover {
            background: rgba(255, 107, 53, 0.15);
            transform: translateX(-10px);
        }

        .highlight-list li::before {
            content: '▶';
            color: #ff6b35;
            margin-left: 1rem;
            font-weight: bold;
        }

        /* Skills Section */
        .skills-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 1.5rem;
            margin: 3rem 0;
        }

        .skill-card {
            background: linear-gradient(135deg, rgba(255, 107, 53, 0.1), rgba(26, 26, 46, 0.8));
            border-radius: 20px;
            padding: 1.5rem;
            border: 1px solid rgba(255, 107, 53, 0.3);
            text-align: center;
            transition: all 0.3s ease;
        }

        .skill-card:hover {
            transform: scale(1.02);
            box-shadow: 0 20px 40px rgba(255, 107, 53, 0.2);
        }

        .skill-icon {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }

        .skill-title {
            color: #ff6b35;
            font-size: 1.2rem;
            margin-bottom: 1rem;
        }

        .skill-items {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            justify-content: center;
        }

        .skill-tag {
            background: rgba(255, 107, 53, 0.2);
            padding: 0.4rem 0.8rem;
            border-radius: 15px;
            font-size: 0.8rem;
            color: #ffffff;
            border: 1px solid rgba(255, 107, 53, 0.4);
        }

        /* Projects Showcase */
        .projects-showcase {
            margin: 4rem 0;
        }

        .project-card {
            background: linear-gradient(135deg, rgba(26, 26, 46, 0.9), rgba(255, 107, 53, 0.05));
            border-radius: 20px;
            padding: 2rem;
            margin-bottom: 2rem;
            border: 1px solid rgba(255, 107, 53, 0.2);
            position: relative;
            overflow: hidden;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 4px;
            background: linear-gradient(90deg, #ff6b35, #f7931e);
        }

        .project-title {
            color: #ff6b35;
            font-size: 1.3rem;
            margin-bottom: 1rem;
        }

        .project-description {
            color: #cccccc;
            margin-bottom: 1.5rem;
            font-size: 0.9rem;
            line-height: 1.6;
        }

        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
        }

        .tech-tag {
            background: rgba(247, 147, 30, 0.2);
            padding: 0.3rem 0.6rem;
            border-radius: 12px;
            font-size: 0.7rem;
            color: #f7931e;
            border: 1px solid rgba(247, 147, 30, 0.4);
        }

        /* Contact Form */
        .contact-section {
            background: linear-gradient(135deg, rgba(255, 107, 53, 0.1), rgba(26, 26, 46, 0.8));
            border-radius: 25px;
            padding: 2rem;
            margin: 3rem 0;
            border: 1px solid rgba(255, 107, 53, 0.3);
            text-align: center;
        }

        .contact-form {
            max-width: 600px;
            margin: 2rem auto;
        }

        .form-group {
            margin-bottom: 1.5rem;
            text-align: right;
        }

        .form-group label {
            display: block;
            color: #ff6b35;
            margin-bottom: 0.5rem;
            font-weight: 500;
            font-size: 0.9rem;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 0.8rem;
            background: rgba(255, 255, 255, 0.1);
            border: 2px solid rgba(255, 107, 53, 0.3);
            border-radius: 12px;
            color: white;
            font-size: 0.9rem;
            transition: all 0.3s ease;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #ff6b35;
            box-shadow: 0 0 15px rgba(255, 107, 53, 0.3);
            background: rgba(255, 255, 255, 0.15);
        }

        .submit-btn {
            background: linear-gradient(45deg, #ff6b35, #f7931e);
            color: white;
            border: none;
            padding: 0.8rem 2rem;
            border-radius: 25px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .submit-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: left 0.5s ease;
        }

        .submit-btn:hover::before {
            left: 100%;
        }

        .submit-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 30px rgba(255, 107, 53, 0.4);
        }

        /* Social Links */
        .social-links {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin: 2rem 0;
        }

        .social-link {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: rgba(255, 107, 53, 0.1);
            border: 2px solid rgba(255, 107, 53, 0.3);
            display: flex;
            align-items: center;
            justify-content: center;
            text-decoration: none;
            color: #ff6b35;
            font-size: 1.3rem;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .social-link::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, #ff6b35, #f7931e);
            opacity: 0;
            transition: opacity 0.3s ease;
            border-radius: 50%;
        }

        .social-link:hover::before {
            opacity: 1;
        }

        .social-link:hover {
            color: white;
            transform: scale(1.1) rotate(10deg);
            border-color: #ff6b35;
        }

        .social-link span {
            position: relative;
            z-index: 2;
        }

        /* Fun Facts */
        .fun-facts {
            background: linear-gradient(135deg, rgba(26, 26, 46, 0.8), rgba(255, 107, 53, 0.05));
            border-radius: 20px;
            padding: 2rem;
            margin: 3rem 0;
            border: 1px solid rgba(255, 107, 53, 0.2);
            text-align: center;
        }

        .fun-facts h3 {
            color: #ff6b35;
            margin-bottom: 1.5rem;
            font-size: 1.6rem;
        }

        .facts-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 1rem;
        }

        .fact-item {
            background: rgba(255, 107, 53, 0.1);
            padding: 1rem;
            border-radius: 15px;
            border: 1px solid rgba(255, 107, 53, 0.2);
            transition: all 0.3s ease;
        }

        .fact-item:hover {
            background: rgba(255, 107, 53, 0.15);
            transform: translateY(-5px);
        }

        .fact-emoji {
            font-size: 1.8rem;
            margin-bottom: 0.5rem;
        }

        /* Responsive Design for tablets */
        @media (min-width: 768px) {
            .container {
                padding: 80px 2rem 0;
            }
            
            .content-grid {
                grid-template-columns: 1fr 1fr;
                gap: 3rem;
            }
            
            .skills-grid {
                grid-template-columns: repeat(2, 1fr);
                gap: 2rem;
            }
            
            .facts-grid {
                grid-template-columns: repeat(2, 1fr);
                gap: 1.5rem;
            }
            
            .name {
                font-size: 3.5rem;
            }
            
            .title {
                font-size: 1.5rem;
            }
            
            .profile-image {
                width: 200px;
                height: 200px;
                font-size: 3rem;
            }
        }

        /* Responsive Design for large screens */
        @media (min-width: 1024px) {
            .skills-grid {
                grid-template-columns: repeat(4, 1fr);
            }
            
            .facts-grid {
                grid-template-columns: repeat(4, 1fr);
            }
            
            .nav-links {
                display: flex;
            }
            
            .nav-toggle {
                display: none;
            }
        }

        /* Mobile navigation */
        @media (max-width: 1023px) {
            .nav-links {
                display: none;
                position: absolute;
                top: 100%;
                left: 0;
                right: 0;
                background: rgba(10, 10, 10, 0.98);
                flex-direction: column;
                padding: 1rem 2rem;
                border-top: 1px solid rgba(255, 107, 53, 0.2);
            }
            
            .nav-links.active {
                display: flex;
            }
            
            .nav-toggle {
                display: flex;
            }
            
            .nav-toggle.active span:nth-child(1) {
                transform: rotate(-45deg) translate(-5px, 6px);
            }
            
            .nav-toggle.active span:nth-child(2) {
                opacity: 0;
            }
            
            .nav-toggle.active span:nth-child(3) {
                transform: rotate(45deg) translate(-5px, -6px);
            }
        }

        /* Extra small phones */
        @media (max-width: 480px) {
            .container {
                padding: 80px 0.5rem 0;
            }
            
            .header {
                padding: 2rem 0.5rem;
                margin: 1rem 0;
            }
            
            .content-card {
                padding: 1.5rem;
            }
            
            .name {
                font-size: 2rem;
            }
            
            .title {
                font-size: 1rem;
            }
            
            .quote {
                font-size: 1rem;
                padding: 0.8rem;
            }
            
            .contact-info {
                flex-direction: column;
                gap: 0.8rem;
            }
            
            .contact-item {
                font-size: 0.8rem;
                padding: 0.6rem 1rem;
            }
        }

        /* Scroll animations */
        .scroll-reveal {
            opacity: 0;
            transform: translateY(50px);
            transition: all 0.6s ease;
        }

        .scroll-reveal.revealed {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>
    <!-- Navigation Bar -->
    <nav class="navbar" id="navbar">
        <div class="nav-container">
            <div class="nav-logo">وسام سعد</div>
            <ul class="nav-links" id="navLinks">
                <li><a href="#home">الرئيسية</a></li>
                <li><a href="#about">من أنا</a></li>
                <li><a href="#skills">المهارات</a></li>
                <li><a href="#projects">المشاريع</a></li>
                <li><a href="#contact">التواصل</a></li>
            </ul>
            <div class="nav-toggle" id="navToggle">
                <span></span>
                <span></span>
                <span></span>
            </div>
        </div>
    </nav>

    <div class="bg-animation"></div>
    <div class="particles" id="particles"></div>

    <div class="container">
        <!-- Header Section -->
        <section id="home" class="header scroll-reveal">
            <div class="header-content">
                <div class="profile-image">وس</div>
                <h1 class="name">وسام سعد</h1>
                <p class="title">باحث في الذكاء الاصطناعي • خبير تعلم عميق • مهندس بيانات</p>
                <div class="quote">
                    "الآلة تتعلم... لكني أنا من علمها أن تفكر."
                </div>
                <div class="contact-info">
                    <div class="contact-item">
                        📧 wissam.ai.master@gmail.com
                    </div>
                    <div class="contact-item">
                        📱 @ws_12fg
                    </div>
                </div>
            </div>
        </section>

        <!-- About & Education Grid -->
        <section id="about" class="content-grid scroll-reveal">
            <div class="content-card">
                <h2 class="card-title">من أنا</h2>
                <div class="card-content">
                    <p>مرحباً، أنا وسام سعد، باحث متخصص في مجال الذكاء الاصطناعي والتعلم العميق. بدأت رحلتي في عالم التكنولوجيا منذ الصغر، حيث كنت مفتوناً بقدرة الحاسوب على حل المشاكل المعقدة.</p>
                    
                    <p>درست هندسة الحاسوب في جامعة بغداد وحصلت على درجة الماجستير من معهد MIT في الذكاء الاصطناعي. تخصصت في تطوير الشبكات العصبية المتقدمة والتعلم المعزز.</p>
                    
                    <p>أؤمن بأن الذكاء الاصطناعي يجب أن يخدم الإنسانية وأن التطوير التقني يجب أن يتماشى مع القيم الأخلاقية.</p>
                </div>
            </div>

            <div class="content-card">
                <h2 class="card-title">الشهادات العلمية</h2>
                <div class="card-content">
                    <ul class="highlight-list">
                        <li>
                            <strong>ماجستير في الذكاء الاصطناعي</strong><br>
                            معهد MIT الأمريكي (2020-2022)<br>
                            المعدل: 3.9/4.0
                        </li>
                        <li>
                            <strong>بكالوريوس في هندسة الحاسوب</strong><br>
                            جامعة بغداد (2015-2019)<br>
                            امتياز مع مرتبة الشرف الأولى
                        </li>
                    </ul>
                </div>
            </div>
        </section>

        <!-- Experience & Research Grid -->
        <div class="content-grid scroll-reveal">
            <div class="content-card">
                <h2 class="card-title">الخبرات العملية</h2>
                <div class="card-content">
                    <ul class="highlight-list">
                        <li>
                            <strong>مهندس تعلم آلي أول - Google DeepMind</strong><br>
                            (2023 - حتى الآن)
                        </li>
                        <li>
                            <strong>متدرب بحثي متقدم - OpenAI</strong><br>
                            (2022 - 2023)
                        </li>
                        <li>
                            <strong>مستشار تقني</strong><br>
                            شركات التكنولوجيا الناشئة (2021 - حتى الآن)
                        </li>
                    </ul>
                </div>
            </div>

            <div class="content-card">
                <h2 class="card-title">الأبحاث المنشورة</h2>
                <div class="card-content">
                    <ul class="highlight-list">
                        <li>
