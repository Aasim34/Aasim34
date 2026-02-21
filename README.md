<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Mohammed Vasim — AI & ML Engineer</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=JetBrains+Mono:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --cyan: #00f7ff;
    --cyan-dim: rgba(0,247,255,0.12);
    --cyan-glow: rgba(0,247,255,0.4);
    --bg: #050a0f;
    --surface: #090f17;
    --surface2: #0d1720;
    --border: rgba(0,247,255,0.15);
    --text: #c8e6f0;
    --text-dim: #5a7a8a;
    --accent: #ff6b35;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    font-family: 'JetBrains Mono', monospace;
    background: var(--bg);
    color: var(--text);
    min-height: 100vh;
    overflow-x: hidden;
    position: relative;
  }

  /* Grid background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,247,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,247,255,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  /* Radial glow top-center */
  body::after {
    content: '';
    position: fixed;
    top: -200px;
    left: 50%;
    transform: translateX(-50%);
    width: 800px;
    height: 600px;
    background: radial-gradient(ellipse, rgba(0,247,255,0.07) 0%, transparent 70%);
    pointer-events: none;
    z-index: 0;
  }

  .wrapper {
    max-width: 780px;
    margin: 0 auto;
    padding: 60px 24px;
    position: relative;
    z-index: 1;
  }

  /* ─── HEADER ─── */
  .header {
    text-align: center;
    margin-bottom: 64px;
    position: relative;
  }

  .status-bar {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: var(--surface2);
    border: 1px solid var(--border);
    border-radius: 100px;
    padding: 6px 16px;
    font-size: 11px;
    color: var(--text-dim);
    letter-spacing: 0.12em;
    text-transform: uppercase;
    margin-bottom: 28px;
  }

  .status-dot {
    width: 6px; height: 6px;
    background: var(--cyan);
    border-radius: 50%;
    box-shadow: 0 0 6px var(--cyan);
    animation: pulse 2s ease-in-out infinite;
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; box-shadow: 0 0 6px var(--cyan); }
    50% { opacity: 0.4; box-shadow: 0 0 2px var(--cyan); }
  }

  .name {
    font-family: 'Syne', sans-serif;
    font-size: clamp(2.4rem, 7vw, 4rem);
    font-weight: 800;
    line-height: 1;
    letter-spacing: -0.02em;
    color: #fff;
    margin-bottom: 12px;
  }

  .name span {
    color: var(--cyan);
    text-shadow: 0 0 30px var(--cyan-glow), 0 0 60px rgba(0,247,255,0.2);
  }

  .tagline {
    font-size: 12px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--text-dim);
    margin-bottom: 32px;
  }

  .typewriter-container {
    display: inline-block;
    font-size: 14px;
    color: var(--cyan);
    letter-spacing: 0.05em;
    margin-bottom: 36px;
    min-height: 22px;
    position: relative;
  }

  .typewriter-container::after {
    content: '|';
    animation: blink 0.8s step-end infinite;
    color: var(--cyan);
    margin-left: 2px;
  }

  @keyframes blink { 0%, 100% { opacity: 1; } 50% { opacity: 0; } }

  .links {
    display: flex;
    justify-content: center;
    gap: 12px;
    flex-wrap: wrap;
  }

  .link-btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 9px 20px;
    border: 1px solid var(--border);
    border-radius: 8px;
    background: var(--surface2);
    color: var(--text);
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    text-decoration: none;
    transition: all 0.2s;
    letter-spacing: 0.05em;
  }

  .link-btn:hover {
    border-color: var(--cyan);
    color: var(--cyan);
    background: var(--cyan-dim);
    box-shadow: 0 0 20px rgba(0,247,255,0.1);
    transform: translateY(-1px);
  }

  .link-btn .ico { font-size: 14px; }

  /* ─── SECTION ─── */
  section { margin-bottom: 56px; }

  .section-label {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 24px;
  }

  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, var(--border), transparent);
  }

  .section-title {
    font-family: 'Syne', sans-serif;
    font-size: 11px;
    font-weight: 700;
    letter-spacing: 0.25em;
    text-transform: uppercase;
    color: var(--cyan);
  }

  .section-num {
    font-size: 10px;
    color: var(--text-dim);
    letter-spacing: 0.1em;
  }

  /* ─── ABOUT ─── */
  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
  }

  .about-item {
    display: flex;
    align-items: flex-start;
    gap: 12px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 14px 16px;
    font-size: 12px;
    line-height: 1.5;
    transition: border-color 0.2s, background 0.2s;
  }

  .about-item:hover {
    border-color: rgba(0,247,255,0.3);
    background: var(--surface2);
  }

  .about-icon {
    font-size: 18px;
    flex-shrink: 0;
    margin-top: 1px;
  }

  .about-text { color: var(--text); }

  /* ─── TECH STACK ─── */
  .tech-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .tech-tag {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 7px 14px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 6px;
    font-size: 11px;
    letter-spacing: 0.08em;
    color: var(--text);
    transition: all 0.2s;
    cursor: default;
  }

  .tech-tag:hover {
    border-color: var(--cyan);
    color: var(--cyan);
    background: var(--cyan-dim);
    transform: translateY(-2px);
    box-shadow: 0 4px 16px rgba(0,247,255,0.08);
  }

  .tech-dot {
    width: 5px; height: 5px;
    border-radius: 50%;
    background: currentColor;
    opacity: 0.6;
  }

  /* ─── PROJECTS ─── */
  .projects-grid {
    display: grid;
    gap: 16px;
  }

  .project-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 24px 28px;
    position: relative;
    overflow: hidden;
    transition: all 0.25s;
  }

  .project-card::before {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, var(--cyan-dim) 0%, transparent 60%);
    opacity: 0;
    transition: opacity 0.25s;
  }

  .project-card:hover {
    border-color: rgba(0,247,255,0.3);
    transform: translateY(-2px);
    box-shadow: 0 8px 32px rgba(0,247,255,0.06);
  }

  .project-card:hover::before { opacity: 1; }

  .project-header {
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    margin-bottom: 10px;
    position: relative;
  }

  .project-name {
    font-family: 'Syne', sans-serif;
    font-size: 16px;
    font-weight: 700;
    color: #fff;
    display: flex;
    align-items: center;
    gap: 10px;
  }

  .project-emoji { font-size: 20px; }

  .project-badge {
    font-size: 9px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    padding: 3px 10px;
    border-radius: 100px;
    border: 1px solid rgba(0,247,255,0.3);
    color: var(--cyan);
    background: var(--cyan-dim);
  }

  .project-desc {
    font-size: 12px;
    color: var(--text-dim);
    line-height: 1.7;
    position: relative;
  }

  .project-tags {
    display: flex;
    gap: 8px;
    margin-top: 14px;
    flex-wrap: wrap;
    position: relative;
  }

  .p-tag {
    font-size: 10px;
    letter-spacing: 0.1em;
    padding: 3px 10px;
    border-radius: 4px;
    background: var(--surface2);
    border: 1px solid var(--border);
    color: var(--text-dim);
  }

  /* ─── STATS ─── */
  .stats-row {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin-bottom: 16px;
  }

  .stat-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    overflow: hidden;
    aspect-ratio: 2/1;
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
  }

  .stat-card img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 12px;
  }

  .stats-single {
    display: flex;
    justify-content: center;
  }

  .stats-single .stat-card {
    width: 50%;
    aspect-ratio: 2/1;
  }

  /* ─── ACHIEVEMENTS ─── */
  .achievements {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 12px;
  }

  .ach-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 20px;
    text-align: center;
    transition: all 0.2s;
  }

  .ach-card:hover {
    border-color: rgba(0,247,255,0.25);
    background: var(--surface2);
  }

  .ach-icon { font-size: 28px; margin-bottom: 10px; }

  .ach-title {
    font-family: 'Syne', sans-serif;
    font-size: 13px;
    font-weight: 700;
    color: #fff;
    margin-bottom: 4px;
  }

  .ach-desc {
    font-size: 10px;
    color: var(--text-dim);
    line-height: 1.5;
  }

  /* ─── FOOTER ─── */
  .footer {
    text-align: center;
    padding-top: 32px;
    border-top: 1px solid var(--border);
  }

  .footer-counter {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    font-size: 11px;
    color: var(--text-dim);
    margin-bottom: 20px;
  }

  .counter-num {
    color: var(--cyan);
    font-weight: 500;
  }

  .motto {
    font-family: 'Syne', sans-serif;
    font-size: 14px;
    font-weight: 600;
    color: var(--text-dim);
    letter-spacing: 0.05em;
  }

  .motto span {
    color: var(--cyan);
  }

  /* ─── ANIMATIONS ─── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .header { animation: fadeUp 0.6s ease both; }
  section:nth-child(1) { animation: fadeUp 0.6s 0.1s ease both; }
  section:nth-child(2) { animation: fadeUp 0.6s 0.2s ease both; }
  section:nth-child(3) { animation: fadeUp 0.6s 0.3s ease both; }
  section:nth-child(4) { animation: fadeUp 0.6s 0.4s ease both; }
  section:nth-child(5) { animation: fadeUp 0.6s 0.5s ease both; }

  .corner-decoration {
    position: absolute;
    width: 60px; height: 60px;
    border-color: rgba(0,247,255,0.2);
    border-style: solid;
    pointer-events: none;
  }

  .corner-tl { top: 0; left: 0; border-width: 2px 0 0 2px; border-radius: 4px 0 0 0; }
  .corner-tr { top: 0; right: 0; border-width: 2px 2px 0 0; border-radius: 0 4px 0 0; }
  .corner-bl { bottom: 0; left: 0; border-width: 0 0 2px 2px; border-radius: 0 0 0 4px; }
  .corner-br { bottom: 0; right: 0; border-width: 0 2px 2px 0; border-radius: 0 0 4px 0; }

  .highlight-card {
    position: relative;
    padding: 4px;
  }

  @media (max-width: 560px) {
    .about-grid { grid-template-columns: 1fr; }
    .achievements { grid-template-columns: 1fr; }
    .stats-row { grid-template-columns: 1fr; }
    .stats-single .stat-card { width: 100%; }
  }
</style>
</head>
<body>

<div class="wrapper">

  <!-- ═══ HEADER ═══ -->
  <div class="header">
    <div class="status-bar">
      <span class="status-dot"></span>
      Available for opportunities
    </div>

    <h1 class="name">Mohammed <span>Vasim</span></h1>
    <p class="tagline">AI & Machine Learning Engineer · Tech Explorer · Automation Builder</p>

    <div class="typewriter-container" id="typewriter"></div>

    <div class="links">
      <a href="mailto:your-email@gmail.com" class="link-btn">
        <span class="ico">✉</span> Gmail
      </a>
      <a href="https://www.linkedin.com/" class="link-btn">
        <span class="ico">in</span> LinkedIn
      </a>
      <a href="https://github.com/Aasim34" class="link-btn">
        <span class="ico">⌥</span> GitHub
      </a>
    </div>
  </div>

  <!-- ═══ ABOUT ═══ -->
  <section>
    <div class="section-label">
      <span class="section-num">01</span>
      <span class="section-title">About Me</span>
    </div>
    <div class="about-grid">
      <div class="about-item">
        <span class="about-icon">🎓</span>
        <span class="about-text">Computer Science Student pushing boundaries in AI research</span>
      </div>
      <div class="about-item">
        <span class="about-icon">🤖</span>
        <span class="about-text">Aspiring AI & ML Engineer building real-world systems</span>
      </div>
      <div class="about-item">
        <span class="about-icon">🔍</span>
        <span class="about-text">Focused on AI Detection, Automation & Cloud Vision</span>
      </div>
      <div class="about-item">
        <span class="about-icon">🌱</span>
        <span class="about-text">Currently deep-diving into Deep Learning & System Design</span>
      </div>
      <div class="about-item" style="grid-column: 1 / -1;">
        <span class="about-icon">⚡</span>
        <span class="about-text">Passion: Turning raw ideas into impactful, scalable products that matter</span>
      </div>
    </div>
  </section>

  <!-- ═══ TECH STACK ═══ -->
  <section>
    <div class="section-label">
      <span class="section-num">02</span>
      <span class="section-title">Tech Stack</span>
    </div>
    <div class="tech-grid">
      <span class="tech-tag"><span class="tech-dot"></span>Python</span>
      <span class="tech-tag"><span class="tech-dot"></span>JavaScript</span>
      <span class="tech-tag"><span class="tech-dot"></span>React</span>
      <span class="tech-tag"><span class="tech-dot"></span>Node.js</span>
      <span class="tech-tag"><span class="tech-dot"></span>TensorFlow</span>
      <span class="tech-tag"><span class="tech-dot"></span>HTML / CSS</span>
      <span class="tech-tag"><span class="tech-dot"></span>C++</span>
      <span class="tech-tag"><span class="tech-dot"></span>C</span>
      <span class="tech-tag"><span class="tech-dot"></span>Firebase</span>
      <span class="tech-tag"><span class="tech-dot"></span>Git</span>
      <span class="tech-tag"><span class="tech-dot"></span>GitHub</span>
      <span class="tech-tag"><span class="tech-dot"></span>VS Code</span>
    </div>
  </section>

  <!-- ═══ PROJECTS ═══ -->
  <section>
    <div class="section-label">
      <span class="section-num">03</span>
      <span class="section-title">Featured Projects</span>
    </div>
    <div class="projects-grid">

      <div class="project-card">
        <div class="project-header">
          <div class="project-name">
            <span class="project-emoji">🧠</span> Real-Eye
          </div>
          <span class="project-badge">AI Detection</span>
        </div>
        <p class="project-desc">
          AI-generated image detection engine using Error Level Analysis (ELA) and noise pattern inspection. Distinguishes real photographs from synthetic media with precision.
        </p>
        <div class="project-tags">
          <span class="p-tag">Python</span>
          <span class="p-tag">ELA</span>
          <span class="p-tag">Computer Vision</span>
          <span class="p-tag">Deep Learning</span>
        </div>
      </div>

      <div class="project-card">
        <div class="project-header">
          <div class="project-name">
            <span class="project-emoji">🌐</span> Nexa AI
          </div>
          <span class="project-badge">Browser Ext.</span>
        </div>
        <p class="project-desc">
          AI-powered browser extension delivering real-time intelligent content analysis, summarization, and context-aware assistance directly in the browser.
        </p>
        <div class="project-tags">
          <span class="p-tag">JavaScript</span>
          <span class="p-tag">LLM</span>
          <span class="p-tag">Chrome Extension</span>
        </div>
      </div>

      <div class="project-card">
        <div class="project-header">
          <div class="project-name">
            <span class="project-emoji">💻</span> Portfolio Website
          </div>
          <span class="project-badge">Web</span>
        </div>
        <p class="project-desc">
          Modern developer portfolio crafted with clean UI principles and performance-first architecture. A showcase of technical depth and design sensibility.
        </p>
        <div class="project-tags">
          <span class="p-tag">React</span>
          <span class="p-tag">CSS</span>
          <span class="p-tag">Performance</span>
        </div>
      </div>

    </div>
  </section>

  <!-- ═══ GITHUB ANALYTICS ═══ -->
  <section>
    <div class="section-label">
      <span class="section-num">04</span>
      <span class="section-title">GitHub Analytics</span>
    </div>
    <div class="stats-row">
      <div class="stat-card">
        <img src="https://github-readme-stats.vercel.app/api?username=Aasim34&show_icons=true&theme=tokyonight&bg_color=090f17&border_color=0d2535&title_color=00f7ff&icon_color=00f7ff&text_color=c8e6f0&hide_border=false" alt="GitHub Stats" loading="lazy"/>
      </div>
      <div class="stat-card">
        <img src="https://github-readme-streak-stats.herokuapp.com/?user=Aasim34&theme=tokyonight&background=090f17&border=0d2535&ring=00f7ff&fire=ff6b35&currStreakLabel=00f7ff" alt="Streak Stats" loading="lazy"/>
      </div>
    </div>
    <div class="stats-single">
      <div class="stat-card" style="width:55%; aspect-ratio: unset; padding: 12px;">
        <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Aasim34&layout=compact&theme=tokyonight&bg_color=090f17&border_color=0d2535&title_color=00f7ff&text_color=c8e6f0" alt="Top Languages" loading="lazy" style="object-fit: contain; border-radius: 8px;"/>
      </div>
    </div>
  </section>

  <!-- ═══ ACHIEVEMENTS ═══ -->
  <section>
    <div class="section-label">
      <span class="section-num">05</span>
      <span class="section-title">Achievements</span>
    </div>
    <div class="achievements">
      <div class="ach-card">
        <div class="ach-icon">🔥</div>
        <div class="ach-title">Consistent Contributor</div>
        <div class="ach-desc">Regular commits & steady progress across all projects</div>
      </div>
      <div class="ach-card">
        <div class="ach-icon">🧠</div>
        <div class="ach-title">Quality Focused</div>
        <div class="ach-desc">Prioritizing depth, clarity, and meaningful impact</div>
      </div>
      <div class="ach-card">
        <div class="ach-icon">🚀</div>
        <div class="ach-title">AI-First Builder</div>
        <div class="ach-desc">Shipping products where intelligence is the foundation</div>
      </div>
    </div>
  </section>

  <!-- ═══ FOOTER ═══ -->
  <div class="footer">
    <div class="footer-counter">
      <span>Profile Views</span>
      <img src="https://komarev.com/ghpvc/?username=Aasim34&label=&color=00f7ff&style=flat" alt="views" style="height:18px;vertical-align:middle;"/>
    </div>
    <div class="motto">
      ⭐ &nbsp;<span>"Code. Learn. Break. Fix. Repeat."</span>&nbsp; ⭐
    </div>
  </div>

</div>

<script>
  // Typewriter effect
  const phrases = [
    'AI & Machine Learning Enthusiast',
    'Full Stack Developer',
    'Cloud Vision Explorer',
    'Building Real World AI Projects',
    'Code. Learn. Break. Fix. Repeat.',
  ];

  let pi = 0, ci = 0, deleting = false, pause = false;
  const el = document.getElementById('typewriter');

  function type() {
    if (pause) { setTimeout(type, 1400); pause = false; return; }
    const phrase = phrases[pi];
    if (!deleting) {
      el.textContent = phrase.slice(0, ci + 1);
      ci++;
      if (ci === phrase.length) { pause = true; deleting = true; setTimeout(type, 60); return; }
      setTimeout(type, 55);
    } else {
      el.textContent = phrase.slice(0, ci - 1);
      ci--;
      if (ci === 0) {
        deleting = false;
        pi = (pi + 1) % phrases.length;
      }
      setTimeout(type, 28);
    }
  }

  type();
</script>
</body>
</html>
