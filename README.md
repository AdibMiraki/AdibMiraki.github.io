<!DOCTYPE html>
<html lang="en" data-theme="dark">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Adib Miraki Feriz — Bioinformatician</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=JetBrains+Mono:wght@300;400;500&family=Outfit:wght@300;400;500;600&display=swap" rel="stylesheet"/>
<style>
  :root[data-theme="dark"] {
    --bg: #080c14;
    --bg2: #0d1525;
    --bg3: #111d35;
    --surface: rgba(255,255,255,0.04);
    --surface2: rgba(255,255,255,0.07);
    --border: rgba(100,180,255,0.12);
    --text: #e8f4ff;
    --text2: #8ab4d4;
    --text3: #4a7a9b;
    --accent: #4fc3f7;
    --accent2: #00e5ff;
    --accent3: #7c4dff;
    --green: #00e676;
    --gold: #ffd740;
    --dna1: rgba(79,195,247,0.6);
    --dna2: rgba(124,77,255,0.6);
    --glow: 0 0 40px rgba(79,195,247,0.15);
    --card-shadow: 0 8px 32px rgba(0,0,0,0.4);
  }
  :root[data-theme="light"] {
    --bg: #f0f6ff;
    --bg2: #e4eef8;
    --bg3: #d8e8f5;
    --surface: rgba(255,255,255,0.7);
    --surface2: rgba(255,255,255,0.9);
    --border: rgba(20,80,160,0.15);
    --text: #0d1e3a;
    --text2: #2c5282;
    --text3: #5a82aa;
    --accent: #0077cc;
    --accent2: #0099dd;
    --accent3: #6200ea;
    --green: #00a651;
    --gold: #e6a800;
    --dna1: rgba(0,119,204,0.5);
    --dna2: rgba(98,0,234,0.5);
    --glow: 0 0 40px rgba(0,119,204,0.1);
    --card-shadow: 0 8px 32px rgba(0,60,120,0.12);
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'Outfit', sans-serif;
    background: var(--bg);
    color: var(--text);
    min-height: 100vh;
    overflow-x: hidden;
    transition: background 0.5s, color 0.5s;
  }

  /* ── DNA SIDE PANELS ── */
  .dna-panel {
    position: fixed;
    top: 0; bottom: 0;
    width: 80px;
    z-index: 0;
    pointer-events: none;
    overflow: hidden;
  }
  .dna-panel.left { left: 0; }
  .dna-panel.right { right: 0; }

  .dna-canvas { width: 100%; height: 100%; }

  /* ── THEME TOGGLE ── */
  .theme-btn {
    position: fixed;
    top: 20px; right: 20px;
    z-index: 100;
    background: var(--surface2);
    border: 1px solid var(--border);
    border-radius: 50px;
    padding: 8px 18px;
    cursor: pointer;
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    color: var(--accent);
    display: flex; align-items: center; gap: 8px;
    transition: all 0.3s;
    backdrop-filter: blur(10px);
    box-shadow: var(--card-shadow);
  }
  .theme-btn:hover { background: var(--surface); transform: scale(1.05); }
  .theme-icon { font-size: 16px; transition: transform 0.5s; }
  .theme-btn:hover .theme-icon { transform: rotate(20deg); }

  /* ── MAIN LAYOUT ── */
  .main {
    max-width: 820px;
    margin: 0 auto;
    padding: 60px 20px 80px;
    position: relative;
    z-index: 1;
  }

  /* ── HERO ── */
  .hero {
    text-align: center;
    padding: 40px 0 50px;
    position: relative;
  }

  .photo-ring {
    width: 140px; height: 140px;
    margin: 0 auto 28px;
    position: relative;
  }
  .photo-ring::before {
    content: '';
    position: absolute;
    inset: -4px;
    border-radius: 50%;
    background: conic-gradient(var(--accent), var(--accent3), var(--accent2), var(--accent));
    animation: spin 4s linear infinite;
  }
  .photo-ring::after {
    content: '';
    position: absolute;
    inset: -8px;
    border-radius: 50%;
    background: conic-gradient(var(--accent3), var(--accent2), var(--accent), var(--accent3));
    animation: spin 8s linear infinite reverse;
    opacity: 0.4;
  }
  @keyframes spin { to { transform: rotate(360deg); } }

  .photo-inner {
    position: relative;
    z-index: 1;
    width: 100%; height: 100%;
    border-radius: 50%;
    overflow: hidden;
    background: var(--bg3);
    border: 3px solid var(--bg);
  }
  .photo-inner img {
    width: 100%; height: 100%;
    object-fit: cover;
    display: block;
  }
  /* Placeholder avatar shown when no real photo */
  .photo-placeholder {
    width: 100%; height: 100%;
    display: flex; align-items: center; justify-content: center;
    font-size: 54px;
    background: linear-gradient(135deg, var(--bg3), var(--bg2));
    color: var(--accent);
    font-family: 'Playfair Display', serif;
    font-weight: 700;
    letter-spacing: -2px;
  }

  .hero-name {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2rem, 5vw, 3rem);
    font-weight: 700;
    letter-spacing: -0.5px;
    line-height: 1.1;
    margin-bottom: 6px;
  }
  .hero-name span { color: var(--accent); }

  .hero-role {
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    color: var(--accent2);
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 20px;
    opacity: 0.9;
  }

  .hero-quote {
    font-family: 'Playfair Display', serif;
    font-style: italic;
    color: var(--text2);
    font-size: 15px;
    max-width: 500px;
    margin: 0 auto 28px;
    line-height: 1.6;
    border-left: 2px solid var(--accent);
    padding-left: 16px;
    text-align: left;
  }

  .badges {
    display: flex; flex-wrap: wrap; gap: 10px;
    justify-content: center;
    margin-bottom: 20px;
  }
  .badge {
    display: inline-flex; align-items: center; gap: 6px;
    padding: 6px 14px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 50px;
    font-size: 12px;
    font-family: 'JetBrains Mono', monospace;
    color: var(--text2);
    text-decoration: none;
    transition: all 0.25s;
    backdrop-filter: blur(6px);
  }
  .badge:hover {
    border-color: var(--accent);
    color: var(--accent);
    box-shadow: 0 0 12px rgba(79,195,247,0.2);
    transform: translateY(-2px);
  }

  /* ── DIVIDER ── */
  .divider {
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--border), transparent);
    margin: 40px 0;
  }

  /* ── SECTION HEADER ── */
  .section-header {
    display: flex; align-items: center; gap: 12px;
    margin-bottom: 24px;
  }
  .section-icon { font-size: 20px; }
  .section-title {
    font-family: 'Playfair Display', serif;
    font-size: 1.4rem;
    font-weight: 700;
    color: var(--text);
  }
  .section-line {
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, var(--border), transparent);
  }

  /* ── ABOUT ── */
  .about-text {
    font-size: 15px;
    line-height: 1.8;
    color: var(--text2);
    margin-bottom: 20px;
  }
  .about-text strong { color: var(--accent); font-weight: 600; }

  .tags {
    display: flex; flex-wrap: wrap; gap: 8px;
  }
  .tag {
    padding: 4px 12px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 4px;
    font-size: 12px;
    font-family: 'JetBrains Mono', monospace;
    color: var(--text2);
  }

  /* ── EDUCATION ── */
  .edu-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px 24px;
    display: flex; align-items: center; gap: 16px;
    transition: all 0.3s;
  }
  .edu-card:hover { border-color: var(--accent); box-shadow: var(--glow); }
  .edu-icon { font-size: 28px; }
  .edu-title { font-size: 15px; font-weight: 600; color: var(--text); margin-bottom: 4px; }
  .edu-sub { font-size: 13px; color: var(--text2); margin-bottom: 4px; }
  .edu-badge {
    display: inline-block;
    padding: 2px 10px;
    background: rgba(0,230,118,0.12);
    border: 1px solid rgba(0,230,118,0.3);
    border-radius: 50px;
    font-size: 11px;
    font-family: 'JetBrains Mono', monospace;
    color: var(--green);
  }

  /* ── TIMELINE ── */
  .timeline { position: relative; padding-left: 28px; }
  .timeline::before {
    content: '';
    position: absolute;
    left: 7px; top: 0; bottom: 0;
    width: 1px;
    background: linear-gradient(to bottom, var(--accent), transparent);
  }
  .tl-item {
    position: relative;
    margin-bottom: 24px;
    padding: 16px 20px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    transition: all 0.3s;
  }
  .tl-item:hover { border-color: var(--accent); transform: translateX(4px); }
  .tl-item::before {
    content: '';
    position: absolute;
    left: -24px; top: 20px;
    width: 10px; height: 10px;
    border-radius: 50%;
    background: var(--accent);
    box-shadow: 0 0 8px var(--accent);
  }
  .tl-role { font-size: 14px; font-weight: 600; color: var(--text); margin-bottom: 2px; }
  .tl-place { font-size: 13px; color: var(--accent); margin-bottom: 2px; }
  .tl-period {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: var(--text3);
  }

  /* ── PUBLICATIONS ── */
  .pub-year {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--accent);
    margin: 28px 0 12px;
    padding-left: 4px;
  }
  .pub-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-left: 3px solid var(--accent3);
    border-radius: 10px;
    padding: 16px 20px;
    margin-bottom: 14px;
    transition: all 0.3s;
    position: relative;
    overflow: hidden;
  }
  .pub-card:hover {
    border-left-color: var(--accent2);
    box-shadow: var(--card-shadow);
    transform: translateY(-2px);
  }
  .pub-card.featured { border-left-color: var(--gold); }
  .pub-card.featured::before {
    content: '⭐ FEATURED';
    position: absolute;
    top: 10px; right: 12px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 9px;
    color: var(--gold);
    letter-spacing: 1px;
  }
  .pub-title {
    font-size: 14px;
    font-weight: 500;
    color: var(--text);
    line-height: 1.5;
    margin-bottom: 6px;
  }
  .pub-authors { font-size: 12px; color: var(--text3); margin-bottom: 6px; line-height: 1.4; }
  .pub-authors strong { color: var(--accent); }
  .pub-journal {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: var(--text2);
    display: flex; align-items: center; gap: 10px; flex-wrap: wrap;
  }
  .pub-link {
    color: var(--accent2);
    text-decoration: none;
    font-size: 11px;
    display: inline-flex; align-items: center; gap: 4px;
  }
  .pub-link:hover { color: var(--accent); }

  /* ── AWARDS ── */
  .awards-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
    gap: 12px;
  }
  .award-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 14px 16px;
    transition: all 0.3s;
  }
  .award-card:hover { border-color: var(--gold); box-shadow: 0 0 20px rgba(255,215,64,0.1); }
  .award-year {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    color: var(--text3);
    margin-bottom: 4px;
    letter-spacing: 1px;
  }
  .award-text { font-size: 13px; color: var(--text); line-height: 1.4; }
  .award-icon { font-size: 18px; margin-bottom: 6px; }

  /* ── REFERENCES ── */
  .refs-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
    gap: 14px;
  }
  .ref-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 18px 20px;
    text-align: center;
    transition: all 0.3s;
  }
  .ref-card:hover { border-color: var(--accent); transform: translateY(-3px); }
  .ref-avatar {
    width: 48px; height: 48px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--accent), var(--accent3));
    margin: 0 auto 10px;
    display: flex; align-items: center; justify-content: center;
    font-size: 18px; color: white; font-weight: 700;
    font-family: 'Playfair Display', serif;
  }
  .ref-name { font-size: 14px; font-weight: 600; color: var(--text); margin-bottom: 4px; }
  .ref-role { font-size: 12px; color: var(--text2); line-height: 1.4; }

  /* ── FOOTER ── */
  .footer {
    text-align: center;
    padding: 40px 0 20px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: var(--text3);
    letter-spacing: 1px;
  }

  /* ── FADE IN ── */
  .fade-in {
    opacity: 0;
    transform: translateY(20px);
    animation: fadeUp 0.6s ease forwards;
  }
  @keyframes fadeUp {
    to { opacity: 1; transform: translateY(0); }
  }
  .fade-in:nth-child(1) { animation-delay: 0.1s; }
  .fade-in:nth-child(2) { animation-delay: 0.2s; }
  .fade-in:nth-child(3) { animation-delay: 0.3s; }

  @media (max-width: 600px) {
    .dna-panel { width: 40px; }
    .main { padding: 50px 12px; }
  }
