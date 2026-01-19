<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TaxBuddy NG - Nigerian Tax Compliance Made Simple</title>
    <meta name="description" content="Calculate PAYE, track VAT, manage deadlines, and stay compliant with FIRS. TaxBuddy NG helps Nigerian individuals and businesses understand their tax obligations.">
    
    <!-- Favicon -->
    <link rel="icon" type="image/svg+xml" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'><text y='0.9em' font-size='90'>🧮</text></svg>">
    
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@600;700&family=Inter:wght@400;500;600&family=JetBrains+Mono:wght@600&display=swap" rel="stylesheet">
    
    <!-- Lucide Icons -->
    <script src="https://unpkg.com/lucide@latest"></script>
    
    <style>
        /* ==========================================
           CSS CUSTOM PROPERTIES
           ========================================== */
        :root {
            /* Colors */
            --color-purple-900: #2A105F;
            --color-purple-700: #6D1ED4;
            --color-purple-600: #7C3AED;
            --color-purple-500: #8B5CF6;
            --color-purple-100: #E9D5FF;
            --color-purple-50: #F5F3FF;
            
            --color-gray-900: #0F172A;
            --color-gray-700: #334155;
            --color-gray-500: #64748B;
            --color-gray-300: #CBD5E1;
            --color-gray-100: #F1F5F9;
            --color-gray-50: #F8FAFC;
            --color-white: #FFFFFF;
            
            --color-emerald-600: #059669;
            --color-emerald-500: #10B981;
            --color-emerald-100: #D1FAE5;
            
            --color-success: #10B981;
            --color-warning: #F59E0B;
            --color-error: #EF4444;
            --color-info: #3B82F6;
            
            --color-warning-bg: #FEF3C7;
            --color-warning-text: #78350F;
            
            /* Typography */
            --font-heading: 'Plus Jakarta Sans', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
            --font-body: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
            --font-mono: 'JetBrains Mono', 'Courier New', monospace;
            
            --font-weight-regular: 400;
            --font-weight-medium: 500;
            --font-weight-semibold: 600;
            --font-weight-bold: 700;
            
            /* Spacing */
            --space-xs: 0.25rem;
            --space-sm: 0.5rem;
            --space-base: 0.75rem;
            --space-md: 1rem;
            --space-lg: 1.5rem;
            --space-xl: 2rem;
            --space-2xl: 3rem;
            --space-3xl: 4rem;
            --space-4xl: 5rem;
            --space-5xl: 7.5rem;
            
            /* Layout */
            --container-max: 80rem;
            --container-reading: 48rem;
            --padding-x-desktop: 5rem;
            --padding-x-tablet: 2.5rem;
            --padding-x-mobile: 1.5rem;
            
            /* Border Radius */
            --radius-sm: 0.5rem;
            --radius-md: 0.75rem;
            --radius-lg: 1rem;
            --radius-xl: 1.5rem;
            --radius-full: 9999px;
            
            /* Shadows */
            --shadow-sm: 0 1px 3px rgba(0, 0, 0, 0.05);
            --shadow-md: 0 4px 12px rgba(0, 0, 0, 0.08);
            --shadow-lg: 0 8px 24px rgba(0, 0, 0, 0.12);
            --shadow-purple-sm: 0 2px 8px rgba(109, 30, 212, 0.2);
            --shadow-purple-md: 0 4px 16px rgba(109, 30, 212, 0.25);
            
            /* Transitions */
            --transition-base: 200ms ease-in-out;
            --transition-all: all 200ms ease-in-out;
        }
        
        /* Reset */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: var(--font-body);
            font-size: 1rem;
            line-height: 1.5;
            color: var(--color-gray-900);
            background: var(--color-white);
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
        }
        
        /* Container */
        .container {
            width: 100%;
            max-width: var(--container-max);
            margin-left: auto;
            margin-right: auto;
            padding-left: var(--padding-x-mobile);
            padding-right: var(--padding-x-mobile);
        }
        
        @media (min-width: 641px) {
            .container {
                padding-left: var(--padding-x-tablet);
                padding-right: var(--padding-x-tablet);
            }
        }
        
        @media (min-width: 1025px) {
            .container {
                padding-left: var(--padding-x-desktop);
                padding-right: var(--padding-x-desktop);
            }
        }
        
        /* Typography */
        h1, h2, h3, h4, h5, h6 {
            font-family: var(--font-heading);
            font-weight: var(--font-weight-bold);
            line-height: 1.2;
            letter-spacing: -0.02em;
        }
        
        h1 { font-size: clamp(2.5rem, 5vw, 3.5rem); }
        h2 { font-size: clamp(2rem, 4vw, 3rem); }
        h3 { font-size: clamp(1.75rem, 3vw, 2.25rem); }
        h4 { font-size: 1.5rem; }
        
        p { margin-bottom: 1rem; }
        
        a {
            color: var(--color-purple-700);
            text-decoration: none;
            transition: var(--transition-base);
        }
        
        a:hover {
            color: var(--color-purple-600);
        }
        
        /* Buttons */
        .btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: var(--space-sm);
            padding: 0.75rem 1.5rem;
            font-family: var(--font-body);
            font-size: 1rem;
            font-weight: var(--font-weight-semibold);
            border-radius: var(--radius-md);
            border: none;
            cursor: pointer;
            transition: var(--transition-all);
            text-decoration: none;
        }
        
        .btn-primary {
            background: var(--color-purple-700);
            color: var(--color-white);
            box-shadow: var(--shadow-purple-sm);
        }
        
        .btn-primary:hover {
            background: var(--color-purple-600);
            transform: translateY(-1px);
            box-shadow: var(--shadow-purple-md);
        }
        
        .btn-secondary {
            background: var(--color-purple-800);
            color: var(--color-white);
            border: 2px solid rgba(255, 255, 255, 0.3);
        }
        
        .btn-secondary:hover {
            background: var(--color-purple-900);
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
            display: flex;
            align-items: center;
            gap: var(--space-sm);
            font-family: var(--font-heading);
            font-size: 1.25rem;
            font-weight: var(--font-weight-bold);
            color: var(--color-gray-900);
            text-decoration: none;
        }
        
        /* Hero */
        .hero {
            padding: 8rem var(--padding-x-mobile) 5rem;
            background: linear-gradient(135deg, var(--color-purple-700) 0%, var(--color-purple-900) 100%);
            color: var(--color-white);
            text-align: center;
        }
        
        .hero h1 {
            margin-bottom: var(--space-lg);
            color: var(--color-white);
        }
        
        .hero-subtitle {
            font-size: clamp(1.125rem, 2vw, 1.5rem);
            margin-bottom: var(--space-2xl);
            color: var(--color-purple-100);
            max-width: 48rem;
            margin-left: auto;
            margin-right: auto;
        }
        
        .hero-actions {
            display: flex;
            gap: var(--space-md);
            justify-content: center;
            flex-wrap: wrap;
        }
        
        /* Preview Section */
        .preview-section {
            padding: var(--space-4xl) 0;
            background: var(--color-gray-50);
        }
        
        .section-header {
            text-align: center;
            margin-bottom: var(--space-4xl);
        }
        
        .section-subtitle {
            font-size: 1.25rem;
            color: var(--color-gray-600);
            margin-top: var(--space-md);
        }
        
        .preview-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: var(--space-xl);
        }
        
        /* Card */
        .card {
            background: var(--color-white);
            border: 1px solid var(--color-gray-300);
            border-radius: var(--radius-lg);
            padding: var(--space-xl);
            box-shadow: var(--shadow-sm);
            transition: var(--transition-all);
            cursor: pointer;
        }
        
        .card:hover {
            box-shadow: var(--shadow-lg);
            border-color: var(--color-purple-700);
            transform: translateY(-4px);
        }
        
        .card-preview {
            height: 12rem;
            border-radius: var(--radius-md);
            margin-bottom: var(--space-lg);
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
        }
        
        .card-preview::after {
            content: '';
            position: absolute;
            inset: 0;
            background: linear-gradient(to top, rgba(0,0,0,0.2), transparent);
        }
        
        .card-badge {
            position: absolute;
            bottom: 1rem;
            right: 1rem;
            background: rgba(255, 255, 255, 0.9);
            padding: 0.25rem 0.75rem;
            border-radius: var(--radius-sm);
            font-size: 0.875rem;
            font-weight: var(--font-weight-semibold);
            z-index: 1;
        }
        
        .card-title {
            display: flex;
            align-items: center;
            justify-content: space-between;
            margin-bottom: var(--space-base);
        }
        
        .card-cta {
            display: flex;
            align-items: center;
            gap: var(--space-sm);
            color: var(--color-purple-700);
            font-weight: var(--font-weight-semibold);
            margin-top: var(--space-md);
        }
        
        /* Features */
        .features-section {
            padding: var(--space-4xl) 0;
            background: var(--color-white);
        }
        
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: var(--space-xl);
        }
        
        .feature-card {
            padding: var(--space-xl);
            background: var(--color-purple-50);
            border: 1px solid var(--color-purple-100);
            border-radius: var(--radius-lg);
        }
        
        .feature-icon {
            width: 3rem;
            height: 3rem;
            background: var(--color-purple-700);
            border-radius: var(--radius-md);
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: var(--space-lg);
        }
        
        .feature-title {
            font-size: 1.25rem;
            margin-bottom: var(--space-base);
        }
        
        /* CTA Section */
        .cta-section {
            padding: var(--space-4xl) 0;
            background: linear-gradient(135deg, var(--color-purple-700) 0%, var(--color-purple-900) 100%);
            color: var(--color-white);
            text-align: center;
        }
        
        .cta-content {
            max-width: 56rem;
            margin: 0 auto;
        }
        
        .email-form {
            display: flex;
            gap: var(--space-base);
            max-width: 32rem;
            margin: var(--space-lg) auto 0;
        }
        
        .email-input {
            flex: 1;
            padding: 1rem 1.5rem;
            border: none;
            border-radius: var(--radius-md);
            font-size: 1rem;
        }
        
        /* Disclaimer */
        .disclaimer {
            padding: var(--space-xl) 0;
            background: var(--color-warning-bg);
            border-top: 2px solid var(--color-warning);
            border-bottom: 2px solid var(--color-warning);
        }
        
        .disclaimer-content {
            display: flex;
            gap: var(--space-md);
            align-items: start;
            max-width: 56rem;
            margin: 0 auto;
        }
        
        .disclaimer-text {
            font-size: 0.875rem;
            line-height: 1.6;
            color: var(--color-warning-text);
        }
        
        /* Footer */
        .footer {
            padding: var(--space-4xl) 0 var(--space-xl);
            background: linear-gradient(135deg, var(--color-purple-900) 0%, var(--color-purple-800) 100%);
            color: var(--color-white);
        }
        
        .footer-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: var(--space-2xl);
            margin-bottom: var(--space-2xl);
        }
        
        .footer-section h4 {
            margin-bottom: var(--space-md);
            font-size: 1.125rem;
        }
        
        .footer-links {
            list-style: none;
        }
        
        .footer-links li {
            margin-bottom: var(--space-sm);
        }
        
        .footer-links a {
            color: rgba(255, 255, 255, 0.8);
            font-size: 0.875rem;
        }
        
        .footer-links a:hover {
            color: var(--color-white);
        }
        
        .footer-bottom {
            border-top: 1px solid rgba(255, 255, 255, 0.2);
            padding-top: var(--space-xl);
            text-align: center;
        }
        
        .footer-bottom p {
            font-size: 0.875rem;
            color: rgba(255, 255, 255, 0.7);
            margin-bottom: var(--space-sm);
        }
        
        /* Utility Classes */
        .text-center { text-align: center; }
        .mb-0 { margin-bottom: 0; }
        .mt-2 { margin-top: var(--space-xl); }
    </style>
