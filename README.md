# varidaham.github.io
<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Timmy | Game QA Tester & Moderator</title>

  <!-- Google Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&family=Fira+Code:wght@400;500&display=swap" rel="stylesheet" />

  <!-- Tailwind CSS CDN -->
  <script src="https://cdn.tailwindcss.com"></script>
  <!-- Lucide Icons -->
  <script src="https://unpkg.com/lucide@latest"></script>

  <script>
    tailwind.config = {
      theme: {
        extend: {
          fontFamily: {
            sans: ['"Plus Jakarta Sans"', 'sans-serif'],
            mono: ['"Fira Code"', 'monospace'],
          },
          colors: {
            charcoal: {
              800: '#1e1e24',
              900: '#131316',
              950: '#0c0c0e',
            }
          }
        }
      }
    }
  </script>

  <style>
    .glow-card {
      background: rgba(26, 26, 32, 0.7);
      backdrop-filter: blur(12px);
      border: 1px solid rgba(255, 255, 255, 0.08);
      transition: all 0.3s ease;
    }
    .glow-card:hover {
      border-color: rgba(6, 182, 212, 0.4);
      box-shadow: 0 0 25px rgba(6, 182, 212, 0.15);
    }
    .text-glow {
      text-shadow: 0 0 20px rgba(168, 85, 247, 0.35);
    }
  </style>
</head>

