<!DOCTYPE html>

<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Bendixen Bookkeeping & Advisory</title>
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,600;0,700;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet"/>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

```
:root {
  --navy:    #ffffff;
  --navy2:   #f5f7fa;
  --navy3:   #eef1f6;
  --gold:    #b8912e;
  --gold2:   #c9a84c;
  --gold3:   #e8c96d;
  --cream:   #faf7f0;
  --text:    #1a2535;
  --muted:   #5a6a80;
  --white:   #ffffff;
}

html { scroll-behavior: smooth; }

body {
  font-family: 'DM Sans', sans-serif;
  background: #ffffff;
  color: var(--text);
  overflow-x: hidden;
}

/* ── NOISE OVERLAY ── */
body::before {
  content: '';
  position: fixed;
  inset: 0;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
  pointer-events: none;
  z-index: 0;
  opacity: 0.15;
}

/* ── NAV ── */
nav {
  position: fixed;
  top: 0; left: 0; right: 0;
  z-index: 100;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 1.4rem 6vw;
  background: rgba(255,255,255,0.92);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid rgba(184,145,46,0.2);
}

.nav-logo {
  font-family: 'Cormorant Garamond', serif;
  font-size: 1.3rem;
  font-weight: 600;
  color: var(--gold);
  letter-spacing: 0.02em;
  text-decoration: none;
}

.nav-links {
  display: flex;
  gap: 2.4rem;
  list-style: none;
}

.nav-links a {
  text-decoration: none;
  color: var(--muted);
  font-size: 0.85rem;
  font-weight: 500;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  transition: color 0.2s;
}

.nav-links a:hover { color: var(--gold); }

.nav-cta {
  background: transparent;
  border: 1px solid var(--gold);
  color: var(--gold2) !important;
  padding: 0.5rem 1.4rem;
  border-radius: 2px;
  transition: background 0.2s, color 0.2s !important;
}

.nav-cta:hover {
  background: var(--gold) !important;
  color: var(--white) !important;
}

/* ── HERO ── */
.hero {
  position: relative;
  min-height: 100vh;
  display: flex;
  align-items: center;
  padding: 0 6vw;
  overflow: hidden;
}

.hero-bg {
  position: absolute;
  inset: 0;
  background:
    radial-gradient(ellipse 80% 60% at 70% 50%, rgba(184,145,46,0.08) 0%, transparent 60%),
    radial-gradient(ellipse 50% 80% at 10% 90%, rgba(230,235,245,0.9) 0%, transparent 70%),
    linear-gradient(135deg, #f0f4f8 0%, #ffffff 50%, #f8f9fb 100%);
  z-index: 0;
}

.hero-grid {
  position: absolute;
  inset: 0;
  background-image:
    linear-gradient(rgba(184,145,46,0.08) 1px, transparent 1px),
    linear-gradient(90deg, rgba(184,145,46,0.08) 1px, transparent 1px);
  background-size: 60px 60px;
  z-index: 0;
  mask-image: radial-gradient(ellipse 70% 70% at 70% 50%, black 0%, transparent 80%);
}

.hero-content {
  position: relative;
  z-index: 1;
  max-width: 700px;
}

.hero-eyebrow {
  display: inline-flex;
  align-items: center;
  gap: 0.7rem;
  font-size: 0.75rem;
  font-weight: 500;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  color: var(--gold);
  margin-bottom: 1.8rem;
  opacity: 0;
  animation: fadeUp 0.8s 0.2s forwards;
}

.hero-eyebrow::before {
  content: '';
  display: block;
  width: 32px;
  height: 1px;
  background: var(--gold);
}

.hero h1 {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(3rem, 6vw, 5.5rem);
  font-weight: 700;
  line-height: 1.05;
  color: var(--text);
  margin-bottom: 1.6rem;
  opacity: 0;
  animation: fadeUp 0.8s 0.35s forwards;
}

.hero h1 em {
  font-style: italic;
  color: var(--gold2);
}

.hero-sub {
  font-size: 1.05rem;
  font-weight: 300;
  color: var(--muted);
  line-height: 1.7;
  max-width: 500px;
  margin-bottom: 2.8rem;
  opacity: 0;
  animation: fadeUp 0.8s 0.5s forwards;
}

.hero-actions {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
  opacity: 0;
  animation: fadeUp 0.8s 0.65s forwards;
}

.btn-primary {
  display: inline-block;
  background: var(--gold);
  color: var(--navy);
  font-family: 'DM Sans', sans-serif;
  font-size: 0.85rem;
  font-weight: 500;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  padding: 1rem 2.2rem;
  text-decoration: none;
  border-radius: 2px;
  transition: background 0.2s, transform 0.2s;
  border: none;
  cursor: pointer;
}

.btn-primary:hover {
  background: var(--gold2);
  transform: translateY(-1px);
}

.btn-ghost {
  display: inline-block;
  background: transparent;
  color: var(--text);
  font-family: 'DM Sans', sans-serif;
  font-size: 0.85rem;
  font-weight: 500;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  padding: 1rem 2.2rem;
  text-decoration: none;
  border-radius: 2px;
  border: 1px solid rgba(255,255,255,0.15);
  transition: border-color 0.2s, color 0.2s;
  cursor: pointer;
}

.btn-ghost:hover {
  border-color: var(--gold);
  color: var(--gold2);
}

.hero-badge {
  position: absolute;
  right: 8vw;
  top: 50%;
  transform: translateY(-50%);
  width: 200px;
  height: 200px;
  opacity: 0;
  animation: fadeIn 1s 0.9s forwards;
}

.hero-badge svg {
  width: 100%;
  height: 100%;
  animation: rotateSlow 20s linear infinite;
}

.hero-badge-center {
  position: absolute;
  inset: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
}

.hero-badge-center span:first-child {
  font-family: 'Cormorant Garamond', serif;
  font-size: 2.5rem;
  font-weight: 700;
  color: var(--gold2);
  line-height: 1;
}

.hero-badge-center span:last-child {
  font-size: 0.65rem;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--muted);
  margin-top: 0.3rem;
}

/* ── TRUST BAR ── */
.trust-bar {
  position: relative;
  z-index: 1;
  background: #f0f4f8;
  border-top: 1px solid rgba(184,145,46,0.2);
  border-bottom: 1px solid rgba(184,145,46,0.2);
  padding: 1.4rem 6vw;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 3rem;
  flex-wrap: wrap;
}

.trust-item {
  display: flex;
  align-items: center;
  gap: 0.6rem;
  font-size: 0.8rem;
  font-weight: 500;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  color: var(--muted);
}

.trust-item svg {
  color: var(--gold);
  flex-shrink: 0;
}

.trust-divider {
  width: 1px;
  height: 20px;
  background: rgba(184,145,46,0.3);
}

/* ── SECTION SHARED ── */
section {
  position: relative;
  z-index: 1;
  padding: 6rem 6vw;
}

.section-label {
  display: inline-flex;
  align-items: center;
  gap: 0.7rem;
  font-size: 0.72rem;
  font-weight: 500;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  color: var(--gold);
  margin-bottom: 1rem;
}

.section-label::before {
  content: '';
  display: block;
  width: 24px;
  height: 1px;
  background: var(--gold);
}

.section-title {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(2rem, 4vw, 3.2rem);
  font-weight: 700;
  color: var(--text);
  line-height: 1.15;
  margin-bottom: 1rem;
}

.section-title em {
  font-style: italic;
  color: var(--gold2);
}

.section-sub {
  font-size: 0.95rem;
  color: var(--muted);
  line-height: 1.7;
  max-width: 520px;
  margin-bottom: 3.5rem;
}

/* ── ABOUT ── */
.about {
  background: var(--navy2);
}

.about-inner {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 5rem;
  align-items: center;
  max-width: 1100px;
  margin: 0 auto;
}

.about-visual {
  position: relative;
}

.about-card {
  background: #ffffff;
  border: 1px solid rgba(201,168,76,0.15);
  border-radius: 4px;
  padding: 2.5rem;
  position: relative;
  overflow: hidden;
}

.about-card::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 3px;
  background: linear-gradient(90deg, var(--gold), var(--gold2), transparent);
}

.about-card-name {
  font-family: 'Cormorant Garamond', serif;
  font-size: 1.8rem;
  font-weight: 700;
  color: var(--text);
  margin-bottom: 0.3rem;
}

.about-card-title {
  font-size: 0.8rem;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: var(--gold);
  margin-bottom: 1.5rem;
}

.about-card-bio {
  font-size: 0.9rem;
  color: #5a6a80;
  line-height: 1.7;
  margin-bottom: 1.8rem;
}

.about-stats {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1rem;
}

.about-stat {
  background: rgba(184,145,46,0.06);
  border: 1px solid rgba(184,145,46,0.15);
  border-radius: 3px;
  padding: 1rem;
  text-align: center;
}

.about-stat-num {
  font-family: 'Cormorant Garamond', serif;
  font-size: 1.8rem;
  font-weight: 700;
  color: var(--gold2);
  line-height: 1;
  margin-bottom: 0.3rem;
}

.about-stat-label {
  font-size: 0.7rem;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--muted);
}

.about-float {
  position: absolute;
  bottom: -1.5rem;
  right: -1.5rem;
  background: var(--gold);
  color: var(--navy);
  padding: 1rem 1.4rem;
  border-radius: 3px;
  font-size: 0.75rem;
  font-weight: 500;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  box-shadow: 0 8px 32px rgba(201,168,76,0.3);
}

.about-text p {
  font-size: 0.95rem;
  color: var(--muted);
  line-height: 1.8;
  margin-bottom: 1.2rem;
}

.about-text p strong {
  color: var(--text);
  font-weight: 500;
}

/* ── SERVICES ── */
.services { background: var(--navy); }

.services-inner {
  max-width: 1100px;
  margin: 0 auto;
}

.services-header {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 3rem;
  align-items: end;
  margin-bottom: 3.5rem;
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1.5rem;
}

.service-card {
  background: #ffffff;
  border: 1px solid rgba(201,168,76,0.1);
  border-radius: 4px;
  padding: 2rem;
  position: relative;
  overflow: hidden;
  transition: border-color 0.3s, transform 0.3s;
}

.service-card:hover {
  border-color: rgba(201,168,76,0.35);
  transform: translateY(-3px);
}

.service-card.featured {
  border-color: rgba(184,145,46,0.3);
  background: linear-gradient(135deg, #fdfaf3 0%, rgba(184,145,46,0.05) 100%);
}

.service-card.featured::after {
  content: 'Most Popular';
  position: absolute;
  top: 1rem; right: 1rem;
  font-size: 0.65rem;
  font-weight: 500;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: var(--navy);
  background: var(--gold);
  padding: 0.25rem 0.6rem;
  border-radius: 2px;
}

.service-icon {
  width: 42px;
  height: 42px;
  background: rgba(201,168,76,0.1);
  border-radius: 3px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 1.2rem;
  color: var(--gold);
}

.service-name {
  font-family: 'Cormorant Garamond', serif;
  font-size: 1.3rem;
  font-weight: 600;
  color: var(--text);
  margin-bottom: 0.6rem;
}

.service-desc {
  font-size: 0.85rem;
  color: var(--muted);
  line-height: 1.65;
  margin-bottom: 1.2rem;
}

.service-price {
  font-size: 0.75rem;
  font-weight: 500;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--gold);
}

/* ── HOW IT WORKS ── */
.how { background: var(--navy2); }

.how-inner {
  max-width: 900px;
  margin: 0 auto;
  text-align: center;
}

.how-steps {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 0;
  margin-top: 3.5rem;
  position: relative;
}

.how-steps::before {
  content: '';
  position: absolute;
  top: 28px;
  left: 12%;
  right: 12%;
  height: 1px;
  background: linear-gradient(90deg, transparent, var(--gold), transparent);
}

.how-step {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1rem;
  padding: 0 1rem;
}

.how-step-num {
  width: 56px;
  height: 56px;
  border-radius: 50%;
  background: #ffffff;
  border: 1px solid rgba(201,168,76,0.3);
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: 'Cormorant Garamond', serif;
  font-size: 1.4rem;
  font-weight: 700;
  color: var(--gold2);
  position: relative;
  z-index: 1;
  flex-shrink: 0;
}

.how-step-title {
  font-family: 'Cormorant Garamond', serif;
  font-size: 1.05rem;
  font-weight: 600;
  color: var(--text);
}

.how-step-desc {
  font-size: 0.8rem;
  color: var(--muted);
  line-height: 1.6;
}

/* ── PRICING ── */
.pricing { background: var(--navy); }

.pricing-inner {
  max-width: 900px;
  margin: 0 auto;
}

.pricing-formula {
  background: var(--navy2);
  border: 1px solid rgba(201,168,76,0.2);
  border-radius: 4px;
  padding: 2.5rem;
  text-align: center;
  margin-bottom: 2rem;
}

.pricing-formula-label {
  font-size: 0.72rem;
  letter-spacing: 0.18em;
  text-transform: uppercase;
  color: var(--gold);
  margin-bottom: 1rem;
}

.pricing-formula-eq {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(1.2rem, 3vw, 1.8rem);
  font-weight: 700;
  color: var(--white);
  line-height: 1.4;
}

.pricing-formula-eq span {
  color: var(--gold2);
}

.pricing-formula-note {
  font-size: 0.82rem;
  color: var(--muted);
  margin-top: 1rem;
}

.pricing-addons {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1rem;
  margin-bottom: 2rem;
}

.addon-card {
  background: #ffffff;
  border: 1px solid rgba(201,168,76,0.1);
  border-radius: 3px;
  padding: 1.4rem;
  display: flex;
  flex-direction: column;
  gap: 0.4rem;
}

.addon-name {
  font-size: 0.85rem;
  font-weight: 500;
  color: #1a2535;
}

.addon-price {
  font-family: 'Cormorant Garamond', serif;
  font-size: 1.3rem;
  font-weight: 700;
  color: var(--gold2);
}

.addon-desc {
  font-size: 0.78rem;
  color: var(--muted);
  line-height: 1.5;
}

.pricing-note {
  background: rgba(201,168,76,0.06);
  border: 1px solid rgba(201,168,76,0.12);
  border-left: 3px solid var(--gold);
  border-radius: 0 3px 3px 0;
  padding: 1rem 1.4rem;
  font-size: 0.82rem;
  color: var(--muted);
  line-height: 1.6;
}

/* ── CONTACT ── */
.contact { background: var(--navy2); }

.contact-inner {
  max-width: 900px;
  margin: 0 auto;
  display: grid;
  grid-template-columns: 1fr 1.2fr;
  gap: 5rem;
  align-items: start;
}

.contact-info p {
  font-size: 0.9rem;
  color: var(--muted);
  line-height: 1.75;
  margin-bottom: 2rem;
}

.contact-detail {
  display: flex;
  align-items: center;
  gap: 0.8rem;
  margin-bottom: 1rem;
  font-size: 0.85rem;
  color: var(--muted);
}

.contact-detail svg { color: var(--gold); flex-shrink: 0; }

.contact-form {
  background: #ffffff;
  border: 1px solid rgba(201,168,76,0.12);
  border-radius: 4px;
  padding: 2.5rem;
  position: relative;
  overflow: hidden;
}

.contact-form::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 3px;
  background: linear-gradient(90deg, var(--gold), var(--gold2), transparent);
}

.form-title {
  font-family: 'Cormorant Garamond', serif;
  font-size: 1.5rem;
  font-weight: 700;
  color: var(--text);
  margin-bottom: 1.6rem;
}

.form-row {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1rem;
}

.form-group {
  margin-bottom: 1.2rem;
}

.form-group label {
  display: block;
  font-size: 0.72rem;
  font-weight: 500;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: var(--muted);
  margin-bottom: 0.5rem;
}

.form-group input,
.form-group select,
.form-group textarea {
  width: 100%;
  background: #f8fafc;
  border: 1px solid rgba(201,168,76,0.15);
  border-radius: 2px;
  padding: 0.75rem 1rem;
  color: #1a2535;
  font-family: 'DM Sans', sans-serif;
  font-size: 0.88rem;
  outline: none;
  transition: border-color 0.2s;
  appearance: none;
}

.form-group input:focus,
.form-group select:focus,
.form-group textarea:focus {
  border-color: var(--gold);
}

.form-group input::placeholder,
.form-group textarea::placeholder { color: rgba(138,155,176,0.5); }

.form-group select option { background: #ffffff; }

.form-group textarea { resize: vertical; min-height: 100px; }

.form-submit {
  width: 100%;
  margin-top: 0.5rem;
}

.form-success {
  display: none;
  text-align: center;
  padding: 2rem;
}

.form-success-icon {
  width: 56px;
  height: 56px;
  background: rgba(201,168,76,0.1);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 1rem;
  color: var(--gold);
}

.form-success h3 {
  font-family: 'Cormorant Garamond', serif;
  font-size: 1.5rem;
  color: var(--text);
  margin-bottom: 0.5rem;
}

.form-success p {
  font-size: 0.88rem;
  color: var(--muted);
}

/* ── FOOTER ── */
footer {
  position: relative;
  z-index: 1;
  background: #1a2535;
  border-top: 1px solid rgba(201,168,76,0.1);
  padding: 2rem 6vw;
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 1rem;
}

.footer-logo {
  font-family: 'Cormorant Garamond', serif;
  font-size: 1.1rem;
  font-weight: 600;
  color: var(--gold3);
}

.footer-copy {
  font-size: 0.78rem;
  color: var(--muted);
}

.footer-copy a {
  color: var(--gold);
  text-decoration: none;
}

/* ── ANIMATIONS ── */
@keyframes fadeUp {
  from { opacity: 0; transform: translateY(20px); }
  to   { opacity: 1; transform: translateY(0); }
}

@keyframes fadeIn {
  from { opacity: 0; }
  to   { opacity: 1; }
}

@keyframes rotateSlow {
  from { transform: rotate(0deg); }
  to   { transform: rotate(360deg); }
}

.reveal {
  opacity: 0;
  transform: translateY(24px);
  transition: opacity 0.7s ease, transform 0.7s ease;
}

.reveal.visible {
  opacity: 1;
  transform: translateY(0);
}

/* ── RESPONSIVE ── */
@media (max-width: 900px) {
  .hero-badge { display: none; }
  .about-inner { grid-template-columns: 1fr; gap: 3rem; }
  .services-grid { grid-template-columns: 1fr; }
  .services-header { grid-template-columns: 1fr; }
  .how-steps { grid-template-columns: 1fr 1fr; gap: 2rem; }
  .how-steps::before { display: none; }
  .pricing-addons { grid-template-columns: 1fr; }
  .contact-inner { grid-template-columns: 1fr; gap: 3rem; }
  .nav-links { display: none; }
  .form-row { grid-template-columns: 1fr; }
}
```

  </style>
