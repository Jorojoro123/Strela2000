<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Strela 2000 - Urban Electric Vehicle Solutions for Hotels</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #333;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            z-index: 1000;
            padding: 1rem 0;
            box-shadow: 0 2px 20px rgba(0, 0, 0, 0.1);
        }

        .nav-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: bold;
            color: #2563eb;
            text-decoration: none;
            cursor: pointer;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            text-decoration: none;
            color: #333;
            font-weight: 500;
            transition: color 0.3s ease;
            cursor: pointer;
        }

        .nav-links a:hover, .nav-links a.active {
            color: #2563eb;
        }

        .cta-btn {
            background: linear-gradient(135deg, #059669, #047857);
            color: white;
            padding: 0.75rem 1.5rem;
            border: none;
            border-radius: 25px;
            text-decoration: none;
            font-weight: 600;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            cursor: pointer;
        }

        .cta-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(5, 150, 105, 0.3);
        }

        /* Page Content */
        .page {
            display: none;
            min-height: 100vh;
            padding-top: 80px;
        }

        .page.active {
            display: block;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, #10b981 0%, #059669 100%);
            padding: 120px 0 80px;
            color: white;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><defs><pattern id="grid" width="10" height="10" patternUnits="userSpaceOnUse"><path d="M 10 0 L 0 0 0 10" fill="none" stroke="rgba(255,255,255,0.1)" stroke-width="1"/></pattern></defs><rect width="100" height="100" fill="url(%23grid)"/></svg>');
            opacity: 0.3;
        }

        .hero-content {
            position: relative;
            z-index: 2;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            font-weight: 700;
            animation: fadeInUp 1s ease;
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 2rem;
            opacity: 0.9;
            animation: fadeInUp 1s ease 0.2s both;
        }

        .hero-buttons {
            animation: fadeInUp 1s ease 0.4s both;
        }

        .hero-buttons .cta-btn {
            margin: 0 10px;
            padding: 1rem 2rem;
            font-size: 1.1rem;
        }

        .btn-secondary {
            background: rgba(255, 255, 255, 0.2);
            border: 2px solid rgba(255, 255, 255, 0.3);
        }

        .btn-secondary:hover {
            background: rgba(255, 255, 255, 0.3);
        }

        /* Features Section */
        .features {
            padding: 80px 0;
            background: #f8fafc;
        }

        .section-title {
            text-align: center;
            margin-bottom: 3rem;
        }

        .section-title h2 {
            font-size: 2.5rem;
            color: #1e293b;
            margin-bottom: 1rem;
        }

        .section-title p {
            font-size: 1.2rem;
            color: #64748b;
            max-width: 600px;
            margin: 0 auto;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .feature-card {
            background: white;
            padding: 2rem;
            border-radius: 15px;
            box-shadow: 0 4px 25px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .feature-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 40px rgba(0, 0, 0, 0.15);
        }

        .feature-icon {
            width: 60px;
            height: 60px;
            background: linear-gradient(135deg, #059669, #047857);
            border-radius: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 1.5rem;
            font-size: 1.5rem;
            color: white;
        }

        .feature-card h3 {
            font-size: 1.4rem;
            color: #1e293b;
            margin-bottom: 1rem;
        }

        .feature-card p {
            color: #64748b;
            line-height: 1.6;
        }

        /* Content Sections */
        .content-section {
            padding: 80px 0;
        }

        .content-section:nth-child(even) {
            background: #f8fafc;
        }

        .content-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
        }

        .content-text h2 {
            font-size: 2.5rem;
            color: #1e293b;
            margin-bottom: 1.5rem;
        }

        .content-text p {
            font-size: 1.1rem;
            color: #64748b;
            margin-bottom: 1.5rem;
            line-height: 1.8;
        }

        .content-visual {
            background: linear-gradient(135deg, #10b981, #059669);
            border-radius: 20px;
            height: 300px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 4rem;
            position: relative;
            overflow: hidden;
        }

        .content-visual::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255, 255, 255, 0.1), transparent);
            animation: shine 3s infinite;
        }

        /* Team Section */
        .team-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .team-card {
            background: white;
            padding: 2rem;
            border-radius: 15px;
            box-shadow: 0 4px 25px rgba(0, 0, 0, 0.1);
            text-align: center;
        }

        .team-avatar {
            width: 100px;
            height: 100px;
            background: linear-gradient(135deg, #10b981, #059669);
            border-radius: 50%;
            margin: 0 auto 1rem;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 2rem;
        }

        .team-card h3 {
            color: #1e293b;
            margin-bottom: 0.5rem;
        }

        .team-card .role {
            color: #059669;
            font-weight: 600;
            margin-bottom: 1rem;
        }

        .team-card p {
            color: #64748b;
            font-size: 0.9rem;
        }

        /* Services Grid */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .service-card {
            background: white;
            padding: 2rem;
            border-radius: 15px;
            box-shadow: 0 4px 25px rgba(0, 0, 0, 0.1);
            border-left: 5px solid #059669;
        }

        .service-card h3 {
            color: #1e293b;
            margin-bottom: 1rem;
            font-size: 1.3rem;
        }

        .service-card p {
            color: #64748b;
            line-height: 1.6;
            margin-bottom: 1rem;
        }

        .service-features {
            list-style: none;
        }

        .service-features li {
            color: #1e293b;
            padding: 0.25rem 0;
            font-size: 0.9rem;
        }

        .service-features li::before {
            content: '✓';
            color: #10b981;
            font-weight: bold;
            margin-right: 0.5rem;
        }

        /* Contact Form */
        .contact-form {
            max-width: 600px;
            margin: 0 auto;
            background: white;
            padding: 2rem;
            border-radius: 15px;
            box-shadow: 0 4px 25px rgba(0, 0, 0, 0.1);
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            color: #1e293b;
            font-weight: 500;
        }

        .form-group input,
        .form-group textarea,
        .form-group select {
            width: 100%;
            padding: 0.75rem;
            border: 2px solid #e2e8f0;
            border-radius: 8px;
            font-size: 1rem;
            transition: border-color 0.3s ease;
        }

        .form-group input:focus,
        .form-group textarea:focus,
        .form-group select:focus {
            outline: none;
            border-color: #059669;
        }

        .form-group textarea {
            height: 120px;
            resize: vertical;
        }

        .contact-info {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .contact-card {
            background: white;
            padding: 2rem;
            border-radius: 15px;
            box-shadow: 0 4px 25px rgba(0, 0, 0, 0.1);
            text-align: center;
        }

        .contact-icon {
            width: 60px;
            height: 60px;
            background: linear-gradient(135deg, #059669, #047857);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 1rem;
            color: white;
            font-size: 1.5rem;
        }

        /* Footer */
        footer {
            background: #0f172a;
            color: white;
            padding: 3rem 0 1rem;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
        }

        .footer-section h3 {
            margin-bottom: 1rem;
            color: #10b981;
        }

        .footer-section p, .footer-section a {
            color: #94a3b8;
            text-decoration: none;
            line-height: 1.8;
        }

        .footer-section a:hover {
            color: white;
        }

        .footer-bottom {
            border-top: 1px solid #334155;
            padding-top: 2rem;
            text-align: center;
            color: #94a3b8;
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

        @keyframes shine {
            0% { transform: translateX(-100%) translateY(-100%) rotate(45deg); }
            100% { transform: translateX(100%) translateY(100%) rotate(45deg); }
        }

        /* Mobile Responsiveness */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .hero p {
                font-size: 1.1rem;
            }

            .hero-buttons .cta-btn {
                display: block;
                margin: 0.5rem 0;
            }

            .content-grid {
                grid-template-columns: 1fr;
                gap: 2rem;
            }

            .section-title h2 {
                font-size: 2rem;
            }

            .features-grid,
            .services-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav>
        <div class="nav-container">
            <a href="#" class="logo" onclick="showPage('home')">Strela 2000</a>
            <ul class="nav-links">
                <li><a href="#" onclick="showPage('home')" class="nav-link active">Home</a></li>
                <li><a href="#" onclick="showPage('about')" class="nav-link">About Us</a></li>
                <li><a href="#" onclick="showPage('services')" class="nav-link">Services & Products</a></li>
                <li><a href="#" onclick="showPage('contact')" class="nav-link">Contact</a></li>
            </ul>
            <a href="#" onclick="showPage('contact')" class="cta-btn">Partner With Us</a>
        </div>
    </nav>

    <!-- HOME PAGE -->
    <div id="home" class="page active">
        <!-- Hero Section -->
        <section class="hero">
            <div class="container">
                <div class="hero-content">
                    <h1>Urban Electric Mobility for Hotels</h1>
                    <p>Partner with Strela 2000 to offer your guests premium small electric vehicles for seamless city exploration</p>
                    <div class="hero-buttons">
                        <a href="#" onclick="showPage('contact')" class="cta-btn">Start Partnership</a>
                        <a href="#" onclick="showPage('services')" class="cta-btn btn-secondary">Learn More</a>
                    </div>
                </div>
            </div>
        </section>

        <!-- Features Section -->
        <section class="features">
            <div class="container">
                <div class="section-title">
                    <h2>Complete Urban Mobility Solution</h2>
                    <p>We provide everything your hotel needs to offer guests a premium electric vehicle sharing experience</p>
                </div>
                <div class="features-grid">
                    <div class="feature-card">
                        <div class="feature-icon">🚗</div>
                        <h3>Premium Electric Vehicles</h3>
                        <p>Compact, efficient, and perfect for urban exploration. Our fleet of small electric vehicles is designed for city mobility with zero emissions.</p>
                    </div>
                    <div class="feature-card">
                        <div class="feature-icon">🏨</div>
                        <h3>Hotel Partnership Program</h3>
                        <p>Seamless integration with your hotel operations. We handle maintenance, charging infrastructure, and guest support.</p>
                    </div>
                    <div class="feature-card">
                        <div class="feature-icon">📱</div>
                        <h3>Digital Platform</h3>
                        <p>Easy-to-use booking system with mobile app integration, real-time availability, and 24/7 customer support.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Benefits Section -->
        <section class="content-section">
            <div class="container">
                <div class="content-grid">
                    <div class="content-text">
                        <h2>Why Choose Strela 2000?</h2>
                        <p>Transform your guest experience while creating new revenue opportunities. Our comprehensive solution handles all aspects of electric vehicle sharing, allowing you to focus on hospitality.</p>
                        <p>With zero upfront investment, professional installation, and 24/7 support, we make it easy for hotels to offer cutting-edge mobility solutions to their guests.</p>
                        <a href="#" onclick="showPage('about')" class="cta-btn">Learn About Us</a>
                    </div>
                    <div class="content-visual">
                        🤝
                    </div>
                </div>
            </div>
        </section>
    </div>

    <!-- ABOUT US PAGE -->
    <div id="about" class="page">
        <section class="content-section" style="padding-top: 120px;">
            <div class="container">
                <div class="section-title">
                    <h2>About Strela 2000</h2>
                    <p>Pioneering the future of urban mobility through innovative B2B partnerships</p>
                </div>
                
                <div class="content-grid">
                    <div class="content-text">
                        <h2>Our Mission</h2>
                        <p>At Strela 2000, we're revolutionizing urban transportation by making electric mobility accessible through strategic hotel partnerships. We believe that sustainable transportation should be convenient, affordable, and seamlessly integrated into the travel experience.</p>
                        <p>Founded with a vision to reduce urban congestion and emissions while enhancing guest experiences, we've developed a comprehensive B2B solution that benefits hotels, guests, and the environment.</p>
                    </div>
                    <div class="content-visual">
                        🌍
                    </div>
                </div>
            </div>
        </section>

        <section class="content-section">
            <div class="container">
                <div class="content-grid">
                    <div class="content-visual">
                        🚀
                    </div>
                    <div class="content-text">
                        <h2>Our Vision</h2>
                        <p>We envision a future where every urban hotel offers sustainable mobility solutions to their guests, creating a network of environmentally conscious travel experiences across cities worldwide.</p>
                        <p>By 2030, we aim to be the leading provider of B2B electric vehicle sharing solutions, partnering with over 1,000 hotels globally and preventing millions of tons of CO2 emissions annually.</p>
                    </div>
                </div>
            </div>
        </section>

        <section class="features">
            <div class="container">
                <div class="section-title">
                    <h2>Our Values</h2>
                    <p>The principles that guide everything we do</p>
                </div>
                <div class="features-grid">
                    <div class="feature-card">
                        <div class="feature-icon">🌱</div>
                        <h3>Sustainability</h3>
                        <p>Every vehicle in our fleet is 100% electric, contributing to cleaner cities and reduced carbon footprints for travelers.</p>
                    </div>
                    <div class="feature-card">
                        <div class="feature-icon">🤝</div>
                        <h3>Partnership</h3>
                        <p>We believe in building long-term relationships with our hotel partners, creating mutual value and shared success.</p>
                    </div>
                    <div class="feature-card">
                        <div class="feature-icon">💡</div>
                        <h3>Innovation</h3>
                        <p>We continuously innovate our technology, vehicles, and services to stay ahead of industry trends and customer needs.</p>
                    </div>
                </div>
            </div>
        </section>

        <section class="content-section">
            <div class="container">
                <div class="section-title">
                    <h2>Our Team</h2>
                    <p>Meet the experts behind Strela 2000's success</p>
                </div>
                <div class="team-grid">
                    <div class="team-card">
                        <div class="team-avatar">👨‍💼</div>
                        <h3>Alex Johnson</h3>
                        <div class="role">CEO & Founder</div>
                        <p>15+ years in sustainable transportation and hospitality partnerships. Former executive at major EV companies.</p>
                    </div>
                    <div class="team-card">
                        <div class="team-avatar">👩‍💻</div>
                        <h3>Sarah Chen</h3>
                        <div class="role">CTO</div>
                        <p>Tech innovator with expertise in IoT, mobile platforms, and smart city solutions. MIT graduate with 12+ years experience.</p>
                    </div>
                    <div class="team-card">
                        <div class="team-avatar">👨‍🔧</div>
                        <h3>Marcus Rodriguez</h3>
                        <div class="role">VP Operations</div>
                        <p>Fleet management specialist with background in automotive engineering and sustainable mobility solutions.</p>
                    </div>
                    <div class="team-card">
                        <div class="team-avatar">👩‍💼</div>
                        <h3>Emma Thompson</h3>
                        <div class="role">Partnership Director</div>
                        <p>Hospitality industry veteran with extensive experience in B2B partnerships and customer success management.</p>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <!-- SERVICES & PRODUCTS PAGE -->
    <div id="services" class="page">
        <section class="content-section" style="padding-top: 120px;">
            <div class="container">
                <div class="section-title">
                    <h2>Services & Products</h2>
                    <p>Comprehensive solutions for hotel partners and their guests</p>
                </div>
            </div>
        </section>

        <section class="features">
            <div class="container">
                <div class="section-title">
                    <h2>Our Vehicle Fleet</h2>
                    <p>Premium electric vehicles designed for urban mobility</p>
                </div>
                <div class="services-grid">
                    <div class="service-card">
                        <h3>Compact Electric Cars</h3>
                        <p>Perfect for city exploration with 2-4 passenger capacity, ideal for couples or small families visiting your hotel.</p>
                        <ul class="service-features">
                            <li>200km range on single charge</li>
                            <li>GPS navigation included</li>
                            <li>Climate control</li>
                            <li>Smartphone integration</li>
                            <li>24/7 roadside assistance</li>
                        </ul>
                    </div>
                    <div class="service-card">
                        <h3>Electric Scooters</h3>
                        <p>Agile and fun way to navigate busy city streets, perfect for quick trips and solo exploration.</p>
                        <ul class="service-features">
                            <li>80km range</li>
                            <li>Lightweight and maneuverable</li>
                            <li>Secure storage compartment</li>
                            <li>LED safety lighting</li>
                            <li>Anti-theft protection</li>
                        </ul>
                    </div>
                    <div class="service-card">
                        <h3>Electric Bikes</h3>
                        <p>Eco-friendly cycling experience with electric assistance for effortless city touring.</p>
                        <ul class="service-features">
                            <li>60km assisted range</li>
                            <li>Multiple assist levels</li>
                            <li>Integrated GPS</li>
                            <li>Weather protection</li>
                            <li>Helmet included</li>
                        </ul>
                    </div>
                </div>
            </div>
        </section>

        <section class="content-section">
            <div class="container">
                <div class="section-title">
                    <h2>Partnership Services</h2>
                    <p>Everything your hotel needs for seamless operations</p>
                </div>
                <div class="services-grid">
                    <div class="service-card">
                        <h3>Installation & Setup</h3>
                        <p>Complete turnkey solution from initial consultation to full operational launch.</p>
                        <ul class="service-features">
                            <li>Site assessment and planning</li>
                            <li>Charging station installation</li>
                            <li>Staff training programs</li>
                            <li>Guest orientation materials</li>
                            <li>Soft launch testing</li>
                        </ul>
                    </div>
                    <div class="service-card">
                        <h3>Technology Platform</h3>
                        <p>Advanced booking and management system integrated with your hotel operations.</p>
                        <ul class="service-features">
                            <li>Mobile app for guests</li>
                            <li>Hotel dashboard</li>
                            <li>Real-time vehicle tracking</li>
                            <li>Automated billing</li>
                            <li>Analytics and reporting</li>
                        </ul>
                    </div>
                    <div class="service-card">
                        <h3>Maintenance & Support</h3>
                        <p>Comprehensive ongoing support to ensure optimal performance and guest satisfaction.</p>
                        <ul class="service-features">
                            <li>24/7 technical support</li>
                            <li>Regular maintenance</li>
                            <li>Vehicle replacement service</li>
                            <li>Emergency response</li>
                            <li>Performance optimization</li>
                        </ul>
                    </div>
                    <div class="service-card">
                        <h3>Marketing & Branding</h3>
                        <p>Co-branded marketing materials and campaigns to promote the service to your guests.</p>
                        <ul class="service-features">
                            <li>Custom branding options</li>
                            <li>Marketing collateral</li>
                            <li>Digital marketing support</li>
                            <li>Guest communication templates</li>
                            <li>Social media assets</li>
                        </ul>
                    </div>
                    <div class="service-card">
                        <h3>Revenue Optimization</h3>
                        <p>Flexible pricing models and revenue sharing to maximize your hotel's profitability.</p>
                        <ul class="service-features">
                            <li>Dynamic pricing strategies</li>
                            <li>Revenue sharing models</li>
                            <li>Performance analytics</li>
                            <li>Seasonal adjustments</li>
                            <li>Profit maximization consulting</li>
                        </ul>
                    </div>
                    <div class="service-card">
                        <h3>Sustainability Reporting</h3>
                        <p>Detailed environmental impact reports to support your hotel's sustainability goals.</p>
                        <ul class="service-features">
                            <li>CO2 reduction tracking</li>
                            <li>Sustainability certificates</li>
                            <li>Environmental impact reports</li>
                            <li>Green certification support</li>
                            <li>CSR documentation</li>
                        </ul>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <!-- CONTACT PAGE -->
    <div id="contact" class="page">
        <section class="content-section" style="padding-top: 120px;">
            <div class="container">
                <div class="section-title">
                    <h2>Contact Us</h2>
                    <p>Ready to transform your guest experience? Let's discuss your partnership opportunities</p>
                </div>

                <div class="contact-form">
                    <form id="contactForm">
                        <div class="form-group">
                            <label for="hotelName">Hotel Name *</label>
                            <input type="text" id="hotelName" name="hotelName" required>
                        </div>
                        <div class="form-group
