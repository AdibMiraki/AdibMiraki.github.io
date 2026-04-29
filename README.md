<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Adib Miraki Feriz — Bioinformatician · Wellcome Sanger Institute</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;500;600&family=Source+Serif+4:ital,opsz,wght@0,8..60,300;0,8..60,400;0,8..60,600;1,8..60,300&display=swap" rel="stylesheet">

<style>
/* ═══════════════════════════════════════════════
   RESET & ROOT
═══════════════════════════════════════════════ */
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

:root {
  --teal:    #00a896;
  --teal-lt: #e6f7f5;
  --violet:  #5c35a8;
  --gold:    #c28a00;
  --rose:    #c0392b;
  --text:    #1c1c2e;
  --mid:     #4a4a6a;
  --dim:     #7a7a9a;
  --border:  #dde2ef;
  --bg:      #ffffff;
  --bg-soft: #f7f8fc;
  --bg-card: #fafbff;
  --shadow:  0 2px 12px rgba(30,30,60,0.07);
  --sidebar: 80px;
}

html { scroll-behavior: smooth; }

body {
  background: var(--bg);
  color: var(--text);
  font-family: 'Source Serif 4', Georgia, serif;
  font-size: 15px;
  line-height: 1.7;
  overflow-x: hidden;
}

/* ═══════════════════════════════════════════════
   DNA SIDEBAR
═══════════════════════════════════════════════ */
#dna-sidebar {
  position: fixed;
  top: 0;
  left: 0;
  width: var(--sidebar);
  height: 100vh;
  z-index: 100;
  background: rgba(255,255,255,0.90);
  backdrop-filter: blur(6px);
  -webkit-backdrop-filter: blur(6px);
  border-right: 1px solid var(--border);
  pointer-events: none;
  overflow: hidden;
}
#dna-sidebar canvas {
  display: block;
  width: 100%;
  height: 100%;
}

/* ═══════════════════════════════════════════════
   PROGRESS BAR
═══════════════════════════════════════════════ */
#progress {
  position: fixed;
  top: 0;
  left: var(--sidebar);
  right: 0;
  height: 2px;
  background: linear-gradient(90deg, var(--teal), var(--violet));
  transform-origin: left;
  transform: scaleX(0);
  z-index: 200;
  transition: transform 0.1s linear;
}

/* ═══════════════════════════════════════════════
   PAGE LAYOUT
═══════════════════════════════════════════════ */
.page {
  margin-left: var(--sidebar);
  min-height: 100vh;
}

.inner {
  max-width: 820px;
  margin: 0 auto;
  padding: 0 40px 100px;
}