</head>
<body>

  <!-- NAV -->

  <nav>
    <a href="#" class="nav-logo">Bendixen Bookkeeping &amp; Advisory</a>
    <ul class="nav-links">
      <li><a href="#about">About</a></li>
      <li><a href="#services">Services</a></li>
      <li><a href="#contact" class="nav-cta">Get Started</a></li>
    </ul>
  </nav>

  <!-- HERO -->

  <section class="hero">
    <div class="hero-bg"></div>
    <div class="hero-grid"></div>
    <div class="hero-content">
      <div class="hero-eyebrow">QuickBooks ProAdvisor Certified</div>
      <h1>Books You Can<br><em>Actually Trust.</em></h1>
      <p class="hero-sub">
        Local bookkeeping for small businesses — clean books, clear reports,
        and a real person who picks up the phone. No jargon, no surprises.
      </p>
      <div class="hero-actions">
        <a href="#contact" class="btn-primary">Get a Free Consultation</a>
        <a href="#services" class="btn-ghost">See Services</a>
      </div>
    </div>

```
<!-- Rotating badge -->
<div class="hero-badge">
  <svg viewBox="0 0 200 200" fill="none" xmlns="http://www.w3.org/2000/svg">
    <circle cx="100" cy="100" r="90" stroke="rgba(184,145,46,0.25)" stroke-width="1"/>
    <circle cx="100" cy="100" r="78" stroke="rgba(184,145,46,0.2)" stroke-width="1" stroke-dasharray="4 6"/>
    <path id="circlePath" d="M 100,100 m -65,0 a 65,65 0 1,1 130,0 a 65,65 0 1,1 -130,0" fill="none"/>
    <text font-family="DM Sans, sans-serif" font-size="11" fill="rgba(201,168,76,0.7)" font-weight="500" letter-spacing="4">
      <textPath href="#circlePath">BENDIXEN BOOKKEEPING & ADVISORY • </textPath>
    </text>
  </svg>
  <div class="hero-badge-center">
    <span>QB</span>
    <span>ProAdvisor</span>
  </div>
</div>
```

  </section>

  <!-- TRUST BAR -->

  <div class="trust-bar">
    <div class="trust-item">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg>
      QuickBooks ProAdvisor Certified
    </div>
    <div class="trust-divider"></div>
    <div class="trust-item">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><path d="M12 8v4l3 3"/></svg>
      Monthly Reports Delivered On Time
    </div>
    <div class="trust-divider"></div>
    <div class="trust-item">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"/><circle cx="9" cy="7" r="4"/><path d="M23 21v-2a4 4 0 0 0-3-3.87"/><path d="M16 3.13a4 4 0 0 1 0 7.75"/></svg>
      Local & Personal Service
    </div>
    <div class="trust-divider"></div>
    <div class="trust-item">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="3" y="11" width="18" height="11" rx="2" ry="2"/><path d="M7 11V7a5 5 0 0 1 10 0v4"/></svg>
      Secure & Confidential
    </div>
  </div>

  <!-- ABOUT -->

  <section class="about" id="about">
    <div class="about-inner">
      <div class="about-visual reveal">
        <div class="about-card">
          <div class="about-card-name">Caleb Bendixen</div>
          <div class="about-card-title">Owner · QuickBooks ProAdvisor</div>
          <p class="about-card-bio">
            Finance graduate with hands-on training in QuickBooks Online,
            financial reporting, and small business bookkeeping. I started Bendixen Bookkeeping
            because small business owners deserve clean books and someone who actually explains what they mean.
          </p>
          <div class="about-stats">
            <div class="about-stat">
              <div class="about-stat-num">QB</div>
              <div class="about-stat-label">ProAdvisor Certified</div>
            </div>
            <div class="about-stat">
              <div class="about-stat-num">100%</div>
              <div class="about-stat-label">Local & Personalized</div>
            </div>
          </div>

