<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="GHOST Harck Tech - Développeur web freelance à Calavi. Création de sites vitrine et applications PWA performantes. Devis gratuit en ligne.">
    <meta name="theme-color" content="#0D1117">
    <title>GHOST Harck Tech - Développeur web freelance Calavi</title>
    
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- FontAwesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #0D1117;
            --accent: #FF6A00;
            --secondary: #1C2128;
            --text: #E6EDF3;
            --text-muted: #8B949E;
        }

        body {
            font-family: 'Inter', sans-serif;
            background-color: var(--primary);
            color: var(--text);
            overflow-x: hidden;
        }

        /* Scroll behavior smooth */
        html {
            scroll-behavior: smooth;
        }

        /* Glassmorphism background */
        .glass {
            background: rgba(255, 106, 0, 0.05);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 106, 0, 0.1);
        }

        /* Header sticky */
        header {
            position: sticky;
            top: 0;
            z-index: 100;
            background: rgba(13, 17, 23, 0.95);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid rgba(255, 106, 0, 0.1);
        }

        /* Logo styling */
        .logo {
            font-family: 'Space Mono', monospace;
            font-size: 1.5rem;
            font-weight: 700;
            letter-spacing: -2px;
            background: linear-gradient(135deg, #FF6A00 0%, #FFA500 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        /* Hero section */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            width: 500px;
            height: 500px;
            background: radial-gradient(circle, rgba(255, 106, 0, 0.1) 0%, transparent 70%);
            top: -200px;
            right: -200px;
            animation: float 6s ease-in-out infinite;
        }

        .hero::after {
            content: '';
            position: absolute;
            width: 400px;
            height: 400px;
            background: radial-gradient(circle, rgba(255, 106, 0, 0.05) 0%, transparent 70%);
            bottom: -150px;
            left: -150px;
            animation: float 8s ease-in-out infinite reverse;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(30px); }
        }

        .hero-content {
            position: relative;
            z-index: 2;
            text-align: center;
            max-width: 900px;
            padding: 2rem;
            animation: fadeInUp 1s ease-out;
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

        .hero h1 {
            font-family: 'Space Mono', monospace;
            font-size: clamp(2.5rem, 8vw, 4.5rem);
            font-weight: 700;
            line-height: 1.2;
            margin-bottom: 1.5rem;
            text-transform: uppercase;
            letter-spacing: -1px;
        }

        .hero h1 .accent {
            color: var(--accent);
        }

        .hero-subtitle {
            font-size: clamp(1rem, 3vw, 1.25rem);
            color: var(--text-muted);
            margin-bottom: 2rem;
            line-height: 1.6;
        }

        /* CTA Buttons */
        .cta-btn {
            display: inline-flex;
            align-items: center;
            gap: 0.75rem;
            padding: 1rem 2rem;
            border-radius: 0.5rem;
            font-weight: 600;
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            border: none;
            cursor: pointer;
            text-decoration: none;
            font-size: 1rem;
        }

        .cta-primary {
            background: linear-gradient(135deg, var(--accent) 0%, #FFA500 100%);
            color: #000;
        }

        .cta-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 20px 40px rgba(255, 106, 0, 0.3);
        }

        .cta-secondary {
            background: rgba(255, 106, 0, 0.1);
            color: var(--accent);
            border: 2px solid var(--accent);
        }

        .cta-secondary:hover {
            background: rgba(255, 106, 0, 0.2);
            transform: translateY(-2px);
        }

        .cta-group {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
            justify-content: center;
            margin-top: 2.5rem;
        }

        /* Services section */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .service-card {
            padding: 2.5rem;
            border-radius: 1rem;
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            border: 1px solid rgba(255, 106, 0, 0.1);
        }

        .service-card:hover {
            transform: translateY(-10px);
            border-color: rgba(255, 106, 0, 0.3);
            background: rgba(255, 106, 0, 0.08);
        }

        .service-icon {
            width: 60px;
            height: 60px;
            background: linear-gradient(135deg, var(--accent) 0%, #FFA500 100%);
            border-radius: 0.75rem;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.75rem;
            color: #000;
            margin-bottom: 1.5rem;
        }

        .service-card h3 {
            font-size: 1.5rem;
            font-weight: 700;
            margin-bottom: 1rem;
        }

        .service-card p {
            color: var(--text-muted);
            margin-bottom: 1.5rem;
            line-height: 1.6;
        }

        .service-price {
            font-family: 'Space Mono', monospace;
            font-size: 1.75rem;
            font-weight: 700;
            color: var(--accent);
            margin-bottom: 1rem;
        }

        /* Sections */
        section {
            padding: 5rem 2rem;
        }

        section:nth-child(even) {
            background: rgba(255, 106, 0, 0.02);
        }

        .section-title {
            font-family: 'Space Mono', monospace;
            font-size: clamp(2rem, 6vw, 3.5rem);
            font-weight: 700;
            text-align: center;
            margin-bottom: 3rem;
            text-transform: uppercase;
            letter-spacing: -1px;
        }

        .section-title .accent {
            color: var(--accent);
        }

        /* About section */
        .about-content {
            max-width: 800px;
            margin: 0 auto;
            text-align: center;
        }

        .about-content p {
            font-size: 1.125rem;
            line-height: 1.8;
            color: var(--text-muted);
            margin-bottom: 1.5rem;
        }

        /* Contact section */
        .contact-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            max-width: 1200px;
            margin: 0 auto;
            align-items: center;
        }

        .contact-info {
            display: flex;
            flex-direction: column;
            gap: 2rem;
        }

        .contact-item {
            padding: 1.5rem;
            background: rgba(255, 106, 0, 0.05);
            border-radius: 0.75rem;
            border: 1px solid rgba(255, 106, 0, 0.1);
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            gap: 1.5rem;
        }

        .contact-item:hover {
            border-color: var(--accent);
            background: rgba(255, 106, 0, 0.1);
        }

        .contact-icon {
            width: 50px;
            height: 50px;
            background: linear-gradient(135deg, var(--accent) 0%, #FFA500 100%);
            border-radius: 0.5rem;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            color: #000;
            flex-shrink: 0;
        }

        .contact-info a {
            color: var(--text);
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .contact-info a:hover {
            color: var(--accent);
        }

        .contact-address {
            font-size: 1rem;
        }

        .contact-buttons {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
        }

        /* Maps iframe */
        .map-container {
            width: 100%;
            border-radius: 1rem;
            overflow: hidden;
            border: 1px solid rgba(255, 106, 0, 0.1);
            height: 500px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
        }

        .map-container iframe {
            width: 100%;
            height: 100%;
            border: none;
        }

        /* Footer */
        footer {
            background: rgba(13, 17, 23, 0.8);
            border-top: 1px solid rgba(255, 106, 0, 0.1);
            padding: 3rem 2rem;
            text-align: center;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
        }

        .footer-info {
            display: flex;
            flex-direction: column;
            gap: 1rem;
            font-size: 0.95rem;
            color: var(--text-muted);
            margin-bottom: 2rem;
        }

        .footer-info div {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
        }

        .footer-info a {
            color: var(--accent);
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .footer-info a:hover {
            color: #FFA500;
        }

        .social-icons {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin-top: 2rem;
        }

        .social-icon {
            width: 45px;
            height: 45px;
            background: rgba(255, 106, 0, 0.1);
            border-radius: 0.5rem;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--accent);
            text-decoration: none;
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 106, 0, 0.2);
        }

        .social-icon:hover {
            background: var(--accent);
            color: #000;
            transform: translateY(-3px);
        }

        /* Scroll animations */
        .fade-in-up {
            opacity: 0;
            transform: translateY(30px);
            animation: fadeInUp 0.8s ease-out forwards;
        }

        /* Navigation menu mobile */
        nav {
            display: flex;
            gap: 2rem;
            align-items: center;
        }

        nav a {
            color: var(--text);
            text-decoration: none;
            font-size: 0.95rem;
            font-weight: 500;
            transition: color 0.3s ease;
        }

        nav a:hover {
            color: var(--accent);
        }

        .nav-icons {
            display: flex;
            gap: 1rem;
            margin-left: auto;
        }

        .nav-icon {
            width: 35px;
            height: 35px;
            background: rgba(255, 106, 0, 0.1);
            border-radius: 0.5rem;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--accent);
            text-decoration: none;
            transition: all 0.3s ease;
        }

        .nav-icon:hover {
            background: rgba(255, 106, 0, 0.2);
        }

        /* Responsive */
        @media (max-width: 768px) {
            nav {
                gap: 1rem;
                font-size: 0.9rem;
            }

            nav a {
                display: none;
            }

            .contact-grid {
                grid-template-columns: 1fr;
            }

            .cta-group {
                flex-direction: column;
            }

            .cta-btn {
                justify-content: center;
                width: 100%;
            }

            section {
                padding: 3rem 1.5rem;
            }

            .hero h1 {
                font-size: 2rem;
            }

            .contact-buttons {
                flex-direction: column;
            }

            .contact-buttons .cta-btn {
                width: 100%;
            }

            .map-container {
                height: 300px;
            }

            .contact-item {
                flex-direction: column;
                text-align: center;
            }

            .contact-icon {
                width: 45px;
                height: 45px;
            }
        }

        /* Scroll indicator */
        .scroll-indicator {
            position: absolute;
            bottom: 30px;
            left: 50%;
            transform: translateX(-50%);
            animation: bounce 2s infinite;
        }

        @keyframes bounce {
            0%, 100% {
                transform: translateX(-50%) translateY(0);
            }
            50% {
                transform: translateX(-50%) translateY(10px);
            }
        }
    </style>
</head>
<body>
    <!-- Header Navigation -->
    <header>
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-20">
                <!-- Logo -->
                <a href="#" class="logo">GHOST Harck Tech</a>

                <!-- Navigation -->
                <nav class="hidden md:flex">
                    <a href="#services" aria-label="Aller aux services">Services</a>
                    <a href="#about" aria-label="À propos">À propos</a>
                    <a href="#contact" aria-label="Contact">Contact</a>
                </nav>

                <!-- Social Icons in Header -->
                <div class="nav-icons">
                    <a href="https://facebook.com/GHOST-Harck-Tech" target="_blank" rel="noopener noreferrer" class="nav-icon" aria-label="Suivre sur Facebook" title="Facebook">
                        <i class="fab fa-facebook-f"></i>
                    </a>
                    <a href="https://wa.me/2290158167445" target="_blank" rel="noopener noreferrer" class="nav-icon" aria-label="Contacter sur WhatsApp" title="WhatsApp">
                        <i class="fab fa-whatsapp"></i>
                    </a>
                    <a href="mailto:shouganne0@gmail.com" class="nav-icon" aria-label="Envoyer un email" title="Email">
                        <i class="fas fa-envelope"></i>
                    </a>
                </div>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <h1>
                Sites & Apps<br>
                <span class="accent">créés depuis mon téléphone</span>
            </h1>
            <p class="hero-subtitle">
                Développeur web freelance à Calavi spécialisé dans la création de sites vitrine et applications PWA performantes. Solutions digitales complètes pour votre business en Afrique de l'Ouest.
            </p>
            <div class="cta-group">
                <a href="#services" class="cta-btn cta-primary" aria-label="Consulter les services">
                    <i class="fas fa-arrow-right"></i> Voir Services
                </a>
                <a href="https://wa.me/2290158167445" target="_blank" rel="noopener noreferrer" class="cta-btn cta-secondary" aria-label="Écrire sur WhatsApp">
                    <i class="fab fa-whatsapp"></i> WhatsApp
                </a>
                <a href="#contact" class="cta-btn cta-secondary" aria-label="Voir l'itinéraire">
                    <i class="fas fa-map-marker-alt"></i> Itinéraire
                </a>
            </div>
        </div>
        <div class="scroll-indicator">
            <i class="fas fa-chevron-down" style="color: var(--accent); font-size: 1.5rem;"></i>
        </div>
    </section>

    <!-- Services Section -->
    <section id="services">
        <div class="max-w-7xl mx-auto">
            <h2 class="section-title">
                Mes <span class="accent">Services</span>
            </h2>
            
            <div class="services-grid">
                <!-- Service 1: Site Vitrine -->
                <div class="service-card glass fade-in-up">
                    <div class="service-icon">
                        <i class="fas fa-globe"></i>
                    </div>
                    <h3>Site Vitrine</h3>
                    <p>Présentez votre entreprise avec un site web professionnel, responsive et optimisé pour le SEO. Parfait pour établir votre présence en ligne et attirer des clients.</p>
                    <div class="service-price">À partir de 150 000 FCFA</div>
                    <p style="font-size: 0.9rem; color: var(--text-muted);">Domaine + hébergement inclus • Support 6 mois</p>
                </div>

                <!-- Service 2: App PWA -->
                <div class="service-card glass fade-in-up">
                    <div class="service-icon">
                        <i class="fas fa-mobile-alt"></i>
                    </div>
                    <h3>App PWA Installable</h3>
                    <p>Application progressive web installable sur mobile et desktop. Fonctionne hors ligne, charges rapides et experience native. Idéal pour e-commerce et services.</p>
                    <div class="service-price">À partir de 300 000 FCFA</div>
                    <p style="font-size: 0.9rem; color: var(--text-muted);">Backend Firebase • Push notifications</p>
                </div>

                <!-- Service 3: Maintenance -->
                <div class="service-card glass fade-in-up">
                    <div class="service-icon">
                        <i class="fas fa-tools"></i>
                    </div>
                    <h3>Maintenance Web</h3>
                    <p>Maintenez et évoluez votre site ou application existant. Corrections de bugs, mises à jour de sécurité, nouvelles fonctionnalités et optimisations de performance.</p>
                    <div class="service-price">À partir de 25 000 FCFA/mois</div>
                    <p style="font-size: 0.9rem; color: var(--text-muted);">Support 24h • Monitoring • Sauvegardes</p>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about">
        <div class="max-w-7xl mx-auto">
            <h2 class="section-title">
                À <span class="accent">Propos</s