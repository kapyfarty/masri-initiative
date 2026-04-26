# masri-initiative
<!DOCTYPE html>

<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MASRI — مبادرة الطلاب الأكاديميين للبحث الطبي</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700;900&family=Cairo:wght@300;400;600;700;900&family=Cormorant+Garamond:ital,wght@0,300;0,600;1,300&display=swap" rel="stylesheet">
<style>
  :root {
    --navy: #0d2545;
    --navy-mid: #1b3a6b;
    --gold: #c9a84c;
    --gold-light: #e8c97a;
    --gold-pale: #fdf6e3;
    --white: #ffffff;
    --off-white: #f8f6f1;
    --dark: #0a0a0a;
    --mid: #555;
    --light-blue: #eaf1fb;
  }

- { margin:0; padding:0; box-sizing:border-box; }

html { scroll-behavior: smooth; }

body {
font-family: ‘Cairo’, sans-serif;
background: var(–dark);
color: var(–white);
overflow-x: hidden;
}

/* ── SCROLLBAR ── */
::-webkit-scrollbar { width: 4px; }
::-webkit-scrollbar-track { background: var(–navy); }
::-webkit-scrollbar-thumb { background: var(–gold); border-radius: 2px; }

/* ── CURSOR ── */
.cursor {
width: 10px; height: 10px;
background: var(–gold);
border-radius: 50%;
position: fixed;
pointer-events: none;
z-index: 9999;
transition: transform 0.15s ease;
mix-blend-mode: difference;
}
.cursor-ring {
width: 36px; height: 36px;
border: 1px solid var(–gold);
border-radius: 50%;
position: fixed;
pointer-events: none;
z-index: 9998;
transition: all 0.25s ease;
opacity: 0.5;
}

/* ── NAV ── */
nav {
position: fixed; top: 0; left: 0; right: 0;
z-index: 1000;
padding: 20px 60px;
display: flex; align-items: center; justify-content: space-between;
background: rgba(10,10,10,0.85);
backdrop-filter: blur(20px);
border-bottom: 1px solid rgba(201,168,76,0.15);
transition: all 0.3s;
}
nav.scrolled {
padding: 14px 60px;
background: rgba(10,10,10,0.97);
}
.nav-logo {
font-family: ‘Playfair Display’, serif;
font-size: 1.6rem;
font-weight: 900;
letter-spacing: 4px;
color: var(–gold);
text-decoration: none;
}
.nav-logo span { color: var(–white); }
.nav-links {
display: flex; gap: 36px;
list-style: none;
}
.nav-links a {
font-family: ‘Cairo’, sans-serif;
font-size: 0.85rem;
font-weight: 600;
color: rgba(255,255,255,0.7);
text-decoration: none;
letter-spacing: 1px;
transition: color 0.3s;
position: relative;
}
.nav-links a::after {
content: ‘’;
position: absolute; bottom: -4px; right: 0;
width: 0; height: 1px;
background: var(–gold);
transition: width 0.3s;
}
.nav-links a:hover { color: var(–gold); }
.nav-links a:hover::after { width: 100%; }
.nav-cta {
background: var(–gold);
color: var(–dark) !important;
padding: 10px 24px;
border-radius: 2px;
font-weight: 700 !important;
transition: all 0.3s !important;
}
.nav-cta:hover { background: var(–gold-light) !important; transform: translateY(-1px); }
.nav-cta::after { display: none !important; }