```
    </div>
  </div>
  <div class="about-text reveal">
    <div class="section-label">About Me</div>
    <h2 class="section-title">A Local Bookkeeper<br>Who <em>Actually Cares</em></h2>
    <p>
      I started Bendixen Bookkeeping & Advisory because I kept seeing the same problem:
      <strong>small business owners doing their own books late at night</strong>, stressed about
      whether the numbers were right, and never quite sure where their money was going.
    </p>
    <p>
      With a Finance degree and QuickBooks ProAdvisor certification, I bring
      real expertise — but more importantly, I communicate in plain English. No confusing
      jargon, no mystery invoices, no ghosting.
    </p>
    <p>
      <strong>You focus on running your business. I'll handle the books.</strong>
    </p>
    <a href="#contact" class="btn-primary" style="margin-top:1rem;">Let's Work Together</a>
  </div>
</div>
```

  </section>

  <!-- SERVICES -->

  <section class="services" id="services">
    <div class="services-inner">
      <div class="services-header">
        <div class="reveal">
          <div class="section-label">What I Offer</div>
          <h2 class="section-title">Services Built for<br><em>Small Businesses</em></h2>
        </div>
        <p class="section-sub reveal" style="margin-bottom:0;">
          Everything runs through QuickBooks Online so your books are always organized,
          accessible, and ready for tax season — no scrambling in April.
        </p>
      </div>
      <div class="services-grid">
        <div class="service-card reveal">
          <div class="service-icon">
            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 2L2 7l10 5 10-5-10-5z"/><path d="M2 17l10 5 10-5"/><path d="M2 12l10 5 10-5"/></svg>
          </div>
          <div class="service-name">Transaction Categorization</div>
          <p class="service-desc">Every transaction reviewed, categorized, and organized in QuickBooks so your books are always accurate and audit-ready.</p>

