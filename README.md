<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>بيت الشاي – طريق الشمال، الكعبان</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Amiri:wght@400;700&family=Cairo:wght@300;400;600;700;900&display=swap" rel="stylesheet" />
  <script src="https://cdn.tailwindcss.com"></script>
  <script>
    tailwind.config = {
      theme: {
        extend: {
          colors: {
            walnut:   '#4A2C0A',
            mahogany: '#6B3A1F',
            sienna:   '#8B5E3C',
            caramel:  '#C4874A',
            gold:     '#D4A843',
            cream:    '#F5ECD7',
            parchment:'#EFE0C2',
            sage:     '#4A6741',
            mossy:    '#3B5438',
          },
          fontFamily: {
            display: ['Amiri', 'serif'],
            body:    ['Cairo', 'sans-serif'],
          },
        },
      },
    };
  </script>
  <style>
    /* ─── Global ─── */
    *, *::before, *::after { box-sizing: border-box; }
    html { scroll-behavior: smooth; }
    body { font-family: 'Cairo', sans-serif; background: #F5ECD7; color: #4A2C0A; overflow-x: hidden; }

    /* ─── Noise texture overlay ─── */
    body::before {
      content: '';
      position: fixed; inset: 0; z-index: 0; pointer-events: none;
      background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.75' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
      opacity: 0.4;
    }

    /* ─── Hero ─── */
    .hero {
      min-height: 100svh;
      background:
        linear-gradient(160deg, rgba(74,44,10,.85) 0%, rgba(107,58,31,.6) 50%, rgba(196,135,74,.3) 100%),
        url('https://images.unsplash.com/photo-1556679343-c7306c1976bc?w=1400&q=80') center/cover no-repeat;
      position: relative; overflow: hidden;
    }
    .hero::after {
      content: '';
      position: absolute; bottom: 0; left: 0; right: 0; height: 120px;
      background: linear-gradient(to bottom, transparent, #F5ECD7);
    }

    /* ─── Steam animation ─── */
    @keyframes steam {
      0%   { transform: translateY(0)   scaleX(1) rotate(-3deg); opacity: .6; }
      50%  { transform: translateY(-30px) scaleX(1.15) rotate(3deg); opacity: .3; }
      100% { transform: translateY(-60px) scaleX(.9) rotate(-2deg); opacity: 0; }
    }
    .steam-line { animation: steam 2.8s ease-in-out infinite; }
    .steam-line:nth-child(2) { animation-delay: .9s; }
    .steam-line:nth-child(3) { animation-delay: 1.8s; }

    /* ─── Fade-up ─── */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(28px); }
      to   { opacity: 1; transform: translateY(0); }
    }
    .fade-up { opacity: 0; animation: fadeUp .8s ease forwards; }
    .delay-1 { animation-delay: .2s; }
    .delay-2 { animation-delay: .45s; }
    .delay-3 { animation-delay: .7s; }
    .delay-4 { animation-delay: .95s; }

    /* ─── Section heading rule ─── */
    .section-title {
      font-family: 'Amiri', serif;
      position: relative; display: inline-block;
    }
    .section-title::after {
      content: '';
      display: block; height: 3px; border-radius: 2px;
      background: linear-gradient(90deg, #D4A843, #8B5E3C, transparent);
      margin-top: 8px;
    }

    /* ─── Card ─── */
    .card {
      background: rgba(255,255,255,.55);
      backdrop-filter: blur(8px);
      border: 1px solid rgba(212,168,67,.3);
      border-radius: 20px;
      transition: transform .25s, box-shadow .25s;
    }
    .card:hover { transform: translateY(-5px); box-shadow: 0 16px 40px rgba(74,44,10,.15); }

    /* ─── Menu card ─── */
    .menu-card {
      background: linear-gradient(145deg, #fff9ee, #fdf3e0);
      border: 1px solid rgba(196,135,74,.35);
      border-radius: 18px;
      overflow: hidden;
      transition: transform .25s, box-shadow .25s;
    }
    .menu-card:hover { transform: translateY(-6px) scale(1.015); box-shadow: 0 18px 44px rgba(74,44,10,.18); }
    .menu-card img { transition: transform .4s; }
    .menu-card:hover img { transform: scale(1.06); }

    /* ─── Badge ─── */
    .badge-24 {
      background: linear-gradient(135deg, #D4A843, #C4874A);
      color: #fff;
      font-weight: 700; font-size: .75rem; letter-spacing: .08em;
      padding: 4px 14px; border-radius: 999px;
      box-shadow: 0 4px 14px rgba(212,168,67,.45);
    }

    /* ─── Divider ornament ─── */
    .ornament {
      display: flex; align-items: center; gap: 12px;
      color: #D4A843; font-size: 1.25rem;
    }
    .ornament::before, .ornament::after {
      content: ''; flex: 1; height: 1px;
      background: linear-gradient(90deg, transparent, #D4A843, transparent);
    }

    /* ─── Floating CTA ─── */
    .float-btn {
      position: fixed; bottom: 22px; left: 50%; transform: translateX(-50%);
      z-index: 999;
      display: flex; gap: 10px; align-items: center;
      animation: floatPop .6s 1.2s ease both;
    }
    @keyframes floatPop {
      from { opacity: 0; transform: translateX(-50%) translateY(20px); }
      to   { opacity: 1; transform: translateX(-50%) translateY(0); }
    }
    .float-btn a {
      display: flex; align-items: center; gap: 8px;
      padding: 13px 24px; border-radius: 999px;
      font-weight: 700; font-size: .9rem; white-space: nowrap;
      box-shadow: 0 8px 24px rgba(0,0,0,.25);
      transition: transform .2s, box-shadow .2s;
    }
    .float-btn a:hover { transform: translateY(-3px); box-shadow: 0 12px 32px rgba(0,0,0,.3); }
    .btn-call  { background: linear-gradient(135deg,#4A6741,#3B5438); color:#fff; }
    .btn-order { background: linear-gradient(135deg,#D4A843,#C4874A); color:#fff; }

    /* ─── Map iframe ─── */
    .map-frame { border-radius: 20px; overflow: hidden; box-shadow: 0 12px 36px rgba(74,44,10,.2); }

    /* ─── Scroll reveal ─── */
    .reveal { opacity: 0; transform: translateY(30px); transition: opacity .7s ease, transform .7s ease; }
    .reveal.visible { opacity: 1; transform: none; }
  </style>
</head>
<body class="relative">

<!-- ═══════════════════════════════════════
     NAVBAR
═══════════════════════════════════════ -->
<header class="fixed top-0 w-full z-50 bg-walnut/90 backdrop-blur-md border-b border-gold/20">
  <div class="max-w-5xl mx-auto px-4 py-3 flex items-center justify-between">
    <div class="flex items-center gap-3">
      <!-- Logo icon -->
      <svg width="36" height="36" viewBox="0 0 36 36" fill="none" xmlns="http://www.w3.org/2000/svg">
        <circle cx="18" cy="18" r="18" fill="#D4A843" opacity=".15"/>
        <text x="18" y="24" text-anchor="middle" font-size="18" fill="#D4A843">🍵</text>
      </svg>
      <span class="font-display text-cream text-xl font-bold">بيت الشاي</span>
    </div>
    <nav class="hidden md:flex gap-6 text-parchment text-sm font-semibold">
      <a href="#features" class="hover:text-gold transition-colors">مزايانا</a>
      <a href="#menu"     class="hover:text-gold transition-colors">القائمة</a>
      <a href="#location" class="hover:text-gold transition-colors">الموقع</a>
    </nav>
    <a href="tel:+97477289797" class="badge-24 hidden md:block">📞 اتصل الآن</a>
  </div>
</header>

<!-- ═══════════════════════════════════════
     HERO
═══════════════════════════════════════ -->
<section class="hero flex flex-col items-center justify-center text-center px-4 pt-20">

  <!-- Steam SVG -->
  <svg class="absolute top-32 left-1/2 -translate-x-1/2 opacity-60 w-32" viewBox="0 0 120 80" fill="none" xmlns="http://www.w3.org/2000/svg">
    <path class="steam-line" d="M30 70 Q35 50 25 30 Q15 10 20 0" stroke="#F5ECD7" stroke-width="3" stroke-linecap="round" fill="none"/>
    <path class="steam-line" d="M60 70 Q65 48 55 28 Q45 8 50 0"  stroke="#F5ECD7" stroke-width="3" stroke-linecap="round" fill="none"/>
    <path class="steam-line" d="M90 70 Q95 50 85 30 Q75 10 80 0" stroke="#F5ECD7" stroke-width="3" stroke-linecap="round" fill="none"/>
  </svg>

  <span class="badge-24 mb-6 fade-up delay-1">🕐 مفتوح 24 ساعة – 7 أيام</span>

  <h1 class="font-display text-cream text-5xl md:text-7xl font-bold leading-tight mb-4 fade-up delay-2"
      style="text-shadow:0 4px 24px rgba(0,0,0,.4)">
    بيت الشاي
  </h1>

  <p class="text-parchment text-lg md:text-2xl font-light mb-2 fade-up delay-3"
     style="text-shadow:0 2px 12px rgba(0,0,0,.5)">
    حيث كل لحظة تستحق كوباً دافئاً
  </p>
  <p class="text-caramel font-semibold mb-10 fade-up delay-3">
    طريق الشمال، مدينة الكعبان – قطر
  </p>

  <div class="flex flex-wrap justify-center gap-4 fade-up delay-4">
    <a href="#menu"
       class="px-8 py-3 rounded-full font-bold text-walnut transition-all hover:scale-105"
       style="background:linear-gradient(135deg,#D4A843,#C4874A); box-shadow:0 6px 20px rgba(212,168,67,.5)">
      🍽️ شاهد القائمة
    </a>
    <a href="https://www.talabat.com" target="_blank"
       class="px-8 py-3 rounded-full font-bold text-cream border-2 border-cream/60 hover:bg-cream/10 transition-all hover:scale-105">
      🛵 اطلب عبر طلبات
    </a>
  </div>

  <!-- Scroll cue -->
  <div class="absolute bottom-28 left-1/2 -translate-x-1/2 text-cream/60 animate-bounce text-2xl">↓</div>
</section>

<!-- ═══════════════════════════════════════
     FEATURES
═══════════════════════════════════════ -->
<section id="features" class="relative z-10 py-20 px-4">
  <div class="max-w-5xl mx-auto">
    <div class="ornament mb-3 reveal"><span>مزايانا</span></div>
    <h2 class="section-title text-walnut text-3xl md:text-4xl font-bold text-center w-full mb-12 reveal">
      لماذا تختار بيت الشاي؟
    </h2>

    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">

      <!-- Card 1 -->
      <div class="card p-8 text-center reveal">
        <div class="w-16 h-16 rounded-2xl flex items-center justify-center mx-auto mb-5 text-3xl"
             style="background:linear-gradient(135deg,#D4A843,#C4874A)">🚗</div>
        <h3 class="font-bold text-walnut text-xl mb-2">خدمة السيارات</h3>
        <p class="text-sienna text-sm leading-relaxed">
          لا تنزل من سيارتك! استقبل طلبك مباشرة على نافذة سيارتك بسرعة وراحة تامة.
        </p>
      </div>

      <!-- Card 2 -->
      <div class="card p-8 text-center reveal" style="transition-delay:.1s">
        <div class="w-16 h-16 rounded-2xl flex items-center justify-center mx-auto mb-5 text-3xl"
             style="background:linear-gradient(135deg,#4A6741,#3B5438)">🛵</div>
        <h3 class="font-bold text-walnut text-xl mb-2">توصيل عبر طلبات</h3>
        <p class="text-sienna text-sm leading-relaxed">
          اطلب من منزلك وسيصل إليك أينما كنت في الكعبان وما حولها عبر تطبيق طلبات.
        </p>
      </div>

      <!-- Card 3 -->
      <div class="card p-8 text-center reveal" style="transition-delay:.2s">
        <div class="w-16 h-16 rounded-2xl flex items-center justify-center mx-auto mb-5 text-3xl"
             style="background:linear-gradient(135deg,#D4A843,#8B5E3C)">🌙</div>
        <h3 class="font-bold text-walnut text-xl mb-2">مفتوح 24/7</h3>
        <p class="text-sienna text-sm leading-relaxed">
          سواء في الفجر أو منتصف الليل – بيت الشاي دائماً مستعد يستقبلك بكوب دافئ.
        </p>
      </div>

    </div>
  </div>
</section>

<!-- ═══════════════════════════════════════
     MENU
═══════════════════════════════════════ -->
<section id="menu" class="py-20 px-4" style="background:linear-gradient(180deg,#F5ECD7 0%,#EFE0C2 100%)">
  <div class="max-w-5xl mx-auto">
    <div class="ornament mb-3 reveal"><span>القائمة</span></div>
    <h2 class="section-title text-walnut text-3xl md:text-4xl font-bold text-center w-full mb-3 reveal">
      أشهى ما نقدّمه
    </h2>
    <p class="text-sienna text-center mb-12 reveal">أكلات بيتية بلمسة خليجية أصيلة</p>

    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-7">

      <!-- Item 1: Sandwiches -->
      <div class="menu-card reveal">
        <div class="overflow-hidden h-48">
          <img src="https://images.unsplash.com/photo-1553909489-cd47e0907980?w=600&q=80"
               alt="ساندوتشات" class="w-full h-full object-cover" />
        </div>
        <div class="p-5">
          <span class="text-xs font-bold text-sage uppercase tracking-wider">الأكثر طلباً</span>
          <h3 class="font-display text-walnut text-2xl font-bold mt-1 mb-2">ساندوتشات</h3>
          <p class="text-sienna text-sm leading-relaxed">
            ساندوتشات طازجة بمكونات مختارة – بيضة، جبن، تونا وأكثر. مقرمشة من الخارج، لذيذة من الداخل.
          </p>
          <div class="mt-4 flex items-center justify-between">
            <span class="text-caramel font-bold text-lg">متوفر الآن</span>
            <span class="badge-24 text-xs">🔥 HOT</span>
          </div>
        </div>
      </div>

      <!-- Item 2: Omelette Paratha -->
      <div class="menu-card reveal" style="transition-delay:.1s">
        <div class="overflow-hidden h-48">
          <img src="https://images.unsplash.com/photo-1565299585323-38d6b0865b47?w=600&q=80"
               alt="أومليت باراتا" class="w-full h-full object-cover" />
        </div>
        <div class="p-5">
          <span class="text-xs font-bold text-gold uppercase tracking-wider">الأكثر شعبية</span>
          <h3 class="font-display text-walnut text-2xl font-bold mt-1 mb-2">أومليت باراتا</h3>
          <p class="text-sienna text-sm leading-relaxed">
            خبز الباراتا الهش مع الأومليت الطري المتبّل – وجبة الفطور المثالية في أي وقت من اليوم.
          </p>
          <div class="mt-4 flex items-center justify-between">
            <span class="text-caramel font-bold text-lg">متوفر الآن</span>
            <span class="badge-24 text-xs">⭐ TOP</span>
          </div>
        </div>
      </div>

      <!-- Item 3: Fries -->
      <div class="menu-card reveal" style="transition-delay:.2s">
        <div class="overflow-hidden h-48">
          <img src="https://images.unsplash.com/photo-1630431341973-02e1b662ec35?w=600&q=80"
               alt="بطاطا مقلية" class="w-full h-full object-cover" />
        </div>
        <div class="p-5">
          <span class="text-xs font-bold text-mahogany uppercase tracking-wider">وجبة خفيفة</span>
          <h3 class="font-display text-walnut text-2xl font-bold mt-1 mb-2">بطاطا مقلية</h3>
          <p class="text-sienna text-sm leading-relaxed">
            بطاطا مقلية ذهبية مقرمشة مع صلصات متنوعة – الرفيق المثالي لكوب الشاي في أي وقت.
          </p>
          <div class="mt-4 flex items-center justify-between">
            <span class="text-caramel font-bold text-lg">متوفر الآن</span>
            <span class="badge-24 text-xs">🍟 CRISPY</span>
          </div>
        </div>
      </div>

    </div>

    <!-- View full menu CTA -->
    <div class="text-center mt-12 reveal">
      <p class="text-sienna mb-4">هل تريد معرفة كامل القائمة؟</p>
      <a href="https://www.talabat.com" target="_blank"
         class="inline-flex items-center gap-3 px-10 py-4 rounded-full font-bold text-walnut text-lg transition-all hover:scale-105"
         style="background:linear-gradient(135deg,#D4A843,#C4874A); box-shadow:0 8px 28px rgba(212,168,67,.4)">
        🍽️ عرض المنيو الكامل على طلبات
      </a>
    </div>
  </div>
</section>

<!-- ═══════════════════════════════════════
     TEA BANNER
═══════════════════════════════════════ -->
<div class="py-14 px-4 text-center" style="background:linear-gradient(135deg,#4A2C0A,#6B3A1F)">
  <p class="font-display text-cream text-3xl md:text-4xl mb-2">"كل كوب شاي حكاية"</p>
  <p class="text-caramel text-sm tracking-widest">BAIT AL SHAY · AL KAABAN · QATAR</p>
</div>

<!-- ═══════════════════════════════════════
     LOCATION
═══════════════════════════════════════ -->
<section id="location" class="py-20 px-4 bg-cream">
  <div class="max-w-5xl mx-auto">
    <div class="ornament mb-3 reveal"><span>الموقع</span></div>
    <h2 class="section-title text-walnut text-3xl md:text-4xl font-bold text-center w-full mb-12 reveal">
      تعال زُرنا
    </h2>

    <div class="grid grid-cols-1 lg:grid-cols-2 gap-10 items-center">

      <!-- Map -->
      <div class="map-frame reveal">
        <iframe
          src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d57919.5!2d51.15!3d25.45!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0x0!2zMjXCsDI3JzAwLjAiTiA1McKwMDknMDAuMCJF!5e0!3m2!1sar!2sqa!4v1717000000000!5m2!1sar!2sqa"
          width="100%" height="340" style="border:0;" allowfullscreen="" loading="lazy"
          referrerpolicy="no-referrer-when-downgrade" title="خريطة بيت الشاي">
        </iframe>
      </div>

      <!-- Info -->
      <div class="space-y-6 reveal" style="transition-delay:.1s">

        <div class="card p-6 flex items-start gap-4">
          <div class="w-12 h-12 rounded-xl flex items-center justify-center flex-shrink-0 text-2xl"
               style="background:linear-gradient(135deg,#D4A843,#C4874A)">📍</div>
          <div>
            <h4 class="font-bold text-walnut text-lg mb-1">العنوان</h4>
            <p class="text-sienna leading-relaxed">طريق الشمال، مدينة الكعبان<br/>قطر</p>
          </div>
        </div>

        <div class="card p-6 flex items-start gap-4">
          <div class="w-12 h-12 rounded-xl flex items-center justify-center flex-shrink-0 text-2xl"
               style="background:linear-gradient(135deg,#4A6741,#3B5438)">📞</div>
          <div>
            <h4 class="font-bold text-walnut text-lg mb-1">اتصل بنا</h4>
            <a href="tel:+97477289797" class="text-sage hover:text-mossy font-bold text-xl transition-colors dir-ltr">
              +974 7728 9797
            </a>
          </div>
        </div>

        <div class="card p-6 flex items-start gap-4">
          <div class="w-12 h-12 rounded-xl flex items-center justify-center flex-shrink-0 text-2xl"
               style="background:linear-gradient(135deg,#8B5E3C,#6B3A1F)">🕐</div>
          <div>
            <h4 class="font-bold text-walnut text-lg mb-1">ساعات العمل</h4>
            <p class="text-sienna">مفتوح <span class="font-bold text-gold">24 ساعة</span>، طوال أيام الأسبوع</p>
          </div>
        </div>

        <a href="https://maps.google.com/?q=Al+Kaaban+Qatar" target="_blank"
           class="block text-center py-4 rounded-2xl font-bold text-cream transition-all hover:scale-105"
           style="background:linear-gradient(135deg,#4A2C0A,#6B3A1F); box-shadow:0 8px 24px rgba(74,44,10,.3)">
          🗺️ افتح في خرائط Google
        </a>
      </div>

    </div>
  </div>
</section>

<!-- ═══════════════════════════════════════
     FOOTER
═══════════════════════════════════════ -->
<footer class="py-8 px-4 text-center" style="background:#4A2C0A">
  <p class="font-display text-gold text-2xl mb-1">بيت الشاي</p>
  <p class="text-parchment/60 text-xs">© 2025 · طريق الشمال، مدينة الكعبان، قطر · +974 7728 9797</p>
</footer>

<!-- ═══════════════════════════════════════
     FLOATING CTA (mobile-friendly)
═══════════════════════════════════════ -->
<div class="float-btn">
  <a href="tel:+97477289797" class="btn-call shadow-lg">
    📞 اتصل
  </a>
  <a href="https://www.talabat.com" target="_blank" class="btn-order shadow-lg">
    🛵 اطلب الآن
  </a>
</div>

<!-- ═══════════════════════════════════════
     JS: scroll reveal
═══════════════════════════════════════ -->
<script>
  const obs = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) { e.target.classList.add('visible'); obs.unobserve(e.target); }
    });
  }, { threshold: 0.12 });
  document.querySelectorAll('.reveal').forEach(el => obs.observe(el));
</script>

</body>
</html>