/* ── HERO ── */
#hero {
min-height: 100vh;
position: relative;
display: flex; align-items: center; justify-content: center;
overflow: hidden;
}
.hero-bg {
position: absolute; inset: 0;
background:
radial-gradient(ellipse 80% 60% at 20% 50%, rgba(27,58,107,0.4) 0%, transparent 60%),
radial-gradient(ellipse 50% 80% at 80% 30%, rgba(201,168,76,0.08) 0%, transparent 60%),
linear-gradient(135deg, #0a0a0a 0%, #0d1a2e 50%, #0a0a0a 100%);
}
.hero-grid {
position: absolute; inset: 0;
background-image:
linear-gradient(rgba(201,168,76,0.04) 1px, transparent 1px),
linear-gradient(90deg, rgba(201,168,76,0.04) 1px, transparent 1px);
background-size: 60px 60px;
mask-image: radial-gradient(ellipse 80% 80% at 50% 50%, black 30%, transparent 100%);
}
.hero-content {
position: relative; z-index: 2;
text-align: center;
max-width: 900px;
padding: 0 40px;
}
.hero-badge {
display: inline-flex; align-items: center; gap: 10px;
background: rgba(201,168,76,0.1);
border: 1px solid rgba(201,168,76,0.3);
padding: 8px 20px;
border-radius: 2px;
font-size: 0.75rem;
font-weight: 700;
letter-spacing: 3px;
color: var(–gold);
text-transform: uppercase;
margin-bottom: 32px;
animation: fadeDown 1s ease both;
}
.hero-badge::before { content: ‘◆’; font-size: 0.5rem; }
.hero-badge::after { content: ‘◆’; font-size: 0.5rem; }
.hero-title {
font-family: ‘Playfair Display’, serif;
font-size: clamp(4rem, 12vw, 9rem);
font-weight: 900;
line-height: 0.9;
letter-spacing: -2px;
color: var(–white);
animation: fadeUp 1s 0.2s ease both;
margin-bottom: 16px;
}
.hero-title .gold { color: var(–gold); }
.hero-subtitle-ar {
font-size: clamp(1.1rem, 2.5vw, 1.5rem);
font-weight: 300;
color: rgba(255,255,255,0.6);
font-family: ‘Cairo’, sans-serif;
animation: fadeUp 1s 0.4s ease both;
margin-bottom: 8px;
}
.hero-subtitle-en {
font-family: ‘Cormorant Garamond’, serif;
font-size: clamp(0.9rem, 1.8vw, 1.1rem);
font-style: italic;
color: rgba(201,168,76,0.7);
letter-spacing: 2px;
animation: fadeUp 1s 0.5s ease both;
margin-bottom: 48px;
}
.hero-stats {
display: flex; gap: 60px; justify-content: center;
animation: fadeUp 1s 0.6s ease both;
margin-bottom: 52px;
}
.hero-stat { text-align: center; }
.hero-stat-num {
font-family: ‘Playfair Display’, serif;
font-size: 2.2rem;
font-weight: 700;
color: var(–gold);
display: block;
line-height: 1;
}
.hero-stat-label {
font-size: 0.7rem;
color: rgba(255,255,255,0.4);
letter-spacing: 2px;
text-transform: uppercase;
margin-top: 4px;
display: block;
}
.hero-actions {
display: flex; gap: 16px; justify-content: center;
animation: fadeUp 1s 0.8s ease both;
}
.btn-primary {
background: var(–gold);
color: var(–dark);
padding: 16px 40px;
font-family: ‘Cairo’, sans-serif;
font-size: 0.9rem;
font-weight: 700;
letter-spacing: 1px;
border: none;
cursor: pointer;
text-decoration: none;
display: inline-block;
transition: all 0.3s;
border-radius: 2px;
}
.btn-primary:hover { background: var(–gold-light); transform: translateY(-2px); box-shadow: 0 8px 30px rgba(201,168,76,0.3); }
.btn-outline {
border: 1px solid rgba(201,168,76,0.4);
color: var(–gold);
padding: 16px 40px;
font-family: ‘Cairo’, sans-serif;
font-size: 0.9rem;
font-weight: 600;
letter-spacing: 1px;
text-decoration: none;
display: inline-block;
transition: all 0.3s;
border-radius: 2px;
}
.btn-outline:hover { border-color: var(–gold); background: rgba(201,168,76,0.08); transform: translateY(-2px); }
.hero-scroll {
position: absolute; bottom: 40px; left: 50%; transform: translateX(-50%);
display: flex; flex-direction: column; align-items: center; gap: 8px;
animation: fadeUp 1s 1.2s ease both;
}
.hero-scroll span {
font-size: 0.65rem; letter-spacing: 3px; color: rgba(255,255,255,0.3);
text-transform: uppercase;
}
.scroll-line {
width: 1px; height: 50px;
background: linear-gradient(to bottom, var(–gold), transparent);
animation: scrollPulse 2s ease infinite;
}

/* ── SECTION BASE ── */
section { padding: 120px 60px; }
.section-tag {
display: inline-block;
font-size: 0.7rem;
font-weight: 700;
letter-spacing: 4px;
text-transform: uppercase;
color: var(–gold);
margin-bottom: 20px;
position: relative;
padding-right: 40px;
}
.section-tag::before {
content: ‘’;
position: absolute; right: 0; top: 50%;
width: 28px; height: 1px;
background: var(–gold);
}
.section-title {
font-family: ‘Playfair Display’, serif;
font-size: clamp(2rem, 5vw, 3.5rem);
font-weight: 700;
line-height: 1.1;
color: var(–white);
margin-bottom: 16px;
}
.section-title .gold { color: var(–gold); }
.section-desc {
font-size: 1.05rem;
font-weight: 300;
color: rgba(255,255,255,0.55);
line-height: 1.8;
max-width: 600px;
}

/* ── ABOUT ── */
#about {
background: var(–dark);
position: relative;
overflow: hidden;
}
#about::before {
content: ‘MASRI’;
position: absolute; left: -2%; top: 50%; transform: translateY(-50%);
font-family: ‘Playfair Display’, serif;
font-size: 20vw;
font-weight: 900;
color: rgba(201,168,76,0.02);
pointer-events: none;
white-space: nowrap;
}
.about-grid {
display: grid;
grid-template-columns: 1fr 1fr;
gap: 80px;
align-items: center;
max-width: 1200px;
margin: 0 auto;
position: relative; z-index: 1;
}
.about-text .section-desc { max-width: 100%; margin-bottom: 32px; }
.about-quote {
border-right: 3px solid var(–gold);
padding-right: 28px;
margin: 32px 0;
}
.about-quote p {
font-family: ‘Cormorant Garamond’, serif;
font-size: 1.4rem;
font-style: italic;
color: var(–gold-light);
line-height: 1.6;
}
.about-visual {
position: relative;
}
.about-card {
background: rgba(27,58,107,0.3);
border: 1px solid rgba(201,168,76,0.15);
padding: 40px;
border-radius: 4px;
position: relative;
overflow: hidden;
}
.about-card::before {
content: ‘’;
position: absolute; top: 0; right: 0;
width: 120px; height: 120px;
background: radial-gradient(circle, rgba(201,168,76,0.15) 0%, transparent 70%);
}
.about-card-num {
font-family: ‘Playfair Display’, serif;
font-size: 4rem;
font-weight: 900;
color: var(–gold);
display: block;
line-height: 1;
margin-bottom: 8px;
}
.about-card-label {
font-size: 0.85rem;
color: rgba(255,255,255,0.5);
letter-spacing: 2px;
text-transform: uppercase;
}
.about-cards-grid {
display: grid;
grid-template-columns: 1fr 1fr;
gap: 16px;
}

/* ── PILLARS ── */
#pillars {
background: linear-gradient(180deg, var(–dark) 0%, #0d1a2e 50%, var(–dark) 100%);
}
.pillars-header {
max-width: 1200px;
margin: 0 auto 80px;
text-align: center;
}
.pillars-header .section-tag { padding-right: 0; padding-left: 40px; }
.pillars-header .section-tag::before { right: auto; left: 0; }
.pillars-header .section-desc { margin: 0 auto; text-align: center; }
.pillars-grid {
display: grid;
grid-template-columns: repeat(3, 1fr);
gap: 2px;
max-width: 1200px;
margin: 0 auto;
}
.pillar {
background: rgba(13,25,45,0.8);
border: 1px solid rgba(201,168,76,0.08);
padding: 48px 36px;
position: relative;
overflow: hidden;
transition: all 0.4s;
cursor: default;
}
.pillar::before {
content: ‘’;
position: absolute; bottom: 0; left: 0; right: 0;
height: 2px;
background: var(–gold);
transform: scaleX(0);
transition: transform 0.4s;
}
.pillar:hover { background: rgba(27,58,107,0.4); transform: translateY(-4px); border-color: rgba(201,168,76,0.25); }
.pillar:hover::before { transform: scaleX(1); }
.pillar-icon {
font-size: 2rem;
margin-bottom: 20px;
display: block;
}
.pillar-num {
font-family: ‘Playfair Display’, serif;
font-size: 0.7rem;
font-weight: 700;
letter-spacing: 4px;
color: var(–gold);
opacity: 0.5;
margin-bottom: 12px;
display: block;
}
.pillar-title {
font-family: ‘Cairo’, sans-serif;
font-size: 1.2rem;
font-weight: 700;
color: var(–white);
margin-bottom: 12px;
}
.pillar-desc {
font-size: 0.88rem;
color: rgba(255,255,255,0.5);
line-height: 1.8;
}
.pillar-tag {
display: inline-block;
margin-top: 20px;
font-size: 0.65rem;
letter-spacing: 2px;
text-transform: uppercase;
color: var(–gold);
opacity: 0.7;
}