</style>
</head>
<body>

<!-- THEME TOGGLE -->
<button class="theme-btn" onclick="toggleTheme()" title="Toggle theme">
  <span class="theme-icon" id="themeIcon">🌙</span>
  <span id="themeLabel">Dark</span>
</button>

<!-- DNA SIDE PANELS -->
<div class="dna-panel left"><canvas class="dna-canvas" id="dnaLeft"></canvas></div>
<div class="dna-panel right"><canvas class="dna-canvas" id="dnaRight"></canvas></div>

<!-- MAIN CONTENT -->
<div class="main">

  <!-- HERO -->
  <div class="hero fade-in">
    <div class="photo-ring">
      <div class="photo-inner">
        <!-- Replace src with your real photo URL, e.g. src="https://your-photo-url.jpg" -->
        <div class="photo-placeholder">Adib Miraki</div>
         <img src="https://github.com/AdibMiraki/AdibMiraki.github.io/blob/main/6035037811414601115.jpg" alt="Adib Miraki Feriz" />
      </div>
    </div>

    <h1 class="hero-name">Adib <span>Miraki Feriz</span></h1>
    <p class="hero-role">Bioinformatician · Wellcome Sanger Institute</p>

    <blockquote class="hero-quote">
      "Giving cells a digital voice and letting data science do the talking."
    </blockquote>

    <div class="badges">
      <a class="badge" href="mailto:am74@sanger.ac.uk">✉️ am74@sanger.ac.uk</a>
      <a class="badge" href="https://lotfollahi.com/Lab/" target="_blank">🏛 Lotfollahi Lab</a>
      <a class="badge" href="https://scholar.google.com/citations?hl=en&user=Xz60exkAAAAJ" target="_blank">📚 Google Scholar</a>
    </div>
  </div>

  <div class="divider"></div>

  <!-- ABOUT -->
  <section class="fade-in">
    <div class="section-header">
      <span class="section-icon">👋</span>
      <h2 class="section-title">About Me</h2>
      <div class="section-line"></div>
    </div>
    <p class="about-text">
      I'm a <strong>Bioinformatician</strong> at the Lotfollahi Lab, Wellcome Sanger Institute, working at the intersection of <strong>machine learning</strong>, <strong>single-cell genomics</strong>, and <strong>spatial transcriptomics</strong>. My research focuses on decoding the language of cells — predicting how they behave, interact, and evolve across different biological contexts.
    </p>
    <div class="tags">
      <span class="tag">Single-cell genomics</span>
      <span class="tag">Spatial transcriptomics</span>
      <span class="tag">Perturbation modeling</span>
      <span class="tag">Tumor immunology</span>
      <span class="tag">Deep learning</span>
      <span class="tag">⚽ Football</span>
      <span class="tag">🚴 Cycling</span>
    </div>
  </section>

  <div class="divider"></div>

  <!-- EDUCATION -->
  <section>
    <div class="section-header">
      <span class="section-icon">🎓</span>
      <h2 class="section-title">Education</h2>
      <div class="section-line"></div>
    </div>
    <div class="edu-card">
      <span class="edu-icon">🎓</span>
      <div>
        <div class="edu-title">BSc Medical Laboratory Sciences</div>
        <div class="edu-sub">Birjand University of Medical Sciences · 2019 – 2023</div>
        <span class="edu-badge">A · Top of Class</span>
      </div>
    </div>
  </section>

  <div class="divider"></div>

  <!-- EXPERIENCE -->
  <section>
    <div class="section-header">
      <span class="section-icon">💼</span>
      <h2 class="section-title">Research Experience</h2>
      <div class="section-line"></div>
    </div>
    <div class="timeline">
      <div class="tl-item">
        <div class="tl-role">On-site Bioinformatician</div>
        <div class="tl-place">Wellcome Sanger Institute · Lotfollahi Lab, Cambridge UK</div>
        <div class="tl-period">Aug 2025 – Present</div>
      </div>
      <div class="tl-item">
        <div class="tl-role">Research Collaborator (Remote Contract)</div>
        <div class="tl-place">Wellcome Sanger Institute · Lotfollahi Lab, Cambridge UK</div>
        <div class="tl-period">Feb 2023 – Aug 2025</div>
      </div>
      <div class="tl-item">
        <div class="tl-role">Research Intern</div>
        <div class="tl-place">Sharif University of Technology, Tehran, Iran</div>
        <div class="tl-period">Oct 2022 – Jan 2023</div>
      </div>
      <div class="tl-item">
        <div class="tl-role">Research Assistant</div>
        <div class="tl-place">Cellular & Molecular Research Center, BUMS</div>
        <div class="tl-period">Apr 2021 – Sep 2022</div>
      </div>
    </div>
  </section>

  <div class="divider"></div>

  <!-- PUBLICATIONS -->
  <section>
    <div class="section-header">
      <span class="section-icon">📜</span>
      <h2 class="section-title">Publications</h2>
      <div class="section-line"></div>
    </div>

    <div class="pub-year">2026</div>

    <div class="pub-card featured">
      <div class="pub-title">Predicting how perturbations reshape cellular trajectories with PerturbGen</div>
      <div class="pub-authors"><strong>Ly K.C.H.*, Miraki Feriz A.*</strong>, Isobe T., Vahidi A., Vaghari D., et al.</div>
      <div class="pub-journal">
        bioRxiv 2026 · Co-first author · Under review at <em>Nature</em>
        <a class="pub-link" href="https://www.biorxiv.org/content/10.64898/2026.03.04.709254v1" target="_blank">📄 Paper</a>
      </div>
    </div>

    <div class="pub-card">
      <div class="pub-title">Multimodal foundation models in colorectal cancer: from prediction to trustworthy clinical insight</div>
      <div class="pub-authors">Gharaie Amirabadi D., <strong>Miraki Feriz A.</strong>, Safarpour H.</div>
      <div class="pub-journal">
        Briefings in Bioinformatics, Vol 27(2), Mar 2026
        <a class="pub-link" href="https://doi.org/10.1093/bib/bbag179" target="_blank">📄 Paper</a>
      </div>
    </div>

    <div class="pub-year">2025</div>

    <div class="pub-card">
      <div class="pub-title">Quantitative characterization of cell niches in spatially resolved omics data</div>
      <div class="pub-authors">Birk S., Bonafonte-Pardàs I., <strong>Miraki Feriz A.</strong>, Boxall A., et al.</div>
      <div class="pub-journal">
        Nature Genetics, 57:897–909, 2025
        <a class="pub-link" href="https://www.nature.com/articles/s41588-025-02120-6" target="_blank">📄 Paper</a>
      </div>
    </div>

    <div class="pub-card">
      <div class="pub-title">The Hippo terminal effector YAP boosts enterovirus replication in type 1 diabetes</div>
      <div class="pub-authors">Geravandi S., Liu H., Pahwa H., ..., <strong>Miraki Feriz A.</strong>, ..., Gotti D.</div>
      <div class="pub-journal">
        Nature Communications, 16(1):8882, 2025
        <a class="pub-link" href="https://www.nature.com/articles/s41467-025-64508-6" target="_blank">📄 Paper</a>
      </div>
    </div>

    <div class="pub-year">2024</div>

    <div class="pub-card">
      <div class="pub-title">Targeting the dynamic transcriptional landscape of Treg subpopulations in pancreatic ductal adenocarcinoma</div>
      <div class="pub-authors"><strong>Miraki Feriz A.</strong>, Khosrojerdi A., Erfanian N., et al.</div>
      <div class="pub-journal">
        Immunobiology, 229(4):152822, 2024
        <a class="pub-link" href="https://www.sciencedirect.com/science/article/pii/S0171298524000408" target="_blank">📄 Paper</a>
      </div>
    </div>

    <div class="pub-card">
      <div class="pub-title">Tumor-infiltrating CD8+ sub-populations in primary and recurrent glioblastoma: An in-silico study</div>
      <div class="pub-authors">Shadbad M.A., <strong>Miraki Feriz A.</strong>, Baradaran B., Safarpour H.</div>
      <div class="pub-journal">
        Heliyon, 10(5):e27329, 2024
        <a class="pub-link" href="https://www.sciencedirect.com/science/article/pii/S2405844024033607" target="_blank">📄 Paper</a>
      </div>
    </div>

    <div class="pub-card">
      <div class="pub-title">Holistic exploration of CHGA and hsa-miR-137 in colorectal cancer via multi-omic data integration</div>
      <div class="pub-authors">Safarpour H., Ranjbaran J., Erfanian N., ..., <strong>Miraki Feriz A.</strong>, ..., Silvestris N.</div>
      <div class="pub-journal">
        Heliyon, 2024
        <a class="pub-link" href="https://www.cell.com/heliyon/fulltext/S2405-8440(24)03077-9" target="_blank">📄 Paper</a>
      </div>
    </div>

    <div class="pub-year">2023</div>

    <div class="pub-card">
      <div class="pub-title">Single-cell RNA sequencing uncovers heterogeneous transcriptional signatures in tumor-infiltrated dendritic cells in prostate cancer</div>
      <div class="pub-authors"><strong>Miraki Feriz A.</strong>, Khosrojerdi A., Lotfollahi M., et al.</div>
      <div class="pub-journal">
        Heliyon, 9(5):e15694, 2023
        <a class="pub-link" href="https://www.sciencedirect.com/science/article/pii/S2405844023029018" target="_blank">📄 Paper</a>
      </div>
    </div>

    <div class="pub-card">
      <div class="pub-title">Deciphering the immune landscape of HNSCC: single-cell transcriptomic analysis of Treg responses to PD-1 blockade therapy</div>
      <div class="pub-authors"><strong>Miraki Feriz A.</strong>, Bahraini F., Khosrojerdi A., et al.</div>
      <div class="pub-journal">
        PLOS ONE, 18(12):e0295863, 2023
        <a class="pub-link" href="https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0295863" target="_blank">📄 Paper</a>
      </div>
    </div>

    <div class="pub-card">
      <div class="pub-title">Deep learning applications in single-cell genomics and transcriptomics data analysis</div>
      <div class="pub-authors">Erfanian N., Heydari A.A., <strong>Miraki Feriz A.</strong>, et al.</div>
      <div class="pub-journal">
        Biomedicine &amp; Pharmacotherapy, 165:115077, 2023
        <a class="pub-link" href="https://www.sciencedirect.com/science/article/pii/S0753332223008685" target="_blank">📄 Paper</a>
      </div>
    </div>

    <div class="pub-card">
      <div class="pub-title">Characterization of Wnt signaling under Lactobacillus acidophilus postbiotic treatment in colorectal cancer</div>
      <div class="pub-authors">Erfanian N., Nasseri S., <strong>Miraki Feriz A.</strong>, et al.</div>
      <div class="pub-journal">
        Scientific Reports, 13(1):22988, 2023
        <a class="pub-link" href="https://www.nature.com/articles/s41598-023-50047-x" target="_blank">📄 Paper</a>
      </div>
    </div>

    <div class="pub-card">
      <div class="pub-title">Putative role of glial cells in treatment resistance depression: single-nuclei transcriptomics evaluation</div>
      <div class="pub-authors">Sanadgol N., <strong>Miraki Feriz A.</strong>, Lisboa S.F., Joca S.R.</div>
      <div class="pub-journal">
        Life Sciences, 331:122025, 2023
        <a class="pub-link" href="https://www.sciencedirect.com/science/article/abs/pii/S0024320523006604" target="_blank">📄 Paper</a>
      </div>
    </div>

    <div class="pub-year">2022</div>

    <div class="pub-card">
      <div class="pub-title">Expression pattern of VISTA in PBMCs of relapsing-remitting multiple sclerosis patients: single-cell RNA sequencing study</div>
      <div class="pub-authors">Derakhshani A., ..., <strong>Miraki Feriz A.</strong>, ..., Ahmadi H.</div>
      <div class="pub-journal">
        Biomedicine &amp; Pharmacotherapy, 148:112725, 2022
        <a class="pub-link" href="https://www.sciencedirect.com/science/article/pii/S0753332222001135" target="_blank">📄 Paper</a>
      </div>
    </div>
  </section>

  <div class="divider"></div>

  <!-- AWARDS -->
  <section>
    <div class="section-header">
      <span class="section-icon">🏆</span>
      <h2 class="section-title">Honors & Awards</h2>
      <div class="section-line"></div>
    </div>
    <div class="awards-grid">
      <div class="award-card">
        <div class="award-icon">🥈</div>
        <div class="award-year">2025</div>
        <div class="award-text">Rank 2nd — AI Hackathon, Birjand University of Medical Sciences</div>
      </div>
      <div class="award-card">
        <div class="award-icon">🏅</div>
        <div class="award-year">2023</div>
        <div class="award-text">Best Researcher of Iran among Undergraduate Students (National)</div>
      </div>
      <div class="award-card">
        <div class="award-icon">🏅</div>
        <div class="award-year">2023</div>
        <div class="award-text">Best Researcher — Birjand University of Medical Sciences</div>
      </div>
      <div class="award-card">
        <div class="award-icon">🏅</div>
        <div class="award-year">2022</div>
        <div class="award-text">Best Researcher — Birjand University of Medical Sciences</div>
      </div>
      <div class="award-card">
        <div class="award-icon">🎤</div>
        <div class="award-year">2022</div>
        <div class="award-text">Best Oral Presenter — 9th International Congress of Medical Students</div>
      </div>
    </div>
  </section>

  <div class="divider"></div>

  <!-- SERVICE -->
  <section>
    <div class="section-header">
      <span class="section-icon">📝</span>
      <h2 class="section-title">Academic Service</h2>
      <div class="section-line"></div>
    </div>
    <div class="tl-item" style="margin-left:0">
      <div class="tl-role">Invited Reviewer</div>
      <div class="tl-place">Briefings in Bioinformatics · Oxford University Press</div>
    </div>
  </section>

  <div class="divider"></div>

  <!-- REFERENCES -->
  <section>
    <div class="section-header">
      <span class="section-icon">🤝</span>
      <h2 class="section-title">References</h2>
      <div class="section-line"></div>
    </div>
    <div class="refs-grid">
      <div class="ref-card">
        <div class="ref-avatar">MH</div>
        <div class="ref-name">Prof. Muzlifah Haniffa</div>
        <div class="ref-role">Senior Group Leader, Wellcome Sanger Institute & University of Cambridge</div>
      </div>
      <div class="ref-card">
        <div class="ref-avatar">ÖB</div>
        <div class="ref-name">Dr. Ömer Ali Bayraktar</div>
        <div class="ref-role">Group Leader, Wellcome Sanger Institute</div>
      </div>
      <div class="ref-card">
        <div class="ref-avatar">ML</div>
        <div class="ref-name">Dr. Mohammad Lotfollahi</div>
        <div class="ref-role">Group Leader, Wellcome Sanger Institute (Supervisor)</div>
      </div>
    </div>
  </section>

  <div class="footer">
    <div style="margin-bottom:8px">Available upon request for academic and research positions.</div>
    <div>© 2026 Adib Miraki Feriz · Wellcome Sanger Institute</div>
  </div>