```
    </div>
    <div class="service-card reveal">
      <div class="service-icon">
        <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="22 12 18 12 15 21 9 3 6 12 2 12"/></svg>
      </div>
      <div class="service-name">Account Reconciliation</div>
      <p class="service-desc">Monthly reconciliation of all bank and credit card accounts so your records match reality — no surprises, no discrepancies.</p>
      
    </div>
    <div class="service-card reveal">
      <div class="service-icon">
        <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="3" y="3" width="18" height="18" rx="2"/><path d="M3 9h18M9 21V9"/></svg>
      </div>
      <div class="service-name">Financial Reports</div>
      <p class="service-desc">Every month you'll receive your three core financial statements — <strong>Profit & Loss</strong> (income vs. expenses), <strong>Balance Sheet</strong> (assets, liabilities & equity), and <strong>Statement of Cash Flows</strong> (where your cash actually went). All generated from your clean books in QuickBooks.</p>
      
    </div>
    <div class="service-card reveal">
      <div class="service-icon">
        <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"/><polyline points="14 2 14 8 20 8"/><line x1="16" y1="13" x2="8" y2="13"/><line x1="16" y1="17" x2="8" y2="17"/></svg>
      </div>
      <div class="service-name">Monthly Summary</div>
      <p class="service-desc">A plain-English written narrative explaining what your numbers actually mean — trends, highlights, and anything to watch.</p>
      
    </div>
    <div class="service-card reveal">
      <div class="service-icon">
        <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"/></svg>
      </div>
      <div class="service-name">Quarterly Advisory Call</div>
      <p class="service-desc">A focused 30–60 minute call to review your financials, discuss your numbers, and answer your questions every quarter.</p>
      
    </div>
    <div class="service-card reveal">
      <div class="service-icon">
        <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><path d="M9.09 9a3 3 0 0 1 5.83 1c0 2-3 3-3 3"/><line x1="12" y1="17" x2="12.01" y2="17"/></svg>
      </div>
      <div class="service-name">Catch-Up Bookkeeping</div>
      <p class="service-desc">Behind on your books? I'll get everything caught up and organized from scratch so you start fresh with clean records.</p>
      
    </div>
  </div>
</div>
```

  </section>

  <!-- HOW IT WORKS -->

  <section class="how">
    <div class="how-inner">
      <div class="reveal">
        <div class="section-label">The Process</div>
        <h2 class="section-title">Simple to <em>Get Started</em></h2>
        <p class="section-sub" style="margin:0.8rem auto 0; text-align:center;">
          From first conversation to clean books in under a week.
        </p>
      </div>
      <div class="how-steps">
        <div class="how-step reveal">
          <div class="how-step-num">1</div>
          <div class="how-step-title">Free Consultation</div>
          <p class="how-step-desc">We chat about your business, your current books, and what you need. No pressure, no commitment.</p>
        </div>
        <div class="how-step reveal">
          <div class="how-step-num">2</div>
          <div class="how-step-title">Custom Quote</div>
          <p class="how-step-desc">I calculate your flat monthly fee based on your transaction volume — transparent and straightforward.</p>
        </div>
        <div class="how-step reveal">
          <div class="how-step-num">3</div>
          <div class="how-step-title">Onboarding</div>
          <p class="how-step-desc">Sign the engagement letter, get set up in QuickBooks, and share access. Usually done in a day.</p>
        </div>
        <div class="how-step reveal">
          <div class="how-step-num">4</div>
          <div class="how-step-title">Clean Books Monthly</div>
          <p class="how-step-desc">Sit back. Your books are done and your P&L lands in your inbox every month like clockwork.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- CONTACT -->

  <section class="contact" id="contact">
    <div class="contact-inner">
      <div class="contact-info reveal">
        <div class="section-label">Get In Touch</div>
        <h2 class="section-title">Let's Talk<br><em>About Your Books</em></h2>
        <p>Fill out the form and I'll get back to you within 1 business day. The first conversation is always free — no pressure, no commitment.</p>
        <div class="contact-detail">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
          caleb@bendixenbookkeeping.com
        </div>
        <div class="contact-detail">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07A19.5 19.5 0 0 1 4.69 12 19.79 19.79 0 0 1 1.65 3.37 2 2 0 0 1 3.62 1h3a2 2 0 0 1 2 1.72c.127.96.361 1.903.7 2.81a2 2 0 0 1-.45 2.11L7.91 8.8a16 16 0 0 0 6.29 6.29l.86-.86a2 2 0 0 1 2.11-.45c.907.339 1.85.573 2.81.7A2 2 0 0 1 22 16.92z"/></svg>
          608-669-6162
        </div>
        <div class="contact-detail">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"/><circle cx="12" cy="10" r="3"/></svg>
          Wisconsin Based · Serving Clients Remotely
        </div>
        <div class="contact-detail">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><polyline points="12 6 12 12 16 14"/></svg>
          Response within 1 business day
        </div>
      </div>
      <div class="contact-form reveal">
        <div id="formContent">
          <div class="form-title">Request a Free Consultation</div>
          <div class="form-row">
            <div class="form-group">
              <label>First Name</label>
              <input type="text" placeholder="Jane" id="firstName"/>
            </div>
            <div class="form-group">
              <label>Last Name</label>
              <input type="text" placeholder="Smith" id="lastName"/>
            </div>
          </div>
          <div class="form-group">
            <label>Business Name</label>
            <input type="text" placeholder="Smith Landscaping LLC" id="businessName"/>
          </div>
          <div class="form-group">
            <label>Email Address</label>
            <input type="email" placeholder="jane@yourbusiness.com" id="email"/>
          </div>
          <div class="form-group">
            <label>Current Bookkeeping Situation</label>
            <select id="situation">
              <option value="" disabled selected>Select one...</option>
              <option>I do it myself</option>
              <option>I'm behind / need catch-up</option>
              <option>I have someone but want to switch</option>
              <option>Just starting out</option>
            </select>
          </div>
          <div class="form-group">
            <label>Anything else I should know?</label>
            <textarea placeholder="Tell me a bit about your business, industry, or what you're looking for..." id="message"></textarea>
          </div>
          <button class="btn-primary form-submit" onclick="submitForm()">Send My Request →</button>
        </div>
        <div class="form-success" id="formSuccess">
          <div class="form-success-icon">
            <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"/></svg>
          </div>
          <h3>Message Received!</h3>
          <p>Thanks for reaching out. I'll be in touch within 1 business day to schedule your free consultation.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- FOOTER -->

  <footer>
    <div class="footer-logo">Bendixen Bookkeeping & Advisory</div>
    <div class="footer-copy">
      © 2026 Bendixen Bookkeeping & Advisory LLC · Wisconsin ·
      <a href="mailto:caleb@bendixenbookkeeping.com">caleb@bendixenbookkeeping.com</a>
    </div>
  </footer>

  <script>
    // Scroll reveal
    const reveals = document.querySelectorAll('.reveal');
    const observer = new IntersectionObserver((entries) => {
      entries.forEach((entry, i) => {
        if (entry.isIntersecting) {
          setTimeout(() => entry.target.classList.add('visible'), i * 80);
        }
      });
    }, { threshold: 0.1 });
    reveals.forEach(el => observer.observe(el));

    // Form submit
    function submitForm() {
      const email = document.getElementById('email').value;
      const firstName = document.getElementById('firstName').value;
      if (!firstName || !email) {
        alert('Please fill in your name and email.');
        return;
      }
      document.getElementById('formContent').style.display = 'none';
      document.getElementById('formSuccess').style.display = 'block';
    }

    // Smooth nav
    document.querySelectorAll('a[href^="#"]').forEach(a => {
      a.addEventListener('click', e => {
        const target = document.querySelector(a.getAttribute('href'));
        if (target) {
          e.preventDefault();
          target.scrollIntoView({ behavior: 'smooth', block: 'start' });
        }
      });
    });
  </script>

</body>
</html>