/* ── STRUCTURE ── */
#structure {
background: var(–dark);
}
.structure-inner {
max-width: 1200px;
margin: 0 auto;
display: grid;
grid-template-columns: 1fr 1.6fr;
gap: 80px;
align-items: start;
}
.tier {
display: flex; align-items: flex-start; gap: 20px;
padding: 24px;
border-right: 2px solid rgba(201,168,76,0.1);
margin-bottom: 2px;
transition: all 0.3s;
position: relative;
}
.tier:hover {
border-right-color: var(–gold);
background: rgba(201,168,76,0.03);
}
.tier-num {
font-family: ‘Playfair Display’, serif;
font-size: 0.7rem;
letter-spacing: 3px;
color: var(–gold);
opacity: 0.6;
min-width: 40px;
padding-top: 4px;
}
.tier-content {}
.tier-title {
font-size: 1rem;
font-weight: 700;
color: var(–white);
margin-bottom: 4px;
}
.tier-role {
font-size: 0.8rem;
color: rgba(255,255,255,0.4);
line-height: 1.6;
}
.tier-badge {
position: absolute; left: 24px; top: 50%; transform: translateY(-50%);
font-size: 0.6rem;
background: rgba(201,168,76,0.15);
color: var(–gold);
padding: 3px 10px;
border-radius: 20px;
letter-spacing: 1px;
}

/* ── COMMITTEES ── */
#committees {
background: linear-gradient(180deg, var(–dark) 0%, #050d1a 100%);
}
.committees-header {
max-width: 1200px; margin: 0 auto 60px;
}
.committees-grid {
display: grid;
grid-template-columns: repeat(4, 1fr);
gap: 16px;
max-width: 1200px;
margin: 0 auto;
}
.committee-card {
background: rgba(13,25,45,0.6);
border: 1px solid rgba(201,168,76,0.1);
padding: 28px 24px;
border-radius: 4px;
transition: all 0.3s;
position: relative;
overflow: hidden;
}
.committee-card:hover {
border-color: rgba(201,168,76,0.4);
background: rgba(27,58,107,0.3);
transform: translateY(-4px);
box-shadow: 0 20px 40px rgba(0,0,0,0.4);
}
.committee-card::after {
content: ‘’;
position: absolute; top: 0; right: 0;
width: 60px; height: 60px;
background: radial-gradient(circle, rgba(201,168,76,0.1) 0%, transparent 70%);
}
.committee-icon {
font-size: 1.6rem;
margin-bottom: 14px;
display: block;
}
.committee-title {
font-size: 0.95rem;
font-weight: 700;
color: var(–white);
margin-bottom: 8px;
line-height: 1.3;
}
.committee-desc {
font-size: 0.78rem;
color: rgba(255,255,255,0.45);
line-height: 1.7;
}

/* ── MEMBERSHIP ── */
#membership {
background: var(–dark);
position: relative;
}
.membership-inner {
max-width: 1200px;
margin: 0 auto;
}
.membership-header { margin-bottom: 60px; }
.tiers-track {
display: grid;
grid-template-columns: repeat(4, 1fr);
gap: 0;
position: relative;
}
.tiers-track::before {
content: ‘’;
position: absolute;
top: 48px; right: 12.5%; left: 12.5%;
height: 1px;
background: linear-gradient(to left, var(–gold), transparent 0%, var(–gold) 33%, var(–gold) 66%, transparent 100%);
opacity: 0.3;
z-index: 0;
}
.mem-tier {
text-align: center;
padding: 0 16px;
position: relative;
z-index: 1;
}
.mem-tier-dot {
width: 96px; height: 96px;
border-radius: 50%;
margin: 0 auto 24px;
display: flex; align-items: center; justify-content: center;
font-family: ‘Playfair Display’, serif;
font-size: 1.8rem;
font-weight: 700;
position: relative;
transition: all 0.3s;
}
.mem-tier-dot.t1 { background: rgba(255,255,255,0.06); border: 1px solid rgba(255,255,255,0.15); color: rgba(255,255,255,0.5); }
.mem-tier-dot.t2 { background: rgba(201,168,76,0.1); border: 1px solid rgba(201,168,76,0.3); color: var(–gold); }
.mem-tier-dot.t3 { background: rgba(27,58,107,0.6); border: 2px solid var(–gold); color: var(–gold-light); }
.mem-tier-dot.t4 { background: linear-gradient(135deg, var(–navy-mid), var(–gold)); border: none; color: var(–white); box-shadow: 0 8px 30px rgba(201,168,76,0.4); }
.mem-tier:hover .mem-tier-dot { transform: scale(1.08); }
.mem-tier-name {
font-size: 1rem;
font-weight: 700;
color: var(–white);
margin-bottom: 8px;
}
.mem-tier-req {
font-size: 0.75rem;
color: rgba(255,255,255,0.35);
margin-bottom: 16px;
line-height: 1.5;
}
.mem-tier-perks {
list-style: none;
text-align: right;
}
.mem-tier-perks li {
font-size: 0.75rem;
color: rgba(255,255,255,0.5);
padding: 4px 0;
border-bottom: 1px solid rgba(255,255,255,0.05);
display: flex; align-items: center; gap: 6px;
justify-content: flex-end;
}
.mem-tier-perks li::before { content: ‘◆’; font-size: 0.4rem; color: var(–gold); }

/* ── ADVISORY ── */
#advisory {
background: linear-gradient(135deg, #050d1a 0%, var(–dark) 100%);
position: relative;
overflow: hidden;
}
#advisory::after {
content: ‘’;
position: absolute; top: -50%; right: -20%;
width: 600px; height: 600px;
border-radius: 50%;
background: radial-gradient(circle, rgba(27,58,107,0.3) 0%, transparent 70%);
pointer-events: none;
}
.advisory-inner {
max-width: 1200px; margin: 0 auto;
display: grid; grid-template-columns: 1fr 1fr; gap: 80px;
align-items: center; position: relative; z-index: 1;
}
.advisory-perks { margin-top: 40px; }
.perk-item {
display: flex; align-items: flex-start; gap: 16px;
padding: 20px 0;
border-bottom: 1px solid rgba(201,168,76,0.08);
}
.perk-num {
font-family: ‘Playfair Display’, serif;
font-size: 1.6rem;
font-weight: 700;
color: var(–gold);
opacity: 0.4;
min-width: 36px;
line-height: 1;
}
.perk-title { font-size: 0.9rem; font-weight: 700; color: var(–white); margin-bottom: 4px; }
.perk-desc { font-size: 0.8rem; color: rgba(255,255,255,0.4); line-height: 1.6; }
.advisory-visual {
background: rgba(27,58,107,0.2);
border: 1px solid rgba(201,168,76,0.15);
border-radius: 4px;
padding: 48px;
position: relative;
overflow: hidden;
}
.advisory-visual::before {
content: ‘§’;
position: absolute; bottom: -20px; left: 20px;
font-family: ‘Playfair Display’, serif;
font-size: 12rem;
color: rgba(201,168,76,0.04);
font-weight: 900;
pointer-events: none;
}
.commitment-item {
display: flex; align-items: center; gap: 16px;
padding: 18px 0;
border-bottom: 1px solid rgba(255,255,255,0.06);
}
.commitment-icon { color: var(–gold); font-size: 1.1rem; min-width: 24px; text-align: center; }
.commitment-text { font-size: 0.9rem; color: rgba(255,255,255,0.7); }

