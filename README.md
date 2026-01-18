<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HvacVoice AI | The 24/7 AI Receptionist for HVAC Companies</title>
    <meta name="description" content="Never miss an emergency repair call again. Our AI voice chatbot answers phones, books appointments, and qualifies leads for HVAC businesses automatically.">
    
    <style>
        /* --- CSS VARIABLES & RESET --- */
        :root {
            --primary: #0f172a;      /* Deep Navy */
            --primary-light: #1e293b;
            --accent: #f97316;       /* HVAC Orange */
            --accent-hover: #ea580c;
            --text-dark: #334155;
            --text-light: #94a3b8;
            --white: #ffffff;
            --bg-light: #f8fafc;
            --success: #10b981;
            
            --font-main: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
            --shadow-sm: 0 1px 3px rgba(0,0,0,0.1);
            --shadow-md: 0 4px 6px -1px rgba(0,0,0,0.1);
            --shadow-lg: 0 10px 15px -3px rgba(0,0,0,0.1);
            --radius: 8px;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: var(--font-main);
            color: var(--text-dark);
            background-color: var(--white);
            line-height: 1.6;
        }

        /* --- UTILITIES --- */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        .text-center { text-align: center; }
        .text-accent { color: var(--accent); }
        .mb-1 { margin-bottom: 0.5rem; }
        .mb-2 { margin-bottom: 1rem; }
        .mb-4 { margin-bottom: 2rem; }

        .btn {
            display: inline-block;
            padding: 12px 28px;
            font-weight: 600;
            text-decoration: none;
            border-radius: var(--radius);
            transition: all 0.3s ease;
            cursor: pointer;
            border: none;
            font-size: 1rem;
        }

        .btn-primary {
            background-color: var(--accent);
            color: var(--white);
            box-shadow: 0 4px 14px rgba(249, 115, 22, 0.4);
        }

        .btn-primary:hover {
            background-color: var(--accent-hover);
            transform: translateY(-2px);
        }

        .btn-outline {
            background-color: transparent;
            border: 2px solid var(--primary);
            color: var(--primary);
        }

        .btn-outline:hover {
            background-color: var(--primary);
            color: var(--white);
        }

        /* --- HEADER --- */
        header {
            background: var(--white);
            border-bottom: 1px solid #e2e8f0;
            position: sticky;
            top: 0;
            z-index: 1000;
            padding: 15px 0;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 800;
            color: var(--primary);
            display: flex;
            align-items: center;
            gap: 8px;
        }
        
        .logo span { color: var(--accent); }

        .nav-links {
            display: flex;
            gap: 30px;
            align-items: center;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--text-dark);
            font-weight: 500;
            font-size: 0.95rem;
            transition: color 0.2s;
        }

        .nav-links a:hover { color: var(--accent); }

        @media(max-width: 768px) {
            .nav-links { display: none; } /* Simplified for mobile demo */
        }

        /* --- HERO SECTION --- */
        .hero {
            background: linear-gradient(to right, var(--primary) 0%, var(--primary-light) 100%);
            color: var(--white);
            padding: 80px 0;
            position: relative;
            overflow: hidden;
        }

        .hero-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
            align-items: center;
        }

        .hero-content h1 {
            font-size: 3rem;
            line-height: 1.2;
            margin-bottom: 20px;
            font-weight: 800;
        }

        .hero-content p {
            font-size: 1.15rem;
            color: var(--text-light);
            margin-bottom: 30px;
            max-width: 500px;
        }

        .hero-stats {
            display: flex;
            gap: 20px;
            margin-top: 30px;
            padding-top: 30px;
            border-top: 1px solid rgba(255,255,255,0.1);
        }

        .stat-item strong { display: block; font-size: 1.5rem; color: var(--accent); }
        .stat-item span { font-size: 0.85rem; color: var(--text-light); }

        /* --- PAIN POINTS (PROBLEM) --- */
        .section { padding: 80px 0; }
        .bg-light { background-color: var(--bg-light); }

        .section-header {
            text-align: center;
            max-width: 700px;
            margin: 0 auto 60px;
        }

        .section-header h2 {
            font-size: 2.25rem;
            color: var(--primary);
            margin-bottom: 15px;
        }

        .card-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .problem-card {
            background: var(--white);
            padding: 30px;
            border-radius: var(--radius);
            box-shadow: var(--shadow-sm);
            border-left: 4px solid #ef4444; /* Red for problem */
        }

        .problem-card h3 { margin-bottom: 10px; font-size: 1.25rem; }

        /* --- DEMO SECTION (SOLUTION) --- */
        .demo-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
            align-items: center;
        }

        /* Chat UI Simulation */
        .chat-ui {
            background: var(--white);
            border-radius: 20px;
            box-shadow: var(--shadow-lg);
            border: 8px solid var(--primary);
            overflow: hidden;
            max-width: 350px;
            margin: 0 auto;
            position: relative;
            height: 600px;
            display: flex;
            flex-direction: column;
        }

        .chat-header {
            background: var(--primary);
            color: white;
            padding: 15px;
            text-align: center;
            font-weight: bold;
            font-size: 0.9rem;
            border-bottom: 1px solid rgba(255,255,255,0.1);
        }

        .chat-body {
            flex: 1;
            padding: 15px;
            background: #f1f5f9;
            display: flex;
            flex-direction: column;
            gap: 15px;
            overflow-y: auto;
        }

        .message {
            max-width: 85%;
            padding: 10px 14px;
            border-radius: 12px;
            font-size: 0.9rem;
            line-height: 1.4;
            opacity: 0; /* Hidden initially for animation */
            transform: translateY(10px);
            transition: all 0.3s ease;
        }

        .message.bot {
            background: var(--white);
            color: var(--text-dark);
            align-self: flex-start;
            border-bottom-left-radius: 2px;
            box-shadow: 0 1px 2px rgba(0,0,0,0.05);
        }

        .message.user {
            background: var(--primary);
            color: var(--white);
            align-self: flex-end;
            border-bottom-right-radius: 2px;
        }

        .message.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .chat-typing {
            font-size: 0.75rem;
            color: #64748b;
            margin-left: 10px;
            display: none;
        }

        .feature-list {
            list-style: none;
        }

        .feature-list li {
            margin-bottom: 20px;
            display: flex;
            align-items: flex-start;
            gap: 15px;
        }

        .check-icon {
            background: var(--success);
            color: white;
            width: 24px;
            height: 24px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-shrink: 0;
            font-size: 0.8rem;
        }

        /* --- HOW IT WORKS --- */
        .steps {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 30px;
            position: relative;
        }

        .steps::before {
            content: '';
            position: absolute;
            top: 40px;
            left: 15%;
            right: 15%;
            height: 2px;
            background: #e2e8f0;
            z-index: 0;
        }

        .step-card {
            background: var(--white);
            padding: 20px;
            text-align: center;
            position: relative;
            z-index: 1;
        }

        .step-number {
            width: 80px;
            height: 80px;
            background: var(--primary);
            color: var(--accent);
            font-size: 2rem;
            font-weight: bold;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px;
            border: 4px solid var(--bg-light);
        }

        /* --- PRICING --- */
        .pricing-card {
            background: var(--white);
            border: 1px solid #e2e8f0;
            border-radius: var(--radius);
            padding: 40px;
            text-align: center;
            transition: transform 0.3s;
        }

        .pricing-card:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow-lg);
            border-color: var(--accent);
        }

        .pricing-card.featured {
            border: 2px solid var(--accent);
            background: #fffaf5; /* Light orange tint */
            position: relative;
            overflow: hidden;
        }

        .badge {
            background: var(--accent);
            color: white;
            padding: 5px 30px;
            position: absolute;
            top: 20px;
            right: -30px;
            transform: rotate(45deg);
            font-size: 0.8rem;
            font-weight: bold;
        }

        .price {
            font-size: 3rem;
            font-weight: 800;
            color: var(--primary);
            margin: 20px 0;
        }

        .price span { font-size: 1rem; color: var(--text-light); font-weight: 400; }

        .pricing-features {
            list-style: none;
            margin: 30px 0;
            text-align: left;
        }

        .pricing-features li {
            padding: 8px 0;
            border-bottom: 1px solid #f1f5f9;
            color: var(--text-dark);
        }

        /* --- FAQ --- */
        .faq-item {
            background: var(--white);
            margin-bottom: 15px;
            border-radius: var(--radius);
            border: 1px solid #e2e8f0;
            overflow: hidden;
        }
        
        .faq-question {
            padding: 20px;
            cursor: pointer;
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-weight: 600;
            background: none;
            width: 100%;
            border: none;
            text-align: left;
            font-size: 1.05rem;
        }

        .faq-answer {
            padding: 0 20px 20px;
            color: var(--text-dark);
            display: none; /* Hidden by default */
            border-top: 1px solid #f1f5f9;
            padding-top: 15px;
        }

        .faq-item.active .faq-answer { display: block; }
        .faq-icon { transition: transform 0.3s; }
        .faq-item.active .faq-icon { transform: rotate(180deg); }

        /* --- FOOTER --- */
        footer {
            background: var(--primary);
            color: #94a3b8;
            padding: 60px 0 20px;
            text-align: center;
        }

        .footer-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-bottom: 30px;
        }

        .footer-links a { color: white; text-decoration: none; }

        /* --- RESPONSIVE --- */
        @media(max-width: 600px) {
            .hero-grid, .demo-container, .steps { grid-template-columns: 1fr; }
            .steps::before { display: none; }
            .hero-content { text-align: center; }
            .hero-content p { margin: 0 auto 30px; }
            .hero-stats { justify-content: center; }
            .chat-ui { margin-bottom: 30px; }
        }

        @media(max-width: 600px) {
            h1 { font-size: 2.2rem; }
            h2 { font-size: 1.8rem; }
            .btn {  font-size: 10px; margin-bottom: 10px; }
            .pricing-card{
                width: 160px;
               
            }
            .pricing-card p{
                font-size: 10px;
            }
           .pricing-card .price{
            font-size: 35px;
            margin-left: -10px;
           }
           .pricing-features li{
            font-size: 10px;
           }
           .pricing-card.featured{
            left: px;
           }
           
        }
    </style>