Get Outlook for iOS
From: Bendixen, Caleb <BendixenCG15@uww.edu>
Sent: Thursday, May 7, 2026 4:05:46 PM
To: Bendixen, Caleb <BendixenCG15@uww.edu>
Subject: Re: Updated White
 
<!DOCTYPE html>

<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Bendixen Bookkeeping & Advisory</title>
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,600;0,700;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet"/>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

```
:root {
  --navy:    #ffffff;
  --navy2:   #f5f7fa;
  --navy3:   #eef1f6;
  --gold:    #b8912e;
  --gold2:   #c9a84c;
  --gold3:   #e8c96d;
  --cream:   #faf7f0;
  --text:    #1a2535;
  --muted:   #5a6a80;
  --white:   #ffffff;
}

html { scroll-behavior: smooth; }

body {
  font-family: 'DM Sans', sans-serif;
  background: #ffffff;
  color: var(--text);
  overflow-x: hidden;
}

/* ── NOISE OVERLAY ── */
body::before {
  content: '';
  position: fixed;
  inset: 0;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
  pointer-events: none;
  z-index: 0;
  opacity: 0.15;
}

/* ── NAV ── */
nav {
  position: fixed;
  top: 0; left: 0; right: 0;
  z-index: 100;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 1.4rem 6vw;
  background: rgba(255,255,255,0.92);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid rgba(184,145,46,0.2);
}

.nav-logo {
  font-family: 'Cormorant Garamond', serif;
  font-size: 1.3rem;
  font-weight: 600;
  color: var(--gold);
  letter-spacing: 0.02em;
  text-decoration: none;
}

.nav-links {
  display: flex;
  gap: 2.4rem;
  list-style: none;
}

.nav-links a {
  text-decoration: none;
  color: var(--muted);
  font-size: 0.85rem;
  font-weight: 500;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  transition: color 0.2s;
}

.nav-links a:hover { color: var(--gold); }

.nav-cta {
  background: transparent;
  border: 1px solid var(--gold);
  color: var(--gold2) !important;
  padding: 0.5rem 1.4rem;
  border-radius: 2px;
  transition: background 0.2s, color 0.2s !important;
}

.nav-cta:hover {
  background: var(--gold) !important;
  color: var(--white) !important;
}

/* ── HERO ── */
.hero {
  position: relative;
  min-height: 100vh;
  display: flex;
  align-items: center;
  padding: 0 6vw;
  overflow: hidden;
}

.hero-bg {
  position: absolute;
  inset: 0;
  background:
    radial-gradient(ellipse 80% 60% at 70% 50%, rgba(184,145,46,0.08) 0%, transparent 60%),
    radial-gradient(ellipse 50% 80% at 10% 90%, rgba(230,235,245,0.9) 0%, transparent 70%),
    linear-gradient(135deg, #f0f4f8 0%, #ffffff 50%, #f8f9fb 100%);
  z-index: 0;
}

.hero-grid {
  position: absolute;
  inset: 0;
  background-image:
    linear-gradient(rgba(184,145,46,0.08) 1px, transparent 1px),
    linear-gradient(90deg, rgba(184,145,46,0.08) 1px, transparent 1px);
  background-size: 60px 60px;
  z-index: 0;
  mask-image: radial-gradient(ellipse 70% 70% at 70% 50%, black 0%, transparent 80%);
}

.hero-content {
  position: relative;
  z-index: 1;
  max-width: 700px;
}

.hero-eyebrow {
  display: inline-flex;
  align-items: center;
  gap: 0.7rem;
  font-size: 0.75rem;
  font-weight: 500;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  color: var(--gold);
  margin-bottom: 1.8rem;
  opacity: 0;
  animation: fadeUp 0.8s 0.2s forwards;
}

.hero-eyebrow::before {
  content: '';
  display: block;
  width: 32px;
  height: 1px;
  background: var(--gold);
}

.hero h1 {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(3rem, 6vw, 5.5rem);
  font-weight: 700;
  line-height: 1.05;
  color: var(--text);
  margin-bottom: 1.6rem;
  opacity: 0;
  animation: fadeUp 0.8s 0.35s forwards;
}

.hero h1 em {
  font-style: italic;
  color: var(--gold2);
}

.hero-sub {
  font-size: 1.05rem;
  font-weight: 300;
  color: var(--muted);
  line-height: 1.7;
  max-width: 500px;
  margin-bottom: 2.8rem;
  opacity: 0;
  animation: fadeUp 0.8s 0.5s forwards;
}

.hero-actions {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
  opacity: 0;
  animation: fadeUp 0.8s 0.65s forwards;
}

.btn-primary {
  display: inline-block;
  background: var(--gold);
  color: var(--navy);
  font-family: 'DM Sans', sans-serif;
  font-size: 0.85rem;
  font-weight: 500;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  padding: 1rem 2.2rem;
  text-decoration: none;
  border-radius: 2px;
  transition: background 0.2s, transform 0.2s;
  border: none;
  cursor: pointer;
}

.btn-primary:hover {
  background: var(--gold2);
  transform: translateY(-1px);
}

.btn-ghost {
  display: inline-block;
  background: transparent;
  color: var(--text);
  font-family: 'DM Sans', sans-serif;
  font-size: 0.85rem;
  font-weight: 500;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  padding: 1rem 2.2rem;
  text-decoration: none;
  border-radius: 2px;
  border: 1px solid rgba(255,255,255,0.15);
  transition: border-color 0.2s, color 0.2s;
  cursor: pointer;
}

.btn-ghost:hover {
  border-color: var(--gold);
  color: var(--gold2);
}

.hero-badge {
  position: absolute;
  right: 8vw;
  top: 50%;
  transform: translateY(-50%);
  width: 200px;
  height: 200px;
  opacity: 0;
  animation: fadeIn 1s 0.9s forwards;
}

.hero-badge svg {
  width: 100%;
  height: 100%;
  animation: rotateSlow 20s linear infinite;
}

.hero-badge-center {
  position: absolute;
  inset: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
}

.hero-badge-center span:first-child {
  font-family: 'Cormorant Garamond', serif;
  font-size: 2.5rem;
  font-weight: 700;
  color: var(--gold2);
  line-height: 1;
}

.hero-badge-center span:last-child {
  font-size: 0.65rem;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--muted);
  margin-top: 0.3rem;
}

/* ── TRUST BAR ── */
.trust-bar {
  position: relative;
  z-index: 1;
  background: #f0f4f8;
  border-top: 1px solid rgba(184,145,46,0.2);
  border-bottom: 1px solid rgba(184,145,46,0.2);
  padding: 1.4rem 6vw;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 3rem;
  flex-wrap: wrap;
}

.trust-item {
  display: flex;
  align-items: center;
  gap: 0.6rem;
  font-size: 0.8rem;
  font-weight: 500;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  color: var(--muted);
}

.trust-item svg {
  color: var(--gold);
  flex-shrink: 0;
}

.trust-divider {
  width: 1px;
  height: 20px;
  background: rgba(184,145,46,0.3);
}

/* ── SECTION SHARED ── */
section {
  position: relative;
  z-index: 1;
  padding: 6rem 6vw;
}

.section-label {
  display: inline-flex;
  align-items: center;
  gap: 0.7rem;
  font-size: 0.72rem;
  font-weight: 500;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  color: var(--gold);
  margin-bottom: 1rem;
}

.section-label::before {
  content: '';
  display: block;
  width: 24px;
  height: 1px;
  background: var(--gold);
}

.section-title {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(2rem, 4vw, 3.2rem);
  font-weight: 700;
  color: var(--text);
  line-height: 1.15;
  margin-bottom: 1rem;
}

.section-title em {
  font-style: italic;
  color: var(--gold2);
}

.section-sub {
  font-size: 0.95rem;
  color: var(--muted);
  line-height: 1.7;
  max-width: 520px;
  margin-bottom: 3.5rem;
}

/* ── ABOUT ── */
.about {
  background: var(--navy2);
}

.about-inner {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 5rem;
  align-items: center;
  max-width: 1100px;
  margin: 0 auto;
}

.about-visual {
  position: relative;
}

.about-card {
  background: #ffffff;
  border: 1px solid rgba(201,168,76,0.15);
  border-radius: 4px;
  padding: 2.5rem;
  position: relative;
  overflow: hidden;
}

.about-card::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 3px;
  background: linear-gradient(90deg, var(--gold), var(--gold2), transparent);
}

.about-card-name {
  font-family: 'Cormorant Garamond', serif;
  font-size: 1.8rem;
  font-weight: 700;
  color: var(--text);
  margin-bottom: 0.3rem;
}

.about-card-title {
  font-size: 0.8rem;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: var(--gold);
  margin-bottom: 1.5rem;
}

.about-card-bio {
  font-size: 0.9rem;
  color: #5a6a80;
  line-height: 1.7;
  margin-bottom: 1.8rem;
}

.about-stats {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1rem;
}

.about-stat {
  background: rgba(184,145,46,0.06);
  border: 1px solid rgba(184,145,46,0.15);
  border-radius: 3px;
  padding: 1rem;
  text-align: center;
}

.about-stat-num {
  font-family: 'Cormorant Garamond', serif;
  font-size: 1.8rem;
  font-weight: 700;
  color: var(--gold2);
  line-height: 1;
  margin-bottom: 0.3rem;
}

.about-stat-label {
  font-size: 0.7rem;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--muted);
}

.about-float {
  position: absolute;
  bottom: -1.5rem;
  right: -1.5rem;
  background: var(--gold);
  color: var(--navy);
  padding: 1rem 1.4rem;
  border-radius: 3px;
  font-size: 0.75rem;
  font-weight: 500;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  box-shadow: 0 8px 32px rgba(201,168,76,0.3);
}

.about-text p {
  font-size: 0.95rem;
  color: var(--muted);
  line-height: 1.8;
  margin-bottom: 1.2rem;
}

.about-text p strong {
  color: var(--text);
  font-weight: 500;
}

/* ── SERVICES ── */
.services { background: var(--navy); }

.services-inner {
  max-width: 1100px;
  margin: 0 auto;
}

.services-header {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 3rem;
  align-items: end;
  margin-bottom: 3.5rem;
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1.5rem;
}

.service-card {
  background: #ffffff;
  border: 1px solid rgba(201,168,76,0.1);
  border-radius: 4px;
  padding: 2rem;
  position: relative;
  overflow: hidden;
  transition: border-color 0.3s, transform 0.3s;
}

.service-card:hover {
  border-color: rgba(201,168,76,0.35);
  transform: translateY(-3px);
}

.service-card.featured {
  border-color: rgba(184,145,46,0.3);
  background: linear-gradient(135deg, #fdfaf3 0%, rgba(184,145,46,0.05) 100%);
}

.service-card.featured::after {
  content: 'Most Popular';
  position: absolute;
  top: 1rem; right: 1rem;
  font-size: 0.65rem;
  font-weight: 500;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: var(--navy);
  background: var(--gold);
  padding: 0.25rem 0.6rem;
  border-radius: 2px;
}

.service-icon {
  width: 42px;
  height: 42px;
  background: rgba(201,168,76,0.1);
  border-radius: 3px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 1.2rem;
  color: var(--gold);
}

.service-name {
  font-family: 'Cormorant Garamond', serif;
  font-size: 1.3rem;
  font-weight: 600;
  color: var(--text);
  margin-bottom: 0.6rem;
}

.service-desc {
  font-size: 0.85rem;
  color: var(--muted);
  line-height: 1.65;
  margin-bottom: 1.2rem;
}

.service-price {
  font-size: 0.75rem;
  font-weight: 500;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--gold);
}

/* ── HOW IT WORKS ── */
.how { background: var(--navy2); }

.how-inner {
  max-width: 900px;
  margin: 0 auto;
  text-align: center;
}

.how-steps {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 0;
  margin-top: 3.5rem;
  position: relative;
}

.how-steps::before {
  content: '';
  position: absolute;
  top: 28px;
  left: 12%;
  right: 12%;
  height: 1px;
  background: linear-gradient(90deg, transparent, var(--gold), transparent);
}

.how-step {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1rem;
  padding: 0 1rem;
}

.how-step-num {
  width: 56px;
  height: 56px;
  border-radius: 50%;
  background: #ffffff;
  border: 1px solid rgba(201,168,76,0.3);
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: 'Cormorant Garamond', serif;
  font-size: 1.4rem;
  font-weight: 700;
  color: var(--gold2);
  position: relative;
  z-index: 1;
  flex-shrink: 0;
}

.how-step-title {
  font-family: 'Cormorant Garamond', serif;
  font-size: 1.05rem;
  font-weight: 600;
  color: var(--text);
}

.how-step-desc {
  font-size: 0.8rem;
  color: var(--muted);
  line-height: 1.6;
}

/* ── PRICING ── */
.pricing { background: var(--navy); }

.pricing-inner {
  max-width: 900px;
  margin: 0 auto;
}

.pricing-formula {
  background: var(--navy2);
  border: 1px solid rgba(201,168,76,0.2);
  border-radius: 4px;
  padding: 2.5rem;
  text-align: center;
  margin-bottom: 2rem;
}

.pricing-formula-label {
  font-size: 0.72rem;
  letter-spacing: 0.18em;
  text-transform: uppercase;
  color: var(--gold);
  margin-bottom: 1rem;
}

.pricing-formula-eq {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(1.2rem, 3vw, 1.8rem);
  font-weight: 700;
  color: var(--white);
  line-height: 1.4;
}

.pricing-formula-eq span {
  color: var(--gold2);
}

.pricing-formula-note {
  font-size: 0.82rem;
  color: var(--muted);
  margin-top: 1rem;
}

.pricing-addons {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1rem;
  margin-bottom: 2rem;
}

.addon-card {
  background: #ffffff;
  border: 1px solid rgba(201,168,76,0.1);
  border-radius: 3px;
  padding: 1.4rem;
  display: flex;
  flex-direction: column;
  gap: 0.4rem;
}

.addon-name {
  font-size: 0.85rem;
  font-weight: 500;
  color: #1a2535;
}

.addon-price {
  font-family: 'Cormorant Garamond', serif;
  font-size: 1.3rem;
  font-weight: 700;
  color: var(--gold2);
}

.addon-desc {
  font-size: 0.78rem;
  color: var(--muted);
  line-height: 1.5;
}

.pricing-note {
  background: rgba(201,168,76,0.06);
  border: 1px solid rgba(201,168,76,0.12);
  border-left: 3px solid var(--gold);
  border-radius: 0 3px 3px 0;
  padding: 1rem 1.4rem;
  font-size: 0.82rem;
  color: var(--muted);
  line-height: 1.6;
}

/* ── CONTACT ── */
.contact { background: var(--navy2); }

.contact-inner {
  max-width: 900px;
  margin: 0 auto;
  display: grid;
  grid-template-columns: 1fr 1.2fr;
  gap: 5rem;
  align-items: start;
}

.contact-info p {
  font-size: 0.9rem;
  color: var(--muted);
  line-height: 1.75;
  margin-bottom: 2rem;
}

.contact-detail {
  display: flex;
  align-items: center;
  gap: 0.8rem;
  margin-bottom: 1rem;
  font-size: 0.85rem;
  color: var(--muted);
}

.contact-detail svg { color: var(--gold); flex-shrink: 0; }

.contact-form {
  background: #ffffff;
  border: 1px solid rgba(201,168,76,0.12);
  border-radius: 4px;
  padding: 2.5rem;
  position: relative;
  overflow: hidden;
}

.contact-form::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 3px;
  background: linear-gradient(90deg, var(--gold), var(--gold2), transparent);
}

.form-title {
  font-family: 'Cormorant Garamond', serif;
  font-size: 1.5rem;
  font-weight: 700;
  color: var(--text);
  margin-bottom: 1.6rem;
}

.form-row {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1rem;
}

.form-group {
  margin-bottom: 1.2rem;
}

.form-group label {
  display: block;
  font-size: 0.72rem;
  font-weight: 500;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: var(--muted);
  margin-bottom: 0.5rem;
}

.form-group input,
.form-group select,
.form-group textarea {
  width: 100%;
  background: #f8fafc;
  border: 1px solid rgba(201,168,76,0.15);
  border-radius: 2px;
  padding: 0.75rem 1rem;
  color: #1a2535;
  font-family: 'DM Sans', sans-serif;
  font-size: 0.88rem;
  outline: none;
  transition: border-color 0.2s;
  appearance: none;
}

.form-group input:focus,
.form-group select:focus,
.form-group textarea:focus {
  border-color: var(--gold);
}

.form-group input::placeholder,
.form-group textarea::placeholder { color: rgba(138,155,176,0.5); }

.form-group select option { background: #ffffff; }

.form-group textarea { resize: vertical; min-height: 100px; }

.form-submit {
  width: 100%;
  margin-top: 0.5rem;
}

.form-success {
  display: none;
  text-align: center;
  padding: 2rem;
}

.form-success-icon {
  width: 56px;
  height: 56px;
  background: rgba(201,168,76,0.1);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 1rem;
  color: var(--gold);
}

.form-success h3 {
  font-family: 'Cormorant Garamond', serif;
  font-size: 1.5rem;
  color: var(--text);
  margin-bottom: 0.5rem;
}

.form-success p {
  font-size: 0.88rem;
  color: var(--muted);
}

/* ── FOOTER ── */
footer {
  position: relative;
  z-index: 1;
  background: #1a2535;
  border-top: 1px solid rgba(201,168,76,0.1);
  padding: 2rem 6vw;
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 1rem;
}

.footer-logo {
  font-family: 'Cormorant Garamond', serif;
  font-size: 1.1rem;
  font-weight: 600;
  color: var(--gold3);
}

.footer-copy {
  font-size: 0.78rem;
  color: var(--muted);
}

.footer-copy a {
  color: var(--gold);
  text-decoration: none;
}

/* ── ANIMATIONS ── */
@keyframes fadeUp {
  from { opacity: 0; transform: translateY(20px); }
  to   { opacity: 1; transform: translateY(0); }
}

@keyframes fadeIn {
  from { opacity: 0; }
  to   { opacity: 1; }
}

@keyframes rotateSlow {
  from { transform: rotate(0deg); }
  to   { transform: rotate(360deg); }
}

.reveal {
  opacity: 0;
  transform: translateY(24px);
  transition: opacity 0.7s ease, transform 0.7s ease;
}

.reveal.visible {
  opacity: 1;
  transform: translateY(0);
}

/* ── RESPONSIVE ── */
@media (max-width: 900px) {
  .hero-badge { display: none; }
  .about-inner { grid-template-columns: 1fr; gap: 3rem; }
  .services-grid { grid-template-columns: 1fr; }
  .services-header { grid-template-columns: 1fr; }
  .how-steps { grid-template-columns: 1fr 1fr; gap: 2rem; }
  .how-steps::before { display: none; }
  .pricing-addons { grid-template-columns: 1fr; }
  .contact-inner { grid-template-columns: 1fr; gap: 3rem; }
  .nav-links { display: none; }
  .form-row { grid-template-columns: 1fr; }
}
```

  </style>
