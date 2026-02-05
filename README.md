import { Link } from 'react-router-dom';
import { Button } from '@/components/ui/button';
import { 
  CheckCircle, 
  Calendar, 
  FolderOpen, 
  Calculator,
  Shield,
  Bell,
  UserPlus,
  ClipboardCheck,
  Check,
  Sparkles
} from 'lucide-react';
import { Logo } from '@/components/Logo';
import { WaitlistForm } from '@/components/landing/WaitlistForm';
import { useFAQ } from '@/hooks/useFAQ';
import {
  Accordion,
  AccordionContent,
  AccordionItem,
  AccordionTrigger,
} from '@/components/ui/accordion';
import { QUICK_ACCESS_CONFIG, formatCurrency, type PlanKey } from '@/config/quickAccess';

const STEPS = [
  { 
    number: 1, 
    icon: UserPlus, 
    title: 'Sign Up Free', 
    description: 'Create your account in under 2 minutes' 
  },
  { 
    number: 2, 
    icon: ClipboardCheck, 
    title: 'Complete Readiness Check', 
    description: 'Answer questions about your tax situation' 
  },
  { 
    number: 3, 
    icon: Calendar, 
    title: 'Set Up Deadlines', 
    description: 'Import or create tax deadline reminders' 
  },
  { 
    number: 4, 
    icon: CheckCircle, 
    title: 'Stay Compliant', 
    description: 'Get alerts, file on time, avoid penalties' 
  },
];

const features = [
  {
    icon: CheckCircle,
    title: 'TIN Onboarding',
    description: 'Step-by-step checklist to get your Tax Identification Number',
  },
  {
    icon: Calendar,
    title: 'Deadline Tracking',
    description: 'Never miss a VAT, WHT, or income tax deadline again',
  },
  {
    icon: Bell,
    title: 'Smart Reminders',
    description: 'Get email alerts before important tax dates',
  },
  {
    icon: Calculator,
    title: 'Tax Calculators',
    description: 'VAT, WHT, and income tax calculators with Nigerian rates',
  },
  {
    icon: FolderOpen,
    title: 'Document Vault',
    description: 'Securely store and organize all your tax documents',
  },
  {
    icon: Shield,
    title: 'Secure & Private',
    description: 'Your data is encrypted and only accessible by you',
  },
];

const PLAN_ORDER: PlanKey[] = ['FREE', 'PRO', 'BUSINESS'];

const PLAN_FEATURES: Record<PlanKey, string[]> = {
  FREE: [
    'Dashboard & KPIs',
    'Basic AI summary',
    '3 AI explanations/month',
    'Talk to a Tax Agent',
  ],
  PRO: [
    'Everything in Free',
    'Full AI explanations',
    'Daily compliance scan',
    'Anomaly detection',
    'Export PDF/ZIP',
    'Submit remittance',
  ],
  BUSINESS: [
    'Everything in Pro',
    'Multi-user roles',
    'Audit pack export',
    'Rule management',
    'Approval workflows',
  ],
};