</head>
<body>
    <!-- Header -->
    <header class="header">
        <div class="container">
            <div class="header-content">
                <a href="#" class="logo">
                    <i data-lucide="calculator" style="width: 1.75rem; height: 1.75rem; color: var(--color-purple-700);"></i>
                    TaxBuddy NG
                </a>
                <a href="https://ng-tax-hero.lovable.app" target="_blank" class="btn btn-primary">
                    Open App
                    <i data-lucide="external-link" style="width: 1rem; height: 1rem;"></i>
                </a>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <h1>Nigerian Tax Compliance,<br>Made Simple</h1>
            <p class="hero-subtitle">
                Calculate PAYE, track VAT, manage deadlines, and stay compliant with FIRS — all in one clean dashboard.
            </p>
            <div class="hero-actions">
                <a href="https://ng-tax-hero.lovable.app/calculator" target="_blank" class="btn btn-primary">
                    Try Tax Calculator
                    <i data-lucide="arrow-right" style="width: 1.25rem; height: 1.25rem;"></i>
                </a>
                <a href="https://ng-tax-hero.lovable.app/dashboard" target="_blank" class="btn btn-secondary">
                    View Dashboard
                    <i data-lucide="layout-dashboard" style="width: 1.25rem; height: 1.25rem;"></i>
                </a>
            </div>
        </div>
    </section>

    <!-- Product Preview Section -->
    <section class="preview-section">
        <div class="container">
            <div class="section-header">
                <h2>See TaxBuddy NG in Action</h2>
                <p class="section-subtitle">Real tools for real Nigerian tax compliance challenges</p>
            </div>
            
            <div class="preview-grid">
                <!-- Dashboard Card -->
                <div class="card" onclick="window.open('https://ng-tax-hero.lovable.app/dashboard', '_blank')">
                    <div class="card-preview" style="background: linear-gradient(135deg, var(--color-purple-500), var(--color-purple-700));">
                        <i data-lucide="layout-dashboard" style="width: 6rem; height: 6rem; color: rgba(255,255,255,0.2);"></i>
                        <span class="card-badge" style="color: var(--color-purple-700);">Live Dashboard</span>
                    </div>
                    <div class="card-title">
                        <h3>Dashboard Overview</h3>
                        <i data-lucide="external-link" style="width: 1.25rem; height: 1.25rem; color: var(--color-purple-700);"></i>
                    </div>
                    <p style="color: var(--color-gray-700);">Track all your tax obligations, upcoming deadlines, and compliance status in one clean view</p>
                    <div class="card-cta">
                        <span>Open Dashboard</span>
                        <i data-lucide="arrow-right" style="width: 1rem; height: 1rem;"></i>
                    </div>
                </div>

                <!-- Calculator Card -->
                <div class="card" onclick="window.open('https://ng-tax-hero.lovable.app/calculator', '_blank')">
                    <div class="card-preview" style="background: linear-gradient(135deg, var(--color-emerald-500), var(--color-emerald-600));">
                        <i data-lucide="calculator" style="width: 6rem; height: 6rem; color: rgba(255,255,255,0.2);"></i>
                        <span class="card-badge" style="color: var(--color-emerald-600);">PAYE Calculator</span>
                    </div>
                    <div class="card-title">
                        <h3>Tax Calculator</h3>
                        <i data-lucide="external-link" style="width: 1.25rem; height: 1.25rem; color: var(--color-purple-700);"></i>
                    </div>
                    <p style="color: var(--color-gray-700);">Calculate PAYE with Nigeria-specific tax bands, reliefs, and deductions instantly</p>
                    <div class="card-cta">
                        <span>Try Calculator</span>
                        <i data-lucide="arrow-right" style="width: 1rem; height: 1rem;"></i>
                    </div>
                </div>

                <!-- VAT Card -->
                <div class="card" onclick="window.open('https://ng-tax-hero.lovable.app/vat', '_blank')">
                    <div class="card-preview" style="background: linear-gradient(135deg, #3B82F6, #2563EB);">
                        <i data-lucide="trending-up" style="width: 6rem; height: 6rem; color: rgba(255,255,255,0.2);"></i>
                        <span class="card-badge" style="color: #2563EB;">VAT Management</span>
                    </div>
                    <div class="card-title">
                        <h3>VAT Tracker</h3>
                        <i data-lucide="external-link" style="width: 1.25rem; height: 1.25rem; color: var(--color-purple-700);"></i>
                    </div>
                    <p style="color: var(--color-gray-700);">Track VAT obligations, manage monthly returns, and stay above the ₦25M threshold</p>
                    <div class="card-cta">
                        <span>Open VAT Tools</span>
                        <i data-lucide="arrow-right" style="width: 1rem; height: 1rem;"></i>
                    </div>
                </div>

                <!-- Deadlines Card -->
                <div class="card" onclick="window.open('https://ng-tax-hero.lovable.app/deadlines', '_blank')">
                    <div class="card-preview" style="background: linear-gradient(135deg, #F59E0B, #D97706);">
                        <i data-lucide="calendar" style="width: 6rem; height: 6rem; color: rgba(255,255,255,0.2);"></i>
                        <span class="card-badge" style="color: #D97706;">Never Miss Filing</span>
                    </div>
                    <div class="card-title">
                        <h3>Deadline Calendar</h3>
                        <i data-lucide="external-link" style="width: 1.25rem; height: 1.25rem; color: var(--color-purple-700);"></i>
                    </div>
                    <p style="color: var(--color-gray-700);">Automated reminders for PAYE, VAT, PIT, and WHT filing deadlines with alerts</p>
                    <div class="card-cta">
                        <span>View Deadlines</span>
                        <i data-lucide="arrow-right" style="width: 1rem; height: 1rem;"></i>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section class="features-section">
        <div class="container">
            <div class="section-header">
                <h2>Everything You Need for Tax Compliance</h2>
                <p class="section-subtitle">Built specifically for Nigerian tax rules and workflows</p>
            </div>
            
            <div class="features-grid">
                <div class="feature-card">
                    <div class="feature-icon">
                        <i data-lucide="calculator" style="width: 1.5rem; height: 1.5rem; color: white;"></i>
                    </div>
                    <h4 class="feature-title">PAYE & PIT Calculators</h4>
                    <p style="color: var(--color-gray-700);">Accurate calculations using current Nigerian tax bands with automatic relief computation</p>
                </div>

                <div class="feature-card">
                    <div class="feature-icon">
                        <i data-lucide="check-circle" style="width: 1.5rem; height: 1.5rem; color: white;"></i>
                    </div>
                    <h4 class="feature-title">Compliance Checklists</h4>
                    <p style="color: var(--color-gray-700);">Profile-based obligation mapping for salary earners, freelancers, and businesses</p>
                </div>

                <div class="feature-card">
                    <div class="feature-icon">
                        <i data-lucide="calendar" style="width: 1.5rem; height: 1.5rem; color: white;"></i>
                    </div>
                    <h4 class="feature-title">Smart Reminders</h4>
                    <p style="color: var(--color-gray-700);">Never miss PAYE, VAT, or PIT filing deadlines with automated deadline tracking</p>
                </div>

                <div class="feature-card">
                    <div class="feature-icon">
                        <i data-lucide="file-text" style="width: 1.5rem; height: 1.5rem; color: white;"></i>
                    </div>
                    <h4 class="feature-title">Record Organization</h4>
                    <p style="color: var(--color-gray-700);">Keep payslips, WHT certificates, and tax statements organized year-round</p>
                </div>

                <div class="feature-card">
                    <div class="feature-icon">
                        <i data-lucide="trending-up" style="width: 1.5rem; height: 1.5rem; color: white;"></i>
                    </div>
                    <h4 class="feature-title">VAT Management</h4>
                    <p style="color: var(--color-gray-700);">Track turnover thresholds, manage monthly returns, and monitor VAT obligations</p>
                </div>

                <div class="feature-card">
                    <div class="feature-icon">
                        <i data-lucide="shield" style="width: 1.5rem; height: 1.5rem; color: white;"></i>
                    </div>
                    <h4 class="feature-title">Privacy First</h4>
                    <p style="color: var(--color-gray-700);">Your data stays yours — no unauthorized filing or FIRS representation</p>
                </div>
            </div>
        </div>
    </section>

    <!-- CTA Section -->
    <section class="cta-section">
        <div class="container">
            <div class="cta-content">
                <h2>Ready to Simplify Your Tax Compliance?</h2>
                <p style="font-size: 1.25rem; color: var(--color-purple-100); margin-top: var(--space-md);">
                    Join thousands of Nigerians managing their taxes with confidence
                </p>
                
                <div class="email-form">
                    <input type="email" class="email-input" placeholder="Enter your email" id="email-input">
                    <button class="btn btn-primary" onclick="window.open('https://ng-tax-hero.lovable.app/signup', '_blank')">
                        Get Started
                    </button>
                </div>
                
                <button class="btn btn-secondary mt-2" onclick="window.open('https://ng-tax-hero.lovable.app', '_blank')" style="width: 100%; max-width: 32rem;">
                    Or Open App Now
                    <i data-lucide="external-link" style="width: 1rem; height: 1rem;"></i>
                </button>
            </div>
        </div>
    </section>

    <!-- Disclaimer -->
    <section class="disclaimer">
        <div class="container">
            <div class="disclaimer-content">
                <i data-lucide="alert-circle" style="width: 1.5rem; height: 1.5rem; color: var(--color-warning); flex-shrink: 0; margin-top: 0.25rem;"></i>
                <div>
                    <h4 style="font-size: 1.125rem; margin-bottom: 0.5rem; color: var(--color-warning-text);">Important Disclaimer</h4>
                    <p class="disclaimer-text mb-0">
                        TaxBuddy NG provides informational support and workflow tools to help