/* ═══════════════════════════════════════════════
   BANNER
═══════════════════════════════════════════════ */
.banner-wrap {
  width: 100%;
  max-height: 200px;
  overflow: hidden;
  margin-bottom: 32px;
}
.banner-wrap img {
  width: 100%;
  display: block;
  object-fit: cover;
}
/* fallback gradient if image 404s */
.banner-fallback {
  display: none;
  width: 100%;
  height: 160px;
  background: linear-gradient(135deg, #0f2027 0%, #203a43 50%, #2c5364 100%);
  border-radius: 0 0 10px 10px;
}

/* ═══════════════════════════════════════════════
   BADGES
═══════════════════════════════════════════════ */
.badges {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 8px;
  margin-bottom: 36px;
}
.badge {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  padding: 5px 13px;
  border-radius: 4px;
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  font-weight: 400;
  color: #fff;
  text-decoration: none;
  letter-spacing: 0.03em;
  transition: opacity 0.2s, transform 0.15s;
}
.badge:hover { opacity: 0.85; transform: translateY(-1px); }
.badge-email   { background: #0f2027; }
.badge-sanger  { background: #2c5364; }
.badge-scholar { background: #3a6bc9; }

/* ═══════════════════════════════════════════════
   DIVIDER
═══════════════════════════════════════════════ */
.divider {
  border: none;
  border-top: 1px solid var(--border);
  margin: 36px 0;
}

/* ═══════════════════════════════════════════════
   SECTION HEADINGS
═══════════════════════════════════════════════ */
.section-heading {
  display: flex;
  align-items: center;
  gap: 10px;
  font-family: 'JetBrains Mono', monospace;
  font-size: 13px;
  font-weight: 600;
  color: var(--text);
  letter-spacing: 0.08em;
  text-transform: uppercase;
  margin: 0 0 20px;
  padding-bottom: 10px;
  border-bottom: 2px solid var(--border);
}
.section-heading .icon {
  font-size: 16px;
  line-height: 1;
}
.section-heading::after {
  content: '';
  flex: 1;
  height: 2px;
  background: linear-gradient(90deg, var(--teal), transparent);
  margin-left: 12px;
  border-radius: 2px;
}

/* ═══════════════════════════════════════════════
   ABOUT SECTION
═══════════════════════════════════════════════ */
.about-body p {
  color: var(--mid);
  margin-bottom: 12px;
}
.about-body strong { color: var(--text); font-weight: 600; }
.about-body a { color: var(--teal); text-decoration: none; }
.about-body a:hover { text-decoration: underline; }

.blockquote {
  border-left: 3px solid var(--teal);
  background: var(--teal-lt);
  padding: 14px 20px;
  margin: 20px 0;
  border-radius: 0 8px 8px 0;
  color: var(--mid);
  font-style: italic;
  font-size: 14px;
}

.interest-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  margin-top: 14px;
}
.interest-tag {
  background: var(--bg-soft);
  border: 1px solid var(--border);
  color: var(--mid);
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  padding: 3px 10px;
  border-radius: 20px;
}

/* ═══════════════════════════════════════════════
   EDUCATION TABLE
═══════════════════════════════════════════════ */
.data-table {
  width: 100%;
  border-collapse: collapse;
  font-size: 13.5px;
  margin-bottom: 8px;
}
.data-table thead th {
  background: var(--bg-soft);
  padding: 10px 14px;
  text-align: left;
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  font-weight: 600;
  color: var(--dim);
  letter-spacing: 0.08em;
  text-transform: uppercase;
  border-bottom: 2px solid var(--border);
}
.data-table tbody td {
  padding: 11px 14px;
  border-bottom: 1px solid var(--border);
  color: var(--mid);
  vertical-align: top;
}
.data-table tbody td:first-child { color: var(--text); font-weight: 500; }
.data-table tbody tr:last-child td { border-bottom: none; }
.data-table tbody tr:hover td { background: var(--bg-soft); }

/* ═══════════════════════════════════════════════
   EXPERIENCE CODE BLOCK
═══════════════════════════════════════════════ */
.exp-block {
  background: #0d1520;
  border-radius: 10px;
  padding: 24px 28px;
  font-family: 'JetBrains Mono', monospace;
  font-size: 12.5px;
  line-height: 2;
  overflow-x: auto;
  border: 1px solid #1e2d40;
}
.exp-block .e-icon  { font-size: 14px; }
.exp-block .e-inst  { color: #00c4b0; font-weight: 500; }
.exp-block .e-city  { color: #7a9ab8; }
.exp-block .e-role  { color: #a0b8d0; }
.exp-block .e-date  { color: #4a6a88; }
.exp-block .e-gap   { display: block; height: 10px; }

/* ═══════════════════════════════════════════════
   PUBLICATIONS
═══════════════════════════════════════════════ */
.year-label {
  font-family: 'JetBrains Mono', monospace;
  font-size: 10px;
  font-weight: 600;
  color: var(--dim);
  letter-spacing: 0.25em;
  text-transform: uppercase;
  margin: 28px 0 8px;
  display: flex;
  align-items: center;
  gap: 10px;
}
.year-label::after {
  content: '';
  flex: 1;
  height: 1px;
  background: var(--border);
}

.pub-card {
  background: var(--bg-card);
  border: 1px solid var(--border);
  border-left: 3px solid var(--border);
  border-radius: 0 8px 8px 0;
  padding: 16px 18px;
  margin-bottom: 12px;
  transition: border-left-color 0.25s, box-shadow 0.25s, background 0.2s;
}
.pub-card:hover {
  border-left-color: var(--teal);
  box-shadow: var(--shadow);
  background: #fff;
}
.pub-card .pub-chips {
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
  margin-bottom: 9px;
}
.chip {
  display: inline-block;
  font-family: 'JetBrains Mono', monospace;
  font-size: 10px;
  padding: 2px 8px;
  border-radius: 3px;
  letter-spacing: 0.05em;
  font-weight: 500;
}
.chip-venue  { background: var(--teal);   color: #fff; }
.chip-nature { background: #1a6e3c;       color: #fff; }
.chip-plos   { background: #b5520a;       color: #fff; }
.chip-bib    { background: #5c35a8;       color: #fff; }
.chip-first  { background: transparent; border: 1px solid var(--teal); color: var(--teal); }
.chip-review { background: #fff3cd; color: #856404; border: 1px solid #ffd96a; }

.pub-card .pub-title {
  font-size: 13.5px;
  font-weight: 600;
  color: var(--text);
  line-height: 1.55;
  margin-bottom: 5px;
  font-family: 'Source Serif 4', serif;
}
.pub-card .pub-authors {
  font-size: 12px;
  color: var(--dim);
  margin-bottom: 7px;
  font-family: 'JetBrains Mono', monospace;
  line-height: 1.6;
}
.pub-card .pub-authors .me { color: var(--teal); font-weight: 500; }
.pub-card .pub-venue-line {
  font-size: 12px;
  color: var(--mid);
  font-style: italic;
  margin-bottom: 8px;
}
.pub-card .pub-link {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: var(--teal);
  text-decoration: none;
  display: inline-flex;
  align-items: center;
  gap: 4px;
}
.pub-card .pub-link:hover { text-decoration: underline; }

/* ═══════════════════════════════════════════════
   AWARDS TABLE
═══════════════════════════════════════════════ */
.award-table tbody td:first-child {
  font-family: 'JetBrains Mono', monospace;
  font-weight: 600;
  color: var(--teal);
  white-space: nowrap;
  font-size: 13px;
}

/* ═══════════════════════════════════════════════
   REFERENCES
═══════════════════════════════════════════════ */
.ref-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(230px, 1fr));
  gap: 14px;
  margin-bottom: 16px;
}
.ref-card {
  background: var(--bg-card);
  border: 1px solid var(--border);
  border-radius: 8px;
  padding: 16px 18px;
  transition: box-shadow 0.2s, border-color 0.2s;
}
.ref-card:hover { box-shadow: var(--shadow); border-color: var(--teal); }
.ref-card .ref-name {
  font-weight: 600;
  color: var(--text);
  font-size: 13.5px;
  margin-bottom: 4px;
}
.ref-card .ref-role {
  font-size: 12px;
  color: var(--dim);
  font-family: 'JetBrains Mono', monospace;
  line-height: 1.5;
}

/* ═══════════════════════════════════════════════
   SERVICE
═══════════════════════════════════════════════ */
.service-item {
  display: flex;
  align-items: flex-start;
  gap: 12px;
  padding: 12px 0;
  border-bottom: 1px solid var(--border);
  font-size: 14px;
  color: var(--mid);
}
.service-item:last-child { border-bottom: none; }
.service-item .svc-dot {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background: var(--teal);
  margin-top: 7px;
  flex-shrink: 0;
}
.service-item strong { color: var(--text); }

/* ═══════════════════════════════════════════════
   FOOTER WAVE
═══════════════════════════════════════════════ */
.footer {
  margin-top: 60px;
  text-align: center;
}
.footer img { width: 100%; display: block; }
.footer-note {
  padding: 16px;
  font-size: 12px;
  color: var(--dim);
  font-style: italic;
  font-family: 'JetBrains Mono', monospace;
}

/* ═══════════════════════════════════════════════
   SCROLL REVEAL
═══════════════════════════════════════════════ */
.reveal {
  opacity: 0;
  transform: translateY(24px);
  transition: opacity 0.65s ease, transform 0.65s ease;
}
.reveal.visible {
  opacity: 1;
  transform: none;
}

/* ═══════════════════════════════════════════════
   RESPONSIVE
═══════════════════════════════════════════════ */
@media (max-width: 640px) {
  :root { --sidebar: 48px; }
  .inner { padding: 0 18px 80px; }
  .ref-grid { grid-template-columns: 1fr; }
  .badges { flex-direction: column; align-items: center; }
}
</style>
</head>
<body>

<!-- ── SCROLL PROGRESS ── -->
<div id="progress"></div>

<!-- ── DNA SIDEBAR ── -->
<div id="dna-sidebar">
  <canvas id="dna-canvas"></canvas>
</div>

<!-- ══════════════════════════════════════════
     PAGE CONTENT
══════════════════════════════════════════ -->
<div class="page">
<div class="inner">

  <!-- BANNER -->
  <div class="banner-wrap">
    <img
      src="https://raw.githubusercontent.com/AdibMiraki/AdibMiraki.github.io/main/banner.svg"
      alt="Adib Miraki Feriz — Gene Banner"
      onerror="this.style.display='none'; this.nextElementSibling.style.display='block';"
    >
    <div class="banner-fallback"></div>
  </div>

  <!-- BADGES -->
  <div class="badges">
    <a href="mailto:am74@sanger.ac.uk" class="badge badge-email">
      ✉ am74@sanger.ac.uk
    </a>
    <a href="https://lotfollahi.com/Lab/" class="badge badge-sanger" target="_blank">
      🏛 Sanger Institute · Lotfollahi Lab
    </a>
    <a href="https://scholar.google.com/citations?hl=en&user=Xz60exkAAAAJ&view_op=list_works" class="badge badge-scholar" target="_blank">
      📚 Google Scholar · Publications
    </a>
  </div>

  <hr class="divider">

  <!-- ── ABOUT ── -->
  <section class="reveal">
    <h2 class="section-heading"><span class="icon">👋</span> About Me</h2>
    <div class="about-body">
      <p>I'm a <strong>Bioinformatician</strong> at the <a href="https://lotfollahi.com/Lab/" target="_blank">Lotfollahi Lab</a>, <strong>Wellcome Sanger Institute</strong>, working at the intersection of <strong>machine learning</strong>, <strong>single-cell genomics</strong>, and <strong>spatial transcriptomics</strong>.</p>
      <p>My research focuses on decoding the language of cells — predicting how they behave, interact, and evolve across different biological contexts. I develop and apply AI-driven frameworks to uncover cellular heterogeneity and perturbation responses in complex tissues.</p>
      <div class="blockquote">"Giving cells a digital voice and letting data science do the talking."</div>
      <div class="interest-tags">
        <span class="interest-tag">🧬 Single-cell transcriptomics</span>
        <span class="interest-tag">🗺 Spatial transcriptomics</span>
        <span class="interest-tag">⚗️ Perturbation modeling</span>
        <span class="interest-tag">🧫 Tumor immunology</span>
        <span class="interest-tag">🤖 Deep learning for genomics</span>
        <span class="interest-tag">⚽ Football</span>
        <span class="interest-tag">🚴 Cycling</span>
      </div>
    </div>
  </section>

  <hr class="divider">

  <!-- ── EDUCATION ── -->
  <section class="reveal">
    <h2 class="section-heading"><span class="icon">🎓</span> Education</h2>
    <table class="data-table">
      <thead>
        <tr>
          <th>Degree</th>
          <th>Institution</th>
          <th>Period</th>
          <th>Grade</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>BSc Medical Laboratory Sciences</td>
          <td>Birjand University of Medical Sciences</td>
          <td>2019 – 2023</td>
          <td>A (Top of Class)</td>
        </tr>
      </tbody>
    </table>
  </section>

  <hr class="divider">

  <!-- ── RESEARCH EXPERIENCE ── -->
  <section class="reveal">
    <h2 class="section-heading"><span class="icon">💼</span> Research Experience</h2>
    <div class="exp-block">
<span><span class="e-icon">🏛</span>  <span class="e-inst">Wellcome Sanger Institute</span><span class="e-city">, Cambridge, UK</span></span>
<span>    <span class="e-role">On-site Bioinformatician · Lotfollahi Lab</span>                    <span class="e-date">Aug 2025 – Present</span></span>
<span class="e-gap"></span>
<span><span class="e-icon">🤝</span>  <span class="e-inst">Wellcome Sanger Institute</span><span class="e-city">, Cambridge, UK</span></span>
<span>    <span class="e-role">Research Collaborator (Remote Contract) · Lotfollahi Lab</span>     <span class="e-date">Feb 2023 – Aug 2025</span></span>
<span class="e-gap"></span>
<span><span class="e-icon">🔬</span>  <span class="e-inst">Sharif University of Technology</span><span class="e-city">, Tehran, Iran</span></span>
<span>    <span class="e-role">Research Intern</span>                                               <span class="e-date">Oct 2022 – Jan 2023</span></span>
<span class="e-gap"></span>
<span><span class="e-icon">🧫</span>  <span class="e-inst">Cellular &amp; Molecular Research Center</span><span class="e-city">, BUMS</span></span>
<span>    <span class="e-role">Research Assistant</span>                                            <span class="e-date">Apr 2021 – Sep 2022</span></span>
    </div>
  </section>

  <hr class="divider">

  <!-- ── PUBLICATIONS ── -->
  <section class="reveal">
    <h2 class="section-heading"><span class="icon">📜</span> Publications</h2>

    <!-- 2026 -->
    <div class="year-label">2026</div>

    <div class="pub-card">
      <div class="pub-chips">
        <span class="chip chip-venue">bioRxiv 2026</span>
        <span class="chip chip-first">⭐ Co-first author</span>
        <span class="chip chip-review">Under review · Nature</span>
      </div>
      <div class="pub-title">Predicting how perturbations reshape cellular trajectories with PerturbGen.</div>
      <div class="pub-authors">Ly K.C.H.*, <span class="me">Miraki Feriz A.*</span>, Isobe T., Vahidi A., Vaghari D., Rostron A., Quiroga Londoño M., Mende N., Vijayabaskar M.S., Moullet M., Rose Foster A., et al.</div>
      <div class="pub-venue-line">bioRxiv · 2026</div>
      <a class="pub-link" href="https://www.biorxiv.org/content/10.64898/2026.03.04.709254v1" target="_blank">📄 Paper Link</a>
    </div>

    <div class="pub-card">
      <div class="pub-chips">
        <span class="chip chip-bib">Briefings in Bioinformatics 2026</span>
      </div>
      <div class="pub-title">Multimodal foundation models in colorectal cancer: from prediction to trustworthy clinical insight.</div>
      <div class="pub-authors">Gharaie Amirabadi D., <span class="me">Miraki Feriz A.</span>, Safarpour H.</div>
      <div class="pub-venue-line">Briefings in Bioinformatics, Volume 27, Issue 2, March 2026</div>
      <a class="pub-link" href="https://doi.org/10.1093/bib/bbag179" target="_blank">📄 Paper Link</a>
    </div>

    <!-- 2025 -->
    <div class="year-label">2025</div>

    <div class="pub-card">
      <div class="pub-chips">
        <span class="chip chip-nature">Nature Genetics 2025</span>
      </div>
      <div class="pub-title">Quantitative characterization of cell niches in spatially resolved omics data.</div>
      <div class="pub-authors">Birk S., Bonafonte-Pardàs I., <span class="me">Miraki Feriz A.</span>, Boxall A., Agirre E., Memi F., ... &amp; Lotfollahi M.</div>
      <div class="pub-venue-line">Nature Genetics, 57:897–909, 2025</div>
      <a class="pub-link" href="https://www.nature.com/articles/s41588-025-02120-6" target="_blank">📄 Paper Link</a>
    </div>

    <div class="pub-card">
      <div class="pub-chips">
        <span class="chip chip-nature">Nature Communications 2025</span>
      </div>
      <div class="pub-title">The Hippo terminal effector YAP boosts enterovirus replication in type 1 diabetes.</div>
      <div class="pub-authors">Geravandi S., Liu H., Pahwa H., Madduri M.K., Atawneh F., <span class="me">Miraki Feriz A.</span>, ..., Gotti D.</div>
      <div class="pub-venue-line">Nature Communications, 16(1):8882, 2025</div>
      <a class="pub-link" href="https://www.nature.com/articles/s41467-025-64508-6" target="_blank">📄 Paper Link</a>
    </div>

    <!-- 2024 -->
    <div class="year-label">2024</div>

    <div class="pub-card">
      <div class="pub-chips">
        <span class="chip chip-venue">Immunobiology 2024</span>
      </div>
      <div class="pub-title">Targeting the dynamic transcriptional landscape of Treg subpopulations in pancreatic ductal adenocarcinoma: Insights from scRNA-seq with a focus on CTLA4 and TIGIT.</div>
      <div class="pub-authors"><span class="me">Miraki Feriz A.</span>, Khosrojerdi A., Erfanian N., Azarkar S., Sajjadi S.M., ..., Racanelli V.</div>
      <div class="pub-venue-line">Immunobiology, 229(4):152822, 2024</div>
      <a class="pub-link" href="https://www.sciencedirect.com/science/article/pii/S0171298524000408" target="_blank">📄 Paper Link</a>
    </div>

    <div class="pub-card">
      <div class="pub-chips">
        <span class="chip chip-venue">Heliyon 2024</span>
      </div>
      <div class="pub-title">Tumor-infiltrating CD8+ sub-populations in primary and recurrent glioblastoma: An in-silico study.</div>
      <div class="pub-authors">Shadbad M.A., <span class="me">Miraki Feriz A.</span>, Baradaran B., Safarpour H.</div>
      <div class="pub-venue-line">Heliyon, 10(5):e27329, 2024</div>
      <a class="pub-link" href="https://www.sciencedirect.com/science/article/pii/S2405844024033607" target="_blank">📄 Paper Link</a>
    </div>

    <div class="pub-card">
      <div class="pub-chips">
        <span class="chip chip-venue">Heliyon 2024</span>
      </div>
      <div class="pub-title">Holistic exploration of CHGA and hsa-miR-137 in colorectal cancer via multi-omic data integration.</div>
      <div class="pub-authors">Safarpour H., Ranjbaran J., Erfanian N., Nomiri S., Derakhshani A., Gerarduzzi C., <span class="me">Miraki Feriz A.</span>, ..., Silvestris N.</div>
      <div class="pub-venue-line">Heliyon, 2024</div>
      <a class="pub-link" href="https://www.cell.com/heliyon/fulltext/S2405-8440(24)03077-9" target="_blank">📄 Paper Link</a>
    </div>

    <!-- 2023 -->
    <div class="year-label">2023</div>

    <div class="pub-card">
      <div class="pub-chips">
        <span class="chip chip-venue">Heliyon 2023</span>
      </div>
      <div class="pub-title">Single-cell RNA sequencing uncovers heterogeneous transcriptional signatures in tumor-infiltrated dendritic cells in prostate cancer.</div>
      <div class="pub-authors"><span class="me">Miraki Feriz A.</span>, Khosrojerdi A., Lotfollahi M., Shamsaki N., ..., Saghafi S., Leone P.</div>
      <div class="pub-venue-line">Heliyon, 9(5):e15694, 2023</div>
      <a class="pub-link" href="https://www.sciencedirect.com/science/article/pii/S2405844023029018" target="_blank">📄 Paper Link</a>
    </div>

    <div class="pub-card">
      <div class="pub-chips">
        <span class="chip chip-plos">PLOS ONE 2023</span>
      </div>
      <div class="pub-title">Deciphering the immune landscape of head and neck squamous cell carcinoma: A single-cell transcriptomic analysis of regulatory T cell responses to PD-1 blockade therapy.</div>
      <div class="pub-authors"><span class="me">Miraki Feriz A.</span>, Bahraini F., Khosrojerdi A., Azarkar S., ..., Safarpour H.</div>
      <div class="pub-venue-line">PLOS ONE, 18(12):e0295863, 2023</div>
      <a class="pub-link" href="https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0295863" target="_blank">📄 Paper Link</a>
    </div>

    <div class="pub-card">
      <div class="pub-chips">
        <span class="chip chip-venue">Scientific Reports 2023</span>
      </div>
      <div class="pub-title">Characterization of Wnt signaling pathway under treatment of Lactobacillus acidophilus postbiotic in colorectal cancer using an integrated in silico and in vitro analysis.</div>
      <div class="pub-authors">Erfanian N., Nasseri S., <span class="me">Miraki Feriz A.</span>, Safarpour H., Namaie M.H.</div>
      <div class="pub-venue-line">Scientific Reports, 13(1):22988, 2023</div>
      <a class="pub-link" href="https://www.nature.com/articles/s41598-023-50047-x" target="_blank">📄 Paper Link</a>
    </div>

    <div class="pub-card">
      <div class="pub-chips">
        <span class="chip chip-bib">Biomedicine &amp; Pharmacotherapy 2023</span>
      </div>
      <div class="pub-title">Deep learning applications in single-cell genomics and transcriptomics data analysis.</div>
      <div class="pub-authors">Erfanian N., Heydari A.A., <span class="me">Miraki Feriz A.</span>, Iañez P., Derakhshani A., ..., Sahebkar A.</div>
      <div class="pub-venue-line">Biomedicine &amp; Pharmacotherapy, 165:115077, 2023</div>
      <a class="pub-link" href="https://www.sciencedirect.com/science/article/pii/S0753332223008685" target="_blank">📄 Paper Link</a>
    </div>

    <div class="pub-card">
      <div class="pub-chips">
        <span class="chip chip-venue">Life Sciences 2023</span>
      </div>
      <div class="pub-title">Putative role of glial cells in treatment resistance depression: An updated critical literature review and evaluation of single-nuclei transcriptomics data.</div>
      <div class="pub-authors">Sanadgol N., <span class="me">Miraki Feriz A.</span>, Lisboa S.F., Joca S.R.</div>
      <div class="pub-venue-line">Life Sciences, 331:122025, 2023</div>
      <a class="pub-link" href="https://www.sciencedirect.com/science/article/abs/pii/S0024320523006604" target="_blank">📄 Paper Link</a>
    </div>

    <!-- 2022 -->
    <div class="year-label">2022</div>

    <div class="pub-card">
      <div class="pub-chips">
        <span class="chip chip-bib">Biomedicine &amp; Pharmacotherapy 2022</span>
      </div>
      <div class="pub-title">The expression pattern of VISTA in the PBMCs of relapsing-remitting multiple sclerosis patients: A single-cell RNA sequencing-based study.</div>
      <div class="pub-authors">Derakhshani A., Asadzadeh Z., Baradaran B., Safarpour H., Rahmani S., Leone P., Shadbad M.A., ..., <span class="me">Miraki Feriz A.</span>, ..., Ahmadi H.</div>
      <div class="pub-venue-line">Biomedicine &amp; Pharmacotherapy, 148:112725, 2022</div>
      <a class="pub-link" href="https://www.sciencedirect.com/science/article/pii/S0753332222001135" target="_blank">📄 Paper Link</a>
    </div>

  </section>

  <hr class="divider">

  <!-- ── HONORS & AWARDS ── -->
  <section class="reveal">
    <h2 class="section-heading"><span class="icon">🏆</span> Honors &amp; Awards</h2>
    <table class="data-table award-table">
      <thead>
        <tr><th>Year</th><th>Award</th></tr>
      </thead>
      <tbody>
        <tr><td>2025</td><td>🥈 Rank 2nd — AI Hackathon, Birjand University of Medical Sciences</td></tr>
        <tr><td>2023</td><td>🏅 Best Researcher of Iran among Undergraduate Students (National)</td></tr>
        <tr><td>2023</td><td>🏅 Best Researcher — Birjand University of Medical Sciences</td></tr>
        <tr><td>2022</td><td>🏅 Best Researcher — Birjand University of Medical Sciences</td></tr>
        <tr><td>2022</td><td>🎤 Best Oral Presenter — 9th International Congress of Medical Students</td></tr>
      </tbody>
    </table>
  </section>

  <hr class="divider">

  <!-- ── ACADEMIC SERVICE ── -->
  <section class="reveal">
    <h2 class="section-heading"><span class="icon">📝</span> Academic Service</h2>
    <div class="service-item">
      <div class="svc-dot"></div>
      <div><strong>Invited Reviewer</strong> — <em>Briefings in Bioinformatics</em> (Oxford University Press)</div>
    </div>
  </section>

  <hr class="divider">

  <!-- ── REFERENCES ── -->
  <section class="reveal">
    <h2 class="section-heading"><span class="icon">🤝</span> References</h2>
    <div class="ref-grid">
      <div class="ref-card">
        <div class="ref-name">Prof. Muzlifah Haniffa</div>
        <div class="ref-role">Senior Group Leader<br>Wellcome Sanger Institute &amp; University of Cambridge</div>
      </div>
      <div class="ref-card">
        <div class="ref-name">Dr. Ömer Ali Bayraktar</div>
        <div class="ref-role">Group Leader<br>Wellcome Sanger Institute</div>
      </div>
      <div class="ref-card">
        <div class="ref-name">Dr. Mohammad Lotfollahi</div>
        <div class="ref-role">Group Leader · Supervisor<br>Wellcome Sanger Institute</div>
      </div>
    </div>
    <p style="font-size:12px; color:var(--dim); font-style:italic; font-family:'JetBrains Mono',monospace;">
      Available upon request for academic and research positions.
    </p>
  </section>

  <!-- FOOTER -->
  <div class="footer">
    <img
      src="https://capsule-render.vercel.app/api?type=waving&color=0:2c5364,50:203a43,100:0f2027&height=100&section=footer"
      alt=""
      onerror="this.style.display='none'"
    >
    <div class="footer-note">Adib Miraki Feriz · Wellcome Sanger Institute · Cambridge, UK</div>
  </div>

</div><!-- /inner -->
</div><!-- /page -->


<!-- ══════════════════════════════════════════
     JAVASCRIPT
══════════════════════════════════════════ -->
<script>
'use strict';

/* ─── scroll state ─── */
let scrollRatio = 0;
window.addEventListener('scroll', () => {
  const max = document.documentElement.scrollHeight - innerHeight || 1;
  scrollRatio = window.scrollY / max;
  document.getElementById('progress').style.transform = `scaleX(${scrollRatio})`;
}, { passive: true });

/* ─── reveal on scroll ─── */
const revealObs = new IntersectionObserver(entries => {
  entries.forEach(e => { if (e.isIntersecting) e.target.classList.add('visible'); });
}, { threshold: 0.08 });
document.querySelectorAll('.reveal').forEach(el => revealObs.observe(el));

/* ══════════════════════════════════════════
   DNA HELIX — LEFT SIDEBAR
══════════════════════════════════════════ */
(function initDNA() {
  const sidebar = document.getElementById('dna-sidebar');
  const canvas  = document.getElementById('dna-canvas');
  const ctx     = canvas.getContext('2d');
  let W, H, dpr;

  function resize() {
    dpr = window.devicePixelRatio || 1;
    W = canvas.width  = sidebar.offsetWidth  * dpr;
    H = canvas.height = sidebar.offsetHeight * dpr;
  }
  resize();
  window.addEventListener('resize', resize);

  /* Base pair data */
  const BASES  = ['A', 'T', 'C', 'G'];
  const PAIR   = { A:'T', T:'A', C:'G', G:'C' };
  const BCOLOR = {
    A: '#009e8e',  /* teal  */
    T: '#5c35a8',  /* violet*/
    C: '#1a78c2',  /* blue  */
    G: '#b08000',  /* gold  */
  };
  /* strand colors */
  const S1_COLOR = '#00a896'; /* teal   */
  const S2_COLOR = '#5c35a8'; /* violet */

  let offset = 0; /* drives continuous upward scroll */

  function frame() {
    ctx.clearRect(0, 0, W, H);

    /* speed: base 0.7, up to +2 as user scrolls */
    const speed = 0.7 + scrollRatio * 2.2;
    offset = (offset + speed) % 1000000; /* prevent overflow */

    const cx          = W / 2;
    const amp         = W * 0.28;           /* ± swing from center */
    const rungSpacing = 28 * dpr;           /* vertical gap between rungs */
    const freq        = (2 * Math.PI) / (rungSpacing * 7); /* one full twist per 7 rungs */
    const totalRungs  = Math.ceil(H / rungSpacing) + 3;

    /* We draw rungs from top to bottom, but offset makes them scroll upward */
    const shift = offset % rungSpacing;

    for (let i = 0; i < totalRungs; i++) {
      const y     = i * rungSpacing - shift;
      const phase = (y + offset) * freq;   /* continuous phase */

      const x1 = cx + Math.sin(phase)            * amp;
      const x2 = cx + Math.sin(phase + Math.PI)  * amp;

      /* z-depth: 0 = back, 1 = front */
      const depth = (Math.sin(phase) + 1) * 0.5;
      const alpha = 0.35 + depth * 0.65;

      /* ── backbone: connect to next rung ── */
      if (i < totalRungs - 1) {
        const y2      = (i + 1) * rungSpacing - shift;
        const phase2  = (y2 + offset) * freq;
        const nx1     = cx + Math.sin(phase2)           * amp;
        const nx2     = cx + Math.sin(phase2 + Math.PI) * amp;

        /* strand 1 */
        ctx.beginPath();
        ctx.moveTo(x1, y);
        ctx.lineTo(nx1, y2);
        ctx.strokeStyle = `rgba(0,168,150,${alpha * 0.6})`;
        ctx.lineWidth   = 2.2 * dpr;
        ctx.lineCap     = 'round';
        ctx.stroke();

        /* strand 2 */
        ctx.beginPath();
        ctx.moveTo(x2, y);
        ctx.lineTo(nx2, y2);
        ctx.strokeStyle = `rgba(92,53,168,${alpha * 0.6})`;
        ctx.lineWidth   = 2.2 * dpr;
        ctx.stroke();
      }

      /* ── rung (base pair) — only when strands are spread ── */
      const spread = Math.abs(x1 - x2);
      if (spread > amp * 0.5) {
        /* gradient rung line */
        const gr = ctx.createLinearGradient(x1, y, x2, y);
        gr.addColorStop(0,   `rgba(0,168,150,${alpha * 0.55})`);
        gr.addColorStop(0.5, `rgba(180,180,200,${alpha * 0.15})`);
        gr.addColorStop(1,   `rgba(92,53,168,${alpha * 0.55})`);
        ctx.beginPath();
        ctx.moveTo(x1, y);
        ctx.lineTo(x2, y);
        ctx.strokeStyle = gr;
        ctx.lineWidth   = 1.3 * dpr;
        ctx.stroke();

        /* base-pair pill label */
        const base = BASES[Math.round(Math.abs(offset / rungSpacing) + i) % 4];
        const comp = PAIR[base];
        const mx   = (x1 + x2) / 2;
        const label = base + '-' + comp;

        ctx.save();
        ctx.font         = `${7 * dpr}px 'JetBrains Mono', monospace`;
        ctx.textAlign    = 'center';
        ctx.textBaseline = 'middle';

        /* pill bg */
        const tw = ctx.measureText(label).width + 7 * dpr;
        const th = 10 * dpr;
        ctx.fillStyle = 'rgba(255,255,255,0.80)';
        ctx.beginPath();
        if (ctx.roundRect) {
          ctx.roundRect(mx - tw / 2, y - th / 2, tw, th, 3 * dpr);
        } else {
          ctx.rect(mx - tw / 2, y - th / 2, tw, th);
        }
        ctx.fill();

        /* label text */
        ctx.fillStyle = BCOLOR[base];
        ctx.globalAlpha = alpha;
        ctx.fillText(label, mx, y);
        ctx.globalAlpha = 1;
        ctx.restore();
      }

      /* ── backbone node dots ── */
      const rDot = (2.5 + depth * 2.2) * dpr;

      /* dot 1 — teal */
      ctx.beginPath();
      ctx.arc(x1, y, rDot, 0, Math.PI * 2);
      ctx.fillStyle   = S1_COLOR;
      ctx.globalAlpha = alpha;
      ctx.shadowColor = '#00c4b0';
      ctx.shadowBlur  = 7 * dpr * depth;
      ctx.fill();

      /* dot 2 — violet */
      ctx.beginPath();
      ctx.arc(x2, y, rDot, 0, Math.PI * 2);
      ctx.fillStyle   = S2_COLOR;
      ctx.shadowColor = '#7b5fc8';
      ctx.shadowBlur  = 7 * dpr * depth;
      ctx.fill();

      ctx.globalAlpha = 1;
      ctx.shadowBlur  = 0;
    }

    requestAnimationFrame(frame);
  }

  frame();
})();
</script>
</body>
</html>