export default function Landing() {
  const { faqItems, isLoading: faqLoading } = useFAQ();
  const topFAQs = faqItems?.slice(0, 5) || [];

  return (
    <div className="min-h-screen bg-background">
      {/* Navigation */}
      <nav className="sticky top-0 z-50 border-b border-border bg-background/95 backdrop-blur supports-[backdrop-filter]:bg-background/60">
        <div className="mx-auto flex max-w-6xl items-center justify-between px-4 py-4 sm:px-6 lg:px-8">
          <Link to="/" className="flex items-center">
            <Logo variant="full" size="lg" />
          </Link>
          <div className="hidden items-center gap-6 md:flex">
            <a href="#how-it-works" className="text-sm text-muted-foreground hover:text-foreground transition-colors">
              How It Works
            </a>
            <a href="#features" className="text-sm text-muted-foreground hover:text-foreground transition-colors">
              Features
            </a>
            <a href="#pricing" className="text-sm text-muted-foreground hover:text-foreground transition-colors">
              Pricing
            </a>
            <Link to="/more/calculators" className="text-sm text-muted-foreground hover:text-foreground transition-colors">
              Calculators
            </Link>
            <Link to="/learn" className="text-sm text-muted-foreground hover:text-foreground transition-colors">
              Learning
            </Link>
            <a href="#faq" className="text-sm text-muted-foreground hover:text-foreground transition-colors">
              FAQ
            </a>
          </div>
          <Link to="/auth">
            <Button variant="outline" size="sm">Sign In</Button>
          </Link>
        </div>
      </nav>

      {/* Hero Section */}
      <header className="relative overflow-hidden">
        <div className="absolute inset-0 bg-gradient-to-br from-primary/10 via-background to-accent/20" />
        <div className="relative mx-auto max-w-6xl px-4 py-16 sm:px-6 sm:py-24 lg:px-8">
          <div className="grid gap-12 lg:grid-cols-2 lg:gap-8">
            <div className="flex flex-col justify-center">
              <h2 className="text-3xl font-bold tracking-tight sm:text-4xl lg:text-5xl">
                Tax Compliance Made Simple for Nigerians
              </h2>
              <p className="mt-4 text-lg text-muted-foreground">
                Track deadlines, manage documents, and calculate taxes — all in one app designed for Nigerian individuals and SMEs.
              </p>
              <div className="mt-8 flex flex-col gap-3 sm:flex-row">
                <Link to="/auth?mode=signup">
                  <Button size="lg" className="w-full sm:w-auto">
                    Get Started Free
                  </Button>
                </Link>
                <Link to="/readiness">
                  <Button variant="outline" size="lg" className="w-full sm:w-auto">
                    Check Your Readiness
                  </Button>
                </Link>
              </div>
            </div>
            <div className="flex items-center justify-center">
              <div className="w-full max-w-md rounded-xl border border-border bg-card p-6 shadow-lg">
                <div className="mb-4 flex items-center gap-2">
                  <Sparkles className="h-5 w-5 text-primary" />
                  <h3 className="font-semibold">Join the Waitlist</h3>
                </div>
                <p className="mb-4 text-sm text-muted-foreground">
                  Be the first to know when new features launch
                </p>
                <WaitlistForm />
              </div>
            </div>
          </div>
        </div>
      </header>

      {/* How It Works Section */}
      <section id="how-it-works" className="border-t border-border bg-muted/30 px-4 py-16 sm:px-6 lg:px-8">
        <div className="mx-auto max-w-6xl">
          <h3 className="mb-4 text-center text-2xl font-bold sm:text-3xl">
            How TaxBuddy NG Works
          </h3>
          <p className="mx-auto mb-12 max-w-2xl text-center text-muted-foreground">
            Get started in minutes with our simple 4-step process
          </p>
          <div className="grid gap-8 sm:grid-cols-2 lg:grid-cols-4">
            {STEPS.map((step, index) => {
              const Icon = step.icon;
              return (
                <div key={step.number} className="relative flex flex-col items-center text-center">
                  {/* Connector line */}
                  {index < STEPS.length - 1 && (
                    <div className="absolute left-1/2 top-8 hidden h-0.5 w-full bg-border lg:block" />
                  )}
                  <div className="relative z-10 mb-4 flex h-16 w-16 items-center justify-center rounded-full bg-primary text-primary-foreground shadow-lg">
                    <Icon className="h-8 w-8" />
                  </div>
                  <span className="mb-2 text-sm font-medium text-primary">Step {step.number}</span>
                  <h4 className="mb-2 font-semibold">{step.title}</h4>
                  <p className="text-sm text-muted-foreground">{step.description}</p>
                </div>
              );
            })}
          </div>
        </div>
      </section>

      {/* Features Section */}
      <section id="features" className="border-t border-border px-4 py-16 sm:px-6 lg:px-8">
        <div className="mx-auto max-w-6xl">
          <h3 className="mb-4 text-center text-2xl font-bold sm:text-3xl">
            Features
          </h3>
          <p className="mx-auto mb-12 max-w-2xl text-center text-muted-foreground">
            Everything you need to stay compliant with Nigerian tax laws
          </p>
          <div className="grid gap-6 sm:grid-cols-2 lg:grid-cols-3">
            {features.map((feature) => {
              const Icon = feature.icon;
              return (
                <div
                  key={feature.title}
                  className="rounded-lg border border-border bg-card p-6 transition-shadow hover:shadow-md"
                >
                  <div className="mb-3 inline-flex rounded-lg bg-primary/10 p-2">
                    <Icon className="h-6 w-6 text-primary" />
                  </div>
                  <h4 className="mb-2 font-semibold">{feature.title}</h4>
                  <p className="text-sm text-muted-foreground">{feature.description}</p>
                </div>
              );
            })}
          </div>
        </div>
      </section>

      {/* Pricing Section */}
      <section id="pricing" className="border-t border-border bg-muted/30 px-4 py-16 sm:px-6 lg:px-8">
        <div className="mx-auto max-w-6xl">
          <h3 className="mb-4 text-center text-2xl font-bold sm:text-3xl">
            Simple, Transparent Pricing
          </h3>
          <p className="mx-auto mb-12 max-w-2xl text-center text-muted-foreground">
            Start free and upgrade as you grow. No hidden fees.
          </p>
          <div className="grid gap-6 md:grid-cols-3">
            {PLAN_ORDER.map((planKey) => {
              const plan = QUICK_ACCESS_CONFIG.plans[planKey];
              const isPro = planKey === 'PRO';
              return (
                <div
                  key={planKey}
                  className={`relative rounded-xl border bg-card p-6 ${
                    isPro ? 'border-primary shadow-lg ring-2 ring-primary/20' : 'border-border'
                  }`}
                >
                  {isPro && (
                    <div className="absolute -top-3 left-1/2 -translate-x-1/2">
                      <span className="rounded-full bg-primary px-3 py-1 text-xs font-medium text-primary-foreground">
                        Most Popular
                      </span>
                    </div>
                  )}
                  <div className="mb-4">
                    <h4 className="text-xl font-bold">{plan.label}</h4>
                    <div className="mt-2">
                      {'price' in plan && plan.price ? (
                        <div className="flex items-baseline gap-1">
                          <span className="text-3xl font-bold">{formatCurrency(plan.price.amount)}</span>
                          <span className="text-muted-foreground">/month</span>
                        </div>
                      ) : (
                        <span className="text-3xl font-bold">Free</span>
                      )}
                    </div>
                  </div>
                  <ul className="mb-6 space-y-3">
                    {PLAN_FEATURES[planKey].map((feature) => (
                      <li key={feature} className="flex items-start gap-2 text-sm">
                        <Check className="mt-0.5 h-4 w-4 shrink-0 text-primary" />
                        <span>{feature}</span>
                      </li>
                    ))}
                  </ul>
                  <Link to="/auth?mode=signup" className="block">
                    <Button 
                      className="w-full" 
                      variant={isPro ? 'default' : 'outline'}
                    >
                      {planKey === 'FREE' ? 'Get Started' : `Upgrade to ${plan.label}`}
                    </Button>
                  </Link>
                </div>
              );
            })}
          </div>
          <p className="mt-8 text-center text-sm text-muted-foreground">
            Need a custom plan?{' '}
            <Link to="/auth" className="text-primary hover:underline">
              Contact us
            </Link>
          </p>
        </div>
      </section>

      {/* FAQ Section */}
      <section id="faq" className="border-t border-border px-4 py-16 sm:px-6 lg:px-8">
        <div className="mx-auto max-w-3xl">
          <h3 className="mb-4 text-center text-2xl font-bold sm:text-3xl">
            Frequently Asked Questions
          </h3>
          <p className="mx-auto mb-12 max-w-2xl text-center text-muted-foreground">
            Got questions? We've got answers.
          </p>
          {faqLoading ? (
            <div className="space-y-4">
              {[1, 2, 3].map((i) => (
                <div key={i} className="h-16 animate-pulse rounded-lg bg-muted" />
              ))}
            </div>
          ) : topFAQs.length > 0 ? (
            <Accordion type="single" collapsible className="w-full">
              {topFAQs.map((item) => (
                <AccordionItem key={item.id} value={item.id}>
                  <AccordionTrigger className="text-left">
                    {item.question}
                  </AccordionTrigger>
                  <AccordionContent className="text-muted-foreground">
                    {item.answer}
                  </AccordionContent>
                </AccordionItem>
              ))}
            </Accordion>
          ) : (
            <p className="text-center text-muted-foreground">
              FAQs coming soon!
            </p>
          )}
          <div className="mt-8 text-center">
            <Link to="/more/faq">
              <Button variant="outline">See All FAQs</Button>
            </Link>
          </div>
        </div>
      </section>

      {/* CTA Section */}
      <section className="border-t border-border bg-primary/5 px-4 py-12 sm:px-6 lg:px-8">
        <div className="mx-auto max-w-lg text-center">
          <h3 className="text-xl font-bold">Ready to simplify your taxes?</h3>
          <p className="mt-2 text-muted-foreground">
            Join thousands of Nigerians who trust TaxBuddy NG
          </p>
          <Link to="/auth?mode=signup" className="mt-6 inline-block">
            <Button size="lg">Create Free Account</Button>
          </Link>
        </div>
      </section>

      {/* Footer */}
      <footer className="border-t border-border px-4 py-6 text-center text-sm text-muted-foreground">
        <p>© 2025 TaxBuddy NG. All rights reserved.</p>
      </footer>
    </div>
  );
}