/* ── IMPACT ── */
#impact {
background: var(–dark);
text-align: center;
}
.impact-inner { max-width: 1200px; margin: 0 auto; }
.impact-header { text-align: center; margin-bottom: 80px; }
.impact-header .section-tag { padding-right: 0; padding-left: 40px; }
.impact-header .section-tag::before { right: auto; left: 0; }
.impact-header .section-desc { margin: 0 auto; }
.roadmap {
position: relative;
display: grid;
grid-template-columns: repeat(3, 1fr);
gap: 40px;
}
.roadmap::before {
content: ‘’;
position: absolute; top: 40px; right: 16.6%; left: 16.6%;
height: 1px;
background: linear-gradient(to left, transparent, var(–gold), transparent);
opacity: 0.3;
}
.roadmap-item { text-align: center; position: relative; }
.roadmap-dot {
width: 80px; height: 80px;
border-radius: 50%;
margin: 0 auto 28px;
background: rgba(27,58,107,0.5);
border: 2px solid rgba(201,168,76,0.3);
display: flex; align-items: center; justify-content: center;
font-family: ‘Playfair Display’, serif;
font-size: 1.1rem;
font-weight: 700;
color: var(–gold);
transition: all 0.3s;
position: relative; z-index: 1;
}
.roadmap-item:hover .roadmap-dot {
border-color: var(–gold);
background: rgba(201,168,76,0.15);
box-shadow: 0 0 30px rgba(201,168,76,0.2);
}
.roadmap-year { font-size: 0.7rem; letter-spacing: 3px; color: var(–gold); margin-bottom: 8px; opacity: 0.7; }
.roadmap-title { font-size: 1.1rem; font-weight: 700; color: var(–white); margin-bottom: 8px; }
.roadmap-desc { font-size: 0.82rem; color: rgba(255,255,255,0.4); line-height: 1.7; }

/* ── JOIN CTA ── */
#join {
background: linear-gradient(135deg, #0d1a2e 0%, #050d1a 100%);
text-align: center;
position: relative;
overflow: hidden;
}
#join::before {
content: ‘’;
position: absolute; inset: 0;
background:
radial-gradient(ellipse 60% 80% at 50% 50%, rgba(201,168,76,0.06) 0%, transparent 70%);
}
#join::after {
content: ‘’;
position: absolute; inset: 0;
background-image:
linear-gradient(rgba(201,168,76,0.03) 1px, transparent 1px),
linear-gradient(90deg, rgba(201,168,76,0.03) 1px, transparent 1px);
background-size: 40px 40px;
}
.join-inner {
position: relative; z-index: 1;
max-width: 700px; margin: 0 auto;
}
.join-inner .section-title { font-size: clamp(2.5rem, 6vw, 4rem); margin-bottom: 20px; }
.join-inner .section-desc { margin: 0 auto 48px; text-align: center; }
.join-actions { display: flex; gap: 16px; justify-content: center; flex-wrap: wrap; }

/* ── FOOTER ── */
footer {
background: var(–dark);
border-top: 1px solid rgba(201,168,76,0.1);
padding: 60px;
}
.footer-inner {
max-width: 1200px; margin: 0 auto;
display: grid; grid-template-columns: 2fr 1fr 1fr; gap: 60px;
margin-bottom: 48px;
}
.footer-brand {}
.footer-logo {
font-family: ‘Playfair Display’, serif;
font-size: 2rem;
font-weight: 900;
color: var(–gold);
letter-spacing: 4px;
display: block;
margin-bottom: 16px;
}
.footer-tagline {
font-size: 0.85rem;
color: rgba(255,255,255,0.4);
line-height: 1.8;
max-width: 280px;
}
.footer-heading {
font-size: 0.7rem;
font-weight: 700;
letter-spacing: 3px;
text-transform: uppercase;
color: var(–gold);
margin-bottom: 20px;
opacity: 0.8;
}
.footer-links { list-style: none; }
.footer-links li { margin-bottom: 10px; }
.footer-links a {
font-size: 0.85rem;
color: rgba(255,255,255,0.4);
text-decoration: none;
transition: color 0.2s;
}
.footer-links a:hover { color: var(–gold); }
.footer-bottom {
border-top: 1px solid rgba(255,255,255,0.06);
padding-top: 28px;
display: flex; justify-content: space-between; align-items: center;
max-width: 1200px; margin: 0 auto;
}
.footer-copy {
font-size: 0.78rem;
color: rgba(255,255,255,0.25);
}
.footer-affil {
font-size: 0.78rem;
color: rgba(255,255,255,0.25);
text-align: left;
}

/* ── ANIMATIONS ── */
@keyframes fadeDown {
from { opacity: 0; transform: translateY(-20px); }
to { opacity: 1; transform: translateY(0); }
}
@keyframes fadeUp {
from { opacity: 0; transform: translateY(30px); }
to { opacity: 1; transform: translateY(0); }
}
@keyframes scrollPulse {
0%, 100% { opacity: 0.3; transform: scaleY(1); }
50% { opacity: 1; transform: scaleY(1.3); }
}
@keyframes shimmer {
0% { background-position: -200% center; }
100% { background-position: 200% center; }
}
.reveal {
opacity: 0; transform: translateY(40px);
transition: all 0.8s cubic-bezier(0.16, 1, 0.3, 1);
}
.reveal.visible { opacity: 1; transform: translateY(0); }

/* ── MOBILE ── */
@media(max-width: 900px) {
nav { padding: 16px 24px; }
.nav-links { display: none; }
section { padding: 80px 24px; }
.about-grid, .advisory-inner, .structure-inner { grid-template-columns: 1fr; gap: 40px; }
.pillars-grid { grid-template-columns: 1fr; }
.committees-grid { grid-template-columns: 1fr 1fr; }
.tiers-track { grid-template-columns: 1fr 1fr; }
.roadmap { grid-template-columns: 1fr; }
.footer-inner { grid-template-columns: 1fr; gap: 32px; }
.footer-bottom { flex-direction: column; gap: 8px; text-align: center; }
.hero-stats { gap: 32px; }
.about-cards-grid { grid-template-columns: 1fr; }
}
</style>

</head>
<body>

<div class="cursor" id="cursor"></div>
<div class="cursor-ring" id="cursorRing"></div>

<!-- NAV -->

