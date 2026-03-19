# devstew[index.html](https://github.com/user-attachments/files/26129602/index.html)
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>devstew — apps &amp; tools</title>
  <meta name="description" content="A portfolio of SaaS apps and tools built by devstew. Fully functioning and shipped." />
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600&family=Manrope:wght@600;700;800&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --bg:            #111318;
      --bg-surface:    #16191f;
      --bg-card:       #1c2028;
      --bg-card-h:     #20242d;
      --border:        rgba(255,255,255,0.07);
      --border-md:     rgba(255,255,255,0.11);
      --text-primary:  #f0f2f5;
      --text-secondary:#8b92a0;
      --text-muted:    #4a5062;
      --accent:        #4f6ef7;
      --accent-dim:    rgba(79,110,247,0.12);
      --accent-border: rgba(79,110,247,0.25);
      --green:         #22c55e;
      --green-dim:     rgba(34,197,94,0.1);
      --radius-sm:     6px;
      --radius-md:     10px;
      --radius-lg:     14px;
    }

    html { scroll-behavior: smooth; }

    body {
      background: var(--bg);
      color: var(--text-primary);
      font-family: 'Inter', sans-serif;
      min-height: 100vh;
      -webkit-font-smoothing: antialiased;
    }

    /* NAV */
    nav {
      position: sticky;
      top: 0;
      z-index: 100;
      background: rgba(17,19,24,0.9);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid var(--border);
      padding: 0 2.5rem;
      height: 60px;
      display: flex;
      align-items: center;
      justify-content: space-between;
    }

    .logo {
      font-family: 'Manrope', sans-serif;
      font-size: 18px;
      font-weight: 800;
      color: var(--text-primary);
      text-decoration: none;
      letter-spacing: -0.5px;
    }

    .logo-dot { color: var(--accent); }

    .nav-pill {
      font-size: 12px;
      font-weight: 500;
      color: var(--green);
      background: var(--green-dim);
      border: 1px solid rgba(34,197,94,0.2);
      padding: 4px 12px;
      border-radius: 20px;
      display: flex;
      align-items: center;
      gap: 6px;
    }

    .live-dot {
      width: 6px;
      height: 6px;
      border-radius: 50%;
      background: var(--green);
      animation: pulse 2s ease infinite;
    }

    @keyframes pulse { 0%,100%{opacity:1} 50%{opacity:0.35} }

    /* HERO */
    .hero {
      max-width: 1100px;
      margin: 0 auto;
      padding: 6rem 2.5rem 5rem;
      display: grid;
      grid-template-columns: 1fr auto;
      align-items: end;
      gap: 3rem;
    }

    .hero-label {
      font-size: 11px;
      font-weight: 600;
      letter-spacing: 2px;
      text-transform: uppercase;
      color: var(--accent);
      margin-bottom: 1.25rem;
    }

    .hero h1 {
      font-family: 'Manrope', sans-serif;
      font-size: clamp(2.6rem, 5vw, 4rem);
      font-weight: 800;
      line-height: 1.08;
      letter-spacing: -1.5px;
      color: var(--text-primary);
      margin-bottom: 1.25rem;
    }

    .hero h1 span { color: var(--accent); }

    .hero-desc {
      font-size: 15px;
      color: var(--text-secondary);
      line-height: 1.7;
      max-width: 420px;
    }

    .hero-stats {
      display: flex;
      flex-direction: column;
      align-items: flex-end;
      gap: 1.25rem;
      flex-shrink: 0;
    }

    .stat-block { text-align: right; }

    .stat-num {
      font-family: 'Manrope', sans-serif;
      font-size: 2.75rem;
      font-weight: 800;
      color: var(--text-primary);
      letter-spacing: -1.5px;
      line-height: 1;
    }

    .stat-label {
      font-size: 12px;
      color: var(--text-muted);
      margin-top: 4px;
    }

    .stat-divider {
      width: 1px;
      height: 32px;
      background: var(--border-md);
      align-self: flex-end;
    }

    /* SECTION */
    .section {
      max-width: 1100px;
      margin: 0 auto;
      padding: 0 2.5rem 5rem;
    }

    .section-header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 1.5rem;
      padding-bottom: 1.25rem;
      border-bottom: 1px solid var(--border);
    }

    .section-title {
      font-family: 'Manrope', sans-serif;
      font-size: 13px;
      font-weight: 700;
      color: var(--text-secondary);
      letter-spacing: 1px;
      text-transform: uppercase;
    }

    .section-count {
      font-size: 12px;
      color: var(--text-muted);
    }

    /* GRID */
    .apps-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 1px;
      background: var(--border);
      border: 1px solid var(--border);
      border-radius: var(--radius-lg);
      overflow: hidden;
    }

    /* CARD */
    .app-card {
      background: var(--bg-card);
      padding: 1.75rem;
      text-decoration: none;
      color: inherit;
      display: flex;
      flex-direction: column;
      position: relative;
      transition: background 0.15s;
      min-height: 230px;
    }

    .app-card:hover { background: var(--bg-card-h); }

    .app-card::before {
      content: '';
      position: absolute;
      top: 0; left: 0; right: 0;
      height: 1px;
      background: transparent;
      transition: background 0.2s;
    }

    .app-card:hover::before { background: var(--card-color, var(--accent)); }

    .card-head {
      display: flex;
      align-items: flex-start;
      justify-content: space-between;
      margin-bottom: 1.25rem;
    }

    .card-icon {
      width: 40px;
      height: 40px;
      border-radius: var(--radius-md);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 18px;
      flex-shrink: 0;
      border: 1px solid var(--border-md);
    }

    .type-tag {
      font-size: 10px;
      font-weight: 600;
      letter-spacing: 0.8px;
      text-transform: uppercase;
      padding: 3px 9px;
      border-radius: 4px;
    }

    .tag-saas {
      background: var(--accent-dim);
      color: #7b97fb;
      border: 1px solid var(--accent-border);
    }

    .tag-tool {
      background: var(--green-dim);
      color: #4ade80;
      border: 1px solid rgba(34,197,94,0.2);
    }

    .card-name {
      font-family: 'Manrope', sans-serif;
      font-size: 16px;
      font-weight: 700;
      color: var(--text-primary);
      letter-spacing: -0.3px;
      margin-bottom: 0.3rem;
    }

    .card-category {
      font-size: 11px;
      font-weight: 500;
      color: var(--text-muted);
      text-transform: uppercase;
      letter-spacing: 0.8px;
      margin-bottom: 0.85rem;
    }

    .card-desc {
      font-size: 13px;
      color: var(--text-secondary);
      line-height: 1.65;
      flex: 1;
      margin-bottom: 1.5rem;
    }

    .card-footer {
      display: flex;
      align-items: center;
      justify-content: space-between;
    }

    .cta-link {
      font-size: 12px;
      font-weight: 600;
      color: var(--accent);
      text-decoration: none;
      display: flex;
      align-items: center;
      gap: 4px;
      transition: gap 0.15s;
    }

    .app-card:hover .cta-link { gap: 7px; }

    .card-status {
      display: flex;
      align-items: center;
      gap: 5px;
      font-size: 11px;
      color: var(--text-muted);
    }

    .status-dot {
      width: 6px;
      height: 6px;
      border-radius: 50%;
      background: var(--green);
    }

    .app-card.placeholder { cursor: default; opacity: 0.38; }
    .app-card.placeholder:hover { background: var(--bg-card); }
    .app-card.placeholder::before { display: none; }

    /* ABOUT */
    .about-strip {
      max-width: 1100px;
      margin: 0 auto;
      padding: 3.5rem 2.5rem 4.5rem;
      border-top: 1px solid var(--border);
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 4rem;
      align-items: center;
    }

    .about-left h2 {
      font-family: 'Manrope', sans-serif;
      font-size: 1.65rem;
      font-weight: 800;
      color: var(--text-primary);
      letter-spacing: -0.5px;
      line-height: 1.2;
      margin-bottom: 0.85rem;
    }

    .about-left p {
      font-size: 14px;
      color: var(--text-secondary);
      line-height: 1.75;
    }

    .stack-grid {
      display: flex;
      flex-wrap: wrap;
      gap: 0.5rem;
    }

    .stack-pill {
      font-size: 12px;
      font-weight: 500;
      color: var(--text-secondary);
      background: var(--bg-card);
      border: 1px solid var(--border-md);
      padding: 6px 14px;
      border-radius: var(--radius-sm);
      transition: border-color 0.15s, color 0.15s;
    }

    .stack-pill:hover {
      border-color: var(--accent-border);
      color: var(--text-primary);
    }

    /* FOOTER */
    footer {
      border-top: 1px solid var(--border);
      padding: 1.5rem 2.5rem;
      display: flex;
      align-items: center;
      justify-content: space-between;
      max-width: 1100px;
      margin: 0 auto;
    }

    .footer-logo {
      font-family: 'Manrope', sans-serif;
      font-size: 14px;
      font-weight: 700;
      color: var(--text-muted);
    }

    .footer-logo span { color: var(--accent); }

    .footer-copy {
      font-size: 12px;
      color: var(--text-muted);
    }

    /* RESPONSIVE */
    @media (max-width: 960px) {
      .apps-grid { grid-template-columns: repeat(2, 1fr); }
      .hero { grid-template-columns: 1fr; }
      .hero-stats { flex-direction: row; align-items: center; justify-content: flex-start; }
      .stat-block { text-align: left; }
      .about-strip { grid-template-columns: 1fr; gap: 2rem; }
    }

    @media (max-width: 600px) {
      nav { padding: 0 1.25rem; }
      .hero { padding: 3.5rem 1.25rem 3rem; }
      .section { padding: 0 1.25rem 3rem; }
      .about-strip { padding: 2.5rem 1.25rem; }
      footer { padding: 1.5rem 1.25rem; flex-direction: column; gap: 0.5rem; align-items: flex-start; }
      .apps-grid { grid-template-columns: 1fr; }
    }
  </style>
