<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TaxBuddy NG - Tax Compliance Made Simple for Nigerians</title>
    <meta name="description" content="Track deadlines, manage documents, and calculate taxes — all in one app designed for Nigerian individuals and SMEs.">
    
    <!-- Favicon -->
    <link rel="icon" type="image/svg+xml" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'><text y='0.9em' font-size='90'>🧮</text></svg>">
    
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@600;700&family=Inter:wght@400;500;600&display=swap" rel="stylesheet">
    
    <!-- Lucide Icons -->
    <script src="https://unpkg.com/lucide@latest"></script>
    
    <style>
        :root {
            --color-purple-900: #4C1D95;
            --color-purple-700: #7C3AED;
            --color-purple-600: #8B5CF6;
            --color-purple-500: #A78BFA;
            --color-purple-100: #E9D5FF;
            --color-purple-50: #FAF5FF;
            
            --color-gray-900: #0F172A;
            --color-gray-700: #334155;
            --color-gray-500: #64748B;
            --color-gray-300: #CBD5E1;
            --color-gray-100: #F1F5F9;
            --color-gray-50: #F8FAFC;
            
            --color-emerald-600: #059669;
            --color-success: #10B981;
            --color-warning: #F59E0B;
            
            --font-heading: 'Plus Jakarta Sans', sans-serif;
            --font-body: 'Inter', sans-serif;
            
            --shadow-sm: 0 1px 3px rgba(0, 0, 0, 0.05);
            --shadow-md: 0 4px 12px rgba(0, 0, 0, 0.08);
            --shadow-lg: 0 8px 24px rgba(0, 0, 0, 0.12);
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: var(--font-body);
            font-size: 16px;
            line-height: 1.6;
            color: var(--color-gray-900);
            background: white;
            -webkit-font-smoothing: antialiased;
        }
        
        .container {
            max-width: 1280px;
            margin: 0 auto;
            padding: 0 1.5rem;
        }
        
        h1, h2, h3, h4 {
            font-family: var(--font-heading);
            font-weight: 700;
            line-height: 1.2;
        }
        
        /* Header */
        .header {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid var(--color-gray-100);
            z-index: 100;
        }
        
        .header-content {
            display: flex;
            align-items: center;
            justify-content: space-between;
            height: 4rem;
        }
        
        .logo {
            font-family: var(--font-heading);
            font-size: 1.25rem;
            font-weight: 700;
            color: var(--color-gray-900);
            text-decoration: none;
        }
        
        .nav {
            display: none;
            gap: 2rem;
        }
        
        @media (min-width: 768px) {
            .nav {
                display: flex;
            }
        }
        
        .nav a {
            color: var(--color-gray-700);
            text-decoration: none;
            font-weight: 500;
            transition: color 0.2s;
        }
        
        .nav a:hover {
            color: #8B5CF6;
        }
        
        .btn {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            padding: 0.75rem 1.5rem;
            font-weight: 600;
            border-radius: 0.75rem;
            text-decoration: none;
            transition: all 0.2s;
            border: none;
            cursor: pointer;
            font-size: 1rem;
        }
        
        .btn-primary {
            background: #8B5CF6;
            color: white;
            box-shadow: 0 2px 8px rgba(139, 92, 246, 0.3);
        }
        
        .btn-primary:hover {
            background: #7C3AED;
            transform: translateY(-1px);
        }
        
        .btn-secondary {
            background: white;
            color: #8B5CF6;
            border: 2px solid #8B5CF6;
        }
        
        .btn-secondary:hover {
            background: #FAF5FF;
        }
        
        .btn-ghost {
            background: transparent;
            color: var(--color-gray-700);
            border: 1px solid var(--color-gray-300);
        }
        
        /* Hero */
        .hero {
            padding: 8rem 0 5rem;
            text-align: center;
            background: linear-gradient(135deg, #8B5CF6 0%, #7C3AED 100%);
            color: white;
        }
        
        .hero h1 {
            font-size: clamp(2.5rem, 5vw, 3.5rem);
            margin-bottom: 1.5rem;
            color: white;
        }
        
        .hero-subtitle {
            font-size: 1.25rem;
            margin-bottom: 2rem;
            color: #F3E8FF;
            max-width: 42rem;
            margin-left: auto;
            margin-right: auto;
        }
        
        .hero-actions {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
        }
        
        /* Waitlist Section */
        .waitlist-section {
            padding: 5rem 0;
            background: var(--color-gray-50);
        }
        
        .waitlist-card {
            max-width: 600px;
            margin: 0 auto;
            background: white;
            padding: 3rem 2rem;
            border-radius: 1rem;
            box-shadow: var(--shadow-lg);
            text-align: center;
        }
        
        .waitlist-card h2 {
            font-size: 2rem;
            margin-bottom: 1rem;
        }
        
        .waitlist-card p {
            color: var(--color-gray-600);
            margin-bottom: 2rem;
        }
        
        .email-form {
            display: flex;
            gap: 0.75rem;
            margin-bottom: 1rem;
        }
        
        .email-input {
            flex: 1;
            padding: 1rem 1.5rem;
            border: 2px solid var(--color-gray-300);
            border-radius: 0.75rem;
            font-size: 1rem;
        }
        
        .checkbox-label {
            display: flex;
            align-items: start;
            gap: 0.5rem;
            text-align: left;
            font-size: 0.875rem;
            color: var(--color-gray-700);
            margin-bottom: 1rem;
        }
        
        .privacy-note {
            font-size: 0.75rem;
            color: var(--color-gray-500);
            text-align: left;
        }
        
        /* How It Works */
        .how-it-works {
            padding: 5rem 0;
            background: white;
        }
        
        .section-header {
            text-align: center;
            margin-bottom: 4rem;
        }
        
        .section-header h2 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }
        
        .section-header p {
            font-size: 1.125rem;
            color: var(--color-gray-600);
        }
        
        .steps-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }
        
        .step-card {
            text-align: center;
            padding: 2rem;
        }
        
        .step-number {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 3rem;
            height: 3rem;
            background: #FAF5FF;
            color: #8B5CF6;
            border-radius: 50%;
            font-weight: 700;
            font-size: 1.25rem;
            margin-bottom: 1.5rem;
        }
        
        .step-card h3 {
            font-size: 1.25rem;
            margin-bottom: 0.75rem;
        }
        
        .step-card p {
            color: var(--color-gray-600);
        }
        
        /* Features */
        .features {
            padding: 5rem 0;
            background: var(--color-gray-50);
        }
        
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }
        
        .feature-card {
            background: white;
            padding: 2rem;
            border-radius: 1rem;
            border: 1px solid var(--color-gray-200);
            transition: all 0.2s;
        }
        
        .feature-card:hover {
            transform: translateY(-4px);
            box-shadow: var(--shadow-lg);
            border-color: #8B5CF6;
        }
        
        .feature-icon {
            width: 3rem;
            height: 3rem;
            background: #8B5CF6;
            color: white;
            border-radius: 0.75rem;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 1.5rem;
        }
        
        .feature-card h3 {
            font-size: 1.25rem;
            margin-bottom: 0.75rem;
        }
        
        .feature-card p {
            color: var(--color-gray-600);
        }
        
        /* Pricing */
        .pricing {
            padding: 5rem 0;
            background: white;
        }
        
        .pricing-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            max-width: 1100px;
            margin: 0 auto;
        }
        
        .pricing-card {
            background: white;
            border: 2px solid var(--color-gray-200);
            border-radius: 1rem;
            padding: 2.5rem 2rem;
            position: relative;
        }
        
        .pricing-card.featured {
            border-color: #8B5CF6;
            box-shadow: 0 8px 24px rgba(139, 92, 246, 0.2);
            transform: scale(1.05);
        }
        
        .pricing-badge {
            position: absolute;
            top: -12px;
            left: 50%;
            transform: translateX(-50%);
            background: #8B5CF6;
            color: white;
            padding: 0.25rem 1rem;
            border-radius: 1rem;
            font-size: 0.875rem;
            font-weight: 600;
        }
        
        .pricing-card h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
        }
        
        .price {
            font-size: 2.5rem;
            font-weight: 700;
            color: var(--color-gray-900);
            margin-bottom: 0.5rem;
        }
        
        .price-period {
            color: var(--color-gray-500);
            font-size: 1rem;
        }
        
        .features-list {
            list-style: none;
            margin: 2rem 0;
        }
        
        .features-list li {
            padding: 0.5rem 0;
            display: flex;
            align-items: start;
            gap: 0.5rem;
        }
        
        .features-list li::before {
            content: "✓";
            color: var(--color-success);
            font-weight: 700;
        }
        
        /* FAQ */
        .faq {
            padding: 5rem 0;
            background: var(--color-gray-50);
        }
        
        .faq-grid {
            max-width: 800px;
            margin: 0 auto;
        }
        
        .faq-item {
            background: white;
            padding: 1.5rem;
            border-radius: 0.75rem;
            margin-bottom: 1rem;
            border: 1px solid var(--color-gray-200);
        }
        
        .faq-question {
            font-weight: 600;
            font-size: 1.125rem;
            margin-bottom: 0.75rem;
            color: var(--color-gray-900);
        }
        
        .faq-answer {
            color: var(--color-gray-600);
        }
        
        /* CTA Section */
        .cta-section {
            padding: 5rem 0;
            background: linear-gradient(135deg, #8B5CF6 0%, #7C3AED 100%);
            color: white;
            text-align: center;
        }
        
        .cta-section h2 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            color: white;
        }
        
        .cta-section p {
            font-size: 1.25rem;
            color: #F3E8FF;
            margin-bottom: 2rem;
        }
        
        /* Footer */
        .footer {
            padding: 2rem 0;
            background: var(--color-gray-900);
            color: white;
            text-align: center;
        }
        
        .footer p {
            color: rgba(255, 255, 255, 0.7);
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2rem;
            }
            
            .section-header h2 {
                font-size: 1.75rem;
            }
            
            .steps-grid,
            .features-grid {
                grid-template-columns: 1fr;
            }
            
            .pricing-grid {
                grid-template-columns: 1fr;
            }
            
            .pricing-card.featured {
                transform: scale(1);
            }
            
            .email-form {
                flex-direction: column;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header class="header">
        <div class="container">
            <div class="header-content">
                <a href="#" class="logo">TaxBuddy NG</a>
                <nav class="nav">
                    <a href="#how-it-works">How It Works</a>
                    <a href="#features">Features</a>
                    <a href="#pricing">Pricing</a>
                    <a href="#faq">FAQ</a>
                </nav>
                <a href="https://ng-tax-hero.lovable.app" target="_blank" class="btn btn-ghost">Sign In</a>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <h1>Tax Compliance Made Simple for Nigerians</h1>
            <p class="hero-subtitle">
                Track deadlines, manage documents, and calculate taxes — all in one app designed for Nigerian individuals and SMEs.
            </p>
            <div class="hero-actions">
                <a href="https://ng-tax-hero.lovable.app/signup" target="_blank" class="btn btn-primary">
                    Get Started Free
                    <i data-lucide="arrow-right" style="width: 1rem; height: 1rem;"></i>
                </a>
                <a href="https://ng-tax-hero.lovable.app/calculator" target="_blank" class="btn btn-secondary">
                    Check Your Readiness
                </a>
            </div>
        </div>
    </section>

    <!-- Waitlist Section -->
    <section class="waitlist-section">
        <div class="container">
            <div class="waitlist-card">
                <h2>Join the Waitlist</h2>
                <p>Be the first to know when new features launch</p>
                
                <form class="email-form" onsubmit="event.preventDefault(); alert('Thanks for joining! Check your email soon.');">
                    <input type="email" class="email-input" placeholder="Enter your email" required>
                    <button type="submit" class="btn btn-primary">Get Early Access</button>
                </form>
                
                <label class="checkbox-label">
                    <input type="checkbox" required>
                    <span>I agree to receive product updates and announcements</span>
                </label>
                
                <p class="privacy-note">
                    <strong>Privacy:</strong> We only collect your email to notify you about early access. We don't sell your data. You can unsubscribe anytime.
                </p>
            </div>
        </div>
    </section>

    <!-- How It Works -->
    <section id="how-it-works" class="how-it-works">
        <div class="container">
            <div class="section-header">
                <h2>How TaxBuddy NG Works</h2>
                <p>Get started in minutes with our simple 4-step process</p>
            </div>
            
            <div class="steps-grid">
                <div class="step-card">
                    <div class="step-number">1</div>
                    <h3>Sign Up Free</h3>
                    <p>Create your account in under 2 minutes</p>
                </div>
                
                <div class="step-card">
                    <div class="step-number">2</div>
                    <h3>Complete Readiness Check</h3>
                    <p>Answer questions about your tax situation</p>
                </div>
                
                <div class="step-card">
                    <div class="step-number">3</div>
                    <h3>Set Up Deadlines</h3>
                    <p>Import or create tax deadline reminders</p>
                </div>
                
                <div class="step-card">
                    <div class="step-number">4</div>
                    <h3>Stay Compliant</h3>
                    <p>Get alerts, file on time, avoid penalties</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Features -->
    <section id="features" class="features">
        <div class="container">
            <div class="section-header">
                <h2>Features</h2>
                <p>Everything you need to stay compliant with Nigerian tax laws</p>
            </div>
            
            <div class="features-grid">
                <div class="feature-card">
                    <div class="feature-icon">
                        <i data-lucide="user-check" style="width: 1.5rem; height: 1.5rem;"></i>
                    </div>
                    <h3>TIN Onboarding</h3>
                    <p>Step-by-step checklist to get your Tax Identification Number</p>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i data-lucide="calendar" style="width: 1.5rem; height: 1.5rem;"></i>
                    </div>
                    <h3>Deadline Tracking</h3>
                    <p>Never miss a VAT, WHT, or income tax deadline again</p>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i data-lucide="bell" style="width: 1.5rem; height: 1.5rem;"></i>
                    </div>
                    <h3>Smart Reminders</h3>
                    <p>Get email alerts before important tax dates</p>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i data-lucide="calculator" style="width: 1.5rem; height: 1.5rem;"></i>
                    </div>
                    <h3>Tax Calculators</h3>
                    <p>VAT, WHT, and income tax calculators with Nigerian rates</p>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i data-lucide="folder" style="width: 1.5rem; height: 1.5rem;"></i>
                    </div>
                    <h3>Document Vault</h3>
                    <p>Securely store and organize all your tax documents</p>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i data-lucide="shield" style="width: 1.5rem; height: 1.5rem;"></i>
                    </div>
                    <h3>Secure & Private</h3>
                    <p>Your data is encrypted and only accessible by you</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Pricing -->
    <section id="pricing" class="pricing">
        <div class="container">
            <div class="section-header">
                <h2>Simple, Transparent Pricing</h2>
                <p>Start free and upgrade as you grow. No hidden fees.</p>
            </div>
            
            <div class="pricing-grid">
                <div class="pricing-card">
                    <h3>Free</h3>
                    <div class="price">Free</div>
                    
                    <ul class="features-list">
                        <li>Dashboard & KPIs</li>
                        <li>Basic AI summary</li>
                        <li>3 AI explanations/month</li>
                        <li>Talk to a Tax Agent</li>
                    </ul>
                    
                    <a href="https://ng-tax-hero.lovable.app/signup" target="_blank" class="btn btn-secondary" style="width: 100%;">Get Started</a>
                </div>
                
                <div class="pricing-card featured">
                    <div class="pricing-badge">Most Popular</div>
                    <h3>Pro</h3>
                    <div class="price">₦3,000<span class="price-period">/month</span></div>
                    
                    <ul class="features-list">
                        <li>Everything in Free</li>
                        <li>Full AI explanations</li>
                        <li>Daily compliance scan</li>
                        <li>Anomaly detection</li>
                        <li>Export PDF/ZIP</li>
                        <li>Submit remittance</li>
                    </ul>
                    
                    <a href="https://ng-tax-hero.lovable.app/pricing" target="_blank" class="btn btn-primary" style="width: 100%;">Upgrade to Pro</a>
                </div>
                
                <div class="pricing-card">
                    <h3>Business</h3>
                    <div class="price">₦15,000<span class="price-period">/month</span></div>
                    
                    <ul class="features-list">
                        <li>Everything in Pro</li>
                        <li>Multi-user roles</li>
                        <li>Audit pack export</li>
                        <li>Rule management</li>
                        <li>Approval workflows</li>
                    </ul>
                    
                    <a href="https://ng-tax-hero.lovable.app/pricing" target="_blank" class="btn btn-secondary" style="width: 100%;">Upgrade to Business</a>
                </div>
            </div>
            
            <p style="text-align: center; margin-top: 2rem; color: var(--color-gray-600);">
                Need a custom plan? <a href="#" style="color: #8B5CF6; text-decoration: underline;">Contact us</a>
            </p>
        </div>
    </section>

    <!-- FAQ -->
    <section id="faq" class="faq">
        <div class="container">
            <div class="section-header">
                <h2>Frequently Asked Questions</h2>
                <p>Got questions? We've got answers.</p>
            </div>
            
            <div class="faq-grid">
                <div class="faq-item">
                    <div class="faq-question">What is Tax Buddy?</div>
                    <div class="faq-answer">TaxBuddy NG is a tax compliance platform designed specifically for Nigerian individuals and SMEs. We help you track deadlines, calculate taxes, and stay compliant with FIRS requirements.</div>
                </div>
                
                <div class="faq-item">
                    <div class="faq-question">Who is Tax Buddy for?</div>
                    <div class="faq-answer">TaxBuddy NG is for Nigerian salary earners, freelancers, contractors, and SMEs who need to manage PAYE, VAT, WHT, and PIT compliance obligations.</div>
                </div>
                
                <div class="faq-item">
                    <div class="faq-question">Is Tax Buddy a government platform?</div>
                    <div class="faq-answer">No. TaxBuddy NG is not affiliated with FIRS or any Nigerian tax authority. We provide informational support and workflow tools, not legal or tax advice.</div>
                </div>
                
                <div class="faq-item">
                    <div class="faq-question">What can I do with Tax Buddy?</div>
                    <div class="faq-answer">Track tax deadlines, calculate PAYE/VAT/WHT, organize documents, get compliance reminders, and access AI-powered tax explanations tailored to Nigerian tax laws.</div>
                </div>
                
                <div class="faq-item">
                    <div class="faq-question">What is the "Quick Access" feature?</div>
                    <div class="faq-answer">Quick Access provides instant links to your most-used tax tools and calculators, making it faster to complete common tasks like PAYE calculations and deadline checks.</div>
                </div>
            </div>
            
            <p style="text-align: center; margin-top: 2rem;">
                <a href="#" style="color: #8B5CF6; text-decoration: underline; font-weight: 600;">See All FAQs →</a>
            </p>
        </div>
    </section>

    <!-- CTA Section -->
    <section class="cta-section">
        <div class="container">
            <h2>Ready to simplify your taxes?</h2>
            <p>Join thousands of Nigerians who trust TaxBuddy NG</p>
            <a href="https://ng-tax-hero.lovable.app/signup" target="_blank" class="btn btn-primary" style="background: white; color: #8B5CF6;">
                Create Free Account
                <i data-lucide="arrow-right" style="width: 1rem; height: 1rem;"></i>
            </a>
        </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
        <div class="container">
            <p>© 2025 TaxBuddy NG. All rights reserved.</p>
        </div>
    </footer>

    <script>
        lucide.createIcons();
    </script>
</body>
</html>