<nav id="navbar">
  <a href="#hero" class="nav-logo">MASRI<span>.</span></a>
  <ul class="nav-links">
    <li><a href="#about">من نحن</a></li>
    <li><a href="#pillars">أهدافنا</a></li>
    <li><a href="#structure">الهيكل</a></li>
    <li><a href="#committees">اللجان</a></li>
    <li><a href="#membership">العضوية</a></li>
    <li><a href="#advisory">المستشارون</a></li>
    <li><a href="#join" class="nav-cta">انضم الآن</a></li>
  </ul>
</nav>

<!-- HERO -->

<section id="hero">
  <div class="hero-bg"></div>
  <div class="hero-grid"></div>
  <div class="hero-content">
    <div class="hero-badge">كلية الطب البشري — جامعة الدلتا</div>
    <h1 class="hero-title">M<span class="gold">A</span>SRI</h1>
    <p class="hero-subtitle-ar">مبادرة الطلاب الأكاديميين للبحث الطبي</p>
    <p class="hero-subtitle-en">Medical Academic Students Research Initiative</p>
    <div class="hero-stats">
      <div class="hero-stat">
        <span class="hero-stat-num">١١</span>
        <span class="hero-stat-label">لجنة متخصصة</span>
      </div>
      <div class="hero-stat">
        <span class="hero-stat-num">ICMJE</span>
        <span class="hero-stat-label">معايير النشر</span>
      </div>
      <div class="hero-stat">
        <span class="hero-stat-num">٣٦٠°</span>
        <span class="hero-stat-label">نظام محاسبة</span>
      </div>
      <div class="hero-stat">
        <span class="hero-stat-num">الأولى</span>
        <span class="hero-stat-label">في مصر</span>
      </div>
    </div>
    <div class="hero-actions">
      <a href="#join" class="btn-primary">انضم إلى MASRI</a>
      <a href="#about" class="btn-outline">اعرف أكثر</a>
    </div>
  </div>
  <div class="hero-scroll">
    <span>scroll</span>
    <div class="scroll-line"></div>
  </div>
</section>

<!-- ABOUT -->

<section id="about">
  <div class="about-grid">
    <div class="about-text reveal">
      <span class="section-tag">من نحن</span>
      <h2 class="section-title">نُحوِّل الطالب من <span class="gold">مستهلك</span> إلى منتج</h2>
      <div class="about-quote">
        <p>"البحث العلمي ليس امتيازاً للأكاديميين — هو حق لكل طالب طب يريد أن يصنع فرقاً."</p>
      </div>
      <p class="section-desc">MASRI هي أول مبادرة بحثية طلابية طبية مستقلة ومنظمة تأسست في كلية الطب البشري بجامعة الدلتا. لا جمعية تقليدية، لا محاضرات فارغة — بنية مؤسسية حقيقية بمعايير دولية وأثر قابل للقياس.</p>
    </div>
    <div class="about-visual reveal">
      <div class="about-cards-grid">
        <div class="about-card">
          <span class="about-card-num">١</span>
          <span class="about-card-label">الأولى من نوعها في الدلتا</span>
        </div>
        <div class="about-card">
          <span class="about-card-num">NAQAAE</span>
          <span class="about-card-label">متوافقة مع معايير الجودة</span>
        </div>
        <div class="about-card">
          <span class="about-card-num">EMSA</span>
          <span class="about-card-label">مسار انتساب دولي</span>
        </div>
        <div class="about-card">
          <span class="about-card-num">٣٩</span>
          <span class="about-card-label">مادة دستورية</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- PILLARS -->

<section id="pillars">
  <div class="pillars-header reveal">
    <span class="section-tag">ما نسعى إليه</span>
    <h2 class="section-title">ستة أعمدة تبني <span class="gold">مستقبلاً</span></h2>
    <p class="section-desc">كل عمود ليس هدفاً نظرياً — بل برنامج عمل فعلي بمخرجات قابلة للقياس والنشر.</p>
  </div>
  <div class="pillars-grid">
    <div class="pillar reveal">
      <span class="pillar-icon">🔬</span>
      <span class="pillar-num">01</span>
      <h3 class="pillar-title">البحث العلمي والنشر</h3>
      <p class="pillar-desc">منهجية بحثية متكاملة من تصميم البروتوكول حتى النشر في مجلات محكّمة بمعايير ICMJE الدولية.</p>
      <span class="pillar-tag">Research & Publication</span>
    </div>
    <div class="pillar reveal">
      <span class="pillar-icon">🌍</span>
      <span class="pillar-num">02</span>
      <h3 class="pillar-title">الفرص الدولية</h3>
      <p class="pillar-desc">قاعدة بيانات حية للمنح والزمالات والبرامج الدولية — انتساب رسمي لـ EMSA وIFMSA وAMEE.</p>
      <span class="pillar-tag">Global Opportunities</span>
    </div>
    <div class="pillar reveal">
      <span class="pillar-icon">🤝</span>
      <span class="pillar-num">03</span>
      <h3 class="pillar-title">الشراكات الاستراتيجية</h3>
      <p class="pillar-desc">مذكرات تفاهم مع المستشفيات وشركات الأدوية والتقنيات الطبية — شراكات حقيقية بعقود رسمية.</p>
      <span class="pillar-tag">Strategic Partnerships</span>
    </div>
    <div class="pillar reveal">
      <span class="pillar-icon">🧠</span>
      <span class="pillar-num">04</span>
      <h3 class="pillar-title">الطب المبني على الأدلة</h3>
      <p class="pillar-desc">Journal Club شهري، تدريب Critical Appraisal، ربط الاستدلال السريري بأحدث الأدلة العلمية.</p>
      <span class="pillar-tag">Evidence-Based Medicine</span>
    </div>
    <div class="pillar reveal">
      <span class="pillar-icon">📱</span>
      <span class="pillar-num">05</span>
      <h3 class="pillar-title">التوعية المجتمعية</h3>
      <p class="pillar-desc">تعريب المحتوى الطبي وإيصاله للمواطن المصري — كتيبات، فيديوهات، إنفوجرافيك بالعربية.</p>
      <span class="pillar-tag">Community Outreach</span>
    </div>
    <div class="pillar reveal">
      <span class="pillar-icon">🤖</span>
      <span class="pillar-num">06</span>
      <h3 class="pillar-title">الذكاء الاصطناعي الطبي</h3>
      <p class="pillar-desc">أبحاث تطبيقية في AI الطبي على البيانات المصرية — الموقع الذي تبحث عنه المنظمات الدولية.</p>
      <span class="pillar-tag">MedTech & AI</span>
    </div>
  </div>
</section>

<!-- STRUCTURE -->

