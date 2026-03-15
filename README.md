# PipHouse
<!DOCTYPE html>

<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>PipHouse | Where Selling Your Property is a Hassle-Free Experience</title>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700;900&family=DM+Sans:wght@300;400;500;600;700&display=swap" rel="stylesheet" />
  <style>
    /* =============================================
       CSS VARIABLES — Edit colors, fonts, sizes here
       ============================================= */
    :root {
      --color-bg:         #0B1A2C;       /* Dark navy background */
      --color-bg-section: #0d2035;       /* Slightly lighter section bg */
      --color-primary:    #E8C97A;       /* Gold accent */
      --color-primary-dark: #c9a84c;    /* Darker gold */
      --color-white:      #FFFFFF;
      --color-text:       #c8d8e8;       /* Body text color */
      --color-text-muted: #7a9ab8;       /* Muted text */
      --color-card:       #122338;       /* Card background */
      --color-card-border:#1e3a55;       /* Card border */
      --color-red:        #e05c5c;       /* Red accent */
      --font-display:     'Playfair Display', Georgia, serif;
      --font-body:        'DM Sans', sans-serif;
      --radius:           12px;
      --radius-lg:        20px;
      --nav-height:       80px;
      --max-width:        1240px;
      --transition:       0.3s ease;
    }

