<!DOCTYPE html>
<html lang="en" data-theme="dark">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Ayoub Belkacem — GitHub Profile</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@300..700&family=Inter:wght@300..700&display=swap" rel="stylesheet">
  <style>
    /* ===================== DESIGN TOKENS ===================== */
    :root, [data-theme="light"] {
      --color-bg:               #f7f6f2;
      --color-surface:          #f9f8f5;
      --color-surface-2:        #fbfbf9;
      --color-surface-offset:   #f3f0ec;
      --color-divider:          #dcd9d5;
      --color-border:           #d4d1ca;
      --color-text:             #28251d;
      --color-text-muted:       #7a7974;
      --color-text-faint:       #bab9b4;
      --color-primary:          #01696f;
      --color-primary-hover:    #0c4e54;
      --color-primary-highlight:#cedcd8;
      --color-success:          #437a22;
      --color-gold:             #d19900;
      --color-purple:           #7a39bb;
      --color-blue:             #006494;
      --shadow-sm: 0 1px 2px oklch(0.2 0.01 80 / 0.06);
      --shadow-md: 0 4px 12px oklch(0.2 0.01 80 / 0.08);
      --shadow-lg: 0 12px 32px oklch(0.2 0.01 80 / 0.12);
      --radius-sm: 0.375rem;
      --radius-md: 0.5rem;
      --radius-lg: 0.75rem;
      --radius-xl: 1rem;
      --radius-full: 9999px;
      --transition: 180ms cubic-bezier(0.16, 1, 0.3, 1);
      --space-1: 0.25rem; --space-2: 0.5rem; --space-3: 0.75rem;
      --space-4: 1rem;    --space-5: 1.25rem; --space-6: 1.5rem;
      --space-8: 2rem;    --space-10: 2.5rem; --space-12: 3rem;
      --space-16: 4rem;
      --text-xs:   clamp(0.75rem,  0.7rem  + 0.25vw, 0.875rem);
      --text-sm:   clamp(0.875rem, 0.8rem  + 0.35vw, 1rem);
      --text-base: clamp(1rem,     0.95rem + 0.25vw, 1.125rem);
      --text-lg:   clamp(1.125rem, 1rem    + 0.75vw, 1.5rem);
      --text-xl:   clamp(1.5rem,   1.2rem  + 1.25vw, 2.25rem);
      --text-2xl:  clamp(2rem,     1.2rem  + 2.5vw,  3.5rem);
      --font-display: 'Fira Code', 'Courier New', monospace;
      --font-body: 'Inter', system-ui, sans-serif;
    }

    [data-theme="dark"] {
      --color-bg:               #0d1117;
      --color-surface:          #161b22;
      --color-surface-2:        #1c2128;
      --color-surface-offset:   #21262d;
      --color-divider:          #30363d;
      --color-border:           #363c43;
      --color-text:             #e6edf3;
      --color-text-muted:       #8b949e;
      --color-text-faint:       #484f58;
      --color-primary:          #58a6ff;
      --color-primary-hover:    #79b8ff;
      --color-primary-highlight:#1f3a5c;
      --color-success:          #3fb950;
      --color-gold:             #d29922;
      --color-purple:           #bc8cff;
      --color-blue:             #58a6ff;
      --shadow-sm: 0 1px 2px oklch(0 0 0 / 0.3);
      --shadow-md: 0 4px 12px oklch(0 0 0 / 0.4);
      --shadow-lg: 0 12px 32px oklch(0 0 0 / 0.5);
    }

    /* ===================== BASE ===================== */
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    html { -webkit-font-smoothing: antialiased; scroll-behavior: smooth; }
    body {
      min-height: 100dvh;
      font-family: var(--font-body);
      font-size: var(--text-base);
      background: var(--color-bg);
      color: var(--color-text);
      transition: background var(--transition), color var(--transition);
      padding: var(--space-8) var(--space-4);
    }
    img { display: block; max-width: 100%; height: auto; }
    a {
      color: var(--color-primary);
      text-decoration: none;
      transition: color var(--transition);
    }
    a:hover { color: var(--color-primary-hover); text-decoration: underline; }
    button { cursor: pointer; background: none; border: none; font: inherit; color: inherit; }

    /* ===================== LAYOUT ===================== */
    .container {
      max-width: 900px;
      margin-inline: auto;
    }

    /* ===================== THEME TOGGLE ===================== */
    .theme-toggle {
      position: fixed;
      top: var(--space-4);
      right: var(--space-4);
      width: 40px; height: 40px;
      border-radius: var(--radius-full);
      background: var(--color-surface);
      border: 1px solid var(--color-border);
      display: flex; align-items: center; justify-content: center;
      color: var(--color-text-muted);
      box-shadow: var(--shadow-md);
      transition: background var(--transition), color var(--transition), box-shadow var(--transition);
      z-index: 100;
    }
    .theme-toggle:hover {
      color: var(--color-text);
      box-shadow: var(--shadow-lg);
    }

    /* ===================== HEADER / HERO ===================== */
    .profile-header {
      display: flex;
      flex-direction: column;
      align-items: center;
      text-align: center;
      gap: var(--space-5);
      padding: var(--space-10) 0 var(--space-8);
      position: relative;
    }

    .avatar-ring {
      width: 100px; height: 100px;
      border-radius: var(--radius-full);
      background: linear-gradient(135deg, var(--color-primary), var(--color-purple), var(--color-gold));
      padding: 3px;
      box-shadow: var(--shadow-lg);
      animation: float 4s ease-in-out infinite;
    }
    @keyframes float {
      0%, 100% { transform: translateY(0); }
      50%       { transform: translateY(-6px); }
    }
    .avatar-inner {
      width: 100%; height: 100%;
      border-radius: var(--radius-full);
      background: var(--color-bg);
      display: flex; align-items: center; justify-content: center;
      font-size: 2.8rem;
    }

    .profile-name {
      font-family: var(--font-display);
      font-size: var(--text-2xl);
      font-weight: 700;
      letter-spacing: -0.02em;
      line-height: 1.1;
    }
    .profile-name .cursor {
      display: inline-block;
      width: 3px;
      height: 1em;
      background: var(--color-primary);
      margin-left: 2px;
      vertical-align: text-bottom;
      animation: blink 1s step-end infinite;
    }
    @keyframes blink { 0%, 100% { opacity: 1; } 50% { opacity: 0; } }

    .profile-title {
      font-size: var(--text-base);
      color: var(--color-text-muted);
      font-family: var(--font-display);
      font-weight: 400;
    }

    .profile-badges {
      display: flex;
      flex-wrap: wrap;
      gap: var(--space-2);
      justify-content: center;
    }
    .badge {
      display: inline-flex;
      align-items: center;
      gap: var(--space-1);
      padding: var(--space-1) var(--space-3);
      border-radius: var(--radius-full);
      font-size: var(--text-xs);
      font-weight: 500;
      border: 1px solid transparent;
      transition: all var(--transition);
    }
    .badge-primary {
      background: var(--color-primary-highlight);
      color: var(--color-primary);
      border-color: color-mix(in oklab, var(--color-primary) 20%, transparent);
    }
    .badge-success {
      background: color-mix(in oklab, var(--color-success) 15%, transparent);
      color: var(--color-success);
      border-color: color-mix(in oklab, var(--color-success) 25%, transparent);
    }
    .badge-purple {
      background: color-mix(in oklab, var(--color-purple) 12%, transparent);
      color: var(--color-purple);
      border-color: color-mix(in oklab, var(--color-purple) 20%, transparent);
    }
    .badge-gold {
      background: color-mix(in oklab, var(--color-gold) 12%, transparent);
      color: var(--color-gold);
      border-color: color-mix(in oklab, var(--color-gold) 20%, transparent);
    }

    /* ===================== PROFILE VIEWER BADGE ===================== */
    .views-badge {
      display: inline-flex;
      align-items: center;
      gap: var(--space-2);
      padding: var(--space-1) var(--space-3);
      border-radius: var(--radius-full);
      background: var(--color-surface-2);
      border: 1px solid var(--color-border);
      font-size: var(--text-xs);
      color: var(--color-text-muted);
    }
    .views-dot {
      width: 8px; height: 8px;
      border-radius: var(--radius-full);
      background: var(--color-success);
      box-shadow: 0 0 6px var(--color-success);
      animation: pulse 2s ease-in-out infinite;
    }
    @keyframes pulse {
      0%, 100% { box-shadow: 0 0 4px var(--color-success); }
      50%       { box-shadow: 0 0 12px var(--color-success); }
    }

    /* ===================== SOCIAL LINKS ===================== */
    .socials {
      display: flex;
      gap: var(--space-3);
      justify-content: center;
      flex-wrap: wrap;
    }
    .social-link {
      display: flex;
      align-items: center;
      gap: var(--space-2);
      padding: var(--space-2) var(--space-4);
      border-radius: var(--radius-lg);
      background: var(--color-surface);
      border: 1px solid var(--color-border);
      font-size: var(--text-sm);
      color: var(--color-text-muted);
      text-decoration: none;
      font-weight: 500;
      box-shadow: var(--shadow-sm);
      transition: all var(--transition);
    }
    .social-link:hover {
      color: var(--color-text);
      background: var(--color-surface-2);
      box-shadow: var(--shadow-md);
      border-color: var(--color-primary);
      text-decoration: none;
      transform: translateY(-2px);
    }
    .social-link svg { flex-shrink: 0; }

    /* ===================== INFO CARDS ROW ===================== */
    .info-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
      gap: var(--space-4);
      margin-bottom: var(--space-6);
    }
    .info-card {
      background: var(--color-surface);
      border: 1px solid var(--color-border);
      border-radius: var(--radius-xl);
      padding: var(--space-5);
      box-shadow: var(--shadow-sm);
      transition: box-shadow var(--transition), transform var(--transition);
    }
    .info-card:hover {
      box-shadow: var(--shadow-md);
      transform: translateY(-2px);
    }
    .info-card-icon {
      font-size: 1.5rem;
      margin-bottom: var(--space-2);
    }
    .info-card-label {
      font-size: var(--text-xs);
      color: var(--color-text-faint);
      text-transform: uppercase;
      letter-spacing: 0.08em;
      font-weight: 600;
      margin-bottom: var(--space-1);
    }
    .info-card-value {
      font-size: var(--text-base);
      font-weight: 500;
      color: var(--color-text);
    }
    .info-card-value a { color: var(--color-primary); }

    /* ===================== SECTION TITLE ===================== */
    .section-title {
      font-family: var(--font-display);
      font-size: var(--text-sm);
      font-weight: 600;
      color: var(--color-text-muted);
      text-transform: uppercase;
      letter-spacing: 0.1em;
      margin-bottom: var(--space-4);
      display: flex;
      align-items: center;
      gap: var(--space-2);
    }
    .section-title::after {
      content: '';
      flex: 1;
      height: 1px;
      background: var(--color-divider);
    }

    /* ===================== TOOLS GRID ===================== */
    .tools-grid {
      display: flex;
      flex-wrap: wrap;
      gap: var(--space-3);
      margin-bottom: var(--space-8);
    }
    .tool-chip {
      display: flex;
      align-items: center;
      gap: var(--space-2);
      padding: var(--space-2) var(--space-3);
      border-radius: var(--radius-lg);
      background: var(--color-surface);
      border: 1px solid var(--color-border);
      font-size: var(--text-sm);
      color: var(--color-text-muted);
      font-weight: 500;
      box-shadow: var(--shadow-sm);
      text-decoration: none;
      transition: all var(--transition);
    }
    .tool-chip:hover {
      background: var(--color-surface-2);
      color: var(--color-text);
      border-color: var(--color-primary);
      box-shadow: var(--shadow-md);
      transform: translateY(-1px);
      text-decoration: none;
    }
    .tool-chip img {
      width: 20px; height: 20px;
      display: inline-block;
      object-fit: contain;
    }

    /* ===================== GITHUB STATS GRID ===================== */
    .stats-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: var(--space-4);
      margin-bottom: var(--space-8);
    }
    .stat-card {
      background: var(--color-surface);
      border: 1px solid var(--color-border);
      border-radius: var(--radius-xl);
      overflow: hidden;
      box-shadow: var(--shadow-sm);
      transition: box-shadow var(--transition), transform var(--transition);
    }
    .stat-card:hover {
      box-shadow: var(--shadow-md);
      transform: translateY(-2px);
    }
    .stat-card img {
      width: 100%;
      height: auto;
      display: block;
    }
    .stat-card-wide {
      grid-column: 1 / -1;
    }

    /* ===================== FOOTER ===================== */
    .footer {
      text-align: center;
      padding: var(--space-8) 0 var(--space-4);
      font-size: var(--text-xs);
      color: var(--color-text-faint);
      border-top: 1px solid var(--color-divider);
    }
    .footer a { color: var(--color-text-muted); }

    /* ===================== SCROLL REVEAL ===================== */
    .fade-in {
      opacity: 1;
    }
    @supports (animation-timeline: scroll()) {
      .fade-in {
        opacity: 0;
        animation: reveal-fade linear both;
        animation-timeline: view();
        animation-range: entry 0% entry 80%;
      }
    }
    @keyframes reveal-fade { to { opacity: 1; } }

    /* ===================== MOBILE ===================== */
    @media (max-width: 600px) {
      body { padding: var(--space-4) var(--space-3); }
      .stats-grid { grid-template-columns: 1fr; }
      .info-grid { grid-template-columns: 1fr; }
    }
    @media (prefers-reduced-motion: reduce) {
      *, *::before, *::after {
        animation-duration: 0.01ms !important;
        transition-duration: 0.01ms !important;
      }
    }
  </style>