<section id="structure">
  <div class="structure-inner">
    <div class="reveal">
      <span class="section-tag">الحوكمة</span>
      <h2 class="section-title">هيكل بُني <span class="gold">ليدوم</span></h2>
      <p class="section-desc" style="margin-bottom:40px;">نظام حوكمة متعدد المستويات يفصل الإشراف الأكاديمي عن التنفيذ الطلابي — مع محاسبة شفافة وسلطة واضحة لكل طرف.</p>
      <div class="tier">
        <span class="tier-num">T1</span>
        <div class="tier-content">
          <div class="tier-title">المرشد العام</div>
          <div class="tier-role">أعلى سلطة أكاديمية. يصادق على القرارات الكبرى ويمثل MASRI أمام الجامعة.</div>
        </div>
      </div>
      <div class="tier">
        <span class="tier-num">T2</span>
        <div class="tier-content">
          <div class="tier-title">مجلس المستشارين الأكاديميين</div>
          <div class="tier-role">٣–٧ من هيئة التدريس. إشراف بحثي، ضمان جودة، لجنة رقابية مستقلة.</div>
        </div>
      </div>
      <div class="tier">
        <span class="tier-num">T3</span>
        <div class="tier-content">
          <div class="tier-title">الرئيس المؤسس ومجلس الإدارة</div>
          <div class="tier-role">قيادة تنفيذية بنظام نقاط شفاف. الرئيس المؤسس بحماية دستورية دائمة.</div>
        </div>
      </div>
      <div class="tier">
        <span class="tier-num">T4</span>
        <div class="tier-content">
          <div class="tier-title">١١ لجنة متخصصة</div>
          <div class="tier-role">تنفيذ المشاريع، الأبحاث، التوعية، الإعلام، الاستقطاب، اللوجستيات.</div>
        </div>
      </div>
      <div class="tier">
        <span class="tier-num">T5</span>
        <div class="tier-content">
          <div class="tier-title">الأعضاء ومجلس الخريجين</div>
          <div class="tier-role">القاعدة البشرية والشبكة المهنية الدائمة لكل من انتمى إلى MASRI.</div>
        </div>
      </div>
    </div>
    <div class="reveal">
      <div style="background:rgba(13,25,45,0.6);border:1px solid rgba(201,168,76,0.12);padding:48px;border-radius:4px;">
        <h3 style="font-family:'Playfair Display',serif;font-size:1.4rem;color:var(--white);margin-bottom:8px;">نظام المحاسبة بالنقاط</h3>
        <p style="font-size:0.85rem;color:rgba(255,255,255,0.4);margin-bottom:32px;line-height:1.7;">كل منصب — بما في ذلك الرئيس — يخضع لتقييم علني كل فصل دراسي. الشفافية هي الحماية.</p>
        <div style="display:grid;gap:12px;">
          <div style="display:flex;justify-content:space-between;align-items:center;padding:14px 16px;background:rgba(201,168,76,0.06);border-radius:2px;">
            <span style="font-size:0.8rem;color:rgba(255,255,255,0.6);">بحث منشور</span>
            <span style="font-family:'Playfair Display',serif;font-size:1.2rem;color:var(--gold);font-weight:700;">٤٠ نقطة</span>
          </div>
          <div style="display:flex;justify-content:space-between;align-items:center;padding:14px 16px;background:rgba(201,168,76,0.06);border-radius:2px;">
            <span style="font-size:0.8rem;color:rgba(255,255,255,0.6);">تأمين منحة دولية</span>
            <span style="font-family:'Playfair Display',serif;font-size:1.2rem;color:var(--gold);font-weight:700;">٢٥ نقطة</span>
          </div>
          <div style="display:flex;justify-content:space-between;align-items:center;padding:14px 16px;background:rgba(201,168,76,0.06);border-radius:2px;">
            <span style="font-size:0.8rem;color:rgba(255,255,255,0.6);">شراكة جديدة (MOU)</span>
            <span style="font-family:'Playfair Display',serif;font-size:1.2rem;color:var(--gold);font-weight:700;">٢٠ نقطة</span>
          </div>
          <div style="display:flex;justify-content:space-between;align-items:center;padding:14px 16px;background:rgba(201,168,76,0.06);border-radius:2px;">
            <span style="font-size:0.8rem;color:rgba(255,255,255,0.6);">تمثيل خارجي</span>
            <span style="font-family:'Playfair Display',serif;font-size:1.2rem;color:var(--gold);font-weight:700;">١٥ نقطة</span>
          </div>
          <div style="display:flex;justify-content:space-between;align-items:center;padding:14px 16px;background:rgba(201,168,76,0.06);border-radius:2px;">
            <span style="font-size:0.8rem;color:rgba(255,255,255,0.6);">تقرير شهري في الموعد</span>
            <span style="font-family:'Playfair Display',serif;font-size:1.2rem;color:var(--gold);font-weight:700;">٥ نقاط</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- COMMITTEES -->

<section id="committees">
  <div class="committees-header reveal">
    <span class="section-tag">اللجان</span>
    <h2 class="section-title">١١ لجنة — <span class="gold">كل واحدة تصنع أثراً</span></h2>
    <p class="section-desc">لا لجان شكلية. كل لجنة لها مخرجات إلزامية ونظام محاسبة واضح.</p>
  </div>
  <div class="committees-grid">
    <div class="committee-card reveal">
      <span class="committee-icon">📄</span>
      <div class="committee-title">البحث العلمي والنشر</div>
      <div class="committee-desc">من البروتوكول إلى الـ Authorship — منهجية بحثية متكاملة بمعايير ICMJE.</div>
    </div>
    <div class="committee-card reveal">
      <span class="committee-icon">⚖️</span>
      <div class="committee-title">الأخلاقيات البحثية</div>
      <div class="committee-desc">Ethical Approval رسمي لكل بحث — البوابة الأساسية للنشر الدولي.</div>
    </div>
    <div class="committee-card reveal">
      <span class="committee-icon">🧬</span>
      <div class="committee-title">الطب المبني على الأدلة</div>
      <div class="committee-desc">Journal Club شهري وتدريب Critical Appraisal وتوصيل PubMed وCochrane.</div>
    </div>
    <div class="committee-card reveal">
      <span class="committee-icon">🤖</span>
      <div class="committee-title">الذكاء الاصطناعي الطبي</div>
      <div class="committee-desc">Validation studies وتقارير AI الطبي في السياق المصري — مجال نادر دولياً.</div>
    </div>
    <div class="committee-card reveal">
      <span class="committee-icon">🌐</span>
      <div class="committee-title">العلاقات الدولية</div>
      <div class="committee-desc">منح وفرص دولية، انتساب EMSA/IFMSA، حضور رقمي دولي.</div>
    </div>
    <div class="committee-card reveal">
      <span class="committee-icon">🇪🇬</span>
      <div class="committee-title">العلاقات المحلية</div>
      <div class="committee-desc">شراكات مع كليات الطب المصرية والمستشفيات وتمثيل وطني.</div>
    </div>
    <div class="committee-card reveal">
      <span class="committee-icon">💰</span>
      <div class="committee-title">التمويل والشراكات الاستراتيجية</div>
      <div class="committee-desc">منح ASRT، EU Grants، شراكات مدفوعة مع شركات الأدوية والتقنيات.</div>
    </div>
    <div class="committee-card reveal">
      <span class="committee-icon">🗣️</span>
      <div class="committee-title">التوعية المجتمعية والتعريب</div>
      <div class="committee-desc">كتيبات وفيديوهات بالعربية العامية — الطب للناس لا للأكاديميين فقط.</div>
    </div>
    <div class="committee-card reveal">
      <span class="committee-icon">📱</span>
      <div class="committee-title">السوشيال ميديا والجرافيك</div>
      <div class="committee-desc">LinkedIn وInstagram وX — هوية بصرية احترافية وحضور رقمي مؤثر.</div>
    </div>
    <div class="committee-card reveal">
      <span class="committee-icon">📅</span>
      <div class="committee-title">الاجتماعات والتنسيق</div>
      <div class="committee-desc">جدولة دقيقة، أجندات مسبقة، محاضر رسمية في ٢٤ ساعة.</div>
    </div>
    <div class="committee-card reveal" style="grid-column:span 2;">
      <span class="committee-icon">🎯</span>
      <div class="committee-title">الاستقطاب والقبول</div>
      <div class="committee-desc">عملية قبول تنافسية تُقيّم الشغف والإمكانية — لا الأوراق وحدها. قرار القبول النهائي للرئيس المؤسس والمرشد العام.</div>
    </div>
  </div>
