
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>eDesign Studio · motion + brand elevation</title>
    <!-- Font Awesome 6 (free) -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Outfit', 'Segoe UI', Roboto, system-ui, sans-serif;
        }

        /* import smooth font */
        @import url('https://fonts.googleapis.com/css2?family=Outfit:wght@300..700&display=swap');

        body {
            min-height: 100vh;
            background: linear-gradient(145deg, #0b3b4f 0%, #1c6e6b 40%, #2a9d8f 70%, #48c9b0 100%);
            background-size: 300% 300%;
            animation: aquaFlow 18s ease infinite;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 1.8rem;
            position: relative;
            overflow-x: hidden;
        }

        @keyframes aquaFlow {
            0% { background-position: 0% 20%; }
            50% { background-position: 100% 70%; }
            100% { background-position: 0% 20%; }
        }

        /* animated green-blue overlapping glass bubbles */
        .bg-bubbles {
            position: absolute;
            inset: 0;
            z-index: 1;
            opacity: 0.25;
            pointer-events: none;
        }

        .bg-bubbles span {
            position: absolute;
            width: 25vmin;
            height: 25vmin;
            border-radius: 50%;
            background: rgba(50, 220, 200, 0.2);
            backdrop-filter: blur(6px);
            border: 2px solid rgba(255, 255, 255, 0.3);
            box-shadow: 0 0 70px #2fe0c0;
            animation: float 24s infinite alternate ease-in-out;
        }

        .bg-bubbles span:nth-child(1) { top: 5%; left: 3%; width: 30vmin; height: 30vmin; background: rgba(70, 230, 190, 0.2); animation-duration: 19s; }
        .bg-bubbles span:nth-child(2) { bottom: 10%; right: 2%; width: 40vmin; height: 40vmin; background: rgba(0, 200, 180, 0.18); animation-duration: 26s; animation-delay: -3s; }
        .bg-bubbles span:nth-child(3) { top: 40%; left: 70%; width: 20vmin; height: 20vmin; background: rgba(90, 240, 200, 0.22); animation-duration: 14s; }
        .bg-bubbles span:nth-child(4) { bottom: 20%; left: 15%; width: 35vmin; height: 35vmin; background: rgba(30, 210, 180, 0.18); animation-duration: 30s; }

        @keyframes float {
            0% { transform: translate(0, 0) scale(1); }
            100% { transform: translate(4%, -5%) scale(1.1); }
        }

        /* main glass card (parent) */
        .glass-studio {
            position: relative;
            z-index: 30;
            max-width: 900px;
            width: 100%;
            background: rgba(10, 50, 55, 0.35);
            backdrop-filter: blur(16px) saturate(200%);
            -webkit-backdrop-filter: blur(16px) saturate(200%);
            border-radius: 56px 28px 56px 28px;
            box-shadow: 0 35px 90px -15px #022e33, 0 0 0 2px rgba(70, 240, 190, 0.4) inset, 0 0 0 3px rgba(50, 210, 200, 0.3) inset;
            padding: 2.5rem 2.5rem;
            border: 1px solid rgba(80, 255, 200, 0.4);
            transition: all 0.3s;
            animation: cardPulse 6s infinite alternate;
        }

        @keyframes cardPulse {
            0% { box-shadow: 0 35px 70px -15px #022e33, 0 0 0 2px rgba(70, 240, 190, 0.3) inset, 0 0 0 3px rgba(50, 210, 200, 0.3) inset; }
            100% { box-shadow: 0 45px 90px -10px #035f5f, 0 0 0 3px rgba(80, 255, 210, 0.7) inset, 0 0 0 5px rgba(30, 200, 180, 0.4) inset; }
        }

        /* individual items fade-in-up (stagger) */
        .fade-item {
            opacity: 0;
            transform: translateY(24px);
            animation: fadeUp 0.7s cubic-bezier(0.2, 0.9, 0.3, 1) forwards;
        }

        .item-1 { animation-delay: 0.1s; }
        .item-2 { animation-delay: 0.25s; }
        .item-3 { animation-delay: 0.4s; }
        .item-4 { animation-delay: 0.55s; }
        .item-5 { animation-delay: 0.7s; }
        .item-6 { animation-delay: 0.85s; }
        .item-7 { animation-delay: 1s; }

        @keyframes fadeUp {
            0% { opacity: 0; transform: translateY(30px); }
            100% { opacity: 1; transform: translateY(0); }
        }

        /* navigation logo — eDesign Studio */
        .nav-logo {
            display: flex;
            align-items: center;
            gap: 8px;
            margin-bottom: 2rem;
            background: rgba(10, 80, 75, 0.35);
            backdrop-filter: blur(10px);
            padding: 0.6rem 2rem 0.6rem 1.8rem;
            border-radius: 100px 20px 100px 20px;
            width: fit-content;
            border: 2px solid #3fe0c0;
            box-shadow: 0 0 30px #1f9f8e;
        }

        .nav-logo i {
            font-size: 2.4rem;
            color: #c6fff0;
            filter: drop-shadow(0 0 12px #28e0d0);
        }

        .nav-logo h2 {
            font-size: 2.2rem;
            font-weight: 600;
            background: linear-gradient(150deg, #ebfff0, #9dffe6, #5fffd0);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            letter-spacing: -0.5px;
        }

        /* marquee glass + fade */
        .marquee-glass {
            width: 100%;
            overflow: hidden;
            background: rgba(20, 100, 95, 0.35);
            backdrop-filter: blur(12px);
            border-radius: 60px 16px 60px 16px;
            border: 2px solid #4fe8cf;
            box-shadow: 0 0 40px #28cca8;
            padding: 0.7rem 0;
            margin: 2rem 0 2.2rem 0;
        }

        .marquee-inner {
            display: inline-block;
            white-space: nowrap;
            animation: scrollRightToLeft 24s linear infinite;
            font-size: 1.9rem;
            font-weight: 500;
            color: #ebfff0;
            text-shadow: 0 0 10px #179688;
        }

        .marquee-inner span {
            margin-right: 3rem;
            background: linear-gradient(135deg, #b3ffe8, #fff7b0);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            font-weight: 600;
        }

        .marquee-inner i {
            margin: 0 2rem;
            color: #74ffdd;
            font-size: 2.2rem;
        }

        @keyframes scrollRightToLeft {
            0% { transform: translateX(0%); }
            100% { transform: translateX(-50%); }
        }

        /* rectangle with round edges (all buttons) */
        .rect-round {
            border-radius: 20px !important;
            transition: all 0.3s ease;
        }

        /* unique download button rectangle-round */
        .download-rect {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 24px;
            background: linear-gradient(115deg, #127c70, #0a5f5f, #1fb5a0);
            background-size: 200% 200%;
            border: 2px solid #9efff0;
            padding: 1.6rem 3.5rem;
            border-radius: 28px;   /* rectangle with round edges */
            font-size: 2.2rem;
            font-weight: 700;
            color: #ffffff;
            text-shadow: 0 3px 10px #005f5f;
            box-shadow: 0 25px 40px -10px #03302b, 0 0 0 3px #64ffda, 0 0 0 6px #25b5a0;
            cursor: pointer;
            width: fit-content;
            min-width: 380px;
            transition: 0.25s;
            animation: btnGlow 2.8s infinite alternate;
        }

        .download-rect i {
            font-size: 2.8rem;
            color: #bafff0;
            filter: drop-shadow(0 0 10px #8cffe6);
        }

        @keyframes btnGlow {
            0% { box-shadow: 0 20px 40px -10px #022e2e, 0 0 0 3px #50f0d0, 0 0 0 6px #168075; }
            100% { box-shadow: 0 35px 60px -10px #044b4b, 0 0 0 4px #a2ffee, 0 0 0 8px #32cfb5; }
        }

        .download-rect:hover {
            transform: scale(1.02) translateY(-4px);
            background: linear-gradient(115deg, #1b9b8a, #0f8575, #2fc7b0);
            box-shadow: 0 40px 60px -10px #0b4640;
        }

        /* copy link area (rect round) */
        .copy-area {
            display: flex;
            background: rgba(0, 70, 65, 0.45);
            backdrop-filter: blur(10px);
            border: 2px solid #6ae6d0;
            border-radius: 28px;   /* rectangle round edges */
            padding: 0.3rem 0.3rem 0.3rem 1.8rem;
            margin-top: 2rem;
            max-width: 620px;
            width: 100%;
        }

        .copy-area input {
            flex: 1;
            background: transparent;
            border: none;
            color: #ecfff6;
            font-size: 1rem;
            font-family: monospace;
            padding: 0.8rem 0;
            outline: none;
        }

        .copy-btn {
            background: #118b7e;
            border: 2px solid #aafff0;
            border-radius: 20px;   /* round edges rectangle */
            padding: 0.8rem 2.2rem;
            font-weight: 700;
            color: #021f1f;
            display: flex;
            align-items: center;
            gap: 8px;
            font-size: 1.1rem;
            cursor: pointer;
            transition: 0.2s;
        }

        .copy-btn i { color: #e0fffa; font-size: 1.3rem; }
        .copy-btn:hover { background: #1fb5a0; color: #000; }

        /* contact buttons — rectangle round edges */
        .contact-row {
            display: flex;
            flex-wrap: wrap;
            gap: 1.2rem;
            margin: 2.5rem 0 0.5rem;
        }

        .contact-btn {
            flex: 1 1 220px;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 15px;
            background: rgba(15, 85, 80, 0.45);
            backdrop-filter: blur(12px);
            border: 2px solid #47e5cf;
            border-radius: 28px;   /* rectangle round */
            padding: 1.2rem 1.8rem;
            font-size: 1.3rem;
            font-weight: 600;
            color: #f0fff9;
            text-decoration: none;
            transition: 0.25s;
            box-shadow: 0 8px 22px #033d3d;
        }

        .contact-btn i { font-size: 2rem; }
        .contact-btn i.fa-whatsapp { color: #9efff0; }  /* soft blue-green */
        .contact-btn i.fa-envelope { color: #b3ffe0; }

        .contact-btn:hover {
            background: rgba(25, 130, 115, 0.7);
            border-color: #a2ffe6;
            transform: translateY(-6px);
            box-shadow: 0 20px 30px #043b33;
        }

        /* MEGA link display */
        .link-hint-rect {
            background: rgba(0, 60, 55, 0.6);
            backdrop-filter: blur(8px);
            border-radius: 20px;    /* round edges */
            padding: 0.9rem 2rem;
            margin: 1.8rem 0 0.8rem;
            border: 2px solid #57e0ca;
            color: #ddfff5;
            word-break: break-all;
            font-size: 0.9rem;
        }

        .footer-note {
            margin-top: 1.5rem;
            color: #d1fff0;
            border-top: 2px dashed #2fc7b0;
            padding-top: 1rem;
            text-align: right;
            font-weight: 300;
        }

        .footer-note strong {
            color: #b3ffe0;
            font-weight: 600;
        }
    </style>
</head>
<body>
    <div class="bg-bubbles">
        <span></span><span></span><span></span><span></span>
    </div>

    <div class="glass-studio">
        <!-- NAV LOGO: eDesign Studio (fade item) -->
        <div class="nav-logo fade-item item-1">
            <i class="fas fa-cubes"></i>
            <h2>eDesign Studio</h2>
        </div>

        <!-- LOOPING MARQUEE (pro message) glass with fade -->
        <div class="marquee-glass fade-item item-2">
            <div class="marquee-inner">
                <span>✦ motion architect ✦</span>
                <i class="fas fa-bolt"></i>
                <span>I engineer brand growth through cinematic motion</span>
                <i class="fas fa-chart-line"></i>
                <span>✦ strategic narratives ✦</span>
                <i class="fas fa-globe"></i>
                <span>elevating brands worldwide</span>
                <i class="fas fa-crown"></i>
                <!-- duplicate for seamless loop -->
                <span>✦ motion architect ✦</span>
                <i class="fas fa-bolt"></i>
                <span>I engineer brand growth through cinematic motion</span>
                <i class="fas fa-chart-line"></i>
                <span>✦ strategic narratives ✦</span>
                <i class="fas fa-globe"></i>
                <span>elevating brands worldwide</span>
                <i class="fas fa-crown"></i>
            </div>
        </div>

        <!-- DOWNLOAD BUTTON (rectangle round) + fade -->
        <div class="fade-item item-3" style="display: flex; justify-content: center; margin: 1.8rem 0 1rem;">
            <button class="download-rect rect-round" id="megaDownloadBtn">
                <i class="fas fa-download"></i>   DOWNLOAD MOTION PACK   <i class="fas fa-star"></i>
            </button>
        </div>

        <!-- COPY LINK area (rectangle round) fade -->
        <div class="copy-area fade-item item-4">
            <input type="text" id="megaLinkInput" value="https://mega.nz/#P!AgCsjwPNllpkd3sM5EII2hrZBzrsopl_lvD0tTCCv8H3mGbNKBfgJuKnMqyoQwRf656A3LbxhBrKPkjjd2en73KJdEOHOWl7S2gvnaglawpG-VpOT8v_BA" readonly>
            <button class="copy-btn rect-round" id="copyLinkBtn"><i class="fas fa-copy"></i> Copy link</button>
        </div>

        <!-- optional link display -->
        <div class="link-hint-rect fade-item item-5">
            <i class="fas fa-link" style="margin-right: 15px; color: #6fffe5;"></i> Direct MEGA · click download or copy
        </div>

        <!-- contact row (WhatsApp / email) rectangle round edges -->
        <div class="contact-row fade-item item-6">
            <a href="https://wa.me/256771794634?text=Hi%20eDesign%20Studio!%20I'm%20interested%20in%20the%20Mega%20Motion%20Pack%20and%20brand%20growth%20services." target="_blank" class="contact-btn rect-round">
                <i class="fab fa-whatsapp"></i> +256 771 794634
            </a>
            <a href="mailto:habra@editsnation.com?subject=Motion%20pack%20inquiry%20%7C%20eDesign%20Studio&body=Hello%2C%20I%20saw%20your%20motion%20pack%20page..." class="contact-btn rect-round">
                <i class="far fa-envelope"></i> habra@editsnation.com
            </a>
        </div>

        <!-- footer / credibility fade -->
        <div class="footer-note fade-item item-7">
            <strong>eDesign Studio</strong> · where motion systems transform brands
        </div>
    </div>

    <script>
        (function() {
            const megaLink = "https://mega.nz/#P!AgCsjwPNllpkd3sM5EII2hrZBzrsopl_lvD0tTCCv8H3mGbNKBfgJuKnMqyoQwRf656A3LbxhBrKPkjjd2en73KJdEOHOWl7S2gvnaglawpG-VpOT8v_BA";

            // download button
            const downloadBtn = document.getElementById('megaDownloadBtn');
            downloadBtn.addEventListener('click', (e) => {
                e.preventDefault();
                window.open(megaLink, '_blank');
                downloadBtn.style.transform = 'scale(0.98)';
                setTimeout(() => downloadBtn.style.transform = '', 150);
            });

            // copy link
            const copyBtn = document.getElementById('copyLinkBtn');
            const linkInput = document.getElementById('megaLinkInput');
            copyBtn.addEventListener('click', () => {
                linkInput.select();
                navigator.clipboard.writeText(megaLink).then(() => {
                    const original = copyBtn.innerHTML;
                    copyBtn.innerHTML = '<i class="fas fa-check"></i> Copied!';
                    copyBtn.style.background = '#259f8f';
                    setTimeout(() => {
                        copyBtn.innerHTML = original;
                        copyBtn.style.background = '#118b7e';
                    }, 1800);
                }).catch(() => alert('Press Ctrl+C to copy'));
            });

            linkInput.addEventListener('focus', () => linkInput.select());
        })();
    </script>
    <!-- tiny extra: glassmorphism and rounded consistency -->
    <style>
        /* all buttons rectangle with round edges (already applied) */
        .contact-btn, .download-rect, .copy-btn, .nav-logo, .marquee-glass, .copy-area, .link-hint-rect {
            transition: all 0.3s ease, transform 0.2s, background 0.2s;
        }
        .download-rect:active { transform: scale(0.96); }
        .fa-whatsapp, .fa-envelope { filter: drop-shadow(0 0 8px #6affd6); }
    </style>
</body>
</html>
