import React, { useState } from 'react';
import { Calculator, CheckCircle, Calendar, FileText, ArrowRight, ExternalLink, LayoutDashboard, TrendingUp, AlertCircle, Shield } from 'lucide-react';

const APP_URL = 'https://ng-tax-hero.lovable.app';

export default function TaxBuddyNGMarketing() {
  const [email, setEmail] = useState('');

  const openApp = (route = '') => {
    window.open(`${APP_URL}${route}`, '_blank');
  };

  return (
    <div className="min-h-screen bg-white">
      {/* Header */}
      <header className="fixed top-0 w-full bg-white/95 backdrop-blur-sm shadow-sm z-50 border-b border-gray-100">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="flex items-center justify-between h-16">
            <div className="flex items-center space-x-2">
              <Calculator className="w-7 h-7 text-purple-600" />
              <span className="text-xl font-bold text-gray-900">TaxBuddy NG</span>
            </div>
            <button 
              onClick={() => openApp()}
              className="px-6 py-2.5 bg-purple-600 text-white rounded-lg font-semibold hover:bg-purple-700 transition flex items-center space-x-2 shadow-sm"
            >
              <span>Open App</span>
              <ExternalLink className="w-4 h-4" />
            </button>
          </div>
        </div>
      </header>

      {/* Hero Section */}
      <section className="pt-32 pb-20 px-4 bg-gradient-to-br from-purple-600 via-purple-700 to-indigo-900">
        <div className="max-w-6xl mx-auto">
          <div className="text-center space-y-8">
            <h1 className="text-5xl md:text-6xl lg:text-7xl font-bold text-white leading-tight">
              Nigerian Tax Compliance,<br />
              <span className="text-purple-200">Made Simple</span>
            </h1>
            <p className="text-xl md:text-2xl text-purple-100 max-w-3xl mx-auto leading-relaxed">
              Calculate PAYE, track VAT, manage deadlines, and stay compliant with FIRS — all in one clean dashboard.
            </p>
            <div className="flex flex-col sm:flex-row gap-4 justify-center pt-6">
              <button 
                onClick={() => openApp('/calculator')}
                className="group px-8 py-4 bg-white text-purple-700 rounded-xl font-bold text-lg hover:bg-purple-50 transition shadow-xl inline-flex items-center justify-center space-x-2"
              >
                <span>Try Tax Calculator</span>
                <ArrowRight className="w-5 h-5 group-hover:translate-x-1 transition-transform" />
              </button>
              <button 
                onClick={() => openApp('/dashboard')}
                className="px-8 py-4 bg-purple-800 text-white border-2 border-white/30 rounded-xl font-bold text-lg hover:bg-purple-900 transition inline-flex items-center justify-center space-x-2"
              >
                <span>View Dashboard</span>
                <LayoutDashboard className="w-5 h-5" />
              </button>
            </div>
          </div>
        </div>
      </section>

      {/* Product Preview Section */}
      <section className="py-20 px-4 bg-gray-50">
        <div className="max-w-7xl mx-auto">
          <div className="text-center mb-16">
            <h2 className="text-4xl md:text-5xl font-bold text-gray-900 mb-4">
              See TaxBuddy NG in Action
            </h2>
            <p className="text-xl text-gray-600 max-w-2xl mx-auto">
              Real tools for real Nigerian tax compliance challenges
            </p>
          </div>

          <div className="grid md:grid-cols-2 gap-8">
            {/* Dashboard Preview */}
            <div 
              onClick={() => openApp('/dashboard')}
              className="group cursor-pointer bg-white rounded-2xl p-8 shadow-lg hover:shadow-2xl transition border border-gray-100"
            >
              <div className="bg-gradient-to-br from-purple-500 to-indigo-600 rounded-xl h-48 mb-6 flex items-center justify-center relative overflow-hidden">
                <LayoutDashboard className="w-24 h-24 text-white/20" />
                <div className="absolute inset-0 bg-gradient-to-t from-black/20 to-transparent" />
                <span className="absolute bottom-4 right-4 px-3 py-1 bg-white/90 text-purple-700 text-sm font-semibold rounded-lg">
                  Live Dashboard
                </span>
              </div>
              <h3 className="text-2xl font-bold text-gray-900 mb-3 flex items-center justify-between">
                Dashboard Overview
                <ExternalLink className="w-5 h-5 text-purple-600 opacity-0 group-hover:opacity-100 transition" />
              </h3>
              <p className="text-gray-600 mb-4">
                Track all your tax obligations, upcoming deadlines, and compliance status in one clean view
              </p>
              <div className="flex items-center text-purple-600 font-semibold">
                <span>Open Dashboard</span>
                <ArrowRight className="w-4 h-4 ml-2 group-hover:translate-x-1 transition-transform" />
              </div>
            </div>

            {/* Calculator Preview */}
            <div 
              onClick={() => openApp('/calculator')}
              className="group cursor-pointer bg-white rounded-2xl p-8 shadow-lg hover:shadow-2xl transition border border-gray-100"
            >
              <div className="bg-gradient-to-br from-green-500 to-emerald-600 rounded-xl h-48 mb-6 flex items-center justify-center relative overflow-hidden">
                <Calculator className="w-24 h-24 text-white/20" />
                <div className="absolute inset-0 bg-gradient-to-t from-black/20 to-transparent" />
                <span className="absolute bottom-4 right-4 px-3 py-1 bg-white/90 text-green-700 text-sm font-semibold rounded-lg">
                  PAYE Calculator
                </span>
              </div>
              <h3 className="text-2xl font-bold text-gray-900 mb-3 flex items-center justify-between">
                Tax Calculator
                <ExternalLink className="w-5 h-5 text-purple-600 opacity-0 group-hover:opacity-100 transition" />
              </h3>
              <p className="text-gray-600 mb-4">
                Calculate PAYE with Nigeria-specific tax bands, reliefs, and deductions instantly
              </p>
              <div className="flex items-center text-purple-600 font-semibold">
                <span>Try Calculator</span>
                <ArrowRight className="w-4 h-4 ml-2 group-hover:translate-x-1 transition-transform" />
              </div>
            </div>

            {/* VAT Tracker */}
            <div 
              onClick={() => openApp('/vat')}
              className="group cursor-pointer bg-white rounded-2xl p-8 shadow-lg hover:shadow-2xl transition border border-gray-100"
            >
              <div className="bg-gradient-to-br from-blue-500 to-cyan-600 rounded-xl h-48 mb-6 flex items-center justify-center relative overflow-hidden">
                <TrendingUp className="w-24 h-24 text-white/20" />
                <div className="absolute inset-0 bg-gradient-to-t from-black/20 to-transparent" />
                <span className="absolute bottom-4 right-4 px-3 py-1 bg-white/90 text-blue-700 text-sm font-semibold rounded-lg">
                  VAT Management
                </span>
              </div>
              <h3 className="text-2xl font-bold text-gray-900 mb-3 flex items-center justify-between">
                VAT Tracker
                <ExternalLink className="w-5 h-5 text-purple-600 opacity-0 group-hover:opacity-100 transition" />
              </h3>
              <p className="text-gray-600 mb-4">
                Track VAT obligations, manage monthly returns, and stay above the ₦25M threshold
              </p>
              <div className="flex items-center text-purple-600 font-semibold">
                <span>Open VAT Tools</span>
                <ArrowRight className="w-4 h-4 ml-2 group-hover:translate-x-1 transition-transform" />
              </div>
            </div>

            {/* Deadlines */}
            <div 
              onClick={() => openApp('/deadlines')}
              className="group cursor-pointer bg-white rounded-2xl p-8 shadow-lg hover:shadow-2xl transition border border-gray-100"
            >
              <div className="bg-gradient-to-br from-orange-500 to-red-600 rounded-xl h-48 mb-6 flex items-center justify-center relative overflow-hidden">
                <Calendar className="w-24 h-24 text-white/20" />
                <div className="absolute inset-0 bg-gradient-to-t from-black/20 to-transparent" />
                <span className="absolute bottom-4 right-4 px-3 py-1 bg-white/90 text-orange-700 text-sm font-semibold rounded-lg">
                  Never Miss Filing
                </span>
              </div>
              <h3 className="text-2xl font-bold text-gray-900 mb-3 flex items-center justify-between">
                Deadline Calendar
                <ExternalLink className="w-5 h-5 text-purple-600 opacity-0 group-hover:opacity-100 transition" />
              </h3>
              <p className="text-gray-600 mb-4">
                Automated reminders for PAYE, VAT, PIT, and WHT filing deadlines with alerts
              </p>
              <div className="flex items-center text-purple-600 font-semibold">
                <span>View Deadlines</span>
                <ArrowRight className="w-4 h-4 ml-2 group-hover:translate-x-1 transition-transform" />
              </div>
            </div>
          </div>
        </div>
      </section>

      {/* Features Section */}
      <section className="py-20 px-4 bg-white">
        <div className="max-w-7xl mx-auto">
          <div className="text-center mb-16">
            <h2 className="text-4xl md:text-5xl font-bold text-gray-900 mb-4">
              Everything You Need for Tax Compliance
            </h2>
            <p className="text-xl text-gray-600 max-w-2xl mx-auto">
              Built specifically for Nigerian tax rules and workflows
            </p>
          </div>

          <div className="grid md:grid-cols-3 gap-8">
            <div className="p-8 rounded-2xl bg-purple-50 border border-purple-100">
              <div className="w-12 h-12 bg-purple-600 rounded-xl flex items-center justify-center mb-6">
                <Calculator className="w-6 h-6 text-white" />
              </div>
              <h3 className="text-xl font-bold text-gray-900 mb-3">PAYE & PIT Calculators</h3>
              <p className="text-gray-600 leading-relaxed">
                Accurate calculations using current Nigerian tax bands with automatic relief computation
              </p>
            </div>

            <div className="p-8 rounded-2xl bg-purple-50 border border-purple-100">
              <div className="w-12 h-12 bg-purple-600 rounded-xl flex items-center justify-center mb-6">
                <CheckCircle className="w-6 h-6 text-white" />
              </div>
              <h3 className="text-xl font-bold text-gray-900 mb-3">Compliance Checklists</h3>
              <p className="text-gray-600 leading-relaxed">
                Profile-based obligation mapping for salary earners, freelancers, and businesses
              </p>
            </div>

            <div className="p-8 rounded-2xl bg-purple-50 border border-purple-100">
              <div className="w-12 h-12 bg-purple-600 rounded-xl flex items-center justify-center mb-6">
                <Calendar className="w-6 h-6 text-white" />
              </div>
              <h3 className="text-xl font-bold text-gray-900 mb-3">Smart Reminders</h3>
              <p className="text-gray-600 leading-relaxed">
                Never miss PAYE, VAT, or PIT filing deadlines with automated deadline tracking
              </p>
            </div>

            <div className="p-8 rounded-2xl bg-purple-50 border border-purple-100">
              <div className="w-12 h-12 bg-purple-600 rounded-xl flex items-center justify-center mb-6">
                <FileText className="w-6 h-6 text-white" />
              </div>
              <h3 className="text-xl font-bold text-gray-900 mb-3">Record Organization</h3>
              <p className="text-gray-600 leading-relaxed">
                Keep payslips, WHT certificates, and tax statements organized year-round
              </p>
            </div>

            <div className="p-8 rounded-2xl bg-purple-50 border border-purple-100">
              <div className="w-12 h-12 bg-purple-600 rounded-xl flex items-center justify-center mb-6">
                <TrendingUp className="w-6 h-6 text-white" />
              </div>
              <h3 className="text-xl font-bold text-gray-900 mb-3">VAT Management</h3>
              <p className="text-gray-600 leading-relaxed">
                Track turnover thresholds, manage monthly returns, and monitor VAT obligations
              </p>
            </div>

            <div className="p-8 rounded-2xl bg-purple-50 border border-purple-100">
              <div className="w-12 h-12 bg-purple-600 rounded-xl flex items-center justify-center mb-6">
                <Shield className="w-6 h-6 text-white" />
              </div>
              <h3 className="text-xl font-bold text-gray-900 mb-3">Privacy First</h3>
              <p className="text-gray-600 leading-relaxed">
                Your data stays yours — no unauthorized filing or FIRS representation
              </p>
            </div>
          </div>
        </div>
      </section>

      {/* Who We Help */}
      <section className="py-20 px-4 bg-gray-50">
        <div className="max-w-6xl mx-auto">
          <div className="text-center mb-16">
            <h2 className="text-4xl md:text-5xl font-bold text-gray-900 mb-4">
              Who We Help
            </h2>
            <p className="text-xl text-gray-600">
              Tax compliance support for every Nigerian taxpayer
            </p>
          </div>

          <div className="grid md:grid-cols-2 lg:grid-cols-4 gap-6">
            <div className="bg-white p-6 rounded-xl shadow-sm hover:shadow-lg transition border border-gray-100">
              <h3 className="font-bold text-gray-900 text-lg mb-2">Salary Earners</h3>
              <p className="text-gray-600 text-sm">
                Verify PAYE deductions, claim reliefs, and understand your tax obligations
              </p>
            </div>

            <div className="bg-white p-6 rounded-xl shadow-sm hover:shadow-lg transition border border-gray-100">
              <h3 className="font-bold text-gray-900 text-lg mb-2">Freelancers</h3>
              <p className="text-gray-600 text-sm">
                Manage irregular income, track WHT, and file quarterly PIT returns
              </p>
            </div>

            <div className="bg-white p-6 rounded-xl shadow-sm hover:shadow-lg transition border border-gray-100">
              <h3 className="font-bold text-gray-900 text-lg mb-2">SME Owners</h3>
              <p className="text-gray-600 text-sm">
                Handle VAT registration, employee PAYE, and business tax filings
              </p>
            </div>

            <div className="bg-white p-6 rounded-xl shadow-sm hover:shadow-lg transition border border-gray-100">
              <h3 className="font-bold text-gray-900 text-lg mb-2">Contractors</h3>
              <p className="text-gray-600 text-sm">
                Maintain clean compliance records for government and corporate contracts
              </p>
            </div>
          </div>
        </div>
      </section>

      {/* Early Access CTA */}
      <section className="py-20 px-4 bg-gradient-to-br from-purple-600 via-purple-700 to-indigo-900">
        <div className="max-w-4xl mx-auto text-center">
          <h2 className="text-4xl md:text-5xl font-bold text-white mb-6">
            Ready to Simplify Your Tax Compliance?
          </h2>
          <p className="text-xl text-purple-100 mb-10">
            Join thousands of Nigerians managing their taxes with confidence
          </p>
          
          <div className="max-w-md mx-auto space-y-4">
            <div className="flex gap-3">
              <input
                type="email"
                value={email}
                onChange={(e) => setEmail(e.target.value)}
                placeholder="Enter your email"
                className="flex-1 px-6 py-4 rounded-xl text-gray-900 placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-white/50"
              />
              <button 
                onClick={() => openApp('/signup')}
                className="px-8 py-4 bg-white text-purple-700 rounded-xl font-bold hover:bg-purple-50 transition shadow-xl whitespace-nowrap"
              >
                Get Started
              </button>
            </div>
            <button 
              onClick={() => openApp()}
              className="w-full px-8 py-4 bg-purple-800 text-white border-2 border-white/30 rounded-xl font-semibold hover:bg-purple-900 transition inline-flex items-center justify-center space-x-2"
            >
              <span>Or Open App Now</span>
              <ExternalLink className="w-4 h-4" />
            </button>
          </div>
        </div>
      </section>

      {/* Compliance Disclaimer */}
      <section className="py-12 px-4 bg-amber-50 border-y border-amber-200">
        <div className="max-w-4xl mx-auto">
          <div className="flex items-start space-x-4">
            <AlertCircle className="w-6 h-6 text-amber-600 flex-shrink-0 mt-1" />
            <div className="space-y-2">
              <h3 className="font-bold text-gray-900 text-lg">Important Disclaimer</h3>
              <p className="text-gray-700 text-sm leading-relaxed">
                TaxBuddy NG provides informational support and workflow tools to help users understand tax obligations. 
                <strong className="text-gray-900"> It does not provide legal or tax advice and is not affiliated with FIRS or any Nigerian tax authority.</strong> 
                {' '}All calculations are estimates based on publicly available tax bands. Individual circumstances vary. 
                For personalized tax advice, please consult a qualified tax professional or chartered accountant.
              </p>
            </div>
          </div>
        </div>
      </section>

      {/* Footer */}
      <footer className="bg-gradient-to-r from-indigo-900 via-purple-900 to-purple-800 text-white py-16 px-4">
        <div className="max-w-7xl mx-auto">
          <div className="grid md:grid-cols-4 gap-12 mb-12">
            <div>
              <div className="flex items-center space-x-2 mb-4">
                <Calculator className="w-6 h-6" />
                <span className="text-lg font-bold">TaxBuddy NG</span>
              </div>
              <p className="text-purple-200 text-sm leading-relaxed">
                Making Nigerian tax compliance clear, simple, and manageable for everyone.
              </p>
            </div>

            <div>
              <h4 className="font-bold text-lg mb-4">Product</h4>
              <ul className="space-y-3 text-sm text-purple-200">
                <li>
                  <button onClick={() => openApp('/calculator')} className="hover:text-white transition">
                    Tax Calculator
                  </button>
                </li>
                <li>
                  <button onClick={() => openApp('/dashboard')} className="hover:text-white transition">
                    Dashboard
                  </button>
                </li>
                <li>
                  <button onClick={() => openApp('/deadlines')} className="hover:text-white transition">
                    Deadline Tracker
                  </button>
                </li>
                <li>
                  <button onClick={() => openApp('/vat')} className="hover:text-white transition">
                    VAT Management
                  </button>
                </li>
              </ul>
            </div>

            <div>
              <h4 className="font-bold text-lg mb-4">Company</h4>
              <ul className="space-y-3 text-sm text-purple-200">
                <li className="hover:text-white cursor-pointer transition">About Us</li>
                <li className="hover:text-white cursor-pointer transition">Privacy Policy</li>
                <li className="hover:text-white cursor-pointer transition">Terms of Service</li>
                <li className="hover:text-white cursor-pointer transition">Contact Support</li>
              </ul>
            </div>

            <div>
              <h4 className="font-bold text-lg mb-4">Resources</h4>
              <ul className="space-y-3 text-sm text-purple-200">
                <li className="hover:text-white cursor-pointer transition">Tax Guide</li>
                <li className="hover:text-white cursor-pointer transition">FIRS Updates</li>
                <li className="hover:text-white cursor-pointer transition">Help Center</li>
                <li className="hover:text-white cursor-pointer transition">Blog</li>
              </ul>
            </div>
          </div>

          <div className="border-t border-purple-700 pt-8 text-center space-y-2">
            <p className="text-sm text-purple-300">
              © 2026 TaxBuddy NG. Not affiliated with FIRS or any Nigerian tax authority.
            </p>
            <p className="text-xs text-purple-400">
              Informational support only • Not legal or tax advice • Consult professionals for personalized guidance
            </p>
          </div>
        </div>
      </footer>
    </div>
  );
}
