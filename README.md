<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Shavkatjon Yuldashev | Data Scientist</title>
    <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --void-black: #050505;
            --industrial-grey: #E5E5E5;
            --glyph-cyan: #00F5FF;
            --glyph-white: #FFFFFF;
        }

        body {
            font-family: 'JetBrains Mono', monospace;
            background-attachment: fixed;
            background-size: 40px 40px;
            transition: background-color 0.3s ease;
            overflow-x: hidden;
            cursor: crosshair;
        }

        body.dark {
            background-color: var(--void-black);
            background-image: 
                linear-gradient(to right, rgba(255, 255, 255, 0.1) 1px, transparent 1px),
                linear-gradient(to bottom, rgba(255, 255, 255, 0.1) 1px, transparent 1px);
            color: white;
        }

        body.light {
            background-color: var(--industrial-grey);
            background-image: 
                linear-gradient(to right, rgba(42, 42, 42, 0.15) 1px, transparent 1px),
                linear-gradient(to bottom, rgba(42, 42, 42, 0.15) 1px, transparent 1px);
            color: #1a1a1a;
        }

        body.dark::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-size: 40px 40px;
            background-position: 20px 20px;
            pointer-events: none;
            z-index: 0;
            background-image: 
                repeating-linear-gradient(0deg, transparent, transparent 19px, rgba(255, 255, 255, 0.2) 19px, rgba(255, 255, 255, 0.2) 21px, transparent 21px, transparent 40px),
                repeating-linear-gradient(90deg, transparent, transparent 19px, rgba(255, 255, 255, 0.2) 19px, rgba(255, 255, 255, 0.2) 21px, transparent 21px, transparent 40px);
        }

        body.light::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-size: 40px 40px;
            background-position: 20px 20px;
            pointer-events: none;
            z-index: 0;
            background-image: 
                repeating-linear-gradient(0deg, transparent, transparent 19px, rgba(42, 42, 42, 0.25) 19px, rgba(42, 42, 42, 0.25) 21px, transparent 21px, transparent 40px),
                repeating-linear-gradient(90deg, transparent, transparent 19px, rgba(42, 42, 42, 0.25) 19px, rgba(42, 42, 42, 0.25) 21px, transparent 21px, transparent 40px);
        }

        .glass {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(24px) saturate(180%);
            -webkit-backdrop-filter: blur(24px) saturate(180%);
            border: 1px solid rgba(255, 255, 255, 0.1);
            box-shadow: 
                0 8px 32px 0 rgba(0, 0, 0, 0.37),
                inset 0 1px 0 0 rgba(255, 255, 255, 0.1);
        }

        .light .glass {
            background: rgba(255, 255, 255, 0.6);
            border: 1px solid rgba(42, 42, 42, 0.15);
            box-shadow: 
                0 8px 32px 0 rgba(0, 0, 0, 0.1),
                inset 0 1px 0 0 rgba(255, 255, 255, 0.8);
        }

        .dot-matrix {
            font-family: 'JetBrains Mono', monospace;
            font-weight: 700;
            letter-spacing: 0.15em;
            text-transform: uppercase;
            text-shadow: 
                0 0 1px currentColor,
                1px 0 1px currentColor,
                -1px 0 1px currentColor,
                0 1px 1px currentColor,
                0 -1px 1px currentColor;
        }

        @keyframes glitch {
            0% { transform: translate(0); }
            20% { transform: translate(-2px, 2px); }
            40% { transform: translate(-2px, -2px); }
            60% { transform: translate(2px, 2px); }
            80% { transform: translate(2px, -2px); }
            100% { transform: translate(0); }
        }

        .glitch-active {
            animation: glitch 0.2s linear 3;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(5deg); }
        }

        @keyframes glow-pulse {
            0%, 100% { opacity: 1; filter: brightness(1); }
            50% { opacity: 0.8; filter: brightness(1.5); }
        }

        @keyframes rotate {
            from { transform: rotateY(0deg); }
            to { transform: rotateY(360deg); }
        }

        .floating-graph {
            animation: float 6s ease-in-out infinite;
            position: absolute;
            opacity: 0.3;
        }

        .floating-graph svg {
            animation: rotate 20s linear infinite;
            transform-style: preserve-3d;
        }

        /* Hero Section */
        .hero {
            position: relative;
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
        }

        .hero-content {
            position: relative;
            z-index: 10;
            text-align: center;
            padding: 2rem;
        }

        .hero-name {
            font-size: clamp(2rem, 8vw, 6rem);
            margin-bottom: 2rem;
            color: white;
        }

        .hero-title {
            display: inline-block;
            padding: 1rem 2rem;
            margin-bottom: 3rem;
        }

        .status-dot {
            width: 8px;
            height: 8px;
            border-radius: 50%;
            background: var(--glyph-cyan);
            display: inline-block;
            animation: glow-pulse 2s ease-in-out infinite;
        }

        .title-text {
            font-size: clamp(0.875rem, 2vw, 1.5rem);
            font-weight: 700;
            letter-spacing: 0.3em;
            color: white;
            margin: 0 1rem;
        }

        .subtitle {
            font-size: 0.75rem;
            color: #999;
            margin-top: 0.5rem;
            letter-spacing: 0.2em;
        }

        /* Theme Toggle */
        .theme-toggle {
            position: fixed;
            top: 2rem;
            right: 2rem;
            z-index: 1000;
            display: flex;
            align-items: center;
            gap: 1rem;
            padding: 1rem 1.5rem;
            border-radius: 9999px;
        }

        .theme-label {
            font-size: 0.75rem;
            color: #999;
            letter-spacing: 0.2em;
        }

        .dial {
            width: 64px;
            height: 64px;
            border-radius: 50%;
            background: linear-gradient(135deg, #4a4a4a, #3a3a3a, #5a5a5a);
            position: relative;
            cursor: pointer;
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.5);
            transition: transform 0.3s ease;
        }

        .dial:hover {
            transform: scale(1.05);
        }

        .dial::before {
            content: '';
            position: absolute;
            inset: 8px;
            border-radius: 50%;
            background: linear-gradient(135deg, #5a5a5a, #4a4a4a, #3a3a3a);
        }

        .dial::after {
            content: '';
            position: absolute;
            inset: 16px;
            border-radius: 50%;
            background: linear-gradient(135deg, #3a3a3a, #2a2a2a, #4a4a4a);
            box-shadow: inset 0 2px 4px rgba(0, 0, 0, 0.5);
        }

        .dial-indicator {
            position: absolute;
            top: 8px;
            left: 50%;
            transform: translateX(-50%);
            width: 2px;
            height: 16px;
            background: var(--glyph-cyan);
            box-shadow: 0 0 8px var(--glyph-cyan);
            z-index: 10;
            transition: transform 0.5s cubic-bezier(0.68, -0.55, 0.265, 1.55);
        }

        .dial.rotated .dial-indicator {
            transform: translateX(-50%) rotate(180deg);
            transform-origin: center 28px;
        }

        .dial-icon {
            position: absolute;
            inset: 0;
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 5;
            color: var(--glyph-cyan);
        }

        /* Social Dock */
        .social-dock {
            position: fixed;
            bottom: 2rem;
            right: 2rem;
            z-index: 1000;
            padding: 1rem 1.5rem;
            border-radius: 9999px;
        }

        .social-links {
            display: flex;
            gap: 1.5rem;
            align-items: center;
        }

        .social-link {
            color: white;
            transition: all 0.3s ease;
            position: relative;
            width: 32px;
            height: 32px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .social-link:hover {
            color: var(--glyph-cyan);
            transform: scale(1.1);
        }

        .social-link::before {
            content: '';
            position: absolute;
            inset: -8px;
            border-radius: 50%;
            background: radial-gradient(circle, var(--glyph-cyan) 0%, transparent 70%);
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .social-link:hover::before {
            opacity: 0.6;
            animation: glow-pulse 1.5s ease-in-out infinite;
        }

        /* Portfolio Section */
        .portfolio {
            padding: 8rem 0;
            position: relative;
            z-index: 10;
        }

        .portfolio-header {
            max-width: 1200px;
            margin: 0 auto 4rem;
            padding: 0 2rem;
        }

        .section-label {
            display: inline-block;
            padding: 0.5rem 1.5rem;
            margin-bottom: 1rem;
            font-size: 0.875rem;
            color: #999;
            letter-spacing: 0.2em;
        }

        .section-title {
            font-size: clamp(2rem, 6vw, 4rem);
            margin-bottom: 1rem;
            color: white;
        }

        .section-description {
            color: #999;
            max-width: 600px;
        }

        .portfolio-scroll {
            display: flex;
            gap: 2rem;
            padding: 0 2rem;
            overflow-x: auto;
            overflow-y: hidden;
            scroll-behavior: smooth;
        }

        .portfolio-scroll::-webkit-scrollbar {
            height: 12px;
        }

        .portfolio-scroll::-webkit-scrollbar-track {
            background: transparent;
        }

        .portfolio-scroll::-webkit-scrollbar-thumb {
            background: rgba(255, 255, 255, 0.2);
            border-radius: 6px;
        }

        .portfolio-scroll::-webkit-scrollbar-thumb:hover {
            background: var(--glyph-cyan);
        }

        .project-card {
            flex-shrink: 0;
            width: 320px;
            height: 600px;
            border-radius: 24px;
            overflow: hidden;
            transition: all 0.3s ease;
        }

        .project-card:hover {
            transform: translateY(-8px);
            border-color: rgba(0, 245, 255, 0.3);
        }

        .card-header {
            padding: 1.5rem;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }

        .card-title {
            font-size: 1.25rem;
            margin-bottom: 0.75rem;
            color: white;
        }

        .status-tag {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            padding: 0.5rem 1rem;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 9999px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            font-size: 0.75rem;
            color: #ccc;
        }

        .status-indicator {
            width: 6px;
            height: 6px;
            border-radius: 50%;
            background: var(--glyph-cyan);
            animation: glow-pulse 2s ease-in-out infinite;
        }

        .category {
            margin-top: 0.75rem;
            font-size: 0.75rem;
            color: #666;
            letter-spacing: 0.1em;
        }

        .card-visual {
            height: 256px;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(to bottom, transparent, rgba(0, 0, 0, 0.2));
            position: relative;
        }

        .card-visual svg {
            filter: drop-shadow(0 0 20px rgba(0, 245, 255, 0.5));
        }

        .card-footer {
            padding: 1.5rem;
        }

        .tech-stack {
            margin-bottom: 1.5rem;
        }

        .tech-label {
            font-size: 0.75rem;
            color: #666;
            margin-bottom: 0.5rem;
            letter-spacing: 0.1em;
        }

        .tech-chips {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
        }

        .tech-chip {
            padding: 0.25rem 0.75rem;
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 4px;
            font-size: 0.75rem;
            color: #ccc;
        }

        .metrics {
            margin-bottom: 1.5rem;
        }

        .metrics-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 0.5rem;
            text-align: center;
        }

        .metric-value {
            font-size: 1.125rem;
            font-weight: 700;
            color: var(--glyph-cyan);
        }

        .metric-label {
            font-size: 0.625rem;
            color: #666;
            text-transform: uppercase;
            letter-spacing: 0.1em;
        }

        .action-button {
            width: 100%;
            padding: 0.75rem 1rem;
            border-radius: 12px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            display: flex;
            align-items: center;
            justify-content: space-between;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .action-button:hover {
            border-color: rgba(0, 245, 255, 0.5);
            background: rgba(0, 245, 255, 0.1);
        }

        .button-text {
            font-size: 0.875rem;
            color: white;
            letter-spacing: 0.1em;
        }

        .toggle-switch {
            width: 48px;
            height: 24px;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 9999px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            position: relative;
            transition: all 0.3s ease;
        }

        .toggle-knob {
            position: absolute;
            top: 4px;
            left: 4px;
            width: 16px;
            height: 16px;
            background: var(--glyph-cyan);
            border-radius: 50%;
            transition: transform 0.3s cubic-bezier(0.68, -0.55, 0.265, 1.55);
        }

        .action-button:hover .toggle-knob {
            transform: translateX(24px);
        }
    </style>
</head>
<body class="dark">
    <!-- Theme Toggle -->
    <div class="theme-toggle glass">
        <span class="theme-label">MODE</span>
        <div class="dial" onclick="toggleTheme()">
            <div class="dial-indicator"></div>
            <div class="dial-icon">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <circle cx="12" cy="12" r="4"/>
                    <path d="M12 2v2m0 16v2M4.93 4.93l1.41 1.41m11.32 11.32l1.41 1.41M2 12h2m16 0h2M4.93 19.07l1.41-1.41m11.32-11.32l1.41-1.41"/>
                </svg>
            </div>
        </div>
        <span class="theme-label theme-mode">VOID</span>
    </div>

    <!-- Social Dock -->
    <div class="social-dock glass">
        <div class="social-links">
            <span class="theme-label">CONNECT</span>
            <a href="https://github.com" target="_blank" class="social-link">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
                    <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
                </svg>
            </a>
            <a href="https://linkedin.com" target="_blank" class="social-link">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
                    <path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/>
                </svg>
            </a>
            <a href="mailto:example@email.com" class="social-link">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/>
                    <polyline points="22,6 12,13 2,6"/>
                </svg>
            </a>
        </div>
    </div>

    <!-- Hero Section -->
    <section class="hero">
        <!-- Floating Graphs -->
        <div class="floating-graph glass" style="top: 10%; left: 5%; padding: 1.5rem; border-radius: 1rem;">
            <svg width="120" height="120" viewBox="0 0 120 120">
                <circle cx="60" cy="60" r="50" fill="none" stroke="currentColor" stroke-width="1" opacity="0.3" style="color: var(--glyph-cyan)"/>
                <ellipse cx="60" cy="60" rx="50" ry="20" fill="none" stroke="currentColor" stroke-width="1" opacity="0.4" style="color: var(--glyph-cyan)"/>
                <ellipse cx="60" cy="60" rx="20" ry="50" fill="none" stroke="currentColor" stroke-width="1" opacity="0.4" style="color: var(--glyph-cyan)"/>
            </svg>
        </div>

        <div class="floating-graph glass" style="top: 25%; right: 10%; padding: 1.5rem; border-radius: 1rem; animation-delay: 1s;">
            <svg width="100" height="100" viewBox="0 0 100 100">
                <circle cx="25" cy="70" r="3" fill="var(--glyph-cyan)" opacity="0.8"/>
                <circle cx="40" cy="50" r="3" fill="var(--glyph-cyan)" opacity="0.8"/>
                <circle cx="55" cy="60" r="3" fill="var(--glyph-cyan)" opacity="0.8"/>
                <circle cx="70" cy="35" r="3" fill="var(--glyph-cyan)" opacity="0.8"/>
                <circle cx="85" cy="40" r="3" fill="var(--glyph-cyan)" opacity="0.8"/>
            </svg>
        </div>

        <div class="hero-content">
            <h1 class="hero-name dot-matrix" id="heroName">SHAVKATJON YULDASHEV</h1>
            <div class="hero-title glass">
                <div style="display: flex; align-items: center; justify-content: center; gap: 1rem;">
                    <div class="status-dot"></div>
                    <span class="title-text">DATA SCIENTIST</span>
                    <div class="status-dot"></div>
                </div>
                <div class="subtitle">SYS.CLASSIFICATION: ML/AI SPECIALIST</div>
            </div>
        </div>
    </section>

    <!-- Portfolio Section -->
    <section class="portfolio">
        <div class="portfolio-header">
            <div class="section-label glass">PORTFOLIO</div>
            <h2 class="section-title dot-matrix">DEPLOYED SYSTEMS</h2>
            <p class="section-description">Production-grade machine learning systems engineered for performance, scalability, and reliability.</p>
        </div>

        <div class="portfolio-scroll">
            <!-- Project 1 -->
            <div class="project-card glass">
                <div class="card-header">
                    <h3 class="card-title dot-matrix">NEURAL VISION</h3>
                    <div class="status-tag">
                        <div class="status-indicator"></div>
                        <span>SYS.ONLINE</span>
                    </div>
                    <div class="category">DEEP LEARNING</div>
                </div>
                <div class="card-visual">
                    <svg width="120" height="120" viewBox="0 0 120 120">
                        <circle cx="60" cy="20" r="6" fill="none" stroke="var(--glyph-cyan)" stroke-width="2"/>
                        <circle cx="30" cy="60" r="6" fill="none" stroke="var(--glyph-cyan)" stroke-width="2"/>
                        <circle cx="90" cy="60" r="6" fill="none" stroke="var(--glyph-cyan)" stroke-width="2"/>
                        <circle cx="20" cy="100" r="6" fill="none" stroke="var(--glyph-cyan)" stroke-width="2"/>
                        <circle cx="60" cy="100" r="6" fill="none" stroke="var(--glyph-cyan)" stroke-width="2"/>
                        <circle cx="100" cy="100" r="6" fill="none" stroke="var(--glyph-cyan)" stroke-width="2"/>
                        <line x1="60" y1="20" x2="30" y2="60" stroke="var(--glyph-cyan)" stroke-width="1" opacity="0.3"/>
                        <line x1="60" y1="20" x2="90" y2="60" stroke="var(--glyph-cyan)" stroke-width="1" opacity="0.3"/>
                        <line x1="30" y1="60" x2="20" y2="100" stroke="var(--glyph-cyan)" stroke-width="1" opacity="0.3"/>
                        <line x1="30" y1="60" x2="60" y2="100" stroke="var(--glyph-cyan)" stroke-width="1" opacity="0.3"/>
                        <line x1="90" y1="60" x2="60" y2="100" stroke="var(--glyph-cyan)" stroke-width="1" opacity="0.3"/>
                        <line x1="90" y1="60" x2="100" y2="100" stroke="var(--glyph-cyan)" stroke-width="1" opacity="0.3"/>
                    </svg>
                </div>
                <div class="card-footer">
                    <div class="tech-stack">
                        <div class="tech-label">TECH STACK</div>
                        <div class="tech-chips">
                            <span class="tech-chip">Python</span>
                            <span class="tech-chip">TensorFlow</span>
                            <span class="tech-chip">OpenCV</span>
                            <span class="tech-chip">Docker</span>
                        </div>
                    </div>
                    <div class="metrics">
                        <div class="tech-label">TELEMETRY</div>
                        <div class="metrics-grid">
                            <div>
                                <div class="metric-value">99.8%</div>
                                <div class="metric-label">Accuracy</div>
                            </div>
                            <div>
                                <div class="metric-value">12ms</div>
                                <div class="metric-label">Latency</div>
                            </div>
                            <div>
                                <div class="metric-value">ResNet</div>
                                <div class="metric-label">Model</div>
                            </div>
                        </div>
                    </div>
                    <div class="action-button glass">
                        <span class="button-text">OPEN PROJECT</span>
                        <div class="toggle-switch">
                            <div class="toggle-knob"></div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Project 2 -->
            <div class="project-card glass">
                <div class="card-header">
                    <h3 class="card-title dot-matrix">MARKET ORACLE</h3>
                    <div class="status-tag">
                        <div class="status-indicator"></div>
                        <span>SYS.ACTIVE</span>
                    </div>
                    <div class="category">FORECASTING</div>
                </div>
                <div class="card-visual">
                    <svg width="140" height="100" viewBox="0 0 140 100">
                        <rect x="20" y="60" width="15" height="35" fill="var(--glyph-cyan)" opacity="0.4"/>
                        <rect x="45" y="45" width="15" height="50" fill="var(--glyph-cyan)" opacity="0.4"/>
                        <rect x="70" y="55" width="15" height="40" fill="var(--glyph-cyan)" opacity="0.4"/>
                        <rect x="95" y="30" width="15" height="65" fill="var(--glyph-cyan)" opacity="0.4"/>
                        <rect x="120" y="40" width="15" height="55" fill="var(--glyph-cyan)" opacity="0.4"/>
                    </svg>
                </div>
                <div class="card-footer">
                    <div class="tech-stack">
                        <div class="tech-label">TECH STACK</div>
                        <div class="tech-chips">
                            <span class="tech-chip">Python</span>
                            <span class="tech-chip">PyTorch</span>
                            <span class="tech-chip">LSTM</span>
                            <span class="tech-chip">AWS</span>
                        </div>
                    </div>
                    <div class="metrics">
                        <div class="tech-label">TELEMETRY</div>
                        <div class="metrics-grid">
                            <div>
                                <div class="metric-value">3.2%</div>
                                <div class="metric-label">MAPE</div>
                            </div>
                            <div>
                                <div class="metric-value">0.94</div>
                                <div class="metric-label">R²</div>
                            </div>
                            <div>
                                <div class="metric-value">47</div>
                                <div class="metric-label">Features</div>
                            </div>
                        </div>
                    </div>
                    <div class="action-button glass">
                        <span class="button-text">OPEN PROJECT</span>
                        <div class="toggle-switch">
                            <div class="toggle-knob"></div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Project 3 -->
            <div class="project-card glass">
                <div class="card-header">
                    <h3 class="card-title dot-matrix">SENTIMENT CORE</h3>
                    <div class="status-tag">
                        <div class="status-indicator"></div>
                        <span>SYS.DEPLOYED</span>
                    </div>
                    <div class="category">NLP</div>
                </div>
                <div class="card-visual">
                    <svg width="120" height="120" viewBox="0 0 120 120">
                        <circle cx="25" cy="70" r="2" fill="var(--glyph-cyan)"/>
                        <circle cx="40" cy="50" r="2" fill="var(--glyph-cyan)"/>
                        <circle cx="55" cy="65" r="2" fill="var(--glyph-cyan)"/>
                        <circle cx="70" cy="40" r="2" fill="var(--glyph-cyan)"/>
                        <circle cx="85" cy="55" r="2" fill="var(--glyph-cyan)"/>
                        <circle cx="95" cy="35" r="2" fill="var(--glyph-cyan)"/>
                    </svg>
                </div>
                <div class="card-footer">
                    <div class="tech-stack">
                        <div class="tech-label">TECH STACK</div>
                        <div class="tech-chips">
                            <span class="tech-chip">Python</span>
                            <span class="tech-chip">BERT</span>
                            <span class="tech-chip">FastAPI</span>
                            <span class="tech-chip">Redis</span>
                        </div>
                    </div>
                    <div class="metrics">
                        <div class="tech-label">TELEMETRY</div>
                        <div class="metrics-grid">
                            <div>
                                <div class="metric-value">0.96</div>
                                <div class="metric-label">F1 Score</div>
                            </div>
                            <div>
                                <div class="metric-value">10K/s</div>
                                <div class="metric-label">Speed</div>
                            </div>
                            <div>
                                <div class="metric-value">12</div>
                                <div class="metric-label">Languages</div>
                            </div>
                        </div>
                    </div>
                    <div class="action-button glass">
                        <span class="button-text">OPEN PROJECT</span>
                        <div class="toggle-switch">
                            <div class="toggle-knob"></div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Project 4 -->
            <div class="project-card glass">
                <div class="card-header">
                    <h3 class="card-title dot-matrix">CLUSTER MATRIX</h3>
                    <div class="status-tag">
                        <div class="status-indicator"></div>
                        <span>SYS.ONLINE</span>
                    </div>
                    <div class="category">CLUSTERING</div>
                </div>
                <div class="card-visual">
                    <svg width="120" height="120" viewBox="0 0 120 120">
                        <circle cx="60" cy="60" r="50" fill="none" stroke="var(--glyph-cyan)" stroke-width="1" opacity="0.3"/>
                        <circle cx="60" cy="60" r="35" fill="none" stroke="var(--glyph-cyan)" stroke-width="1" opacity="0.3"/>
                        <circle cx="60" cy="60" r="20" fill="none" stroke="var(--glyph-cyan)" stroke-width="1" opacity="0.3"/>
                        <circle cx="60" cy="25" r="3" fill="var(--glyph-cyan)"/>
                        <circle cx="85" cy="45" r="3" fill="var(--glyph-cyan)"/>
                        <circle cx="85" cy="75" r="3" fill="var(--glyph-cyan)"/>
                        <circle cx="60" cy="95" r="3" fill="var(--glyph-cyan)"/>
                        <circle cx="35" cy="75" r="3" fill="var(--glyph-cyan)"/>
                        <circle cx="35" cy="45" r="3" fill="var(--glyph-cyan)"/>
                    </svg>
                </div>
                <div class="card-footer">
                    <div class="tech-stack">
                        <div class="tech-label">TECH STACK</div>
                        <div class="tech-chips">
                            <span class="tech-chip">Python</span>
                            <span class="tech-chip">Scikit-learn</span>
                            <span class="tech-chip">K-Means</span>
                            <span class="tech-chip">PostgreSQL</span>
                        </div>
                    </div>
                    <div class="metrics">
                        <div class="tech-label">TELEMETRY</div>
                        <div class="metrics-grid">
                            <div>
                                <div class="metric-value">0.87</div>
                                <div class="metric-label">Silhouette</div>
                            </div>
                            <div>
                                <div class="metric-value">8</div>
                                <div class="metric-label">Clusters</div>
                            </div>
                            <div>
                                <div class="metric-value">2.4M</div>
                                <div class="metric-label">Records</div>
                            </div>
                        </div>
                    </div>
                    <div class="action-button glass">
                        <span class="button-text">OPEN PROJECT</span>
                        <div class="toggle-switch">
                            <div class="toggle-knob"></div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Spacer -->
            <div style="width: 2rem; flex-shrink: 0;"></div>
        </div>
    </section>

    <script>
        // Theme Toggle
        function toggleTheme() {
            const body = document.body;
            const dial = document.querySelector('.dial');
   <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Shavkatjon Yuldashev | Data Scientist</title>
    <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --void-black: #050505;
            --industrial-grey: #E5E5E5;
            --glyph-cyan: #00F5FF;
            --glyph-white: #FFFFFF;
        }

        body {
            font-family: 'JetBrains Mono', monospace;
            background-attachment: fixed;
            background-size: 40px 40px;
            transition: background-color 0.3s ease;
            overflow-x: hidden;
            cursor: crosshair;
        }

        body.dark {
            background-color: var(--void-black);
            background-image: 
                linear-gradient(to right, rgba(255, 255, 255, 0.1) 1px, transparent 1px),
                linear-gradient(to bottom, rgba(255, 255, 255, 0.1) 1px, transparent 1px);
            color: white;
        }

        body.light {
            background-color: var(--industrial-grey);
            background-image: 
                linear-gradient(to right, rgba(42, 42, 42, 0.15) 1px, transparent 1px),
                linear-gradient(to bottom, rgba(42, 42, 42, 0.15) 1px, transparent 1px);
            color: #1a1a1a;
        }

        body.dark::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-size: 40px 40px;
            background-position: 20px 20px;
            pointer-events: none;
            z-index: 0;
            background-image: 
                repeating-linear-gradient(0deg, transparent, transparent 19px, rgba(255, 255, 255, 0.2) 19px, rgba(255, 255, 255, 0.2) 21px, transparent 21px, transparent 40px),
                repeating-linear-gradient(90deg, transparent, transparent 19px, rgba(255, 255, 255, 0.2) 19px, rgba(255, 255, 255, 0.2) 21px, transparent 21px, transparent 40px);
        }

        body.light::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-size: 40px 40px;
            background-position: 20px 20px;
            pointer-events: none;
            z-index: 0;
            background-image: 
                repeating-linear-gradient(0deg, transparent, transparent 19px, rgba(42, 42, 42, 0.25) 19px, rgba(42, 42, 42, 0.25) 21px, transparent 21px, transparent 40px),
                repeating-linear-gradient(90deg, transparent, transparent 19px, rgba(42, 42, 42, 0.25) 19px, rgba(42, 42, 42, 0.25) 21px, transparent 21px, transparent 40px);
        }

        .glass {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(24px) saturate(180%);
            -webkit-backdrop-filter: blur(24px) saturate(180%);
            border: 1px solid rgba(255, 255, 255, 0.1);
            box-shadow: 
                0 8px 32px 0 rgba(0, 0, 0, 0.37),
                inset 0 1px 0 0 rgba(255, 255, 255, 0.1);
        }

        .light .glass {
            background: rgba(255, 255, 255, 0.6);
            border: 1px solid rgba(42, 42, 42, 0.15);
            box-shadow: 
                0 8px 32px 0 rgba(0, 0, 0, 0.1),
                inset 0 1px 0 0 rgba(255, 255, 255, 0.8);
        }

        .dot-matrix {
            font-family: 'JetBrains Mono', monospace;
            font-weight: 700;
            letter-spacing: 0.15em;
            text-transform: uppercase;
            text-shadow: 
                0 0 1px currentColor,
                1px 0 1px currentColor,
                -1px 0 1px currentColor,
                0 1px 1px currentColor,
                0 -1px 1px currentColor;
        }

        @keyframes glitch {
            0% { transform: translate(0); }
            20% { transform: translate(-2px, 2px); }
            40% { transform: translate(-2px, -2px); }
            60% { transform: translate(2px, 2px); }
            80% { transform: translate(2px, -2px); }
            100% { transform: translate(0); }
        }

        .glitch-active {
            animation: glitch 0.2s linear 3;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(5deg); }
        }

        @keyframes glow-pulse {
            0%, 100% { opacity: 1; filter: brightness(1); }
            50% { opacity: 0.8; filter: brightness(1.5); }
        }

        @keyframes rotate {
            from { transform: rotateY(0deg); }
            to { transform: rotateY(360deg); }
        }

        .floating-graph {
            animation: float 6s ease-in-out infinite;
            position: absolute;
            opacity: 0.3;
        }

        .floating-graph svg {
            animation: rotate 20s linear infinite;
            transform-style: preserve-3d;
        }

        /* Hero Section */
        .hero {
            position: relative;
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
        }

        .hero-content {
            position: relative;
            z-index: 10;
            text-align: center;
            padding: 2rem;
        }

        .hero-name {
            font-size: clamp(2rem, 8vw, 6rem);
            margin-bottom: 2rem;
            color: white;
        }

        .hero-title {
            display: inline-block;
            padding: 1rem 2rem;
            margin-bottom: 3rem;
        }

        .status-dot {
            width: 8px;
            height: 8px;
            border-radius: 50%;
            background: var(--glyph-cyan);
            display: inline-block;
            animation: glow-pulse 2s ease-in-out infinite;
        }

        .title-text {
            font-size: clamp(0.875rem, 2vw, 1.5rem);
            font-weight: 700;
            letter-spacing: 0.3em;
            color: white;
            margin: 0 1rem;
        }

        .subtitle {
            font-size: 0.75rem;
            color: #999;
            margin-top: 0.5rem;
            letter-spacing: 0.2em;
        }

        /* Theme Toggle */
        .theme-toggle {
            position: fixed;
            top: 2rem;
            right: 2rem;
            z-index: 1000;
            display: flex;
            align-items: center;
            gap: 1rem;
            padding: 1rem 1.5rem;
            border-radius: 9999px;
        }

        .theme-label {
            font-size: 0.75rem;
            color: #999;
            letter-spacing: 0.2em;
        }

        .dial {
            width: 64px;
            height: 64px;
            border-radius: 50%;
            background: linear-gradient(135deg, #4a4a4a, #3a3a3a, #5a5a5a);
            position: relative;
            cursor: pointer;
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.5);
            transition: transform 0.3s ease;
        }

        .dial:hover {
            transform: scale(1.05);
        }

        .dial::before {
            content: '';
            position: absolute;
            inset: 8px;
            border-radius: 50%;
            background: linear-gradient(135deg, #5a5a5a, #4a4a4a, #3a3a3a);
        }

        .dial::after {
            content: '';
            position: absolute;
            inset: 16px;
            border-radius: 50%;
            background: linear-gradient(135deg, #3a3a3a, #2a2a2a, #4a4a4a);
            box-shadow: inset 0 2px 4px rgba(0, 0, 0, 0.5);
        }

        .dial-indicator {
            position: absolute;
            top: 8px;
            left: 50%;
            transform: translateX(-50%);
            width: 2px;
            height: 16px;
            background: var(--glyph-cyan);
            box-shadow: 0 0 8px var(--glyph-cyan);
            z-index: 10;
            transition: transform 0.5s cubic-bezier(0.68, -0.55, 0.265, 1.55);
        }

        .dial.rotated .dial-indicator {
            transform: translateX(-50%) rotate(180deg);
            transform-origin: center 28px;
        }

        .dial-icon {
            position: absolute;
            inset: 0;
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 5;
            color: var(--glyph-cyan);
        }

        /* Social Dock */
        .social-dock {
            position: fixed;
            bottom: 2rem;
            right: 2rem;
            z-index: 1000;
            padding: 1rem 1.5rem;
            border-radius: 9999px;
        }

        .social-links {
            display: flex;
            gap: 1.5rem;
            align-items: center;
        }

        .social-link {
            color: white;
            transition: all 0.3s ease;
            position: relative;
            width: 32px;
            height: 32px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .social-link:hover {
            color: var(--glyph-cyan);
            transform: scale(1.1);
        }

        .social-link::before {
            content: '';
            position: absolute;
            inset: -8px;
            border-radius: 50%;
            background: radial-gradient(circle, var(--glyph-cyan) 0%, transparent 70%);
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .social-link:hover::before {
            opacity: 0.6;
            animation: glow-pulse 1.5s ease-in-out infinite;
        }

        /* Portfolio Section */
        .portfolio {
            padding: 8rem 0;
            position: relative;
            z-index: 10;
        }

        .portfolio-header {
            max-width: 1200px;
            margin: 0 auto 4rem;
            padding: 0 2rem;
        }

        .section-label {
            display: inline-block;
            padding: 0.5rem 1.5rem;
            margin-bottom: 1rem;
            font-size: 0.875rem;
            color: #999;
            letter-spacing: 0.2em;
        }

        .section-title {
            font-size: clamp(2rem, 6vw, 4rem);
            margin-bottom: 1rem;
            color: white;
        }

        .section-description {
            color: #999;
            max-width: 600px;
        }

        .portfolio-scroll {
            display: flex;
            gap: 2rem;
            padding: 0 2rem;
            overflow-x: auto;
            overflow-y: hidden;
            scroll-behavior: smooth;
        }

        .portfolio-scroll::-webkit-scrollbar {
            height: 12px;
        }

        .portfolio-scroll::-webkit-scrollbar-track {
            background: transparent;
        }

        .portfolio-scroll::-webkit-scrollbar-thumb {
            background: rgba(255, 255, 255, 0.2);
            border-radius: 6px;
        }

        .portfolio-scroll::-webkit-scrollbar-thumb:hover {
            background: var(--glyph-cyan);
        }

        .project-card {
            flex-shrink: 0;
            width: 320px;
            height: 600px;
            border-radius: 24px;
            overflow: hidden;
            transition: all 0.3s ease;
        }

        .project-card:hover {
            transform: translateY(-8px);
            border-color: rgba(0, 245, 255, 0.3);
        }

        .card-header {
            padding: 1.5rem;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }

        .card-title {
            font-size: 1.25rem;
            margin-bottom: 0.75rem;
            color: white;
        }

        .status-tag {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            padding: 0.5rem 1rem;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 9999px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            font-size: 0.75rem;
            color: #ccc;
        }

        .status-indicator {
            width: 6px;
            height: 6px;
            border-radius: 50%;
            background: var(--glyph-cyan);
            animation: glow-pulse 2s ease-in-out infinite;
        }

        .category {
            margin-top: 0.75rem;
            font-size: 0.75rem;
            color: #666;
            letter-spacing: 0.1em;
        }

        .card-visual {
            height: 256px;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(to bottom, transparent, rgba(0, 0, 0, 0.2));
            position: relative;
        }

        .card-visual svg {
            filter: drop-shadow(0 0 20px rgba(0, 245, 255, 0.5));
        }

        .card-footer {
            padding: 1.5rem;
        }

        .tech-stack {
            margin-bottom: 1.5rem;
        }

        .tech-label {
            font-size: 0.75rem;
            color: #666;
            margin-bottom: 0.5rem;
            letter-spacing: 0.1em;
        }

        .tech-chips {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
        }

        .tech-chip {
            padding: 0.25rem 0.75rem;
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 4px;
            font-size: 0.75rem;
            color: #ccc;
        }

        .metrics {
            margin-bottom: 1.5rem;
        }

        .metrics-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 0.5rem;
            text-align: center;
        }

        .metric-value {
            font-size: 1.125rem;
            font-weight: 700;
            color: var(--glyph-cyan);
        }

        .metric-label {
            font-size: 0.625rem;
            color: #666;
            text-transform: uppercase;
            letter-spacing: 0.1em;
        }

        .action-button {
            width: 100%;
            padding: 0.75rem 1rem;
            border-radius: 12px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            display: flex;
            align-items: center;
            justify-content: space-between;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .action-button:hover {
            border-color: rgba(0, 245, 255, 0.5);
            background: rgba(0, 245, 255, 0.1);
        }

        .button-text {
            font-size: 0.875rem;
            color: white;
            letter-spacing: 0.1em;
        }

        .toggle-switch {
            width: 48px;
            height: 24px;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 9999px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            position: relative;
            transition: all 0.3s ease;
        }

        .toggle-knob {
            position: absolute;
            top: 4px;
            left: 4px;
            width: 16px;
            height: 16px;
            background: var(--glyph-cyan);
            border-radius: 50%;
            transition: transform 0.3s cubic-bezier(0.68, -0.55, 0.265, 1.55);
        }

        .action-button:hover .toggle-knob {
            transform: translateX(24px);
        }
    </style>
</head>
<body class="dark">
    <!-- Theme Toggle -->
    <div class="theme-toggle glass">
        <span class="theme-label">MODE</span>
        <div class="dial" onclick="toggleTheme()">
            <div class="dial-indicator"></div>
            <div class="dial-icon">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <circle cx="12" cy="12" r="4"/>
                    <path d="M12 2v2m0 16v2M4.93 4.93l1.41 1.41m11.32 11.32l1.41 1.41M2 12h2m16 0h2M4.93 19.07l1.41-1.41m11.32-11.32l1.41-1.41"/>
                </svg>
            </div>
        </div>
        <span class="theme-label theme-mode">VOID</span>
    </div>

    <!-- Social Dock -->
    <div class="social-dock glass">
        <div class="social-links">
            <span class="theme-label">CONNECT</span>
            <a href="https://github.com" target="_blank" class="social-link">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
                    <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
                </svg>
            </a>
            <a href="https://linkedin.com" target="_blank" class="social-link">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
                    <path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/>
                </svg>
            </a>
            <a href="mailto:example@email.com" class="social-link">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/>
                    <polyline points="22,6 12,13 2,6"/>
                </svg>
            </a>
        </div>
    </div>

    <!-- Hero Section -->
    <section class="hero">
        <!-- Floating Graphs -->
        <div class="floating-graph glass" style="top: 10%; left: 5%; padding: 1.5rem; border-radius: 1rem;">
            <svg width="120" height="120" viewBox="0 0 120 120">
                <circle cx="60" cy="60" r="50" fill="none" stroke="currentColor" stroke-width="1" opacity="0.3" style="color: var(--glyph-cyan)"/>
                <ellipse cx="60" cy="60" rx="50" ry="20" fill="none" stroke="currentColor" stroke-width="1" opacity="0.4" style="color: var(--glyph-cyan)"/>
                <ellipse cx="60" cy="60" rx="20" ry="50" fill="none" stroke="currentColor" stroke-width="1" opacity="0.4" style="color: var(--glyph-cyan)"/>
            </svg>
        </div>

        <div class="floating-graph glass" style="top: 25%; right: 10%; padding: 1.5rem; border-radius: 1rem; animation-delay: 1s;">
            <svg width="100" height="100" viewBox="0 0 100 100">
                <circle cx="25" cy="70" r="3" fill="var(--glyph-cyan)" opacity="0.8"/>
                <circle cx="40" cy="50" r="3" fill="var(--glyph-cyan)" opacity="0.8"/>
                <circle cx="55" cy="60" r="3" fill="var(--glyph-cyan)" opacity="0.8"/>
                <circle cx="70" cy="35" r="3" fill="var(--glyph-cyan)" opacity="0.8"/>
                <circle cx="85" cy="40" r="3" fill="var(--glyph-cyan)" opacity="0.8"/>
            </svg>
        </div>

        <div class="hero-content">
            <h1 class="hero-name dot-matrix" id="heroName">SHAVKATJON YULDASHEV</h1>
            <div class="hero-title glass">
                <div style="display: flex; align-items: center; justify-content: center; gap: 1rem;">
                    <div class="status-dot"></div>
                    <span class="title-text">DATA SCIENTIST</span>
                    <div class="status-dot"></div>
                </div>
                <div class="subtitle">SYS.CLASSIFICATION: ML/AI SPECIALIST</div>
            </div>
        </div>
    </section>

    <!-- Portfolio Section -->
    <section class="portfolio">
        <div class="portfolio-header">
            <div class="section-label glass">PORTFOLIO</div>
            <h2 class="section-title dot-matrix">DEPLOYED SYSTEMS</h2>
            <p class="section-description">Production-grade machine learning systems engineered for performance, scalability, and reliability.</p>
        </div>

        <div class="portfolio-scroll">
            <!-- Project 1 -->
            <div class="project-card glass">
                <div class="card-header">
                    <h3 class="card-title dot-matrix">NEURAL VISION</h3>
                    <div class="status-tag">
                        <div class="status-indicator"></div>
                        <span>SYS.ONLINE</span>
                    </div>
                    <div class="category">DEEP LEARNING</div>
                </div>
                <div class="card-visual">
                    <svg width="120" height="120" viewBox="0 0 120 120">
                        <circle cx="60" cy="20" r="6" fill="none" stroke="var(--glyph-cyan)" stroke-width="2"/>
                        <circle cx="30" cy="60" r="6" fill="none" stroke="var(--glyph-cyan)" stroke-width="2"/>
                        <circle cx="90" cy="60" r="6" fill="none" stroke="var(--glyph-cyan)" stroke-width="2"/>
                        <circle cx="20" cy="100" r="6" fill="none" stroke="var(--glyph-cyan)" stroke-width="2"/>
                        <circle cx="60" cy="100" r="6" fill="none" stroke="var(--glyph-cyan)" stroke-width="2"/>
                        <circle cx="100" cy="100" r="6" fill="none" stroke="var(--glyph-cyan)" stroke-width="2"/>
                        <line x1="60" y1="20" x2="30" y2="60" stroke="var(--glyph-cyan)" stroke-width="1" opacity="0.3"/>
                        <line x1="60" y1="20" x2="90" y2="60" stroke="var(--glyph-cyan)" stroke-width="1" opacity="0.3"/>
                        <line x1="30" y1="60" x2="20" y2="100" stroke="var(--glyph-cyan)" stroke-width="1" opacity="0.3"/>
                        <line x1="30" y1="60" x2="60" y2="100" stroke="var(--glyph-cyan)" stroke-width="1" opacity="0.3"/>
                        <line x1="90" y1="60" x2="60" y2="100" stroke="var(--glyph-cyan)" stroke-width="1" opacity="0.3"/>
                        <line x1="90" y1="60" x2="100" y2="100" stroke="var(--glyph-cyan)" stroke-width="1" opacity="0.3"/>
                    </svg>
                </div>
                <div class="card-footer">
                    <div class="tech-stack">
                        <div class="tech-label">TECH STACK</div>
                        <div class="tech-chips">
                            <span class="tech-chip">Python</span>
                            <span class="tech-chip">TensorFlow</span>
                            <span class="tech-chip">OpenCV</span>
                            <span class="tech-chip">Docker</span>
                        </div>
                    </div>
                    <div class="metrics">
                        <div class="tech-label">TELEMETRY</div>
                        <div class="metrics-grid">
                            <div>
                                <div class="metric-value">99.8%</div>
                                <div class="metric-label">Accuracy</div>
                            </div>
                            <div>
                                <div class="metric-value">12ms</div>
                                <div class="metric-label">Latency</div>
                            </div>
                            <div>
                                <div class="metric-value">ResNet</div>
                                <div class="metric-label">Model</div>
                            </div>
                        </div>
                    </div>
                    <div class="action-button glass">
                        <span class="button-text">OPEN PROJECT</span>
                        <div class="toggle-switch">
                            <div class="toggle-knob"></div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Project 2 -->
            <div class="project-card glass">
                <div class="card-header">
                    <h3 class="card-title dot-matrix">MARKET ORACLE</h3>
                    <div class="status-tag">
                        <div class="status-indicator"></div>
                        <span>SYS.ACTIVE</span>
                    </div>
                    <div class="category">FORECASTING</div>
                </div>
                <div class="card-visual">
                    <svg width="140" height="100" viewBox="0 0 140 100">
                        <rect x="20" y="60" width="15" height="35" fill="var(--glyph-cyan)" opacity="0.4"/>
                        <rect x="45" y="45" width="15" height="50" fill="var(--glyph-cyan)" opacity="0.4"/>
                        <rect x="70" y="55" width="15" height="40" fill="var(--glyph-cyan)" opacity="0.4"/>
                        <rect x="95" y="30" width="15" height="65" fill="var(--glyph-cyan)" opacity="0.4"/>
                        <rect x="120" y="40" width="15" height="55" fill="var(--glyph-cyan)" opacity="0.4"/>
                    </svg>
                </div>
                <div class="card-footer">
                    <div class="tech-stack">
                        <div class="tech-label">TECH STACK</div>
                        <div class="tech-chips">
                            <span class="tech-chip">Python</span>
                            <span class="tech-chip">PyTorch</span>
                            <span class="tech-chip">LSTM</span>
                            <span class="tech-chip">AWS</span>
                        </div>
                    </div>
                    <div class="metrics">
                        <div class="tech-label">TELEMETRY</div>
                        <div class="metrics-grid">
                            <div>
                                <div class="metric-value">3.2%</div>
                                <div class="metric-label">MAPE</div>
                            </div>
                            <div>
                                <div class="metric-value">0.94</div>
                                <div class="metric-label">R²</div>
                            </div>
                            <div>
                                <div class="metric-value">47</div>
                                <div class="metric-label">Features</div>
                            </div>
                        </div>
                    </div>
                    <div class="action-button glass">
                        <span class="button-text">OPEN PROJECT</span>
                        <div class="toggle-switch">
                            <div class="toggle-knob"></div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Project 3 -->
            <div class="project-card glass">
                <div class="card-header">
                    <h3 class="card-title dot-matrix">SENTIMENT CORE</h3>
                    <div class="status-tag">
                        <div class="status-indicator"></div>
                        <span>SYS.DEPLOYED</span>
                    </div>
                    <div class="category">NLP</div>
                </div>
                <div class="card-visual">
                    <svg width="120" height="120" viewBox="0 0 120 120">
                        <circle cx="25" cy="70" r="2" fill="var(--glyph-cyan)"/>
                        <circle cx="40" cy="50" r="2" fill="var(--glyph-cyan)"/>
                        <circle cx="55" cy="65" r="2" fill="var(--glyph-cyan)"/>
                        <circle cx="70" cy="40" r="2" fill="var(--glyph-cyan)"/>
                        <circle cx="85" cy="55" r="2" fill="var(--glyph-cyan)"/>
                        <circle cx="95" cy="35" r="2" fill="var(--glyph-cyan)"/>
                    </svg>
                </div>
                <div class="card-footer">
                    <div class="tech-stack">
                        <div class="tech-label">TECH STACK</div>
                        <div class="tech-chips">
                            <span class="tech-chip">Python</span>
                            <span class="tech-chip">BERT</span>
                            <span class="tech-chip">FastAPI</span>
                            <span class="tech-chip">Redis</span>
                        </div>
                    </div>
                    <div class="metrics">
                        <div class="tech-label">TELEMETRY</div>
                        <div class="metrics-grid">
                            <div>
                                <div class="metric-value">0.96</div>
                                <div class="metric-label">F1 Score</div>
                            </div>
                            <div>
                                <div class="metric-value">10K/s</div>
                                <div class="metric-label">Speed</div>
                            </div>
                            <div>
                                <div class="metric-value">12</div>
                                <div class="metric-label">Languages</div>
                            </div>
                        </div>
                    </div>
                    <div class="action-button glass">
                        <span class="button-text">OPEN PROJECT</span>
                        <div class="toggle-switch">
                            <div class="toggle-knob"></div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Project 4 -->
            <div class="project-card glass">
                <div class="card-header">
                    <h3 class="card-title dot-matrix">CLUSTER MATRIX</h3>
                    <div class="status-tag">
                        <div class="status-indicator"></div>
                        <span>SYS.ONLINE</span>
                    </div>
                    <div class="category">CLUSTERING</div>
                </div>
                <div class="card-visual">
                    <svg width="120" height="120" viewBox="0 0 120 120">
                        <circle cx="60" cy="60" r="50" fill="none" stroke="var(--glyph-cyan)" stroke-width="1" opacity="0.3"/>
                        <circle cx="60" cy="60" r="35" fill="none" stroke="var(--glyph-cyan)" stroke-width="1" opacity="0.3"/>
                        <circle cx="60" cy="60" r="20" fill="none" stroke="var(--glyph-cyan)" stroke-width="1" opacity="0.3"/>
                        <circle cx="60" cy="25" r="3" fill="var(--glyph-cyan)"/>
                        <circle cx="85" cy="45" r="3" fill="var(--glyph-cyan)"/>
                        <circle cx="85" cy="75" r="3" fill="var(--glyph-cyan)"/>
                        <circle cx="60" cy="95" r="3" fill="var(--glyph-cyan)"/>
                        <circle cx="35" cy="75" r="3" fill="var(--glyph-cyan)"/>
                        <circle cx="35" cy="45" r="3" fill="var(--glyph-cyan)"/>
                    </svg>
                </div>
                <div class="card-footer">
                    <div class="tech-stack">
                        <div class="tech-label">TECH STACK</div>
                        <div class="tech-chips">
                            <span class="tech-chip">Python</span>
                            <span class="tech-chip">Scikit-learn</span>
                            <span class="tech-chip">K-Means</span>
                            <span class="tech-chip">PostgreSQL</span>
                        </div>
                    </div>
                    <div class="metrics">
                        <div class="tech-label">TELEMETRY</div>
                        <div class="metrics-grid">
                            <div>
                                <div class="metric-value">0.87</div>
                                <div class="metric-label">Silhouette</div>
                            </div>
                            <div>
                                <div class="metric-value">8</div>
                                <div class="metric-label">Clusters</div>
                            </div>
                            <div>
                                <div class="metric-value">2.4M</div>
                                <div class="metric-label">Records</div>
                            </div>
                        </div>
                    </div>
                    <div class="action-button glass">
                        <span class="button-text">OPEN PROJECT</span>
                        <div class="toggle-switch">
                            <div class="toggle-knob"></div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Spacer -->
            <div style="width: 2rem; flex-shrink: 0;"></div>
        </div>
    </section>

    <script>
        // Theme Toggle
        function toggleTheme() {
            const body = document.body;
            const dial = document.querySelector('.dial');
            const modeLabel = document.querySelector('.theme-mode');
            
            if (body.classList.contains('dark')) {
                body.classList.remove('dark');
                body.classList.add('light');
                dial.classList.add('rotated');
                modeLabel.textContent = 'LIGHT';
            } else {
                body.classList.remove('light');
                body.classList.add('dark');
                dial.classList.remove('rotated');
                modeLabel.textContent = 'VOID';
            }
        }

        // Glitch Effect
        function triggerGlitch() {
            const heroName = document.getElementById('heroName');
            heroName.classList.add('glitch-active');
            setTimeout(() => {
                heroName.classList.remove('glitch-active');
            }, 600);
        }

        // Trigger glitch every 5 seconds
        setInterval(triggerGlitch, 5000);

        // Initial glitch after 1 second
        setTimeout(triggerGlitch, 1000);
    </script>
</body>
</html>
         const modeLabel = document.querySelector('.theme-mode');
            
            if (body.classList.contains('dark')) {
                body.classList.remove('dark');
                body.classList.add('light');
                dial.classList.add('rotated');
                modeLabel.textContent = 'LIGHT';
            } else {
                body.classList.remove('light');
                body.classList.add('dark');
                dial.classList.remove('rotated');
                modeLabel.textContent = 'VOID';
            }
        }

        // Glitch Effect
        function triggerGlitch() {
            const heroName = document.getElementById('heroName');
            heroName.classList.add('glitch-active');
            setTimeout(() => {
                heroName.classList.remove('glitch-active');
            }, 600);
        }

        // Trigger glitch every 5 seconds
        setInterval(triggerGlitch, 5000);

        // Initial glitch after 1 second
        setTimeout(triggerGlitch, 1000);
    </script>
</body>
</html>