```
/* =============================================
   RESET & BASE
   ============================================= */
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
html { scroll-behavior: smooth; }
body {
  font-family: var(--font-body);
  background: var(--color-bg);
  color: var(--color-text);
  line-height: 1.6;
  overflow-x: hidden;
}
a { text-decoration: none; color: inherit; }
img { max-width: 100%; display: block; }
ul { list-style: none; }

/* =============================================
   UTILITY
   ============================================= */
.container { max-width: var(--max-width); margin: 0 auto; padding: 0 24px; }
.section-label {
  font-family: var(--font-body);
  font-size: 12px;
  font-weight: 700;
  letter-spacing: 3px;
  text-transform: uppercase;
  color: var(--color-primary);
  margin-bottom: 12px;
}
.section-title {
  font-family: var(--font-display);
  font-size: clamp(28px, 4vw, 44px);
  font-weight: 700;
  color: var(--color-white);
  line-height: 1.2;
  margin-bottom: 16px;
}
.section-sub {
  font-size: 16px;
  color: var(--color-text-muted);
  max-width: 620px;
  line-height: 1.7;
}
.btn {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 14px 28px;
  border-radius: 50px;
  font-family: var(--font-body);
  font-weight: 600;
  font-size: 14px;
  letter-spacing: 0.5px;
  transition: var(--transition);
  cursor: pointer;
  border: none;
}
.btn-primary {
  background: var(--color-primary);
  color: #0B1A2C;
}
.btn-primary:hover { background: var(--color-primary-dark); transform: translateY(-2px); }
.btn-outline {
  background: transparent;
  color: var(--color-white);
  border: 2px solid rgba(255,255,255,0.3);
}
.btn-outline:hover { border-color: var(--color-primary); color: var(--color-primary); }

/* Stars */
.stars { display: flex; gap: 3px; }
.stars span { color: var(--color-primary); font-size: 14px; }

/* =============================================
   NAVIGATION
   ============================================= */
nav {
  position: fixed;
  top: 0; left: 0; right: 0;
  height: var(--nav-height);
  z-index: 1000;
  background: rgba(11, 26, 44, 0.95);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid rgba(232, 201, 122, 0.1);
  transition: var(--transition);
}
.nav-inner {
  max-width: var(--max-width);
  margin: 0 auto;
  padding: 0 24px;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.nav-logo {
  display: flex;
  align-items: center;
  gap: 10px;
  font-family: var(--font-display);
  font-size: 22px;
  font-weight: 700;
  color: var(--color-white);
}
.nav-logo .logo-icon {
  width: 38px; height: 38px;
  background: var(--color-primary);
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 20px;
}
.nav-logo .logo-pip { color: var(--color-primary); }
.nav-links {
  display: flex;
  align-items: center;
  gap: 32px;
}
.nav-links a {
  font-size: 13px;
  font-weight: 600;
  letter-spacing: 1px;
  text-transform: uppercase;
  color: var(--color-text);
  transition: var(--transition);
  position: relative;
}
.nav-links a::after {
  content: '';
  position: absolute;
  bottom: -4px; left: 0; right: 0;
  height: 2px;
  background: var(--color-primary);
  transform: scaleX(0);
  transition: var(--transition);
}
.nav-links a:hover { color: var(--color-primary); }
.nav-links a:hover::after { transform: scaleX(1); }
.nav-cta { margin-left: 16px; }
.hamburger { display: none; flex-direction: column; gap: 5px; cursor: pointer; padding: 4px; }
.hamburger span { display: block; width: 24px; height: 2px; background: var(--color-white); border-radius: 2px; transition: var(--transition); }

/* Mobile nav */
.mobile-nav {
  display: none;
  position: fixed;
  top: var(--nav-height); left: 0; right: 0;
  background: rgba(11, 26, 44, 0.98);
  backdrop-filter: blur(12px);
  padding: 24px;
  z-index: 999;
  border-bottom: 1px solid rgba(232,201,122,0.1);
  flex-direction: column;
  gap: 16px;
}
.mobile-nav a {
  font-size: 15px;
  font-weight: 600;
  letter-spacing: 1px;
  text-transform: uppercase;
  color: var(--color-text);
  padding: 10px 0;
  border-bottom: 1px solid rgba(255,255,255,0.05);
}
.mobile-nav.open { display: flex; }

/* =============================================
   HERO
   ============================================= */
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  position: relative;
  overflow: hidden;
  padding-top: var(--nav-height);
  background: linear-gradient(135deg, #060f1a 0%, #0d2035 40%, #0b1a2c 100%);
}
.hero-bg-glow {
  position: absolute;
  top: -20%; left: -10%;
  width: 60vw; height: 60vw;
  background: radial-gradient(ellipse, rgba(232,201,122,0.06) 0%, transparent 70%);
  pointer-events: none;
}
.hero-bg-glow2 {
  position: absolute;
  bottom: -10%; right: -5%;
  width: 50vw; height: 50vw;
  background: radial-gradient(ellipse, rgba(30,80,140,0.15) 0%, transparent 70%);
  pointer-events: none;
}
/* Animated stars */
.hero-stars {
  position: absolute;
  inset: 0;
  pointer-events: none;
  overflow: hidden;
}
.star {
  position: absolute;
  background: var(--color-primary);
  border-radius: 50%;
  animation: twinkle 3s infinite alternate;
}
@keyframes twinkle {
  0% { opacity: 0.2; transform: scale(1); }
  100% { opacity: 0.9; transform: scale(1.4); }
}
/* Snowflakes */
.snowflake {
  position: absolute;
  color: rgba(255,255,255,0.6);
  font-size: 16px;
  animation: fall linear infinite;
  pointer-events: none;
}
@keyframes fall {
  0% { transform: translateY(-20px) rotate(0deg); opacity: 1; }
  100% { transform: translateY(110vh) rotate(720deg); opacity: 0; }
}

.hero-inner {
  position: relative;
  z-index: 2;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 60px;
  align-items: center;
  padding: 80px 24px;
  max-width: var(--max-width);
  margin: 0 auto;
  width: 100%;
}
.hero-badge {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background: rgba(232,201,122,0.1);
  border: 1px solid rgba(232,201,122,0.25);
  border-radius: 50px;
  padding: 8px 16px;
  font-size: 12px;
  font-weight: 600;
  letter-spacing: 1.5px;
  text-transform: uppercase;
  color: var(--color-primary);
  margin-bottom: 24px;
}
.hero-title {
  font-family: var(--font-display);
  font-size: clamp(36px, 5vw, 62px);
  font-weight: 900;
  color: var(--color-white);
  line-height: 1.1;
  margin-bottom: 20px;
}
.hero-title em {
  font-style: normal;
  color: var(--color-primary);
}
.hero-desc {
  font-size: 17px;
  color: var(--color-text-muted);
  line-height: 1.75;
  margin-bottom: 36px;
  max-width: 480px;
}
.hero-actions { display: flex; gap: 14px; flex-wrap: wrap; margin-bottom: 48px; }
.hero-social-proof {
  display: flex;
  align-items: center;
  gap: 16px;
}
.hero-avatars { display: flex; }
.hero-avatars span {
  width: 36px; height: 36px;
  border-radius: 50%;
  border: 2px solid var(--color-bg);
  background: var(--color-primary);
  margin-left: -8px;
  display: flex; align-items: center; justify-content: center;
  font-size: 12px;
  font-weight: 700;
  color: #0B1A2C;
}
.hero-avatars span:first-child { margin-left: 0; }
.hero-social-text { font-size: 13px; color: var(--color-text-muted); }
.hero-social-text strong { color: var(--color-white); display: block; }

/* Hero right — house illustration */
.hero-visual {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
}
.hero-house-card {
  background: var(--color-card);
  border: 1px solid var(--color-card-border);
  border-radius: var(--radius-lg);
  overflow: hidden;
  width: 100%;
  max-width: 460px;
  box-shadow: 0 40px 80px rgba(0,0,0,0.4);
  animation: float 4s ease-in-out infinite;
}
@keyframes float {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-12px); }
}
.hero-house-img {
  width: 100%; height: 260px;
  background: linear-gradient(160deg, #1a3a5c 0%, #0d2035 100%);
  position: relative;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 80px;
}
.hero-house-info { padding: 20px 24px; }
.hero-house-info h3 {
  font-family: var(--font-display);
  font-size: 20px;
  color: var(--color-white);
  margin-bottom: 4px;
}
.hero-house-info p { font-size: 13px; color: var(--color-text-muted); margin-bottom: 12px; }
.hero-house-meta { display: flex; gap: 16px; }
.hero-house-meta span {
  font-size: 12px;
  color: var(--color-text-muted);
  display: flex;
  align-items: center;
  gap: 4px;
}
.badge-price {
  position: absolute;
  top: 20px; right: 20px;
  background: var(--color-primary);
  color: #0B1A2C;
  font-weight: 700;
  font-size: 14px;
  padding: 6px 14px;
  border-radius: 50px;
}
.badge-verified {
  position: absolute;
  bottom: 20px; left: 20px;
  background: rgba(11,26,44,0.85);
  backdrop-filter: blur(8px);
  border: 1px solid rgba(232,201,122,0.2);
  border-radius: 50px;
  padding: 8px 14px;
  display: flex;
  align-items: center;
  gap: 8px;
  font-size: 12px;
  color: var(--color-text);
}
.badge-verified .dot { width: 8px; height: 8px; background: #4ade80; border-radius: 50%; animation: pulse 2s infinite; }
@keyframes pulse { 0%, 100% { opacity: 1; } 50% { opacity: 0.4; } }

/* =============================================
   STATS BAR
   ============================================= */
.stats-bar {
  background: var(--color-card);
  border-top: 1px solid var(--color-card-border);
  border-bottom: 1px solid var(--color-card-border);
  padding: 40px 24px;
}
.stats-inner {
  max-width: var(--max-width);
  margin: 0 auto;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 24px;
  text-align: center;
}
.stat-item { padding: 20px; }
.stat-item .stat-num {
  font-family: var(--font-display);
  font-size: clamp(32px, 4vw, 48px);
  font-weight: 900;
  color: var(--color-primary);
  line-height: 1;
  margin-bottom: 8px;
}
.stat-item .stat-label {
  font-size: 14px;
  color: var(--color-text-muted);
  font-weight: 500;
}
.stat-divider {
  width: 1px;
  background: var(--color-card-border);
  align-self: stretch;
}

/* =============================================
   TRUST LOGOS MARQUEE
   ============================================= */
.trusted-section { padding: 40px 0; overflow: hidden; }
.trusted-label {
  text-align: center;
  font-size: 12px;
  letter-spacing: 3px;
  text-transform: uppercase;
  color: var(--color-text-muted);
  margin-bottom: 28px;
}
.marquee-wrapper { overflow: hidden; position: relative; }
.marquee-wrapper::before,
.marquee-wrapper::after {
  content: '';
  position: absolute;
  top: 0; bottom: 0;
  width: 120px;
  z-index: 2;
}
.marquee-wrapper::before { left: 0; background: linear-gradient(to right, var(--color-bg), transparent); }
.marquee-wrapper::after { right: 0; background: linear-gradient(to left, var(--color-bg), transparent); }
.marquee-track {
  display: flex;
  align-items: center;
  gap: 60px;
  width: max-content;
  animation: marquee 20s linear infinite;
}
.marquee-track:hover { animation-play-state: paused; }
@keyframes marquee {
  0% { transform: translateX(0); }
  100% { transform: translateX(-50%); }
}
.logo-pill {
  background: var(--color-card);
  border: 1px solid var(--color-card-border);
  border-radius: 50px;
  padding: 12px 28px;
  font-weight: 700;
  font-size: 14px;
  color: var(--color-text-muted);
  white-space: nowrap;
  transition: var(--transition);
}
.logo-pill:hover { border-color: var(--color-primary); color: var(--color-primary); }

/* =============================================
   PROCESS
   ============================================= */
.process-section { padding: 100px 24px; }
.process-inner { max-width: var(--max-width); margin: 0 auto; }
.process-header { text-align: center; margin-bottom: 72px; }
.process-header .section-sub { margin: 0 auto; }
.process-steps {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 32px;
  position: relative;
}
.process-steps::before {
  content: '';
  position: absolute;
  top: 48px; left: 16.67%; right: 16.67%;
  height: 2px;
  background: linear-gradient(to right, var(--color-primary), transparent, var(--color-primary));
  opacity: 0.3;
}
.process-step {
  background: var(--color-card);
  border: 1px solid var(--color-card-border);
  border-radius: var(--radius-lg);
  padding: 40px 32px;
  text-align: center;
  position: relative;
  transition: var(--transition);
}
.process-step:hover {
  border-color: var(--color-primary);
  transform: translateY(-6px);
  box-shadow: 0 20px 40px rgba(232,201,122,0.08);
}
.step-num {
  font-family: var(--font-display);
  font-size: 64px;
  font-weight: 900;
  color: rgba(232,201,122,0.12);
  line-height: 1;
  margin-bottom: 20px;
}
.step-icon {
  width: 64px; height: 64px;
  background: rgba(232,201,122,0.1);
  border: 1px solid rgba(232,201,122,0.25);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 28px;
  margin: 0 auto 20px;
}
.process-step h3 {
  font-family: var(--font-display);
  font-size: 20px;
  color: var(--color-white);
  margin-bottom: 12px;
}
.process-step p { font-size: 14px; color: var(--color-text-muted); line-height: 1.7; }

/* =============================================
   SERVICES
   ============================================= */
.services-section {
  padding: 100px 24px;
  background: var(--color-bg-section);
}
.services-inner { max-width: var(--max-width); margin: 0 auto; }
.services-header { text-align: center; margin-bottom: 64px; }
.services-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 24px;
}
.service-card {
  background: var(--color-card);
  border: 1px solid var(--color-card-border);
  border-radius: var(--radius-lg);
  padding: 36px 32px;
  position: relative;
  overflow: hidden;
  transition: var(--transition);
}
.service-card::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 3px;
  background: linear-gradient(to right, var(--color-primary), transparent);
  transform: scaleX(0);
  transform-origin: left;
  transition: var(--transition);
}
.service-card:hover {
  border-color: rgba(232,201,122,0.3);
  transform: translateY(-4px);
  box-shadow: 0 20px 40px rgba(0,0,0,0.2);
}
.service-card:hover::before { transform: scaleX(1); }
.service-icon {
  width: 52px; height: 52px;
  background: rgba(232,201,122,0.1);
  border-radius: var(--radius);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 24px;
  margin-bottom: 20px;
}
.service-card h3 {
  font-family: var(--font-display);
  font-size: 20px;
  color: var(--color-white);
  margin-bottom: 10px;
}
.service-card p { font-size: 14px; color: var(--color-text-muted); line-height: 1.7; margin-bottom: 24px; }
.service-links { display: flex; gap: 12px; }
.service-links a {
  font-size: 13px;
  font-weight: 600;
  color: var(--color-primary);
  display: flex;
  align-items: center;
  gap: 4px;
  transition: var(--transition);
}
.service-links a:hover { gap: 8px; }

/* =============================================
   WHY CHOOSE US
   ============================================= */
.why-section { padding: 100px 24px; }
.why-inner {
  max-width: var(--max-width);
  margin: 0 auto;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 80px;
  align-items: center;
}
.why-visual {
  position: relative;
  border-radius: var(--radius-lg);
  overflow: hidden;
  background: linear-gradient(135deg, #1a3a5c 0%, #0d2035 100%);
  min-height: 420px;
  display: flex;
  align-items: center;
  justify-content: center;
}
.why-house-emoji { font-size: 120px; opacity: 0.8; }
.why-stat-badge {
  position: absolute;
  background: var(--color-card);
  border: 1px solid var(--color-card-border);
  border-radius: var(--radius);
  padding: 16px 20px;
  box-shadow: 0 10px 30px rgba(0,0,0,0.3);
}
.why-stat-badge.top-left { top: 24px; left: 24px; }
.why-stat-badge.bottom-right { bottom: 24px; right: 24px; }
.why-stat-badge .badge-num {
  font-family: var(--font-display);
  font-size: 28px;
  font-weight: 900;
  color: var(--color-primary);
}
.why-stat-badge .badge-text { font-size: 12px; color: var(--color-text-muted); }
.why-content h2 { margin-bottom: 40px; }
.why-features { display: flex; flex-direction: column; gap: 28px; }
.why-feature { display: flex; gap: 20px; }
.feature-icon {
  width: 48px; height: 48px;
  flex-shrink: 0;
  background: rgba(232,201,122,0.1);
  border: 1px solid rgba(232,201,122,0.2);
  border-radius: var(--radius);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 22px;
}
.feature-text h4 {
  font-family: var(--font-display);
  font-size: 18px;
  color: var(--color-white);
  margin-bottom: 6px;
}
.feature-text p { font-size: 14px; color: var(--color-text-muted); line-height: 1.7; }

/* =============================================
   FAQ
   ============================================= */
.faq-section {
  padding: 100px 24px;
  background: var(--color-bg-section);
}
.faq-inner { max-width: 800px; margin: 0 auto; }
.faq-header { text-align: center; margin-bottom: 56px; }
.faq-list { display: flex; flex-direction: column; gap: 12px; }
.faq-item {
  background: var(--color-card);
  border: 1px solid var(--color-card-border);
  border-radius: var(--radius);
  overflow: hidden;
  transition: var(--transition);
}
.faq-item.open { border-color: rgba(232,201,122,0.3); }
.faq-question {
  width: 100%;
  background: none;
  border: none;
  padding: 22px 28px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 16px;
  cursor: pointer;
  text-align: left;
  color: var(--color-white);
  font-family: var(--font-body);
  font-size: 16px;
  font-weight: 600;
}
.faq-question:hover { color: var(--color-primary); }
.faq-chevron {
  width: 28px; height: 28px;
  flex-shrink: 0;
  background: rgba(232,201,122,0.1);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 14px;
  transition: var(--transition);
}
.faq-item.open .faq-chevron { transform: rotate(180deg); background: var(--color-primary); color: #0B1A2C; }
.faq-answer {
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.4s ease, padding 0.3s ease;
  padding: 0 28px;
  font-size: 14px;
  color: var(--color-text-muted);
  line-height: 1.8;
}
.faq-item.open .faq-answer { max-height: 200px; padding: 0 28px 22px; }

/* =============================================
   TESTIMONIALS
   ============================================= */
.testimonials-section { padding: 100px 24px; }
.testimonials-inner { max-width: var(--max-width); margin: 0 auto; }
.testimonials-header { text-align: center; margin-bottom: 64px; }
.testimonials-header .section-sub { margin: 0 auto 24px; }
.testimonials-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 24px;
  margin-bottom: 24px;
}
.testimonials-grid.second-row { grid-template-columns: repeat(2, 1fr); max-width: 66%; margin: 0 auto; }
.testimonial-card {
  background: var(--color-card);
  border: 1px solid var(--color-card-border);
  border-radius: var(--radius-lg);
  padding: 32px;
  position: relative;
  transition: var(--transition);
}
.testimonial-card:hover {
  border-color: rgba(232,201,122,0.2);
  transform: translateY(-4px);
}
.testimonial-quote {
  font-size: 48px;
  color: var(--color-primary);
  line-height: 1;
  margin-bottom: 16px;
  font-family: Georgia, serif;
  opacity: 0.4;
}
.testimonial-title {
  font-family: var(--font-display);
  font-size: 16px;
  font-weight: 700;
  color: var(--color-primary);
  margin-bottom: 12px;
}
.testimonial-text { font-size: 14px; color: var(--color-text-muted); line-height: 1.75; margin-bottom: 24px; }
.testimonial-author { display: flex; align-items: center; gap: 12px; }
.author-avatar {
  width: 44px; height: 44px;
  border-radius: 50%;
  background: var(--color-primary);
  display: flex; align-items: center; justify-content: center;
  font-weight: 700;
  font-size: 16px;
  color: #0B1A2C;
  flex-shrink: 0;
}
.author-name {
  font-weight: 700;
  font-size: 14px;
  color: var(--color-white);
}
.author-location { font-size: 12px; color: var(--color-text-muted); }

/* =============================================
   CTA BANNER
   ============================================= */
.cta-section {
  padding: 80px 24px;
  background: linear-gradient(135deg, #0d2035 0%, #0b1a2c 100%);
  position: relative;
  overflow: hidden;
}
.cta-glow {
  position: absolute;
  top: 50%; left: 50%;
  transform: translate(-50%, -50%);
  width: 60vw; height: 60vh;
  background: radial-gradient(ellipse, rgba(232,201,122,0.07) 0%, transparent 70%);
  pointer-events: none;
}
.cta-inner {
  max-width: 700px;
  margin: 0 auto;
  text-align: center;
  position: relative;
  z-index: 2;
}
.cta-inner .section-title { font-size: clamp(28px, 4vw, 46px); margin-bottom: 20px; }
.cta-inner p { font-size: 17px; color: var(--color-text-muted); margin-bottom: 36px; }

/* =============================================
   CONTACT
   ============================================= */
.contact-section { padding: 100px 24px; }
.contact-inner {
  max-width: var(--max-width);
  margin: 0 auto;
  display: grid;
  grid-template-columns: 1fr 1.4fr;
  gap: 80px;
}
.contact-info h2 { margin-bottom: 20px; }
.contact-info .section-sub { margin-bottom: 40px; }
.contact-items { display: flex; flex-direction: column; gap: 28px; }
.contact-item { display: flex; gap: 16px; }
.contact-item-icon {
  width: 48px; height: 48px;
  flex-shrink: 0;
  background: rgba(232,201,122,0.1);
  border: 1px solid rgba(232,201,122,0.2);
  border-radius: var(--radius);
  display: flex; align-items: center; justify-content: center;
  font-size: 20px;
}
.contact-item-text label {
  font-size: 11px;
  letter-spacing: 2px;
  text-transform: uppercase;
  color: var(--color-text-muted);
  display: block;
  margin-bottom: 4px;
}
.contact-item-text a, .contact-item-text p {
  font-size: 15px;
  font-weight: 600;
  color: var(--color-white);
  transition: var(--transition);
}
.contact-item-text a:hover { color: var(--color-primary); }

/* Form */
.contact-form {
  background: var(--color-card);
  border: 1px solid var(--color-card-border);
  border-radius: var(--radius-lg);
  padding: 40px;
}
.contact-form h3 {
  font-family: var(--font-display);
  font-size: 24px;
  color: var(--color-white);
  margin-bottom: 28px;
}
.form-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }
.form-group { display: flex; flex-direction: column; gap: 8px; }
.form-group.full { grid-column: 1 / -1; }
.form-group label { font-size: 13px; font-weight: 600; color: var(--color-text-muted); }
.form-group input,
.form-group select,
.form-group textarea {
  background: rgba(255,255,255,0.04);
  border: 1px solid var(--color-card-border);
  border-radius: var(--radius);
  padding: 14px 16px;
  color: var(--color-white);
  font-family: var(--font-body);
  font-size: 14px;
  transition: var(--transition);
  width: 100%;
}
.form-group input:focus,
.form-group select:focus,
.form-group textarea:focus {
  outline: none;
  border-color: var(--color-primary);
  background: rgba(232,201,122,0.04);
}
.form-group input::placeholder,
.form-group textarea::placeholder { color: var(--color-text-muted); }
.form-group select option { background: var(--color-card); }
.form-group textarea { min-height: 80px; resize: vertical; }
.form-consent {
  font-size: 12px;
  color: var(--color-text-muted);
  line-height: 1.6;
  margin-top: 4px;
}
.form-consent a { color: var(--color-primary); }
.form-submit { margin-top: 24px; }
.form-submit .btn { width: 100%; justify-content: center; font-size: 15px; padding: 16px; }
.form-success {
  display: none;
  text-align: center;
  padding: 24px;
  color: #4ade80;
  font-weight: 600;
}

/* =============================================
   FOOTER
   ============================================= */
footer {
  background: #060f1a;
  border-top: 1px solid var(--color-card-border);
  padding: 64px 24px 32px;
}
.footer-inner {
  max-width: var(--max-width);
  margin: 0 auto;
}
.footer-grid {
  display: grid;
  grid-template-columns: 1.5fr 1fr 1fr;
  gap: 60px;
  margin-bottom: 48px;
}
.footer-brand .logo { margin-bottom: 16px; }
.footer-brand p { font-size: 14px; color: var(--color-text-muted); line-height: 1.7; max-width: 280px; }
.footer-col h4 {
  font-size: 12px;
  letter-spacing: 2px;
  text-transform: uppercase;
  color: var(--color-text-muted);
  margin-bottom: 20px;
}
.footer-col ul { display: flex; flex-direction: column; gap: 12px; }
.footer-col ul li a {
  font-size: 14px;
  color: var(--color-text);
  transition: var(--transition);
}
.footer-col ul li a:hover { color: var(--color-primary); }
.footer-bottom {
  border-top: 1px solid var(--color-card-border);
  padding-top: 24px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 12px;
}
.footer-bottom p { font-size: 13px; color: var(--color-text-muted); }
.footer-bottom a { color: var(--color-primary); }

/* =============================================
   RESPONSIVE
   ============================================= */
@media (max-width: 1024px) {
  .hero-inner { grid-template-columns: 1fr; text-align: center; }
  .hero-visual { display: none; }
  .why-inner { grid-template-columns: 1fr; }
  .why-visual { min-height: 280px; }
  .process-steps { grid-template-columns: 1fr; }
  .process-steps::before { display: none; }
  .testimonials-grid.second-row { grid-template-columns: 1fr; max-width: 100%; }
}
@media (max-width: 768px) {
  .nav-links, .nav-cta { display: none; }
  .hamburger { display: flex; }
  .stats-inner { grid-template-columns: repeat(2, 1fr); }
  .stat-divider { display: none; }
  .services-grid { grid-template-columns: 1fr; }
  .testimonials-grid { grid-template-columns: 1fr; }
  .footer-grid { grid-template-columns: 1fr; gap: 36px; }
  .contact-inner { grid-template-columns: 1fr; gap: 48px; }
  .form-grid { grid-template-columns: 1fr; }
}
@media (max-width: 480px) {
  .stats-inner { grid-template-columns: 1fr 1fr; }
  .hero-actions { justify-content: center; }
  .hero-social-proof { justify-content: center; }
}
```

  </style>