</head>
<body>

  <!-- NAV -->

  <nav>
    <a href="#" class="nav-logo">Bendixen Bookkeeping &amp; Advisory</a>
    <ul class="nav-links">
      <li><a href="#about">About</a></li>
      <li><a href="#services">Services</a></li>
      <li><a href="#contact" class="nav-cta">Get Started</a></li>
    </ul>
  </nav>

  <!-- HERO -->

  <section class="hero">
    <div class="hero-bg"></div>
    <div class="hero-grid"></div>
    <div class="hero-content">
      <div class="hero-eyebrow">QuickBooks ProAdvisor Certified</div>
      <h1>Books You Can<br><em>Actually Trust.</em></h1>
      <p class="hero-sub">
        Local bookkeeping for small businesses — clean books, clear reports,
        and a real person who picks up the phone. No jargon, no surprises.
      </p>
      <div class="hero-actions">
        <a href="#contact" class="btn-primary">Get a Free Consultation</a>
        <a href="#services" class="btn-ghost">See Services</a>
      </div>
    </div>

```
<!-- Rotating badge -->
<div class="hero-badge">
  <svg viewBox="0 0 200 200" fill="none" xmlns="http://www.w3.org/2000/svg">
    <circle cx="100" cy="100" r="90" stroke="rgba(184,145,46,0.25)" stroke-width="1"/>
    <circle cx="100" cy="100" r="78" stroke="rgba(184,145,46,0.2)" stroke-width="1" stroke-dasharray="4 6"/>
    <path id="circlePath" d="M 100,100 m -65,0 a 65,65 0 1,1 130,0 a 65,65 0 1,1 -130,0" fill="none"/>
    <text font-family="DM Sans, sans-serif" font-size="11" fill="rgba(201,168,76,0.7)" font-weight="500" letter-spacing="4">
      <textPath href="#circlePath">BENDIXEN BOOKKEEPING & ADVISORY • </textPath>
    </text>
  </svg>
  <div class="hero-badge-center">
    <span>QB</span>
    <span>ProAdvisor</span>
  </div>
</div>
```

  </section>

  <!-- TRUST BAR -->

  <div class="trust-bar">
    <div class="trust-item">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg>
      QuickBooks ProAdvisor Certified
    </div>
    <div class="trust-divider"></div>
    <div class="trust-item">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><path d="M12 8v4l3 3"/></svg>
      Monthly Reports Delivered On Time
    </div>
    <div class="trust-divider"></div>
    <div class="trust-item">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"/><circle cx="9" cy="7" r="4"/><path d="M23 21v-2a4 4 0 0 0-3-3.87"/><path d="M16 3.13a4 4 0 0 1 0 7.75"/></svg>
      Local & Personal Service
    </div>
    <div class="trust-divider"></div>
    <div class="trust-item">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="3" y="11" width="18" height="11" rx="2" ry="2"/><path d="M7 11V7a5 5 0 0 1 10 0v4"/></svg>
      Secure & Confidential
    </div>
  </div>

  <!-- ABOUT -->

  <section class="about" id="about">
    <div class="about-inner">
      <div class="about-visual reveal">
        <div class="about-card">
          <div class="about-card-name">Caleb Bendixen</div>
          <div class="about-card-title">Owner · QuickBooks ProAdvisor</div>
          <p class="about-card-bio">
            Finance graduate with hands-on training in QuickBooks Online,
            financial reporting, and small business bookkeeping. I started Bendixen Bookkeeping
            because small business owners deserve clean books and someone who actually explains what they mean.
          </p>
          <div class="about-stats">
            <div class="about-stat">
              <div class="about-stat-num">QB</div>
              <div class="about-stat-label">ProAdvisor Certified</div>
            </div>
            <div class="about-stat">
              <div class="about-stat-num">100%</div>
              <div class="about-stat-label">Local & Personalized</div>
            </div>
          </div>

