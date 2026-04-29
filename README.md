<img width="900" height="220" alt="banner" src="https://github.com/user-attachments/assets/39246d92-c7d0-4481-a8c7-827e4692bb5f" />![<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 900 220" width="900" height="220">
  <defs>
    <linearGradient id="bg" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%"   stop-color="#030b14"/>
      <stop offset="50%"  stop-color="#071826"/>
      <stop offset="100%" stop-color="#030f1c"/>
    </linearGradient>
    <radialGradient id="vignette" cx="50%" cy="50%" r="70%">
      <stop offset="0%"   stop-color="#030b14" stop-opacity="0"/>
      <stop offset="100%" stop-color="#030b14" stop-opacity="0.68"/>
    </radialGradient>
    <filter id="nameglow" x="-20%" y="-50%" width="140%" height="200%">
      <feGaussianBlur stdDeviation="5" result="blur"/>
      <feMerge><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>
    <style>
      @keyframes drift1 { 0%{transform:translateY(220px)} 100%{transform:translateY(-30px)} }
      @keyframes drift2 { 0%{transform:translateY(220px) translateX(0)} 100%{transform:translateY(-30px) translateX(14px)} }
      @keyframes drift3 { 0%{transform:translateY(220px) translateX(0)} 100%{transform:translateY(-30px) translateX(-10px)} }
      @keyframes drift4 { 0%{transform:translateY(220px) translateX(0)} 100%{transform:translateY(-30px) translateX(22px)} }
      @keyframes drift5 { 0%{transform:translateY(220px) translateX(0)} 100%{transform:translateY(-30px) translateX(-22px)} }
      @keyframes fade   { 0%{opacity:0} 10%{opacity:1} 85%{opacity:0.7} 100%{opacity:0} }
      @keyframes pulse  { 0%,100%{opacity:0.85} 50%{opacity:1} }
      @keyframes helixscroll { 0%{transform:translateY(0)} 100%{transform:translateY(-22px)} }
      .gene {
        font-family: 'Courier New', Courier, monospace;
        animation-timing-function: linear;
        animation-iteration-count: infinite;
        animation-name: fade;
      }
    </style>
  </defs>

  <!-- Background -->
  <rect width="900" height="220" fill="url(#bg)"/>

  <!-- DNA helix left (animated scroll) -->
  <g opacity="0.13" style="animation: helixscroll 2.6s linear infinite">
    <path d="M42,0 Q56,11 42,22 Q28,33 42,44 Q56,55 42,66 Q28,77 42,88 Q56,99 42,110 Q28,121 42,132 Q56,143 42,154 Q28,165 42,176 Q56,187 42,198 Q28,209 42,240" stroke="#4ab8ff" stroke-width="1.4" fill="none"/>
    <path d="M65,0 Q51,11 65,22 Q79,33 65,44 Q51,55 65,66 Q79,77 65,88 Q51,99 65,110 Q79,121 65,132 Q51,143 65,154 Q79,165 65,176 Q51,187 65,198 Q79,209 65,240" stroke="#4ab8ff" stroke-width="1.4" fill="none"/>
    <line x1="42" y1="22"  x2="65" y2="22"  stroke="#4ab8ff" stroke-width="0.9"/>
    <line x1="42" y1="44"  x2="65" y2="44"  stroke="#4ab8ff" stroke-width="0.9"/>
    <line x1="42" y1="66"  x2="65" y2="66"  stroke="#4ab8ff" stroke-width="0.9"/>
    <line x1="42" y1="88"  x2="65" y2="88"  stroke="#4ab8ff" stroke-width="0.9"/>
    <line x1="42" y1="110" x2="65" y2="110" stroke="#4ab8ff" stroke-width="0.9"/>
    <line x1="42" y1="132" x2="65" y2="132" stroke="#4ab8ff" stroke-width="0.9"/>
    <line x1="42" y1="154" x2="65" y2="154" stroke="#4ab8ff" stroke-width="0.9"/>
    <line x1="42" y1="176" x2="65" y2="176" stroke="#4ab8ff" stroke-width="0.9"/>
    <line x1="42" y1="198" x2="65" y2="198" stroke="#4ab8ff" stroke-width="0.9"/>
    <line x1="42" y1="220" x2="65" y2="220" stroke="#4ab8ff" stroke-width="0.9"/>
  </g>

  <!-- DNA helix right (animated scroll, offset phase) -->
  <g opacity="0.13" style="animation: helixscroll 2.6s linear infinite; animation-delay:-1.3s">
    <path d="M835,0 Q849,11 835,22 Q821,33 835,44 Q849,55 835,66 Q821,77 835,88 Q849,99 835,110 Q821,121 835,132 Q849,143 835,154 Q821,165 835,176 Q849,187 835,198 Q821,209 835,240" stroke="#4ab8ff" stroke-width="1.4" fill="none"/>
    <path d="M858,0 Q844,11 858,22 Q872,33 858,44 Q844,55 858,66 Q872,77 858,88 Q844,99 858,110 Q872,121 858,132 Q844,143 858,154 Q872,165 858,176 Q844,187 858,198 Q872,209 858,240" stroke="#4ab8ff" stroke-width="1.4" fill="none"/>
    <line x1="835" y1="22"  x2="858" y2="22"  stroke="#4ab8ff" stroke-width="0.9"/>
    <line x1="835" y1="44"  x2="858" y2="44"  stroke="#4ab8ff" stroke-width="0.9"/>
    <line x1="835" y1="66"  x2="858" y2="66"  stroke="#4ab8ff" stroke-width="0.9"/>
    <line x1="835" y1="88"  x2="858" y2="88"  stroke="#4ab8ff" stroke-width="0.9"/>
    <line x1="835" y1="110" x2="858" y2="110" stroke="#4ab8ff" stroke-width="0.9"/>
    <line x1="835" y1="132" x2="858" y2="132" stroke="#4ab8ff" stroke-width="0.9"/>
    <line x1="835" y1="154" x2="858" y2="154" stroke="#4ab8ff" stroke-width="0.9"/>
    <line x1="835" y1="176" x2="858" y2="176" stroke="#4ab8ff" stroke-width="0.9"/>
    <line x1="835" y1="198" x2="858" y2="198" stroke="#4ab8ff" stroke-width="0.9"/>
    <line x1="835" y1="220" x2="858" y2="220" stroke="#4ab8ff" stroke-width="0.9"/>
  </g>

  <!-- ═══ FLOATING GENE LABELS ═══ -->
  <!-- Each gene: unique x start, font-size, color, animation-duration, animation-delay -->

  <text class="gene" x="92"  font-size="9"  fill="#7dd3f8" style="animation-name:drift1;animation-duration:9s;animation-delay:0s">FOXP3</text>
  <text class="gene" x="155" font-size="8"  fill="#a5f3fc" style="animation-name:drift2;animation-duration:11s;animation-delay:1.2s">scRNA-seq</text>
  <text class="gene" x="238" font-size="9"  fill="#67e8f9" style="animation-name:drift3;animation-duration:8.5s;animation-delay:0.4s">CTLA4</text>
  <text class="gene" x="308" font-size="8"  fill="#7dd3f8" style="animation-name:drift4;animation-duration:10s;animation-delay:2.1s">PerturbGen</text>
  <text class="gene" x="405" font-size="9"  fill="#bae6fd" style="animation-name:drift1;animation-duration:12s;animation-delay:0.8s">TIGIT</text>
  <text class="gene" x="468" font-size="8"  fill="#93c5fd" style="animation-name:drift5;animation-duration:9.5s;animation-delay:3s">NicheCompass</text>
  <text class="gene" x="608" font-size="9"  fill="#7dd3f8" style="animation-name:drift2;animation-duration:10.5s;animation-delay:1.5s">UMAP</text>
  <text class="gene" x="668" font-size="8"  fill="#a5f3fc" style="animation-name:drift3;animation-duration:8s;animation-delay:0.2s">PD-1</text>
  <text class="gene" x="728" font-size="9"  fill="#67e8f9" style="animation-name:drift4;animation-duration:11.5s;animation-delay:2.5s">CD8+</text>
  <text class="gene" x="792" font-size="8"  fill="#bae6fd" style="animation-name:drift1;animation-duration:9s;animation-delay:1.8s">YAP</text>

  <text class="gene" x="108" font-size="8"  fill="#93c5fd" style="animation-name:drift3;animation-duration:13s;animation-delay:4s">Treg</text>
  <text class="gene" x="182" font-size="9"  fill="#7dd3f8" style="animation-name:drift1;animation-duration:10s;animation-delay:5.5s">KRAS</text>
  <text class="gene" x="258" font-size="8"  fill="#a5f3fc" style="animation-name:drift2;animation-duration:8s;animation-delay:3.3s">IL1B</text>
  <text class="gene" x="338" font-size="9"  fill="#67e8f9" style="animation-name:drift4;animation-duration:11s;animation-delay:6s">Spatial</text>
  <text class="gene" x="428" font-size="8"  fill="#bae6fd" style="animation-name:drift5;animation-duration:9s;animation-delay:4.7s">GBM</text>
  <text class="gene" x="508" font-size="9"  fill="#93c5fd" style="animation-name:drift1;animation-duration:12s;animation-delay:2.8s">TME</text>
  <text class="gene" x="572" font-size="8"  fill="#7dd3f8" style="animation-name:drift3;animation-duration:10.5s;animation-delay:5s">PDAC</text>
  <text class="gene" x="642" font-size="9"  fill="#a5f3fc" style="animation-name:drift2;animation-duration:8.5s;animation-delay:3.8s">snRNA</text>
  <text class="gene" x="708" font-size="8"  fill="#67e8f9" style="animation-name:drift4;animation-duration:9.5s;animation-delay:1s">WGCNA</text>
  <text class="gene" x="772" font-size="9"  fill="#bae6fd" style="animation-name:drift1;animation-duration:11s;animation-delay:4.2s">SFRP1</text>

  <text class="gene" x="128" font-size="8"  fill="#67e8f9" style="animation-name:drift2;animation-duration:9s;animation-delay:7s">LAG-3</text>
  <text class="gene" x="208" font-size="9"  fill="#7dd3f8" style="animation-name:drift5;animation-duration:11s;animation-delay:6.5s">GZMK</text>
  <text class="gene" x="282" font-size="8"  fill="#93c5fd" style="animation-name:drift1;animation-duration:8s;animation-delay:7.8s">NKG2D</text>
  <text class="gene" x="368" font-size="9"  fill="#a5f3fc" style="animation-name:drift3;animation-duration:10s;animation-delay:7.2s">HLA-E</text>
  <text class="gene" x="452" font-size="8"  fill="#bae6fd" style="animation-name:drift4;animation-duration:12s;animation-delay:8s">VISTA</text>
  <text class="gene" x="532" font-size="9"  fill="#67e8f9" style="animation-name:drift2;animation-duration:9.5s;animation-delay:6.8s">AQP4</text>
  <text class="gene" x="597" font-size="8"  fill="#7dd3f8" style="animation-name:drift5;animation-duration:10s;animation-delay:8.5s">CD44</text>
  <text class="gene" x="657" font-size="9"  fill="#93c5fd" style="animation-name:drift1;animation-duration:8.5s;animation-delay:7.5s">SLC1A2</text>
  <text class="gene" x="752" font-size="8"  fill="#a5f3fc" style="animation-name:drift3;animation-duration:11.5s;animation-delay:6.2s">MMP7</text>
  <text class="gene" x="812" font-size="9"  fill="#bae6fd" style="animation-name:drift4;animation-duration:9s;animation-delay:7s">GZMA</text>

  <text class="gene" x="100" font-size="8"  fill="#a5f3fc" style="animation-name:drift4;animation-duration:10s;animation-delay:9.5s">β-cell</text>
  <text class="gene" x="175" font-size="8"  fill="#67e8f9" style="animation-name:drift2;animation-duration:12s;animation-delay:10s">Lotfollahi</text>
  <text class="gene" x="268" font-size="9"  fill="#bae6fd" style="animation-name:drift1;animation-duration:9s;animation-delay:9.2s">CVB</text>
  <text class="gene" x="325" font-size="8"  fill="#93c5fd" style="animation-name:drift3;animation-duration:11s;animation-delay:10.5s">diffusion</text>
  <text class="gene" x="420" font-size="9"  fill="#7dd3f8" style="animation-name:drift5;animation-duration:8.5s;animation-delay:9.8s">scVI</text>
  <text class="gene" x="480" font-size="8"  fill="#a5f3fc" style="animation-name:drift4;animation-duration:10.5s;animation-delay:11s">Cambridge</text>
  <text class="gene" x="580" font-size="9"  fill="#67e8f9" style="animation-name:drift2;animation-duration:9s;animation-delay:10.2s">Sanger</text>
  <text class="gene" x="645" font-size="8"  fill="#bae6fd" style="animation-name:drift1;animation-duration:11.5s;animation-delay:9s">Nature</text>
  <text class="gene" x="710" font-size="9"  fill="#93c5fd" style="animation-name:drift3;animation-duration:8s;animation-delay:11.5s">NOTCH</text>
  <text class="gene" x="775" font-size="8"  fill="#7dd3f8" style="animation-name:drift5;animation-duration:10s;animation-delay:10.8s">VAE</text>

  <!-- Vignette overlay -->
  <rect width="900" height="220" fill="url(#vignette)"/>

  <!-- Name text -->
  <text
    x="450" y="102"
    font-family="'Trebuchet MS', 'Segoe UI', sans-serif"
    font-size="40"
    font-weight="700"
    fill="white"
    text-anchor="middle"
    letter-spacing="5"
    filter="url(#nameglow)"
    style="animation: pulse 3.5s ease-in-out infinite"
  >ADIB MIRAKI FERIZ</text>

  <!-- Subtitle -->
  <text
    x="450" y="138"
    font-family="Georgia, 'Times New Roman', serif"
    font-size="13.5"
    font-style="italic"
    fill="#7dd3f8"
    text-anchor="middle"
    letter-spacing="2.5"
    opacity="0.88"
  >Bioinformatician · Wellcome Sanger Institute</text>

  <!-- Decorative line -->
  <line x1="260" y1="148" x2="640" y2="148" stroke="#4ab8ff" stroke-width="0.5" opacity="0.3"/>

</svg>
Uploading banner.svg…]()