</head>
<body>

  <!-- ======================== NAVIGATION ======================== -->

  <nav id="navbar">
    <div class="nav-inner">
      <a href="#" class="nav-logo">
        <div class="logo-icon">🏡</div>
        <span><span class="logo-pip">Pip</span>House</span>
      </a>
      <ul class="nav-links">
        <li><a href="#">HOME</a></li>
        <li><a href="#services">SERVICES</a></li>
        <li><a href="#about">ABOUT US</a></li>
        <li><a href="#projects">PROJECTS</a></li>
        <li><a href="#contact">CONTACT US</a></li>
      </ul>
      <a href="#contact" class="btn btn-primary nav-cta">Get Started Today</a>
      <div class="hamburger" id="hamburger" onclick="toggleMenu()">
        <span></span><span></span><span></span>
      </div>
    </div>
  </nav>

  <!-- Mobile Nav -->

  <div class="mobile-nav" id="mobileNav">
    <a href="#" onclick="toggleMenu()">HOME</a>
    <a href="#services" onclick="toggleMenu()">SERVICES</a>
    <a href="#about" onclick="toggleMenu()">ABOUT US</a>
    <a href="#projects" onclick="toggleMenu()">PROJECTS</a>
    <a href="#contact" onclick="toggleMenu()">CONTACT US</a>
    <a href="#contact" class="btn btn-primary" onclick="toggleMenu()" style="text-align:center;margin-top:8px;">Get Started Today</a>
  </div>

  <!-- ======================== HERO ======================== -->

  <section class="hero">
    <div class="hero-bg-glow"></div>
    <div class="hero-bg-glow2"></div>
    <!-- Animated stars -->
    <div class="hero-stars" id="heroStars"></div>
    <!-- Snowflakes -->
    <div id="snowflakes"></div>