```
    </div>
  </div>
  <div class="about-text reveal">
    <div class="section-label">About Me</div>
    <h2 class="section-title">A Local Bookkeeper<br>Who <em>Actually Cares</em></h2>
    <p>
      I started Bendixen Bookkeeping & Advisory because I kept seeing the same problem:
      <strong>small business owners doing their own books late at night</strong>, stressed about
      whether the numbers were right, and never quite sure where their money was going.
    </p>
    <p>
      With a Finance degree and QuickBooks ProAdvisor certification, I bring
      real expertise — but more importantly, I communicate in plain English. No confusing
      jargon, no mystery invoices, no ghosting.
    </p>
    <p>
      <strong>You focus on running your business. I'll handle the books.</strong>
    </p>
    <a href="#contact" class="btn-primary" style="margin-top:1rem;">Let's Work Together</a>
  </div>
</div>
```

  </section>

  <!-- SERVICES -->

  <section class="services" id="services">
    <div class="services-inner">
      <div class="services-header">
        <div class="reveal">
          <div class="section-label">What I Offer</div>
          <h2 class="section-title">Services Built for<br><em>Small Businesses</em></h2>
        </div>
        <p class="section-sub reveal" style="margin-bottom:0;">
          Everything runs through QuickBooks Online so your books are always organized,
          accessible, and ready for tax season — no scrambling in April.
        </p>
      </div>
      <div class="services-grid">
        <div class="service-card reveal">
          <div class="service-icon">
            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 2L2 7l10 5 10-5-10-5z"/><path d="M2 17l10 5 10-5"/><path d="M2 12l10 5 10-5"/></svg>
          </div>
          <div class="service-name">Transaction Categorization</div>
          <p class="service-desc">Every transaction reviewed, categorized, and organized in QuickBooks so your books are always accurate and audit-ready.</p>

