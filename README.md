#onlyforsamplenotanrealwebsite



<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SB Online Store - Premium Mobile Accessories</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        :root {
            --primary: #6c5ce7;
            --secondary: #a29bfe;
            --accent: #fd79a8;
            --dark: #2d3436;
            --light: #dfe6e9;
            --shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
        }

        body {
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
            color: var(--light);
            min-height: 100vh;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header Styles */
        header {
            padding: 20px 0;
            position: relative;
            z-index: 100;
        }

        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .logo img {
            height: 60px;
            border-radius: 12px;
            box-shadow: var(--shadow);
            transition: transform 0.3s ease;
        }

        .logo img:hover {
            transform: scale(1.05) rotate(2deg);
        }

        .logo-text {
            font-size: 24px;
            font-weight: 700;
            background: linear-gradient(to right, var(--primary), var(--accent));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 5px 15px rgba(108, 92, 231, 0.3);
        }

        /* 3D Text Effect */
        .store-name {
            text-align: center;
            margin: 40px 0;
            perspective: 1000px;
        }

        .store-name h1 {
            font-size: 4.5rem;
            font-weight: 900;
            text-transform: uppercase;
            letter-spacing: 3px;
            color: transparent;
            background: linear-gradient(to right, var(--primary), var(--secondary), var(--accent));
            -webkit-background-clip: text;
            background-clip: text;
            text-shadow: 
                0 1px 0 #ccc, 
                0 2px 0 #c9c9c9, 
                0 3px 0 #bbb, 
                0 4px 0 #b9b9b9, 
                0 5px 0 #aaa, 
                0 6px 1px rgba(0,0,0,.1), 
                0 0 5px rgba(0,0,0,.1), 
                0 1px 3px rgba(0,0,0,.3), 
                0 3px 5px rgba(0,0,0,.2), 
                0 10px 10px rgba(0,0,0,.25), 
                0 20px 20px rgba(0,0,0,.15);
            transform: rotateX(10deg);
            animation: float 3s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: rotateX(10deg) translateY(0); }
            50% { transform: rotateX(10deg) translateY(-10px); }
        }

        /* Featured Product Section */
        .featured-product {
            display: flex;
            justify-content: center;
            margin: 60px 0;
            perspective: 1000px;
        }

        .product-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 30px;
            width: 100%;
            max-width: 800px;
            box-shadow: 
                0 15px 35px rgba(0, 0, 0, 0.5),
                inset 0 1px 0 rgba(255, 255, 255, 0.2);
            border: 1px solid rgba(255, 255, 255, 0.1);
            transform-style: preserve-3d;
            transition: transform 0.5s ease, box-shadow 0.5s ease;
        }

        .product-card:hover {
            transform: translateY(-10px) rotateX(5deg);
            box-shadow: 
                0 25px 50px rgba(0, 0, 0, 0.6),
                inset 0 1px 0 rgba(255, 255, 255, 0.2);
        }

        .product-title {
            font-size: 2rem;
            margin-bottom: 20px;
            text-align: center;
            color: var(--light);
            text-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
        }

        .product-gallery {
            position: relative;
            height: 300px;
            margin-bottom: 25px;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
            transform-style: preserve-3d;
        }

        .gallery-slide {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            opacity: 0;
            transition: opacity 0.8s ease;
            background-size: cover;
            background-position: center;
        }

        .gallery-slide.active {
            opacity: 1;
        }

        .gallery-nav {
            position: absolute;
            bottom: 15px;
            left: 0;
            width: 100%;
            display: flex;
            justify-content: center;
            gap: 10px;
            z-index: 10;
        }

        .nav-dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.5);
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .nav-dot.active {
            background: var(--accent);
            transform: scale(1.2);
        }

        .product-info {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: 25px;
        }

        .product-price {
            font-size: 2.2rem;
            font-weight: 700;
            color: var(--accent);
            text-shadow: 0 2px 10px rgba(253, 121, 168, 0.4);
        }

        .view-product-btn {
            background: linear-gradient(45deg, var(--primary), var(--accent));
            color: white;
            border: none;
            padding: 12px 30px;
            border-radius: 50px;
            font-size: 1.1rem;
            font-weight: 600;
            cursor: pointer;
            box-shadow: 0 5px 15px rgba(108, 92, 231, 0.4);
            transition: all 0.3s ease;
            transform-style: preserve-3d;
            position: relative;
            overflow: hidden;
        }

        .view-product-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: left 0.5s;
        }

        .view-product-btn:hover {
            transform: translateY(-3px) scale(1.05);
            box-shadow: 0 8px 25px rgba(108, 92, 231, 0.6);
        }

        .view-product-btn:hover::before {
            left: 100%;
        }

        /* Footer */
        footer {
            text-align: center;
            padding: 30px 0;
            margin-top: 60px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }

        .social-icons {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 20px 0;
        }

        .social-icon {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.1);
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s ease;
            transform-style: preserve-3d;
        }

        .social-icon:hover {
            transform: translateY(-5px) rotateY(15deg);
            background: var(--primary);
            box-shadow: 0 5px 15px rgba(108, 92, 231, 0.4);
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .store-name h1 {
                font-size: 3rem;
            }
            
            .product-card {
                padding: 20px;
            }
            
            .product-title {
                font-size: 1.5rem;
            }
            
            .product-info {
                flex-direction: column;
                gap: 20px;
            }
            
            .product-price {
                font-size: 1.8rem;
            }
        }

        @media (max-width: 480px) {
            .store-name h1 {
                font-size: 2.2rem;
            }
            
            .logo-text {
                font-size: 18px;
            }
            
            .logo img {
                height: 45px;
            }
        }

        /* Floating elements for 3D effect */
        .floating-element {
            position: absolute;
            width: 100px;
            height: 100px;
            border-radius: 50%;
            background: radial-gradient(circle, var(--primary) 0%, transparent 70%);
            opacity: 0.1;
            z-index: -1;
            animation: float-around 15s infinite linear;
        }

        .floating-element:nth-child(1) {
            top: 10%;
            left: 5%;
            width: 120px;
            height: 120px;
            animation-duration: 20s;
        }

        .floating-element:nth-child(2) {
            top: 60%;
            right: 10%;
            width: 80px;
            height: 80px;
            animation-duration: 25s;
            animation-delay: 2s;
        }

        .floating-element:nth-child(3) {
            bottom: 20%;
            left: 15%;
            width: 60px;
            height: 60px;
            animation-duration: 18s;
            animation-delay: 5s;
        }

        @keyframes float-around {
            0% {
                transform: translate(0, 0) rotate(0deg);
            }
            25% {
                transform: translate(50px, 50px) rotate(90deg);
            }
            50% {
                transform: translate(100px, 0) rotate(180deg);
            }
            75% {
                transform: translate(50px, -50px) rotate(270deg);
            }
            100% {
                transform: translate(0, 0) rotate(360deg);
            }
        }
    </style>