```
<div class="hero-inner">
  <div class="hero-content">
    <div class="hero-badge">⭐ Rated 4.9 on Google Reviews</div>
    <h1 class="hero-title">
      Give Yourself the Gift of a<br/>
      <em>Hassle-Free</em> Home Sale<br/>
      with PipHouse!
    </h1>
    <p class="hero-desc">
      At PipHouse, we make selling your property simple, fast, and stress-free —
      so you can focus on what truly matters.
    </p>
    <div class="hero-actions">
      <a href="#contact" class="btn btn-primary">Contact Us →</a>
      <a href="#about" class="btn btn-outline">Learn More</a>
    </div>
    <div class="hero-social-proof">
      <div class="hero-avatars">
        <span>S</span><span>M</span><span>N</span><span>B</span>
      </div>
      <div class="hero-social-text">
        <strong>300+ Happy Clients</strong>
        Trusted across the Dallas/Fort Worth area
      </div>
    </div>
  </div>

  <div class="hero-visual">
    <div class="hero-house-card">
      <div class="hero-house-img">
        🏠
        <span class="badge-price">$546,000</span>
        <span class="badge-verified">
          <span class="dot"></span> Available Now
        </span>
      </div>
      <div class="hero-house-info">
        <h3>House in Arlington</h3>
        <p>Cooper St, Arlington, TX 76010</p>
        <div class="hero-house-meta">
          <span>🛏 3 Beds</span>
          <span>🚿 2 Baths</span>
          <span>📐 3,580 sqft</span>
        </div>
      </div>
    </div>
  </div>
</div>
```

  </section>

  <!-- ======================== STATS ======================== -->

  <section class="stats-bar" id="about">
    <div class="stats-inner">
      <div class="stat-item">
        <div class="stat-num">4.9★</div>
        <div class="stat-label">Client Rating</div>
      </div>
      <div class="stat-item">
        <div class="stat-num">$17M+</div>
        <div class="stat-label">Real Estate Sold</div>
      </div>
      <div class="stat-item">
        <div class="stat-num">100+</div>
        <div class="stat-label">Properties Sold</div>
      </div>
      <div class="stat-item">
        <div class="stat-num">5+</div>
        <div class="stat-label">Years in Business</div>
      </div>
    </div>
  </section>

  <!-- ======================== TRUSTED BY ======================== -->

  <section class="trusted-section">
    <p class="trusted-label">Trusted By</p>
    <div class="marquee-wrapper">
      <div class="marquee-track">
        <div class="logo-pill">🏦 First American Title</div>
        <div class="logo-pill">🏢 Stewart Title</div>
        <div class="logo-pill">🚚 U-Haul Moving</div>
        <div class="logo-pill">🔑 Old Republic Title</div>
        <div class="logo-pill">🏡 Real Estate Partners</div>
        <!-- Duplicate for seamless loop -->
        <div class="logo-pill">🏦 First American Title</div>
        <div class="logo-pill">🏢 Stewart Title</div>
        <div class="logo-pill">🚚 U-Haul Moving</div>
        <div class="logo-pill">🔑 Old Republic Title</div>
        <div class="logo-pill">🏡 Real Estate Partners</div>
      </div>
    </div>
  </section>

  <!-- ======================== PROCESS ======================== -->

  <section class="process-section">
    <div class="process-inner">
      <div class="process-header">
        <p class="section-label">Working Process</p>
        <h2 class="section-title">Three Simple Steps to Sell Your Property!</h2>
        <p class="section-sub">Sell your property with our streamlined process: Share your property details, receive a fair cash offer, and let our expert team handle the rest, from review to closing.</p>
      </div>
      <div class="process-steps">
        <div class="process-step">
          <div class="step-num">01</div>
          <div class="step-icon">📋</div>
          <h3>Send Property Details Online</h3>
          <p>Submit your property information on our "Contact us" page.</p>
        </div>
        <div class="process-step">
          <div class="step-num">02</div>
          <div class="step-icon">🤝</div>
          <h3>Review and Offer</h3>
          <p>We'll reach out to discuss your situation, set a time to walk the property or have you submit pictures, and we'll provide you with an offer!</p>
        </div>
        <div class="process-step">
          <div class="step-num">03</div>
          <div class="step-icon">✅</div>
          <h3>Accept and Relax</h3>
          <p>Once you accept our offer, one of our friendly transactions coordinators will guide you through the rest. Holding your hand all the way until closing day.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- ======================== SERVICES ======================== -->

  <section class="services-section" id="services">
    <div class="services-inner">
      <div class="services-header">
        <p class="section-label">Services</p>
        <h2 class="section-title">Which Solution Best Fits Your Needs?</h2>
        <p class="section-sub" style="margin:0 auto;">Reach out to our friendly team for personalized assistance with your property needs.</p>
      </div>
      <div class="services-grid">
        <div class="service-card">
          <div class="service-icon">💵</div>
          <h3>Fast Cash Offer</h3>
          <p>Need money quickly? We've got you covered with our speedy cash offers.</p>
          <div class="service-links">
            <a href="#contact">Get Started →</a>
            <a href="#contact" style="color:var(--color-text-muted);">Learn More</a>
          </div>
        </div>
        <div class="service-card">
          <div class="service-icon">🔨</div>
          <h3>Renovations</h3>
          <p>Looking to upgrade your property? Our renovation services enhance your home's value.</p>
          <div class="service-links">
            <a href="#contact">Get Started →</a>
            <a href="#contact" style="color:var(--color-text-muted);">Learn More</a>
          </div>
        </div>
        <div class="service-card">
          <div class="service-icon">🏦</div>
          <h3>Monthly Mortgage Takeover</h3>
          <p>Say goodbye to the stress of monthly mortgage payments. Let us handle them for you.</p>
          <div class="service-links">
            <a href="#contact">Get Started →</a>
            <a href="#contact" style="color:var(--color-text-muted);">Learn More</a>
          </div>
        </div>
        <div class="service-card">
          <div class="service-icon">📄</div>
          <h3>Seller Finance</h3>
          <p>Want flexible payment options? We offer seller financing to suit your needs.</p>
          <div class="service-links">
            <a href="#contact">Get Started →</a>
            <a href="#contact" style="color:var(--color-text-muted);">Learn More</a>
          </div>
        </div>
        <div class="service-card">
          <div class="service-icon">🚚</div>
          <h3>Moving Services</h3>
          <p>Moving can be a hassle. Let us lighten the load with our convenient moving services.</p>
          <div class="service-links">
            <a href="#contact">Get Started →</a>
            <a href="#contact" style="color:var(--color-text-muted);">Learn More</a>
          </div>
        </div>
        <div class="service-card">
          <div class="service-icon">🎁</div>
          <h3>Referral Fees</h3>
          <p>Spread the word and earn up to $3,000 in referral fees. It's our way of saying thanks!</p>
          <div class="service-links">
            <a href="#contact">Get Started →</a>
            <a href="#contact" style="color:var(--color-text-muted);">Learn More</a>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- ======================== WHY CHOOSE US ======================== -->

  <section class="why-section">
    <div class="why-inner">
      <div class="why-visual">
        <div class="why-house-emoji">🏡</div>
        <div class="why-stat-badge top-left">
          <div class="badge-num">14</div>
          <div class="badge-text">Days to close</div>
        </div>
        <div class="why-stat-badge bottom-right">
          <div class="badge-num">$0</div>
          <div class="badge-text">Fees or commissions</div>
        </div>
      </div>
      <div class="why-content">
        <p class="section-label">Why Choose Us</p>
        <h2 class="section-title">Why Choose PipHouse for Your Property Needs?</h2>
        <div class="why-features">
          <div class="why-feature">
            <div class="feature-icon">💰</div>
            <div class="feature-text">
              <h4>No Commissions or Closing Costs</h4>
              <p>Say goodbye to commission fees and closing costs — our listings come with no hidden expenses, ensuring a straightforward and transparent buying process.</p>
            </div>
          </div>
          <div class="why-feature">
            <div class="feature-icon">⚡</div>
            <div class="feature-text">
              <h4>Fast Closing</h4>
              <p>Swift transactions await with our Fast Closing service, ensuring your real estate deals are completed efficiently and hassle-free, in as little as 14 days.</p>
            </div>
          </div>
          <div class="why-feature">
            <div class="feature-icon">🔍</div>
            <div class="feature-text">
              <h4>Complete Transparency</h4>
              <p>Experience trust and confidence with our commitment to complete transparency, ensuring a smooth and honest real estate journey.</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- ======================== FAQ ======================== -->

  <section class="faq-section">
    <div class="faq-inner">
      <div class="faq-header">
        <p class="section-label">FAQ</p>
        <h2 class="section-title">Have Questions? We've Got Answers!</h2>
        <p class="section-sub" style="margin:0 auto;">Get clarity on our process, fees, timelines, and more with these frequently asked questions.</p>
      </div>
      <div class="faq-list">
        <div class="faq-item">
          <button class="faq-question" onclick="toggleFaq(this)">
            How quickly can I expect to receive an offer for my property?
            <div class="faq-chevron">▾</div>
          </button>
          <div class="faq-answer">We strive to provide offers promptly. Typically, you'll receive an offer within 24 hours of sharing your property details with us.</div>
        </div>
        <div class="faq-item">
          <button class="faq-question" onclick="toggleFaq(this)">
            How do I get started with PipHouse?
            <div class="faq-chevron">▾</div>
          </button>
          <div class="faq-answer">Getting started with PipHouse is easy. Simply contact us through our website or give us a call to schedule a consultation. We'll guide you through the process and answer any questions you may have.</div>
        </div>
        <div class="faq-item">
          <button class="faq-question" onclick="toggleFaq(this)">
            What are the benefits of selling my property to PipHouse?
            <div class="faq-chevron">▾</div>
          </button>
          <div class="faq-answer">Selling your property to PipHouse offers several benefits, including fast cash offers, flexible closing timelines, no hidden costs or fees, complementary moving services if needed and personalized service tailored to your needs.</div>
        </div>
        <div class="faq-item">
          <button class="faq-question" onclick="toggleFaq(this)">
            Does PipHouse charge any fees for its services?
            <div class="faq-chevron">▾</div>
          </button>
          <div class="faq-answer">No, PipHouse does not charge any fees for its services. We cover all closing costs, fees, and commissions, ensuring a transparent and hassle-free experience for our clients.</div>
        </div>
        <div class="faq-item">
          <button class="faq-question" onclick="toggleFaq(this)">
            How soon can I expect to close the deal once I accept your offer?
            <div class="faq-chevron">▾</div>
          </button>
          <div class="faq-answer">At PipHouse, we understand the importance of a timely and efficient closing process. Once you accept our offer, we aim to finalize the deal as quickly as possible. In many cases, we can close the transaction in as little as 14 days.</div>
        </div>
      </div>
    </div>
  </section>

  <!-- ======================== TESTIMONIALS ======================== -->

  <section class="testimonials-section">
    <div class="testimonials-inner">
      <div class="testimonials-header">
        <p class="section-label">Testimonials</p>
        <h2 class="section-title">What Our Great Customers Say</h2>
        <p class="section-sub">Discover what our clients have to say about their experience with PipHouse.</p>
        <a href="#contact" class="btn btn-primary" style="margin-top:8px;">Contact Us</a>
      </div>
      <div class="testimonials-grid">
        <div class="testimonial-card">
          <div class="testimonial-quote">"</div>
          <div class="testimonial-title">GREAT JOB !!!</div>
          <p class="testimonial-text">We have had nothing but a good experience with PipHouse. Selling my mom's house, after she passed, was an emotional experience. Manny managed the complicated situation with great calmness and without pressure. His whole group was kind and respectful of my needs and timing. They worked with the title company, the movers and the estate sale group. GREAT JOB !!!</p>
          <div class="testimonial-author">
            <div class="author-avatar">SF</div>
            <div>
              <div class="author-name">Smith Family</div>
              <div class="author-location">Dallas, TX</div>
            </div>
          </div>
        </div>
        <div class="testimonial-card">
          <div class="testimonial-quote">"</div>
          <div class="testimonial-title">I highly recommend working with Manny</div>
          <p class="testimonial-text">Everyone at PipHouse was a pleasure to work with. In February of last year, my great aunt passed away and I needed to sell 2 of her properties to help with expenses. When I met with Manuel, he was extremely understanding of my situation and ensured me they would do everything possible to make sure this was a simple process.</p>
          <div class="testimonial-author">
            <div class="author-avatar">MA</div>
            <div>
              <div class="author-name">Marya Aguin</div>
              <div class="author-location">Dallas, TX</div>
            </div>
          </div>
        </div>
        <div class="testimonial-card">
          <div class="testimonial-quote">"</div>
          <div class="testimonial-title">Highly recommend them!</div>
          <p class="testimonial-text">PipHouse bought my grandfather's house last November and I can say it was a pleasure working with them! The whole process was simple and I really felt like they held our hands from start to finish. We had originally planned to list with an agent, but we decided to work with PipHouse instead because they could close quicker!</p>
          <div class="testimonial-author">
            <div class="author-avatar">MW</div>
            <div>
              <div class="author-name">Marcus Williams</div>
              <div class="author-location">Dallas, TX</div>
            </div>
          </div>
        </div>
      </div>
      <div class="testimonials-grid second-row">
        <div class="testimonial-card">
          <div class="testimonial-quote">"</div>
          <div class="testimonial-title">Manny is a great problem solver</div>
          <p class="testimonial-text">I have been very impressed with professionalism and friendliness at the same time. Manny is a great problem solver and very effective at getting things done. Enjoyed working with you!</p>
          <div class="testimonial-author">
            <div class="author-avatar">BA</div>
            <div>
              <div class="author-name">Bijan Afkami</div>
              <div class="author-location">Dallas, TX</div>
            </div>
          </div>
        </div>
        <div class="testimonial-card">
          <div class="testimonial-quote">"</div>
          <div class="testimonial-title">They were incredibly helpful!</div>
          <p class="testimonial-text">Definitely recommend if you need to sell your house fast and easy! They understood my situation and offered a creative solution that worked for my family and I. Not only did they make the process easy, they were incredibly helpful throughout the whole process!</p>
          <div class="testimonial-author">
            <div class="author-avatar">NR</div>
            <div>
              <div class="author-name">Nathan Ramirez</div>
              <div class="author-location">Dallas, TX</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- ======================== CTA BANNER ======================== -->

  <section class="cta-section">
    <div class="cta-glow"></div>
    <div class="cta-inner">
      <p class="section-label">Ready to Start?</p>
      <h2 class="section-title">Ready to Partner with Us? Let's Get Started Today!</h2>
      <p>Take the next step towards hassle-free property transactions by reaching out to us today. Whether you're selling, buying, or just curious, we're here to help!</p>
      <a href="#contact" class="btn btn-primary" style="font-size:16px;padding:16px 36px;">Get Started Today →</a>
    </div>
  </section>

  <!-- ======================== CONTACT ======================== -->

  <section class="contact-section" id="contact">
    <div class="contact-inner">
      <div class="contact-info">
        <p class="section-label">Contact Us</p>
        <h2 class="section-title">Let's Connect Today!</h2>
        <p class="section-sub">Connect with PipHouse: Reach out today to start your stress-free property journey. Our dedicated team is here to assist you every step of the way.</p>
        <div class="contact-items">
          <div class="contact-item">
            <div class="contact-item-icon">📍</div>
            <div class="contact-item-text">
              <label>Location</label>
              <p>1425 W Pioneer Dr, Irving, TX 75061, United States</p>
            </div>
          </div>
          <div class="contact-item">
            <div class="contact-item-icon">✉️</div>
            <div class="contact-item-text">
              <label>Email</label>
              <a href="mailto:PipHousellc@gmail.com">PipHousellc@gmail.com</a>
            </div>
          </div>
          <div class="contact-item">
            <div class="contact-item-icon">📞</div>
            <div class="contact-item-text">
              <label>Phone Number</label>
              <a href="tel:4696584582">(469) 658-4582</a>
            </div>
          </div>
        </div>
      </div>