## 👋 About Me

I'm a **Bioinformatician** at the [Lotfollahi Lab](https://www.sanger.ac.uk/group/lotfollahi-group/), **Wellcome Sanger Institute**, working at the intersection of **machine learning**, **single-cell genomics**, and **spatial transcriptomics**.

My research focuses on decoding the language of cells — predicting how they behave, interact, and evolve across different biological contexts. I develop and apply AI-driven frameworks to uncover cellular heterogeneity and perturbation responses in complex tissues.

> *"Giving cells a digital voice and letting data science do the talking."*

🧬 **Research Interests:** Single-cell & spatial transcriptomics · Perturbation modeling · Tumor immunology · Deep learning for genomics  
⚽🚴 **Outside the lab:** Football · Cycling · Endless curiosity

---

## 🎓 Education

| Degree | Institution | Period | Grade |
|--------|------------|--------|-------|
| BSc Medical Laboratory Sciences | Birjand University of Medical Sciences | 2019 – 2023 | A (Top of Class) |

---

## 💼 Research Experience

```
🏛  Wellcome Sanger Institute, Cambridge, UK
    On-site Bioinformatician · Lotfollahi Lab                    Aug 2025 – Present

🤝  Wellcome Sanger Institute, Cambridge, UK
    Research Collaborator (Remote Contract) · Lotfollahi Lab     Feb 2023 – Aug 2025

🔬  Sharif University of Technology, Tehran, Iran
    Research Intern                                               Oct 2022 – Jan 2023

🧫  Cellular & Molecular Research Center, BUMS
    Research Associate                                            Apr 2021 – Sep 2022
```