<body class="bg-charcoal-950 text-gray-200 font-sans selection:bg-cyan-500/20 selection:text-cyan-300 min-h-screen">

  <!-- ==================== HEADER ==================== -->
  <header class="sticky top-0 z-50 backdrop-blur-xl bg-charcoal-950/70 border-b border-white/[0.06]">
    <div class="max-w-7xl mx-auto px-6 h-20 flex items-center justify-between">
      <a href="#" class="text-xl font-bold tracking-tight text-white flex items-center gap-2 group">
        <span class="w-8 h-8 rounded-lg bg-gradient-to-tr from-purple-600 to-cyan-400 flex items-center justify-center text-white font-black text-sm shadow-lg shadow-purple-500/30 group-hover:scale-105 transition-transform">QA</span>
        <span>Timmy<span class="text-cyan-400">Portfolio</span></span>
      </a>

      <!-- Desktop Nav -->
      <nav class="hidden md:flex items-center gap-8 text-sm font-medium text-gray-300">
        <a href="#about" class="hover:text-cyan-400 transition-colors">About</a>
        <a href="#qa-moderation" class="hover:text-cyan-400 transition-colors">QA &amp; Moderation</a>
        <a href="#skills" class="hover:text-cyan-400 transition-colors">Skills</a>
        <a href="#contact" class="hover:text-cyan-400 transition-colors">Contact</a>
      </nav>

      <!-- CTA Button -->
      <div class="hidden md:flex items-center">
        <a href="#contact" class="px-5 py-2.5 rounded-xl text-sm font-semibold bg-white/5 border border-white/10 hover:border-cyan-400/50 hover:bg-cyan-500/10 text-white transition-all">
          Connect With Me
        </a>
      </div>

      <!-- Mobile Menu Button -->
      <button id="mobileMenuBtn" aria-label="Toggle Navigation" class="md:hidden text-gray-400 hover:text-white p-2">
        <i data-lucide="menu" class="w-6 h-6"></i>
      </button>
    </div>

    <!-- Mobile Nav Dropdown -->
    <div id="mobileMenu" class="hidden md:hidden px-6 py-4 bg-charcoal-900 border-b border-white/[0.06] space-y-3 text-sm">
      <a href="#about" class="mobile-link block text-gray-300 hover:text-cyan-400 font-medium">About</a>
      <a href="#qa-moderation" class="mobile-link block text-gray-300 hover:text-cyan-400 font-medium">QA &amp; Moderation</a>
      <a href="#skills" class="mobile-link block text-gray-300 hover:text-cyan-400 font-medium">Skills</a>
      <a href="#contact" class="mobile-link block text-gray-300 hover:text-cyan-400 font-medium">Contact</a>
    </div>
  </header>

  <main class="max-w-7xl mx-auto px-6 py-16 space-y-32">

    <!-- ==================== HERO SECTION ==================== -->
    <section class="pt-12 sm:pt-20 flex flex-col items-start">
      <div class="inline-flex items-center gap-2 px-3 py-1 rounded-full bg-cyan-500/10 border border-cyan-500/20 text-cyan-400 text-xs font-semibold mb-6">
        <span class="w-2 h-2 rounded-full bg-cyan-400 animate-pulse"></span>
        Available for QA &amp; Moderation Roles
      </div>

      <h1 class="text-4xl sm:text-6xl lg:text-7xl font-extrabold tracking-tight text-white max-w-4xl leading-[1.1]">
        Elevating gameplay quality &amp; <span class="bg-gradient-to-r from-purple-400 via-indigo-400 to-cyan-400 bg-clip-text text-transparent text-glow">testing games to perfection.</span>
      </h1>

      <p class="mt-6 text-lg sm:text-xl text-gray-400 max-w-2xl leading-relaxed">
        Hi, I'm <strong class="text-white font-semibold">Timmy</strong>. I am an active game QA tester and community moderator dedicated to bug-free gameplay and healthy gaming communities.
      </p>

      <div class="mt-10 flex flex-wrap gap-4 items-center">
        <a href="#qa-moderation" class="px-7 py-3.5 rounded-xl font-semibold bg-gradient-to-r from-purple-600 to-cyan-500 text-white shadow-lg shadow-purple-600/30 hover:scale-[1.02] active:scale-95 transition-all flex items-center gap-2">
          <span>Game QA Experience</span>
          <i data-lucide="gamepad-2" class="w-4 h-4"></i>
        </a>
        <a href="#contact" class="px-7 py-3.5 rounded-xl font-semibold glow-card text-white hover:text-cyan-400 hover:scale-[1.02] active:scale-95 transition-all flex items-center gap-2">
          <span>Get in Touch</span>
          <i data-lucide="arrow-right" class="w-4 h-4"></i>
        </a>
      </div>
    </section>

    <!-- ==================== ABOUT SECTION ==================== -->
    <section id="about" class="scroll-mt-24 grid md:grid-cols-2 gap-12 items-center">
      <div class="space-y-6">
        <div class="text-cyan-400 text-xs font-bold uppercase tracking-widest">About Me</div>
        <h2 class="text-3xl sm:text-4xl font-bold text-white tracking-tight">Detail-focused tester with deep gaming intuition.</h2>
        <p class="text-gray-400 leading-relaxed">
          I bridge the gap between players and development teams by identifying edge-case bugs, stress-testing mechanics, verifying game balances, and enforcing friendly community guidelines.
        </p>
        <div class="grid grid-cols-2 gap-4 pt-2">
          <div class="glow-card p-4 rounded-xl">
            <div class="text-2xl font-bold text-cyan-400 font-mono">100%</div>
            <div class="text-xs text-gray-400 uppercase mt-1">Dedication to Quality</div>
          </div>
          <div class="glow-card p-4 rounded-xl">
            <div class="text-2xl font-bold text-purple-400 font-mono">24/7</div>
            <div class="text-xs text-gray-400 uppercase mt-1">Active Community Support</div>
          </div>
        </div>
      </div>

      <div class="glow-card p-6 sm:p-8 rounded-2xl relative overflow-hidden font-mono text-sm leading-relaxed border border-white/10 bg-charcoal-900/90 shadow-2xl">
        <div class="flex items-center gap-2 pb-4 mb-4 border-b border-white/5 text-gray-500 text-xs">
          <span class="w-3 h-3 rounded-full bg-red-500/80 inline-block"></span>
          <span class="w-3 h-3 rounded-full bg-yellow-500/80 inline-block"></span>
          <span class="w-3 h-3 rounded-full bg-emerald-500/80 inline-block"></span>
          <span class="ml-2 text-gray-400">timmy_profile.json</span>
        </div>
        <div class="space-y-1">
          <p class="text-purple-400"><span class="text-cyan-400">const</span> profile = {</p>
          <p class="pl-4 text-gray-300">name: <span class="text-emerald-400">"Timmy"</span>,</p>
          <p class="pl-4 text-gray-300">specialization: [<span class="text-emerald-400">"Game QA"</span>, <span class="text-emerald-400">"Moderation"</span>],</p>
          <p class="pl-4 text-gray-300">platforms: [<span class="text-emerald-400">"Roblox"</span>, <span class="text-emerald-400">"Discord"</span>],</p>
          <p class="pl-4 text-gray-300">focus: <span class="text-emerald-400">"Delivering zero-bug experiences"</span></p>
          <p class="text-purple-400">};</p>
        </div>
      </div>
    </section>

    <!-- ==================== QA & MODERATION ==================== -->
    <section id="qa-moderation" class="scroll-mt-24 space-y-10">
      <div>
        <div class="text-cyan-400 text-xs font-bold uppercase tracking-widest">Expertise</div>
        <h2 class="text-3xl sm:text-4xl font-bold text-white tracking-tight mt-1">QA &amp; Moderation Services</h2>
      </div>

      <div class="grid md:grid-cols-2 gap-6">
        <!-- QA Card -->
        <div class="glow-card p-8 rounded-2xl space-y-4">
          <div class="w-12 h-12 rounded-xl bg-purple-500/10 border border-purple-500/20 flex items-center justify-center text-purple-400">
            <i data-lucide="bug" class="w-6 h-6"></i>
          </div>
          <h3 class="text-xl font-bold text-white">Quality Assurance &amp; Bug Hunting</h3>
          <p class="text-gray-400 text-sm leading-relaxed">
            Detailed repro steps, collision &amp; physics boundary testing, stress-testing multiplayer load, and regression testing after critical patches.
          </p>
          <ul class="text-sm text-gray-300 space-y-2 pt-2">
            <li class="flex items-center gap-2"><i data-lucide="check" class="w-4 h-4 text-cyan-400"></i> Clear reproduction steps with video/logs</li>
            <li class="flex items-center gap-2"><i data-lucide="check" class="w-4 h-4 text-cyan-400"></i> Game mechanic exploits &amp; economy sanity checks</li>
            <li class="flex items-center gap-2"><i data-lucide="check" class="w-4 h-4 text-cyan-400"></i> Multi-device testing across different specs</li>
          </ul>
        </div>

        <!-- Moderation Card -->
        <div class="glow-card p-8 rounded-2xl space-y-4">
          <div class="w-12 h-12 rounded-xl bg-cyan-500/10 border border-cyan-500/20 flex items-center justify-center text-cyan-400">
            <i data-lucide="shield-check" class="w-6 h-6"></i>
          </div>
          <h3 class="text-xl font-bold text-white">Community &amp; Server Moderation</h3>
          <p class="text-gray-400 text-sm leading-relaxed">
            Protecting servers and communities with fair rule enforcement, ticket resolution, raid prevention, and player engagement.
          </p>
          <ul class="text-sm text-gray-300 space-y-2 pt-2">
            <li class="flex items-center gap-2"><i data-lucide="check" class="w-4 h-4 text-cyan-400"></i> Discord &amp; in-game moderation workflows</li>
            <li class="flex items-center gap-2"><i data-lucide="check" class="w-4 h-4 text-cyan-400"></i> Conflict de-escalation &amp; strict anti-toxicity</li>
            <li class="flex items-center gap-2"><i data-lucide="check" class="w-4 h-4 text-cyan-400"></i> Community event organization &amp; feedback collection</li>
          </ul>
        </div>
      </div>
    </section>

    <!-- ==================== SKILLS ==================== -->
    <section id="skills" class="scroll-mt-24 space-y-8">
      <div>
        <div class="text-cyan-400 text-xs font-bold uppercase tracking-widest">Toolbox</div>
        <h2 class="text-3xl sm:text-4xl font-bold text-white tracking-tight mt-1">Core Competencies</h2>
      </div>

      <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 gap-4">
        <div class="glow-card p-5 rounded-xl flex items-center gap-3">
          <i data-lucide="check-circle" class="w-5 h-5 text-purple-400"></i>
          <span class="font-medium text-sm text-white">Bug Reporting</span>
        </div>
        <div class="glow-card p-5 rounded-xl flex items-center gap-3">
          <i data-lucide="gamepad" class="w-5 h-5 text-cyan-400"></i>
          <span class="font-medium text-sm text-white">Roblox Testing</span>
        </div>
        <div class="glow-card p-5 rounded-xl flex items-center gap-3">
          <i data-lucide="message-square" class="w-5 h-5 text-purple-400"></i>
          <span class="font-medium text-sm text-white">Discord Moderation</span>
        </div>
        <div class="glow-card p-5 rounded-xl flex items-center gap-3">
          <i data-lucide="clipboard-list" class="w-5 h-5 text-cyan-400"></i>
          <span class="font-medium text-sm text-white">Test Case Execution</span>
        </div>
        <div class="glow-card p-5 rounded-xl flex items-center gap-3">
          <i data-lucide="shield" class="w-5 h-5 text-purple-400"></i>
          <span class="font-medium text-sm text-white">Rule Enforcement</span>
        </div>
        <div class="glow-card p-5 rounded-xl flex items-center gap-3">
          <i data-lucide="cpu" class="w-5 h-5 text-cyan-400"></i>
          <span class="font-medium text-sm text-white">Stress &amp; Load Tests</span>
        </div>
        <div class="glow-card p-5 rounded-xl flex items-center gap-3">
          <i data-lucide="users" class="w-5 h-5 text-purple-400"></i>
          <span class="font-medium text-sm text-white">Community Relations</span>
        </div>
        <div class="glow-card p-5 rounded-xl flex items-center gap-3">
          <i data-lucide="video" class="w-5 h-5 text-cyan-400"></i>
          <span class="font-medium text-sm text-white">Video Reproduction</span>
        </div>
      </div>
    </section>

    <!-- ==================== CONTACT ==================== -->
    <section id="contact" class="scroll-mt-24">
      <div class="glow-card rounded-3xl p-8 sm:p-12 border border-purple-500/20 bg-charcoal-900/80 max-w-3xl mx-auto text-center space-y-6">
        <div>
          <span class="text-cyan-400 text-xs font-bold uppercase tracking-widest">Get In Touch</span>
          <h2 class="text-3xl sm:text-4xl font-bold text-white tracking-tight mt-2">Let's work together.</h2>
        </div>

        <p class="text-gray-400 text-sm sm:text-base leading-relaxed max-w-xl mx-auto">
          Whether you need an active QA tester for your game, or a trustworthy moderator for your community, feel free to reach out via email or connect with me on socials!
        </p>

        <!-- Social & Email Links -->
        <div class="pt-4 flex flex-col sm:flex-row items-center justify-center gap-4 flex-wrap">
          <!-- Direct Email Button -->
          <a href="mailto:varidaham44@gmail.com" class="w-full sm:w-auto px-6 py-3.5 rounded-xl font-semibold bg-gradient-to-r from-purple-600 to-cyan-500 text-white shadow-lg shadow-purple-600/30 hover:scale-[1.02] active:scale-95 transition-all flex items-center justify-center gap-2">
            <i data-lucide="mail" class="w-4 h-4"></i>
            <span>varidaham44@gmail.com</span>
          </a>

          <!-- Discord Link -->
          <a href="#" target="_blank" rel="noopener noreferrer" class="w-full sm:w-auto px-6 py-3.5 rounded-xl font-semibold glow-card text-white hover:text-cyan-400 hover:scale-[1.02] active:scale-95 transition-all flex items-center justify-center gap-2 border border-white/10">
            <i data-lucide="message-square" class="w-4 h-4"></i>
            <span>Discord</span>
          </a>

          <!-- Roblox / Social Link -->
          <a href="#" target="_blank" rel="noopener noreferrer" class="w-full sm:w-auto px-6 py-3.5 rounded-xl font-semibold glow-card text-white hover:text-cyan-400 hover:scale-[1.02] active:scale-95 transition-all flex items-center justify-center gap-2 border border-white/10">
            <i data-lucide="gamepad-2" class="w-4 h-4"></i>
            <span>Roblox Profile</span>
          </a>
        </div>
      </div>
    </section>

  </main>

  <!-- ==================== FOOTER ==================== -->
  <footer class="border-t border-white/[0.06] py-10 bg-charcoal-950/80 text-sm text-gray-500">
    <div class="max-w-7xl mx-auto px-6 flex flex-col sm:flex-row items-center justify-between gap-4">
      <div>
        &copy; <span id="currentYear"></span> Timmy. All rights reserved.
      </div>
      <div class="flex items-center gap-6">
        <a href="#about" class="hover:text-cyan-400 transition-colors">About</a>
        <a href="#qa-moderation" class="hover:text-cyan-400 transition-colors">QA Experience</a>
        <a href="#skills" class="hover:text-cyan-400 transition-colors">Skills</a>
        <a href="#contact" class="hover:text-cyan-400 transition-colors">Contact</a>
      </div>
    </div>
  </footer>

  <!-- Scripts -->
  <script>
    // Initialize Lucide icons
    lucide.createIcons();

    // Dynamically set copyright year
    document.getElementById('currentYear').textContent = new Date().getFullYear();

    // Mobile menu toggle
    const mobileMenuBtn = document.getElementById('mobileMenuBtn');
    const mobileMenu = document.getElementById('mobileMenu');
    const mobileLinks = document.querySelectorAll('.mobile-link');

    mobileMenuBtn.addEventListener('click', () => {
      mobileMenu.classList.toggle('hidden');
    });

    mobileLinks.forEach(link => {
      link.addEventListener('click', () => {
        mobileMenu.classList.add('hidden');
      });
    });
  </script>
</body>
</html>