</div>

<script>
// ── THEME TOGGLE ──
function toggleTheme() {
  const html = document.documentElement;
  const isDark = html.getAttribute('data-theme') === 'dark';
  html.setAttribute('data-theme', isDark ? 'light' : 'dark');
  document.getElementById('themeIcon').textContent = isDark ? '☀️' : '🌙';
  document.getElementById('themeLabel').textContent = isDark ? 'Light' : 'Dark';
  drawDNA(); // redraw with new colors
}

// ── DNA ANIMATION ──
const canvases = [document.getElementById('dnaLeft'), document.getElementById('dnaRight')];

function getThemeColors() {
  const isDark = document.documentElement.getAttribute('data-theme') === 'dark';
  return {
    strand1: isDark ? 'rgba(79,195,247,' : 'rgba(0,119,204,',
    strand2: isDark ? 'rgba(124,77,255,' : 'rgba(98,0,234,',
    rung: isDark ? 'rgba(0,229,255,' : 'rgba(0,100,200,',
    glow: isDark ? 'rgba(79,195,247,0.2)' : 'rgba(0,119,204,0.15)',
  };
}

const dnaStates = canvases.map(() => ({ offset: 0 }));

function drawDNACanvas(canvas, state, flip) {
  const ctx = canvas.getContext('2d');
  const W = canvas.width = canvas.offsetWidth;
  const H = canvas.height = canvas.offsetHeight;
  ctx.clearRect(0, 0, W, H);

  const cols = getThemeColors();
  const amplitude = W * 0.32;
  const cx = W / 2;
  const period = 120;
  const numRungs = Math.floor(H / 18);
  const speed = state.offset;

  // Draw two strands
  for (let strand = 0; strand < 2; strand++) {
    const phase = strand === 0 ? 0 : Math.PI;
    ctx.beginPath();
    for (let y = 0; y <= H; y += 2) {
      const x = cx + amplitude * Math.sin((y / period) * Math.PI * 2 + speed + phase);
      if (y === 0) ctx.moveTo(flip ? W - x : x, y);
      else ctx.lineTo(flip ? W - x : x, y);
    }
    const alpha = strand === 0 ? '0.7)' : '0.5)';
    ctx.strokeStyle = strand === 0 ? cols.strand1 + alpha : cols.strand2 + alpha;
    ctx.lineWidth = 2.5;
    ctx.shadowColor = strand === 0 ? cols.strand1 + '0.4)' : cols.strand2 + '0.3)';
    ctx.shadowBlur = 8;
    ctx.stroke();
    ctx.shadowBlur = 0;
  }

  // Draw rungs (base pairs)
  for (let i = 0; i <= numRungs; i++) {
    const y = (i * (H / numRungs) + (speed * 10 % (H / numRungs))) % H;
    const x1 = cx + amplitude * Math.sin((y / period) * Math.PI * 2 + speed);
    const x2 = cx + amplitude * Math.sin((y / period) * Math.PI * 2 + speed + Math.PI);

    const progress = Math.abs(Math.sin((y / period) * Math.PI * 2 + speed));
    const alpha = 0.2 + progress * 0.6;

    ctx.beginPath();
    ctx.moveTo(flip ? W - x1 : x1, y);
    ctx.lineTo(flip ? W - x2 : x2, y);
    ctx.strokeStyle = cols.rung + alpha + ')';
    ctx.lineWidth = 1.5;
    ctx.stroke();

    // Dots at ends
    [x1, x2].forEach(x => {
      ctx.beginPath();
      ctx.arc(flip ? W - x : x, y, 2.5, 0, Math.PI * 2);
      ctx.fillStyle = cols.rung + (alpha + 0.2) + ')';
      ctx.fill();
    });
  }
}

let animFrame;
function animate() {
  dnaStates[0].offset += 0.012;
  dnaStates[1].offset += 0.012;
  drawDNACanvas(canvases[0], dnaStates[0], false);
  drawDNACanvas(canvases[1], dnaStates[1], true);
  animFrame = requestAnimationFrame(animate);
}

function drawDNA() { /* colors updated on next frame */ }

// Start
animate();

// Resize handler
window.addEventListener('resize', () => {
  canvases.forEach(c => { c.width = c.offsetWidth; c.height = c.offsetHeight; });
});
</script>
</body>
</html>