</section>

<!-- MEMBERSHIP -->

<section id="membership">
  <div class="membership-inner">
    <div class="membership-header reveal">
      <span class="section-tag">الانتماء</span>
      <h2 class="section-title">أربع درجات من <span class="gold">الانتماء</span></h2>
      <p class="section-desc">كل درجة بمتطلبات واضحة وامتيازات حقيقية. الترقي يعتمد على الإنجاز الفعلي لا الأقدمية.</p>
    </div>
    <div class="tiers-track reveal">
      <div class="mem-tier">
        <div class="mem-tier-dot t1">م</div>
        <div class="mem-tier-name">عضو مشارك</div>
        <div class="mem-tier-req">الحضور وإتمام Orientation Session</div>
        <ul class="mem-tier-perks">
          <li>قائمة الفرص والمنح</li>
          <li>النشرة الإخبارية</li>
          <li>الفعاليات العامة</li>
        </ul>
      </div>
      <div class="mem-tier">
        <div class="mem-tier-dot t2">ف</div>
        <div class="mem-tier-name">عضو فعّال</div>
        <div class="mem-tier-req">مساهمة حقيقية في مشروع واحد</div>
        <ul class="mem-tier-perks">
          <li>شهادة رسمية معتمدة</li>
          <li>الذكر في التقارير</li>
          <li>أولوية في التدريبات</li>
        </ul>
      </div>
      <div class="mem-tier">
        <div class="mem-tier-dot t3">م</div>
        <div class="mem-tier-name">عضو متميز</div>
        <div class="mem-tier-req">نشر أو تمثيل خارجي أو قيادة مشروع</div>
        <ul class="mem-tier-perks">
          <li>Authorship في الأبحاث</li>
          <li>أولوية في المنح</li>
          <li>خطاب توصية رسمي</li>
          <li>تمثيل خارجي</li>
        </ul>
      </div>
      <div class="mem-tier">
        <div class="mem-tier-dot t4">خ</div>
        <div class="mem-tier-name">عضو فخري</div>
        <div class="mem-tier-req">إنجاز استثنائي يُقرره مجلس الإدارة</div>
        <ul class="mem-tier-perks">
          <li>لقب دائم مدى الحياة</li>
          <li>جميع امتيازات المتميز</li>
          <li>مجلس الخريجين الدائم</li>
          <li>سفير MASRI الدائم</li>
        </ul>
      </div>
    </div>
  </div>
</section>

<!-- ADVISORY -->

<section id="advisory">
  <div class="advisory-inner">
    <div class="reveal">
      <span class="section-tag">المجلس الاستشاري</span>
      <h2 class="section-title">دور يستحق <span class="gold">أكاديمياً حقيقياً</span></h2>
      <p class="section-desc">المجلس الاستشاري ليس لجنة شكلية — بل شراكة حقيقية بامتيازات أكاديمية ملموسة ومسؤوليات واضحة.</p>
      <div class="advisory-perks">
        <div class="perk-item">
          <span class="perk-num">١</span>
          <div>
            <div class="perk-title">Co-authorship في الأبحاث</div>
            <div class="perk-desc">اسمك في كل بحث تشرف عليه وفق معايير ICMJE — نشر حقيقي بمجلات محكّمة.</div>
          </div>
        </div>
        <div class="perk-item">
          <span class="perk-num">٢</span>
          <div>
            <div class="perk-title">شهادة مستشار أكاديمي معتمدة</div>
            <div class="perk-desc">وثيقة رسمية باسم MASRI قابلة للإدراج في السيرة الذاتية والملفات الدولية.</div>
          </div>
        </div>
        <div class="perk-item">
          <span class="perk-num">٣</span>
          <div>
            <div class="perk-title">حضور دولي دائم</div>
            <div class="perk-desc">اسمك في كل المراسلات والانتسابات الدولية — EMSA, IFMSA, AMEE.</div>
          </div>
        </div>
        <div class="perk-item">
          <span class="perk-num">٤</span>
          <div>
            <div class="perk-title">أولوية في التمويل البحثي</div>
            <div class="perk-desc">أولوية في الاستفادة من أي منح أو تمويل تحصل عليه MASRI.</div>
          </div>
        </div>
      </div>
    </div>
    <div class="advisory-visual reveal">
      <h3 style="font-family:'Playfair Display',serif;font-size:1.3rem;color:var(--white);margin-bottom:8px;">الالتزامات السنوية</h3>
      <p style="font-size:0.82rem;color:rgba(255,255,255,0.4);margin-bottom:28px;">الحد الأدنى المطلوب — لا أكثر.</p>
      <div class="commitment-item">
        <span class="commitment-icon">📅</span>
        <span class="commitment-text">اجتماع فصلي واحد (٤ اجتماعات سنوياً)</span>
      </div>
      <div class="commitment-item">
        <span class="commitment-icon">💬</span>
        <span class="commitment-text">الرد على استفسارات البحث خلال ١٤ يوماً</span>
      </div>
      <div class="commitment-item">
        <span class="commitment-icon">📋</span>
        <span class="commitment-text">مراجعة بروتوكول بحثي واحد كل ٦ أشهر</span>
      </div>
      <div class="commitment-item">
        <span class="commitment-icon">🎓</span>
        <span class="commitment-text">محاضرة أو ورشة عمل واحدة سنوياً</span>
      </div>
      <div style="margin-top:32px;padding:20px;background:rgba(201,168,76,0.06);border:1px solid rgba(201,168,76,0.15);border-radius:2px;">
        <p style="font-size:0.8rem;color:rgba(255,255,255,0.5);line-height:1.7;font-style:italic;">يُصدر تقرير الأداء السنوي علناً — الشفافية المتبادلة تُعزز المصداقية الجماعية.</p>
      </div>
    </div>
  </div>
