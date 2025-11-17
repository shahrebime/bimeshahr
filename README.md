<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BimePlus | بیمه پلاس</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        :root {
            --primary: #6C63FF;
            --secondary: #4A44C6;
            --accent: #FF6584;
            --dark: #2A2D3E;
            --light: #F8F9FF;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Vazirmatn', 'Segoe UI', Tahoma, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, var(--dark) 0%, #1A1C2E 100%);
            color: var(--light);
            min-height: 100vh;
            overflow-x: hidden;
        }
        
        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* نوار ناوبری */
        .navbar {
            background: rgba(42, 45, 62, 0.95);
            backdrop-filter: blur(20px);
            padding: 20px 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            border-bottom: 1px solid rgba(255,255,255,0.1);
        }
        
        .nav-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            font-size: 2.2em;
            font-weight: bold;
            background: linear-gradient(45deg, var(--primary), var(--accent));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .nav-links {
            display: flex;
            gap: 30px;
        }
        
        .nav-links a {
            color: var(--light);
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s;
            padding: 10px 20px;
            border-radius: 25px;
        }
        
        .nav-links a:hover, .nav-links a.active {
            background: var(--primary);
            color: white;
        }
        
        /* هیرو سکشن */
        .hero {
            padding: 180px 0 100px;
            text-align: center;
            position: relative;
        }
        
        .hero-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at top right, var(--primary) 0%, transparent 50%);
            opacity: 0.1;
            z-index: -1;
        }
        
        .hero h1 {
            font-size: 4em;
            margin-bottom: 20px;
            background: linear-gradient(45deg, var(--light), var(--primary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .hero p {
            font-size: 1.3em;
            margin-bottom: 40px;
            opacity: 0.9;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }
        
        /* خدمات */
        .services {
            padding: 80px 0;
        }
        
        .section-title {
            text-align: center;
            font-size: 2.5em;
            margin-bottom: 50px;
            color: var(--primary);
        }
        
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
        }
        
        .service-card {
            background: rgba(255,255,255,0.05);
            border-radius: 20px;
            padding: 40px 30px;
            text-align: center;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255,255,255,0.1);
            transition: all 0.3s;
            position: relative;
            overflow: hidden;
        }
        
        .service-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 4px;
            background: linear-gradient(45deg, var(--primary), var(--accent));
        }
        
        .service-card:hover {
            transform: translateY(-10px);
            background: rgba(255,255,255,0.08);
        }
        
        .service-icon {
            width: 80px;
            height: 80px;
            background: linear-gradient(45deg, var(--primary), var(--secondary));
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px;
            font-size: 2em;
        }
        
        .service-card h3 {
            font-size: 1.5em;
            margin-bottom: 15px;
            color: var(--primary);
        }
        
        .price {
            font-size: 2em;
            font-weight: bold;
            color: var(--accent);
            margin: 20px 0;
        }
        
        /* دکمه‌ها */
        .btn {
            background: linear-gradient(45deg, var(--primary), var(--secondary));
            color: white;
            padding: 15px 35px;
            border: none;
            border-radius: 30px;
            font-size: 1.1em;
            font-weight: 600;
            cursor: pointer;
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 10px;
            transition: all 0.3s;
            margin: 5px;
        }
        
        .btn:hover {
            transform: scale(1.05);
            box-shadow: 0 10px 25px rgba(108, 99, 255, 0.3);
        }
        
        .btn-outline {
            background: transparent;
            border: 2px solid var(--primary);
            color: var(--primary);
        }
        
        .btn-outline:hover {
            background: var(--primary);
            color: white;
        }
        
        /* فوتر */
        footer {
            background: rgba(26, 28, 46, 0.95);
            padding: 60px 0 30px;
            margin-top: 80px;
            border-top: 1px solid rgba(255,255,255,0.1);
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }
        
        .footer-section h3 {
            color: var(--primary);
            margin-bottom: 20px;
            font-size: 1.3em;
        }
        
        .footer-section p, .footer-section a {
            color: rgba(255,255,255,0.7);
            text-decoration: none;
            margin-bottom: 10px;
            display: block;
            transition: color 0.3s;
        }
        
        .footer-section a:hover {
            color: var(--primary);
        }
        
        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }
        
        .social-links a {
            width: 40px;
            height: 40px;
            background: rgba(255,255,255,0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s;
        }
        
        .social-links a:hover {
            background: var(--primary);
            transform: scale(1.1);
        }
        
        .copyright {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid rgba(255,255,255,0.1);
            color: rgba(255,255,255,0.5);
        }
        
        /* انیمیشن‌ها */
        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }
        
        .floating {
            animation: float 3s ease-in-out infinite;
        }
        
        /* رسپانسیو */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }
            
            .hero h1 {
                font-size: 2.5em;
            }
            
            .services-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- نوار ناوبری -->
    <nav class="navbar">
        <div class="container">
            <div class="nav-content">
                <div class="logo">
                    <i class="fas fa-shield-alt"></i>
                    BimePlus
                </div>
                <div class="nav-links">
                    <a href="index.html" class="active"><i class="fas fa-home"></i> خانه</a>
                    <a href="services.html"><i class="fas fa-list"></i> خدمات</a>
                    <a href="prices.html"><i class="fas fa-tags"></i> قیمت‌ها</a>
                    <a href="about.html"><i class="fas fa-info-circle"></i> درباره ما</a>
                    <a href="contact.html"><i class="fas fa-phone"></i> تماس</a>
                </div>
            </div>
        </div>
    </nav>

    <!-- بخش اصلی -->
    <section class="hero">
        <div class="hero-bg"></div>
        <div class="container">
            <h1 class="floating">بیمه پلاس</h1>
            <p>پلتفرم هوشمند بیمه‌ای با بهترین پوشش‌ها و مناسب‌ترین قیمت‌ها</p>
            <div style="margin-top: 40px;">
                <a href="prices.html" class="btn">
                    <i class="fas fa-bolt"></i>
                    مشاهده قیمت‌ها
                </a>
                <a href="about.html" class="btn btn-outline">
                    <i class="fas fa-play-circle"></i>
                    راهنمای استفاده
                </a>
            </div>
        </div>
    </section>

    <!-- خدمات -->
    <section class="services">
        <div class="container">
            <h2 class="section-title">خدمات بیمه‌ای ما</h2>
            <div class="services-grid">
                <div class="service-card">
                    <div class="service-icon">
                        <i class="fas fa-car"></i>
                    </div>
                    <h3>بیمه شخص ثالث</h3>
                    <p>پوشش کامل مسئولیت مدنی در مقابل اشخاص ثالث</p>
                    <div class="price">از ۱,۲۰۰,۰۰۰ تومان</div>
                    <a href="prices.html" class="btn">
                        <i class="fas fa-shopping-cart"></i>
                        خرید آنلاین
                    </a>
                </div>

                <div class="service-card">
                    <div class="service-icon">
                        <i class="fas fa-car-crash"></i>
                    </div>
                    <h3>بیمه بدنه</h3>
                    <p>پوشش کامل خسارات بدنه و تصادفات</p>
                    <div class="price">از ۲,۸۰۰,۰۰۰ تومان</div>
                    <a href="prices.html" class="btn">
                        <i class="fas fa-shopping-cart"></i>
                        خرید آنلاین
                    </a>
                </div>

                <div class="service-card">
                    <div class="service-icon">
                        <i class="fas fa-motorcycle"></i>
                    </div>
                    <h3>بیمه موتورسیکلت</h3>
                    <p>پوشش کامل برای انواع موتورسیکلت</p>
                    <div class="price">از ۵۰۰,۰۰۰ تومان</div>
                    <a href="prices.html" class="btn">
                        <i class="fas fa-shopping-cart"></i>
                        خرید آنلاین
                    </a>
                </div>
            </div>
        </div>
    </section>

    <!-- فوتر -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h3>BimePlus</h3>
                    <p>پلتفرم پیشرو در خدمات بیمه‌ای آنلاین با بیش از ۱۰ سال سابقه درخشان</p>
                    <div class="social-links">
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-telegram"></i></a>
                        <a href="#"><i class="fab fa-whatsapp"></i></a>
                        <a href="#"><i class="fab fa-linkedin"></i></a>
                    </div>
                </div>

                <div class="footer-section">
                    <h3>لینک‌های سریع</h3>
                    <a href="index.html">خانه</a>
                    <a href="services.html">خدمات</a>
                    <a href="prices.html">قیمت‌ها</a>
                    <a href="about.html">درباره ما</a>
                    <a href="contact.html">تماس با ما</a>
                </div>

                <div class="footer-section">
                    <h3>تماس با ما</h3>
                    <p><i class="fas fa-phone"></i> ۰۲۱-۱۲۳۴۵۶۷۸</p>
                    <p><i class="fas fa-envelope"></i> info@bimeplus.com</p>
                    <p><i class="fas fa-map-marker-alt"></i> تهران، میرداماد، برج بیمه</p>
                </div>

                <div class="footer-section">
                    <h3>ساعات کاری</h3>
                    <p>شنبه تا چهارشنبه: ۸:۰۰ - ۱۷:۰۰</p>
                    <p>پنجشنبه: ۸:۰۰ - ۱۴:۰۰</p>
                    <p>جمعه: تعطیل</p>
                </div>
            </div>

            <div class="copyright">
                <p>© ۲۰۲۴ BimePlus. کلیه حقوق محفوظ است.</p>
            </div>
        </div>
    </footer>

    <script>
        // اسکرول نرم برای لینک‌ها
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });

        // افکت اسکرول برای نوار ناوبری
        window.addEventListener('scroll', function() {
            const navbar = document.querySelector('.navbar');
            if (window.scrollY > 100) {
                navbar.style.background = 'rgba(42, 45, 62, 0.98)';
            } else {
                navbar.style.background = 'rgba(42, 45, 62, 0.95)';
            }
        });
    </script>
</body>
</html>
