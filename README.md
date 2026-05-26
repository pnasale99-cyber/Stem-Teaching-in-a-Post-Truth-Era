<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>STEM Teaching in a Post-Truth Era</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,wght@0,300;0,400;0,600;1,300;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  :root {
    --teal-deep: #085041; --teal-mid: #0F6E56; --teal-light: #1D9E75; --teal-pale: #E1F5EE; --teal-soft: #9FE1CB;
    --blue-deep: #0C447C; --blue-mid: #185FA5; --blue-light: #378ADD; --blue-pale: #E6F1FB;
    --amber-deep: #633806; --amber-mid: #854F0B; --amber-light: #BA7517; --amber-pale: #FAEEDA; --amber-glow: #FAC775;
    --coral-mid: #993C1D; --coral-light: #D85A30; --coral-pale: #FAECE7;
    --gray-deep: #2C2C2A; --gray-mid: #5F5E5A; --gray-light: #B4B2A9; --gray-pale: #F1EFE8;
    --font-display: 'Fraunces', Georgia, serif; --font-body: 'DM Sans', sans-serif;
  }
  html { scroll-behavior: smooth; }
  body { font-family: var(--font-body); font-size: 16px; line-height: 1.7; color: var(--gray-deep); background: #fff; }

  nav { position: sticky; top: 0; z-index: 100; background: var(--teal-deep); display: flex; align-items: center; padding: 0 2rem; min-height: 56px; box-shadow: 0 2px 12px rgba(0,0,0,0.18); }
  .nav-brand { font-family: var(--font-display); font-size: 1.05rem; font-weight: 600; color: var(--teal-soft); margin-right: auto; white-space: nowrap; }
  .nav-links { display: flex; list-style: none; overflow-x: auto; }
  .nav-links a { display: block; padding: 0 1rem; line-height: 56px; color: rgba(255,255,255,0.75); text-decoration: none; font-size: 0.82rem; font-weight: 500; letter-spacing: 0.02em; white-space: nowrap; transition: color 0.2s, background 0.2s; }
  .nav-links a:hover { color: #fff; background: rgba(255,255,255,0.08); }

  .hero { background: var(--teal-deep); position: relative; overflow: hidden; padding: 5rem 2rem 4rem; text-align: center; }
  .hero::before { content:''; position:absolute; inset:0; background: radial-gradient(ellipse 60% 60% at 80% 20%, rgba(29,158,117,0.22) 0%, transparent 60%), radial-gradient(ellipse 50% 70% at 15% 85%, rgba(9,112,78,0.18) 0%, transparent 60%); }
  .hero-eyebrow { font-size:0.78rem; font-weight:500; letter-spacing:0.14em; text-transform:uppercase; color:var(--teal-soft); margin-bottom:1.25rem; }
  .hero h1 { font-family:var(--font-display); font-size:clamp(2.2rem,5vw,3.8rem); font-weight:300; color:#fff; line-height:1.12; max-width:800px; margin:0 auto 1.5rem; letter-spacing:-0.02em; position:relative; }
  .hero h1 em { font-style:italic; color:var(--teal-soft); }
  .hero-sub { font-size:1.08rem; color:rgba(255,255,255,0.72); max-width:580px; margin:0 auto 2.5rem; font-weight:300; position:relative; }
  .hero-pills { display:flex; flex-wrap:wrap; gap:0.6rem; justify-content:center; position:relative; }
  .pill { display:inline-block; padding:0.45rem 1.1rem; border-radius:999px; font-size:0.8rem; font-weight:500; text-decoration:none; transition:transform 0.15s; cursor:pointer; }
  .pill:hover { transform:translateY(-2px); }
  .pill-teal { background:var(--teal-light); color:#fff; }
  .pill-amber { background:var(--amber-glow); color:var(--amber-deep); }
  .pill-blue { background:var(--blue-light); color:#fff; }
  .pill-coral { background:var(--coral-light); color:#fff; }

  section { padding: 4.5rem 2rem; }
  section:nth-child(even) { background: var(--gray-pale); }
  .container { max-width: 960px; margin: 0 auto; }
  .section-eyebrow { font-size:0.75rem; font-weight:500; letter-spacing:0.13em; text-transform:uppercase; color:var(--teal-mid); margin-bottom:0.75rem; }
  .section-title { font-family:var(--font-display); font-size:clamp(1.7rem,3.5vw,2.4rem); font-weight:400; color:var(--teal-deep); line-height:1.18; margin-bottom:1rem; letter-spacing:-0.015em; }
  .section-lead { font-size:1.05rem; color:var(--gray-mid); max-width:620px; margin-bottom:2.5rem; font-weight:300; }

  .def-grid { display:grid; grid-template-columns:repeat(auto-fit,minmax(260px,1fr)); gap:1.25rem; }
  .def-card { background:#fff; border-radius:16px; padding:1.75rem; border-top:4px solid; box-shadow:0 1px 4px rgba(0,0,0,0.06); }
  .def-card.teal { border-color:var(--teal-light); } .def-card.blue { border-color:var(--blue-light); } .def-card.amber { border-color:var(--amber-light); }
  .def-card h3 { font-family:var(--font-display); font-size:1.1rem; font-weight:600; margin-bottom:0.6rem; }
  .def-card.teal h3 { color:var(--teal-deep); } .def-card.blue h3 { color:var(--blue-deep); } .def-card.amber h3 { color:var(--amber-deep); }
  .def-card p { font-size:0.92rem; color:var(--gray-mid); line-height:1.65; }
  .scenario-box { background:var(--amber-pale); border-left:5px solid var(--amber-light); border-radius:0 12px 12px 0; padding:1.5rem 1.75rem; margin-top:2rem; }
  .scenario-label { font-size:0.72rem; font-weight:500; letter-spacing:0.12em; text-transform:uppercase; color:var(--amber-mid); margin-bottom:0.5rem; }
  .scenario-box p { font-size:0.95rem; color:var(--amber-deep); line-height:1.6; font-style:italic; }

  .pedagogy-grid { display:grid; grid-template-columns:repeat(auto-fit,minmax(280px,1fr)); gap:1.5rem; }
  .pcard { background:#fff; border-radius:16px; overflow:hidden; box-shadow:0 1px 4px rgba(0,0,0,0.07); }
  .pcard-header { padding:1.5rem 1.5rem 1rem; display:flex; align-items:flex-start; gap:1rem; }
  .pcard-icon { width:46px; height:46px; border-radius:12px; display:flex; align-items:center; justify-content:center; flex-shrink:0; font-size:1.4rem; }
  .pcard-icon.teal{background:var(--teal-pale);} .pcard-icon.blue{background:var(--blue-pale);} .pcard-icon.amber{background:var(--amber-pale);}
  .pcard h3 { font-family:var(--font-display); font-size:1.05rem; font-weight:600; color:var(--teal-deep); margin-bottom:0.3rem; }
  .pcard-tagline { font-size:0.82rem; color:var(--gray-mid); }
  .pcard-body { padding:0 1.5rem 1.5rem; }
  .pcard-body p { font-size:0.9rem; color:var(--gray-mid); line-height:1.65; margin-bottom:0.75rem; }
  .example-tag { display:inline-block; background:var(--teal-pale); color:var(--teal-deep); border-radius:999px; font-size:0.78rem; font-weight:500; padding:0.25rem 0.8rem; }
  .pcard-footer { background:var(--teal-pale); padding:0.85rem 1.5rem; font-size:0.82rem; color:var(--teal-mid); font-weight:500; }
  .key-message { background:linear-gradient(135deg,var(--teal-deep),var(--teal-mid)); color:#fff; border-radius:16px; padding:2rem 2.25rem; margin-top:2rem; font-family:var(--font-display); font-size:1.1rem; font-weight:300; line-height:1.55; font-style:italic; }

  .lit-grid { display:grid; grid-template-columns:repeat(auto-fit,minmax(200px,1fr)); gap:1rem; margin-bottom:2rem; }
  .lit-card { background:#fff; border-radius:14px; padding:1.5rem 1.25rem; text-align:center; box-shadow:0 1px 4px rgba(0,0,0,0.06); transition:transform 0.2s; }
  .lit-card:hover{transform:translateY(-3px);}
  .lit-icon{font-size:2rem;margin-bottom:0.75rem;}
  .lit-card h3{font-size:0.95rem;font-weight:500;color:var(--teal-deep);margin-bottom:0.5rem;}
  .lit-card p{font-size:0.82rem;color:var(--gray-mid);line-height:1.55;}
  .checklist{background:var(--teal-deep);color:#fff;border-radius:16px;padding:2rem;}
  .checklist h3{font-family:var(--font-display);font-size:1.15rem;font-weight:400;color:var(--teal-soft);margin-bottom:1.25rem;}
  .checklist-item{display:flex;align-items:flex-start;gap:0.75rem;padding:0.6rem 0;border-bottom:1px solid rgba(255,255,255,0.1);font-size:0.92rem;color:rgba(255,255,255,0.85);}
  .checklist-item:last-child{border-bottom:none;}
  .check-box{width:22px;height:22px;border-radius:6px;border:2px solid var(--teal-soft);flex-shrink:0;margin-top:2px;display:flex;align-items:center;justify-content:center;cursor:pointer;transition:background 0.2s;}
  .check-box.checked{background:var(--teal-light);border-color:var(--teal-light);}
  .check-box.checked::after{content:'✓';font-size:12px;color:#fff;font-weight:700;}

  .strategies-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));gap:1rem;}
  .strategy-card{background:#fff;border-radius:14px;padding:1.25rem 1.5rem;box-shadow:0 1px 4px rgba(0,0,0,0.06);display:flex;gap:1rem;align-items:flex-start;transition:box-shadow 0.2s;}
  .strategy-card:hover{box-shadow:0 4px 16px rgba(0,0,0,0.1);}
  .s-num{width:36px;height:36px;border-radius:10px;background:var(--teal-pale);color:var(--teal-deep);font-weight:700;font-size:0.9rem;display:flex;align-items:center;justify-content:center;flex-shrink:0;}
  .strategy-card h3{font-size:0.95rem;font-weight:500;color:var(--gray-deep);margin-bottom:0.25rem;}
  .strategy-card p{font-size:0.82rem;color:var(--gray-mid);}

  /* MODAL OVERLAY */
  .modal-overlay{display:none;position:fixed;inset:0;background:rgba(0,0,0,0.6);z-index:1000;align-items:center;justify-content:center;padding:1rem;}
  .modal-overlay.active{display:flex;}
  .modal-box{background:#fff;border-radius:20px;width:100%;max-width:780px;max-height:90vh;overflow:hidden;display:flex;flex-direction:column;box-shadow:0 20px 60px rgba(0,0,0,0.3);}
  .modal-header{padding:1.25rem 1.5rem;border-bottom:1px solid var(--gray-pale);display:flex;align-items:center;gap:1rem;flex-shrink:0;}
  .modal-title{font-family:var(--font-display);font-size:1.1rem;font-weight:600;color:var(--teal-deep);flex:1;}
  .modal-close{width:36px;height:36px;border-radius:10px;border:none;background:var(--gray-pale);cursor:pointer;font-size:1.1rem;display:flex;align-items:center;justify-content:center;transition:background 0.2s;flex-shrink:0;}
  .modal-close:hover{background:#e0ded7;}
  .modal-content{overflow-y:auto;padding:1.75rem 2rem;flex:1;}
  .modal-footer{padding:1rem 1.5rem;border-top:1px solid var(--gray-pale);display:flex;gap:0.75rem;justify-content:flex-end;flex-shrink:0;background:#fafaf8;}
  .btn-print{padding:0.6rem 1.25rem;border-radius:10px;border:none;background:var(--teal-light);color:#fff;font-family:var(--font-body);font-size:0.85rem;font-weight:600;cursor:pointer;transition:background 0.2s;}
  .btn-print:hover{background:var(--teal-mid);}
  .btn-close2{padding:0.6rem 1.25rem;border-radius:10px;border:1.5px solid var(--gray-light);background:transparent;color:var(--gray-mid);font-family:var(--font-body);font-size:0.85rem;cursor:pointer;}

  /* RESOURCE CONTENT STYLES (inside modal) */
  .res-doc{font-family:var(--font-body);color:var(--gray-deep);}
  .res-doc h1{font-family:var(--font-display);font-size:1.4rem;font-weight:600;color:var(--teal-deep);margin-bottom:0.25rem;}
  .res-doc .res-subtitle{font-size:0.85rem;color:var(--gray-mid);margin-bottom:1.5rem;}
  .res-doc h2{font-family:var(--font-display);font-size:1rem;font-weight:600;color:var(--teal-deep);margin:1.5rem 0 0.6rem;padding:0.5rem 0.75rem;background:var(--teal-pale);border-radius:8px;}
  .res-doc h3{font-size:0.9rem;font-weight:600;color:var(--teal-mid);margin:1rem 0 0.4rem;}
  .res-doc p{font-size:0.88rem;color:var(--gray-mid);line-height:1.65;margin-bottom:0.6rem;}
  .res-doc table{width:100%;border-collapse:collapse;margin:0.75rem 0 1rem;font-size:0.82rem;}
  .res-doc th{background:var(--teal-deep);color:#fff;padding:0.6rem 0.75rem;text-align:left;font-weight:500;}
  .res-doc td{padding:0.55rem 0.75rem;border-bottom:1px solid var(--gray-pale);vertical-align:top;color:var(--gray-mid);}
  .res-doc tr:nth-child(even) td{background:#fafaf8;}
  .res-doc .field-box{border:1.5px solid var(--gray-light);border-radius:8px;padding:0.6rem 0.75rem;min-height:48px;margin-bottom:0.75rem;font-size:0.82rem;color:var(--gray-light);}
  .res-doc .two-col{display:grid;grid-template-columns:1fr 1fr;gap:1rem;}
  .res-doc .badge{display:inline-block;font-size:0.7rem;font-weight:600;letter-spacing:0.08em;text-transform:uppercase;border-radius:999px;padding:0.2rem 0.65rem;margin-bottom:0.75rem;}
  .res-doc .badge-teal{background:var(--teal-pale);color:var(--teal-deep);}
  .res-doc .badge-blue{background:var(--blue-pale);color:var(--blue-deep);}
  .res-doc .badge-amber{background:var(--amber-pale);color:var(--amber-deep);}
  .res-doc .cer-box{border:2px solid var(--teal-light);border-radius:12px;padding:1rem 1.25rem;margin-bottom:1rem;}
  .res-doc .cer-label{font-size:0.75rem;font-weight:700;letter-spacing:0.1em;text-transform:uppercase;color:var(--teal-deep);margin-bottom:0.35rem;}
  .res-doc .prompt-card{border-radius:12px;padding:1rem 1.25rem;margin-bottom:0.75rem;}
  .res-doc .rating-row{display:flex;align-items:center;gap:0.75rem;margin-bottom:0.6rem;font-size:0.85rem;}
  .res-doc .rating-dots{display:flex;gap:4px;}
  .res-doc .dot{width:16px;height:16px;border-radius:50%;border:2px solid var(--teal-mid);cursor:pointer;transition:background 0.15s;}
  .res-doc .dot:hover{background:var(--teal-light);}
  .res-doc .divider{border:none;border-top:2px solid var(--gray-pale);margin:1.25rem 0;}
  .res-doc .info-strip{background:var(--teal-pale);border-radius:10px;padding:0.75rem 1rem;font-size:0.82rem;color:var(--teal-deep);margin-bottom:1rem;}

  /* Download cards */
  .downloads-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(240px,1fr));gap:1.25rem;margin-top:2rem;}
  .dl-card{background:#fff;border-radius:16px;overflow:hidden;box-shadow:0 2px 8px rgba(0,0,0,0.08);display:flex;flex-direction:column;transition:transform 0.2s,box-shadow 0.2s;}
  .dl-card:hover{transform:translateY(-3px);box-shadow:0 6px 20px rgba(0,0,0,0.12);}
  .dl-card-top{padding:1.5rem 1.25rem 1rem;flex:1;}
  .dl-badge{display:inline-block;font-size:0.68rem;font-weight:600;letter-spacing:0.1em;text-transform:uppercase;border-radius:999px;padding:0.2rem 0.65rem;margin-bottom:0.75rem;}
  .dl-icon{font-size:2.2rem;margin-bottom:0.6rem;display:block;}
  .dl-card h4{font-size:0.92rem;font-weight:600;margin-bottom:0.4rem;line-height:1.3;}
  .dl-card p{font-size:0.8rem;color:var(--gray-mid);line-height:1.55;margin-bottom:0.6rem;}
  .dl-meta{font-size:0.72rem;color:var(--gray-light);margin-top:0.25rem;}
  .dl-card-footer{padding:0.85rem 1.25rem;display:flex;gap:0.5rem;align-items:center;border-top:1px solid var(--gray-pale);}
  .btn-open{flex:1;display:inline-block;text-align:center;padding:0.55rem 0.75rem;border-radius:8px;font-size:0.78rem;font-weight:600;text-decoration:none;cursor:pointer;border:none;font-family:var(--font-body);transition:background 0.2s,transform 0.1s;}
  .btn-open:hover{transform:translateY(-1px);}
  .btn-tag{display:inline-block;padding:0.4rem 0.75rem;border-radius:8px;font-size:0.75rem;font-weight:500;background:var(--gray-pale);color:var(--gray-mid);border:none;}
  .dl-r1{border-top:4px solid var(--teal-light);}
  .dl-r1 .dl-badge{background:var(--teal-pale);color:var(--teal-deep);}
  .dl-r1 h4{color:var(--teal-deep);}
  .dl-r1 .btn-open{background:var(--teal-light);color:#fff;}
  .dl-r1 .btn-open:hover{background:var(--teal-mid);}
  .dl-r2{border-top:4px solid var(--blue-light);}
  .dl-r2 .dl-badge{background:var(--blue-pale);color:var(--blue-deep);}
  .dl-r2 h4{color:var(--blue-deep);}
  .dl-r2 .btn-open{background:var(--blue-light);color:#fff;}
  .dl-r2 .btn-open:hover{background:var(--blue-mid);}
  .dl-r3{border-top:4px solid var(--amber-light);}
  .dl-r3 .dl-badge{background:var(--amber-pale);color:var(--amber-deep);}
  .dl-r3 h4{color:var(--amber-deep);}
  .dl-r3 .btn-open{background:var(--amber-light);color:#fff;}
  .dl-r3 .btn-open:hover{background:var(--amber-mid);}
  .dl-r4{border-top:4px solid #534AB7;}
  .dl-r4 .dl-badge{background:#EEEDFE;color:#26215C;}
  .dl-r4 h4{color:#26215C;}
  .dl-r4 .btn-open{background:#534AB7;color:#fff;}
  .dl-r4 .btn-open:hover{background:#3C3489;}
  .dl-intro{background:linear-gradient(135deg,var(--teal-pale),var(--blue-pale));border-radius:14px;padding:1.25rem 1.5rem;margin-bottom:1.5rem;display:flex;gap:1rem;align-items:center;}
  .dl-intro-icon{font-size:1.8rem;flex-shrink:0;}
  .dl-intro p{font-size:0.88rem;color:var(--teal-deep);line-height:1.55;}

  /* Reflection section */
  .reflect-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(280px,1fr));gap:1.25rem;}
  .reflect-card{background:#fff;border-radius:16px;padding:1.75rem;border-left:4px solid var(--blue-light);box-shadow:0 1px 4px rgba(0,0,0,0.06);}
  .reflect-q{font-family:var(--font-display);font-size:1rem;font-weight:400;color:var(--blue-deep);font-style:italic;line-height:1.5;margin-bottom:0.75rem;}
  .reflect-hint{font-size:0.82rem;color:var(--gray-mid);line-height:1.55;}
  .pd-banner{background:var(--blue-mid);color:#fff;border-radius:16px;padding:2rem 2.25rem;margin-bottom:2.5rem;display:flex;gap:1.5rem;align-items:center;flex-wrap:wrap;}
  .pd-banner-icon{font-size:2.5rem;flex-shrink:0;}
  .pd-banner h3{font-family:var(--font-display);font-size:1.2rem;font-weight:400;margin-bottom:0.4rem;}
  .pd-banner p{font-size:0.9rem;color:rgba(255,255,255,0.8);}

  /* References */
  .ref-section{background:var(--teal-deep);color:#fff;}
  .ref-section .section-title{color:var(--teal-soft);}
  .ref-section .section-lead{color:rgba(255,255,255,0.65);}
  .ref-links{display:grid;grid-template-columns:repeat(auto-fit,minmax(240px,1fr));gap:1rem;margin-bottom:2.5rem;}
  .ref-link-card{background:rgba(255,255,255,0.07);border:1px solid rgba(255,255,255,0.14);border-radius:14px;padding:1.25rem;}
  .ref-link-card h4{font-size:0.9rem;font-weight:500;color:var(--teal-soft);margin-bottom:0.4rem;}
  .ref-link-card p{font-size:0.8rem;color:rgba(255,255,255,0.65);line-height:1.55;}
  .ref-link-card a{color:var(--teal-soft);font-size:0.78rem;}
  .ref-list{list-style:none;}
  .ref-list li{padding:0.9rem 0;border-bottom:1px solid rgba(255,255,255,0.1);font-size:0.88rem;color:rgba(255,255,255,0.72);line-height:1.6;}
  .ref-list li:last-child{border-bottom:none;}

  footer{background:#111;color:rgba(255,255,255,0.5);text-align:center;padding:1.5rem 2rem;font-size:0.8rem;}
  @media(max-width:640px){nav{padding:0 1rem;}.nav-brand{font-size:0.9rem;}.nav-links a{padding:0 0.6rem;font-size:0.75rem;}section{padding:3rem 1.25rem;}.res-doc .two-col{grid-template-columns:1fr;}.modal-content{padding:1.25rem;}}

  @media print {
    nav, .modal-header, .modal-footer, .hero, #context, #pedagogies, #literacies, #strategies .strategies-grid, #strategies > .container > .section-eyebrow, #strategies > .container > .section-title, #strategies > .container > .section-lead, #reflection, #resources, footer { display: none !important; }
    .modal-overlay { display: block !important; position: static; background: none; padding: 0; }
    .modal-box { box-shadow: none; max-height: none; border-radius: 0; }
    .modal-content { overflow: visible; }
  }
</style>
</head>
<body>

<!-- ═══════════════════════════════════ MODAL ═══════════════════════════════════ -->
<div class="modal-overlay" id="resModal">
  <div class="modal-box">
    <div class="modal-header">
      <span class="modal-title" id="modalTitle">Resource</span>
      <button class="modal-close" onclick="closeModal()">✕</button>
    </div>
    <div class="modal-content" id="modalContent"></div>
    <div class="modal-footer">
      <button class="btn-close2" onclick="closeModal()">Close</button>
      <button class="btn-print" onclick="window.print()">🖨️ Print / Save PDF</button>
    </div>
  </div>
</div>

<!-- NAV -->
<nav>
  <span class="nav-brand">STEM & Post-Truth</span>
  <ul class="nav-links">
    <li><a href="#context">Context</a></li>
    <li><a href="#pedagogies">Pedagogies</a></li>
    <li><a href="#literacies">Literacies</a></li>
    <li><a href="#strategies">Strategies</a></li>
    <li><a href="#reflection">Reflection</a></li>
    <li><a href="#resources">Resources</a></li>
  </ul>
</nav>

<!-- HERO -->
<div class="hero">
  <p class="hero-eyebrow">Professional Learning Resource · EDUC6046</p>
  <h1>STEM Teaching in a<br><em>Post-Truth Era</em></h1>
  <p class="hero-sub">Supporting teachers to build critical, inquiry-based STEM classrooms where students learn to navigate misinformation and evaluate evidence.</p>
  <div class="hero-pills">
    <a href="#context" class="pill pill-teal">🌏 Understanding the Challenge</a>
    <a href="#pedagogies" class="pill pill-amber">📐 STEM Pedagogies</a>
    <a href="#literacies" class="pill pill-blue">🔍 Critical Literacies</a>
    <a href="#strategies" class="pill pill-coral">💡 Practical Strategies</a>
  </div>
</div>

<!-- PAGE 1: CONTEXT -->
<section id="context">
  <div class="container">
    <p class="section-eyebrow">Page 1 — Foundation</p>
    <h2 class="section-title">Understanding STEM in a Post-Truth World</h2>
    <p class="section-lead">Before we can equip students, we must understand the landscape teachers and learners navigate every day.</p>
    <div class="def-grid">
      <div class="def-card teal">
        <h3>🔬 What is STEM Education?</h3>
        <p>STEM education integrates <strong>Science, Technology, Engineering, and Mathematics</strong> to support problem-solving, creativity, collaboration, and critical thinking. It is inherently inquiry-driven and evidence-based — skills students urgently need in today's information environment.</p>
      </div>
      <div class="def-card blue">
        <h3>📡 What is a Post-Truth Environment?</h3>
        <p>A <em>post-truth environment</em> is one where emotions, opinions, and misinformation can influence people more powerfully than evidence and facts. Social media algorithms amplify emotionally resonant content, regardless of its accuracy.</p>
      </div>
      <div class="def-card amber">
        <h3>⚠️ Why This Matters in STEM</h3>
        <p>Students are constantly exposed to information from social media, online platforms, and digital spaces. Teachers must help them evaluate evidence, identify credible sources, and understand the difference between scientific consensus and contested claims.</p>
      </div>
    </div>
    <div class="scenario-box">
      <p class="scenario-label">📖 Classroom Scenario</p>
      <p>A student challenges climate change science using misinformation shared on social media. How does a STEM teacher respond in a way that is academically rigorous, emotionally sensitive, and builds lasting critical thinking skills?</p>
    </div>
  </div>
</section>

<!-- PAGE 2: PEDAGOGIES -->
<section id="pedagogies" style="background:var(--gray-pale);">
  <div class="container">
    <p class="section-eyebrow">Page 2 — Pedagogy</p>
    <h2 class="section-title">Student-Centred STEM Pedagogies</h2>
    <p class="section-lead">Effective STEM teaching uses learner-driven approaches that naturally build critical thinking and evidence evaluation skills.</p>
    <div class="pedagogy-grid">
      <div class="pcard">
        <div class="pcard-header"><div class="pcard-icon teal">🔎</div><div><h3>Inquiry-Based Learning</h3><span class="pcard-tagline">Question → Evidence → Explanation</span></div></div>
        <div class="pcard-body"><p>Students investigate questions, collect evidence, and develop explanations through a structured process that mirrors authentic scientific practice.</p><span class="example-tag">Example: Investigating local water quality</span></div>
        <div class="pcard-footer">Builds: questioning, data collection, evidence reasoning</div>
      </div>
      <div class="pcard">
        <div class="pcard-header"><div class="pcard-icon blue">🧩</div><div><h3>Problem-Based Learning</h3><span class="pcard-tagline">Real Problems → STEM Solutions</span></div></div>
        <div class="pcard-body"><p>Students solve authentic real-world problems using STEM concepts, developing the habit of applying knowledge to messy, genuine challenges.</p><span class="example-tag">Example: Designing solutions for community waste management</span></div>
        <div class="pcard-footer">Builds: application, collaboration, systems thinking</div>
      </div>
      <div class="pcard">
        <div class="pcard-header"><div class="pcard-icon amber">🛠️</div><div><h3>Project-Based Learning</h3><span class="pcard-tagline">Knowledge → Collaborative Creation</span></div></div>
        <div class="pcard-body"><p>Students create projects that apply STEM knowledge collaboratively, producing tangible artefacts that demonstrate understanding.</p><span class="example-tag">Example: Designing low-cost solar energy models</span></div>
        <div class="pcard-footer">Builds: creativity, teamwork, communication</div>
      </div>
    </div>
    <div class="key-message">"Student-centred STEM learning helps students question information, test evidence, and construct knowledge responsibly — the very skills needed to navigate a post-truth world."</div>
  </div>
</section>

<!-- PAGE 3: LITERACIES -->
<section id="literacies">
  <div class="container">
    <p class="section-eyebrow">Page 3 — Critical Literacies</p>
    <h2 class="section-title">The Four Critical Literacies in STEM</h2>
    <p class="section-lead">Equipping students with multiple overlapping literacies gives them the tools to navigate misinformation at every level.</p>
    <div class="lit-grid">
      <div class="lit-card"><div class="lit-icon">💻</div><h3>Digital Literacy</h3><p>Students learn to use digital tools responsibly and understand how online platforms curate and amplify information.</p></div>
      <div class="lit-card"><div class="lit-icon">📰</div><h3>Media Literacy</h3><p>Students critically evaluate media messages, identify bias, and understand how news and social media work.</p></div>
      <div class="lit-card"><div class="lit-icon">🧪</div><h3>Scientific Literacy</h3><p>Students understand scientific concepts, how knowledge is generated, and how to evaluate evidence and consensus.</p></div>
      <div class="lit-card"><div class="lit-icon">🏛️</div><h3>Critical Literacy</h3><p>Students question bias, assumptions, and power structures embedded in how information is created and shared.</p></div>
    </div>
    <div class="checklist">
      <h3>✅ Teacher Checklist: Evaluating Information</h3>
      <div class="checklist-item"><div class="check-box" onclick="this.classList.toggle('checked')"></div><span>Who created this information, and what is their expertise or motivation?</span></div>
      <div class="checklist-item"><div class="check-box" onclick="this.classList.toggle('checked')"></div><span>Is evidence provided? Is the evidence peer-reviewed or scientifically validated?</span></div>
      <div class="checklist-item"><div class="check-box" onclick="this.classList.toggle('checked')"></div><span>Is the source credible and transparent about its methods and funding?</span></div>
      <div class="checklist-item"><div class="check-box" onclick="this.classList.toggle('checked')"></div><span>Does the information align with the broader scientific consensus?</span></div>
      <div class="checklist-item"><div class="check-box" onclick="this.classList.toggle('checked')"></div><span>Are emotional appeals being used to override evidence-based reasoning?</span></div>
    </div>
  </div>
</section>

<!-- PAGE 4: STRATEGIES -->
<section id="strategies" style="background:var(--gray-pale);">
  <div class="container">
    <p class="section-eyebrow">Page 4 — Practice</p>
    <h2 class="section-title">Practical Strategies for Teachers</h2>
    <p class="section-lead">Concrete, classroom-ready approaches that embed critical thinking into everyday STEM teaching.</p>
    <div class="strategies-grid">
      <div class="strategy-card"><div class="s-num">1</div><div><h3>Collaborative Group Investigations</h3><p>Students work in teams to investigate a question together, sharing evidence and challenging each other's reasoning.</p></div></div>
      <div class="strategy-card"><div class="s-num">2</div><div><h3>Reflective Questioning</h3><p>Use structured questions like "How do you know?", "What's the evidence?" to build metacognitive habits.</p></div></div>
      <div class="strategy-card"><div class="s-num">3</div><div><h3>Evidence-Based Classroom Discussions</h3><p>Structured discussions where students must cite evidence for every claim, modelling scientific discourse.</p></div></div>
      <div class="strategy-card"><div class="s-num">4</div><div><h3>Fact-Checking Activities</h3><p>Students use reliable tools (e.g., Snopes, Google Scholar) to evaluate claims encountered in the news or social media.</p></div></div>
      <div class="strategy-card"><div class="s-num">5</div><div><h3>STEM Inquiry Tasks</h3><p>Open-ended investigations where students design their own research questions and methodology.</p></div></div>
      <div class="strategy-card"><div class="s-num">6</div><div><h3>Community-Based STEM Projects</h3><p>Connect learning to local issues — pollution, water access, conservation — giving evidence-evaluation authentic stakes.</p></div></div>
    </div>

    <h3 style="font-family:var(--font-display);font-size:1.35rem;font-weight:400;color:var(--teal-deep);margin:2.5rem 0 0.75rem;">📥 Classroom-Ready Downloadable Resources</h3>
    <div class="dl-intro">
      <div class="dl-intro-icon">🖨️</div>
      <p>Each resource below was developed using <strong>best-practice frameworks</strong> from STEM education research. Click <strong>Open Resource</strong> to view the full document — you can also print or save as PDF from inside each resource.</p>
    </div>

    <div class="downloads-grid">
      <div class="dl-card dl-r1">
        <div class="dl-card-top">
          <span class="dl-badge">Resource 1 · Teacher Tool</span>
          <span class="dl-icon">📋</span>
          <h4>5E STEM Lesson Plan Template — Post-Truth Edition</h4>
          <p>A complete lesson plan built on the 5E Instructional Model (Engage → Explore → Explain → Elaborate → Evaluate), adapted for post-truth STEM teaching with CER integration and reflection space.</p>
          <p class="dl-meta">📐 5E Model · Bybee et al. (2006) · 2 pages · Print-ready</p>
        </div>
        <div class="dl-card-footer">
          <button class="btn-open" onclick="openResource('r1')">⬇ Open Resource</button>
          <span class="btn-tag">Teacher</span>
        </div>
      </div>
      <div class="dl-card dl-r2">
        <div class="dl-card-top">
          <span class="dl-badge">Resource 2 · Student Worksheet</span>
          <span class="dl-icon">🔬</span>
          <h4>CER Inquiry Activity Template — STEM Post-Truth</h4>
          <p>A student-facing worksheet combining the SIFT method for source checking with the Claim–Evidence–Reasoning framework for scientific argumentation.</p>
          <p class="dl-meta">📐 CER · SIFT (Caulfield, 2019) · 2 pages · Print-ready</p>
        </div>
        <div class="dl-card-footer">
          <button class="btn-open" onclick="openResource('r2')">⬇ Open Resource</button>
          <span class="btn-tag">Students</span>
        </div>
      </div>
      <div class="dl-card dl-r3">
        <div class="dl-card-top">
          <span class="dl-badge">Resource 3 · Discussion Cards</span>
          <span class="dl-icon">💬</span>
          <h4>STEM Discussion Prompt Cards — Post-Truth</h4>
          <p>20 colour-coded discussion cards across 5 critical thinking levels with a Think–Pair–Evidence–Share protocol and academic sentence starters.</p>
          <p class="dl-meta">📐 Levels: Entry · Intermediate · Advanced · Cut-and-use card format</p>
        </div>
        <div class="dl-card-footer">
          <button class="btn-open" onclick="openResource('r3')">⬇ Open Resource</button>
          <span class="btn-tag">Both</span>
        </div>
      </div>
      <div class="dl-card dl-r4">
        <div class="dl-card-top">
          <span class="dl-badge">Resource 4 · Teacher Reflection</span>
          <span class="dl-icon">📝</span>
          <h4>Teacher Reflection Worksheet — STEM Post-Truth</h4>
          <p>A structured professional reflection tool using the 4Ws framework (What → So What → Now What → What If) with confidence self-rating, goal-setting, and wellbeing check-in.</p>
          <p class="dl-meta">📐 Rolfe et al. (2001) · AITSL Standards aligned · After every lesson</p>
        </div>
        <div class="dl-card-footer">
          <button class="btn-open" onclick="openResource('r4')">⬇ Open Resource</button>
          <span class="btn-tag">Teacher</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- PAGE 5: REFLECTION -->
<section id="reflection">
  <div class="container">
    <p class="section-eyebrow">Page 5 — Teacher Growth</p>
    <h2 class="section-title">Professional Reflection & Teacher Development</h2>
    <p class="section-lead">Ongoing professional learning is essential for teachers navigating the rapidly changing information landscape in STEM education.</p>
    <div class="pd-banner">
      <div class="pd-banner-icon">🎓</div>
      <div><h3>Why Professional Development Matters</h3><p>Teachers need ongoing learning opportunities to strengthen STEM teaching confidence and to respond effectively to the misinformation challenges their students face every day.</p></div>
    </div>
    <h3 style="font-family:var(--font-display);font-size:1.15rem;font-weight:400;color:var(--teal-deep);margin-bottom:1.25rem;">Reflective Questions for Teachers</h3>
    <div class="reflect-grid">
      <div class="reflect-card"><p class="reflect-q">"How confident am I in teaching STEM concepts, particularly where student misconceptions or social media claims arise?"</p><p class="reflect-hint">Consider rating your confidence across different STEM areas and identifying where targeted PD might help.</p></div>
      <div class="reflect-card"><p class="reflect-q">"How do I currently help students evaluate information critically — and how might I do this more explicitly?"</p><p class="reflect-hint">Think about whether critical evaluation is embedded in your lessons or treated as a separate skill.</p></div>
      <div class="reflect-card"><p class="reflect-q">"What strategies can improve student inquiry, engagement, and critical thinking in my specific school context?"</p><p class="reflect-hint">Consider the cultural, resource, and community context of your school when selecting strategies.</p></div>
    </div>
    <div style="background:var(--blue-pale);border-radius:16px;padding:1.75rem 2rem;margin-top:2rem;">
      <h3 style="font-family:var(--font-display);font-size:1.05rem;font-weight:600;color:var(--blue-deep);margin-bottom:0.75rem;">📋 Teacher Self-Assessment Checklist</h3>
      <p style="font-size:0.9rem;color:var(--gray-mid);margin-bottom:1rem;">Rate yourself 1–5 in each area to identify your professional learning priorities:</p>
      <div style="display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:0.75rem;">
        <div style="background:#fff;border-radius:10px;padding:1rem;font-size:0.85rem;color:var(--gray-mid);">🔬 <strong>Scientific content knowledge</strong> — Can I explain the evidence behind key STEM topics?</div>
        <div style="background:#fff;border-radius:10px;padding:1rem;font-size:0.85rem;color:var(--gray-mid);">📱 <strong>Digital & media literacy</strong> — Do I model critical evaluation of online information?</div>
        <div style="background:#fff;border-radius:10px;padding:1rem;font-size:0.85rem;color:var(--gray-mid);">💬 <strong>Responding to misinformation</strong> — Do I have confident, evidence-based strategies?</div>
        <div style="background:#fff;border-radius:10px;padding:1rem;font-size:0.85rem;color:var(--gray-mid);">🤝 <strong>Student-centred facilitation</strong> — Do I foster student inquiry rather than transmit knowledge?</div>
      </div>
    </div>
  </div>
</section>

<!-- PAGE 6: RESOURCES -->
<section id="resources" class="ref-section">
  <div class="container">
    <p class="section-eyebrow" style="color:var(--teal-soft);">Page 6 — Resources & References</p>
    <h2 class="section-title">Resources & References</h2>
    <p class="section-lead">Curated professional and academic resources to deepen your understanding of post-truth challenges in STEM education.</p>
    <div class="ref-links">
      <div class="ref-link-card"><h4>🌐 UNESCO Digital Literacy</h4><p>Frameworks and policy resources for building digital literacy in education contexts.</p><a href="https://www.unesco.org/en/digital-education" target="_blank">unesco.org/en/digital-education ↗</a></div>
      <div class="ref-link-card"><h4>📊 OECD STEM Education</h4><p>International research and guidance on STEM teaching quality and student outcomes.</p><a href="https://www.oecd.org/education/school/stem-education.htm" target="_blank">oecd.org/education ↗</a></div>
      <div class="ref-link-card"><h4>🎓 Inquiry-Based Learning</h4><p>Videos, case studies, and professional readings on implementing inquiry in STEM classrooms.</p><a href="https://www.nsta.org" target="_blank">nsta.org ↗</a></div>
    </div>
    <h3 style="font-family:var(--font-display);font-size:1.1rem;font-weight:400;color:var(--teal-soft);margin-bottom:1rem;">APA 7 Reference List</h3>
    <ul class="ref-list">
      <li>Breakstone, J., Smith, M., Wineburg, S., Rapaport, A., Carle, J., Garland, M., & Saavedra, A. (2021). Students' civic online reasoning: A national portrait. <em>Educational Researcher, 50</em>(8), 505–515.</li>
      <li>Hobbs, R. (2010). <em>Digital and media literacy: A plan of action.</em> Aspen Institute.</li>
      <li>Lewandowsky, S., Ecker, U. K. H., & Cook, J. (2017). Beyond misinformation: Understanding and coping with the post-truth era. <em>Journal of Applied Research in Memory and Cognition, 6</em>(4), 353–369.</li>
      <li>OECD. (2019). <em>PISA 2018 results (Volume III): What school life means for students' lives.</em> OECD Publishing.</li>
      <li>Osborne, J. (2014). Teaching scientific practices: Meeting the challenge of change. <em>Journal of Science Teacher Education, 25</em>(2), 177–196.</li>
      <li>UNESCO. (2023). <em>Global education monitoring report 2023: Technology in education — A tool on whose terms?</em> UNESCO.</li>
    </ul>
    <div style="background:rgba(255,255,255,0.06);border:1px solid rgba(255,255,255,0.12);border-radius:16px;padding:1.75rem 2rem;margin-top:2.5rem;text-align:center;">
      <p style="font-family:var(--font-display);font-size:1.1rem;font-weight:300;color:#fff;line-height:1.6;font-style:italic;max-width:640px;margin:0 auto;">"Empowering teachers with STEM knowledge and critical literacy skills helps students become informed, evidence-based, and responsible learners in a post-truth world."</p>
    </div>
  </div>
</section>

<footer>STEM Teaching in a Post-Truth Era — EDUC6046 Assessment 2 · Professional Learning Resource</footer>

<script>
// ═══════════════════════ RESOURCE CONTENT ═══════════════════════

const resources = {

  r1: {
    title: '📋 Resource 1 — 5E STEM Lesson Plan Template (Post-Truth Edition)',
    html: `<div class="res-doc">
      <span class="badge badge-teal">Resource 1 · Teacher Tool</span>
      <h1>5E STEM Lesson Plan Template</h1>
      <p class="res-subtitle">Post-Truth Edition &nbsp;·&nbsp; EDUC6046 &nbsp;·&nbsp; Framework: Bybee et al. (2006) 5E Instructional Model</p>
      <div class="info-strip">📌 <strong>How to use:</strong> Complete each phase of the 5E model below. Use the Post-Truth Integration Checklist (bottom) before delivering your lesson to ensure critical literacy is embedded throughout.</div>

      <h2>📌 Lesson Overview</h2>
      <div class="two-col">
        <div>
          <h3>Subject / Learning Area</h3><div class="field-box">e.g. Science — Earth and Space Sciences</div>
          <h3>Year Level</h3><div class="field-box">e.g. Year 9</div>
          <h3>Duration</h3><div class="field-box">e.g. 60 minutes</div>
        </div>
        <div>
          <h3>Lesson Topic</h3><div class="field-box">e.g. Climate Change — Evidence &amp; Misconceptions</div>
          <h3>Curriculum Link</h3><div class="field-box">e.g. ACSSU189 — Earth's resources</div>
          <h3>Post-Truth Context / Focus Misconception</h3><div class="field-box">e.g. "Climate change is a hoax" — circulating on social media</div>
        </div>
      </div>

      <h2>🎯 Learning Objectives</h2>
      <p>By the end of this lesson, students will be able to:</p>
      <div class="field-box" style="min-height:80px;">1.<br>2.<br>3.</div>

      <h2>🔁 The 5E Phases</h2>
      <table>
        <tr><th style="width:18%">Phase</th><th style="width:38%">Teacher Actions</th><th style="width:44%">Student Activity / Post-Truth Integration</th></tr>
        <tr><td><strong>1. ENGAGE</strong><br><em style="font-size:0.75rem;color:#888">Hook &amp; activate prior knowledge</em></td><td><div class="field-box" style="min-height:60px;">Present a provocative claim from social media. Ask: "Have you seen this? Do you think it's true?"</div></td><td><div class="field-box" style="min-height:60px;">Students respond to claim. Identify their initial belief and source of that belief.</div></td></tr>
        <tr><td><strong>2. EXPLORE</strong><br><em style="font-size:0.75rem;color:#888">Investigate &amp; discover</em></td><td><div class="field-box" style="min-height:60px;">Provide data sets, primary sources, and conflicting media claims for students to examine.</div></td><td><div class="field-box" style="min-height:60px;">Students use SIFT method to evaluate sources. Complete evidence table.</div></td></tr>
        <tr><td><strong>3. EXPLAIN</strong><br><em style="font-size:0.75rem;color:#888">Construct meaning</em></td><td><div class="field-box" style="min-height:60px;">Facilitate discussion. Introduce scientific vocabulary and consensus position.</div></td><td><div class="field-box" style="min-height:60px;">Students explain findings using CER framework: Claim → Evidence → Reasoning.</div></td></tr>
        <tr><td><strong>4. ELABORATE</strong><br><em style="font-size:0.75rem;color:#888">Apply &amp; extend</em></td><td><div class="field-box" style="min-height:60px;">Connect to a real-world or community context. Pose an extension challenge.</div></td><td><div class="field-box" style="min-height:60px;">Students apply learning to a new scenario or design a response to the original misconception.</div></td></tr>
        <tr><td><strong>5. EVALUATE</strong><br><em style="font-size:0.75rem;color:#888">Assess understanding</em></td><td><div class="field-box" style="min-height:60px;">Use exit tickets, peer discussion, or written responses to assess learning.</div></td><td><div class="field-box" style="min-height:60px;">Students self-assess their initial belief vs. their evidence-based conclusion.</div></td></tr>
      </table>

      <h2>📐 Assessment Strategy</h2>
      <div class="two-col">
        <div><h3>Formative Assessment</h3><div class="field-box" style="min-height:56px;">e.g. Exit ticket: Write one piece of evidence and explain why it is reliable.</div></div>
        <div><h3>Success Criteria</h3><div class="field-box" style="min-height:56px;">e.g. Student can identify a credible source and use CER to explain a STEM concept.</div></div>
      </div>

      <h2>✅ Post-Truth Integration Checklist</h2>
      <table>
        <tr><th>Item</th><th style="width:80px;text-align:center;">✓</th></tr>
        <tr><td>At least one misconception or social media claim is addressed in the lesson</td><td style="text-align:center;">☐</td></tr>
        <tr><td>Students evaluate at least one source using SIFT or a similar framework</td><td style="text-align:center;">☐</td></tr>
        <tr><td>CER (Claim–Evidence–Reasoning) is explicitly used or modelled</td><td style="text-align:center;">☐</td></tr>
        <tr><td>Scientific consensus is distinguished from contested claims</td><td style="text-align:center;">☐</td></tr>
        <tr><td>Students reflect on how their thinking changed during the lesson</td><td style="text-align:center;">☐</td></tr>
      </table>

      <h2>💭 Teacher Reflection (after lesson)</h2>
      <div class="field-box" style="min-height:80px;">What worked well? What would I change? How did students engage with the post-truth element?</div>
    </div>`
  },

  r2: {
    title: '🔬 Resource 2 — CER Inquiry Activity Template (STEM Post-Truth)',
    html: `<div class="res-doc">
      <span class="badge badge-blue">Resource 2 · Student Worksheet</span>
      <h1>CER Inquiry Activity Template</h1>
      <p class="res-subtitle">STEM Post-Truth Edition &nbsp;·&nbsp; Frameworks: CER (McNeill &amp; Krajcik) · SIFT (Caulfield, 2019)</p>
      <div class="info-strip">📌 <strong>Instructions:</strong> Work through each section carefully. Your goal is to investigate a claim using real evidence and explain your reasoning like a scientist.</div>

      <h2>🔍 Part 1 — SIFT: Evaluating Your Source</h2>
      <p>Before you begin your investigation, evaluate one of the sources you plan to use using the <strong>SIFT method</strong>:</p>
      <table>
        <tr><th style="width:22%">Step</th><th style="width:38%">What to do</th><th style="width:40%">Your Response</th></tr>
        <tr><td><strong>S — Stop</strong></td><td>Pause before sharing or accepting the claim. What is your gut reaction?</td><td><div class="field-box" style="min-height:44px;"></div></td></tr>
        <tr><td><strong>I — Investigate the Source</strong></td><td>Who created this? What is their purpose or expertise?</td><td><div class="field-box" style="min-height:44px;"></div></td></tr>
        <tr><td><strong>F — Find Better Coverage</strong></td><td>What do other credible sources say about this topic?</td><td><div class="field-box" style="min-height:44px;"></div></td></tr>
        <tr><td><strong>T — Trace Claims</strong></td><td>Where did the original claim come from? Is it peer-reviewed or verified?</td><td><div class="field-box" style="min-height:44px;"></div></td></tr>
      </table>

      <h2>📊 Part 2 — Evidence Table</h2>
      <p>Record at least <strong>3 pieces of evidence</strong> from different sources. Rate the credibility of each source.</p>
      <table>
        <tr><th>#</th><th>Evidence (what does the source say?)</th><th>Source Name / Type</th><th>Credibility (1–5)</th><th>Why credible or not?</th></tr>
        <tr><td>1</td><td><div class="field-box" style="min-height:44px;"></div></td><td><div class="field-box" style="min-height:44px;"></div></td><td><div class="field-box" style="min-height:44px;"></div></td><td><div class="field-box" style="min-height:44px;"></div></td></tr>
        <tr><td>2</td><td><div class="field-box" style="min-height:44px;"></div></td><td><div class="field-box" style="min-height:44px;"></div></td><td><div class="field-box" style="min-height:44px;"></div></td><td><div class="field-box" style="min-height:44px;"></div></td></tr>
        <tr><td>3</td><td><div class="field-box" style="min-height:44px;"></div></td><td><div class="field-box" style="min-height:44px;"></div></td><td><div class="field-box" style="min-height:44px;"></div></td><td><div class="field-box" style="min-height:44px;"></div></td></tr>
      </table>

      <h2>✍️ Part 3 — CER Scientific Argument</h2>
      <p>Use the evidence above to build a complete scientific argument using the <strong>Claim–Evidence–Reasoning</strong> framework.</p>
      <div class="cer-box">
        <p class="cer-label">C — Claim</p>
        <p style="font-size:0.82rem;color:var(--gray-mid);margin-bottom:0.5rem;">State your position clearly. What do you believe to be true, based on the evidence?</p>
        <div class="field-box" style="min-height:60px;"></div>
      </div>
      <div class="cer-box">
        <p class="cer-label">E — Evidence</p>
        <p style="font-size:0.82rem;color:var(--gray-mid);margin-bottom:0.5rem;">Summarise the most important evidence from your table that supports your claim.</p>
        <div class="field-box" style="min-height:72px;"></div>
      </div>
      <div class="cer-box">
        <p class="cer-label">R — Reasoning</p>
        <p style="font-size:0.82rem;color:var(--gray-mid);margin-bottom:0.5rem;">Explain <em>why</em> your evidence supports your claim. How does science explain this?</p>
        <div class="field-box" style="min-height:80px;"></div>
      </div>

      <h2>🪞 Part 4 — Reflection</h2>
      <div class="two-col">
        <div><h3>Did your thinking change?</h3><div class="field-box" style="min-height:60px;">What did you believe before? What do you believe now?</div></div>
        <div><h3>What surprised you?</h3><div class="field-box" style="min-height:60px;">What was the most interesting or unexpected thing you discovered?</div></div>
      </div>
    </div>`
  },

  r3: {
    title: '💬 Resource 3 — STEM Discussion Prompt Cards (Post-Truth)',
    html: `<div class="res-doc">
      <span class="badge badge-amber">Resource 3 · Discussion Cards</span>
      <h1>STEM Discussion Prompt Cards</h1>
      <p class="res-subtitle">Post-Truth Edition &nbsp;·&nbsp; Cut along dotted lines &nbsp;·&nbsp; 5 categories across 3 levels</p>
      <div class="info-strip">📌 <strong>How to use:</strong> Print and cut these cards. Distribute by level or student readiness. Use the <strong>Think–Pair–Evidence–Share</strong> protocol: Think alone → Discuss with a partner → Find evidence → Share with class.</div>

      <h2>🟢 Level 1 — Entry: Understanding the Issue</h2>
      <div style="display:grid;grid-template-columns:1fr 1fr;gap:0.75rem;margin-bottom:0.5rem;">
        <div class="prompt-card" style="background:#E1F5EE;border:2px dashed var(--teal-light);">
          <p style="font-size:0.7rem;font-weight:700;color:var(--teal-deep);letter-spacing:0.08em;text-transform:uppercase;margin-bottom:0.4rem;">Card 1A</p>
          <p style="font-size:0.88rem;color:var(--teal-deep);font-weight:500;">"What is one thing you have seen online about [topic] that you were unsure was true?"</p>
          <p style="font-size:0.75rem;color:var(--teal-mid);margin-top:0.5rem;">Sentence starter: <em>"I saw a post that said... and I wasn't sure because..."</em></p>
        </div>
        <div class="prompt-card" style="background:#E1F5EE;border:2px dashed var(--teal-light);">
          <p style="font-size:0.7rem;font-weight:700;color:var(--teal-deep);letter-spacing:0.08em;text-transform:uppercase;margin-bottom:0.4rem;">Card 1B</p>
          <p style="font-size:0.88rem;color:var(--teal-deep);font-weight:500;">"What makes you trust a piece of information? List three things."</p>
          <p style="font-size:0.75rem;color:var(--teal-mid);margin-top:0.5rem;">Sentence starter: <em>"I trust information when I see..."</em></p>
        </div>
        <div class="prompt-card" style="background:#E1F5EE;border:2px dashed var(--teal-light);">
          <p style="font-size:0.7rem;font-weight:700;color:var(--teal-deep);letter-spacing:0.08em;text-transform:uppercase;margin-bottom:0.4rem;">Card 1C</p>
          <p style="font-size:0.88rem;color:var(--teal-deep);font-weight:500;">"What is the difference between an opinion and a scientific fact?"</p>
          <p style="font-size:0.75rem;color:var(--teal-mid);margin-top:0.5rem;">Sentence starter: <em>"A scientific fact is different because..."</em></p>
        </div>
        <div class="prompt-card" style="background:#E1F5EE;border:2px dashed var(--teal-light);">
          <p style="font-size:0.7rem;font-weight:700;color:var(--teal-deep);letter-spacing:0.08em;text-transform:uppercase;margin-bottom:0.4rem;">Card 1D</p>
          <p style="font-size:0.88rem;color:var(--teal-deep);font-weight:500;">"Why might someone share false information? What are their possible reasons?"</p>
          <p style="font-size:0.75rem;color:var(--teal-mid);margin-top:0.5rem;">Sentence starter: <em>"Someone might share false info because..."</em></p>
        </div>
      </div>

      <h2>🟡 Level 2 — Intermediate: Evaluating Evidence</h2>
      <div style="display:grid;grid-template-columns:1fr 1fr;gap:0.75rem;margin-bottom:0.5rem;">
        <div class="prompt-card" style="background:var(--amber-pale);border:2px dashed var(--amber-light);">
          <p style="font-size:0.7rem;font-weight:700;color:var(--amber-deep);letter-spacing:0.08em;text-transform:uppercase;margin-bottom:0.4rem;">Card 2A</p>
          <p style="font-size:0.88rem;color:var(--amber-deep);font-weight:500;">"Compare these two sources [A and B]. Which is more reliable, and why?"</p>
          <p style="font-size:0.75rem;color:var(--amber-mid);margin-top:0.5rem;">Sentence starter: <em>"Source A/B is more reliable because the evidence shows..."</em></p>
        </div>
        <div class="prompt-card" style="background:var(--amber-pale);border:2px dashed var(--amber-light);">
          <p style="font-size:0.7rem;font-weight:700;color:var(--amber-deep);letter-spacing:0.08em;text-transform:uppercase;margin-bottom:0.4rem;">Card 2B</p>
          <p style="font-size:0.88rem;color:var(--amber-deep);font-weight:500;">"What does the scientific consensus say about [topic]? How is this different from media coverage?"</p>
          <p style="font-size:0.75rem;color:var(--amber-mid);margin-top:0.5rem;">Sentence starter: <em>"Scientists agree that... however, in the media..."</em></p>
        </div>
        <div class="prompt-card" style="background:var(--amber-pale);border:2px dashed var(--amber-light);">
          <p style="font-size:0.7rem;font-weight:700;color:var(--amber-deep);letter-spacing:0.08em;text-transform:uppercase;margin-bottom:0.4rem;">Card 2C</p>
          <p style="font-size:0.88rem;color:var(--amber-deep);font-weight:500;">"Use the CER framework to respond to the claim: '[Insert claim here]'."</p>
          <p style="font-size:0.75rem;color:var(--amber-mid);margin-top:0.5rem;">Structure: <em>Claim → Evidence → Reasoning</em></p>
        </div>
        <div class="prompt-card" style="background:var(--amber-pale);border:2px dashed var(--amber-light);">
          <p style="font-size:0.7rem;font-weight:700;color:var(--amber-deep);letter-spacing:0.08em;text-transform:uppercase;margin-bottom:0.4rem;">Card 2D</p>
          <p style="font-size:0.88rem;color:var(--amber-deep);font-weight:500;">"Why might emotional language in a headline make us more likely to believe something?"</p>
          <p style="font-size:0.75rem;color:var(--amber-mid);margin-top:0.5rem;">Sentence starter: <em>"Emotional language affects us because..."</em></p>
        </div>
      </div>

      <h2>🔴 Level 3 — Advanced: Critical & Power Analysis</h2>
      <div style="display:grid;grid-template-columns:1fr 1fr;gap:0.75rem;margin-bottom:0.5rem;">
        <div class="prompt-card" style="background:var(--coral-pale);border:2px dashed var(--coral-light);">
          <p style="font-size:0.7rem;font-weight:700;color:var(--coral-mid);letter-spacing:0.08em;text-transform:uppercase;margin-bottom:0.4rem;">Card 3A</p>
          <p style="font-size:0.88rem;color:var(--coral-mid);font-weight:500;">"Who benefits from people believing this misinformation? What systems or interests does it protect?"</p>
          <p style="font-size:0.75rem;color:var(--coral-mid);margin-top:0.5rem;">Sentence starter: <em>"This misinformation benefits... because..."</em></p>
        </div>
        <div class="prompt-card" style="background:var(--coral-pale);border:2px dashed var(--coral-light);">
          <p style="font-size:0.7rem;font-weight:700;color:var(--coral-mid);letter-spacing:0.08em;text-transform:uppercase;margin-bottom:0.4rem;">Card 3B</p>
          <p style="font-size:0.88rem;color:var(--coral-mid);font-weight:500;">"How do algorithmic platforms shape what we think is true? What are the implications for scientific literacy?"</p>
          <p style="font-size:0.75rem;color:var(--coral-mid);margin-top:0.5rem;">Sentence starter: <em>"Algorithms influence our beliefs by..."</em></p>
        </div>
        <div class="prompt-card" style="background:var(--coral-pale);border:2px dashed var(--coral-light);">
          <p style="font-size:0.7rem;font-weight:700;color:var(--coral-mid);letter-spacing:0.08em;text-transform:uppercase;margin-bottom:0.4em;">Card 3C</p>
          <p style="font-size:0.88rem;color:var(--coral-mid);font-weight:500;">"How might cultural identity or lived experience shape how someone accepts or rejects scientific information?"</p>
          <p style="font-size:0.75rem;color:var(--coral-mid);margin-top:0.5rem;">Sentence starter: <em>"A person's background might affect their trust in science because..."</em></p>
        </div>
        <div class="prompt-card" style="background:var(--coral-pale);border:2px dashed var(--coral-light);">
          <p style="font-size:0.7rem;font-weight:700;color:var(--coral-mid);letter-spacing:0.08em;text-transform:uppercase;margin-bottom:0.4rem;">Card 3D</p>
          <p style="font-size:0.88rem;color:var(--coral-mid);font-weight:500;">"As a future citizen, what is your responsibility when you encounter misinformation in your community?"</p>
          <p style="font-size:0.75rem;color:var(--coral-mid);margin-top:0.5rem;">Sentence starter: <em>"I believe citizens have a responsibility to..."</em></p>
        </div>
      </div>

      <hr class="divider">
      <div class="info-strip">🧑‍🏫 <strong>Teacher Usage Guide:</strong> Distribute Level 1 cards for Years 7–8 or as warm-up starters. Use Level 2 for Years 9–10 investigation tasks. Reserve Level 3 for senior students or extension groups. Mix levels to encourage peer support and collaborative dialogue.</div>
    </div>`
  },

  r4: {
    title: '📝 Resource 4 — Teacher Reflection Worksheet (STEM Post-Truth)',
    html: `<div class="res-doc">
      <span class="badge" style="background:#EEEDFE;color:#26215C;">Resource 4 · Teacher Reflection</span>
      <h1>Teacher Reflection Worksheet</h1>
      <p class="res-subtitle">STEM Post-Truth Edition &nbsp;·&nbsp; Framework: Rolfe et al. (2001) What–So What–Now What &nbsp;·&nbsp; AITSL Standards Aligned</p>
      <div class="info-strip">📌 <strong>When to use:</strong> Complete this after every STEM lesson that addresses misinformation or post-truth challenges. Allow 10–15 minutes. Your reflections inform your professional growth over time.</div>

      <h2>📋 Lesson Snapshot</h2>
      <div class="two-col">
        <div>
          <h3>Date &amp; Year Level</h3><div class="field-box"></div>
          <h3>Topic / Misconception Addressed</h3><div class="field-box"></div>
        </div>
        <div>
          <h3>STEM Pedagogy Used (circle)</h3>
          <div class="field-box" style="min-height:44px;">Inquiry-Based &nbsp;&nbsp; Problem-Based &nbsp;&nbsp; Project-Based &nbsp;&nbsp; Direct Instruction &nbsp;&nbsp; Other</div>
          <h3>Post-Truth Strategy Used</h3>
          <div class="field-box" style="min-height:44px;">SIFT &nbsp;&nbsp; CER &nbsp;&nbsp; Discussion Prompts &nbsp;&nbsp; Fact-Check Activity &nbsp;&nbsp; Other</div>
        </div>
      </div>

      <h2>🔁 The 4Ws Reflection Framework</h2>
      <div class="cer-box" style="border-color:#534AB7;">
        <p class="cer-label" style="color:#26215C;">WHAT — What happened in this lesson?</p>
        <p style="font-size:0.82rem;color:var(--gray-mid);margin-bottom:0.5rem;">Describe the key moments. What did you do? How did students respond?</p>
        <div class="field-box" style="min-height:72px;"></div>
      </div>
      <div class="cer-box" style="border-color:var(--teal-light);">
        <p class="cer-label">SO WHAT — Why does it matter?</p>
        <p style="font-size:0.82rem;color:var(--gray-mid);margin-bottom:0.5rem;">What was significant about what happened? What does this tell you about student learning or your teaching?</p>
        <div class="field-box" style="min-height:72px;"></div>
      </div>
      <div class="cer-box" style="border-color:var(--blue-light);">
        <p class="cer-label" style="color:var(--blue-deep);">NOW WHAT — What will you do differently?</p>
        <p style="font-size:0.82rem;color:var(--gray-mid);margin-bottom:0.5rem;">What specific change will you make in your next lesson? What do you need to learn more about?</p>
        <div class="field-box" style="min-height:72px;"></div>
      </div>
      <div class="cer-box" style="border-color:var(--amber-light);">
        <p class="cer-label" style="color:var(--amber-deep);">WHAT IF — Exploring possibilities</p>
        <p style="font-size:0.82rem;color:var(--gray-mid);margin-bottom:0.5rem;">What if you had more time / resources / support? What possibilities might open up?</p>
        <div class="field-box" style="min-height:60px;"></div>
      </div>

      <h2>⭐ Confidence Self-Rating</h2>
      <p style="font-size:0.85rem;color:var(--gray-mid);margin-bottom:1rem;">Rate your confidence in each area today (1 = not confident, 5 = very confident):</p>
      <table>
        <tr><th>Teaching Area</th><th style="width:160px;text-align:center;">Rating (circle 1–5)</th></tr>
        <tr><td>Explaining the scientific consensus on today's topic</td><td style="text-align:center;">1 &nbsp; 2 &nbsp; 3 &nbsp; 4 &nbsp; 5</td></tr>
        <tr><td>Responding to student misinformation calmly and effectively</td><td style="text-align:center;">1 &nbsp; 2 &nbsp; 3 &nbsp; 4 &nbsp; 5</td></tr>
        <tr><td>Facilitating student-centred inquiry and discussion</td><td style="text-align:center;">1 &nbsp; 2 &nbsp; 3 &nbsp; 4 &nbsp; 5</td></tr>
        <tr><td>Embedding critical literacy into STEM content</td><td style="text-align:center;">1 &nbsp; 2 &nbsp; 3 &nbsp; 4 &nbsp; 5</td></tr>
        <tr><td>Using evidence-based teaching strategies</td><td style="text-align:center;">1 &nbsp; 2 &nbsp; 3 &nbsp; 4 &nbsp; 5</td></tr>
        <tr><td>Linking lesson to real-world post-truth challenges</td><td style="text-align:center;">1 &nbsp; 2 &nbsp; 3 &nbsp; 4 &nbsp; 5</td></tr>
      </table>

      <h2>🎯 Professional Learning Goals</h2>
      <div class="two-col">
        <div><h3>Short-term goal (next 2 weeks)</h3><div class="field-box" style="min-height:56px;"></div></div>
        <div><h3>Longer-term goal (this term)</h3><div class="field-box" style="min-height:56px;"></div></div>
      </div>
      <h3>Professional learning I need to seek out</h3>
      <div class="field-box" style="min-height:44px;">e.g. PD on scientific literacy, media literacy workshops, peer observation...</div>

      <h2>💙 Teacher Wellbeing Check-In</h2>
      <p style="font-size:0.85rem;color:var(--gray-mid);margin-bottom:0.75rem;">Teaching in a post-truth era can be emotionally demanding. How are you feeling today?</p>
      <div class="field-box" style="min-height:56px;">Reflect honestly. What support do you need?</div>
    </div>`
  }

};

function openResource(id) {
  const r = resources[id];
  if (!r) return;
  document.getElementById('modalTitle').textContent = r.title;
  document.getElementById('modalContent').innerHTML = r.html;
  document.getElementById('resModal').classList.add('active');
  document.body.style.overflow = 'hidden';
}

function closeModal() {
  document.getElementById('resModal').classList.remove('active');
  document.body.style.overflow = '';
}

// Close on backdrop click
document.getElementById('resModal').addEventListener('click', function(e) {
  if (e.target === this) closeModal();
});

// Close on Escape key
document.addEventListener('keydown', function(e) {
  if (e.key === 'Escape') closeModal();
});
</script>
</body>
</html>
