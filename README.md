<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Shefali Chaudhary — DevOps Engineer</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@400;600;700&family=Outfit:wght@300;400;500;600&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --bg:      #060509;
    --surface: #0a080f;
    --card:    #0e0b16;
    --border:  #1c1430;
    --accent:  #f97316;
    --accent2: #a855f7;
    --accent3: #4ade80;
    --blue:    #38bdf8;
    --text:    #ede8f5;
    --muted:   #4a3a60;
    --sub:     #8b7aa8;
    --glass:   rgba(249,115,22,0.04);
  }

  *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }
  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Outfit', sans-serif;
    font-weight: 300;
    overflow-x: hidden;
    min-height: 100vh;
  }

  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background:
      radial-gradient(ellipse 55% 50% at 15% 15%, rgba(249,115,22,0.05) 0%, transparent 60%),
      radial-gradient(ellipse 50% 55% at 85% 85%, rgba(168,85,247,0.05) 0%, transparent 60%),
      radial-gradient(ellipse 40% 40% at 50% 50%, rgba(74,222,128,0.02) 0%, transparent 60%);
    pointer-events: none;
    z-index: 0;
  }

  body::after {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.03'/%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 0;
    opacity: 0.5;
  }

  .wrap {
    position: relative;
    z-index: 1;
    max-width: 900px;
    margin: 0 auto;
    padding: 0 2rem;
  }

  /* ─── HERO ─── */
  .hero {
    position: relative;
    z-index: 1;
    padding: 6rem 2rem 4rem;
    max-width: 900px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 1fr auto;
    align-items: center;
    gap: 3rem;
  }

  .hero-greeting {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.72rem;
    letter-spacing: 0.3em;
    color: var(--accent);
    text-transform: uppercase;
    margin-bottom: 1rem;
    opacity: 0;
    animation: rise 0.6s 0.1s ease forwards;
    display: flex;
    align-items: center;
    gap: 0.6rem;
  }

  .hero-greeting::before {
    content: '';
    width: 28px;
    height: 1px;
    background: var(--accent);
    display: inline-block;
  }

  .hero-name {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(3.2rem, 8vw, 6rem);
    font-weight: 700;
    line-height: 1;
    letter-spacing: -0.01em;
    color: #fff;
    opacity: 0;
    animation: rise 0.7s 0.2s ease forwards;
  }

  .hero-name .accent-outline {
    color: transparent;
    -webkit-text-stroke: 1.5px var(--accent);
  }

  .hero-role {
    font-family: 'Outfit', sans-serif;
    font-size: 0.88rem;
    font-weight: 400;
    color: var(--sub);
    letter-spacing: 0.08em;
    margin-top: 1rem;
    opacity: 0;
    animation: rise 0.7s 0.35s ease forwards;
  }

  .hero-role span { color: var(--accent2); font-weight: 500; }

  .hero-motto {
    margin-top: 1.5rem;
    padding: 0.9rem 1.25rem;
    border-left: 2px solid var(--accent);
    background: var(--glass);
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.05rem;
    font-style: italic;
    color: var(--sub);
    opacity: 0;
    animation: rise 0.7s 0.5s ease forwards;
  }

  .hero-motto strong {
    color: var(--text);
    font-style: normal;
    font-weight: 600;
  }

  .hero-badges {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
    margin-top: 1.75rem;
    opacity: 0;
    animation: rise 0.7s 0.65s ease forwards;
  }

  .badge {
    display: flex;
    align-items: center;
    gap: 0.4rem;
    padding: 0.35rem 0.75rem;
    border: 1px solid var(--border);
    background: var(--card);
    font-size: 0.68rem;
    letter-spacing: 0.1em;
    color: var(--sub);
    font-family: 'JetBrains Mono', monospace;
    transition: all 0.2s;
    cursor: default;
  }

  .badge:hover { border-color: var(--accent); color: var(--accent); background: rgba(249,115,22,0.05); }

  .badge .dot {
    width: 5px; height: 5px;
    border-radius: 50%;
    background: var(--accent3);
    animation: pulse 2s infinite;
  }

  /* AVATAR */
  .hero-avatar {
    width: 180px; height: 180px;
    border: 1px solid var(--border);
    display: flex; align-items: center; justify-content: center;
    position: relative;
    opacity: 0;
    animation: rise 0.8s 0.4s ease forwards;
    flex-shrink: 0;
  }

  .hero-avatar::before {
    content: '';
    position: absolute;
    inset: -8px;
    border: 1px solid rgba(249,115,22,0.15);
  }

  .hero-avatar::after {
    content: '';
    position: absolute;
    inset: -16px;
    border: 1px solid rgba(249,115,22,0.06);
  }

  .avatar-inner {
    width: 100%; height: 100%;
    background: linear-gradient(135deg, var(--card), var(--surface));
    display: flex; align-items: center; justify-content: center;
    flex-direction: column; gap: 0.3rem;
  }

  .avatar-initials {
    font-family: 'Cormorant Garamond', serif;
    font-size: 3.5rem; font-weight: 700;
    color: var(--accent); line-height: 1;
  }

  .avatar-sub {
    font-size: 0.55rem; letter-spacing: 0.25em;
    color: var(--muted); text-transform: uppercase;
    font-family: 'JetBrains Mono', monospace;
  }

  @keyframes rise {
    from { opacity: 0; transform: translateY(16px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; }
    50%       { opacity: 0.4; }
  }

  /* ─── SECTION ─── */
  .section {
    position: relative; z-index: 1;
    max-width: 900px; margin: 0 auto 3.5rem;
    padding: 0 2rem;
  }

  .sec-head {
    display: flex; align-items: center;
    gap: 1rem; margin-bottom: 1.75rem;
  }

  .sec-num {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.6rem; color: var(--accent);
    letter-spacing: 0.15em; opacity: 0.6;
  }

  .sec-title {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.6rem; font-weight: 600;
    color: var(--text); letter-spacing: 0.02em;
  }

  .sec-line {
    flex: 1; height: 1px;
    background: linear-gradient(90deg, var(--border), transparent);
  }

  /* ─── DIVIDER ─── */
  .divider {
    position: relative; z-index: 1;
    max-width: 900px; margin: 0 auto 3rem;
    padding: 0 2rem;
  }
  .div-inner {
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--border), transparent);
  }

  /* ─── ABOUT GRID ─── */
  .about-grid {
    display: grid; grid-template-columns: 1fr 1fr;
    gap: 1px; background: var(--border);
  }

  .about-item {
    background: var(--card); padding: 1.25rem 1.5rem;
    display: flex; gap: 1rem; align-items: flex-start;
    transition: background 0.2s;
  }

  .about-item:hover { background: var(--surface); }

  .about-icon { font-size: 1rem; flex-shrink: 0; width: 28px; text-align: center; margin-top: 0.1rem; }

  .about-text { font-size: 0.82rem; line-height: 1.7; color: var(--sub); font-weight: 300; }
  .about-text strong { color: var(--text); font-weight: 500; }
  .about-text em { color: var(--accent); font-style: normal; }

  /* ─── BOLLYWOOD BLOCK ─── */
  .bw-table {
    width: 100%; border-collapse: collapse;
    font-size: 0.8rem;
  }

  .bw-table thead tr { border-bottom: 1px solid var(--border); }

  .bw-table th {
    padding: 0.6rem 1rem; text-align: left;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.6rem; letter-spacing: 0.2em;
    color: var(--muted); font-weight: 500;
    text-transform: uppercase;
  }

  .bw-table td {
    padding: 0.9rem 1rem;
    border-bottom: 1px solid rgba(28,20,48,0.8);
    vertical-align: top;
    color: var(--sub);
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.73rem; line-height: 1.6;
  }

  .bw-table td:first-child { color: var(--blue); width: 44%; }
  .bw-table tr:hover td { background: var(--glass); }

  .bw-note {
    margin-top: 1px;
    padding: 1.1rem 1.5rem;
    border-left: 2px solid var(--accent2);
    background: var(--card);
    font-family: 'Outfit', sans-serif;
    font-size: 0.8rem; line-height: 1.8;
    color: var(--sub);
  }

  .bw-note strong { color: var(--accent); }
  .bw-note em { color: var(--text); font-style: normal; font-weight: 500; }

  /* ─── PROJECTS ─── */
  .projects-grid {
    display: grid; grid-template-columns: 1fr 1fr;
    gap: 1px; background: var(--border);
  }

  .project-card {
    background: var(--card); padding: 1.75rem;
    position: relative; overflow: hidden;
    transition: background 0.2s;
  }

  .project-card::before {
    content: '';
    position: absolute; top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent), transparent);
    transform: scaleX(0); transform-origin: left;
    transition: transform 0.3s;
  }

  .project-card:hover { background: var(--surface); }
  .project-card:hover::before { transform: scaleX(1); }

  .proj-status {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.6rem; letter-spacing: 0.2em;
    margin-bottom: 0.75rem;
    display: flex; align-items: center; gap: 0.4rem;
  }

  .sdot { width: 5px; height: 5px; border-radius: 50%; }
  .active .sdot { background: var(--accent3); animation: pulse 2s infinite; }
  .planned .sdot { background: var(--muted); }
  .active { color: var(--accent3); }
  .planned { color: var(--muted); }

  .proj-title {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.15rem; font-weight: 600;
    color: var(--text); margin-bottom: 0.6rem; line-height: 1.3;
  }

  .proj-desc {
    font-size: 0.78rem; color: var(--sub);
    line-height: 1.65; margin-bottom: 1rem;
  }

  .tag-row { display: flex; flex-wrap: wrap; gap: 0.35rem; }

  .tag {
    font-size: 0.62rem; padding: 0.2rem 0.5rem;
    border: 1px solid var(--border); color: var(--muted);
    letter-spacing: 0.08em; font-family: 'JetBrains Mono', monospace;
    transition: border-color 0.2s, color 0.2s;
  }

  .project-card:hover .tag { border-color: rgba(249,115,22,0.3); color: var(--sub); }

  /* ─── TOOLS ─── */
  .tools-cat {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.62rem; letter-spacing: 0.25em;
    color: var(--muted); text-transform: uppercase;
    margin-bottom: 0.85rem;
    display: flex; align-items: center; gap: 0.75rem;
  }

  .tools-cat::after {
    content: ''; flex: 1; height: 1px; background: var(--border);
  }

  .tools-row { display: flex; flex-wrap: wrap; gap: 6px; margin-bottom: 1.5rem; }

  .tool-chip {
    display: flex; align-items: center; gap: 0.4rem;
    padding: 0.4rem 0.8rem;
    border: 1px solid var(--border); background: var(--card);
    font-size: 0.72rem; font-family: 'JetBrains Mono', monospace;
    color: var(--sub); letter-spacing: 0.04em;
    cursor: default; transition: all 0.18s;
    position: relative; overflow: hidden;
  }

  .tool-chip::before {
    content: ''; position: absolute; inset: 0;
    background: linear-gradient(135deg, rgba(249,115,22,0.06), transparent);
    opacity: 0; transition: opacity 0.2s;
  }

  .tool-chip:hover { border-color: var(--accent); color: var(--text); }
  .tool-chip:hover::before { opacity: 1; }

  .t-icon {
    width: 14px; height: 14px; border-radius: 2px;
    display: flex; align-items: center; justify-content: center;
    font-size: 0.65rem; flex-shrink: 0;
  }

  .cloud  .t-icon { background: rgba(56,189,248,0.12); color: var(--blue); }
  .devops .t-icon { background: rgba(249,115,22,0.12); color: var(--accent); }
  .iac    .t-icon { background: rgba(168,85,247,0.12);  color: var(--accent2); }
  .obs    .t-icon { background: rgba(74,222,128,0.12);  color: var(--accent3); }
  .lang   .t-icon { background: rgba(56,189,248,0.08);  color: var(--blue); }
  .sec    .t-icon { background: rgba(249,115,22,0.08);  color: var(--accent); }

  /* ─── ACTIVITY TERMINAL ─── */
  .stack-visual {
    border: 1px solid var(--border);
    background: var(--card); padding: 1.75rem;
    font-family: 'JetBrains Mono', monospace;
  }

  .sv-header {
    display: flex; align-items: center; gap: 0.5rem;
    margin-bottom: 1.5rem; padding-bottom: 0.75rem;
    border-bottom: 1px solid var(--border);
  }

  .sv-dot { width: 8px; height: 8px; border-radius: 50%; }
  .sv-r { background: #ff5f57; }
  .sv-y { background: #febc2e; }
  .sv-g { background: #28c840; }

  .sv-title {
    margin-left: auto; font-size: 0.6rem;
    letter-spacing: 0.2em; color: var(--muted);
  }

  .sv-row {
    display: flex; align-items: center;
    gap: 1rem; margin-bottom: 0.75rem;
    opacity: 0; animation: rise 0.5s forwards;
  }

  .sv-row:nth-child(2) { animation-delay: 0.15s; }
  .sv-row:nth-child(3) { animation-delay: 0.25s; }
  .sv-row:nth-child(4) { animation-delay: 0.35s; }
  .sv-row:nth-child(5) { animation-delay: 0.45s; }
  .sv-row:nth-child(6) { animation-delay: 0.55s; }

  .sv-key { width: 110px; font-size: 0.68rem; color: var(--muted); flex-shrink: 0; }

  .sv-bar {
    flex: 1; height: 4px;
    background: rgba(255,255,255,0.04);
    border-radius: 2px; overflow: hidden;
  }

  .sv-fill {
    height: 100%; border-radius: 2px;
    transform: scaleX(0); transform-origin: left;
    animation: fillBar 1.2s cubic-bezier(0.4,0,0.2,1) forwards;
    animation-delay: 0.4s;
  }

  @keyframes fillBar { to { transform: scaleX(1); } }

  .sv-pct { font-size: 0.65rem; color: var(--accent); width: 32px; text-align: right; flex-shrink: 0; }

  .sv-footer {
    margin-top: 1.25rem; padding-top: 1rem;
    border-top: 1px solid var(--border);
    display: flex; justify-content: space-between;
    font-size: 0.65rem; color: var(--muted);
  }

  .sv-status { display: flex; align-items: center; gap: 0.4rem; color: var(--accent3); }
  .sv-status::before { content: '●'; font-size: 0.5rem; animation: pulse 2s infinite; }

  /* ─── METRICS ─── */
  .metrics-grid {
    display: grid; grid-template-columns: repeat(5, 1fr);
    gap: 1px; background: var(--border);
  }

  .metric {
    background: var(--card); padding: 1.25rem;
    text-align: center; transition: background 0.2s;
  }

  .metric:hover { background: var(--surface); }

  .metric-val {
    font-family: 'Cormorant Garamond', serif;
    font-size: 2.4rem; font-weight: 700;
    color: var(--accent); line-height: 1; display: block;
  }

  .metric-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.58rem; letter-spacing: 0.15em;
    color: var(--muted); margin-top: 0.3rem;
    display: block; text-transform: uppercase;
  }

  /* ─── PIPELINE ─── */
  .pipeline {
    display: flex; gap: 1px; background: var(--border);
    margin-top: 1px;
  }

  .pipe-step {
    flex: 1; background: var(--card); padding: 1rem;
    text-align: center; position: relative;
    overflow: hidden; transition: background 0.2s;
  }

  .pipe-step:hover { background: var(--surface); }

  .pipe-step::after {
    content: '▶';
    position: absolute; right: -1px; top: 50%;
    transform: translateY(-50%);
    font-size: 0.45rem; color: var(--border); z-index: 2;
  }

  .pipe-step:last-child::after { display: none; }

  .pipe-name {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.58rem; letter-spacing: 0.15em;
    color: var(--muted); margin-bottom: 0.4rem; text-transform: uppercase;
  }

  .pipe-val {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.15rem; font-weight: 700;
  }

  /* ─── GOALS ─── */
  .goals-list {
    display: grid; grid-template-columns: 1fr 1fr;
    gap: 1px; background: var(--border);
  }

  .goal-card {
    background: var(--card); padding: 1.25rem 1.5rem;
    position: relative; overflow: hidden;
    transition: background 0.2s;
  }

  .goal-card::before {
    content: '';
    position: absolute; left: 0; top: 0; bottom: 0;
    width: 2px;
    background: linear-gradient(180deg, var(--accent), transparent);
    transform: scaleY(0); transform-origin: top;
    transition: transform 0.3s;
  }

  .goal-card:hover { background: var(--surface); }
  .goal-card:hover::before { transform: scaleY(1); }

  .goal-tag {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.58rem; letter-spacing: 0.2em;
    color: var(--accent); opacity: 0.7;
    margin-bottom: 0.4rem; text-transform: uppercase;
  }

  .goal-text { font-size: 0.82rem; color: var(--sub); line-height: 1.6; }
  .goal-text strong { color: var(--text); font-weight: 500; }

  /* ─── CONNECT ─── */
  .connect-strip {
    display: grid; grid-template-columns: repeat(3, 1fr);
    gap: 1px; background: var(--border);
  }

  .connect-item {
    background: var(--card); padding: 1.5rem 1rem;
    text-align: center; text-decoration: none;
    color: var(--sub); transition: all 0.2s;
    position: relative; overflow: hidden;
    display: flex; flex-direction: column;
    align-items: center; gap: 0.5rem;
  }

  .connect-item::after {
    content: '';
    position: absolute; bottom: 0; left: 0; right: 0;
    height: 2px; background: var(--accent);
    transform: scaleX(0); transition: transform 0.3s;
  }

  .connect-item:hover { background: var(--surface); color: var(--text); }
  .connect-item:hover::after { transform: scaleX(1); }

  .connect-icon-wrap {
    width: 40px; height: 40px;
    border: 1px solid var(--border);
    display: flex; align-items: center; justify-content: center;
    font-size: 0.9rem; transition: border-color 0.2s;
    font-family: 'JetBrains Mono', monospace;
  }

  .connect-item:hover .connect-icon-wrap { border-color: var(--accent); }

  .connect-name {
    font-size: 0.72rem; font-family: 'JetBrains Mono', monospace;
    letter-spacing: 0.08em;
  }

  .connect-sub { font-size: 0.6rem; color: var(--muted); letter-spacing: 0.05em; }

  /* ─── FOOTER ─── */
  .footer {
    position: relative; z-index: 1;
    max-width: 900px; margin: 4rem auto 0;
    padding: 2rem; display: flex;
    align-items: center; justify-content: space-between;
    border-top: 1px solid var(--border);
  }

  .footer-left {
    font-family: 'Cormorant Garamond', serif;
    font-size: 0.95rem; color: var(--muted); font-style: italic;
  }

  .footer-right {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.6rem; letter-spacing: 0.15em;
    color: var(--muted); text-align: right; line-height: 1.8;
  }

  .footer-right .highlight { color: var(--accent); }

  /* ─── RESPONSIVE ─── */
  @media (max-width: 640px) {
    .hero { grid-template-columns: 1fr; gap: 2rem; }
    .hero-avatar { width: 120px; height: 120px; margin: 0 auto; }
    .about-grid, .projects-grid, .goals-list, .metrics-grid, .connect-strip { grid-template-columns: 1fr; }
    .pipeline { flex-direction: column; }
    .footer { flex-direction: column; gap: 1.5rem; text-align: center; }
    .footer-right { text-align: center; }
  }
</style>
</head>
<body>

<!-- ─── HERO ─── -->
<section class="hero">
  <div class="hero-left">
    <div class="hero-greeting">Hello, World — I'm</div>
    <h1 class="hero-name">Shefali<br><span class="accent-outline">Chaudhary</span></h1>
    <p class="hero-role">
      DevOps Engineer &nbsp;·&nbsp; <span>Cloud Architect</span> &nbsp;·&nbsp; SRE
    </p>
    <blockquote class="hero-motto">
      <strong>"The pipeline is my canvas.</strong> The commit is my brushstroke. The cluster is my gallery."
    </blockquote>
    <div class="hero-badges">
      <span class="badge"><span class="dot"></span>ALL SYSTEMS GREEN</span>
      <span class="badge">1.5 YRS EXPERIENCE</span>
      <span class="badge">GITOPS ADVOCATE</span>
      <span class="badge">ZERO MANUAL STEPS</span>
      <span class="badge">UPTIME 99.9%</span>
    </div>
  </div>

  <div class="hero-avatar">
    <div class="avatar-inner">
      <div class="avatar-initials">SC</div>
      <div class="avatar-sub">DevOps · SRE</div>
    </div>
  </div>
</section>

<div class="divider wrap"><div class="div-inner"></div></div>

<!-- ─── ABOUT ─── -->
<section class="section">
  <div class="sec-head">
    <span class="sec-num">01</span>
    <h2 class="sec-title">About Me</h2>
    <span class="sec-line"></span>
  </div>
  <div class="about-grid">
    <div class="about-item">
      <span class="about-icon">🎨</span>
      <p class="about-text"><strong>1.5 years</strong> turning coffee and YAML into infrastructure that actually works — systems that are <em>self-healing</em>, self-scaling, and occasionally self-explaining.</p>
    </div>
    <div class="about-item">
      <span class="about-icon">☁️</span>
      <p class="about-text">I treat infrastructure like art. <strong>Every resource has intention. Every module has elegance.</strong> Every pipeline should be so clean it runs itself at 3am.</p>
    </div>
    <div class="about-item">
      <span class="about-icon">🔄</span>
      <p class="about-text"><strong>Strong CI/CD advocate</strong> — multi-stage pipelines with SAST/DAST scanning and zero-downtime blue-green deploys on Kubernetes. Ship fast. Rollback faster.</p>
    </div>
    <div class="about-item">
      <span class="about-icon">📊</span>
      <p class="about-text">Currently obsessing over <strong>GitOps patterns</strong>, Kubernetes cost visibility, and that rare beautiful moment when the <em>best alert is the one you never receive.</em></p>
    </div>
    <div class="about-item">
      <span class="about-icon">🌍</span>
      <p class="about-text"><strong>Multi-cloud expertise</strong> across AWS & Azure — designing enterprise-grade landing zones with Terraform module libraries, VPC, EKS, RDS, and IAM.</p>
    </div>
    <div class="about-item">
      <span class="about-icon">🎯</span>
      <p class="about-text">Committed to <strong>Cloud-Native & SRE best practices</strong>. If it's not in Git, it doesn't exist. Ephemeral infra only — except the IaC state file.</p>
    </div>
  </div>
</section>

<!-- ─── BOLLYWOOD ─── -->
<section class="section">
  <div class="sec-head">
    <span class="sec-num">02</span>
    <h2 class="sec-title">Zindagi Na Milegi Dobara — A DevOps Reading</h2>
    <span class="sec-line"></span>
  </div>
  <table class="bw-table">
    <thead>
      <tr>
        <th>🎵 The Song Says</th>
        <th>⚙️ The Engineer Does</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>"Seize the moment, life won't come again"</td>
        <td>Ship fast. git push --force-with-lease when the prod window is open.</td>
      </tr>
      <tr>
        <td>"The sea is deep, dive in fearlessly"</td>
        <td>Multi-region. Multi-AZ. Fear no failover — build for it.</td>
      </tr>
      <tr>
        <td>"Leave the shore behind, discover the horizon"</td>
        <td>Migrate to Kubernetes. The monolith is the shore. Microservices are the horizon.</td>
      </tr>
      <tr>
        <td>"Dikhne mein chhoti si lagti hai, par hai badi mushkil"</td>
        <td>A 3-line Terraform change that takes 3 days of plan/destroy/import.</td>
      </tr>
      <tr>
        <td>"We are here today, gone tomorrow"</td>
        <td>Ephemeral infra only. Nothing is permanent. Except the IaC state file.</td>
      </tr>
    </tbody>
  </table>
  <div class="bw-note">
    <strong>Zindagi na milegi dobara</strong> — and neither will your prod deployment window.<br>
    The Bollywood hero jumps into the sea with no plan. The DevOps engineer jumps in with
    <em>Terraform, a rollback strategy, and a Grafana dashboard already open.</em><br>
    Same fearlessness. Better observability.
  </div>
</section>

<!-- ─── PROJECTS ─── -->
<section class="section">
  <div class="sec-head">
    <span class="sec-num">03</span>
    <h2 class="sec-title">Currently Building</h2>
    <span class="sec-line"></span>
  </div>
  <div class="projects-grid">
    <div class="project-card">
      <div class="proj-status active"><span class="sdot"></span>IN PROGRESS</div>
      <div class="proj-title">Jenkins × GitHub Actions<br>Hybrid Pipeline</div>
      <div class="proj-desc">Multi-stage CI/CD with parallel testing, SAST/DAST scanning, and zero-downtime blue-green deploys on Kubernetes.</div>
      <div class="tag-row">
        <span class="tag">Jenkins</span><span class="tag">GitHub Actions</span>
        <span class="tag">SonarQube</span><span class="tag">Trivy</span><span class="tag">Docker</span>
      </div>
    </div>
    <div class="project-card">
      <div class="proj-status active"><span class="sdot"></span>IN PROGRESS</div>
      <div class="proj-title">Terraform AWS<br>Module Library</div>
      <div class="proj-desc">Reusable, opinionated Terraform modules for VPC, EKS, RDS and IAM — enterprise landing zone ready.</div>
      <div class="tag-row">
        <span class="tag">Terraform</span><span class="tag">AWS</span>
        <span class="tag">Terragrunt</span><span class="tag">HCL</span>
      </div>
    </div>
    <div class="project-card">
      <div class="proj-status active"><span class="sdot"></span>IN PROGRESS</div>
      <div class="proj-title">Kubernetes<br>Observability Stack</div>
      <div class="proj-desc">Prometheus + Grafana with custom SLO/SLA alerting and cost-per-namespace dashboards.</div>
      <div class="tag-row">
        <span class="tag">Prometheus</span><span class="tag">Grafana</span>
        <span class="tag">Helm</span><span class="tag">Loki</span>
      </div>
    </div>
    <div class="project-card">
      <div class="proj-status planned"><span class="sdot"></span>PLANNED</div>
      <div class="proj-title">GitOps:<br>ArgoCD + Atlantis</div>
      <div class="proj-desc">Full GitOps workflow — ArgoCD for app delivery, Atlantis for Terraform PRs. Infra changes via pull request only.</div>
      <div class="tag-row">
        <span class="tag">ArgoCD</span><span class="tag">Kubernetes</span><span class="tag">Atlantis</span>
      </div>
    </div>
  </div>
</section>

<!-- ─── TOOLS ─── -->
<section class="section">
  <div class="sec-head">
    <span class="sec-num">04</span>
    <h2 class="sec-title">Technical Arsenal</h2>
    <span class="sec-line"></span>
  </div>

  <div class="tools-cat">☁️ Cloud Infrastructure</div>
  <div class="tools-row">
    <span class="tool-chip cloud"><span class="t-icon">A</span>AWS</span>
    <span class="tool-chip cloud"><span class="t-icon">Az</span>Azure</span>
    <span class="tool-chip cloud"><span class="t-icon">☸</span>Kubernetes</span>
    <span class="tool-chip cloud"><span class="t-icon">⛵</span>Helm</span>
    <span class="tool-chip cloud"><span class="t-icon">⚡</span>EC2 / EKS / ECS</span>
    <span class="tool-chip cloud"><span class="t-icon">🌐</span>Route 53</span>
    <span class="tool-chip cloud"><span class="t-icon">⚖</span>ALB / NLB</span>
    <span class="tool-chip cloud"><span class="t-icon">🌩</span>CloudFront</span>
  </div>

  <div class="tools-cat">⚙️ Infrastructure as Code</div>
  <div class="tools-row">
    <span class="tool-chip iac"><span class="t-icon">T</span>Terraform</span>
    <span class="tool-chip iac"><span class="t-icon">A</span>Ansible</span>
    <span class="tool-chip iac"><span class="t-icon">B</span>Azure Bicep</span>
    <span class="tool-chip iac"><span class="t-icon">Tg</span>Terragrunt</span>
    <span class="tool-chip iac"><span class="t-icon">CF</span>CloudFormation</span>
  </div>

  <div class="tools-cat">🔄 CI/CD & DevSecOps</div>
  <div class="tools-row">
    <span class="tool-chip devops"><span class="t-icon">J</span>Jenkins</span>
    <span class="tool-chip devops"><span class="t-icon">⚙</span>GitHub Actions</span>
    <span class="tool-chip devops"><span class="t-icon">GL</span>GitLab CI</span>
    <span class="tool-chip devops"><span class="t-icon">Az</span>Azure DevOps</span>
    <span class="tool-chip devops"><span class="t-icon">Δ</span>ArgoCD</span>
    <span class="tool-chip sec"><span class="t-icon">Q</span>SonarQube</span>
    <span class="tool-chip sec"><span class="t-icon">🛡</span>Trivy</span>
    <span class="tool-chip sec"><span class="t-icon">⚠</span>OWASP ZAP</span>
  </div>

  <div class="tools-cat">🐳 Containers & Orchestration</div>
  <div class="tools-row">
    <span class="tool-chip devops"><span class="t-icon">🐳</span>Docker</span>
    <span class="tool-chip devops"><span class="t-icon">P</span>Podman</span>
    <span class="tool-chip devops"><span class="t-icon">K</span>Kustomize</span>
    <span class="tool-chip devops"><span class="t-icon">I</span>Istio</span>
  </div>

  <div class="tools-cat">📊 Monitoring & Observability</div>
  <div class="tools-row">
    <span class="tool-chip obs"><span class="t-icon">P</span>Prometheus</span>
    <span class="tool-chip obs"><span class="t-icon">G</span>Grafana</span>
    <span class="tool-chip obs"><span class="t-icon">CW</span>CloudWatch</span>
    <span class="tool-chip obs"><span class="t-icon">EL</span>ELK Stack</span>
    <span class="tool-chip obs"><span class="t-icon">L</span>Loki</span>
  </div>

  <div class="tools-cat">💻 Scripting & Languages</div>
  <div class="tools-row">
    <span class="tool-chip lang"><span class="t-icon">$</span>Bash</span>
    <span class="tool-chip lang"><span class="t-icon">P</span>Python</span>
    <span class="tool-chip lang"><span class="t-icon">H</span>HCL</span>
    <span class="tool-chip lang"><span class="t-icon">Y</span>YAML</span>
    <span class="tool-chip lang"><span class="t-icon">G</span>Go</span>
  </div>
</section>

<!-- ─── ACTIVITY ─── -->
<section class="section">
  <div class="sec-head">
    <span class="sec-num">05</span>
    <h2 class="sec-title">Activity & Metrics</h2>
    <span class="sec-line"></span>
  </div>

  <!-- Metrics strip -->
  <div class="metrics-grid" style="margin-bottom:1px;">
    <div class="metric">
      <span class="metric-val">482</span>
      <span class="metric-label">Commits</span>
    </div>
    <div class="metric">
      <span class="metric-val">26</span>
      <span class="metric-label">Repos</span>
    </div>
    <div class="metric">
      <span class="metric-val">34</span>
      <span class="metric-label">Day Streak 🔥</span>
    </div>
    <div class="metric">
      <span class="metric-val">89</span>
      <span class="metric-label">Pull Requests</span>
    </div>
    <div class="metric">
      <span class="metric-val">47</span>
      <span class="metric-label">Reviews</span>
    </div>
  </div>

  <!-- Terminal -->
  <div class="stack-visual">
    <div class="sv-header">
      <span class="sv-dot sv-r"></span>
      <span class="sv-dot sv-y"></span>
      <span class="sv-dot sv-g"></span>
      <span class="sv-title">shefali@cloud ~ % gh activity --visual</span>
    </div>
    <div class="sv-row">
      <span class="sv-key">Terraform / HCL</span>
      <span class="sv-bar"><span class="sv-fill" style="width:82%; background: linear-gradient(90deg,#f97316,#fb923c);"></span></span>
      <span class="sv-pct">82%</span>
    </div>
    <div class="sv-row">
      <span class="sv-key">YAML / Helm</span>
      <span class="sv-bar"><span class="sv-fill" style="width:75%; background: linear-gradient(90deg,#a855f7,#c084fc);"></span></span>
      <span class="sv-pct">75%</span>
    </div>
    <div class="sv-row">
      <span class="sv-key">Shell / Bash</span>
      <span class="sv-bar"><span class="sv-fill" style="width:68%; background: linear-gradient(90deg,#4ade80,#86efac);"></span></span>
      <span class="sv-pct">68%</span>
    </div>
    <div class="sv-row">
      <span class="sv-key">Python</span>
      <span class="sv-bar"><span class="sv-fill" style="width:55%; background: linear-gradient(90deg,#38bdf8,#7dd3fc);"></span></span>
      <span class="sv-pct">55%</span>
    </div>
    <div class="sv-row">
      <span class="sv-key">Dockerfile</span>
      <span class="sv-bar"><span class="sv-fill" style="width:45%; background: linear-gradient(90deg,#f97316,#a855f7);"></span></span>
      <span class="sv-pct">45%</span>
    </div>
    <div class="sv-footer">
      <div class="sv-status">commit_style → fix: actually fix it this time</div>
      <div>fav: terraform plan → stare → apply → pray</div>
    </div>
  </div>

  <!-- Pipeline -->
  <div class="pipeline">
    <div class="pipe-step">
      <div class="pipe-name">Pipeline</div>
      <div class="pipe-val" style="color:var(--accent3)">PASSING</div>
    </div>
    <div class="pipe-step">
      <div class="pipe-name">Infra</div>
      <div class="pipe-val" style="color:var(--accent3)">GREEN</div>
    </div>
    <div class="pipe-step">
      <div class="pipe-name">Alerts</div>
      <div class="pipe-val" style="color:var(--accent3)">0</div>
    </div>
    <div class="pipe-step">
      <div class="pipe-name">Manual Steps</div>
      <div class="pipe-val" style="color:var(--accent)">0</div>
    </div>
    <div class="pipe-step">
      <div class="pipe-name">Uptime</div>
      <div class="pipe-val" style="color:var(--blue)">99.9%</div>
    </div>
  </div>
</section>

<!-- ─── GOALS ─── -->
<section class="section">
  <div class="sec-head">
    <span class="sec-num">06</span>
    <h2 class="sec-title">Current Focus</h2>
    <span class="sec-line"></span>
  </div>
  <div class="goals-list">
    <div class="goal-card">
      <div class="goal-tag">01 · Automating</div>
      <p class="goal-text">Full <strong>GitOps workflow</strong> with ArgoCD & Atlantis — infra changes via pull request only, no manual interventions.</p>
    </div>
    <div class="goal-card">
      <div class="goal-tag">02 · Observing</div>
      <p class="goal-text"><strong>Kubernetes cost visibility</strong> — SLO/SLA alerting with cost-per-namespace dashboards in Prometheus & Grafana.</p>
    </div>
    <div class="goal-card">
      <div class="goal-tag">03 · Securing</div>
      <p class="goal-text"><strong>DevSecOps pipelines</strong> — integrating Trivy, SonarQube & OWASP ZAP into every CI/CD workflow seamlessly.</p>
    </div>
    <div class="goal-card">
      <div class="goal-tag">04 · Scaling</div>
      <p class="goal-text">Enterprise-grade <strong>Terraform module library</strong> — reusable, opinionated, landing-zone ready for any team.</p>
    </div>
  </div>
</section>

<div class="divider wrap"><div class="div-inner"></div></div>

<!-- ─── CONNECT ─── -->
<section class="section">
  <div class="sec-head">
    <span class="sec-num">07</span>
    <h2 class="sec-title">Let's Connect</h2>
    <span class="sec-line"></span>
  </div>
  <div class="connect-strip">
    <a class="connect-item" href="https://www.linkedin.com/in/shefali-chaudhary-00554b1ba" target="_blank">
      <div class="connect-icon-wrap">in</div>
      <div class="connect-name">LinkedIn</div>
      <div class="connect-sub">shefali-chaudhary</div>
    </a>
    <a class="connect-item" href="mailto:shefalichaudhary649@gmail.com">
      <div class="connect-icon-wrap">@</div>
      <div class="connect-name">Gmail</div>
      <div class="connect-sub">shefalichaudhary649</div>
    </a>
    <a class="connect-item" href="https://github.com/Shefalihub" target="_blank">
      <div class="connect-icon-wrap">🐙</div>
      <div class="connect-name">GitHub</div>
      <div class="connect-sub">Shefalihub</div>
    </a>
  </div>
  <p style="margin-top:1rem; font-size:0.7rem; color:var(--muted); font-family:'JetBrains Mono',monospace; letter-spacing:0.08em;">
    ☁️ &nbsp; Let's talk cloud architecture, pipelines, or why your infra costs too much.
  </p>
</section>

<!-- ─── FOOTER ─── -->
<footer class="footer wrap">
  <div class="footer-left">"The pipeline is my canvas. The commit is my brushstroke."</div>
  <div class="footer-right">
    <span class="highlight">SHEFALI CHAUDHARY</span><br>
    DevOps Engineer · Cloud Architect · SRE<br>
    Built with intention. Deployed with confidence.
  </div>
</footer>

</body>
</html>