```
    </div>
    <div class="service-card reveal">
      <div class="service-icon">
        <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="22 12 18 12 15 21 9 3 6 12 2 12"/></svg>
      </div>
      <div class="service-name">Account Reconciliation</div>
      <p class="service-desc">Monthly reconciliation of all bank and credit card accounts so your records match reality — no surprises, no discrepancies.</p>
      
    </div>
    <div class="service-card reveal">
      <div class="service-icon">
        <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="3" y="3" width="18" height="18" rx="2"/><path d="M3 9h18M9 21V9"/></svg>
      </div>
      <div class="service-name">Financial Reports</div>
      <p class="service-desc">Every month you'll receive your three core financial statements — <strong>Profit & Loss</strong> (income vs. expenses), <strong>Balance Sheet</strong> (assets, liabilities & equity), and <strong>Statement of Cash Flows</strong> (where your cash actually went). All generated from your clean books in QuickBooks.</p>
      
    </div>
    <div class="service-card reveal">
      <div class="service-icon">
        <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"/><polyline points="14 2 14 8 20 8"/><line x1="16" y1="13" x2="8" y2="13"/><line x1="16" y1="17" x2="8" y2="17"/></svg>
      </div>
      <div class="service-name">Monthly Summary</div>
      <p class="service-desc">A plain-English written narrative explaining what your numbers actually mean — trends, highlights, and anything to watch.</p>
      
    </div>
    <div class="service-card reveal">
      <div class="service-icon">
        <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"/></svg>
      </div>
      <div class="service-name">Quarterly Advisory Call</div>
      <p class="service-desc">A focused 30–60 minute call to review your financials, discuss your numbers, and answer your questions every quarter.</p>
      
    </div>
    <div class="service-card reveal">
      <div class="service-icon">
        <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><path d="M9.09 9a3 3 0 0 1 5.83 1c0 2-3 3-3 3"/><line x1="12" y1="17" x2="12.01" y2="17"/></svg>
      </div>
      <div class="service-name">Catch-Up Bookkeeping</div>
      <p class="service-desc">Behind on your books? I'll get everything caught up and organized from scratch so you start fresh with clean records.</p>
      
    </div>
  </div>
</div>
```

  </section>

  <!-- HOW IT WORKS -->

  <section class="how">
    <div class="how-inner">
      <div class="reveal">
        <div class="section-label">The Process</div>
        <h2 class="section-title">Simple to <em>Get Started</em></h2>
        <p class="section-sub" style="margin:0.8rem auto 0; text-align:center;">
          From first conversation to clean books in under a week.
        </p>
      </div>
      <div class="how-steps">
        <div class="how-step reveal">
          <div class="how-step-num">1</div>
          <div class="how-step-title">Free Consultation</div>
          <p class="how-step-desc">We chat about your business, your current books, and what you need. No pressure, no commitment.</p>
        </div>
        <div class="how-step reveal">
          <div class="how-step-num">2</div>
          <div class="how-step-title">Custom Quote</div>
          <p class="how-step-desc">I calculate your flat monthly fee based on your transaction volume — transparent and straightforward.</p>
        </div>
        <div class="how-step reveal">
          <div class="how-step-num">3</div>
          <div class="how-step-title">Onboarding</div>
          <p class="how-step-desc">Sign the engagement letter, get set up in QuickBooks, and share access. Usually done in a day.</p>
        </div>
        <div class="how-step reveal">
          <div class="how-step-num">4</div>
          <div class="how-step-title">Clean Books Monthly</div>
          <p class="how-step-desc">Sit back. Your books are done and your P&L lands in your inbox every month like clockwork.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- CONTACT -->

  <section class="contact" id="contact">
    <div class="contact-inner">
      <div class="contact-info reveal">
        <div class="section-label">Get In Touch</div>
        <h2 class="section-title">Let's Talk<br><em>About Your Books</em></h2>
        <p>Fill out the form and I'll get back to you within 1 business day. The first conversation is always free — no pressure, no commitment.</p>
        <div class="contact-detail">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
          caleb@bendixenbookkeeping.com
        </div>
        <div class="contact-detail">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07A19.5 19.5 0 0 1 4.69 12 19.79 19.79 0 0 1 1.65 3.37 2 2 0 0 1 3.62 1h3a2 2 0 0 1 2 1.72c.127.96.361 1.903.7 2.81a2 2 0 0 1-.45 2.11L7.91 8.8a16 16 0 0 0 6.29 6.29l.86-.86a2 2 0 0 1 2.11-.45c.907.339 1.85.573 2.81.7A2 2 0 0 1 22 16.92z"/></svg>
          608-669-6162
        </div>
        <div class="contact-detail">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"/><circle cx="12" cy="10" r="3"/></svg>
          Wisconsin Based · Serving Clients Remotely
        </div>
        <div class="contact-detail">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><polyline points="12 6 12 12 16 14"/></svg>
          Response within 1 business day
        </div>
      </div>
      <div class="contact-form reveal">
        <div id="formContent">
          <div class="form-title">Request a Free Consultation</div>
          <div class="form-row">
            <div class="form-group">
              <label>First Name</label>
              <input type="text" placeholder="Jane" id="firstName"/>
            </div>
            <div class="form-group">
              <label>Last Name</label>
              <input type="text" placeholder="Smith" id="lastName"/>
            </div>
          </div>
          <div class="form-group">
            <label>Business Name</label>
            <input type="text" placeholder="Smith Landscaping LLC" id="businessName"/>
          </div>
          <div class="form-group">
            <label>Email Address</label>
            <input type="email" placeholder="jane@yourbusiness.com" id="email"/>
          </div>
          <div class="form-group">
            <label>Current Bookkeeping Situation</label>
            <select id="situation">
              <option value="" disabled selected>Select one...</option>
              <option>I do it myself</option>
              <option>I'm behind / need catch-up</option>
              <option>I have someone but want to switch</option>
              <option>Just starting out</option>
            </select>
          </div>
          <div class="form-group">
            <label>Anything else I should know?</label>
            <textarea placeholder="Tell me a bit about your business, industry, or what you're looking for..." id="message"></textarea>
          </div>
          <button class="btn-primary form-submit" onclick="submitForm()">Send My Request →</button>
        </div>
        <div class="form-success" id="formSuccess">
          <div class="form-success-icon">
            <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"/></svg>
          </div>
          <h3>Message Received!</h3>
          <p>Thanks for reaching out. I'll be in touch within 1 business day to schedule your free consultation.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- FOOTER -->

  <footer>
    <div class="footer-logo">Bendixen Bookkeeping & Advisory</div>
    <div class="footer-copy">
      © 2026 Bendixen Bookkeeping & Advisory LLC · Wisconsin ·
      <a href="mailto:caleb@bendixenbookkeeping.com">caleb@bendixenbookkeeping.com</a>
    </div>
  </footer>

  <script>
    // Scroll reveal
    const reveals = document.querySelectorAll('.reveal');
    const observer = new IntersectionObserver((entries) => {
      entries.forEach((entry, i) => {
        if (entry.isIntersecting) {
          setTimeout(() => entry.target.classList.add('visible'), i * 80);
        }
      });
    }, { threshold: 0.1 });
    reveals.forEach(el => observer.observe(el));

    // Form submit
    function submitForm() {
      const email = document.getElementById('email').value;
      const firstName = document.getElementById('firstName').value;
      if (!firstName || !email) {
        alert('Please fill in your name and email.');
        return;
      }
      document.getElementById('formContent').style.display = 'none';
      document.getElementById('formSuccess').style.display = 'block';
    }

    // Smooth nav
    document.querySelectorAll('a[href^="#"]').forEach(a => {
      a.addEventListener('click', e => {
        const target = document.querySelector(a.getAttribute('href'));
        if (target) {
          e.preventDefault();
          target.scrollIntoView({ behavior: 'smooth', block: 'start' });
        }
      });
    });
  </script>

</body>
</html>
