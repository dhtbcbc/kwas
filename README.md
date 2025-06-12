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
            background: linear-gradient(135deg, #0a0a0a 0%, #1a1a2e 50%, #16213e 100%);
            color: #ffffff;
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(10, 10, 10, 0.95);
            backdrop-filter: blur(20px);
            z-index: 1000;
            padding: 1rem 0;
            transition: all 0.3s ease;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding-right: 1rem; /* Adjust padding for mobile */
            padding-left: 1rem;
        }

        nav .nav-brand {
            font-size: 1.5rem;
            color: #ff6b35;
            font-weight: bold;
            text-decoration: none;
        }

        nav ul {
            display: flex;
            justify-content: center;
            list-style: none;
            gap: 2rem;
        }

        nav a {
            color: #fff;
            text-decoration: none;
            padding: 0.5rem 1rem;
            border-radius: 25px;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        nav a:hover {
            background: linear-gradient(45deg, #ff6b35, #f7931e);
            transform: translateY(-2px);
            box-shadow: 0 10px 20px rgba(255, 107, 53, 0.3);
        }

        /* Hamburger Menu Icon */
        .hamburger-menu {
            display: none; /* Hidden by default, shown on small screens */
            flex-direction: column;
            cursor: pointer;
            width: 30px;
            height: 20px;
            justify-content: space-between;
            position: relative;
            z-index: 1001;
        }

        .hamburger-menu span {
            display: block;
            width: 100%;
            height: 3px;
            background: #fff;
            border-radius: 5px;
            transition: all 0.3s ease;
        }

        .hamburger-menu.active span:nth-child(1) {
            transform: translateY(8px) rotate(45deg);
        }

        .hamburger-menu.active span:nth-child(2) {
            opacity: 0;
        }

        .hamburger-menu.active span:nth-child(3) {
            transform: translateY(-8px) rotate(-45deg);
        }

        /* Mobile Nav Menu */
        .nav-menu-mobile {
            display: none; /* Hidden by default */
            position: fixed;
            top: 0;
            right: 0;
            width: 70%; /* Adjust as needed */
            height: 100%;
            background: rgba(10, 10, 10, 0.98);
            backdrop-filter: blur(20px);
            flex-direction: column;
            align-items: center;
            justify-content: center;
            gap: 2rem;
            transform: translateX(100%);
            transition: transform 0.3s ease-in-out;
            padding-top: 60px; /* To avoid overlapping with fixed nav */
        }

        .nav-menu-mobile.active {
            transform: translateX(0);
            display: flex;
        }

        .nav-menu-mobile li {
            width: 100%;
            text-align: center;
        }

        .nav-menu-mobile a {
            padding: 1rem 0;
            display: block;
            width: 80%;
            margin: 0 auto;
            border-radius: 10px;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            background: radial-gradient(circle at 30% 50%, rgba(255, 107, 53, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 70% 30%, rgba(247, 147, 30, 0.1) 0%, transparent 50%);
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 1000"><circle cx="500" cy="200" r="2" fill="%23ff6b35" opacity="0.3"><animate attributeName="opacity" values="0.3;1;0.3" dur="3s" repeatCount="indefinite"/></circle><circle cx="300" cy="400" r="1.5" fill="%23f7931e" opacity="0.4"><animate attributeName="opacity" values="0.4;0.8;0.4" dur="2s" repeatCount="indefinite"/></circle><circle cx="700" cy="600" r="2.5" fill="%23ff6b35" opacity="0.2"><animate attributeName="opacity" values="0.2;0.6;0.2" dur="4s" repeatCount="indefinite"/></circle></svg>') no-repeat center;
            background-size: cover;
        }

        .hero-content {
            text-align: center;
            z-index: 2;
            max-width: 800px;
            padding: 0 2rem;
            animation: fadeInUp 1s ease-out;
        }

        .hero h1 {
            font-size: 4rem;
            font-weight: 700;
            margin-bottom: 1rem;
            background: linear-gradient(45deg, #ff6b35, #f7931e, #ffffff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: glow 2s ease-in-out infinite alternate;
        }

        .hero-subtitle {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            color: #cccccc;
            font-weight: 300;
        }

        .hero-quote {
            font-size: 1.3rem;
            font-style: italic;
            color: #ff6b35;
            margin-bottom: 2rem;
            padding: 1rem;
            border-left: 4px solid #ff6b35;
            background: rgba(255, 107, 53, 0.1);
            border-radius: 0 10px 10px 0;
        }

        /* Sections */
        section {
            padding: 5rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 3rem;
            position: relative;
            color: #ff6b35;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 3px;
            background: linear-gradient(45deg, #ff6b35, #f7931e);
            border-radius: 2px;
        }

        /* About Section */
        .about-content {
            display: grid;
            grid-template-columns: 1fr 2fr;
            gap: 3rem;
            align-items: center;
        }

        .about-image {
            text-align: center;
        }

        .profile-pic {
            width: 300px;
            height: 300px;
            border-radius: 50%;
            background: linear-gradient(45deg, #ff6b35, #f7931e);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            color: white;
            margin: 0 auto;
            box-shadow: 0 20px 40px rgba(255, 107, 53, 0.3);
            transition: transform 0.3s ease;
        }

        .profile-pic:hover {
            transform: scale(1.05) rotate(5deg);
        }

        .about-text {
            font-size: 1.1rem;
            line-height: 1.8;
            color: #e0e0e0;
        }

        .about-text p {
            margin-bottom: 1.5rem;
        }

        /* Cards */
        .cards-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .card {
            background: linear-gradient(135deg, rgba(255, 107, 53, 0.1) 0%, rgba(26, 26, 46, 0.8) 100%);
            border: 1px solid rgba(255, 107, 53, 0.3);
            border-radius: 15px;
            padding: 2rem;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
            position: relative;
            overflow: hidden;
        }

        .card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 107, 53, 0.1), transparent);
            transition: left 0.5s ease;
        }

        .card:hover::before {
            left: 100%;
        }

        .card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(255, 107, 53, 0.2);
            border-color: #ff6b35;
        }

        .card h3 {
            color: #ff6b35;
            margin-bottom: 1rem;
            font-size: 1.3rem;
        }

        .card p,
        .card li {
            color: #cccccc;
            margin-bottom: 0.5rem;
        }

        .card ul {
            list-style: none;
            padding-right: 1rem;
        }

        .card li::before {
            content: '▶';
            color: #ff6b35;
            margin-left: 0.5rem;
        }

        /* Skills */
        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }

        .skill-category {
            background: rgba(26, 26, 46, 0.6);
            border-radius: 15px;
            padding: 2rem;
            border: 1px solid rgba(255, 107, 53, 0.2);
        }

        .skill-category h3 {
            color: #ff6b35;
            margin-bottom: 1rem;
            text-align: center;
        }

        .skill-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1rem;
            padding: 0.5rem;
            background: rgba(255, 107, 53, 0.1);
            border-radius: 8px;
        }

        /* Contact Form */
        .contact-form {
            max-width: 600px;
            margin: 0 auto;
            background: rgba(26, 26, 46, 0.6);
            padding: 2rem;
            border-radius: 15px;
            border: 1px solid rgba(255, 107, 53, 0.3);
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            color: #ff6b35;
            margin-bottom: 0.5rem;
            font-weight: 500;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 1rem;
            background: rgba(255, 255, 255, 0.1);
            border: 1px solid rgba(255, 107, 53, 0.3);
            border-radius: 8px;
            color: white;
            font-size: 1rem;
            transition: all 0.3s ease;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #ff6b35;
            box-shadow: 0 0 10px rgba(255, 107, 53, 0.3);
        }

        .submit-btn {
            background: linear-gradient(45deg, #ff6b35, #f7931e);
            color: white;
            border: none;
            padding: 1rem 2rem;
            border-radius: 25px;
            font-size: 1.1rem;
            cursor: pointer;
            transition: all 0.3s ease;
            width: 100%;
        }

        .submit-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 20px rgba(255, 107, 53, 0.4);
        }

        /* Social Links */
        .social-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-top: 2rem;
        }

        .social-link {
            display: inline-block;
            padding: 1rem;
            background: rgba(255, 107, 53, 0.1);
            border: 2px solid rgba(255, 107, 53, 0.3);
            border-radius: 50%;
            color: #ff6b35;
            text-decoration: none;
            transition: all 0.3s ease;
            font-size: 1.5rem;
            width: 60px;
            height: 60px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .social-link:hover {
            background: #ff6b35;
            color: white;
            transform: scale(1.1) rotate(10deg);
        }

        /* Fun Facts */
        .fun-facts {
            background: rgba(26, 26, 46, 0.4);
            border-radius: 15px;
            padding: 2rem;
            margin-top: 2rem;
            border: 1px solid rgba(255, 107, 53, 0.2);
        }

        .fun-facts h3 {
            color: #ff6b35;
            text-align: center;
            margin-bottom: 1.5rem;
        }

        .fun-facts ul {
            list-style: none;
            text-align: center;
        }

        .fun-facts li {
            margin-bottom: 1rem;
            font-size: 1.1rem;
            color: #e0e0e0;
        }

        .fun-facts li::before {
            content: '🎯';
            margin-left: 0.5rem;
        }

        /* Animations */
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

        @keyframes glow {
            from {
                text-shadow: 0 0 10px rgba(255, 107, 53, 0.5);
            }

            to {
                text-shadow: 0 0 20px rgba(255, 107, 53, 0.8), 0 0 30px rgba(247, 147, 30, 0.6);
            }
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }

            .hero-subtitle {
                font-size: 1.2rem;
            }

            .about-content {
                grid-template-columns: 1fr;
                text-align: center;
            }

            /* Show hamburger on mobile, hide desktop nav */
            nav ul {
                display: none;
            }

            .hamburger-menu {
                display: flex;
            }
        }


        /* Smooth Scroll */
        html {
            scroll-behavior: smooth;
        }

        /* Scroll Reveal Animation */
        .reveal {
            opacity: 0;
            transform: translateY(50px);
            transition: all 0.6s ease;
        }

        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* Particle Background Effect */
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
            width: 2px;
            height: 2px;
            background: #ff6b35;
            border-radius: 50%;
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%,
            100% {
                transform: translateY(0px) rotate(0deg);
            }

            50% {
                transform: translateY(-20px) rotate(180deg);
            }
        }

        /* Gradient Text Effect */
        .gradient-text {
            background: linear-gradient(45deg, #ff6b35, #f7931e, #ffffff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
    </style>
</head>

<body>
    <div class="particles" id="particles"></div>

    <nav>
        <a href="#home" class="nav-brand">وسام سعد</a>
        <ul id="desktop-nav">
            <li><a href="#home">الرئيسية</a></li>
            <li><a href="#about">من أنا</a></li>
            <li><a href="#education">التعليم</a></li>
            <li><a href="#experience">الخبرات</a></li>
            <li><a href="#research">الأبحاث</a></li>
            <li id="projects-link"><a href="#projects">المشاريع</a></li>
            <li><a href="#skills">المهارات</a></li>
            <li id="contact-link"><a href="#contact">التواصل</a></li>
        </ul>
        <div class="hamburger-menu" id="hamburger-menu">
            <span></span>
            <span></span>
            <span></span>
        </div>
        <ul class="nav-menu-mobile" id="mobile-nav">
            <li><a href="#home">الرئيسية</a></li>
            <li><a href="#about">من أنا</a></li>
            <li><a href="#education">التعليم</a></li>
            <li><a href="#experience">الخبرات</a></li>
            <li><a href="#research">الأبحاث</a></li>
            <li><a href="#projects">المشاريع</a></li>
            <li><a href="#skills">المهارات</a></li>
            <li><a href="#contact">التواصل</a></li>
        </ul>
    </nav>

    <section id="home" class="hero">
        <div class="hero-content">
            <h1>وسام سعد</h1>
            <div class="hero-subtitle">باحث في الذكاء الاصطناعي • صانع للمستقبل • متحدث في المؤتمرات الدولية</div>
            <div class="hero-quote">
                "الآلة تتعلم... لكني أنا من علمها أن تفكر."
            </div>
            <div style="margin-top: 2rem;">
                <span style="background: rgba(255, 107, 53, 0.2); padding: 0.5rem 1rem; border-radius: 20px; margin: 0 0.5rem;">خبير تعلم عميق</span>
                <span style="background: rgba(247, 147, 30, 0.2); padding: 0.5rem 1rem; border-radius: 20px; margin: 0 0.5rem;">مهندس بيانات</span>
                <span style="background: rgba(255, 107, 53, 0.2); padding: 0.5rem 1rem; border-radius: 20px; margin: 0 0.5rem;">باحث ذكاء اصطناعي</span>
            </div>
        </div>
    </section>

    <section id="about" class="reveal">
        <h2 class="section-title">من أنا</h2>
        <div class="about-content">
            <div class="about-image">
                <div class="profile-pic">وس</div>
            </div>
            <div class="about-text">
                <p>مرحباً، أنا وسام سعد، باحث متخصص في مجال الذكاء الاصطناعي والتعلم العميق. بدأت رحلتي في عالم التكنولوجيا منذ الصغر، حيث كنت مفتوناً بقدرة الحاسوب على حل المشاكل المعقدة وتقليد الذكاء البشري.</p>
                <p>درست هندسة الحاسوب في جامعة بغداد، حيث تميزت في مجال الخوارزميات والبرمجة. لكن شغفي الحقيقي كان في فهم كيفية تعلم الآلات، مما دفعني لمواصلة دراستي العليا في معهد ماساتشوستس للتكنولوجيا (MIT) حيث حصلت على درجة الماجستير في الذكاء الاصطناعي.</p>
                <p>خلال مسيرتي الأكاديمية والمهنية، تخصصت في تطوير الشبكات العصبية المتقدمة، والتعلم المعزز، ومعالجة اللغات الطبيعية. شاركت في أبحاث متطورة تهدف إلى جعل الذكاء الاصطناعي أكثر فهماً وتفاعلاً مع البشر، خاصة في مجال اللغة العربية.</p>
                <p>أؤمن بأن الذكاء الاصطناعي يجب أن يخدم الإنسانية، وأن التطوير التقني يجب أن يتماشى مع القيم الأخلاقية. لذلك أركز في أبحاثي على تطوير أنظمة ذكية مسؤولة وقابلة للتفسير.</p>
            </div>
        </div>
    </section>

    <section id="education" class="reveal">
        <h2 class="section-title">الشهادات العلمية</h2>
        <div class="cards-grid">
            <div class="card">
                <h3>🎓 ماجستير في الذكاء الاصطناعي</h3>
                <p><strong>معهد ماساتشوستس للتكنولوجيا (MIT)</strong></p>
                <p>2020 - 2022</p>
                <p>التركيز على التعلم العميق والشبكات العصبية المتقدمة</p>
                <p>أطروحة التخرج: "تطوير نماذج لغوية عربية متقدمة باستخدام التعلم المعزز"</p>
                <p><strong>المعدل:</strong> 3.9/4.0</p>
            </div>
            <div class="card">
                <h3>🎓 بكالوريوس في هندسة الحاسوب</h3>
                <p><strong>جامعة بغداد - كلية الهندسة</strong></p>
                <p>2015 - 2019</p>
                <p>التركيز على هندسة البرمجيات والخوارزميات</p>
                <p>مشروع التخرج: "نظام ذكي لإدارة حركة المرور باستخدام الرؤية الحاسوبية"</p>
                <p><strong>المعدل:</strong> امتياز مع مرتبة الشرف الأولى</p>
            </div>
        </div>
    </section>

    <section id="experience" class="reveal">
        <h2 class="section-title">الخبرات العملية</h2>
        <div class="cards-grid">
            <div class="card">
                <h3>🚀 مهندس تعلم آلي أول - Google DeepMind</h3>
                <p><strong>2023 - حتى الآن</strong></p>
                <p>تطوير نماذج ذكاء اصطناعي متقدمة للتطبيقات الطبية والعلمية</p>
                <ul>
                    <li>قيادة فريق من 8 مهندسين في مشاريع التعلم العميق</li>
                    <li>تطوير خوارزميات تحليل الصور الطبية بدقة 98.5%</li>
                    <li>نشر 12 بحث علمي في مجلات محكمة</li>
                </ul>
            </div>
            <div class="card">
                <h3>🔬 متدرب بحثي متقدم - OpenAI</h3>
                <p><strong>2022 - 2023</strong></p>
                <p>العمل على تطوير نماذج اللغة الكبيرة وتحسين قدراتها في اللغة العربية</p>
                <ul>
                    <li>تطوير تقنيات تحسين أداء النماذج اللغوية</li>
                    <li>العمل على مشروع GPT العربي</li>
                    <li>تطوير معايير أخلاقية للذكاء الاصطناعي</li>
                </ul>
            </div>
            <div class="card">
                <h3>💡 مستشار تقني - شركات التكنولوجيا الناشئة</h3>
                <p><strong>2021 - حتى الآن</strong></p>
                <p>تقديم الاستشارات التقنية لأكثر من 15 شركة ناشئة في مجال الذكاء الاصطناعي</p>
                <ul>
                    <li>مساعدة الشركات في تطوير استراتيجيات الذكاء الاصطناعي</li>
                    <li>تصميم أنظمة تعلم آلي مخصصة</li>
                    <li>تدريب الفرق التقنية على أحدث التقنيات</li>
                </ul>
            </div>
        </div>
    </section>

    <section id="research" class="reveal">
        <h2 class="section-title">الأبحاث والمنشورات</h2>
        <div class="cards-grid">
            <div class="card">
                <h3>📚 "تطوير شبكات عصبية قابلة للتكيف في تحليل الصور الطبية"</h3>
                <p><strong>مجلة Nature Machine Intelligence - 2024</strong></p>
                <p>بحث رائد في تطوير خوارزميات تشخيص طبي بدقة عالية باستخدام التعلم العميق</p>
                <p><strong>الاستشهادات:</strong> 287 | <strong>Impact Factor:</strong> 8.9</p>
            </div>
            <div class="card">
                <h3>📚 "نحو فهم عاطفي أعمق للغة العربية باستخدام BERT العربي"</h3>
                <p><strong>مؤتمر ACL الدولي - 2023</strong></p>
                <p>تطوير نموذج متطور لفهم المشاعر والعواطف في النصوص العربية</p>
                <p><strong>الاستشهادات:</strong> 156 | <strong>معدل القبول:</strong> 15%</p>
            </div>
            <div class="card">
                <h3>📚 "أنظمة تعلم معزز لقيادة المركبات ذاتية التحكم"</h3>
                <p><strong>مجلة IEEE Transactions on AI - 2023</strong></p>
                <p>بحث متقدم في تطوير خوارزميات القيادة الذاتية باستخدام التعلم المعزز</p>
                <p><strong>الاستشهادات:</strong> 203 | <strong>Impact Factor:</strong> 7.2</p>
            </div>
            <div class="card">
                <h3>📚 "الذكاء الاصطناعي الأخلاقي: إطار عمل للتطوير المسؤول"</h3>
                <p><strong>مجلة AI Ethics - 2024</strong></p>
                <p>وضع معايير أخلاقية لتطوير أنظمة الذكاء الاصطناعي في المنطقة العربية</p>
                <p><strong>الاستشهادات:</strong> 124 | <strong>Impact Factor:</strong> 6.8</p>
            </div>
        </div>
    </section>

    <section id="projects" class="reveal">
        <h2 class="section-title">المشاريع المتميزة</h2>
        <div class="cards-grid">
            <div class="card">
                <h3>🚁 نظام توجيه الطائرات بدون طيار الذكي</h3>
                <p>تطوير نظام متقدم لتوجيه الطائرات بدون طيار باستخدام التعلم المعزز والرؤية الحاسوبية</p>
                <ul>
                    <li>دقة الملاحة: 99.7%</li>
                    <li>قدرة على التعامل مع الظروف الجوية المختلفة</li>
                    <li>تجنب العوائق بذكاء</li>
                    <li>استخدام في عمليات الإنقاذ والمراقبة</li>
                </ul>
                <p><strong>التقنيات:</strong> PyTorch, Computer Vision, Reinforcement Learning</p>
            </div>
            <div class="card">
                <h3>🔤 معالج اللغة العربية الذكي</h3>
                <p>أداة متطورة لمعالجة وفهم اللغة العربية وتحليل المشاعر بدقة عالية</p>
                <ul>
                    <li>تحليل المشاعر بدقة 96.3%</li>
                    <li>دعم جميع اللهجات العربية</li>
                    <li>تصحيح إملائي ونحوي ذكي</li>
                    <li>ترجمة متقدمة إلى 15 لغة</li>
                </ul>
                <p><strong>التقنيات:</strong> BERT, Transformers, NLP, TensorFlow</p>
            </div>
            <div class="card">
                <h3>🤝 مترجم لغة الإشارة الفوري</h3>
                <p>نظام ثوري لترجمة لغة الإشارة إلى نص ومن النص إلى لغة الإشارة في الوقت الفعلي</p>
                <ul>
                    <li>دقة الترجمة: 94.8%</li>
                    <li>دعم لغة الإشارة العربية والإنجليزية</li>
                    <li>واجهة سهلة الاستخدام</li>
                    <li>يساعد أكثر من 10,000 شخص من ذوي الاحتياجات الخاصة</li>
                </ul>
                <p><strong>التقنيات:</strong> OpenCV, MediaPipe, Deep Learning, React</p>
            </div>
            <div class="card">
                <h3>🧠 منصة التعلم الذكي التفاعلية</h3>
                <p>منصة تعليمية تستخدم الذكاء الاصطناعي لتخصيص المحتوى التعليمي لكل طالب</p>
                <ul>
                    <li>تخصيص المسار التعليمي حسب قدرات الطالب</li>
                    <li>تحليل نقاط القوة والضعف</li>
                    <li>اقتراح المحتوى المناسب</li>
                    <li>تحسين النتائج بنسبة 87%</li>
                </ul>
                <p><strong>التقنيات:</strong> Machine Learning, Python, React, Node.js</p>
            </div>
        </div>
    </section>

    <section id="skills" class="reveal">
        <h2 class="section-title">المهارات التقنية</h2>
        <div class="skills-container">
            <div class="skill-category">
                <h3>💻 لغات البرمجة</h3>
                <div class="skill-item">
                    <span>Python</span>
                    <span style="color: #ff6b35;">خبير</span>
                </div>
                <div class="skill-item">
                    <span>JavaScript/TypeScript</span>
                    <span style="color: #ff6b35;">متقدم</span>
                </div>
                <div class="skill-item">
                    <span>C++</span>
                    <span style="color: #f7931e;">متقدم</span>
                </div>
                <div class="skill-item">
                    <span>R</span>
                    <span style="color: #f7931e;">متوسط</span>
                </div>
                <div class="skill-item">
                    <span>SQL</span>
                    <span style="color: #ff6b35;">متقدم</span>
                </div>
            </div>

            <div class="skill-category">
                <h3>🤖 أطر العمل والمكتبات</h3>
                <div class="skill-item">
                    <span>TensorFlow</span>
                    <span style="color: #ff6b35;">خبير</span>
                </div>
                <div class="skill-item">
                    <span>PyTorch</span>
                    <span style="color: #ff6b35;">خبير</span>
                </div>
                <div class="skill-item">
                    <span>Keras</span>
                    <span style="color: #ff6b35;">متقدم</span>
                </div>
                <div class="skill-item">
                    <span>Scikit-learn</span>
                    <span style="color: #f7931e;">متقدم</span>
                </div>
                <div class="skill-item">
                    <span>OpenCV</span>
                    <span style="color: #ff6b35;">متقدم</span>
                </div>
            </div>

            <div class="skill-category">
                <h3>☁️ التقنيات السحابية</h3>
                <div class="skill-item">
                    <span>AWS</span>
                    <span style="color: #ff6b35;">متقدم</span>
                </div>
                <div class="skill-item">
                    <span>Google Cloud Platform</span>
                    <span style="color: #ff6b35;">متقدم</span>
                </div>
                <div class="skill-item">
                    <span>Microsoft Azure</span>
                    <span style="color: #f7931e;">متوسط</span>
                </div>
                <div class="skill-item">
                    <span>Docker</span>
                    <span style="color: #ff6b35;">متقدم</span>
                </div>
                <div class="skill-item">
                    <span>Kubernetes</span>
                    <span style="color: #f7931e;">متوسط</span>
                </div>
            </div>

            <div class="skill-category">
                <h3>🎯 التخصصات</h3>
                <div class="skill-item">
                    <span>التعلم العميق</span>
                    <span style="color: #ff6b35;">خبير</span>
                </div>
                <div class="skill-item">
                    <span>معالجة اللغات الطبيعية</span>
                    <span style="color: #ff6b35;">خبير</span>
                </div>
                <div class="skill-item">
                    <span>الرؤية الحاسوبية</span>
                    <span style="color: #ff6b35;">متقدم</span>
                </div>
                <div class="skill-item">
                    <span>التعلم المعزز</span>
                    <span style="color: #ff6b35;">متقدم</span>
                </div>
                <div class="skill-item">
                    <span>تحليل البيانات</span>
                    <span style="color: #f7931e;">متقدم</span>
                </div>
            </div>
        </div>

        <div class="fun-facts">
            <h3>🎈 معلومات ممتعة عني</h3>
            <ul>
                <li>أتحدث 3 لغات بطلاقة: العربية، الإنجليزية، وبعض اليابانية</li>
                <li>أحب لعب الشطرنج وأدرس الفيزياء النظرية في وقت فراغي</li>
                <li>بنيت نظام ذكاء اصطناعي للعب FIFA ضدي... وهزمني!</li>
                <li>أشارك في مسابقات الروبوتات العالمية وحققت المركز الثاني في 2023</li>
                <li>أكتب الشعر باللغة العربية وأستخدم الذكاء الاصطناعي لتحليل القوافي</li>
                <li>أحب الطبخ وأطبق مبادئ خوارزميات التحسين في تحضير الوصفات</li>
            </ul>
        </div>
    </section>

    <section id="contact" class="reveal">
        <h2 class="section-title">تواصل معي</h2>
        <div class="contact-form">
            <form>
                <div class="form-group">
                    <label for="name">الاسم الكامل</label>
                    <input type="text" id="name" name="name" required>
                </div>
                <div class="form-group">
                    <label for="email">البريد الإلكتروني</label>
                    <input type="email" id="email" name="email" required>
                </div>
                <div class="form-group">
                    <label for="subject">الموضوع</label>
                    <input type="text" id="subject" name="subject" required>
                </div>
                <div class="form-group">
                    <label for="message">الرسالة</label>
                    <textarea id="message" name="message" rows="5" required></textarea>
                </div>
                <button type="submit" class="submit-btn">إرسال الرسالة</button>
            </form>
        </div>

        <div class="social-links">
            <a href="mailto:wissam.ai.master@gmail.com" class="social-link" title="البريد الإلكتروني">📧</a>
            <a href="https://t.me/ws_12fg" class="social-link" title="تليغرام">📱</a>
            <a href="#" class="social-link" title="لينكدإن">💼</a>
            <a href="#" class="social-link" title="تويتر">🐦</a>
            <a href="#" class="social-link" title="جيت هاب">💻</a>
            <a href="#" class="social-link" title="جوجل سكولار">🎓</a>
        </div>

        <div style="text-align: center; margin-top: 3rem; padding: 2rem; background: rgba(26, 26, 46, 0.4); border-radius: 15px; border: 1px solid rgba(255, 107, 53, 0.2);">
            <h3 style="color: #ff6b35; margin-bottom: 1rem;">معلومات التواصل المباشر</h3>
            <p style="margin-bottom: 0.5rem;"><strong>البريد الإلكتروني:</strong> wissam.ai.master@gmail.com</p>
            <p style="margin-bottom: 0.5rem;"><strong>تليغرام:</strong> @ws_12fg</p>
            <p style="margin-bottom: 0.5rem;"><strong>الموقع:</strong> بغداد، العراق</p>
            <p style="color: #cccccc; margin-top: 1rem;">
                متاح للاستشارات التقنية، المحاضرات، والتعاون في مشاريع الذكاء الاصطناعي
            </p>
        </div>
    </section>

    <footer style="background: rgba(10, 10, 10, 0.9); padding: 2rem; text-align: center; border-top: 1px solid rgba(255, 107, 53, 0.3);">
        <p>&copy; 2024 وسام سعد - جميع الحقوق محفوظة</p>
        <p style="color: #cccccc; margin-top: 0.5rem;">
            "في عالم يتطور بسرعة الضوء، الذكاء الاصطناعي هو مفتاح المستقبل"
        </p>
    </footer>

    <script>
        // Smooth scrolling for navigation links
        document.querySelectorAll('nav a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
                // Close mobile menu after clicking a link
                if (document.getElementById('mobile-nav').classList.contains('active')) {
                    document.getElementById('mobile-nav').classList.remove('active');
                    document.getElementById('hamburger-menu').classList.remove('active');
                }
            });
        });

        // Reveal animation on scroll
        window.addEventListener('scroll', reveal);

        function reveal() {
            const reveals = document.querySelectorAll('.reveal');
            for (let i = 0; i < reveals.length; i++) {
                const windowHeight = window.innerHeight;
                const elementTop = reveals[i].getBoundingClientRect().top;
                const elementVisible = 150;

                if (elementTop < windowHeight - elementVisible) {
                    reveals[i].classList.add('active');
                }
            }
        }

        // Generate floating particles
        function createParticles() {
            const particlesContainer = document.getElementById('particles');
            for (let i = 0; i < 50; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.top = Math.random() * 100 + '%';
                particle.style.animationDelay = Math.random() * 6 + 's';
                particle.style.animationDuration = (Math.random() * 3 + 3) + 's';
                particlesContainer.appendChild(particle);
            }
        }

        // Initialize particles
        createParticles();

        // Form submission
        document.querySelector('form').addEventListener('submit', function (e) {
            e.preventDefault();
            alert('شكراً لتواصلك معي! سأرد عليك في أقرب وقت ممكن.');
            this.reset(); // Reset form fields
        });

        // Navigation background change on scroll
        window.addEventListener('scroll', function () {
            const nav = document.querySelector('nav');
            if (window.scrollY > 100) {
                nav.style.background = 'rgba(10, 10, 10, 0.98)';
            } else {
                nav.style.background = 'rgba(10, 10, 10, 0.95)';
            }
        });

        // Typing effect for hero subtitle
        const subtitle = document.querySelector('.hero-subtitle');
        const text = subtitle.textContent;
        subtitle.textContent = '';
        let i = 0;

        function typeWriter() {
            if (i < text.length) {
                subtitle.textContent += text.charAt(i);
                i++;
                setTimeout(typeWriter, 50);
            }
        }

        setTimeout(typeWriter, 1000);

        // Add hover effects to cards
        document.querySelectorAll('.card').forEach(card => {
            card.addEventListener('mouseenter', function () {
                this.style.transform = 'translateY(-15px) scale(1.02)';
            });

            card.addEventListener('mouseleave', function () {
                this.style.transform = 'translateY(0) scale(1)';
            });
        });

        // Parallax effect for hero section
        window.addEventListener('scroll', function () {
            const scrolled = window.pageYOffset;
            const rate = scrolled * -0.5;
            const hero = document.querySelector('.hero');
            hero.style.transform = `translateY(${rate}px)`;
        });

        // Initialize reveal animation
        reveal();

        // Hamburger Menu functionality
        const hamburgerMenu = document.getElementById('hamburger-menu');
        const mobileNav = document.getElementById('mobile-nav');

        hamburgerMenu.addEventListener('click', function () {
            hamburgerMenu.classList.toggle('active');
            mobileNav.classList.toggle('active');
        });

        // Hide/Show Projects and Contact links on scroll for desktop navigation
        const projectsLink = document.getElementById('projects-link');
        const contactLink = document.getElementById('contact-link');

        window.addEventListener('scroll', function() {
            const projectsSection = document.getElementById('projects');
            const contactSection = document.getElementById('contact');
            const scrollPosition = window.scrollY || document.documentElement.scrollTop;
            const windowHeight = window.innerHeight;

            // Check if projects section is visible
            const projectsRect = projectsSection.getBoundingClientRect();
            const isProjectsVisible = (projectsRect.top < windowHeight && projectsRect.bottom >= 0);

            // Check if contact section is visible
            const contactRect = contactSection.getBoundingClientRect();
            const isContactVisible = (contactRect.top < windowHeight && contactRect.bottom >= 0);

            // If projects or contact section are on screen, show their links, otherwise hide
            if (isProjectsVisible || isContactVisible || scrollPosition === 0) {
                projectsLink.style.display = 'list-item';
                contactLink.style.display = 'list-item';
                projectsLink.style.opacity = '1';
                contactLink.style.opacity = '1';
                projectsLink.style.transform = 'translateY(0)';
                contactLink.style.transform = 'translateY(0)';
            } else {
                projectsLink.style.display = 'none'; // Hide when not relevant
                contactLink.style.display = 'none'; // Hide when not relevant
                // projectsLink.style.opacity = '0'; // You can use opacity for a fading effect
                // contactLink.style.opacity = '0';
                // projectsLink.style.transform = 'translateY(20px)'; // For a slight slide effect
                // contactLink.style.transform = 'translateY(20px)';
            }
        });
        // Initial check on load
        window.dispatchEvent(new Event('scroll'));
    </script>
</body>

</html>