</head>
<body>
    <!-- Floating background elements -->
    <div class="floating-element"></div>
    <div class="floating-element"></div>
    <div class="floating-element"></div>

    <div class="container">
        <header>
            <div class="header-content">
                <div class="logo">
                    <img src="https://i.postimg.cc/Wb3qNcM3/Screenshot-2025-09-28-01-42-30-74.jpg" alt="SB Online Store Logo">
                    <div class="logo-text">SB Online Store</div>
                </div>
            </div>
        </header>

        <section class="store-name">
            <h1>SB Online Store</h1>
        </section>

        <section class="featured-product">
            <div class="product-card">
                <h2 class="product-title">RGB Keyboard with Case for iPad & Other Tablets</h2>
                
                <div class="product-gallery">
                    <div class="gallery-slide active" style="background-image: url('https://i.postimg.cc/8C1SGN6Y/IMG-20250928-014609.jpg')"></div>
                    <div class="gallery-slide" style="background-image: url('https://i.postimg.cc/CKPL6z2T/IMG-20250928-014624.jpg')"></div>
                    <div class="gallery-slide" style="background-image: url('https://i.postimg.cc/wMJqvFj9/IMG-20250928-014632.jpg')"></div>
                    <div class="gallery-slide" style="background-image: url('https://i.postimg.cc/QdSXHFhj/IMG-20250928-014710.jpg')"></div>
                    
                    <div class="gallery-nav">
                        <div class="nav-dot active" data-slide="0"></div>
                        <div class="nav-dot" data-slide="1"></div>
                        <div class="nav-dot" data-slide="2"></div>
                        <div class="nav-dot" data-slide="3"></div>
                    </div>
                </div>
                
                <div class="product-info">
                    <div class="product-price">PKR 4,000</div>
                    <a href="https://www.olx.com.pk/item/rgb-keyboard-with-case-for-apple-i-pad-and-others-tablet-universal-model-iid-1106770669" target="_blank" class="view-product-btn">
                        View Product <i class="fas fa-external-link-alt"></i>
                    </a>
                </div>
            </div>
        </section>
    </div>

    <footer>
        <div class="container">
            <div class="social-icons">
                <a href="#" class="social-icon"><i class="fab fa-facebook-f"></i></a>
                <a href="#" class="social-icon"><i class="fab fa-instagram"></i></a>
                <a href="#" class="social-icon"><i class="fab fa-twitter"></i></a>
                <a href="#" class="social-icon"><i class="fab fa-whatsapp"></i></a>
            </div>
            <p>&copy; 2025 SB Online Store. All rights reserved.</p>
        </div>
    </footer>

    <script>
        // Product Gallery Slider
        document.addEventListener('DOMContentLoaded', function() {
            const slides = document.querySelectorAll('.gallery-slide');
            const dots = document.querySelectorAll('.nav-dot');
            let currentSlide = 0;
            
            // Function to show a specific slide
            function showSlide(n) {
                slides.forEach(slide => slide.classList.remove('active'));
                dots.forEach(dot => dot.classList.remove('active'));
                
                currentSlide = (n + slides.length) % slides.length;
                slides[currentSlide].classList.add('active');
                dots[currentSlide].classList.add('active');
            }
            
            // Add click events to dots
            dots.forEach((dot, index) => {
                dot.addEventListener('click', () => {
                    showSlide(index);
                });
            });
            
            // Auto slide change
            setInterval(() => {
                showSlide(currentSlide + 1);
            }, 4000);
            
            // 3D effect on product card based on mouse movement
            const productCard = document.querySelector('.product-card');
            
            productCard.addEventListener('mousemove', (e) => {
                const cardRect = productCard.getBoundingClientRect();
                const cardCenterX = cardRect.left + cardRect.width / 2;
                const cardCenterY = cardRect.top + cardRect.height / 2;
                
                const mouseX = e.clientX - cardCenterX;
                const mouseY = e.clientY - cardCenterY;
                
                const rotateY = (mouseX / cardRect.width) * 20;
                const rotateX = -(mouseY / cardRect.height) * 20;
                
                productCard.style.transform = `translateY(-10px) rotateX(${rotateX}deg) rotateY(${rotateY}deg)`;
            });
            
            productCard.addEventListener('mouseleave', () => {
                productCard.style.transform = 'translateY(-10px) rotateX(5deg)';
            });
        });
    </script>
