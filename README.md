<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Mir Anwara — IT Business Analyst Portfolio</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;900&family=DM+Sans:wght@300;400;500;600&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --navy: #0F2241;
    --navy-mid: #1B3565;
    --gold: #C9A84C;
    --gold-light: #E8C96A;
    --teal: #0E8A8A;
    --teal-light: #12AAAA;
    --white: #FFFFFF;
    --off-white: #F8F9FC;
    --light: #EEF2F8;
    --mid: #3D4F6B;
    --soft: #8296B0;
    --text: #1E2D42;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'DM Sans', sans-serif;
    background: var(--off-white);
    color: var(--text);
    overflow-x: hidden;
  }

  /* ── NAV ── */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    background: rgba(15,34,65,0.97);
    backdrop-filter: blur(12px);
    display: flex; align-items: center; justify-content: space-between;
    padding: 0 48px;
    height: 64px;
    border-bottom: 1px solid rgba(201,168,76,0.25);
  }
  .nav-logo {
    font-family: 'Playfair Display', serif;
    font-size: 1.2rem; color: var(--gold); letter-spacing: 0.5px;
  }
  .nav-links { display: flex; gap: 32px; }
  .nav-links a {
    color: rgba(255,255,255,0.7); text-decoration: none;
    font-size: 0.85rem; font-weight: 500; letter-spacing: 0.5px;
    text-transform: uppercase; transition: color 0.2s;
  }
  .nav-links a:hover { color: var(--gold); }

  /* ── HERO ── */
  .hero {
    min-height: 100vh;
    background: linear-gradient(135deg, var(--navy) 0%, var(--navy-mid) 60%, #0E3D5C 100%);
    display: flex; align-items: center;
    padding: 100px 80px 80px;
    position: relative; overflow: hidden;
  }
  .hero::before {
    content: '';
    position: absolute; top: -200px; right: -200px;
    width: 700px; height: 700px;
    background: radial-gradient(circle, rgba(201,168,76,0.08) 0%, transparent 70%);
    border-radius: 50%;
  }
  .hero::after {
    content: '';
    position: absolute; bottom: -100px; left: 30%;
    width: 400px; height: 400px;
    background: radial-gradient(circle, rgba(14,138,138,0.08) 0%, transparent 70%);
    border-radius: 50%;
  }
  .hero-content { position: relative; z-index: 2; max-width: 800px; }
  .hero-tag {
    display: inline-block;
    background: rgba(201,168,76,0.15);
    border: 1px solid rgba(201,168,76,0.4);
    color: var(--gold-light);
    font-size: 0.75rem; font-weight: 600;
    letter-spacing: 2px; text-transform: uppercase;
    padding: 6px 16px; border-radius: 20px;
    margin-bottom: 28px;
    animation: fadeUp 0.6s ease forwards;
  }
  .hero h1 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(3rem, 6vw, 5.5rem);
    font-weight: 900; line-height: 1.05;
    color: var(--white);
    margin-bottom: 8px;
    animation: fadeUp 0.7s ease forwards;
  }
  .hero h1 span { color: var(--gold); }
  .hero-title {
    font-size: 1.1rem; font-weight: 400;
    color: rgba(255,255,255,0.65);
    margin-bottom: 28px; letter-spacing: 0.3px;
    animation: fadeUp 0.8s ease forwards;
  }
  .hero-desc {
    font-size: 1rem; line-height: 1.8;
    color: rgba(255,255,255,0.55);
    max-width: 580px; margin-bottom: 40px;
    animation: fadeUp 0.9s ease forwards;
  }
  .hero-badges {
    display: flex; flex-wrap: wrap; gap: 10px;
    margin-bottom: 44px;
    animation: fadeUp 1s ease forwards;
  }
  .badge {
    background: rgba(255,255,255,0.06);
    border: 1px solid rgba(255,255,255,0.12);
    color: rgba(255,255,255,0.75);
    padding: 6px 14px; border-radius: 6px;
    font-size: 0.8rem; font-weight: 500;
    font-family: 'DM Mono', monospace;
  }
  .hero-cta { display: flex; gap: 16px; flex-wrap: wrap; animation: fadeUp 1.1s ease forwards; }
  .btn-primary {
    background: var(--gold);
    color: var(--navy); font-weight: 700;
    padding: 14px 28px; border-radius: 8px;
    text-decoration: none; font-size: 0.9rem;
    transition: all 0.2s; letter-spacing: 0.3px;
  }
  .btn-primary:hover { background: var(--gold-light); transform: translateY(-2px); box-shadow: 0 8px 24px rgba(201,168,76,0.3); }
  .btn-outline {
    background: transparent;
    border: 1px solid rgba(255,255,255,0.25);
    color: rgba(255,255,255,0.8);
    padding: 14px 28px; border-radius: 8px;
    text-decoration: none; font-size: 0.9rem;
    transition: all 0.2s;
  }
  .btn-outline:hover { border-color: var(--gold); color: var(--gold); }

  /* ── METRICS STRIP ── */
  .metrics {
    background: var(--navy);
    padding: 40px 80px;
    display: grid; grid-template-columns: repeat(4, 1fr);
    border-bottom: 1px solid rgba(201,168,76,0.2);
  }
  .metric-item {
    text-align: center; padding: 20px;
    border-right: 1px solid rgba(255,255,255,0.06);
  }
  .metric-item:last-child { border-right: none; }
  .metric-val {
    font-family: 'Playfair Display', serif;
    font-size: 2.8rem; font-weight: 700;
    color: var(--gold); line-height: 1;
    margin-bottom: 8px;
  }
  .metric-label { font-size: 0.8rem; color: rgba(255,255,255,0.45); letter-spacing: 0.5px; text-transform: uppercase; }

  /* ── SECTIONS ── */
  section { padding: 90px 80px; }
  .section-label {
    font-size: 0.72rem; font-weight: 600; letter-spacing: 3px;
    text-transform: uppercase; color: var(--teal);
    margin-bottom: 12px;
  }
  .section-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(1.8rem, 3vw, 2.8rem);
    font-weight: 700; color: var(--navy);
    margin-bottom: 48px; line-height: 1.2;
  }
  .section-title span { color: var(--gold); }

  /* ── ABOUT ── */
  .about { background: var(--white); }
  .about-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 64px; align-items: start; }
  .about-text { font-size: 1rem; line-height: 1.9; color: var(--mid); }
  .about-text p { margin-bottom: 20px; }
  .about-text strong { color: var(--navy); }
  .about-skills h4 { font-size: 0.75rem; letter-spacing: 2px; text-transform: uppercase; color: var(--soft); margin-bottom: 16px; margin-top: 32px; }
  .about-skills h4:first-child { margin-top: 0; }
  .skill-tags { display: flex; flex-wrap: wrap; gap: 8px; }
  .skill-tag {
    background: var(--light);
    color: var(--navy); font-size: 0.8rem; font-weight: 500;
    padding: 6px 12px; border-radius: 6px;
    border: 1px solid rgba(15,34,65,0.08);
    font-family: 'DM Mono', monospace;
  }
  .skill-tag.gold { background: rgba(201,168,76,0.1); border-color: rgba(201,168,76,0.3); color: #7A5C1E; }
  .skill-tag.teal { background: rgba(14,138,138,0.08); border-color: rgba(14,138,138,0.25); color: #0A5E5E; }

  /* ── PROJECTS ── */
  .projects { background: var(--off-white); }
  .projects-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 28px; }
  .project-card {
    background: var(--white);
    border-radius: 12px;
    border: 1px solid rgba(15,34,65,0.08);
    overflow: hidden;
    transition: all 0.3s;
    position: relative;
  }
  .project-card:hover { transform: translateY(-6px); box-shadow: 0 20px 48px rgba(15,34,65,0.12); border-color: var(--gold); }
  .project-card-top {
    height: 6px;
    background: linear-gradient(90deg, var(--navy), var(--teal));
  }
  .project-card:nth-child(2) .project-card-top { background: linear-gradient(90deg, var(--teal), var(--gold)); }
  .project-card:nth-child(3) .project-card-top { background: linear-gradient(90deg, var(--gold), var(--navy)); }
  .project-body { padding: 28px; }
  .project-num {
    font-family: 'DM Mono', monospace;
    font-size: 0.7rem; color: var(--soft);
    letter-spacing: 2px; margin-bottom: 12px;
  }
  .project-title {
    font-family: 'Playfair Display', serif;
    font-size: 1.15rem; font-weight: 700;
    color: var(--navy); margin-bottom: 12px; line-height: 1.3;
  }
  .project-desc { font-size: 0.88rem; line-height: 1.7; color: var(--mid); margin-bottom: 20px; }
  .project-tools { display: flex; flex-wrap: wrap; gap: 6px; margin-bottom: 24px; }
  .tool-chip {
    background: var(--light); color: var(--navy);
    font-size: 0.72rem; font-weight: 600;
    padding: 4px 10px; border-radius: 4px;
    font-family: 'DM Mono', monospace;
  }
  .project-outcome {
    background: rgba(14,138,138,0.06);
    border-left: 3px solid var(--teal);
    padding: 10px 14px; border-radius: 0 6px 6px 0;
    font-size: 0.82rem; color: var(--mid); margin-bottom: 20px;
  }
  .project-outcome strong { color: var(--teal); }
  .project-links { display: flex; gap: 12px; }
  .proj-link {
    font-size: 0.8rem; font-weight: 600;
    text-decoration: none; padding: 8px 16px;
    border-radius: 6px; transition: all 0.2s;
  }
  .proj-link.github { background: var(--navy); color: var(--white); }
  .proj-link.github:hover { background: var(--navy-mid); }
  .proj-link.kaggle { background: rgba(14,138,138,0.1); color: var(--teal); border: 1px solid rgba(14,138,138,0.25); }
  .proj-link.kaggle:hover { background: var(--teal); color: var(--white); }

  /* ── EXPERIENCE ── */
  .experience { background: var(--white); }
  .exp-timeline { position: relative; padding-left: 32px; }
  .exp-timeline::before {
    content: ''; position: absolute;
    left: 0; top: 8px; bottom: 8px;
    width: 2px; background: linear-gradient(to bottom, var(--navy), var(--teal), rgba(201,168,76,0.3));
  }
  .exp-item { position: relative; margin-bottom: 48px; }
  .exp-item::before {
    content: ''; position: absolute;
    left: -38px; top: 6px;
    width: 12px; height: 12px; border-radius: 50%;
    background: var(--gold); border: 3px solid var(--white);
    box-shadow: 0 0 0 2px var(--navy);
  }
  .exp-dates { font-family: 'DM Mono', monospace; font-size: 0.75rem; color: var(--teal); margin-bottom: 6px; }
  .exp-title { font-size: 1.05rem; font-weight: 700; color: var(--navy); margin-bottom: 4px; }
  .exp-company { font-size: 0.88rem; color: var(--soft); margin-bottom: 14px; }
  .exp-bullets { list-style: none; }
  .exp-bullets li {
    font-size: 0.9rem; line-height: 1.7; color: var(--mid);
    padding-left: 18px; margin-bottom: 8px; position: relative;
  }
  .exp-bullets li::before { content: '▸'; position: absolute; left: 0; color: var(--gold); }

  /* ── PLATFORMS ── */
  .platforms { background: var(--navy); }
  .platforms .section-title { color: var(--white); }
  .platforms .section-label { color: var(--gold); }
  .platform-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 24px; }
  .platform-card {
    background: rgba(255,255,255,0.04);
    border: 1px solid rgba(255,255,255,0.1);
    border-radius: 12px; padding: 32px;
    text-align: center; transition: all 0.3s;
  }
  .platform-card:hover { background: rgba(255,255,255,0.08); border-color: var(--gold); transform: translateY(-4px); }
  .platform-icon { font-size: 2.5rem; margin-bottom: 16px; }
  .platform-name { font-family: 'Playfair Display', serif; font-size: 1.3rem; color: var(--gold); margin-bottom: 10px; }
  .platform-desc { font-size: 0.85rem; color: rgba(255,255,255,0.5); line-height: 1.7; margin-bottom: 20px; }
  .platform-link {
    display: inline-block;
    border: 1px solid rgba(201,168,76,0.4);
    color: var(--gold); font-size: 0.8rem; font-weight: 600;
    padding: 8px 20px; border-radius: 6px; text-decoration: none;
    transition: all 0.2s;
  }
  .platform-link:hover { background: var(--gold); color: var(--navy); }

  /* ── CONTACT ── */
  .contact { background: var(--off-white); text-align: center; }
  .contact-box {
    max-width: 640px; margin: 0 auto;
    background: var(--white); border-radius: 16px;
    padding: 56px 48px;
    border: 1px solid rgba(15,34,65,0.08);
    box-shadow: 0 8px 32px rgba(15,34,65,0.06);
  }
  .contact-box h3 {
    font-family: 'Playfair Display', serif;
    font-size: 1.8rem; color: var(--navy); margin-bottom: 14px;
  }
  .contact-box p { font-size: 0.95rem; color: var(--mid); line-height: 1.7; margin-bottom: 36px; }
  .contact-links { display: flex; justify-content: center; gap: 16px; flex-wrap: wrap; }
  .contact-link {
    display: flex; align-items: center; gap: 8px;
    padding: 12px 20px; border-radius: 8px;
    text-decoration: none; font-size: 0.88rem; font-weight: 600;
    transition: all 0.2s;
  }
  .contact-link.email { background: var(--navy); color: var(--white); }
  .contact-link.linkedin { background: #0A66C2; color: var(--white); }
  .contact-link.github-c { background: #1B1F23; color: var(--white); }
  .contact-link:hover { transform: translateY(-2px); opacity: 0.9; }
  .open-badge {
    display: inline-flex; align-items: center; gap: 8px;
    background: rgba(14,138,138,0.1); color: var(--teal);
    border: 1px solid rgba(14,138,138,0.25);
    padding: 8px 18px; border-radius: 20px;
    font-size: 0.8rem; font-weight: 600;
    margin-bottom: 28px;
  }
  .open-dot { width: 7px; height: 7px; border-radius: 50%; background: var(--teal); animation: pulse 1.5s infinite; }

  /* ── FOOTER ── */
  footer {
    background: var(--navy); color: rgba(255,255,255,0.35);
    text-align: center; padding: 28px;
    font-size: 0.8rem;
    border-top: 1px solid rgba(201,168,76,0.15);
  }
  footer span { color: var(--gold); }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to   { opacity: 1; transform: translateY(0); }
  }
  @keyframes pulse {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.4; }
  }

  /* ── RESPONSIVE ── */
  @media (max-width: 900px) {
    nav { padding: 0 24px; }
    .nav-links { gap: 18px; }
    .hero { padding: 100px 24px 60px; }
    .metrics { grid-template-columns: repeat(2,1fr); padding: 32px 24px; }
    section { padding: 60px 24px; }
    .about-grid { grid-template-columns: 1fr; gap: 36px; }
    .projects-grid { grid-template-columns: 1fr; }
    .platform-grid { grid-template-columns: 1fr; }
    .contact-box { padding: 36px 24px; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo">Mir Anwara</div>
  <div class="nav-links">
    <a href="#about">About</a>
    <a href="#projects">Projects</a>
    <a href="#experience">Experience</a>
    <a href="#platforms">Profiles</a>
    <a href="#contact">Contact</a>
  </div>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-content">
    <div class="hero-tag">🚀 Open to Work — India & Gulf</div>
    <h1>Mir<br><span>Anwara</span></h1>
    <div class="hero-title">IT Business Analyst &nbsp;·&nbsp; BFSI Domain Specialist &nbsp;·&nbsp; Banking → Technology</div>
    <p class="hero-desc">
      Bridging banking domain expertise with data-driven IT delivery.
      4+ years in BFSI operations — now channelling deep financial knowledge
      into technology solutions, analytics, and business transformation.
    </p>
    <div class="hero-badges">
      <span class="badge">Power BI</span>
      <span class="badge">SQL</span>
      <span class="badge">Python</span>
      <span class="badge">BRD / FRD</span>
      <span class="badge">UAT</span>
      <span class="badge">CASA · Lending · Payments</span>
      <span class="badge">ML · XGBoost</span>
    </div>
    <div class="hero-cta">
      <a href="#projects" class="btn-primary">View My Projects</a>
      <a href="#contact" class="btn-outline">Get In Touch</a>
    </div>
  </div>
</section>

<!-- METRICS -->
<div class="metrics">
  <div class="metric-item"><div class="metric-val">4+</div><div class="metric-label">Years Experience</div></div>
  <div class="metric-item"><div class="metric-val">92%</div><div class="metric-label">ML Model Accuracy</div></div>
  <div class="metric-item"><div class="metric-val">20%</div><div class="metric-label">Process Efficiency Gain</div></div>
  <div class="metric-item"><div class="metric-val">28K+</div><div class="metric-label">Records Analysed</div></div>
</div>

<!-- ABOUT -->
<section class="about" id="about">
  <div class="section-label">Who I Am</div>
  <div class="section-title">Banking Domain Meets <span>IT Delivery</span></div>
  <div class="about-grid">
    <div class="about-text">
      <p>I am an <strong>IT Business Analyst</strong> with 4+ years of deep banking operations experience at <strong>SBI Cards & Payment Services</strong> and <strong>Federal Operations and Services Ltd.</strong> — now transitioning into technology delivery with a powerful dual advantage.</p>
      <p>My banking background gives me something most IT BAs lack: <strong>genuine domain expertise</strong>. I understand how CASA accounts, lending workflows, payment systems (UPI, IMPS, NEFT, RTGS), KYC/AML, and reconciliation processes actually work — not just in theory, but from years of hands-on operations.</p>
      <p>Combined with strong technical skills in <strong>Power BI, SQL, Python, and ML modelling</strong>, I bridge the gap between business stakeholders and development teams — translating complex banking needs into clear, structured IT requirements.</p>
      <p>I am actively targeting <strong>IT BA, Systems Analyst, and Functional Consultant</strong> roles across India and the Gulf (UAE, KSA, Qatar).</p>
    </div>
    <div class="about-skills">
      <h4>Analytics & BI</h4>
      <div class="skill-tags">
        <span class="skill-tag teal">Power BI</span>
        <span class="skill-tag teal">DAX</span>
        <span class="skill-tag teal">Power Query</span>
        <span class="skill-tag teal">Advanced Excel</span>
        <span class="skill-tag teal">SQL (MySQL)</span>
      </div>
      <h4>IT Business Analysis</h4>
      <div class="skill-tags">
        <span class="skill-tag gold">BRD / FRD</span>
        <span class="skill-tag gold">User Stories</span>
        <span class="skill-tag gold">Process Mapping</span>
        <span class="skill-tag gold">GAP Analysis</span>
        <span class="skill-tag gold">UAT</span>
        <span class="skill-tag gold">Stakeholder Mgmt</span>
      </div>
      <h4>Python & ML</h4>
      <div class="skill-tags">
        <span class="skill-tag">Python</span>
        <span class="skill-tag">Pandas</span>
        <span class="skill-tag">Scikit-learn</span>
        <span class="skill-tag">XGBoost</span>
        <span class="skill-tag">SMOTE</span>
        <span class="skill-tag">Matplotlib</span>
      </div>
      <h4>BFSI Domain</h4>
      <div class="skill-tags">
        <span class="skill-tag">CASA</span>
        <span class="skill-tag">Lending</span>
        <span class="skill-tag">UPI / IMPS</span>
        <span class="skill-tag">KYC / AML</span>
        <span class="skill-tag">Reconciliation</span>
        <span class="skill-tag">RBI Guidelines</span>
      </div>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section class="projects" id="projects">
  <div class="section-label">What I've Built</div>
  <div class="section-title">Project <span>Showcase</span></div>
  <div class="projects-grid">

    <div class="project-card">
      <div class="project-card-top"></div>
      <div class="project-body">
        <div class="project-num">PROJECT 01</div>
        <div class="project-title">Banking Fraud Detection & Anomaly System</div>
        <p class="project-desc">End-to-end ML pipeline on 28,000+ real banking transaction records. Detects fraud patterns, payment anomalies, and reconciliation gaps using ensemble ML models.</p>
        <div class="project-tools">
          <span class="tool-chip">Python</span><span class="tool-chip">SQL</span>
          <span class="tool-chip">Random Forest</span><span class="tool-chip">XGBoost</span>
          <span class="tool-chip">SMOTE</span><span class="tool-chip">Power BI</span>
        </div>
        <div class="project-outcome"><strong>Outcome:</strong> 92% fraud detection accuracy. Interactive Power BI risk dashboards delivered.</div>
        <div class="project-links">
          <a href="https://github.com/mir-anwara/banking-fraud-detection" target="_blank" class="proj-link github">GitHub →</a>
          <a href="https://kaggle.com/miranwara" target="_blank" class="proj-link kaggle">Kaggle →</a>
        </div>
      </div>
    </div>

    <div class="project-card">
      <div class="project-card-top"></div>
      <div class="project-body">
        <div class="project-num">PROJECT 02</div>
        <div class="project-title">Retail Banking KPI Dashboard & Process Improvement</div>
        <p class="project-desc">Complete BA engagement — AS-IS/TO-BE process mapping, BRD/FRD documentation, and Power BI KPI dashboard for CASA, Lending, and Payments operations.</p>
        <div class="project-tools">
          <span class="tool-chip">Power BI</span><span class="tool-chip">Advanced Excel</span>
          <span class="tool-chip">BRD/FRD</span><span class="tool-chip">Process Mapping</span>
          <span class="tool-chip">UAT</span>
        </div>
        <div class="project-outcome"><strong>Outcome:</strong> 20% cycle time reduction. Adopted as primary management dashboard across 3 business units.</div>
        <div class="project-links">
          <a href="https://github.com/mir-anwara/retail-banking-kpi-dashboard" target="_blank" class="proj-link github">GitHub →</a>
        </div>
      </div>
    </div>

    <div class="project-card">
      <div class="project-card-top"></div>
      <div class="project-body">
        <div class="project-num">PROJECT 03</div>
        <div class="project-title">Payment Analytics & Reconciliation Intelligence</div>
        <p class="project-desc">Multi-channel payment analysis (UPI/IMPS/NEFT/card) with automated reconciliation model. Hierarchical Power BI views from BU level to individual transaction.</p>
        <div class="project-tools">
          <span class="tool-chip">SQL</span><span class="tool-chip">Advanced Excel</span>
          <span class="tool-chip">Power BI</span><span class="tool-chip">Python</span>
          <span class="tool-chip">Chargeback Analysis</span>
        </div>
        <div class="project-outcome"><strong>Outcome:</strong> 20% error reduction. 95% audit-readiness. Reconciliation gaps identified & resolved.</div>
        <div class="project-links">
          <a href="https://github.com/mir-anwara/payment-reconciliation-analytics" target="_blank" class="proj-link github">GitHub →</a>
        </div>
      </div>
    </div>

  </div>
</section>

<!-- EXPERIENCE -->
<section class="experience" id="experience">
  <div class="section-label">Career Journey</div>
  <div class="section-title">Work <span>Experience</span></div>
  <div class="exp-timeline">

    <div class="exp-item">
      <div class="exp-dates">DEC 2025 — PRESENT</div>
      <div class="exp-title">Senior IT Business Analyst</div>
      <div class="exp-company">Federal Operations and Services Ltd. &nbsp;·&nbsp; Kolkata, India</div>
      <ul class="exp-bullets">
        <li>Elicited and documented BRDs/FRDs from business stakeholders; translated banking workflows into structured IT requirements — delivering 20% STP cycle time improvement</li>
        <li>Built Power BI KPI dashboards (TAT, FTR, AHT) as analytics bridge between business and IT teams</li>
        <li>Managed end-to-end UAT: test scenario design, defect tracking, zero-defect go-lives</li>
      </ul>
    </div>

    <div class="exp-item">
      <div class="exp-dates">AUG 2021 — NOV 2024</div>
      <div class="exp-title">Business Analyst — Payments & Digital Lending</div>
      <div class="exp-company">SBI Cards & Payment Services Ltd. &nbsp;·&nbsp; Bhubaneswar, India</div>
      <ul class="exp-bullets">
        <li>Analysed 28,000+ payment records using SQL — detected anomalies reducing error rates by 20%</li>
        <li>Produced BRD-aligned SOPs, functional specs, and traceability matrices for IT change initiatives</li>
        <li>Delivered Power BI dashboards tracking billing KPIs, chargeback trends; achieved 95% client retention</li>
      </ul>
    </div>

    <div class="exp-item">
      <div class="exp-dates">2020 — 2021</div>
      <div class="exp-title">Mechanical & HSE Engineer</div>
      <div class="exp-company">Freezeco Pvt. Ltd. &amp; Triveni Earthmovers &nbsp;·&nbsp; India</div>
      <ul class="exp-bullets">
        <li>Managed HVAC/plant systems and HSE compliance; early exposure to systems thinking and process documentation</li>
      </ul>
    </div>

  </div>
</section>

<!-- PLATFORMS -->
<section class="platforms" id="platforms">
  <div class="section-label">Find Me Online</div>
  <div class="section-title">Professional <span style="color:var(--gold)">Profiles</span></div>
  <div class="platform-grid">
    <div class="platform-card">
      <div class="platform-icon">🐙</div>
      <div class="platform-name">GitHub</div>
      <p class="platform-desc">All 3 projects with full code, documentation, README files, and Power BI screenshots. SQL scripts and Python notebooks available.</p>
      <a href="https://github.com/mir-anwara" target="_blank" class="platform-link">github.com/mir-anwara →</a>
    </div>
    <div class="platform-card">
      <div class="platform-icon">📊</div>
      <div class="platform-name">Kaggle</div>
      <p class="platform-desc">Published notebooks for the Fraud Detection project — full data science workflow with EDA, feature engineering, and ML modelling.</p>
      <a href="https://kaggle.com/miranwara" target="_blank" class="platform-link">kaggle.com/miranwara →</a>
    </div>
    <div class="platform-card">
      <div class="platform-icon">💻</div>
      <div class="platform-name">LeetCode</div>
      <p class="platform-desc">Practising SQL and Python problems relevant to Business Analyst and Data Analyst roles — 25+ SQL problems solved.</p>
      <a href="https://leetcode.com/mir-anwara" target="_blank" class="platform-link">leetcode.com/mir-anwara →</a>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section class="contact" id="contact">
  <div class="contact-box">
    <div class="open-badge"><span class="open-dot"></span> Available for Opportunities</div>
    <h3>Let's Connect</h3>
    <p>Open to IT Business Analyst, Systems Analyst, and Functional Consultant roles across <strong>India</strong> and the <strong>Gulf (UAE, KSA, Qatar)</strong>. Happy to connect, discuss opportunities, or collaborate.</p>
    <div class="contact-links">
      <a href="mailto:mirquality99@gmail.com" class="contact-link email">📧 Email Me</a>
      <a href="https://linkedin.com/in/mir-anwara-87b14138a" target="_blank" class="contact-link linkedin">LinkedIn</a>
      <a href="https://github.com/mir-anwara" target="_blank" class="contact-link github-c">GitHub</a>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <p>© 2025 <span>Mir Anwara</span> &nbsp;·&nbsp; IT Business Analyst &nbsp;·&nbsp; Built with passion, powered by data</p>
</footer>

</body>
</html>