</head>
<body>

    <!-- NAV -->
    <header>
        <div class="container">
            <nav>
                <div class="logo">
                    <!-- Simple SVG Icon representing voice/wave -->
                    <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" style="color:var(--accent)">
                        <path d="M12 1a3 3 0 0 0-3 3v8a3 3 0 0 0 6 0V4a3 3 0 0 0-3-3z"></path>
                        <path d="M19 10v2a7 7 0 0 1-14 0v-2"></path>
                        <line x1="12" y1="19" x2="12" y2="23"></line>
                        <line x1="8" y1="23" x2="16" y2="23"></line>
                    </svg>
                    HvacVoice<span>AI</span>
                </div>
                <div class="nav-links">
                    <a href="#problem">Why Us</a>
                    <a href="#demo">How It Works</a>
                    <a href="#pricing">Pricing</a>
                    <a href="#faq">FAQ</a>
                </div>
                <a href="#pricing" class="btn btn-primary">Start Free Trial</a>
            </nav>
        </div>
        <elevenlabs-convai agent-id="agent_0601kea24rwaf7x8d581dcjm11xb"></elevenlabs-convai><script src="https://unpkg.com/@elevenlabs/convai-widget-embed" async type="text/javascript"></script>
        
    </header>

    <!-- HERO SECTION -->
    <section class="hero">
        <div class="container hero-grid">
            <div class="hero-content">
                <h1>Never Miss an Emergency Repair Call Again.</h1>
                <p>The AI receptionist built for HVAC companies. Answers phone calls instantly, qualifies leads, and books appointments into your calendar 24/7.</p>
                <div class="cta-group">
                    <a href="#demo" class="btn btn-primary">Watch the Demo</a>
                    <a href="#pricing" class="btn btn-outline" style="color: white; border-color: white; margin-left: 10px;">View Pricing</a>
                </div>
                <div class="hero-stats">
                    <div class="stat-item">
                        <strong>$50k+</strong>
                        <span>Revenue saved avg.</span>
                    </div>
                    <div class="stat-item">
                        <strong>24/7</strong>
                        <span>Always Available</span>
                    </div>
                    <div class="stat-item">
                        <strong>100%</strong>
                        <span>Bilingual Support</span>
                    </div>
                </div>
            </div>
            <!-- Visual representation of HVAC Technician -->
            <div class="hero-image" style="text-align: center;">
                <!-- Updated Image Source to be HVAC specific -->
                <img src="https://hvac.mumtazawan.com/HVAC%201.png?q=80&w=600&auto=format&fit=crop" alt="HVAC Technician repairing AC unit" style="border-radius: var(--radius); box-shadow: var(--shadow-lg); max-width: 100%;">
            </div>
        </div>
    </section>

    <!-- PROBLEM SECTION -->
    <section id="problem" class="section bg-light">
        <div class="container">
            <div class="section-header">
                <h2>The Silent Revenue Killer</h2>
                <p>Your technicians are under houses or on roofs. They can't pick up. Every missed call is a customer calling your competitor.</p>
            </div>
            <div class="card-grid">
                <div class="problem-card">
                    <h3>ðŸ“¶ After-Hours Ghosting</h3>
                    <p>AC breaks at 2 AM. Customers need help NOW. If they reach voicemail, they hang up and call the next listing on Google.</p>
                </div>
                <div class="problem-card">
                    <h3>ðŸ”¥ Missed Emergencies</h3>
                    <p>Emergency repairs are your highest margin jobs. Missing just one call a day costs you thousands in lost revenue every month.</p>
                </div>
                <div class="problem-card">
                    <h3>ðŸ“… Scheduling Chaos</h3>
                    <p>Playing phone tag to book a simple tune-up wastes your office staff's time and frustrates customers.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- DEMO / SOLUTION SECTION -->
    <section id="demo" class="section">
        <div class="container demo-container">
            
            <!-- Left: Value Props -->
            <div class="demo-content">
                <span class="text-accent" style="font-weight: 700; letter-spacing: 1px;">LIVE SIMULATION</span>
                <h2 class="mb-2">Meet "Scarlet": Your AI HVAC Receptionist</h2>
                <p class="mb-4">Watch how Scarlet handles a distressed customer with a broken AC. It understands context, handles objections, and books the job directly into your CRM.</p>
                
                <ul class="feature-list">
                    <li>
                        <div class="check-icon">âœ“</div>
                        <div>
                            <strong>Natural Conversation</strong><br>
                            Sounds human, not robotic. Handles interruptions.
                        </div>
                    </li>
                    <li>
                        <div class="check-icon">âœ“</div>
                        <div>
                            <strong>Intelligent Dispatching</strong><br>
                            Detects emergencies and texts your on-call tech.
                        </div>
                    </li>
                    <li>
                        <div class="check-icon">âœ“</div>
                        <div>
                            <strong>Direct Booking</strong><br>
                            Syncs with ServiceTitan, Housecall Pro, and Google Calendar.
                        </div>
                    </li>
                </ul>

                <button id="replay-demo" class="btn btn-outline" style="margin-top: 20px;">â†º Replay Simulation</button>
            </div>

            <!-- Right: Phone UI Animation -->
            <div class="chat-ui">
                <div class="chat-header">
                    ðŸ“ž Incoming Call: (555) 012-3456
                </div>
                <div class="chat-body" id="chat-container">
                    <!-- Messages injected via JS -->
                </div>
                <div class="chat-typing" id="typing-indicator">Atlas is speaking...</div>
            </div>

        </div>
    </section>

    <!-- HOW IT WORKS -->
    <section class="section bg-light">
        <div class="container">
            <div class="section-header">
                <h2>Setup in Minutes, not Weeks</h2>
                <p>We train the AI on your pricing, service area, and company personality.</p>
            </div>
            <div class="steps">
                <div class="step-card">
                    <div class="step-number">1</div>
                    <h3>Upload Knowledge</h3>
                    <p>Give us your price book, FAQs, and technician schedules. The AI learns your business instantly.</p>
                </div>
                <div class="step-card">
                    <div class="step-number">2</div>
                    <h3>Forward Calls</h3>
                    <p>Set up call forwarding on your existing business line for after-hours or overflow calls.</p>
                </div>
                <div class="step-card">
                    <div class="step-number">3</div>
                    <h3>Watch Bookings Grow</h3>
                    <p>Atlas answers, books, and updates your dashboard. You just wake up to a full schedule.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- TESTIMONIALS -->
    <section class="section">
        <div class="container">
            <div class="section-header">
                <h2>Trusted by Local HVAC Pros</h2>
            </div>
            <div class="card-grid">
                <div style="background: white; padding: 30px; border-radius: 8px; box-shadow: var(--shadow-sm);">
                    <p class="mb-2">"We were missing about 15 calls a day. Since installing HvacVoice AI, we booked an extra $8k in repairs last month alone. It pays for itself 100x over."</p>
                    <div style="display: flex; align-items: center; gap: 10px;">
                        <img src="https://picsum.photos/seed/mike/50/50" alt="Avatar" style="border-radius: 50%;">
                        <div>
                            <strong>Mike R.</strong><br>
                            <span style="font-size: 0.85rem; color: #64748b;">Owner, CoolAir Solutions</span>
                        </div>
                    </div>
                </div>
                <div style="background: white; padding: 30px; border-radius: 8px; box-shadow: var(--shadow-sm);">
                    <p class="mb-2">"My customers can't tell it's an AI. It handles the Spanish calls perfectly too, which we struggled with before."</p>
                    <div style="display: flex; align-items: center; gap: 10px;">
                        <img src="https://picsum.photos/seed/sarah/50/50" alt="Avatar" style="border-radius: 50%;">
                        <div>
                            <strong>Sarah Jenkins</strong><br>
                            <span style="font-size: 0.85rem; color: #64748b;">Manager, Apex HVAC</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- PRICING -->
    <section id="pricing" class="section bg-light">
        <div class="container">
            <div class="section-header">
                <h2>Simple, Flat Pricing</h2>
                <p>No contracts. Cancel anytime. Scale as you grow.</p>
            </div>
            <div class="card-grid" style="max-width: 900px; margin: 0 auto; grid-template-columns: 1fr 1fr;">
                <!-- Starter Plan -->
                <div class="pricing-card">
                    <h3>Growth</h3>
                    <div class="price">$299<span>/mo</span></div>
                    <p>Perfect for small teams growing fast.</p>
                    <ul class="pricing-features">
                        <li>âœ“ 100 Minutes / month</li>
                        <li>âœ“ After-hours & Overflow</li>
                        <li>âœ“ Google Calendar Sync</li>
                        <li>âœ“ SMS & Email Notifications</li>
                        <li>âœ“ English Only</li>
                    </ul>
                    <a href="#" class="btn btn-outline " style="width: 130px; margin-left: -27px;">Start Free Trial</a>
                </div>

                <!-- Pro Plan -->
                <div class="pricing-card featured">
                    <div class="badge">POPULAR</div>
                    <h3>Fleet</h3>
                    <div class="price">$499<span>/mo</span></div>
                    <p>For established HVAC companies.</p>
                    <ul class="pricing-features">
                        <li>âœ“ <strong>Unlimited</strong> Minutes</li>
                        <li>âœ“ 24/7 Full Replacement</li>
                        <li>âœ“ CRM Integration (ServiceTitan)</li>
                        <li>âœ“ Bilingual (English/Spanish)</li>
                        <li>âœ“ Custom Voice Training</li>
                    </ul>
                    <a href="#" class="btn btn-primary " style="width: 139px; margin-left: -30px;">Get Started Now</a>
                </div>
            </div>
        </div>
    </section>

    <!-- FAQ -->
    <section id="faq" class="section">
        <div class="container" style="max-width: 800px;">
            <div class="section-header">
                <h2>Frequently Asked Questions</h2>
            </div>
            
            <div class="faq-item">
                <button class="faq-question">
                    Can the AI handle emergency calls?
                    <span class="faq-icon">â–¼</span>
                </button>
                <div class="faq-answer">
                    Yes. The AI is trained to detect keywords like "emergency," "leaking," or "no cooling." It can immediately patch the call through to your on-call technician or send a high-priority SMS dispatch.
                </div>
            </div>

            <div class="faq-item">
                <button class="faq-question">
                    Do I need to change my phone number?
                    <span class="faq-icon">â–¼</span>
                </button>
                <div class="faq-answer">
                    No. We provide a simple call-forwarding code that you input into your existing provider. You can forward calls only after 5 PM, or only when your line is busy.
                </div>
            </div>

            <div class="faq-item">
                <button class="faq-question">
                    How does it handle appointments?
                    <span class="faq-icon">â–¼</span>
                </button>
                <div class="faq-answer">
                    The AI connects to your Google Calendar or ServiceTitan account. It looks at your techs' availability in real-time and proposes slots to the customer. Once confirmed, it locks it in.
                </div>
            </div>
        </div>
    </section>

    <!-- FINAL CTA -->
    <section class="section" style="background: var(--primary); color: white; text-align: center;">
        <div class="container">
            <h2 style="margin-bottom: 20px;">Ready to Capture Every Lead?</h2>
            <p style="margin-bottom: 30px; color: var(--text-light); max-width: 600px; margin-left: auto; margin-right: auto;">
                Stop letting money go to voicemail. Join 500+ HVAC companies automating their front desk today.
            </p>
            <a href="#pricing" class="btn btn-primary" style="font-size: 1.2rem; padding: 15px 40px;">Start Your 14-Day Free Trial</a>
            <p style="margin-top: 15px; font-size: 0.85rem; color: var(--text-light);">No credit card required for setup.</p>
        </div>
    </section>

    <!-- FOOTER -->
    <footer>
        <div class="container">
            <div class="logo" style="justify-content: center; margin-bottom: 20px; color: white;">
                HvacVoice<span>AI</span>
            </div>
            <div class="footer-links">
                <a href="#">Privacy Policy</a>
                <a href="#">Terms of Service</a>
                <a href="#">Support</a>
            </div>
            <p>&copy; 2023 HvacVoice AI. All rights reserved.</p>
        </div>
    </footer>

    <!-- INTERACTIVE SCRIPTS -->
    <script>
        // 1. FAQ ACCORDION LOGIC
        document.querySelectorAll('.faq-question').forEach(button => {
            button.addEventListener('click', () => {
                const item = button.parentElement;
                
                // Toggle current
                item.classList.toggle('active');

                // Optional: Close others
                document.querySelectorAll('.faq-item').forEach(otherItem => {
                    if (otherItem !== item) {
                        otherItem.classList.remove('active');
                    }
                });
            });
        });

        // 2. CHAT SIMULATION LOGIC
        const chatContainer = document.getElementById('chat-container');
        const typingIndicator = document.getElementById('typing-indicator');
        const replayBtn = document.getElementById('replay-demo');

        const script = [
            { type: 'user', text: "Hello? My AC just stopped blowing cold air and it's 90 degrees in here." },
            { type: 'bot', text: "I'm so sorry to hear that! I can definitely help. This sounds like an emergency. Is anyone currently having health issues due to the heat?" },
            { type: 'user', text: "My elderly mother is here, she's struggling a bit." },
            { type: 'bot', text: "Understood. Let's prioritize this immediately. I have a technician available in your area. Can he be there within 45 minutes?" },
            { type: 'user', text: "Yes, please!" },
            { type: 'bot', text: "Great. The dispatch fee is $89. I'm texting you the confirmation now. What is the best number to reach you at?" },
            { type: 'user', text: "555-012-3456." },
            { type: 'bot', text: "Perfect. You're all set. Stay cool!" }
        ];

        let timeoutIds = [];

        function createMessage(msg) {
            const div = document.createElement('div');
            div.classList.add('message', msg.type);
            div.textContent = msg.text;
            return div;
        }

        function runChatSimulation() {
            // Clear existing
            chatContainer.innerHTML = '';
            timeoutIds.forEach(id => clearTimeout(id));
            timeoutIds = [];

            let delay = 500;

            script.forEach((msg, index) => {
                timeoutIds.push(setTimeout(() => {
                    // Show typing indicator before bot messages
                    if(msg.type === 'bot') {
                        typingIndicator.style.display = 'block';
                        
                        setTimeout(() => {
                            typingIndicator.style.display = 'none';
                            const el = createMessage(msg);
                            chatContainer.appendChild(el);
                            // Trigger reflow for animation
                            void el.offsetWidth; 
                            el.classList.add('visible');
                            chatContainer.scrollTop = chatContainer.scrollHeight;
                        }, 1500); // "Think" time
                    } else {
                        // User message appears instantly (simulated)
                        const el = createMessage(msg);
                        chatContainer.appendChild(el);
                        void el.offsetWidth;
                        el.classList.add('visible');
                        chatContainer.scrollTop = chatContainer.scrollHeight;
                    }
                }, delay));
                
                // Increase delay based on previous message length (reading time) + base buffer
                const readingTime = (msg.text.length * 50) + 1000;
                delay += readingTime + 1000; 
            });
        }

        // Run on load
        window.addEventListener('DOMContentLoaded', runChatSimulation);
        
        // Replay button
        replayBtn.addEventListener('click', runChatSimulation);

    </script>
</body>
</html>
```
