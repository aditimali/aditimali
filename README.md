

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Aditi Mali – Data & Business Analyst</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700;900&family=DM+Sans:wght@300;400;500;600&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet"/>
<style>
  :root {
    --navy: #0a1628;
    --deep: #0d1f3c;
    --blue: #1a3a6b;
    --accent: #4f8ef7;
    --gold: #f0b429;
    --teal: #00d4aa;
    --text: #e8edf5;
    --muted: #8899bb;
    --card: rgba(15, 30, 60, 0.7);
    --border: rgba(79, 142, 247, 0.2);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--navy);
    color: var(--text);
    font-family: 'DM Sans', sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* === ANIMATED BACKGROUND === */
  .bg {
    position: fixed;
    inset: 0;
    z-index: 0;
    overflow: hidden;
  }

  .bg::before {
    content: '';
    position: absolute;
    inset: 0;
    background:
      radial-gradient(ellipse 80% 60% at 10% 20%, rgba(26,58,107,0.6) 0%, transparent 60%),
      radial-gradient(ellipse 60% 50% at 90% 80%, rgba(0,212,170,0.12) 0%, transparent 55%),
      radial-gradient(ellipse 50% 40% at 60% 10%, rgba(79,142,247,0.1) 0%, transparent 50%),
      linear-gradient(160deg, #0a1628 0%, #0d1f3c 50%, #0a1628 100%);
  }

  /* Floating grid lines */
  .grid-lines {
    position: absolute;
    inset: 0;
    background-image:
      linear-gradient(rgba(79,142,247,0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(79,142,247,0.04) 1px, transparent 1px);
    background-size: 60px 60px;
    animation: gridMove 20s linear infinite;
  }

  @keyframes gridMove {
    0% { transform: translateY(0); }
    100% { transform: translateY(60px); }
  }

  /* Floating orbs */
  .orb {
    position: absolute;
    border-radius: 50%;
    filter: blur(80px);
    animation: float 12s ease-in-out infinite;
    opacity: 0.4;
  }
  .orb1 { width: 500px; height: 500px; background: rgba(26,58,107,0.7); top: -100px; left: -100px; animation-duration: 15s; }
  .orb2 { width: 350px; height: 350px; background: rgba(0,212,170,0.15); bottom: 10%; right: -50px; animation-duration: 18s; animation-delay: -6s; }
  .orb3 { width: 250px; height: 250px; background: rgba(240,180,41,0.08); top: 40%; left: 30%; animation-duration: 12s; animation-delay: -3s; }

  @keyframes float {
    0%, 100% { transform: translate(0, 0) scale(1); }
    33% { transform: translate(30px, -40px) scale(1.05); }
    66% { transform: translate(-20px, 20px) scale(0.97); }
  }

  /* Data particles */
  .particles { position: absolute; inset: 0; }
  .particle {
    position: absolute;
    width: 2px; height: 2px;
    background: var(--accent);
    border-radius: 50%;
    animation: rise linear infinite;
    opacity: 0;
  }
  @keyframes rise {
    0% { transform: translateY(100vh); opacity: 0; }
    10% { opacity: 0.6; }
    90% { opacity: 0.3; }
    100% { transform: translateY(-10vh); opacity: 0; }
  }

  /* === LAYOUT === */
  .container {
    position: relative;
    z-index: 1;
    max-width: 960px;
    margin: 0 auto;
    padding: 60px 24px;
  }

  /* === HERO === */
  .hero {
    text-align: center;
    padding: 60px 0 50px;
    animation: fadeUp 0.9s ease both;
  }

  .hero-badge {
    display: inline-block;
    background: rgba(79,142,247,0.12);
    border: 1px solid rgba(79,142,247,0.3);
    color: var(--accent);
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    letter-spacing: 2px;
    padding: 6px 18px;
    border-radius: 100px;
    margin-bottom: 28px;
    text-transform: uppercase;
  }

  .hero h1 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(42px, 7vw, 72px);
    font-weight: 900;
    line-height: 1.05;
    background: linear-gradient(135deg, #e8edf5 30%, #4f8ef7 65%, #00d4aa 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 16px;
  }

  .hero-sub {
    font-size: 18px;
    color: var(--muted);
    font-weight: 300;
    letter-spacing: 0.5px;
    margin-bottom: 32px;
  }

  .hero-sub span {
    color: var(--gold);
    font-weight: 500;
  }

  .typing-bar {
    display: inline-flex;
    align-items: center;
    gap: 10px;
    background: rgba(79,142,247,0.08);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 10px 20px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    color: var(--teal);
    margin-bottom: 40px;
  }
  .typing-bar .dot { width: 8px; height: 8px; border-radius: 50%; background: var(--teal); animation: blink 1.2s ease infinite; }
  @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0.2} }

  .hero-links {
    display: flex;
    gap: 14px;
    justify-content: center;
    flex-wrap: wrap;
  }

  .btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 11px 24px;
    border-radius: 8px;
    font-size: 14px;
    font-weight: 500;
    text-decoration: none;
    transition: all 0.25s ease;
    cursor: pointer;
    border: none;
  }
  .btn-primary {
    background: var(--accent);
    color: #fff;
    box-shadow: 0 4px 20px rgba(79,142,247,0.35);
  }
  .btn-primary:hover { transform: translateY(-2px); box-shadow: 0 8px 30px rgba(79,142,247,0.45); }
  .btn-outline {
    background: transparent;
    color: var(--text);
    border: 1px solid var(--border);
  }
  .btn-outline:hover { border-color: var(--accent); color: var(--accent); transform: translateY(-2px); }

  /* === SECTION === */
  section {
    margin-bottom: 60px;
    animation: fadeUp 0.8s ease both;
  }

  .section-label {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 28px;
  }
  .section-label .line {
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, var(--border), transparent);
  }
  .section-label h2 {
    font-family: 'Playfair Display', serif;
    font-size: 22px;
    font-weight: 700;
    color: var(--text);
    white-space: nowrap;
  }
  .section-label .icon {
    font-size: 20px;
  }

  /* === CURRENTLY CARD === */
  .currently-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 14px;
  }

  .currently-item {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 18px 20px;
    display: flex;
    gap: 14px;
    align-items: flex-start;
    backdrop-filter: blur(10px);
    transition: all 0.25s ease;
  }
  .currently-item:hover {
    border-color: rgba(79,142,247,0.5);
    transform: translateY(-3px);
    box-shadow: 0 8px 30px rgba(0,0,0,0.3);
  }
  .currently-item .emoji { font-size: 22px; flex-shrink: 0; margin-top: 2px; }
  .currently-item .content label {
    display: block;
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 1.5px;
    color: var(--accent);
    font-family: 'JetBrains Mono', monospace;
    margin-bottom: 5px;
  }
  .currently-item .content p { font-size: 14px; color: var(--text); line-height: 1.5; }

  /* === COMPETENCIES TABLE === */
  .comp-table {
    width: 100%;
    border-collapse: separate;
    border-spacing: 0;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 14px;
    overflow: hidden;
    backdrop-filter: blur(10px);
  }
  .comp-table thead tr {
    background: rgba(79,142,247,0.12);
  }
  .comp-table th {
    padding: 14px 20px;
    text-align: left;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    color: var(--accent);
    border-bottom: 1px solid var(--border);
  }
  .comp-table td {
    padding: 12px 20px;
    font-size: 14px;
    color: var(--muted);
    border-bottom: 1px solid rgba(79,142,247,0.07);
  }
  .comp-table tr:last-child td { border-bottom: none; }
  .comp-table tr:hover td { background: rgba(79,142,247,0.05); color: var(--text); }
  .comp-table td:last-child { color: var(--teal); font-family: 'JetBrains Mono', monospace; font-size: 13px; }

  /* === SKILL BADGES === */
  .badges-section { display: flex; flex-direction: column; gap: 20px; }
  .badge-group label {
    display: block;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 12px;
  }
  .badge-row { display: flex; flex-wrap: wrap; gap: 10px; }
  .badge {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 8px 16px;
    border-radius: 8px;
    font-size: 13px;
    font-weight: 500;
    border: 1px solid transparent;
    transition: all 0.2s ease;
    cursor: default;
  }
  .badge:hover { transform: translateY(-2px); filter: brightness(1.15); }
  .badge-powerbi  { background: rgba(242,199,17,0.1);  border-color: rgba(242,199,17,0.3);  color: #f2c711; }
  .badge-tableau  { background: rgba(233,118,39,0.1);  border-color: rgba(233,118,39,0.3);  color: #e97627; }
  .badge-excel    { background: rgba(33,115,70,0.15);  border-color: rgba(33,115,70,0.3);   color: #4CAF7D; }
  .badge-mysql    { background: rgba(68,121,161,0.15); border-color: rgba(68,121,161,0.3);  color: #5B9BD5; }
  .badge-python   { background: rgba(55,118,171,0.15); border-color: rgba(55,118,171,0.3);  color: #4f9eff; }
  .badge-java     { background: rgba(237,139,0,0.1);   border-color: rgba(237,139,0,0.3);   color: #ED8B00; }
  .badge-firebase { background: rgba(255,202,40,0.1);  border-color: rgba(255,202,40,0.3);  color: #FFCA28; }
  .badge-git      { background: rgba(240,80,50,0.1);   border-color: rgba(240,80,50,0.3);   color: #F05032; }
  .badge-vapt     { background: rgba(200,50,50,0.1);   border-color: rgba(200,50,50,0.3);   color: #FF6B6B; }
  .badge-android  { background: rgba(61,220,132,0.1);  border-color: rgba(61,220,132,0.3);  color: #3DDC84; }

  /* === PROJECTS === */
  .projects-grid { display: flex; flex-direction: column; gap: 18px; }
  .project-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 26px 28px;
    backdrop-filter: blur(10px);
    transition: all 0.3s ease;
    position: relative;
    overflow: hidden;
  }
  .project-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0;
    width: 3px; height: 100%;
    border-radius: 3px 0 0 3px;
  }
  .project-card.bi::before   { background: linear-gradient(180deg, var(--accent), var(--teal)); }
  .project-card.sec::before  { background: linear-gradient(180deg, #FF6B6B, #ff9a3c); }
  .project-card.app::before  { background: linear-gradient(180deg, #3DDC84, #00d4aa); }
  .project-card:hover { border-color: rgba(79,142,247,0.4); transform: translateX(6px); box-shadow: 0 10px 40px rgba(0,0,0,0.35); }

  .project-header { display: flex; align-items: flex-start; justify-content: space-between; margin-bottom: 12px; gap: 12px; }
  .project-title  { font-family: 'Playfair Display', serif; font-size: 18px; font-weight: 700; color: var(--text); }
  .project-tools  { display: flex; gap: 6px; flex-wrap: wrap; }
  .tool-tag {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    padding: 3px 10px;
    border-radius: 100px;
    background: rgba(79,142,247,0.12);
    border: 1px solid var(--border);
    color: var(--accent);
    white-space: nowrap;
  }
  .project-desc { font-size: 14px; color: var(--muted); line-height: 1.7; margin-bottom: 14px; }
  .project-skills { display: flex; flex-wrap: wrap; gap: 8px; }
  .skill-chip {
    font-size: 11px;
    padding: 4px 12px;
    border-radius: 100px;
    background: rgba(0,212,170,0.08);
    border: 1px solid rgba(0,212,170,0.2);
    color: var(--teal);
  }

  /* === CERTIFICATIONS === */
  .cert-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }
  .cert-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 24px;
    backdrop-filter: blur(10px);
    transition: all 0.25s ease;
  }
  .cert-card:hover { border-color: rgba(240,180,41,0.4); transform: translateY(-3px); box-shadow: 0 10px 30px rgba(0,0,0,0.3); }
  .cert-icon { font-size: 32px; margin-bottom: 12px; }
  .cert-name { font-size: 15px; font-weight: 600; color: var(--text); margin-bottom: 6px; }
  .cert-issuer { font-family: 'JetBrains Mono', monospace; font-size: 11px; color: var(--gold); letter-spacing: 1px; margin-bottom: 8px; }
  .cert-desc { font-size: 13px; color: var(--muted); line-height: 1.5; }

  /* === CONNECT === */
  .connect-grid { display: flex; gap: 14px; flex-wrap: wrap; }
  .connect-btn {
    display: inline-flex;
    align-items: center;
    gap: 10px;
    padding: 14px 24px;
    border-radius: 10px;
    font-size: 14px;
    font-weight: 500;
    text-decoration: none;
    border: 1px solid var(--border);
    background: var(--card);
    color: var(--text);
    backdrop-filter: blur(10px);
    transition: all 0.25s ease;
  }
  .connect-btn:hover { transform: translateY(-3px); box-shadow: 0 8px 25px rgba(0,0,0,0.35); }
  .connect-btn.linkedin:hover { border-color: #0077b5; color: #0077b5; }
  .connect-btn.gmail:hover    { border-color: #ea4335; color: #ea4335; }
  .connect-btn.github:hover   { border-color: #fff;    color: #fff; }

  /* === FOOTER === */
  .footer {
    text-align: center;
    padding: 40px 0 20px;
    border-top: 1px solid var(--border);
    margin-top: 20px;
  }
  .footer p { font-size: 13px; color: var(--muted); margin-bottom: 8px; }
  .footer .quote {
    font-family: 'Playfair Display', serif;
    font-size: 16px;
    font-style: italic;
    color: var(--accent);
  }
  .open-badge {
    display: inline-block;
    margin-top: 16px;
    background: rgba(0,212,170,0.1);
    border: 1px solid rgba(0,212,170,0.3);
    color: var(--teal);
    font-size: 12px;
    font-family: 'JetBrains Mono', monospace;
    padding: 6px 18px;
    border-radius: 100px;
    letter-spacing: 1px;
    animation: pulse 2.5s ease infinite;
  }
  @keyframes pulse { 0%,100%{box-shadow:0 0 0 0 rgba(0,212,170,0.3)} 50%{box-shadow:0 0 0 8px rgba(0,212,170,0)} }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(28px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  section:nth-child(2)  { animation-delay: 0.1s; }
  section:nth-child(3)  { animation-delay: 0.2s; }
  section:nth-child(4)  { animation-delay: 0.3s; }
  section:nth-child(5)  { animation-delay: 0.4s; }
  section:nth-child(6)  { animation-delay: 0.5s; }

  @media (max-width: 640px) {
    .currently-grid, .cert-grid { grid-template-columns: 1fr; }
    .hero h1 { font-size: 38px; }
  }
</style>
</head>
<body>

<!-- BACKGROUND -->
<div class="bg">
  <div class="grid-lines"></div>
  <div class="orb orb1"></div>
  <div class="orb orb2"></div>
  <div class="orb orb3"></div>
  <div class="particles" id="particles"></div>
</div>

<div class="container">

  <!-- HERO -->
  <div class="hero">
    <div class="hero-badge">📊 Data Analyst &nbsp;·&nbsp; Business Analyst &nbsp;·&nbsp; IT Undergraduate</div>
    <h1>Aditi Mali</h1>
    <p class="hero-sub">Transforming raw data into <span>strategic business decisions</span></p>
    <div class="typing-bar">
      <div class="dot"></div>
      <span>Power BI · Tableau · SQL · Python · Excel · ML</span>
    </div>
    <div class="hero-links">
      <a class="btn btn-primary" href="mailto:aditimali285@gmail.com">✉️ Get In Touch</a>
      <a class="btn btn-outline" href="https://linkedin.com/in/aditi-mali-258982248" target="_blank">💼 LinkedIn</a>
      <a class="btn btn-outline" href="https://github.com/aditiMali23" target="_blank">🐙 GitHub</a>
    </div>
  </div>

  <!-- CURRENTLY -->
  <section>
    <div class="section-label">
      <span class="icon">📌</span>
      <h2>Currently</h2>
      <div class="line"></div>
    </div>
    <div class="currently-grid">
      <div class="currently-item">
        <span class="emoji">🔭</span>
        <div class="content">
          <label>Working On</label>
          <p>Business Intelligence Dashboards using Power BI & Tableau</p>
        </div>
      </div>
      <div class="currently-item">
        <span class="emoji">👥</span>
        <div class="content">
          <label>Looking To Collaborate</label>
          <p>Data-driven projects and analytics case studies</p>
        </div>
      </div>
      <div class="currently-item">
        <span class="emoji">💛</span>
        <div class="content">
          <label>Looking For Help With</label>
          <p>Predictive analytics & advanced ML for business forecasting</p>
        </div>
      </div>
      <div class="currently-item">
        <span class="emoji">🌱</span>
        <div class="content">
          <label>Currently Learning</label>
          <p>Advanced SQL, DAX for Power BI & Statistical Analysis</p>
        </div>
      </div>
      <div class="currently-item">
        <span class="emoji">💬</span>
        <div class="content">
          <label>Ask Me About</label>
          <p>KPI Tracking, Data Visualization, Business Reporting, SQL</p>
        </div>
      </div>
      <div class="currently-item">
        <span class="emoji">⚡</span>
        <div class="content">
          <label>Fun Fact</label>
          <p>I can look at a messy dataset and spot the story it's trying to tell!</p>
        </div>
      </div>
    </div>
  </section>

  <!-- CORE COMPETENCIES -->
  <section>
    <div class="section-label">
      <span class="icon">📊</span>
      <h2>Core Competencies</h2>
      <div class="line"></div>
    </div>
    <table class="comp-table">
      <thead>
        <tr>
          <th>Analytics</th>
          <th>Business Intelligence</th>
          <th>Tool</th>
        </tr>
      </thead>
      <tbody>
        <tr><td>Data Cleaning & EDA</td><td>Dashboard Design</td><td>Power BI</td></tr>
        <tr><td>KPI Tracking</td><td>Business Reporting</td><td>Tableau</td></tr>
        <tr><td>Statistical Analysis</td><td>Stakeholder Insights</td><td>Excel (Advanced)</td></tr>
        <tr><td>Data Storytelling</td><td>Trend Analysis</td><td>MySQL</td></tr>
        <tr><td>Predictive Insights</td><td>Decision Support</td><td>Python</td></tr>
      </tbody>
    </table>
  </section>

  <!-- TECH STACK -->
  <section>
    <div class="section-label">
      <span class="icon">🛠️</span>
      <h2>Tech Stack</h2>
      <div class="line"></div>
    </div>
    <div class="badges-section">
      <div class="badge-group">
        <label>Data & BI Tools</label>
        <div class="badge-row">
          <span class="badge badge-powerbi">📊 Power BI</span>
          <span class="badge badge-tableau">📈 Tableau</span>
          <span class="badge badge-excel">📗 Excel</span>
          <span class="badge badge-mysql">🗄️ MySQL</span>
          <span class="badge badge-python">🐍 Python</span>
        </div>
      </div>
      <div class="badge-group">
        <label>Development & Other</label>
        <div class="badge-row">
          <span class="badge badge-java">☕ Java</span>
          <span class="badge badge-android">🤖 Android</span>
          <span class="badge badge-firebase">🔥 Firebase</span>
          <span class="badge badge-git">🌿 Git</span>
          <span class="badge badge-vapt">🔐 VAPT</span>
        </div>
      </div>
    </div>
  </section>

  <!-- PROJECTS -->
  <section>
    <div class="section-label">
      <span class="icon">💼</span>
      <h2>Featured Projects</h2>
      <div class="line"></div>
    </div>
    <div class="projects-grid">
      <div class="project-card bi">
        <div class="project-header">
          <div class="project-title">📊 Adventure Works – BI Dashboard</div>
          <div class="project-tools">
            <span class="tool-tag">Tableau</span>
            <span class="tool-tag">Power BI</span>
            <span class="tool-tag">Excel</span>
          </div>
        </div>
        <p class="project-desc">Designed and developed end-to-end interactive dashboards to analyze sales performance, customer trends, and business KPIs. Enabled data-driven decision-making for stakeholders through dynamic visualizations, focused on telling a clear business story through data.</p>
        <div class="project-skills">
          <span class="skill-chip">Dashboard Design</span>
          <span class="skill-chip">KPI Tracking</span>
          <span class="skill-chip">Business Reporting</span>
          <span class="skill-chip">Data Visualization</span>
        </div>
      </div>

      <div class="project-card sec">
        <div class="project-header">
          <div class="project-title">🔒 VAPT Security Tool</div>
          <div class="project-tools">
            <span class="tool-tag">Python</span>
            <span class="tool-tag">Security Testing</span>
          </div>
        </div>
        <p class="project-desc">Built an automated vulnerability assessment tool to identify SQLi, XSS, and authentication vulnerabilities in e-commerce platforms. Streamlined security testing workflows, reducing manual testing time through automated scanning.</p>
        <div class="project-skills">
          <span class="skill-chip">Automation</span>
          <span class="skill-chip">Problem Solving</span>
          <span class="skill-chip">Python Scripting</span>
        </div>
      </div>

      <div class="project-card app">
        <div class="project-header">
          <div class="project-title">📱 Student Notes App</div>
          <div class="project-tools">
            <span class="tool-tag">Android</span>
            <span class="tool-tag">Java</span>
            <span class="tool-tag">Firebase</span>
          </div>
        </div>
        <p class="project-desc">Developed a fully functional Android app with categorized notes, search, and filtering capabilities. Integrated Firebase real-time database for cloud-synced storage. Deployed to 100+ students, significantly improving access to academic content.</p>
        <div class="project-skills">
          <span class="skill-chip">Full-Stack Development</span>
          <span class="skill-chip">Firebase</span>
          <span class="skill-chip">User-Centric Design</span>
        </div>
      </div>
    </div>
  </section>

  <!-- CERTIFICATIONS -->
  <section>
    <div class="section-label">
      <span class="icon">🏅</span>
      <h2>Certifications</h2>
      <div class="line"></div>
    </div>
    <div class="cert-grid">
      <div class="cert-card">
        <div class="cert-icon">🎓</div>
        <div class="cert-name">Data Analyst / Business Analyst</div>
        <div class="cert-issuer">ExcelR</div>
        <div class="cert-desc">Advanced analytics techniques covering BI, reporting, data-driven decision-making and business analysis.</div>
      </div>
      <div class="cert-card">
        <div class="cert-icon">🤖</div>
        <div class="cert-name">Generative AI for Analytics</div>
        <div class="cert-issuer">GenAI Program</div>
        <div class="cert-desc">AI-powered data analytics and job simulation training covering generative AI applications in business.</div>
      </div>
    </div>
  </section>

  <!-- CONNECT -->
  <section>
    <div class="section-label">
      <span class="icon">🤝</span>
      <h2>Let's Connect</h2>
      <div class="line"></div>
    </div>
    <div class="connect-grid">
      <a class="connect-btn linkedin" href="https://linkedin.com/in/aditi-mali-258982248" target="_blank">
        <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        LinkedIn
      </a>
      <a class="connect-btn gmail" href="mailto:aditimali285@gmail.com">
        <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor"><path d="M24 5.457v13.909c0 .904-.732 1.636-1.636 1.636h-3.819V11.73L12 16.64l-6.545-4.91v9.273H1.636A1.636 1.636 0 0 1 0 19.366V5.457c0-2.023 2.309-3.178 3.927-1.964L5.455 4.64 12 9.548l6.545-4.91 1.528-1.145C21.69 2.28 24 3.434 24 5.457z"/></svg>
        aditimali285@gmail.com
      </a>
      <a class="connect-btn github" href="https://github.com/aditiMali23" target="_blank">
        <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor"><path d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"/></svg>
        aditiMali23
      </a>
    </div>
  </section>

  <!-- FOOTER -->
  <div class="footer">
    <p class="quote">"I don't just analyze data — I translate it into business value."</p>
    <br/>
    <div class="open-badge">🟢 Open to DA & BA Internship Opportunities</div>
  </div>

</div>

<script>
  // Generate floating particles
  const container = document.getElementById('particles');
  for (let i = 0; i < 40; i++) {
    const p = document.createElement('div');
    p.className = 'particle';
    p.style.left = Math.random() * 100 + '%';
    p.style.width = p.style.height = (Math.random() * 3 + 1) + 'px';
    p.style.animationDuration = (Math.random() * 15 + 10) + 's';
    p.style.animationDelay = (Math.random() * 15) + 's';
    // Alternate colors
    const colors = ['#4f8ef7','#00d4aa','#f0b429','#ffffff'];
    p.style.background = colors[Math.floor(Math.random() * colors.length)];
    container.appendChild(p);
  }
</script>
</body>
</html>
