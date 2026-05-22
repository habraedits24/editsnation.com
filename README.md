<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>Hyper Flux Studio | Premium Editing Assets</title>
    <!-- Font Awesome 6 -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <!-- Google Font: Proxima Nova alternative (using Nunito as it's closest, plus fallback) 
         'Proxima Nova' not free on google fonts, but using 'Plus Jakarta Sans' which is modern clean similar vibe.
         Also system fonts with fallback to achieve premium look -->
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Plus Jakarta Sans', 'Segoe UI', 'Inter', -apple-system, BlinkMacSystemFont, 'Proxima Nova', system-ui, sans-serif;
            background: #0a0a0f;
            color: #f0f0f8;
            line-height: 1.5;
            overflow-x: hidden;
        }

        /* Smooth, non-laggy background: previous gradient blend with subtle static animation to reduce GPU strain */
        .bg-smooth {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -2;
            background: radial-gradient(circle at 20% 30%, #0b0b1a, #03030a);
        }

        .bg-smooth::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 70% 40%, rgba(255, 80, 120, 0.2), transparent 60%),
                        radial-gradient(circle at 30% 80%, rgba(80, 150, 255, 0.2), transparent 70%);
            filter: blur(60px);
            opacity: 0.8;
            animation: gentlePulse 10s ease infinite alternate;
            will-change: opacity;
        }

        @keyframes gentlePulse {
            0% {
                opacity: 0.5;
            }
            100% {
                opacity: 1;
            }
        }

        /* subtle static pattern instead of heavy particles */
        .subtle-grid {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            pointer-events: none;
            background-image: radial-gradient(rgba(255, 77, 125, 0.08) 1px, transparent 1px);
            background-size: 48px 48px;
        }

        .container {
            max-width: 1280px;
            margin: 0 auto;
            padding: 2rem 1.5rem 4rem;
            position: relative;
            z-index: 2;
        }

        /* Header / Title */
        .hero {
            text-align: center;
            margin-bottom: 2.8rem;
            margin-top: 1rem;
        }

        .badge {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            background: linear-gradient(135deg, rgba(255, 80, 120, 0.2), rgba(80, 150, 255, 0.2));
            backdrop-filter: blur(8px);
            border-radius: 100px;
            padding: 0.4rem 1.4rem;
            font-size: 0.8rem;
            font-weight: 600;
            letter-spacing: 0.3px;
            border: 1px solid rgba(255, 120, 160, 0.4);
            margin-bottom: 1.5rem;
        }

        h1 {
            font-size: 3.4rem;
            font-weight: 800;
            background: linear-gradient(135deg, #FFFFFF, #ffb3c6, #a0c4ff);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
            letter-spacing: -0.02em;
            margin-bottom: 0.8rem;
        }

        .hero p {
            font-size: 1.2rem;
            color: #ccccf0;
            max-width: 600px;
            margin: 0 auto;
        }

        .offer-sub {
            text-align: center;
            margin-bottom: 3rem;
            font-weight: 500;
            color: #cfcfef;
            background: rgba(255, 255, 255, 0.02);
            width: fit-content;
            margin-left: auto;
            margin-right: auto;
            padding: 0.5rem 1.2rem;
            border-radius: 60px;
            backdrop-filter: blur(4px);
        }

        /* Pricing cards grid */
        .pricing-grid {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 2rem;
            margin-bottom: 3.5rem;
        }

        .card {
            background: rgba(12, 12, 25, 0.7);
            backdrop-filter: blur(12px);
            border-radius: 2rem;
            padding: 2rem 1.8rem;
            width: 300px;
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 100, 140, 0.3);
            box-shadow: 0 20px 35px -12px rgba(0, 0, 0, 0.5);
            text-align: center;
        }

        .card:hover {
            transform: translateY(-6px);
            border-color: rgba(255, 120, 180, 0.7);
            box-shadow: 0 25px 40px -12px rgba(255, 80, 120, 0.2);
            background: rgba(20, 20, 40, 0.75);
        }

        .plan-icon {
            font-size: 2.3rem;
            margin-bottom: 0.6rem;
            background: linear-gradient(145deg, #ff9fbd, #84b4ff);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
        }

        .plan-name {
            font-size: 1.8rem;
            font-weight: 700;
            margin-bottom: 0.3rem;
        }

        .price {
            font-size: 2.5rem;
            font-weight: 800;
            margin: 0.6rem 0 0.2rem;
            background: linear-gradient(135deg, #fff, #ffbfd5);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
        }

        .price-period {
            font-size: 0.8rem;
            font-weight: 400;
            color: #b9b9e6;
            margin-bottom: 0.6rem;
        }

        .bundle-size {
            background: rgba(255, 120, 160, 0.18);
            border-radius: 40px;
            padding: 0.25rem 0.9rem;
            display: inline-block;
            font-size: 0.7rem;
            font-weight: 600;
            color: #ffbfd5;
            margin-bottom: 1rem;
        }

        .description {
            font-size: 0.85rem;
            color: #d3d3fc;
            margin: 0.8rem 0 1rem;
            border-top: 1px dashed rgba(255, 140, 170, 0.4);
            padding-top: 0.8rem;
        }

        .feature-list {
            list-style: none;
            text-align: left;
            margin: 1rem 0 1.6rem;
        }

        .feature-list li {
            margin-bottom: 0.6rem;
            font-size: 0.85rem;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .feature-list li i {
            width: 20px;
            color: #ff7b9c;
            font-size: 0.9rem;
        }

        /* WhatsApp payment buttons gradient */
        .whatsapp-pay-btn {
            background: linear-gradient(95deg, #25d366, #128C7E);
            border: none;
            padding: 0.75rem 0;
            border-radius: 2rem;
            font-weight: 700;
            font-size: 0.9rem;
            color: white;
            cursor: pointer;
            transition: 0.25s;
            width: 100%;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            text-decoration: none;
            box-shadow: 0 6px 14px rgba(37, 211, 102, 0.25);
        }

        .whatsapp-pay-btn:hover {
            transform: scale(1.02);
            background: linear-gradient(95deg, #1fbc5c, #0c6b5e);
            box-shadow: 0 10px 20px rgba(37, 211, 102, 0.45);
        }

        /* Contact section with gradient themed buttons (smooth) */
        .contact-section {
            text-align: center;
            margin-top: 2rem;
            padding: 2rem 0 1rem;
            border-top: 1px solid rgba(255, 255, 255, 0.08);
        }

        .contact-title {
            font-size: 1.2rem;
            font-weight: 600;
            margin-bottom: 1.5rem;
            color: #eaeaff;
        }

        .contact-buttons {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 1.4rem;
            align-items: center;
        }

        /* Gradiented contact buttons with goo-like hover */
        .whatsapp-btn, .telegram-btn, .call-btn {
            display: inline-flex;
            align-items: center;
            gap: 12px;
            padding: 0.75rem 2rem;
            border-radius: 60px;
            font-weight: 600;
            font-size: 0.95rem;
            text-decoration: none;
            transition: all 0.25s ease;
            backdrop-filter: blur(4px);
            border: 1px solid rgba(255, 255, 255, 0.15);
        }

        .whatsapp-btn {
            background: linear-gradient(105deg, #25d366, #128C7E);
            color: white;
            box-shadow: 0 4px 12px rgba(37, 211, 102, 0.3);
        }

        .telegram-btn {
            background: linear-gradient(125deg, #2a3f5e, #1c2b3c);
            color: white;
            border: 1px solid #4e7ca0;
        }

        .telegram-btn i {
            color: #26A5E4;
        }

        .call-btn {
            background: linear-gradient(125deg, #c94f6f, #a83557);
            color: white;
            box-shadow: 0 4px 12px rgba(201, 79, 111, 0.3);
        }

        .whatsapp-btn:hover, .telegram-btn:hover, .call-btn:hover {
            transform: translateY(-3px);
            filter: brightness(1.05);
            box-shadow: 0 12px 22px rgba(0, 0, 0, 0.25);
        }

        .whatsapp-btn:hover {
            background: linear-gradient(105deg, #1fbb5c, #0f7a6b);
            box-shadow: 0 12px 22px rgba(37, 211, 102, 0.45);
        }

        .telegram-btn:hover {
            background: linear-gradient(125deg, #3f6085, #2a4057);
            border-color: #7db9e8;
        }

        .call-btn:hover {
            background: linear-gradient(125deg, #db6082, #bc3f62);
            box-shadow: 0 12px 22px rgba(219, 96, 130, 0.4);
        }

        /* Footer call area */
        .footer-call {
            text-align: center;
            margin-top: 2rem;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 0.8rem;
        }

        .footer-note {
            font-size: 0.7rem;
            opacity: 0.7;
        }

        .assets-note {
            text-align: center;
            margin: 2rem auto 1rem;
            font-size: 0.85rem;
            color: #b5b5e6;
            background: rgba(0, 0, 0, 0.3);
            padding: 0.7rem 1rem;
            border-radius: 2rem;
            width: fit-content;
            backdrop-filter: blur(5px);
        }

        /* Responsive */
        @media (max-width: 750px) {
            .container {
                padding: 1.5rem 1.2rem;
            }
            h1 {
                font-size: 2.2rem;
            }
            .hero p {
                font-size: 1rem;
            }
            .card {
                width: 100%;
                max-width: 340px;
            }
            .contact-buttons {
                flex-direction: column;
                width: 100%;
            }
            .whatsapp-btn, .telegram-btn, .call-btn {
                width: 80%;
                justify-content: center;
            }
        }

        @media (max-width: 480px) {
            .card {
                padding: 1.5rem;
            }
            .plan-name {
                font-size: 1.5rem;
            }
            .price {
                font-size: 2rem;
            }
        }

        /* Simple reveal on scroll (lightweight) */
        .reveal-on-scroll {
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.6s ease, transform 0.6s ease;
        }

        .reveal-on-scroll.visible {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>
<div class="bg-smooth"></div>
<div class="subtle-grid"></div>

<div class="container">
    <div class="hero reveal-on-scroll">
        <div class="badge">
            <i class="fas fa-crown"></i> HYPER FLUX STUDIO
        </div>
        <h1>Get Full Access to our <br>Premium Assets Library</h1>
        <p>Create Stunning & Unique Video Productions!</p>
    </div>
    <div class="offer-sub reveal-on-scroll">
        <i class="fas fa-film"></i> Professional LUTs · SFX · Transitions · Motion Graphics · Overlays
    </div>

    <div class="pricing-grid">
        <!-- Single Selected Bundle $30 - up to 100GB -->
        <div class="card reveal-on-scroll">
            <div class="plan-icon"><i class="fas fa-star-of-life"></i></div>
            <div class="plan-name">Starter Kit</div>
            <div class="price">$30</div>
            <div class="price-period">one-time payment</div>
            <div class="bundle-size"><i class="fas fa-database"></i> Up to 100GB · Curated Pack</div>
            <div class="description">
                Perfect for solo creators & social media editors
            </div>
            <ul class="feature-list">
                <li><i class="fas fa-check-circle"></i> 100GB premium assets (4K+ overlays, transitions)</li>
                <li><i class="fas fa-check-circle"></i> SFX & cinematic LUTs bundle</li>
                <li><i class="fas fa-check-circle"></i> Commercial use license</li>
                <li><i class="fas fa-cloud-download-alt"></i> Instant download link</li>
            </ul>
            <a href="https://wa.me/256771794634?text=Hello%20Hyper%20Flux!%20I%20want%20to%20purchase%20the%20%2430%20Starter%20Kit%20(100GB)%20bundle.%20Please%20share%20payment%20details." class="whatsapp-pay-btn" target="_blank">
                <i class="fab fa-whatsapp"></i> Buy via WhatsApp
            </a>
        </div>

        <!-- All Pack Bundles $100 - up to 600GB -->
        <div class="card reveal-on-scroll">
            <div class="plan-icon"><i class="fas fa-gem"></i></div>
            <div class="plan-name">Master Vault</div>
            <div class="price">$100</div>
            <div class="price-period">one-time payment · full library</div>
            <div class="bundle-size"><i class="fas fa-hard-drive"></i> Up to 600GB · All Packs</div>
            <div class="description">
                Ultimate collection for professionals & studios
            </div>
            <ul class="feature-list">
                <li><i class="fas fa-check-circle"></i> 600GB+ assets (every single bundle + future updates)</li>
                <li><i class="fas fa-check-circle"></i> Full access: transitions, SFX, LUTs, motion assets</li>
                <li><i class="fas fa-check-circle"></i> Extended commercial & multi-user license</li>
                <li><i class="fas fa-trophy"></i> Priority support + custom requests</li>
            </ul>
            <a href="https://wa.me/256771794634?text=Hello%20Hyper%20Flux!%20I%20want%20the%20%24100%20MASTER%20VAULT%20(600GB)%20All%20Packs%20bundle.%20Send%20me%20payment%20info%20please." class="whatsapp-pay-btn" target="_blank">
                <i class="fab fa-whatsapp"></i> Buy via WhatsApp
            </a>
        </div>
    </div>

    <!-- Note: Building a professional with latest features -->
    <div class="assets-note reveal-on-scroll">
        <i class="fas fa-microchip"></i> Building a professional workflow with latest features — AI tools, 3D assets, motion array style & more.
    </div>

    <!-- Contact section with WhatsApp, Telegram (t.me/habra_edits), and Call button -->
    <div class="contact-section reveal-on-scroll">
        <div class="contact-title">
            <i class="fas fa-headset"></i> Need help? Reach out through any channel
        </div>
        <div class="contact-buttons">
            <a href="https://wa.me/256771794634" class="whatsapp-btn" target="_blank">
                <i class="fab fa-whatsapp"></i> WhatsApp Support
            </a>
            <a href="https://t.me/habra_edits" class="telegram-btn" target="_blank">
                <i class="fab fa-telegram-plane"></i> Telegram (@habra_edits)
            </a>
            <a href="tel:+256200927763" class="call-btn">
                <i class="fas fa-phone-alt"></i> Call +256 200 927 763
            </a>
        </div>
    </div>

    <!-- Footer with additional details -->
    <div class="footer-call reveal-on-scroll">
        <div class="footer-note">
            <i class="fas fa-clock"></i> Mon-Fri 9AM–8PM (EAT) · Instant replies on WhatsApp & Telegram
        </div>
        <div class="footer-note">
            © Hyper Flux Studio — elevate every frame. All assets are original & royalty-ready.
        </div>
    </div>
</div>

<!-- Lightweight scroll reveal without lag -->
<script>
    (function() {
        // Smooth reveal on scroll with Intersection Observer (lightweight)
        const elements = document.querySelectorAll('.reveal-on-scroll');
        if (elements.length) {
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('visible');
                        observer.unobserve(entry.target);
                    }
                });
            }, { threshold: 0.1, rootMargin: "0px 0px -20px 0px" });
            elements.forEach(el => observer.observe(el));
        }
        // Manual trigger for any element already visible
        window.addEventListener('load', () => {
            const visibleElements = document.querySelectorAll('.reveal-on-scroll');
            visibleElements.forEach(el => {
                const rect = el.getBoundingClientRect();
                if (rect.top < window.innerHeight - 50) {
                    el.classList.add('visible');
                }
            });
        });
    })();
</script>
</body>
</html>
