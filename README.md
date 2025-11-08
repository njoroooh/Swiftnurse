<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SwiftNurse - Healthcare Solution Close To You</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary-pink: #ff6b9e;
            --light-pink: #ffebf1;
            --dark-pink: #e84393;
            --primary-blue: #0984e3;
            --light-blue: #e3f2fd;
            --dark-blue: #0a79df;
            --pure-white: #ffffff;
            --light-gray: #f5f6fa;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }

        @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap');

        body {
            background-color: var(--light-gray);
            color: #333;
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Header Styles */
        header {
            background: linear-gradient(135deg, var(--primary-pink), var(--primary-blue));
            color: var(--pure-white);
            padding: 1rem 0;
            position: fixed;
            width: 100%;
            z-index: 1000;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
        }

        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .logo-icon {
            font-size: 2rem;
            color: var(--pure-white);
        }

        .logo-text {
            font-size: 1.5rem;
            font-weight: 700;
            letter-spacing: 1px;
        }

        .logo-tagline {
            font-size: 0.7rem;
            opacity: 0.8;
            margin-top: -5px;
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        nav a {
            color: var(--pure-white);
            text-decoration: none;
            font-weight: 500;
            font-size: 1rem;
            position: relative;
            padding: 0.5rem 0;
            transition: all 0.3s ease;
        }

        nav a:after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            background: var(--pure-white);
            bottom: 0;
            left: 0;
            transition: width 0.3s ease;
        }

        nav a:hover:after {
            width: 100%;
        }

        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            color: var(--pure-white);
            font-size: 1.5rem;
            cursor: pointer;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            background: linear-gradient(rgba(255, 107, 158, 0.7), rgba(9, 132, 227, 0.7)), 
                        url('https://images.unsplash.com/photo-1576091160550-2173dba999ef?q=80&w=2070&auto=format&fit=crop') center/cover;
            display: flex;
            align-items: center;
            text-align: center;
            color: var(--pure-white);
            padding-top: 80px;
        }

        .hero-content {
            max-width: 800px;
            margin: 0 auto;
            padding: 2rem;
        }

        .hero-title {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
            animation: fadeInDown 1s ease;
        }

        .hero-subtitle {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            opacity: 0.9;
            animation: fadeInUp 1s ease 0.3s forwards;
            opacity: 0;
        }

        .btn {
            display: inline-block;
            background-color: var(--pure-white);
            color: var(--primary-pink);
            padding: 1rem 2rem;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            font-size: 1.1rem;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
            animation: fadeIn 1s ease 0.6s forwards;
            opacity: 0;
        }

        .btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
            background-color: var(--light-pink);
        }

        .btn-blue {
            background-color: var(--primary-blue);
            color: white;
            margin-left: 1rem;
        }

        .btn-blue:hover {
            background-color: var(--dark-blue);
        }

        /* Services Section */
        .services {
            padding: 5rem 0;
            background-color: var(--pure-white);
        }

        .section-title {
            text-align: center;
            margin-bottom: 3rem;
            position: relative;
        }

        .section-title h2 {
            font-size: 2.5rem;
            color: var(--primary-pink);
            display: inline-block;
        }

        .section-title h2:after {
            content: '';
            position: absolute;
            width: 80px;
            height: 3px;
            background: var(--primary-blue);
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        .service-card {
            background-color: var(--light-gray);
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: all 0.4s ease;
            position: relative;
        }

        .service-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
        }

        .service-img {
            width: 100%;
            height: 250px;
            object-fit: cover;
            transition: transform 0.5s ease;
        }

        .service-card:hover .service-img {
            transform: scale(1.05);
        }

        .service-content {
            padding: 1.5rem;
        }

        .service-title {
            font-size: 1.5rem;
            color: var(--primary-blue);
            margin-bottom: 0.5rem;
        }

        .service-description {
            color: #666;
            margin-bottom: 1rem;
        }

        .service-icon {
            font-size: 2.5rem;
            color: var(--primary-pink);
            margin-bottom: 1rem;
        }

        /* About Section */
        .about {
            padding: 5rem 0;
            background-color: var(--light-pink);
        }

        .about-container {
            display: flex;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
            gap: 3rem;
        }

        .about-img {
            flex: 1;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
        }

        .about-img img {
            width: 100%;
            height: auto;
            display: block;
            transition: transform 0.5s ease;
        }

        .about-img:hover img {
            transform: scale(1.05);
        }

        .about-content {
            flex: 1;
        }

        .about-title {
            font-size: 2rem;
            color: var(--primary-blue);
            margin-bottom: 1rem;
        }

        .about-text {
            margin-bottom: 1.5rem;
            color: #555;
        }

        .features-list {
            list-style: none;
            margin-bottom: 2rem;
        }

        .features-list li {
            margin-bottom: 0.8rem;
            position: relative;
            padding-left: 2rem;
        }

        .features-list li:before {
            content: '\f00c';
            font-family: 'Font Awesome 6 Free';
            font-weight: 900;
            position: absolute;
            left: 0;
            color: var(--primary-pink);
        }

        /* Testimonials */
        .testimonials {
            padding: 5rem 0;
            background-color: var(--light-blue);
        }

        .testimonials-slider {
            max-width: 800px;
            margin: 0 auto;
            padding: 0 2rem;
            position: relative;
        }

        .testimonial-card {
            background-color: var(--pure-white);
            padding: 2rem;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            text-align: center;
            margin: 0 1rem;
        }

        .client-img {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            object-fit: cover;
            margin: 0 auto 1rem;
            border: 3px solid var(--primary-pink);
        }

        .client-quote {
            font-style: italic;
            color: #555;
            margin-bottom: 1rem;
        }

        .client-name {
            font-weight: 600;
            color: var(--primary-blue);
        }

        .client-role {
            color: #777;
            font-size: 0.9rem;
        }

        /* Contact Section */
        .contact {
            padding: 5rem 0;
            background: linear-gradient(135deg, var(--light-pink), var(--light-blue));
        }

        .contact-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 3rem;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        .contact-info {
            background-color: var(--pure-white);
            padding: 2rem;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
        }

        .contact-title {
            font-size: 1.8rem;
            color: var(--primary-pink);
            margin-bottom: 1.5rem;
        }

        .contact-details {
            list-style: none;
        }

        .contact-details li {
            margin-bottom: 1.5rem;
            display: flex;
            align-items: flex-start;
            gap: 1rem;
        }

        .contact-icon {
            font-size: 1.5rem;
            color: var(--primary-blue);
            margin-top: 0.3rem;
        }

        .contact-form {
            background-color: var(--pure-white);
            padding: 2rem;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-control {
            width: 100%;
            padding: 1rem;
            border: 1px solid #ddd;
            border-radius: 8px;
            font-size: 1rem;
            transition: all 0.3s ease;
        }

        .form-control:focus {
            border-color: var(--primary-pink);
            outline: none;
            box-shadow: 0 0 0 3px rgba(255, 107, 158, 0.2);
        }

        textarea.form-control {
            min-height: 150px;
            resize: vertical;
        }

        .submit-btn {
            background-color: var(--primary-pink);
            color: white;
            border: none;
            padding: 1rem 2rem;
            border-radius: 8px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            width: 100%;
        }

        .submit-btn:hover {
            background-color: var(--dark-pink);
            transform: translateY(-3px);
        }

        /* Form Message */
        .form-message {margin-top:1rem; padding:1rem; border-radius:8px; font-weight:600; display:none;}
        .form-message.success {background-color: #d4edda; color:#155724; border:1px solid #c3e6cb;}
        .form-message.error {background-color: #f8d7da; color:#721c24; border:1px solid #f5c6cb;}

        /* Footer */
        footer {
            background: linear-gradient(135deg, var(--primary-pink), var(--primary-blue));
            color: var(--pure-white);
            padding: 3rem 0 1rem;
        }

        .footer-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        .footer-col h3 {
            font-size: 1.3rem;
            margin-bottom: 1.5rem;
            position: relative;
            display: inline-block;
        }

        .footer-col h3:after {
            content: '';
            position: absolute;
            width: 50px;
            height: 2px;
            background: var(--pure-white);
            bottom: -8px;
            left: 0;
        }

        .footer-links {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 0.8rem;
        }

        .footer-links a {
            color: var(--pure-white);
            text-decoration: none;
            transition: all 0.3s ease;
            opacity: 0.8;
        }

        .footer-links a:hover {
            opacity: 1;
            padding-left: 5px;
        }

        .social-links {
            display: flex;
            gap: 1rem;
            margin-top: 1.5rem;
        }

        .social-link {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            color: var(--pure-white);
            font-size: 1.2rem;
            transition: all 0.3s ease;
        }

        .social-link:hover {
            background-color: rgba(255, 255, 255, 0.2);
            transform: translateY(-3px);
        }

        .copyright {
            text-align: center;
            margin-top: 3rem;
            padding-top: 1.5rem;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            opacity: 0.8;
        }

        /* Animations */
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes fadeInDown {
            from { opacity: 0; transform: translateY(-30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Responsive Styles */
        @media (max-width: 992px) {
            .hero-title { font-size: 2.8rem; }
            .about-container { flex-direction: column; }
        }

        @media (max-width: 768px) {
            .header-container { padding: 0 1rem; }
            nav ul { display: none; }
            .mobile-menu-btn { display: block; }
            .hero-title { font-size: 2.2rem; }
            .hero-subtitle { font-size: 1.2rem; }
            .btn { display: block; margin: 1rem auto; width: 80%; }
            .btn-blue { margin-left: auto; }
        }

        @media (max-width: 576px) {
            .hero-title { font-size: 1.8rem; }
            .section-title h2 { font-size: 2rem; }
            .service-card { min-width: 100%; }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header id="header">
        <div class="header-container">
            <div class="logo">
                <i class="fas fa-heartbeat logo-icon"></i>
                <div>
                    <div class="logo-text">SwiftNurse</div>
                    <div class="logo-tagline">Healthcare solution close to you</div>
                </div>
            </div>
            <nav>
                <ul id="nav-menu">
                    <li><a href="#hero">Home</a></li>
                    <li><a href="#services">Services</a></li>
                    <li><a href="#about">About</a></li>
                    <li><a href="#testimonials">Testimonials</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
            </nav>
            <button class="mobile-menu-btn" id="mobile-menu-btn"><i class="fas fa-bars"></i></button>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="hero">
        <div class="hero-content">
            <h1 class="hero-title">Your Health, Our Priority</h1>
            <p class="hero-subtitle">SwiftNurse provides trusted healthcare services at your doorstep.</p>
            <a href="#contact" class="btn">Book a Nurse</a>
            <a href="#services" class="btn btn-blue">Explore Services</a>
        </div>
    </section>

    <!-- Services Section -->
    <section class="services" id="services">
        <div class="section-title">
            <h2>Our Services</h2>
        </div>
        <div class="services-grid">
            <div class="service-card">
                <img src="https://images.unsplash.com/photo-1588776814546-15c115e6b9de?q=80&w=800&auto=format&fit=crop" class="service-img" alt="Home Nursing">
                <div class="service-content">
                    <i class="fas fa-user-nurse service-icon"></i>
                    <h3 class="service-title">Home Nursing</h3>
                    <p class="service-description">Professional nurses for home care and post-operative recovery.</p>
                </div>
            </div>
            <div class="service-card">
                <img src="https://images.unsplash.com/photo-1588776814546-15c115e6b9de?q=80&w=800&auto=format&fit=crop" class="service-img" alt="Pediatric Care">
                <div class="service-content">
                    <i class="fas fa-baby service-icon"></i>
                    <h3 class="service-title">Pediatric Care</h3>
                    <p class="service-description">Specialized care for infants and children in the comfort of your home.</p>
                </div>
            </div>
            <div class="service-card">
                <img src="https://images.unsplash.com/photo-1588776814546-15c115e6b9de?q=80&w=800&auto=format&fit=crop" class="service-img" alt="Elderly Care">
                <div class="service-content">
                    <i class="fas fa-procedures service-icon"></i>
                    <h3 class="service-title">Elderly Care</h3>
                    <p class="service-description">Comprehensive care plans for seniors to maintain independence and health.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section class="about" id="about">
        <div class="about-container">
            <div class="about-img">
                <img src="https://images.unsplash.com/photo-1600185361463-6ab28a4b591f?q=80&w=800&auto=format&fit=crop" alt="About SwiftNurse">
            </div>
            <div class="about-content">
                <h2 class="about-title">About SwiftNurse</h2>
                <p class="about-text">SwiftNurse connects patients with professional healthcare providers, ensuring timely and efficient care at home.</p>
                <ul class="features-list">
                    <li>Certified and experienced nurses</li>
                    <li>24/7 availability</li>
                    <li>Affordable and transparent pricing</li>
                    <li>Personalized care plans</li>
                </ul>
                <a href="#contact" class="btn">Book a Nurse</a>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="contact" id="contact">
        <div class="section-title">
            <h2>Contact Us</h2>
        </div>
        <div class="contact-container">
            <div class="contact-info">
                <h3 class="contact-title">Get in Touch</h3>
                <ul class="contact-details">
                    <li><i class="fas fa-map-marker-alt contact-icon"></i>123 Health Street, Wellness City</li>
                    <li><i class="fas fa-phone contact-icon"></i>+123 456 7890</li>
                    <li><i class="fas fa-envelope contact-icon"></i>contact@swiftnurse.com</li>
                </ul>
            </div>
            <div class="contact-form">
                <form id="booking-form">
                    <div class="form-group">
                        <input type="text" name="name" class="form-control" placeholder="Your Name" required>
                    </div>
                    <div class="form-group">
                        <input type="email" name="email" class="form-control" placeholder="Your Email" required>
                    </div>
                    <div class="form-group">
                        <textarea name="message" class="form-control" placeholder="Your Message" required></textarea>
                    </div>
                    <button type="submit" class="submit-btn">Send Message</button>
                    <div class="form-message" id="form-message"></div>
                </form>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-container">
            <div class="footer-col">
                <h3>SwiftNurse</h3>
                <p>Your trusted healthcare partner.</p>
            </div>
            <div class="footer-col">
                <h3>Links</h3>
                <ul class="footer-links">
                    <li><a href="#hero">Home</a></li>
                    <li><a href="#services">Services</a></li>
                    <li><a href="#about">About</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
            </div>
            <div class="footer-col">
                <h3>Follow Us</h3>
                <div class="social-links">
                    <a href="#" class="social-link"><i class="fab fa-facebook-f"></i></a>
                    <a href="#" class="social-link"><i class="fab fa-twitter"></i></a>
                    <a href="#" class="social-link"><i class="fab fa-instagram"></i></a>
                    <a href="#" class="social-link"><i class="fab fa-linkedin-in"></i></a>
                </div>
            </div>
        </div>
        <div class="copyright">
            &copy; 2025 SwiftNurse. All rights reserved.
        </div>
    </footer>

    <!-- Scripts -->
    <script src="https://cdn.emailjs.com/dist/email.min.js"></script>
    <script>
        (function() {
            emailjs.init("aNt7HVW9ZnYMbAceL"); // Your EmailJS public key
        })();

        const form = document.getElementById('booking-form');
        const formMessage = document.getElementById('form-message');

        form.addEventListener('submit', function(e){
            e.preventDefault();
            emailjs.sendForm("service_9rfro2l", "template_vxztb8d", this)
            .then(() => {
                formMessage.textContent = "Your message has been sent successfully!";
                formMessage.className = "form-message success";
                formMessage.style.display = "block";
                form.reset();
            }, (error) => {
                formMessage.textContent = "Oops! Something went wrong. Please try again.";
                formMessage.className = "form-message error";
                formMessage.style.display = "block";
                console.error(error);
            });
        });
    </script>
</body>
</html>