</head>
<body>

  <!-- Theme Toggle -->
  <button class="theme-toggle" data-theme-toggle aria-label="Toggle theme">
    <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
      <path d="M21 12.79A9 9 0 1 1 11.21 3 7 7 0 0 0 21 12.79z"/>
    </svg>
  </button>

  <div class="container">

    <!-- ===== PROFILE HEADER ===== -->
    <header class="profile-header">
      <div class="views-badge">
        <span class="views-dot"></span>
        <span>Live Profile</span>
        <img src="https://komarev.com/ghpvc/?username=ay-bkm&color=brightgreen&style=flat&label=visitors" alt="Profile views" style="height:20px;width:auto;display:inline-block;" loading="lazy" />
      </div>

      <div class="avatar-ring">
        <div class="avatar-inner">🧙‍♂️</div>
      </div>

      <div>
        <h1 class="profile-name">Ayoub Belkacem<span class="cursor"></span></h1>
        <p class="profile-title">// Software Sorcerer &amp; Digital Crafter 🪄</p>
      </div>

      <div class="profile-badges">
        <span class="badge badge-primary">🐍 Pythonic Potions</span>
        <span class="badge badge-success">🌱 Always Learning</span>
        <span class="badge badge-purple">🔮 Coding Conjurations</span>
        <span class="badge badge-gold">⚡ Digital Wonders</span>
      </div>

      <div class="socials">
        <a href="https://twitter.com/ayblkcm" class="social-link" target="_blank" rel="noopener noreferrer">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-4.714-6.231-5.401 6.231H2.744l7.737-8.835L1.254 2.25H8.08l4.253 5.622zm-1.161 17.52h1.833L7.084 4.126H5.117z"/></svg>
          Twitter
        </a>
        <a href="https://instagram.com/aybkm" class="social-link" target="_blank" rel="noopener noreferrer">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="2" width="20" height="20" rx="5" ry="5"/><path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"/><line x1="17.5" y1="6.5" x2="17.51" y2="6.5"/></svg>
          Instagram
        </a>
        <a href="https://medium.com/@aybkm" class="social-link" target="_blank" rel="noopener noreferrer">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M13.54 12a6.8 6.8 0 01-6.77 6.82A6.8 6.8 0 010 12a6.8 6.8 0 016.77-6.82A6.8 6.8 0 0113.54 12zm7.42 0c0 3.54-1.51 6.42-3.38 6.42-1.87 0-3.39-2.88-3.39-6.42s1.52-6.42 3.39-6.42 3.38 2.88 3.38 6.42M24 12c0 3.17-.53 5.75-1.19 5.75-.66 0-1.19-2.58-1.19-5.75s.53-5.75 1.19-5.75C23.47 6.25 24 8.83 24 12z"/></svg>
          Medium
        </a>
        <a href="mailto:ay.belkacem@gmail.com" class="social-link">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
          Email
        </a>
      </div>
    </header>

    <!-- ===== INFO CARDS ===== -->
    <div class="info-grid fade-in">
      <div class="info-card">
        <div class="info-card-icon">📝</div>
        <div class="info-card-label">Writing at</div>
        <div class="info-card-value"><a href="https://aybkm.medium.com" target="_blank" rel="noopener noreferrer">aybkm.medium.com</a></div>
      </div>
      <div class="info-card">
        <div class="info-card-icon">📍</div>
        <div class="info-card-label">Location</div>
        <div class="info-card-value">Morocco 🇲🇦</div>
      </div>
      <div class="info-card">
        <div class="info-card-icon">⚗️</div>
        <div class="info-card-label">Currently Brewing</div>
        <div class="info-card-value">Python & Full-Stack Magic</div>
      </div>
    </div>

    <!-- ===== TOOLS SECTION ===== -->
    <section class="fade-in">
      <p class="section-title">🧪 Languages &amp; Tools in My Cauldron</p>
      <div class="tools-grid">
        <a href="https://www.python.org" class="tool-chip" target="_blank" rel="noopener noreferrer">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/python/python-original.svg" alt="Python" loading="lazy" />
          Python
        </a>
        <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript" class="tool-chip" target="_blank" rel="noopener noreferrer">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/javascript/javascript-original.svg" alt="JavaScript" loading="lazy" />
          JavaScript
        </a>
        <a href="https://react.dev/" class="tool-chip" target="_blank" rel="noopener noreferrer">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/react/react-original-wordmark.svg" alt="React" loading="lazy" />
          React
        </a>
        <a href="https://nodejs.org" class="tool-chip" target="_blank" rel="noopener noreferrer">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/nodejs/nodejs-original-wordmark.svg" alt="Node.js" loading="lazy" />
          Node.js
        </a>
        <a href="https://expressjs.com" class="tool-chip" target="_blank" rel="noopener noreferrer">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/express/express-original.svg" alt="Express.js" loading="lazy" />
          Express
        </a>
        <a href="https://redux.js.org" class="tool-chip" target="_blank" rel="noopener noreferrer">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/redux/redux-original.svg" alt="Redux" loading="lazy" />
          Redux
        </a>
        <a href="https://www.w3.org/html/" class="tool-chip" target="_blank" rel="noopener noreferrer">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/html5/html5-original-wordmark.svg" alt="HTML5" loading="lazy" />
          HTML5
        </a>
        <a href="https://www.w3schools.com/css/" class="tool-chip" target="_blank" rel="noopener noreferrer">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/css3/css3-original-wordmark.svg" alt="CSS3" loading="lazy" />
          CSS3
        </a>
        <a href="https://getbootstrap.com" class="tool-chip" target="_blank" rel="noopener noreferrer">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/bootstrap/bootstrap-plain-wordmark.svg" alt="Bootstrap" loading="lazy" />
          Bootstrap
        </a>
        <a href="https://www.mysql.com/" class="tool-chip" target="_blank" rel="noopener noreferrer">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/mysql/mysql-original-wordmark.svg" alt="MySQL" loading="lazy" />
          MySQL
        </a>
        <a href="https://www.php.net" class="tool-chip" target="_blank" rel="noopener noreferrer">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/php/php-original.svg" alt="PHP" loading="lazy" />
          PHP
        </a>
        <a href="https://www.java.com" class="tool-chip" target="_blank" rel="noopener noreferrer">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/java/java-original.svg" alt="Java" loading="lazy" />
          Java
        </a>
        <a href="https://www.cprogramming.com/" class="tool-chip" target="_blank" rel="noopener noreferrer">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/c/c-original.svg" alt="C" loading="lazy" />
          C
        </a>
        <a href="https://git-scm.com/" class="tool-chip" target="_blank" rel="noopener noreferrer">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/git/git-original.svg" alt="Git" loading="lazy" />
          Git
        </a>
        <a href="https://www.linux.org/" class="tool-chip" target="_blank" rel="noopener noreferrer">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/linux/linux-original.svg" alt="Linux" loading="lazy" />
          Linux
        </a>
        <a href="https://zapier.com" class="tool-chip" target="_blank" rel="noopener noreferrer">
          <img src="https://cdn.simpleicons.org/zapier/FF4A00" alt="Zapier" loading="lazy" />
          Zapier
        </a>
      </div>
    </section>

    <!-- ===== GITHUB STATS ===== -->
    <section class="fade-in">
      <p class="section-title">📊 GitHub Stats &amp; Activity</p>
      <div class="stats-grid">
        <div class="stat-card">
          <img
            src="https://github-readme-stats.vercel.app/api?username=ay-bkm&show_icons=true&theme=github_dark&hide_border=true&bg_color=0d1117&title_color=58a6ff&text_color=8b949e&icon_color=3fb950"
            alt="Ayoub's GitHub Stats"
            loading="lazy"
            width="495" height="195"
          />
        </div>
        <div class="stat-card">
          <img
            src="https://github-readme-stats.vercel.app/api/top-langs/?username=ay-bkm&layout=compact&theme=github_dark&hide_border=true&bg_color=0d1117&title_color=58a6ff&text_color=8b949e"
            alt="Top Languages"
            loading="lazy"
            width="495" height="195"
          />
        </div>
        <div class="stat-card stat-card-wide">
          <img
            src="https://streak-stats.demolab.com/?user=ay-bkm&theme=github-dark-blue&hide_border=true&background=0d1117&ring=58a6ff&fire=d29922&currStreakLabel=58a6ff"
            alt="GitHub Streak"
            loading="lazy"
            width="900" height="195"
          />
        </div>
      </div>
    </section>

    <!-- ===== FOOTER ===== -->
    <footer class="footer">
      <p>Crafted with ✨ by <a href="https://github.com/ay-bkm" target="_blank" rel="noopener noreferrer">Ayoub Belkacem</a> · Casablanca, Morocco</p>
    </footer>

  </div>

  <script>
    // Theme toggle
    (function() {
      const toggle = document.querySelector('[data-theme-toggle]');
      const root = document.documentElement;
      let theme = 'dark';
      root.setAttribute('data-theme', theme);

      function updateIcon() {
        toggle.innerHTML = theme === 'dark'
          ? '<svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="5"/><path d="M12 1v2M12 21v2M4.22 4.22l1.42 1.42M18.36 18.36l1.42 1.42M1 12h2M21 12h2M4.22 19.78l1.42-1.42M18.36 5.64l1.42-1.42"/></svg>'
          : '<svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 12.79A9 9 0 1 1 11.21 3 7 7 0 0 0 21 12.79z"/></svg>';
        toggle.setAttribute('aria-label', 'Switch to ' + (theme === 'dark' ? 'light' : 'dark') + ' mode');
      }

      toggle.addEventListener('click', function() {
        theme = theme === 'dark' ? 'light' : 'dark';
        root.setAttribute('data-theme', theme);
        updateIcon();

        // Update GitHub stats image URLs to match the theme
        updateStatsTheme(theme);
      });

      function updateStatsTheme(t) {
        const statsImg = document.querySelector('.stats-grid .stat-card:nth-child(1) img');
        const langsImg = document.querySelector('.stats-grid .stat-card:nth-child(2) img');
        const streakImg = document.querySelector('.stat-card-wide img');
        if (t === 'light') {
          statsImg.src = 'https://github-readme-stats.vercel.app/api?username=ay-bkm&show_icons=true&theme=default&hide_border=true&bg_color=f9f8f5&title_color=01696f&text_color=7a7974&icon_color=437a22';
          langsImg.src = 'https://github-readme-stats.vercel.app/api/top-langs/?username=ay-bkm&layout=compact&theme=default&hide_border=true&bg_color=f9f8f5&title_color=01696f&text_color=7a7974';
          streakImg.src = 'https://streak-stats.demolab.com/?user=ay-bkm&theme=default&hide_border=true&background=f9f8f5&ring=01696f&fire=d19900&currStreakLabel=01696f';
        } else {
          statsImg.src = 'https://github-readme-stats.vercel.app/api?username=ay-bkm&show_icons=true&theme=github_dark&hide_border=true&bg_color=0d1117&title_color=58a6ff&text_color=8b949e&icon_color=3fb950';
          langsImg.src = 'https://github-readme-stats.vercel.app/api/top-langs/?username=ay-bkm&layout=compact&theme=github_dark&hide_border=true&bg_color=0d1117&title_color=58a6ff&text_color=8b949e';
          streakImg.src = 'https://streak-stats.demolab.com/?user=ay-bkm&theme=github-dark-blue&hide_border=true&background=0d1117&ring=58a6ff&fire=d29922&currStreakLabel=58a6ff';
        }
      }

      updateIcon();
    })();
  </script>
</body>
</html>
