---
title:
description: AccuKnox Help Center is a one-stop destination for all your queries related to AccuKnox products. Get started with our product documentation, FAQs, and more.
hide:
  - navigation
  - toc
---

<style>
  @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800;900&display=swap');

  /* Reset & Base */
  h1 {
      display: none !important;
  }

  /* Fonts */
  body, .md-typeset, .md-typeset h1, .md-typeset h2, .md-typeset h3, .md-typeset h4, .md-typeset h5, .md-typeset h6 {
      font-family: 'Poppins', sans-serif !important;
  }

  .md-main__inner {
    min-width: 103% !important;
    margin-left: -2%;
    overflow-y: hidden;
    margin-top: -1%;
  }

  .md-content {
      width: 100% !important;
  }

  /* SECTION 1: HERO */
  .hero-section {
    background-color: #000028; /* Dark blue match */
    color: white;
    text-align: center;
    padding: 60px 20px;
    font-family: 'Poppins', sans-serif;
  }

  .hero-title {
    font-size: 2.5rem;
    font-weight: 700;
    margin-bottom: 1rem;
    color: white;
  }

  .hero-subtitle {
    font-size: 1rem;
    color: #cbd5e1;
    margin-bottom: 3rem;
    font-weight: 300;
  }

  /* CAROUSEL STYLES */
  .carousel-container {
    perspective: 1000px;
    width: 100%;
    margin-top: 40px;
    display: flex;
    justify-content: center;
    position: relative;
    height: 400px;
  }

  .carousel-card {
    background-color: #e6ecf2;
    border-radius: 8px;
    position: absolute;
    width: 60%;
    max-width: 700px;
    height: 100%;
    transition: all 0.6s cubic-bezier(0.25, 0.8, 0.25, 1);
    box-shadow: 0 10px 30px rgba(0,0,0,0.15);
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer;
    overflow: hidden;
    /* Default Hidden State */
    opacity: 0;
    z-index: 0;
    transform: translateX(0) scale(0.5);
    background-color: #cbd5e1;
  }

  /* Center Card: Front and flat */
  .card-center {
    z-index: 3;
    transform: translateX(0) scale(1);
    opacity: 1;
    background-color: #e6ecf2;
  }

  /* Left Card: Pushed back, rotated Y, moved left */
  .card-left {
    z-index: 2; /* Higher than hidden, lower than center */
    transform: translateX(-55%) scale(0.8) rotateY(25deg);
    opacity: 0.6;
    background-color: #cbd5e1; /* Darker to simulate shadow */
  }

  /* Right Card: Pushed back, rotated Y, moved right */
  .card-right {
    z-index: 2;
    transform: translateX(55%) scale(0.8) rotateY(-25deg);
    opacity: 0.6;
    background-color: #cbd5e1;
  }

  /* Hover effects for side cards to invite interaction */
  .card-left:hover, .card-right:hover {
      opacity: 0.8;
      z-index: 3; /* bring to front on hover maybe? Or just highlight */
  }

  /* SECTION 2: EXPLORER */
  .explorer-section {
    padding: 40px 20px;
    background-color: #ffffff;
    font-family: 'Poppins', sans-serif;
  }

  .explorer-title {
    text-align: center;
    font-size: 1.75rem;
    font-weight: 700;
    color: #000;
    margin-bottom: 30px;
  }

  /* Tabs */
  .tabs-container {
    display: flex;
    justify-content: center;
    gap: 10px;
    margin-bottom: 30px;
    flex-wrap: wrap;
    background: #f8fafc;
    padding: 10px;
    border-radius: 50px;
    width: fit-content;
    margin-left: auto;
    margin-right: auto;
  }

  .tab-btn {
    background: transparent;
    border: none;
    padding: 10px 20px;
    border-radius: 20px;
    cursor: pointer;
    font-size: 0.9rem;
    font-weight: 600;
    color: #64748b;
    display: flex;
    align-items: center;
    gap: 8px;
    transition: all 0.2s;
  }

  .tab-btn.active {
    background-color: #0f172a; /* Dark active state */
    color: white;
  }

  .tab-btn:hover:not(.active) {
    background-color: #e2e8f0;
  }

  /* Modules Split View */
  .modules-container {
    display: flex;
    max-width: 1200px;
    margin: 0 auto;
    border: 1px solid #e2e8f0;
    border-radius: 12px;
    overflow: hidden;
    min-height: 500px;
  }

  .modules-sidebar {
    width: 25%;
    background-color: #ffffff;
    border-right: 1px solid #e2e8f0;
    padding: 20px 0;
  }

  .module-item {
    padding: 15px 20px;
    cursor: pointer;
    display: flex;
    align-items: center;
    gap: 10px;
    color: #475569;
    font-weight: 500;
    transition: background 0.2s;
    border-left: 3px solid transparent;
  }

  .module-item:hover {
    background-color: #f1f5f9;
  }

  .module-item.active {
    background-color: #eff6ff;
    color: #2563eb;
    border-left-color: #2563eb;
  }

  .module-icon {
      width: 18px;
      height: 18px;
      opacity: 0.7;
  }

  .modules-content {
    width: 75%;
    background-color: #f8fafc;
    padding: 40px;
    display: flex;
    flex-direction: column;
  }

  .content-header {
    display: flex;
    gap: 10px;
    margin-bottom: 20px;
  }

  .action-btn {
    background: white;
    border: 1px solid #e2e8f0;
    padding: 6px 16px;
    border-radius: 6px;
    font-size: 0.85rem;
    color: #475569;
    cursor: pointer;
    text-decoration: none;
    display: inline-block;
  }
  .action-btn:first-child {
      background: #eff6ff;
      color: #2563eb;
      border-color: #bfdbfe;
      font-weight: 600;
  }
  .action-btn:hover {
      background: #f8fafc;
      color: #0f172a;
  }

  .module-detail-title {
    font-size: 1.35rem;
    font-weight: 700;
    color: #0f172a;
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 10px;
  }

  .agentless-badge {
    background-color: #dbeafe;
    color: #1e40af;
    font-size: 0.75rem;
    padding: 2px 8px;
    border-radius: 4px;
    vertical-align: middle;
  }

  .module-description {
    color: #64748b;
    line-height: 1.6;
    margin-bottom: 30px;
    max-width: 800px;
  }

  .module-visual-placeholder {
    flex-grow: 1;
    background-color: #e2e8f0; /* darker placeholder */
    border-radius: 8px;
    margin-bottom: 20px;
    min-height: 200px;
    display: flex;
    align-items: center;
    justify-content: center;
    color: #94a3b8;
  }

  .learn-more-link {
    color: #2563eb;
    text-decoration: none;
    font-weight: 600;
    display: inline-flex;
    align-items: center;
    gap: 5px;
  }
  .learn-more-link:hover {
      text-decoration: underline;
  }

  /* SECTION 3: USE CASES (Resyled) */
  .use-cases-section {
    padding: 60px 40px;
    background-color: #ffffff;
    font-family: 'Poppins', sans-serif;
  }

  .section-heading-3 {
      text-align: center;
      font-size: 1.8rem;
      font-weight: 800;
      color: #0f172a;
      margin-bottom: 40px;
  }

  .use-cases-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 30px;
    max-width: 1200px;
    margin: 0 auto;
  }

  .use-case-card {
      border: 1px solid #e2e8f0;
      border-radius: 12px;
      padding: 24px;
      background: white;
      transition: all 0.2s ease;
  }

  .use-case-card:hover {
      box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
      border-color: #cbd5e1;
  }

  .use-case-header {
      display: flex;
      align-items: center;
      gap: 12px;
      margin-bottom: 20px;
      padding-bottom: 15px;
      border-bottom: 1px solid #f1f5f9;
  }

  .use-case-icon {
      width: 40px;
      height: 40px;
      border-radius: 8px;
      display: flex;
      align-items: center;
      justify-content: center;
      color: white;
  }

  /* Icon variants based on image colors approximately */
  .icon-blue { background-color: #eff6ff; color: #3b82f6; } /* Light blue bg, Blue icon */
  .icon-indigo { background-color: #eef2ff; color: #6366f1; }
  .icon-sky { background-color: #f0f9ff; color: #0ea5e9; }


  .use-case-title {
      font-size: 1.1rem !important; /* Override MD styles */
      font-weight: 700 !important;
      color: #0f172a !important;
      margin: 0 !important;
      padding: 0 !important;
      border: none !important;
      display: block !important;
      line-height: 1.3;
  }

  .use-case-list {
      list-style: none;
      padding: 0;
      margin: 0;
  }

  .use-case-list li {
      margin-bottom: 12px;
      display: flex;
      align-items: flex-start;
      gap: 8px;
  }

  .use-case-list li::before {
      content: "›"; /* Simple arrow, or use background image */
      color: #3b82f6;
      font-weight: bold;
      font-size: 1.2rem;
      line-height: 1rem;
  }

  .use-case-list a {
      color: #64748b;
      text-decoration: none;
      font-size: 0.95rem;
      transition: color 0.2s;
      line-height: 1.4;
  }

  .use-case-list a:hover {
      color: #2563eb;
  }

  .view-all-btn {
      display: block;
      width: fit-content;
      margin: 40px auto 0;
      padding: 12px 24px;
      background-color: #2563eb;
      color: white !important;
      text-decoration: none;
      border-radius: 6px;
      font-weight: 600;
  }
  .view-all-btn:hover {
      background-color: #1e40af;
  }

  /* EXISTING SECTIONS STYLES RETAINED PARTIALLY FOR COMPATIBILITY */
  /* Section 4, 5, 7 styles */
  .integrations-container {
    display: flex;
    align-items: center;
    background-color: #000025;
    padding: 80px 40px;
    font-family: 'Poppins', sans-serif;
  }
  .image-container2 { flex: 1; display: flex; justify-content: center; }
  .integrations-image { max-width: 100%; height: auto; }
  .text-container-int { flex: 1; color: #fff; margin-left: 40px; }
.integrations-title { font-weight: 900; font-size: 2rem; margin-bottom: 1rem; line-height: 1.2; color: white;}
  .integrations-description { font-size: 0.95rem; line-height: 1.6; margin-bottom: 20px; color: #cbd5e1; }
  .btn-style { background-color: #2563eb; color: white !important; padding: 10px 20px; border-radius: 5px; text-decoration: none; display: inline-block; font-weight: bold; border:none; cursor: pointer;}

  .section5-container { background-color: #f9f9fc; padding: 60px 20px; text-align: center; font-family: 'Poppins', sans-serif;}
  .section5-card-container { display: flex; justify-content: center; gap: 30px; margin-top: 40px; flex-wrap: wrap;}
  .section5-card { background: white; padding: 30px; border-radius: 8px; box-shadow: 0 4px 6px rgba(0,0,0,0.05); width: 350px; text-align: center; }
  .section5-card img { width: 60px; margin-bottom: 15px; }
  .section5-card-title { font-size: 1.1rem; font-weight: bold; margin-bottom: 10px; color: #0f172a;}
  .section5-card-link { color: #2563eb; font-weight: 600; text-decoration: none; }

  .home-section-7 { padding: 40px 0; text-align: center; background: white; font-family: 'Poppins', sans-serif;}
  .section7-nav { display: flex; justify-content: center; gap: 40px; margin-top: 20px; }
  .section7-link { color: #2563eb; font-weight: 700; text-decoration: none; padding-right: 20px; border-right: 1px solid #cbd5e1; }
  .section7-link:last-child { border-right: none; }

  .section-heading {
      text-align: center;
      color: #030372;
      font-size: 1.8rem !important;
      font-weight: 900 !important;
      text-align: center;
      margin-bottom: 10px;
  }

  @media (max-width: 991px) {
    .modules-container { flex-direction: column; }
    .modules-sidebar { width: 100%; border-right: none; border-bottom: 1px solid #e2e8f0; display: flex; overflow-x: auto;}
    .modules-content { width: 100%; }
    .integrations-container { flex-direction: column; text-align: center; }
    .text-container-int { margin-left: 0; margin-top: 30px; }
    .use-cases-grid { grid-template-columns: 1fr; }
  }
</style>

<!-- SECTION 1: HERO -->
<section class="hero-section">
  <div class="hero-title">Welcome to AccuKnox Help Center</div>
  <div class="hero-subtitle">Explore our comprehensive documentation and resources for cloud-native security</div>

  <!-- Carousel Container -->
  <div class="carousel-container" id="heroCarousel">
      <!-- Item 1 (Left) -->
      <div class="carousel-card card-left" onclick="rotateCarousel('left')">
         <img src="https://i.ibb.co/WNRCVKdV/1.png" alt="Carousel Image 1" style="border-radius: 8px;">
      </div>

      <!-- Item 2 (Center) -->
      <div class="carousel-card card-center" onclick="/* Center click */">
          <img src="https://i.ibb.co/MxmkQNVm/2.png" alt="Carousel Image 2" style=" border-radius: 8px;">
      </div>

      <!-- Item 3 (Right) -->
      <div class="carousel-card card-right" onclick="rotateCarousel('right')">
          <img src="https://i.ibb.co/8nmZpBZh/3.png" alt="Carousel Image 3" style=" border-radius: 8px;">
      </div>

      <!-- Item 4 (Hidden) -->
      <div class="carousel-card" onclick="/* hidden */">
        <img src="https://i.ibb.co/ZpwLD896/4.png" alt="Carousel Image 4" style=" border-radius: 8px;">
      </div>

       <!-- Item 5 (Hidden) -->
      <div class="carousel-card" onclick="/* hidden */">
        <img src="https://i.ibb.co/xSw1QpYD/5.png" alt="Carousel Image 5" style=" border-radius: 8px;">
      </div>

  </div>
</section>

<!-- SECTION 2: EXPLORE MODULES -->
<section class="explorer-section">
  <div class="explorer-title" style="font-size: 1.8rem; font-weight: 800; text-align: center; color: #0f172a; margin-bottom: 25px;">Explore AccuKnox's Documentation for Securing Assets at Scale</div>

  <div class="tabs-container" id="categoryTabs">
    <button class="tab-btn active" onclick="selectCategory('code', this)">
        <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="16 18 22 12 16 6"></polyline><polyline points="8 6 2 12 8 18"></polyline></svg> Secure Code
    </button>
    <button class="tab-btn" onclick="selectCategory('cloud', this)">
        <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M18 10h-1.26A8 8 0 1 0 9 20h9a5 5 0 0 0 0-10z"></path></svg> Secure Cloud
    </button>
    <button class="tab-btn" onclick="selectCategory('workloads', this)">
        <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polygon points="12 2 2 7 12 12 22 7 12 2"></polygon><polyline points="2 17 12 22 22 17"></polyline><polyline points="2 12 12 17 22 12"></polyline></svg> Secure Workloads
    </button>
    <button class="tab-btn" onclick="selectCategory('ai', this)">
        <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M12 2a2 2 0 0 1 2 2v2a2 2 0 0 1-2 2 2 2 0 0 1-2-2V4a2 2 0 0 1 2-2z"></path><path d="M12 16a2 2 0 0 1 2 2v2a2 2 0 0 1-2 2 2 2 0 0 1-2 2 2 2 0 0 1-2-2v-2a2 2 0 0 1 2-2z"></path><path d="M2 12a2 2 0 0 1 2-2h2a2 2 0 0 1 2 2 2 2 0 0 1-2 2H4a2 2 0 0 1-2-2z"></path><path d="M16 12a2 2 0 0 1 2-2h2a2 2 0 0 1 2 2 2 2 0 0 1-2 2h-2a2 2 0 0 1-2-2z"></path><line x1="12" y1="8" x2="12" y2="16"></line><line x1="12" y1="16" x2="16" y2="12"></line><line x1="12" y1="8" x2="8" y2="12"></line></svg> Secure AI
    </button>
    <button class="tab-btn" onclick="selectCategory('compliance', this)">
        <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 4h2a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h2"></path><rect x="8" y="2" width="8" height="4" rx="1" ry="1"></rect><path d="M9 14l2 2 4-4"></path></svg> Compliance
    </button>
    <button class="tab-btn" onclick="selectCategory('onprem', this)">
        <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="4" y="2" width="16" height="20" rx="2" ry="2"></rect><line x1="9" y1="22" x2="9" y2="22"></line><line x1="15" y1="22" x2="15" y2="22"></line></svg> On-Prem
    </button>
  </div>

  <div class="modules-container">
    <div class="modules-sidebar" id="modulesList">
      <!-- CODE -->
      <div class="module-item active" data-cat="code" onclick="selectModule('devsecops', this)">
         <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"></path></svg> DevSecOps (ASPM)
      </div>
      <div class="module-item" data-cat="code" onclick="selectModule('api', this)">
         <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="11" width="18" height="11" rx="2" ry="2"></rect><path d="M7 11V7a5 5 0 0 1 10 0v4"></path></svg> API Security
      </div>

      <!-- CLOUD -->
      <div class="module-item" data-cat="cloud" style="display:none;" onclick="selectModule('cspm', this)">
         <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M18 10h-1.26A8 8 0 1 0 9 20h9a5 5 0 0 0 0-10z"></path></svg> Cloud Security (CSPM)
      </div>
      <div class="module-item" data-cat="cloud" style="display:none;" onclick="selectModule('cdr', this)">
         <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="3"></circle><path d="M19.4 15a1.65 1.65 0 0 0 .33 1.82l.06.06a2 2 0 0 1 0 2.83 2 2 0 0 1-2.83 0l-.06-.06a1.65 1.65 0 0 0-1.82-.33 1.65 1.65 0 0 0-1 1.51V21a2 2 0 0 1-2 2 2 2 0 0 1-2-2v-.09A1.65 1.65 0 0 0 9 19.4a1.65 1.65 0 0 0-1.82.33l-.06.06a2 2 0 0 1-2.83 0 2 2 0 0 1 0-2.83l.06-.06a1.65 1.65 0 0 0 .33-1.82 1.65 1.65 0 0 0-1.51-1H3a2 2 0 0 1-2-2 2 2 0 0 1 2-2h.09A1.65 1.65 0 0 0 4.6 9a1.65 1.65 0 0 0-.33-1.82l-.06-.06a2 2 0 0 1 0-2.83 2 2 0 0 1 2.83 0l.06.06a1.65 1.65 0 0 0 1.82.33H9a1.65 1.65 0 0 0 1-1.51V3a2 2 0 0 1 2-2 2 2 0 0 1 2 2v.09a1.65 1.65 0 0 0 1 1.51 1.65 1.65 0 0 0 1.82-.33l.06-.06a2 2 0 0 1 2.83 0 2 2 0 0 1 0 2.83l-.06.06a1.65 1.65 0 0 0-.33 1.82V9a1.65 1.65 0 0 0 1.51 1H21a2 2 0 0 1 2 2 2 2 0 0 1-2 2h-.09a1.65 1.65 0 0 0-1.51 1z"></path></svg> Cloud Detection & Response (CDR)
      </div>
      <div class="module-item" data-cat="cloud" style="display:none;" onclick="selectModule('secrets', this)">
         <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M21 2l-2 2m-7.61 7.61a5.5 5.5 0 1 1-7.778 7.778 5.5 5.5 0 0 1 7.777-7.777zm0 0L15.5 7.5m0 0l3 3L22 7l-3-3m-3.5 3.5L19 4"></path></svg> Secrets Manager
      </div>

      <!-- WORKLOADS -->
      <div class="module-item" data-cat="workloads" style="display:none;" onclick="selectModule('cwpp', this)">
         <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"></path></svg> Runtime Protection (CWPP)
      </div>
      <div class="module-item" data-cat="workloads" style="display:none;" onclick="selectModule('kiem', this)">
         <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"></path><circle cx="8.5" cy="7" r="4"></circle><polyline points="17 11 19 13 23 9"></polyline></svg> K8s Identity & Entitlements (KIEM)
      </div>
      <div class="module-item" data-cat="workloads" style="display:none;" onclick="selectModule('kspm', this)">
         <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"></circle><path d="M12 2a7 7 0 1 0 10 10"></path></svg> Kubernetes Security Posture (KSPM)
      </div>

      <!-- AI -->
      <div class="module-item" data-cat="ai" style="display:none;" onclick="selectModule('aiml', this)">
         <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M12 2a2 2 0 0 1 2 2v2a2 2 0 0 1-2 2 2 2 0 0 1-2-2V4a2 2 0 0 1 2-2z"></path><path d="M12 16a2 2 0 0 1 2 2v2a2 2 0 0 1-2 2 2 2 0 0 1-2 2 2 2 0 0 1-2-2v-2a2 2 0 0 1 2-2z"></path><path d="M2 12a2 2 0 0 1 2-2h2a2 2 0 0 1 2 2 2 2 0 0 1-2 2H4a2 2 0 0 1-2-2z"></path><path d="M16 12a2 2 0 0 1 2-2h2a2 2 0 0 1 2 2 2 2 0 0 1-2 2h-2a2 2 0 0 1-2-2z"></path><line x1="12" y1="8" x2="12" y2="16"></line><line x1="12" y1="16" x2="16" y2="12"></line><line x1="12" y1="8" x2="8" y2="12"></line></svg> AI/ML Security
      </div>

      <!-- COMPLIANCE -->
      <div class="module-item" data-cat="compliance" style="display:none;" onclick="selectModule('comp', this)">
         <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 4h2a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h2"></path><rect x="8" y="2" width="8" height="4" rx="1" ry="1"></rect><path d="M9 14l2 2 4-4"></path></svg> Continuous Compliance
      </div>

       <!-- ONPREM -->
      <div class="module-item" data-cat="onprem" style="display:none;" onclick="selectModule('onprem-install', this)">
         <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="4" y="2" width="16" height="20" rx="2" ry="2"></rect><line x1="9" y1="22" x2="9" y2="22"></line><line x1="15" y1="22" x2="15" y2="22"></line></svg> On-Prem Deployment
      </div>
    </div>

    <div class="modules-content" id="moduleDetail">
       <!-- START CONTENT BLOCKS -->
        <!-- DevSecOps -->
        <div id="devsecops" class="module-detail-block">
            <div class="content-header">
                <a href="/use-cases/aspm/" class="action-btn">Getting Started</a>
                <a href="/use-cases/aspm/" class="action-btn">Integrations</a>
                <a href="/use-cases/aspm/" class="action-btn">Use Case</a>
            </div>
            <div class="module-detail-title">
                DevSecOps (ASPM) <span class="agentless-badge">Agentless</span>
            </div>
            <div class="module-description">
                Embeds security practices into DevOps, automating security testing and compliance throughout the SDLC from build to runtime environments.
            </div>
            <div class="module-visual-placeholder">
                 <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="#cbd5e1" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"></path></svg>
            </div>
            <a href="/use-cases/aspm/" class="learn-more-link">Learn more about DevSecOps &rarr;</a>
        </div>

        <!-- API -->
        <div id="api" class="module-detail-block" style="display:none;">
            <div class="content-header">
                <a href="/use-cases/api-security/" class="action-btn">Getting Started</a>
                <a href="/use-cases/api-security/" class="action-btn">Integrations</a>
                <a href="/use-cases/api-security/" class="action-btn">Use Case</a>
            </div>
            <div class="module-detail-title">
                API Security
            </div>
            <div class="module-description">
                Comprehensive API security monitoring and protection to detect vulnerabilities, prevent attacks, and ensure secure API communications.
            </div>
             <div class="module-visual-placeholder">
                 <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="#cbd5e1" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="11" width="18" height="11" rx="2" ry="2"></rect><path d="M7 11V7a5 5 0 0 1 10 0v4"></path></svg>
            </div>
            <a href="/use-cases/api-security/" class="learn-more-link">Learn more about API Security &rarr;</a>
        </div>

        <!-- CSPM -->
        <div id="cspm" class="module-detail-block" style="display:none;">
            <div class="content-header">
                <a href="/use-cases/cspm/" class="action-btn">Getting Started</a>
                <a href="/use-cases/cspm/" class="action-btn">Integrations</a>
                <a href="/use-cases/cspm/" class="action-btn">Use Case</a>
            </div>
            <div class="module-detail-title">
                Cloud Security (CSPM) <span class="agentless-badge">Agentless</span>
            </div>
            <div class="module-description">
                Identifies cloud misconfigurations, ensures compliance, and continuously monitors security across multi-cloud environments.
            </div>
            <div class="module-visual-placeholder">
                 <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="#cbd5e1" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M18 10h-1.26A8 8 0 1 0 9 20h9a5 5 0 0 0 0-10z"></path></svg>
            </div>
            <a href="/use-cases/cspm/" class="learn-more-link">Learn more about Cloud Security &rarr;</a>
        </div>

        <!-- CDR -->
        <div id="cdr" class="module-detail-block" style="display:none;">
            <div class="content-header">
                <a href="/getting-started/aws-cdr/" class="action-btn">Getting Started</a>
                <a href="/getting-started/aws-cdr/" class="action-btn">Integrations</a>
                <a href="/getting-started/aws-cdr/" class="action-btn">Use Case</a>
            </div>
            <div class="module-detail-title">
                Cloud Detection & Response (CDR)
            </div>
            <div class="module-description">
                Detect and remediate threats on AWS, GCP, and Azure, focusing on high-signal security events.
            </div>
            <div class="module-visual-placeholder">
                 <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="#cbd5e1" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="3"></circle><path d="M19.4 15a1.65 1.65 0 0 0 .33 1.82l.06.06a2 2 0 0 1 0 2.83 2 2 0 0 1-2.83 0l-.06-.06a1.65 1.65 0 0 0-1.82-.33 1.65 1.65 0 0 0-1 1.51V21a2 2 0 0 1-2 2 2 2 0 0 1-2-2v-.09A1.65 1.65 0 0 0 9 19.4a1.65 1.65 0 0 0-1.82.33l-.06.06a2 2 0 0 1-2.83 0 2 2 0 0 1 0-2.83l.06-.06a1.65 1.65 0 0 0 .33-1.82 1.65 1.65 0 0 0-1.51-1H3a2 2 0 0 1-2-2 2 2 0 0 1 2-2h.09A1.65 1.65 0 0 0 4.6 9a1.65 1.65 0 0 0-.33-1.82l-.06-.06a2 2 0 0 1 0-2.83 2 2 0 0 1 2.83 0l.06.06a1.65 1.65 0 0 0 1.82.33H9a1.65 1.65 0 0 0 1-1.51V3a2 2 0 0 1 2-2 2 2 0 0 1 2 2v.09a1.65 1.65 0 0 0 1 1.51 1.65 1.65 0 0 0 1.82-.33l.06-.06a2 2 0 0 1 2.83 0 2 2 0 0 1 0 2.83l-.06.06a1.65 1.65 0 0 0-.33 1.82V9a1.65 1.65 0 0 0 1.51 1H21a2 2 0 0 1 2 2 2 2 0 0 1-2 2h-.09a1.65 1.65 0 0 0-1.51 1z"></path></svg>
            </div>
            <a href="/getting-started/aws-cdr/" class="learn-more-link">Learn more about Detection & Response &rarr;</a>
        </div>

        <!-- Secrets -->
        <div id="secrets" class="module-detail-block" style="display:none;">
            <div class="content-header">
                <a href="/getting-started/secrets-management/" class="action-btn">Getting Started</a>
                <a href="/getting-started/secrets-management/" class="action-btn">Integrations</a>
                <a href="/getting-started/secrets-management/" class="action-btn">Use Case</a>
            </div>
            <div class="module-detail-title">
                Secrets Manager
            </div>
            <div class="module-description">
                Secure storage and management of sensitive credentials, API keys, and secrets using encryption and access controls.
            </div>
            <div class="module-visual-placeholder">
                 <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="#cbd5e1" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M21 2l-2 2m-7.61 7.61a5.5 5.5 0 1 1-7.778 7.778 5.5 5.5 0 0 1 7.777-7.777zm0 0L15.5 7.5m0 0l3 3L22 7l-3-3m-3.5 3.5L19 4"></path></svg>
            </div>
            <a href="/getting-started/secrets-management/" class="learn-more-link">Learn more about Secrets Manager &rarr;</a>
        </div>

        <!-- CWPP -->
        <div id="cwpp" class="module-detail-block" style="display:none;">
            <div class="content-header">
                <a href="/use-cases/cwpp/" class="action-btn">Getting Started</a>
                <a href="/use-cases/cwpp/" class="action-btn">Integrations</a>
                <a href="/use-cases/cwpp/" class="action-btn">Use Case</a>
            </div>
            <div class="module-detail-title">
                Runtime Protection (CWPP)
            </div>
            <div class="module-description">
                Protects cloud workloads by detecting threats, vulnerabilities, and misconfigurations in real time.
            </div>
            <div class="module-visual-placeholder">
                 <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="#cbd5e1" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"></path></svg>
            </div>
            <a href="/use-cases/cwpp/" class="learn-more-link">Learn more about Runtime Protection &rarr;</a>
        </div>

        <!-- KIEM -->
        <div id="kiem" class="module-detail-block" style="display:none;">
            <div class="content-header">
                <a href="/use-cases/kiem/" class="action-btn">Getting Started</a>
                <a href="/use-cases/kiem/" class="action-btn">Integrations</a>
                <a href="/use-cases/kiem/" class="action-btn">Use Case</a>
            </div>
            <div class="module-detail-title">
                K8s Identity & Entitlements (KIEM)
            </div>
            <div class="module-description">
                Enforces IAM controls and entitlement policies across Kubernetes clusters to prevent privilege escalation.
            </div>
            <div class="module-visual-placeholder">
                 <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="#cbd5e1" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M16 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"></path><circle cx="8.5" cy="7" r="4"></circle><polyline points="17 11 19 13 23 9"></polyline></svg>
            </div>
            <a href="/use-cases/kiem/" class="learn-more-link">Learn more about K8s Identity &rarr;</a>
        </div>

        <!-- KSPM -->
        <div id="kspm" class="module-detail-block" style="display:none;">
            <div class="content-header">
                <a href="/use-cases/kspm/" class="action-btn">Getting Started</a>
                <a href="/use-cases/kspm/" class="action-btn">Integrations</a>
                <a href="/use-cases/kspm/" class="action-btn">Use Case</a>
            </div>
            <div class="module-detail-title">
                Kubernetes Security Posture (KSPM)
            </div>
            <div class="module-description">
                Continuously monitors Kubernetes clusters to identify and remediate misconfigurations and vulnerabilities.
            </div>
            <div class="module-visual-placeholder">
                 <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="#cbd5e1" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"></circle><path d="M12 2a7 7 0 1 0 10 10"></path></svg>
            </div>
            <a href="/use-cases/kspm/" class="learn-more-link">Learn more about K8s Posture &rarr;</a>
        </div>

        <!-- AIML -->
        <div id="aiml" class="module-detail-block" style="display:none;">
            <div class="content-header">
                <a href="/use-cases/aiml-usecases/" class="action-btn">Getting Started</a>
                <a href="/use-cases/aiml-usecases/" class="action-btn">Integrations</a>
                <a href="/use-cases/aiml-usecases/" class="action-btn">Use Case</a>
            </div>
            <div class="module-detail-title">
                AI/ML Security
            </div>
            <div class="module-description">
                AI-SPM capability that detects cloud misconfigurations and monitors AI and ML models with continuous intelligence.
            </div>
            <div class="module-visual-placeholder">
                 <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="#cbd5e1" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M12 2a2 2 0 0 1 2 2v2a2 2 0 0 1-2 2 2 2 0 0 1-2-2V4a2 2 0 0 1 2-2z"></path><path d="M12 16a2 2 0 0 1 2 2v2a2 2 0 0 1-2 2 2 2 0 0 1-2 2 2 2 0 0 1-2-2v-2a2 2 0 0 1 2-2z"></path><path d="M2 12a2 2 0 0 1 2-2h2a2 2 0 0 1 2 2 2 2 0 0 1-2 2H4a2 2 0 0 1-2-2z"></path><path d="M16 12a2 2 0 0 1 2-2h2a2 2 0 0 1 2 2 2 2 0 0 1-2 2h-2a2 2 0 0 1-2-2z"></path><line x1="12" y1="8" x2="12" y2="16"></line><line x1="12" y1="16" x2="16" y2="12"></line><line x1="12" y1="8" x2="8" y2="12"></line></svg>
            </div>
            <a href="/use-cases/aiml-usecases/" class="learn-more-link">Learn more about AI/ML Security &rarr;</a>
        </div>

        <!-- Compliance -->
        <div id="comp" class="module-detail-block" style="display:none;">
            <div class="content-header">
                <a href="/use-cases/compliance/" class="action-btn">Getting Started</a>
                <a href="/use-cases/compliance/" class="action-btn">Integrations</a>
                <a href="/use-cases/compliance/" class="action-btn">Use Case</a>
            </div>
            <div class="module-detail-title">
                Continuous Compliance <span class="agentless-badge">Agentless</span>
            </div>
            <div class="module-description">
                Unified visibility into security posture, risk, and compliance across multi-cloud and Kubernetes environments.
            </div>
            <div class="module-visual-placeholder">
                 <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="#cbd5e1" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M16 4h2a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h2"></path><rect x="8" y="2" width="8" height="4" rx="1" ry="1"></rect><path d="M9 14l2 2 4-4"></path></svg>
            </div>
            <a href="/use-cases/compliance/" class="learn-more-link">Learn more about Compliance &rarr;</a>
        </div>

        <!-- On-Prem -->
        <div id="onprem-install" class="module-detail-block" style="display:none;">
            <div class="content-header">
                <a href="/getting-started/on-prem-installation-guide/" class="action-btn">Getting Started</a>
                <a href="/getting-started/on-prem-installation-guide/" class="action-btn">Integrations</a>
                <a href="/getting-started/on-prem-installation-guide/" class="action-btn">Use Case</a>
            </div>
            <div class="module-detail-title">
                On-Prem Deployment <span class="agentless-badge">Agentless</span>
            </div>
            <div class="module-description">
                Secure air-gapped deployment of the CNAPP platform designed to meet federal and regulated environment requirements.
            </div>
            <div class="module-visual-placeholder">
                 <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="#cbd5e1" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><rect x="4" y="2" width="16" height="20" rx="2" ry="2"></rect><line x1="9" y1="22" x2="9" y2="22"></line><line x1="15" y1="22" x2="15" y2="22"></line></svg>
            </div>
            <a href="/getting-started/on-prem-installation-guide/" class="learn-more-link">Learn more about On-Prem &rarr;</a>
        </div>

    </div>

  </div>
</section>

<!-- SECTION 3: POPULAR USE CASES -->
<section class="use-cases-section">
  <div class="section-heading-3" style="font-size: 1.8rem; font-weight: 800; text-align: center; color: #0f172a; margin-bottom: 40px;">Popular Use Cases</div>
  <div class="use-cases-grid">
    <!-- Card 1 -->
    <div class="use-case-card">
       <div class="use-case-header">
         <div class="use-case-icon icon-blue">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"></path></svg>
         </div>
         <h3 class="use-case-title">DevSecOps (ASPM)</h3>
       </div>
       <ul class="use-case-list">
         <li><a href="/use-cases/iac-scan/" target="_blank">IaC Scan AWS S3 Buckets</a></li>
         <li><a href="/use-cases/sast-sq/" target="_blank">SAST + SQL Injection</a></li>
         <li><a href="/use-cases/container-scan/" target="_blank">ASPM Container Scan</a></li>
         <li><a href="/use-cases/epss-scoring/" target="_blank">EPSS Scoring</a></li>
       </ul>
    </div>

    <!-- Card 2 -->
    <div class="use-case-card">
       <div class="use-case-header">
         <div class="use-case-icon icon-blue">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="2" y="7" width="20" height="14" rx="2" ry="2"></rect><path d="M16 21V5a2 2 0 0 0-2-2h-4a2 2 0 0 0-2 2v16"></path></svg>
         </div>
         <h3 class="use-case-title">Container Security (CWPP)</h3>
       </div>
       <ul class="use-case-list">
         <li><a href="/use-cases/image-scan/" target="_blank">Container Image Scan</a></li>
         <li><a href="/use-cases/app-hardening/" target="_blank">Runtime Application Hardening</a></li>
         <li><a href="/use-cases/hardening/" target="_blank">Workload Hardening</a></li>
       </ul>
    </div>

    <!-- Card 3 -->
    <div class="use-case-card">
       <div class="use-case-header">
         <div class="use-case-icon icon-blue">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="11" width="18" height="11" rx="2" ry="2"></rect><path d="M7 11V7a5 5 0 0 1 10 0v4"></path></svg>
         </div>
         <h3 class="use-case-title">Secrets Management</h3>
       </div>
       <ul class="use-case-list">
         <li><a href="/getting-started/secrets-management/" target="_blank">Secrets Management Policy</a></li>
         <li><a href="/use-cases/hashicorp/" target="_blank">HashiCorp Vault Hardening</a></li>
         <li><a href="/use-cases/cyberark-conjur/" target="_blank">CyberArk Conjur Hardening</a></li>
       </ul>
    </div>

    <!-- Card 4 -->
    <div class="use-case-card">
       <div class="use-case-header">
         <div class="use-case-icon icon-blue">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M22 11.08V12a10 10 0 1 1-5.93-9.14"></path><polyline points="22 4 12 14.01 9 11.01"></polyline></svg>
         </div>
         <h3 class="use-case-title">Posture Assessment (CWPP)</h3>
       </div>
       <ul class="use-case-list">
         <li><a href="/use-cases/app-behavior/" target="_blank">Runtime Application Behaviour</a></li>
         <li><a href="/use-cases/forensics/" target="_blank">Audit/Forensics</a></li>
         <li><a href="/use-cases/zero-trust/" target="_blank">Zero Trust Security</a></li>
       </ul>
    </div>

    <!-- Card 5 -->
    <div class="use-case-card">
       <div class="use-case-header">
         <div class="use-case-icon icon-blue">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="2" y="2" width="20" height="8" rx="2" ry="2"></rect><rect x="2" y="14" width="20" height="8" rx="2" ry="2"></rect><line x1="6" y1="6" x2="6.01" y2="6"></line><line x1="6" y1="18" x2="6.01" y2="18"></line></svg>
         </div>
         <h3 class="use-case-title">Host Security (CWPP)</h3>
       </div>
       <ul class="use-case-list">
         <li><a href="/use-cases/host-sec/" target="_blank">Host Scan</a></li>
         <li><a href="/use-cases/malware-scan/" target="_blank">Malware Scan</a></li>
         <li><a href="/use-cases/vm-hardening/" target="_blank">VM Hardening</a></li>
       </ul>
    </div>

    <!-- Card 6 -->
    <div class="use-case-card">
       <div class="use-case-header">
         <div class="use-case-icon icon-blue">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M18 10h-1.26A8 8 0 1 0 9 20h9a5 5 0 0 0 0-10z"></path></svg>
         </div>
         <h3 class="use-case-title">Cloud Security (CSPM)</h3>
       </div>
       <ul class="use-case-list">
         <li><a href="/use-cases/asset-inventory/" target="_blank">Asset Inventory</a></li>
         <li><a href="/use-cases/cloud-misconfigurations" target="_blank">Cloud Misconfiguration</a></li>
       </ul>
    </div>

     <!-- Card 7 -->
    <div class="use-case-card">
       <div class="use-case-header">
         <div class="use-case-icon icon-blue">
             <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="3"></circle><path d="M19.4 15a1.65 1.65 0 0 0 .33 1.82l.06.06a2 2 0 0 1 0 2.83 2 2 0 0 1-2.83 0l-.06-.06a1.65 1.65 0 0 0-1.82-.33 1.65 1.65 0 0 0-1 1.51V21a2 2 0 0 1-2 2 2 2 0 0 1-2-2v-.09A1.65 1.65 0 0 0 9 19.4a1.65 1.65 0 0 0-1.82.33l-.06.06a2 2 0 0 1-2.83 0 2 2 0 0 1 0-2.83l.06-.06a1.65 1.65 0 0 0 .33-1.82 1.65 1.65 0 0 0-1.51-1H3a2 2 0 0 1-2-2 2 2 0 0 1 2-2h.09A1.65 1.65 0 0 0 4.6 9a1.65 1.65 0 0 0-.33-1.82l-.06-.06a2 2 0 0 1 0-2.83 2 2 0 0 1 2.83 0l.06.06a1.65 1.65 0 0 0 1.82.33H9a1.65 1.65 0 0 0 1-1.51V3a2 2 0 0 1 2-2 2 2 0 0 1 2 2v.09a1.65 1.65 0 0 0 1 1.51 1.65 1.65 0 0 0 1.82-.33l.06-.06a2 2 0 0 1 2.83 0 2 2 0 0 1 0 2.83l-.06.06a1.65 1.65 0 0 0-.33 1.82V9a1.65 1.65 0 0 0 1.51 1H21a2 2 0 0 1 2 2 2 2 0 0 1-2 2h-.09a1.65 1.65 0 0 0-1.51 1z"></path></svg>
         </div>
         <h3 class="use-case-title">Automation</h3>
       </div>
       <ul class="use-case-list">
         <li><a href="/integrations/freshservice-cspm/" target="_blank">Ticketing</a></li>
         <li><a href="/use-cases/rules-engine-ticket-creation/" target="_blank">Rules Engine</a></li>
       </ul>
    </div>

    <!-- Card 8 -->
    <div class="use-case-card">
       <div class="use-case-header">
         <div class="use-case-icon icon-blue">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M1 12s4-8 11-8 11 8 11 8-4 8-11 8-11-8-11-8z"></path><circle cx="12" cy="12" r="3"></circle></svg>
         </div>
         <h3 class="use-case-title">Cloud Detection & Response</h3>
       </div>
       <ul class="use-case-list">
          <li><a href="/getting-started/aws-cdr/" target="_blank">Onboarding AWS for CDR</a></li>
          <li><a href="/getting-started/azure-cdr/" target="_blank">Onboarding Azure for CDR</a></li>
          <li><a href="/getting-started/gcp-cdr/" target="_blank">Onboarding GCP for CDR</a></li>
          <li><a href="/getting-started/cdr-setup/" target="_blank">Alert Remediation</a></li>
       </ul>
    </div>

    <!-- Card 9 -->
    <div class="use-case-card">
       <div class="use-case-header">
         <div class="use-case-icon icon-blue">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="4" y="4" width="16" height="16" rx="2" ry="2"></rect><rect x="9" y="9" width="6" height="6"></rect><line x1="9" y1="1" x2="9" y2="4"></line><line x1="15" y1="1" x2="15" y2="4"></line><line x1="9" y1="20" x2="9" y2="23"></line><line x1="15" y1="20" x2="15" y2="23"></line><line x1="20" y1="9" x2="23" y2="9"></line><line x1="20" y1="14" x2="23" y2="14"></line><line x1="1" y1="9" x2="4" y2="9"></line><line x1="1" y1="14" x2="4" y2="14"></line></svg>
         </div>
         <h3 class="use-case-title">AI/ML Security</h3>
       </div>
       <ul class="use-case-list">
          <li><a href="/use-cases/jupyter-notebook/" target="_blank">Jupyter Notebook Security</a></li>
          <li><a href="/use-cases/aiml-runtime-onboard/" target="_blank">LLM Security Onboarding</a></li>
          <li><a href="/use-cases/modelarmor/" target="_blank">ModelArmor (Open Source)</a></li>
       </ul>
    </div>

  </div>
  <a href="/use-cases/" class="view-all-btn">VIEW ALL USE CASES &rarr;</a>
</section>

<!-- SECTION 4 - INTEGRATION -->
<section>
<div class="integrations-container">
 <div class="image-container2">
   <img src="introduction/cards/integrations-updated.png" alt="Integrations" class="integrations-image">
 </div>
 <div class="text-container-int">
   <article class="integrations-title">Integrate Seamlessly In Your Technology Ecosystem</article>
   <p class="integrations-description">Check out integrations for Azure, Google Cloud Build, AWS, Jenkins, Gitlab, CheckMarkx and more. We also support Container Platforms like Nutanix, Rafay and Mirantis and Notification platforms like Slack.</p>
   <a href="/integrations/jira-cloud/" class="btn-style">GET STARTED &rarr;</a>
 </div>
</div>
</section>

<!-- SECTION 5 - TECHNICAL SUPPORT -->
<section>
  <div class="section5-container">
    <h2 class="section-heading">Technical Support</h2>
    <div class="section5-card-container">
        <div class="section5-card">
            <img src="introduction/cards/badge1.svg" alt="Tech Support Icon">
            <h3 class="section5-card-title">Raise Ticket</h3>
            <p>Contact our Support Team to quickly resolve any issues.</p>
            <a href="https://accu-knox.atlassian.net/servicedesk/customer/portal/1" target="_blank" class="section5-card-link">CONNECT WITH US &rarr;</a>
        </div>
        <div class="section5-card">
            <img src="introduction/cards/badge2.svg" alt="Certification Icon">
            <h3 class="section5-card-title">AccuKnox Certifications</h3>
            <p>AccuKnox certifications ensure compliance with industry security standards.</p>
            <a href="https://www.accuknox.com/certifications" target="_blank" class="section5-card-link">GET CERTIFIED &rarr;</a>
        </div>
        <div class="section5-card">
            <img src="introduction/cards/badge3.svg" alt="Downloads Icon">
            <h3 class="section5-card-title">Resources</h3>
            <p>Download and make the most of AccuKnox guides and manuals.</p>
            <a href="/resources/accuknox-manual/" target="_blank" class="section5-card-link">DOWNLOAD NOW &rarr;</a>
        </div>
    </div>
  </div>
</section>

<!-- SECTION 7 -->
<section class="home-section-7">
<h2 class="section-heading">Find Out More</h2>
<div class="section7-nav">
    <a href="/resources/accuknox-manual/" class="section7-link" target="_blank">RESOURCES</a>
    <a href="/support-matrix/kubearmor-support-matrix/" target="_blank" class="section7-link">SUPPORT MATRIX</a>
    <a href="https://help.accuknox.com/getting-started/3.3-release/" target="_blank" class="section7-link">LATEST RELEASE NOTES</a>
    <a href="/faqs/" target="_blank" class="section7-link" style="border-right: 0px">FAQ</a>
</div>
</section>

<script>
function selectCategory(catId, btn) {
    // 1. Update Tabs
    document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
    btn.classList.add('active');

    // 2. Filter Sidebar
    const sidebarItems = document.querySelectorAll('.module-item');
    let firstVisible = null;
    sidebarItems.forEach(item => {
        if (item.getAttribute('data-cat') === catId) {
            item.style.display = 'flex';
            if (!firstVisible) firstVisible = item;
        } else {
            item.style.display = 'none';
        }
        item.classList.remove('active');
    });

    // 3. Select first module of new category
    if (firstVisible) {
        firstVisible.click();
    }
}

function selectModule(modId, item) {
    // 1. Update Sidebar Active State
    document.querySelectorAll('.module-item').forEach(i => i.classList.remove('active'));
    item.classList.add('active');

    // 2. Show Content
    document.querySelectorAll('.module-detail-block').forEach(b => {
        if (b.id === modId) {
            b.style.display = 'block';
        } else {
            b.style.display = 'none';
        }
    });
}

// Carousel Logic
let carouselCards = document.querySelectorAll('.carousel-card');
function updateCarouselDisplay() {
    carouselCards = document.querySelectorAll('.carousel-card');
}

function rotateCarousel(direction) {
    const cards = Array.from(document.querySelectorAll('.carousel-card'));
    // Identify current positions
    let leftIndex = cards.findIndex(c => c.classList.contains('card-left'));
    let centerIndex = cards.findIndex(c => c.classList.contains('card-center'));
    let rightIndex = cards.findIndex(c => c.classList.contains('card-right'));

    // Clear classes
    cards.forEach(c => c.classList.remove('card-left', 'card-center', 'card-right'));

    if (direction === 'right') {
        // Move Right item to Center. Center to Left. Left to Right (cycle)
        cards[rightIndex].classList.add('card-center');
        cards[centerIndex].classList.add('card-left');
        cards[leftIndex].classList.add('card-right');
    } else {
        // Move Left item to Center. Center to Right. Right to Left
        cards[leftIndex].classList.add('card-center');
        cards[centerIndex].classList.add('card-right');
        cards[rightIndex].classList.add('card-left');
    }
}
</script>