```
  <div class="contact-form">
    <h3>Book A Free Estimate</h3>
    <div class="form-grid" id="contactForm">
      <div class="form-group">
        <label>Full Name</label>
        <input type="text" placeholder="John Smith" />
      </div>
      <div class="form-group">
        <label>Phone Number</label>
        <input type="tel" placeholder="(469) 000-0000" />
      </div>
      <div class="form-group">
        <label>Email</label>
        <input type="email" placeholder="john@email.com" />
      </div>
      <div class="form-group">
        <label>Date</label>
        <input type="date" />
      </div>
      <div class="form-group full">
        <label>Property Address</label>
        <input type="text" placeholder="123 Main St, Irving, TX" />
      </div>
      <div class="form-group full">
        <label>Property Condition</label>
        <select>
          <option value="">Select condition...</option>
          <option>Excellent</option>
          <option>Good</option>
          <option>Fair</option>
          <option>Needs Work</option>
        </select>
      </div>
      <div class="form-group full">
        <label>Estimated Mortgage Amount</label>
        <input type="text" placeholder="$0" />
      </div>
      <div class="form-group full">
        <label>Message</label>
        <textarea placeholder="Tell us about your situation..."></textarea>
      </div>
      <div class="form-group full">
        <p class="form-consent">I agree to receive text messages from PipHouse at the mobile number I provided. These messages may include helpful updates, exclusive promotions, and important information. Standard message and data rates may apply. You can opt out anytime by replying "STOP."</p>
      </div>
    </div>
    <div class="form-submit">
      <button class="btn btn-primary" onclick="submitForm()">Send My Request →</button>
    </div>
    <div class="form-success" id="formSuccess">
      ✅ Thank you! We will be in contact with you shortly!
    </div>
  </div>
</div>
```

  </section>

  <!-- ======================== FOOTER ======================== -->

  <footer>
    <div class="footer-inner">
      <div class="footer-grid">
        <div class="footer-brand">
          <div class="logo">
            <a href="#" class="nav-logo">
              <div class="logo-icon">🏡</div>
              <span><span class="logo-pip">Pip</span>House</span>
            </a>
          </div>
          <p style="margin-top:16px;">Where Every Property We Buy Tells a Story</p>
        </div>
        <div class="footer-col">
          <h4>Menu</h4>
          <ul>
            <li><a href="#">Home</a></li>
            <li><a href="#about">About Us</a></li>
            <li><a href="#services">Services</a></li>
            <li><a href="#projects">Projects</a></li>
            <li><a href="#contact">Contact Us</a></li>
            <li><a href="#">Disclaimers</a></li>
          </ul>
        </div>
        <div class="footer-col">
          <h4>Reach Us At</h4>
          <ul>
            <li><a href="#">1425 W Pioneer Dr, Irving, TX 75061</a></li>
            <li><a href="mailto:PipHousellc@gmail.com">PipHousellc@gmail.com</a></li>
            <li><a href="tel:4696584582">(469) 658-4582</a></li>
          </ul>
        </div>
      </div>
      <div class="footer-bottom">
        <p>Copyright © PipHouse LLC. 2026 | Designed and Developed by <a href="https://betheanomaly.io/" target="_blank">Anomaly</a></p>
        <a href="#">Privacy Policy & SMS Terms & Conditions</a>
      </div>
    </div>
  </footer>

  <!-- ======================== SCRIPTS ======================== -->

  <script>
    // ---------- Mobile Nav ----------
    function toggleMenu() {
      document.getElementById('mobileNav').classList.toggle('open');
    }

    // ---------- Navbar scroll shadow ----------
    window.addEventListener('scroll', () => {
      document.getElementById('navbar').style.boxShadow =
        window.scrollY > 20 ? '0 4px 30px rgba(0,0,0,0.4)' : 'none';
    });

    // ---------- Generate star field ----------
    (function generateStars() {
      const container = document.getElementById('heroStars');
      for (let i = 0; i < 60; i++) {
        const s = document.createElement('div');
        s.className = 'star';
        const size = Math.random() * 3 + 1;
        s.style.cssText = `
          width:${size}px; height:${size}px;
          top:${Math.random() * 100}%;
          left:${Math.random() * 100}%;
          animation-delay:${Math.random() * 4}s;
          animation-duration:${2 + Math.random() * 3}s;
        `;
        container.appendChild(s);
      }
    })();

    // ---------- Snowflakes ----------
    (function generateSnow() {
      const container = document.getElementById('snowflakes');
      const flakes = ['❄', '❅', '❆', '✦', '·'];
      for (let i = 0; i < 18; i++) {
        const f = document.createElement('div');
        f.className = 'snowflake';
        f.textContent = flakes[Math.floor(Math.random() * flakes.length)];
        f.style.cssText = `
          left:${Math.random() * 100}%;
          font-size:${Math.random() * 14 + 10}px;
          animation-duration:${6 + Math.random() * 8}s;
          animation-delay:${Math.random() * 8}s;
          opacity:${0.3 + Math.random() * 0.4};
        `;
        container.appendChild(f);
      }
    })();

    // ---------- FAQ Accordion ----------
    function toggleFaq(btn) {
      const item = btn.parentElement;
      const isOpen = item.classList.contains('open');
      // Close all
      document.querySelectorAll('.faq-item').forEach(i => i.classList.remove('open'));
      // Open clicked if it was closed
      if (!isOpen) item.classList.add('open');
    }

    // ---------- Form Submit ----------
    function submitForm() {
      document.getElementById('contactForm').style.display = 'none';
      document.querySelector('.form-submit').style.display = 'none';
      document.getElementById('formSuccess').style.display = 'block';
    }

    // ---------- Smooth scroll for anchor links ----------
    document.querySelectorAll('a[href^="#"]').forEach(a => {
      a.addEventListener('click', e => {
        const id = a.getAttribute('href').slice(1);
        if (!id) return;
        const el = document.getElementById(id);
        if (el) {
          e.preventDefault();
          el.scrollIntoView({ behavior: 'smooth', block: 'start' });
        }
      });
    });
  </script>

</body>
</html>