---

## 📜 Publications

### 2026

**Ly K.C.H.\*, Miraki Feriz A.\*, Isobe T., Vahidi A., Vaghari D., Rostron A., Quiroga Londoño M., Mende N., Vijayabaskar M.S., Moullet M., Rose Foster A., et al.**  
*Predicting how perturbations reshape cellular trajectories with PerturbGen.*  
**bioRxiv** 2026 — ⭐ *Co-first author · Under review at **Nature*** · [📄 Paper Link](https://www.biorxiv.org/content/10.64898/2026.03.04.709254v1)

---

**Gharaie Amirabadi D., Miraki Feriz A., Safarpour H.**  
*Multimodal foundation models in colorectal cancer: from prediction to trustworthy clinical insight.*  
**Briefings in Bioinformatics**, Volume 27, Issue 2, March 2026 · [📄 Paper Link](https://doi.org/10.1093/bib/bbag179)

---

### 2025

**Birk S., Bonafonte-Pardàs I., Miraki Feriz A., Boxall A., Agirre E., Memi F., ... & Lotfollahi M.**  
*Quantitative characterization of cell niches in spatially resolved omics data.*  
**Nature Genetics**, 57:897–909, 2025 · [📄 Paper Link](https://www.nature.com/articles/s41588-025-02120-6)

---

**Geravandi S., Liu H., Pahwa H., Madduri M.K., Atawneh F., Miraki Feriz A., ..., Gotti D.**  
*The Hippo terminal effector YAP boosts enterovirus replication in type 1 diabetes.*  
**Nature Communications**, 16(1):8882, 2025 · [📄 Paper Link](https://www.nature.com/articles/s41467-025-64508-6)

---

### 2024

**Miraki Feriz A., Khosrojerdi A., Erfanian N., Azarkar S., Sajjadi S.M., ..., Racanelli V.**  
*Targeting the dynamic transcriptional landscape of Treg subpopulations in pancreatic ductal adenocarcinoma: Insights from scRNA-seq with a focus on CTLA4 and TIGIT.*  
**Immunobiology**, 229(4):152822, 2024 · [📄 Paper Link](https://www.sciencedirect.com/science/article/pii/S0171298524000408)

---

**Shadbad M.A., Miraki Feriz A., Baradaran B., Safarpour H.**  
*Tumor-infiltrating CD8+ sub-populations in primary and recurrent glioblastoma: An in-silico study.*  
**Heliyon**, 10(5):e27329, 2024 · [📄 Paper Link](https://www.sciencedirect.com/science/article/pii/S2405844024033607)

---

**Safarpour H., Ranjbaran J., Erfanian N., Nomiri S., Derakhshani A., Gerarduzzi C., Miraki Feriz A., ..., Silvestris N.**  
*Holistic exploration of CHGA and hsa-miR-137 in colorectal cancer via multi-omic data integration.*  
**Heliyon**, 2024 · [📄 Paper Link](https://www.cell.com/heliyon/fulltext/S2405-8440(24)03077-9)

---

### 2023

**Miraki Feriz A., Khosrojerdi A., Lotfollahi M., Shamsaki N., ..., Saghafi S., Leone P.**  
*Single-cell RNA sequencing uncovers heterogeneous transcriptional signatures in tumor-infiltrated dendritic cells in prostate cancer.*  
**Heliyon**, 9(5):e15694, 2023 · [📄 Paper Link](https://www.sciencedirect.com/science/article/pii/S2405844023029018)

---

**Miraki Feriz A., Bahraini F., Khosrojerdi A., Azarkar S., ..., Safarpour H.**  
*Deciphering the immune landscape of head and neck squamous cell carcinoma: A single-cell transcriptomic analysis of regulatory T cell responses to PD-1 blockade therapy.*  
**PLOS ONE**, 18(12):e0295863, 2023 · [📄 Paper Link](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0295863)

---

**Erfanian N., Nasseri S., Miraki Feriz A., Safarpour H., Namaie M.H.**  
*Characterization of Wnt signaling pathway under treatment of Lactobacillus acidophilus postbiotic in colorectal cancer using an integrated in silico and in vitro analysis.*  
**Scientific Reports**, 13(1):22988, 2023 · [📄 Paper Link](https://www.nature.com/articles/s41598-023-50047-x)

---

**Erfanian N., Heydari A.A., Miraki Feriz A., Iañez P., Derakhshani A., ..., Sahebkar A.**  
*Deep learning applications in single-cell genomics and transcriptomics data analysis.*  
**Biomedicine & Pharmacotherapy**, 165:115077, 2023 · [📄 Paper Link](https://www.sciencedirect.com/science/article/pii/S0753332223008685)

---

**Sanadgol N., Miraki Feriz A., Lisboa S.F., Joca S.R.**  
*Putative role of glial cells in treatment resistance depression: An updated critical literature review and evaluation of single-nuclei transcriptomics data.*  
**Life Sciences**, 331:122025, 2023 · [📄 Paper Link](https://www.sciencedirect.com/science/article/abs/pii/S0024320523006604)

---

### 2022

**Derakhshani A., Asadzadeh Z., Baradaran B., Safarpour H., Rahmani S., Leone P., Shadbad M.A., ..., Miraki Feriz A., ..., Ahmadi H.**  
*The expression pattern of VISTA in the PBMCs of relapsing-remitting multiple sclerosis patients: A single-cell RNA sequencing-based study.*  
**Biomedicine & Pharmacotherapy**, 148:112725, 2022 · [📄 Paper Link](https://www.sciencedirect.com/science/article/pii/S0753332222001135)

---

## 🏆 Honors & Awards

| Year | Award |
|------|-------|
| 2025 | 🥈 Rank 2nd — AI Hackathon, Birjand University of Medical Sciences |
| 2023 | 🏅 Best Researcher of Iran among Undergraduate Students (National) |
| 2023 | 🏅 Best Researcher — Birjand University of Medical Sciences |
| 2022 | 🏅 Best Researcher — Birjand University of Medical Sciences |
| 2022 | 🎤 Best Oral Presenter — 9th International Congress of Medical Students |

---

## 📝 Academic Service

- **Invited Reviewer** — *Briefings in Bioinformatics* (Oxford University Press)

---

## 🤝 References

| Name | Role |
|------|------|
| **Prof. Muzlifah Haniffa** | Senior Group Leader, Wellcome Sanger Institute & University of Cambridge |
| **Dr. Ömer Ali Bayraktar** | Group Leader, Wellcome Sanger Institute |
| **Dr. Mohammad Lotfollahi** | Group Leader, Wellcome Sanger Institute (Supervisor) |

---

<div align="center">

*Available upon request for academic and research positions.*

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:2c5364,50:203a43,100:0f2027&height=100&section=footer" />

</div>