</section>

<!-- IMPACT -->

<section id="impact">
  <div class="impact-inner">
    <div class="impact-header reveal">
      <span class="section-tag">الرؤية</span>
      <h2 class="section-title">خارطة طريق <span class="gold">ثلاث سنوات</span></h2>
      <p class="section-desc">أهداف واضحة، قابلة للقياس، مبنية على التراكم لا العشوائية.</p>
    </div>
    <div class="roadmap">
      <div class="roadmap-item reveal">
        <div class="roadmap-dot">Y1</div>
        <div class="roadmap-year">السنة الأولى</div>
        <div class="roadmap-title">التأسيس والتفعيل</div>
        <div class="roadmap-desc">اعتراف رسمي، تشكيل اللجان، أول بروتوكول بحثي مكتمل، إطلاق LinkedIn، أول Journal Club.</div>
      </div>
      <div class="roadmap-item reveal">
        <div class="roadmap-dot">Y2</div>
        <div class="roadmap-year">السنة الثانية</div>
        <div class="roadmap-title">الإنتاج والانتشار</div>
        <div class="roadmap-desc">أول مخطوطة للنشر الدولي، طلب انتساب EMSA/IFMSA، شراكة مع مستشفى، أول مؤتمر خارجي.</div>
      </div>
      <div class="roadmap-item reveal">
        <div class="roadmap-dot">Y3</div>
        <div class="roadmap-year">السنة الثالثة</div>
        <div class="roadmap-title">الاعتراف والتوسع</div>
        <div class="roadmap-desc">MASRI معترف بها دولياً، نموذج يُحتذى على مستوى مصر، أبحاث منشورة بأسماء طلاب الدلتا.</div>
      </div>
    </div>
  </div>
</section>

<!-- JOIN CTA -->

<section id="join">
  <div class="join-inner">
    <div class="reveal">
      <span class="section-tag" style="padding-right:0;padding-left:40px;">الانضمام</span>
      <h2 class="section-title">مكانك في <span class="gold">MASRI</span> ينتظرك</h2>
      <p class="section-desc">لا نقبل أي شخص — نقبل من يملك شغفاً حقيقياً وإرادة للبناء. إذا كنت مستعداً لصنع فرق حقيقي، نحن جاهزون.</p>
      <div class="join-actions">
        <a href="mailto:masri@deltauni.edu.eg" class="btn-primary">تقدم بطلب الانضمام</a>
        <a href="#about" class="btn-outline">اعرف شروط القبول</a>
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->

<footer>
  <div class="footer-inner">
    <div class="footer-brand">
      <span class="footer-logo">MASRI</span>
      <p class="footer-tagline">مبادرة الطلاب الأكاديميين للبحث الطبي — كلية الطب البشري، جامعة الدلتا للعلوم والتكنولوجيا.</p>
      <p style="margin-top:16px;font-size:0.75rem;color:rgba(255,255,255,0.2);letter-spacing:2px;">Medical Academic Students Research Initiative</p>
    </div>
    <div>
      <div class="footer-heading">روابط سريعة</div>
      <ul class="footer-links">
        <li><a href="#about">من نحن</a></li>
        <li><a href="#pillars">أهدافنا</a></li>
        <li><a href="#structure">الهيكل التنظيمي</a></li>
        <li><a href="#committees">اللجان</a></li>
        <li><a href="#membership">العضوية</a></li>
        <li><a href="#advisory">المجلس الاستشاري</a></li>
      </ul>
    </div>
    <div>
      <div class="footer-heading">الانتساب الدولي</div>
      <ul class="footer-links">
        <li><a href="#">EMSA — الاتحاد الأوروبي لطلاب الطب</a></li>
        <li><a href="#">IFMSA — الاتحاد الدولي</a></li>
        <li><a href="#">AMEE — تعليم طبي دولي</a></li>
        <li><a href="#">NAQAAE — جودة التعليم المصري</a></li>
        <li><a href="#">ICMJE — معايير النشر الدولية</a></li>
      </ul>
    </div>
  </div>
  <div class="footer-bottom">
    <p class="footer-copy">© 2024 MASRI — جميع الحقوق محفوظة. كلية الطب البشري، جامعة الدلتا.</p>
    <p class="footer-affil">Founding President: _______________ | General Mentor: Prof. Ahmed Ammar</p>
  </div>
</footer>

<script>
  // Custom cursor
  const cursor = document.getElementById('cursor');
  const ring = document.getElementById('cursorRing');
  let mx=0,my=0,rx=0,ry=0;
  document.addEventListener('mousemove',e=>{
    mx=e.clientX; my=e.clientY;
    cursor.style.left=mx-5+'px'; cursor.style.top=my-5+'px';
  });
  function animRing(){
    rx+=(mx-rx-18)*0.12; ry+=(my-ry-18)*0.12;
    ring.style.left=rx+'px'; ring.style.top=ry+'px';
    requestAnimationFrame(animRing);
  }
  animRing();
  document.querySelectorAll('a,button,.pillar,.committee-card').forEach(el=>{
    el.addEventListener('mouseenter',()=>{ ring.style.transform='scale(2)'; ring.style.opacity='0.8'; });
    el.addEventListener('mouseleave',()=>{ ring.style.transform='scale(1)'; ring.style.opacity='0.5'; });
  });

  // Navbar scroll
  const nav = document.getElementById('navbar');
  window.addEventListener('scroll',()=>{
    nav.classList.toggle('scrolled', window.scrollY > 60);
  });

  // Reveal on scroll
  const reveals = document.querySelectorAll('.reveal');
  const observer = new IntersectionObserver(entries=>{
    entries.forEach((e,i)=>{
      if(e.isIntersecting){
        setTimeout(()=> e.target.classList.add('visible'), i*80);
      }
    });
  },{threshold:0.1,rootMargin:'0px 0px -60px 0px'});
  reveals.forEach(el=> observer.observe(el));

  // Smooth nav highlight
  const sections = document.querySelectorAll('section[id]');
  const navLinks = document.querySelectorAll('.nav-links a');
  window.addEventListener('scroll',()=>{
    let cur='';
    sections.forEach(s=>{ if(window.scrollY>=s.offsetTop-120) cur=s.getAttribute('id'); });
    navLinks.forEach(a=>{
      a.style.color = a.getAttribute('href')==='#'+cur ? 'var(--gold)' : '';
    });
  });
</script>

</body>
</html>
