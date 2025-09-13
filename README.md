import React, { useState } from 'react';
import { 
  DollarSign, Check, Star, Users, Shield, Zap, ArrowRight, 
  Play, ChevronDown, Menu, X, Mail, Phone, MapPin,
  BarChart3, Clock, FileText, CreditCard, Globe, Smartphone
} from 'lucide-react';

const LandingPage = () => {
  const [mobileMenuOpen, setMobileMenuOpen] = useState(false);
  const [selectedPlan, setSelectedPlan] = useState('pro');
  const [email, setEmail] = useState('');

  const features = [
    {
      icon: <FileText className="w-6 h-6" />,
      title: "Professional Invoices",
      description: "Create beautiful, branded invoices in seconds with our intuitive editor."
    },
    {
      icon: <CreditCard className="w-6 h-6" />,
      title: "Instant Payments",
      description: "Get paid faster with integrated Stripe, PayPal, and bank transfer options."
    },
    {
      icon: <Clock className="w-6 h-6" />,
      title: "Recurring Billing",
      description: "Automate subscription invoices and never miss a payment again."
    },
    {
      icon: <BarChart3 className="w-6 h-6" />,
      title: "Advanced Analytics",
      description: "Track revenue, monitor cash flow, and analyze client payment patterns."
    },
    {
      icon: <Smartphone className="w-6 h-6" />,
      title: "Mobile Ready",
      description: "Access your invoices anywhere with our mobile-optimized platform."
    },
    {
      icon: <Shield className="w-6 h-6" />,
      title: "Bank-Level Security",
      description: "Your data is protected with enterprise-grade encryption and security."
    }
  ];

  const testimonials = [
    {
      name: "Sarah Johnson",
      role: "Freelance Designer",
      company: "Design Studio Pro",
      content: "InvoicePro cut my invoicing time by 80%. The automated reminders alone have improved my cash flow dramatically.",
      rating: 5,
      avatar: "https://images.unsplash.com/photo-1494790108755-2616b612b786?w=64&h=64&fit=crop&crop=face"
    },
    {
      name: "Michael Chen",
      role: "Agency Owner",
      company: "Digital Marketing Co",
      content: "Finally, an invoicing solution that grows with your business. The analytics help me make better financial decisions.",
      rating: 5,
      avatar: "https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?w=64&h=64&fit=crop&crop=face"
    },
    {
      name: "Emily Rodriguez",
      role: "Consultant",
      company: "Business Solutions LLC",
      content: "My clients love the professional look of the invoices, and I love how easy it is to track everything.",
      rating: 5,
      avatar: "https://images.unsplash.com/photo-1438761681033-6461ffad8d80?w=64&h=64&fit=crop&crop=face"
    }
  ];

  const pricingPlans = [
    {
      id: 'starter',
      name: 'Starter',
      price: 9,
      description: 'Perfect for freelancers and small businesses',
      features: [
        'Up to 50 invoices/month',
        'Basic payment processing',
        'Email support',
        '5 clients maximum',
        'Basic reporting'
      ],
      popular: false
    },
    {
      id: 'pro',
      name: 'Professional',
      price: 29,
      description: 'Best for growing businesses',
      features: [
        'Unlimited invoices',
        'Advanced payment processing',
        'Recurring billing',
        'Unlimited clients',
        'Advanced analytics',
        'Priority support',
        'Custom branding',
        'API access'
      ],
      popular: true
    },
    {
      id: 'enterprise',
      name: 'Enterprise',
      price: 79,
      description: 'For large teams and agencies',
      features: [
        'Everything in Pro',
        'Multi-user accounts',
        'White-label solution',
        'Advanced integrations',
        'Dedicated account manager',
        'Custom onboarding',
        'SLA guarantee',
        '99.9% uptime'
      ],
      popular: false
    }
  ];

  const handleSignUp = (planId) => {
    // Redirect to signup with plan parameter
    window.location.href = `/signup?plan=${planId}&email=${encodeURIComponent(email)}`;
  };

  return (
    <div className="min-h-screen bg-white">
      {/* Navigation */}
      <nav className="bg-white shadow-sm border-b sticky top-0 z-50">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="flex justify-between h-16">
            <div className="flex items-center">
              <div className="flex items-center gap-2">
                <div className="bg-blue-600 p-2 rounded-lg">
                  <DollarSign className="w-6 h-6 text-white" />
                </div>
                <span className="text-2xl font-bold text-gray-900">InvoicePro</span>
              </div>
            </div>
            
            <div className="hidden md:flex items-center space-x-8">
              <a href="#features" className="text-gray-600 hover:text-gray-900 transition-colors">Features</a>
              <a href="#pricing" className="text-gray-600 hover:text-gray-900 transition-colors">Pricing</a>
              <a href="#testimonials" className="text-gray-600 hover:text-gray-900 transition-colors">Reviews</a>
              <a href="/login" className="text-gray-600 hover:text-gray-900 transition-colors">Login</a>
              <button 
                onClick={() => handleSignUp('pro')}
                className="bg-blue-600 text-white px-4 py-2 rounded-lg hover:bg-blue-700 transition-colors"
              >
                Start Free Trial
              </button>
            </div>

            <div className="md:hidden flex items-center">
              <button onClick={() => setMobileMenuOpen(!mobileMenuOpen)}>
                {mobileMenuOpen ? <X className="w-6 h-6" /> : <Menu className="w-6 h-6" />}
              </button>
            </div>
          </div>
        </div>

        {/* Mobile menu */}
        {mobileMenuOpen && (
          <div className="md:hidden bg-white border-t">
            <div className="px-2 pt-2 pb-3 space-y-1">
              <a href="#features" className="block px-3 py-2 text-gray-600">Features</a>
              <a href="#pricing" className="block px-3 py-2 text-gray-600">Pricing</a>
              <a href="#testimonials" className="block px-3 py-2 text-gray-600">Reviews</a>
              <a href="/login" className="block px-3 py-2 text-gray-600">Login</a>
              <button 
                onClick={() => handleSignUp('pro')}
                className="w-full text-left px-3 py-2 text-blue-600 font-medium"
              >
                Start Free Trial
              </button>
            </div>
          </div>
        )}
      </nav>

      {/* Hero Section */}
      <section className="bg-gradient-to-br from-blue-50 via-white to-purple-50 py-20">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
            <div>
              <div className="inline-flex items-center gap-2 bg-blue-100 text-blue-800 px-3 py-1 rounded-full text-sm font-medium mb-6">
                <Star className="w-4 h-4" />
                Trusted by 10,000+ businesses
              </div>
              
              <h1 className="text-5xl lg:text-6xl font-bold text-gray-900 mb-6 leading-tight">
                Get Paid Faster with 
                <span className="text-blue-600"> Professional Invoices</span>
              </h1>
              
              <p className="text-xl text-gray-600 mb-8 leading-relaxed">
                Create, send, and track invoices in minutes. Accept payments online, 
                automate follow-ups, and get powerful insights to grow your business.
              </p>

              <div className="flex flex-col sm:flex-row gap-4 mb-8">
                <div className="flex-1">
                  <input
                    type="email"
                    placeholder="Enter your email address"
                    value={email}
                    onChange={(e) => setEmail(e.target.value)}
                    className="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-blue-500 text-lg"
                  />
                </div>
                <button 
                  onClick={() => handleSignUp('pro')}
                  className="bg-blue-600 text-white px-8 py-3 rounded-lg hover:bg-blue-700 transition-colors font-semibold text-lg flex items-center gap-2 justify-center"
                >
                  Start Free Trial
                  <ArrowRight className="w-5 h-5" />
                </button>
              </div>

              <div className="flex items-center gap-6 text-sm text-gray-600">
                <div className="flex items-center gap-1">
                  <Check className="w-4 h-4 text-green-500" />
                  14-day free trial
                </div>
                <div className="flex items-center gap-1">
                  <Check className="w-4 h-4 text-green-500" />
                  No credit card required
                </div>
                <div className="flex items-center gap-1">
                  <Check className="w-4 h-4 text-green-500" />
                  Cancel anytime
                </div>
              </div>
            </div>

            <div className="relative">
              <div className="bg-white rounded-2xl shadow-2xl p-6 transform rotate-3 hover:rotate-0 transition-transform duration-300">
                <div className="bg-blue-600 text-white p-4 rounded-lg mb-4">
                  <h3 className="font-semibold text-lg mb-2">INVOICE #INV-2025-001</h3>
                  <div className="flex justify-between items-center">
                    <span>Acme Corporation</span>
                    <span className="bg-green-500 px-2 py-1 rounded text-sm">PAID</span>
                  </div>
                </div>
                <div className="space-y-3">
                  <div className="flex justify-between">
                    <span className="text-gray-600">Web Development</span>
                    <span className="font-semibold">$2,500.00</span>
                  </div>
                  <div className="flex justify-between">
                    <span className="text-gray-600">Tax (8.5%)</span>
                    <span className="font-semibold">$212.50</span>
                  </div>
                  <div className="border-t pt-3 flex justify-between text-lg font-bold">
                    <span>Total</span>
                    <span className="text-green-600">$2,712.50</span>
                  </div>
                </div>
              </div>
              
              {/* Floating elements */}
              <div className="absolute -top-4 -left-4 bg-green-100 text-green-800 px-3 py-2 rounded-lg text-sm font-medium animate-bounce">
                Payment Received!
              </div>
              <div className="absolute -bottom-4 -right-4 bg-blue-100 text-blue-800 px-3 py-2 rounded-lg text-sm font-medium">
                Auto-Generated
              </div>
            </div>
          </div>
        </div>
      </section>

      {/* Features Section */}
      <section id="features" className="py-20 bg-gray-50">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="text-center mb-16">
            <h2 className="text-4xl font-bold text-gray-900 mb-4">
              Everything You Need to Get Paid
            </h2>
            <p className="text-xl text-gray-600 max-w-2xl mx-auto">
              From invoice creation to payment tracking, InvoicePro handles every aspect 
              of your billing workflow so you can focus on growing your business.
            </p>
          </div>

          <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            {features.map((feature, index) => (
              <div key={index} className="bg-white p-6 rounded-xl shadow-sm hover:shadow-md transition-shadow">
                <div className="bg-blue-100 text-blue-600 p-3 rounded-lg inline-block mb-4">
                  {feature.icon}
                </div>
                <h3 className="text-xl font-semibold text-gray-900 mb-2">
                  {feature.title}
                </h3>
                <p className="text-gray-600">
                  {feature.description}
                </p>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* Testimonials Section */}
      <section id="testimonials" className="py-20 bg-white">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="text-center mb-16">
            <h2 className="text-4xl font-bold text-gray-900 mb-4">
              Loved by Thousands of Businesses
            </h2>
            <p className="text-xl text-gray-600">
              See what our customers have to say about InvoicePro
            </p>
          </div>

          <div className="grid grid-cols-1 md:grid-cols-3 gap-8">
            {testimonials.map((testimonial, index) => (
              <div key={index} className="bg-gray-50 p-6 rounded-xl">
                <div className="flex items-center gap-1 mb-4">
                  {[...Array(testimonial.rating)].map((_, i) => (
                    <Star key={i} className="w-5 h-5 text-yellow-400 fill-current" />
                  ))}
                </div>
                <p className="text-gray-700 mb-6 italic">
                  "{testimonial.content}"
                </p>
                <div className="flex items-center gap-3">
                  <img 
                    src={testimonial.avatar} 
                    alt={testimonial.name}
                    className="w-12 h-12 rounded-full"
                  />
                  <div>
                    <div className="font-semibold text-gray-900">{testimonial.name}</div>
                    <div className="text-gray-600 text-sm">{testimonial.role} at {testimonial.company}</div>
                  </div>
                </div>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* Pricing Section */}
      <section id="pricing" className="py-20 bg-gray-900 text-white">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="text-center mb-16">
            <h2 className="text-4xl font-bold mb-4">
              Simple, Transparent Pricing
            </h2>
            <p className="text-xl text-gray-300">
              Choose the perfect plan for your business. Upgrade or downgrade at any time.
            </p>
          </div>

          <div className="grid grid-cols-1 md:grid-cols-3 gap-8">
            {pricingPlans.map((plan) => (
              <div 
                key={plan.id} 
                className={`relative bg-gray-800 rounded-2xl p-8 ${
                  plan.popular ? 'ring-2 ring-blue-500 scale-105' : ''
                }`}
              >
                {plan.popular && (
                  <div className="absolute -top-4 left-1/2 transform -translate-x-1/2">
                    <span className="bg-blue-500 text-white px-4 py-1 rounded-full text-sm font-medium">
                      Most Popular
                    </span>
                  </div>
                )}
                
                <div className="text-center mb-8">
                  <h3 className="text-2xl font-bold mb-2">{plan.name}</h3>
                  <div className="mb-4">
                    <span className="text-4xl font-bold">${plan.price}</span>
                    <span className="text-gray-400">/month</span>
                  </div>
                  <p className="text-gray-300">{plan.description}</p>
                </div>

                <ul className="space-y-3 mb-8">
                  {plan.features.map((feature, index) => (
                    <li key={index} className="flex items-center gap-3">
                      <Check className="w-5 h-5 text-green-400 flex-shrink-0" />
                      <span className="text-gray-300">{feature}</span>
                    </li>
                  ))}
                </ul>

                <button
                  onClick={() => handleSignUp(plan.id)}
                  className={`w-full py-3 rounded-lg font-semibold transition-colors ${
                    plan.popular
                      ? 'bg-blue-600 hover:bg-blue-700 text-white'
                      : 'bg-gray-700 hover:bg-gray-600 text-white'
                  }`}
                >
                  Start {plan.name} Plan
                </button>
              </div>
            ))}
          </div>

          <div className="text-center mt-12">
            <p className="text-gray-400 mb-4">
              All plans include 14-day free trial • No setup fees • Cancel anytime
            </p>
            <div className="flex justify-center items-center gap-8 text-sm text-gray-500">
              <div className="flex items-center gap-2">
                <Shield className="w-4 h-4" />
                Bank-level security
              </div>
              <div className="flex items-center gap-2">
                <Globe className="w-4 h-4" />
                99.9% uptime SLA
              </div>
              <div className="flex items-center gap-2">
                <Users className="w-4 h-4" />
                24/7 support
              </div>
            </div>
          </div>
        </div>
      </section>

      {/* Final CTA Section */}
      <section className="py-20 bg-blue-600 text-white">
        <div className="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
          <h2 className="text-4xl font-bold mb-4">
            Ready to Get Paid Faster?
          </h2>
          <p className="text-xl text-blue-100 mb-8">
            Join thousands of businesses already using InvoicePro to streamline their billing
          </p>
          
          <div className="flex flex-col sm:flex-row gap-4 justify-center items-center max-w-md mx-auto">
            <input
              type="email"
              placeholder="Enter your email"
              value={email}
              onChange={(e) => setEmail(e.target.value)}
              className="w-full px-4 py-3 rounded-lg text-gray-900 border-0 focus:ring-2 focus:ring-blue-300"
            />
            <button 
              onClick={() => handleSignUp('pro')}
              className="w-full sm:w-auto bg-white text-blue-600 px-8 py-3 rounded-lg hover:bg-gray-100 transition-colors font-semibold whitespace-nowrap"
            >
              Start Free Trial
            </button>
          </div>

          <p className="text-blue-100 text-sm mt-4">
            14-day free trial • No credit card required
          </p>
        </div>
      </section>

      {/* Footer */}
      <footer className="bg-gray-900 text-white py-12">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="grid grid-cols-1 md:grid-cols-4 gap-8">
            <div>
              <div className="flex items-center gap-2 mb-4">
                <div className="bg-blue-600 p-2 rounded-lg">
                  <DollarSign className="w-6 h-6 text-white" />
                </div>
                <span className="text-xl font-bold">InvoicePro</span>
              </div>
              <p className="text-gray-400 mb-4">
                The modern invoicing solution for businesses of all sizes.
              </p>
              <div className="flex gap-4">
                <a href="#" className="text-gray-400 hover:text-white transition-colors">Privacy</a>
                <a href="#" className="text-gray-400 hover:text-white transition-colors">Terms</a>
              </div>
            </div>

            <div>
              <h3 className="font-semibold mb-4">Product</h3>
              <div className="space-y-2">
                <a href="#features" className="block text-gray-400 hover:text-white transition-colors">Features</a>
                <a href="#pricing" className="block text-gray-400 hover:text-white transition-colors">Pricing</a>
                <a href="#" className="block text-gray-400 hover:text-white transition-colors">API</a>
                <a href="#" className="block text-gray-400 hover:text-white transition-colors">Integrations</a>
              </div>
            </div>

            <div>
              <h3 className="font-semibold mb-4">Support</h3>
              <div className="space-y-2">
                <a href="#" className="block text-gray-400 hover:text-white transition-colors">Help Center</a>
                <a href="#" className="block text-gray-400 hover:text-white transition-colors">Contact Us</a>
                <a href="#" className="block text-gray-400 hover:text-white transition-colors">Status</a>
                <a href="#" className="block text-gray-400 hover:text-white transition-colors">Community</a>
              </div>
            </div>

            <div>
              <h3 className="font-semibold mb-4">Contact</h3>
              <div className="space-y-2 text-gray-400">
                <div className="flex items-center gap-2">
                  <Mail className="w-4 h-4" />
                  hello@invoicepro.com
                </div>
                <div className="flex items-center gap-2">
                  <Phone className="w-4 h-4" />
                  (555) 123-4567
                </div>
              </div>
            </div>
          </div>

          <div className="border-t border-gray-800 mt-12 pt-8 text-center text-gray-400">
            <p>&copy; 2025 InvoicePro. All rights reserved.</p>
          </div>
        </div>
      </footer>
    </div>
  );
};

export default LandingPage;
