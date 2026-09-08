<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Imran Kedir · Full‑Stack Dev</title>
  <!-- Font Awesome (free icons) -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    /* ----- reset & base ----- */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background: #0b0d15;
      background-image: radial-gradient(circle at 10% 20%, rgba(20, 30, 50, 0.6) 0%, transparent 50%),
                        radial-gradient(circle at 80% 70%, rgba(10, 50, 40, 0.3) 0%, transparent 60%);
      font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
      color: #e2e8f0;
      line-height: 1.6;
      padding: 2rem 1rem;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
    }

    .glass-card {
      max-width: 1100px;
      width: 100%;
      background: rgba(18, 26, 40, 0.65);
      backdrop-filter: blur(16px) saturate(180%);
      -webkit-backdrop-filter: blur(16px) saturate(180%);
      border: 1px solid rgba(255, 255, 255, 0.06);
      border-radius: 3.5rem;
      box-shadow: 0 30px 60px -20px rgba(0,0,0,0.8), 0 0 0 1px rgba(255,255,255,0.02) inset;
      padding: 2.8rem 2.5rem;
      transition: all 0.3s ease;
    }

    /* ----- typography ----- */
    h1, h2, h3 {
      font-weight: 500;
      letter-spacing: -0.02em;
    }

    h1 {
      font-size: 2.8rem;
      background: linear-gradient(145deg, #f0f9ff 0%, #a5d9ff 80%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      margin-bottom: 0.2rem;
    }

    .subhead {
      font-size: 1.2rem;
      font-weight: 400;
      color: #b0c7e7;
      letter-spacing: -0.01em;
      margin-bottom: 0.75rem;
    }

    .badge-group {
      display: flex;
      flex-wrap: wrap;
      gap: 0.7rem 1.2rem;
      justify-content: center;
      margin: 1rem 0 1.2rem 0;
    }

    .badge-link {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      background: rgba(255, 255, 255, 0.04);
      backdrop-filter: blur(4px);
      padding: 0.4rem 1.2rem 0.4rem 1rem;
      border-radius: 40px;
      border: 1px solid rgba(255, 255, 255, 0.06);
      color: #d6e3ff;
      font-size: 0.9rem;
      font-weight: 450;
      text-decoration: none;
      transition: 0.25s ease;
      box-shadow: 0 2px 8px rgba(0,0,0,0.2);
    }

    .badge-link i {
      font-size: 1.1rem;
      color: #70b8ff;
    }

    .badge-link:hover {
      background: rgba(60, 130, 255, 0.15);
      border-color: rgba(100, 180, 255, 0.3);
      transform: translateY(-2px);
      box-shadow: 0 8px 20px -10px #1a6eff40;
    }

    .bio-text {
      max-width: 720px;
      margin: 0.5rem auto 1.8rem auto;
      font-size: 1rem;
      color: #c8d9f0;
      background: rgba(0, 0, 0, 0.15);
      padding: 1rem 1.8rem;
      border-radius: 60px;
      backdrop-filter: blur(4px);
      border: 1px solid rgba(255,255,255,0.03);
    }

    hr {
      border: none;
      height: 1px;
      background: linear-gradient(90deg, transparent, rgba(255,255,255,0.08), transparent);
      margin: 2rem 0 1.8rem 0;
    }

    /* ----- grid sections ----- */
    .grid-2col {
      display: grid;
      grid-template-columns: 1fr 1.2fr;
      gap: 2rem;
      margin-top: 0.5rem;
    }

    @media (max-width: 760px) {
      .glass-card { padding: 1.8rem 1.2rem; }
      h1 { font-size: 2.1rem; }
      .grid-2col { grid-template-columns: 1fr; gap: 1.5rem; }
      .badge-group { gap: 0.5rem; }
    }

    .section-title {
      font-size: 1.1rem;
      text-transform: uppercase;
      letter-spacing: 0.04em;
      color: #8aa9e6;
      margin-bottom: 1.2rem;
      border-bottom: 1px solid rgba(255,255,255,0.04);
      padding-bottom: 0.5rem;
      display: flex;
      align-items: center;
      gap: 0.6rem;
    }

    .section-title i {
      color: #4a8eff;
      font-size: 1.2rem;
    }

    .tech-tag {
      display: inline-block;
      background: rgba(60, 130, 255, 0.08);
      border: 1px solid rgba(70, 140, 255, 0.15);
      padding: 0.15rem 0.9rem;
      border-radius: 30px;
      font-size: 0.8rem;
      font-weight: 450;
      color: #bfd7ff;
      margin: 0.15rem 0.15rem;
      backdrop-filter: blur(4px);
      transition: 0.2s;
    }

    .tech-tag:hover {
      background: rgba(60, 130, 255, 0.18);
      border-color: #4a8eff60;
    }

    .project-item {
      background: rgba(0, 0, 0, 0.2);
      border-radius: 2rem;
      padding: 1rem 1.4rem;
      margin-bottom: 1rem;
      border-left: 3px solid #2d6aff40;
      transition: 0.2s;
    }

    .project-item:hover {
      background: rgba(20, 40, 70, 0.3);
      border-left-color: #4a8eff;
    }

    .project-item h3 {
      font-size: 1.05rem;
      font-weight: 500;
      color: #deecff;
      display: flex;
      align-items: center;
      gap: 0.6rem;
    }

    .project-item h3 i {
      color: #4a8eff;
      font-size: 1rem;
    }

    .project-item p {
      font-size: 0.9rem;
      color: #bccce6;
      margin-top: 0.2rem;
    }

    .project-stack {
      margin-top: 0.4rem;
      display: flex;
      flex-wrap: wrap;
      gap: 0.3rem;
    }

    .stat-box {
      background: rgba(0, 0, 0, 0.25);
      border-radius: 2rem;
      padding: 1.4rem 1.2rem;
      backdrop-filter: blur(4px);
      border: 1px solid rgba(255,255,255,0.02);
    }

    .stat-box img {
      border-radius: 16px;
      width: 100%;
      height: auto;
      box-shadow: 0 10px 30px -10px #00000080;
    }

    .flex-stats {
      display: flex;
      flex-wrap: wrap;
      gap: 1.2rem;
      justify-content: center;
    }

    .flex-stats > * {
      flex: 1 1 180px;
    }

    .connect-links {
      display: flex;
      flex-wrap: wrap;
      gap: 0.8rem 1.5rem;
      justify-content: center;
      margin: 1.2rem 0 0.5rem 0;
    }

    .connect-links a {
      color: #c4d7ff;
      text-decoration: none;
      font-size: 0.95rem;
      display: inline-flex;
      align-items: center;
      gap: 0.4rem;
      border-bottom: 1px solid transparent;
      transition: 0.2s;
      padding: 0.1rem 0.1rem;
    }

    .connect-links a i {
      color: #5b93ff;
      width: 1.4rem;
    }

    .connect-links a:hover {
      color: white;
      border-bottom-color: #4a8eff80;
    }

    .footer-quote {
      text-align: center;
      margin-top: 1.6rem;
      font-size: 0.95rem;
      color: #809bc7;
      letter-spacing: 0.02em;
    }

    .footer-quote i {
      color: #4a8eff;
      margin: 0 0.2rem;
    }

    .level-up-list {
      list-style: none;
      padding-left: 0.2rem;
    }

    .level-up-list li {
      padding: 0.2rem 0;
      display: flex;
      align-items: center;
      gap: 0.6rem;
      font-size: 0.92rem;
      color: #ccdefa;
    }

    .level-up-list li i {
      color: #3d85ff;
      width: 1.2rem;
      font-size: 0.8rem;
    }

    .highlight {
      color: #b0d0ff;
      font-weight: 450;
    }
  </style>
</head>
<body>

<div class="glass-card">

  <!-- header -->
  <div style="text-align: center;">
    <h1>👋 Hi, I'm Imran Kedir</h1>
    <div class="subhead">Full‑Stack Software Developer · React · TypeScript · Node.js · PostgreSQL</div>

    <div class="badge-group">
      <a href="https://imranka.vercel.app/" class="badge-link"><i class="fas fa-globe"></i> Portfolio</a>
      <a href="https://www.linkedin.com/in/imranka641/" class="badge-link"><i class="fab fa-linkedin-in"></i> LinkedIn</a>
      <a href="https://t.me/imranka641" class="badge-link"><i class="fab fa-telegram-plane"></i> Telegram</a>
      <a href="mailto:imranka641@gmail.com" class="badge-link"><i class="fas fa-envelope"></i> Email</a>
    </div>

    <div class="bio-text">
      <i class="fas fa-code" style="margin-right: 0.5rem; color: #5b93ff;"></i>
      I build modern, high‑performance, production‑ready web applications with a strong focus on clean UI/UX, scalable backend architectures, and reliable real‑world solutions.
    </div>
  </div>

  <hr>

  <!-- about + featured projects grid -->
  <div class="grid-2col">

    <!-- left column: about + stack + level up -->
    <div>
      <!-- about -->
      <div class="section-title"><i class="fas fa-user-astronaut"></i> About Me</div>
      <div style="background: rgba(0,0,0,0.15); border-radius: 2rem; padding: 1.2rem 1.5rem; backdrop-filter: blur(4px);">
        <p style="margin-bottom: 0.6rem;"><i class="fas fa-graduation-cap" style="color: #4a8eff; width: 1.6rem;"></i> B.Sc. Information Science · Jimma University (JiT)</p>
        <p style="margin-bottom: 0.6rem;"><i class="fas fa-layer-group" style="color: #4a8eff; width: 1.6rem;"></i> Full‑Stack web engineering: React/TS + Node.js/Express</p>
        <p style="margin-bottom: 0.6rem;"><i class="fas fa-database" style="color: #4a8eff; width: 1.6rem;"></i> PostgreSQL · Prisma · MySQL — normalized schemas</p>
        <p style="margin-bottom: 0.4rem;"><i class="fas fa-robot" style="color: #4a8eff; width: 1.6rem;"></i> AI chatbots · privacy‑first offline tools · workflow automation</p>
        <p style="margin-top: 0.8rem;"><i class="fas fa-handshake" style="color: #4a8eff; width: 1.6rem;"></i> <span class="highlight">Open for contract, freelance & full‑time remote</span></p>
      </div>

      <!-- tech stack -->
      <div class="section-title" style="margin-top: 2rem;"><i class="fas fa-cogs"></i> Tech Stack</div>
      <div style="display: flex; flex-wrap: wrap; gap: 0.35rem 0.5rem; background: rgba(0,0,0,0.08); padding: 0.8rem 1rem; border-radius: 2rem;">
        <span class="tech-tag">React</span><span class="tech-tag">TypeScript</span><span class="tech-tag">JavaScript</span>
        <span class="tech-tag">Tailwind CSS</span><span class="tech-tag">Node.js</span><span class="tech-tag">Express</span>
        <span class="tech-tag">PHP</span><span class="tech-tag">REST APIs</span><span class="tech-tag">PostgreSQL</span>
        <span class="tech-tag">Prisma</span><span class="tech-tag">MySQL</span><span class="tech-tag">Git</span>
        <span class="tech-tag">Vite</span><span class="tech-tag">Postman</span>
      </div>

      <!-- level up -->
      <div class="section-title" style="margin-top: 2rem;"><i class="fas fa-rocket"></i> Currently Leveling Up</div>
      <ul class="level-up-list">
        <li><i class="fas fa-bolt"></i> Advanced React & TypeScript · design systems, state orchestration</li>
        <li><i class="fas fa-project-diagram"></i> Distributed backend · clean architecture, microservices</li>
        <li><i class="fas fa-database"></i> PostgreSQL query optimization, connection pooling, Prisma</li>
        <li><i class="fas fa-lock"></i> OAuth2, JWT lifecycle, RBAC policies</li>
        <li><i class="fas fa-cloud-upload-alt"></i> DevOps: CI/CD, container builds, zero‑downtime</li>
      </ul>
    </div>

    <!-- right column: featured projects + stats -->
    <div>
      <div class="section-title"><i class="fas fa-star"></i> Featured Projects</div>

      <div class="project-item">
        <h3><i class="fas fa-comment-dots"></i> AI Business Chatbot</h3>
        <p>Intelligent customer assistant with custom knowledge‑base ingestion, FAQs & service catalogs.</p>
        <div class="project-stack"><span class="tech-tag">React</span><span class="tech-tag">Node.js</span><span class="tech-tag">Express</span><span class="tech-tag">AI APIs</span></div>
      </div>

      <div class="project-item">
        <h3><i class="fas fa-file-signature"></i> Tax Clearance Certificate System</h3>
        <p>Enterprise platform with QR fraud‑verification, multi‑role access, and real‑time validation.</p>
        <div class="project-stack"><span class="tech-tag">React</span><span class="tech-tag">TypeScript</span><span class="tech-tag">PostgreSQL</span><span class="tech-tag">Prisma</span></div>
      </div>

      <div class="project-item">
        <h3><i class="fas fa-pray"></i> DelailulKheirat</h3>
        <p>Daily zikr & prayer companion with categorized readings, audio, notifications & local persistence.</p>
        <div class="project-stack"><span class="tech-tag">Mobile/Web</span><span class="tech-tag">JavaScript</span><span class="tech-tag">Local Persistence</span></div>
      </div>

      <div class="project-item" style="margin-bottom: 0;">
        <h3><i class="fas fa-home"></i> Real Estate Platform</h3>
        <p>End‑to‑end property management: unit catalog, lease scheduling, inquiry pipelines, floor plans.</p>
        <div class="project-stack"><span class="tech-tag">Node.js</span><span class="tech-tag">Express</span><span class="tech-tag">PostgreSQL</span><span class="tech-tag">MySQL</span></div>
      </div>

      <div style="margin-top: 1.2rem; text-align: right; font-size: 0.9rem; color: #8aa9e6;">
        <i class="fas fa-arrow-right"></i> <a href="https://imranka.vercel.app/" style="color: #8bb1ff; text-decoration: none;">explore more on portfolio →</a>
      </div>

      <!-- GitHub stats (modern minimal) -->
      <div class="section-title" style="margin-top: 1.8rem;"><i class="fab fa-github"></i> GitHub Metrics</div>
      <div class="flex-stats">
        <div class="stat-box">
          <img src="https://github-readme-stats.vercel.app/api?username=imranka641&show_icons=true&theme=tokyonight&hide_border=true&count_private=true&bg_color=0d1117&title_color=8bb1ff&icon_color=4a8eff" alt="stats" />
        </div>
        <div class="stat-box">
          <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=imranka641&layout=compact&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=8bb1ff" alt="top langs" />
        </div>
      </div>
    </div>
  </div>

  <hr>

  <!-- connect -->
  <div style="text-align: center;">
    <div class="section-title" style="justify-content: center; border-bottom: none; margin-bottom: 0.4rem;">
      <i class="fas fa-paper-plane"></i> Connect & Collaborate
    </div>
    <div class="connect-links">
      <a href="https://imranka.vercel.app/"><i class="fas fa-globe"></i> imranka.vercel.app</a>
      <a href="https://www.linkedin.com/in/imranka641/"><i class="fab fa-linkedin-in"></i> imranka641</a>
      <a href="https://t.me/imranka641"><i class="fab fa-telegram-plane"></i> @imranka641</a>
      <a href="https://wa.me/251913841757"><i class="fab fa-whatsapp"></i> +251 913 841 757</a>
      <a href="mailto:imranka641@gmail.com"><i class="fas fa-envelope"></i> imranka641@gmail.com</a>
    </div>

    <div class="footer-quote">
      <i class="fas fa-code"></i> “Building useful, resilient software — one commit at a time.” <i class="fas fa-code"></i>
    </div>
  </div>

</div>
<!-- end glass-card -->

</body>
</html>