</head>
<body>

<nav>
  <a class="logo" href="/">devstew<span class="logo-dot">.</span></a>
  <div class="nav-pill">
    <span class="live-dot"></span>
    6 apps live
  </div>
</nav>

<div class="hero">
  <div>
    <div class="hero-label">Product Portfolio</div>
    <h1>Apps built to<br><span>solve real problems.</span></h1>
    <p class="hero-desc">A growing collection of SaaS apps and tools — each one fully functioning, paywalled, and built to ship. No demos. No mockups.</p>
  </div>
  <div class="hero-stats">
    <div class="stat-block">
      <div class="stat-num">6</div>
      <div class="stat-label">Live apps</div>
    </div>
    <div class="stat-divider"></div>
    <div class="stat-block">
      <div class="stat-num">6</div>
      <div class="stat-label">Total built</div>
    </div>
  </div>
</div>

<div class="section">
  <div class="section-header">
    <span class="section-title">All Products</span>
    <span class="section-count">6 products</span>
  </div>

  <div class="apps-grid">

    <a class="app-card" href="https://partner-cashflow-clarity.lovable.app" target="_blank" rel="noopener" style="--card-color:#4f6ef7;">
      <div class="card-head">
        <div class="card-icon" style="background:rgba(79,110,247,0.1);">💰</div>
        <span class="type-tag tag-saas">SaaS</span>
      </div>
      <div class="card-name">Cashflow Clarity</div>
      <div class="card-category">Startup &amp; Founders</div>
      <div class="card-desc">Time and expense tracker built for early-stage founders. Know exactly where your money and hours are going.</div>
      <div class="card-footer">
        <span class="cta-link">View app <span>→</span></span>
        <span class="card-status"><span class="status-dot"></span> Live</span>
      </div>
    </a>

    <a class="app-card" href="https://dry-smart-log.lovable.app" target="_blank" rel="noopener" style="--card-color:#06b6d4;">
      <div class="card-head">
        <div class="card-icon" style="background:rgba(6,182,212,0.1);">💧</div>
        <span class="type-tag tag-saas">SaaS</span>
      </div>
      <div class="card-name">DrySmartLog</div>
      <div class="card-category">Water Restoration</div>
      <div class="card-desc">Digital drying logs for restoration crews. Track moisture readings, equipment placement, and drying progress on every job.</div>
      <div class="card-footer">
        <span class="cta-link">View app <span>→</span></span>
        <span class="card-status"><span class="status-dot"></span> Live</span>
      </div>
    </a>

    <a class="app-card" href="https://restoration-craft.lovable.app" target="_blank" rel="noopener" style="--card-color:#f97316;">
      <div class="card-head">
        <div class="card-icon" style="background:rgba(249,115,22,0.1);">🔧</div>
        <span class="type-tag tag-saas">SaaS</span>
      </div>
      <div class="card-name">RestorationCraft</div>
      <div class="card-category">Estimator's Aid</div>
      <div class="card-desc">Scope builder for restoration estimators. Build accurate job scopes faster and reduce missed line items on every bid.</div>
      <div class="card-footer">
        <span class="cta-link">View app <span>→</span></span>
        <span class="card-status"><span class="status-dot"></span> Live</span>
      </div>
    </a>

    <a class="app-card" href="https://future-flourish-fund.lovable.app" target="_blank" rel="noopener" style="--card-color:#22c55e;">
      <div class="card-head">
        <div class="card-icon" style="background:rgba(34,197,94,0.1);">📈</div>
        <span class="type-tag tag-saas">SaaS</span>
      </div>
      <div class="card-name">Future You</div>
      <div class="card-category">Personal Budget</div>
      <div class="card-desc">Budget planner that maps today's spending to your future self. See where your money goes and where it should.</div>
      <div class="card-footer">
        <span class="cta-link">View app <span>→</span></span>
        <span class="card-status"><span class="status-dot"></span> Live</span>
      </div>
    </a>

    <a class="app-card" href="https://fleet-chums.lovable.app" target="_blank" rel="noopener" style="--card-color:#eab308;">
      <div class="card-head">
        <div class="card-icon" style="background:rgba(234,179,8,0.1);">🚗</div>
        <span class="type-tag tag-tool">Tool</span>
      </div>
      <div class="card-name">Fleet Buddy</div>
      <div class="card-category">Small Business Fleet</div>
      <div class="card-desc">Simple fleet manager for small businesses. Track vehicles, maintenance, and drivers without the enterprise price tag.</div>
      <div class="card-footer">
        <span class="cta-link">View app <span>→</span></span>
        <span class="card-status"><span class="status-dot"></span> Live</span>
      </div>
    </a>

    <a class="app-card" href="https://rv-plan-pro.lovable.app" target="_blank" rel="noopener" style="--card-color:#a855f7;">
      <div class="card-head">
        <div class="card-icon" style="background:rgba(168,85,247,0.1);">🚐</div>
        <span class="type-tag tag-tool">Tool</span>
      </div>
      <div class="card-name">RV Plan Pro</div>
      <div class="card-category">Profit Planner</div>
      <div class="card-desc">Profit planning tool for RV rental operators. Model your revenue, costs, and margins to run a more profitable rental business.</div>
      <div class="card-footer">
        <span class="cta-link">View app <span>→</span></span>
        <span class="card-status"><span class="status-dot"></span> Live</span>
      </div>
    </a>

  </div>
</div>

<div class="about-strip">
  <div class="about-left">
    <h2>Built by one person,<br>shipped for real users.</h2>
    <p>Every app here solves a specific problem for a specific industry. No VC funding, no dev team — just a solo builder using modern no-code tools to move fast and ship products that work.</p>
  </div>
  <div class="stack-grid">
    <span class="stack-pill">Lovable</span>
    <span class="stack-pill">Supabase</span>
    <span class="stack-pill">Stripe</span>
    <span class="stack-pill">Vercel</span>
    <span class="stack-pill">Claude AI</span>
    <span class="stack-pill">No-code first</span>
  </div>
</div>

<footer>
  <div class="footer-logo">devstew<span>.</span></div>
  <div class="footer-copy">© 2025 devstew.io · All 6 apps fully functioning</div>
</footer>

</body>
</html>
