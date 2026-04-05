
<style>
  @import url('https://fonts.googleapis.com/css2?family=Fira+Code:wght@300;400;500;600&family=Space+Mono:wght@400;700&display=swap');
  * { box-sizing: border-box; margin: 0; padding: 0; }
  .readme-wrap { font-family: 'Fira Code', monospace; background: #0d1117; color: #e6edf3; border-radius: 12px; overflow: hidden; border: 1px solid #30363d; max-width: 860px; margin: 0 auto; }
  .tab-bar { background: #161b22; border-bottom: 1px solid #30363d; padding: 0 16px; display: flex; align-items: center; gap: 8px; height: 40px; }
  .dot { width: 12px; height: 12px; border-radius: 50%; }
  .dot.r{background:#ff5f57}.dot.y{background:#febc2e}.dot.g{background:#28c840}
  .tab-label { font-size: 11px; color: #7d8590; margin-left: 8px; }
  .readme-body { padding: 28px 32px 36px; position: relative; }
  .hero { display: flex; align-items: center; gap: 20px; margin-bottom: 28px; padding-bottom: 24px; border-bottom: 1px solid #21262d; }
  .avatar-ring { width: 80px; height: 80px; border-radius: 50%; border: 2px solid #238636; padding: 3px; flex-shrink: 0; background: #161b22; display: flex; align-items: center; justify-content: center; font-size: 32px; position: relative; }
  .avatar-ring::after { content:''; position:absolute; inset:-4px; border-radius:50%; border:2px solid #1f6feb; opacity:0.4; }
  .hero-text h1 { font-family:'Space Mono',monospace; font-size:22px; font-weight:700; color:#e6edf3; margin-bottom:6px; }
  .hero-text h1 span { color:#3fb950; }
  .badges { display:flex; flex-wrap:wrap; gap:6px; }
  .badge-inline { background:#1f6feb22; border:1px solid #1f6feb55; color:#58a6ff; font-size:11px; padding:2px 8px; border-radius:20px; }
  .section-label { font-size:11px; color:#3fb950; letter-spacing:2px; text-transform:uppercase; margin-bottom:12px; font-family:'Space Mono',monospace; display:flex; align-items:center; gap:8px; }
  .section-label::after { content:''; flex:1; height:1px; background:#21262d; }
  .about-block { background:#161b22; border:1px solid #30363d; border-left:3px solid #3fb950; border-radius:6px; padding:16px 20px; margin-bottom:24px; font-size:13px; color:#8b949e; line-height:1.8; }
  .about-block .line { display:flex; align-items:flex-start; gap:10px; margin-bottom:5px; }
  .about-block .line:last-child { margin-bottom:0; }
  .ico{color:#3fb950;flex-shrink:0}.ico.b{color:#58a6ff}.ico.a{color:#d29922}.ico.r{color:#f85149}
  .val{color:#e6edf3}.val a{color:#58a6ff;text-decoration:none}.val a:hover{text-decoration:underline}

  .stats-row { display:grid; grid-template-columns:repeat(3,1fr); gap:10px; margin-bottom:24px; }
  .stat-card { background:#161b22; border:1px solid #30363d; border-radius:8px; padding:14px 16px; }
  .stat-card .s-label { font-size:11px; color:#7d8590; }
  .stat-card .s-val { font-size:18px; font-weight:700; font-family:'Space Mono',monospace; margin-top:2px; }
  .stat-card.green{border-top:2px solid #3fb950}.stat-card.blue{border-top:2px solid #58a6ff}.stat-card.amber{border-top:2px solid #d29922}
  .stat-card.green .s-val{color:#3fb950}.stat-card.blue .s-val{color:#58a6ff}.stat-card.amber .s-val{color:#d29922}

  .projects-grid { display:grid; grid-template-columns:1fr 1fr; gap:10px; margin-bottom:24px; }
  .pc { background:#161b22; border:1px solid #30363d; border-radius:8px; padding:14px 16px; position:relative; overflow:hidden; }
  .pc::before { content:''; position:absolute; top:0;left:0;right:0; height:2px; }
  .pc.flagship::before{background:linear-gradient(90deg,#f85149,#d29922)}
  .pc.saas::before{background:linear-gradient(90deg,#1f6feb,#3fb950)}
  .pc.ai::before{background:linear-gradient(90deg,#6e40c9,#58a6ff)}
  .pc.edu::before{background:linear-gradient(90deg,#3fb950,#1f6feb)}
  .pc.full::before{background:linear-gradient(90deg,#d29922,#f85149)}
  .pc.ui::before{background:linear-gradient(90deg,#58a6ff,#6e40c9)}
  .pc.startup::before{background:linear-gradient(90deg,#8b949e,#484f58)}
  .pc-head { display:flex; align-items:flex-start; justify-content:space-between; margin-bottom:6px; gap:8px; }
  .pc-title { font-size:13px; font-family:'Space Mono',monospace; color:#e6edf3; font-weight:700; }
  .pc-title a { color:#58a6ff; text-decoration:none; }
  .pc-title a:hover { text-decoration:underline; }
  .status { font-size:10px; padding:2px 8px; border-radius:20px; flex-shrink:0; display:flex; align-items:center; gap:4px; white-space:nowrap; }
  .status.live { background:#1a3a2a; border:1px solid #3fb950; color:#3fb950; }
  .status.dev { background:#2a2a1a; border:1px solid #d29922; color:#d29922; }
  .status.demo { background:#1a2a3a; border:1px solid #58a6ff; color:#58a6ff; }
  .live-dot { width:5px;height:5px;border-radius:50%;background:#3fb950;animation:pulse 1.5s infinite; }
  @keyframes pulse{0%,100%{opacity:1}50%{opacity:0.3}}
  .pc-cat { font-size:10px; color:#8b949e; margin-bottom:6px; }
  .pc-desc { font-size:11px; color:#7d8590; line-height:1.6; margin-bottom:8px; }
  .tech-tags { display:flex; flex-wrap:wrap; gap:5px; }
  .tag { font-size:10px; padding:2px 7px; border-radius:4px; border:1px solid #30363d; color:#8b949e; background:#0d1117; }
  .tag.php{border-color:#777bb3;color:#9b8eca}
  .tag.ai{border-color:#6e40c9;color:#a78bfa}
  .tag.js{border-color:#f7df1e;color:#c9a800}
  .tag.py{border-color:#3776ab;color:#58a6ff}
  .tag.mysql{border-color:#00758f;color:#29b5d3}
  .tag.html{border-color:#e34f26;color:#ef7b4f}
  .tag.css{border-color:#1572b6;color:#4ea5d9}
  .tag.api{border-color:#3fb950;color:#3fb950}
  .tag.pwa{border-color:#5a0fc8;color:#a78bfa}

  .tech-grid { display:flex; flex-wrap:wrap; gap:8px; margin-bottom:24px; }
  .tech-pill { background:#161b22; border:1px solid #30363d; border-radius:6px; padding:6px 14px; font-size:12px; color:#e6edf3; display:flex; align-items:center; gap:6px; }
  .tech-pill:hover{border-color:#58a6ff}
  .dot-s{width:7px;height:7px;border-radius:50%;flex-shrink:0}

  .connect-row { display:flex; flex-wrap:wrap; gap:10px; margin-bottom:20px; }
  .connect-btn { background:#21262d; border:1px solid #30363d; border-radius:6px; padding:8px 16px; font-size:12px; color:#e6edf3; font-family:'Fira Code',monospace; display:flex; align-items:center; gap:8px; text-decoration:none; }
  .connect-btn:hover{background:#30363d;border-color:#58a6ff;color:#58a6ff}

  .footer-line { font-size:11px; color:#484f58; text-align:center; padding-top:16px; border-top:1px solid #21262d; }
  .footer-line span{color:#3fb950}

  .copy-btn { position:absolute; top:12px; right:16px; background:#21262d; border:1px solid #30363d; color:#7d8590; font-size:11px; padding:4px 10px; border-radius:5px; cursor:pointer; font-family:'Fira Code',monospace; }
  .copy-btn:hover{background:#30363d;color:#e6edf3}

  @media(max-width:520px){.projects-grid,.stats-row{grid-template-columns:1fr}.hero{flex-direction:column;text-align:center}}
</style>

<div class="readme-wrap">
  <div class="tab-bar">
    <div class="dot r"></div><div class="dot y"></div><div class="dot g"></div>
    <span class="tab-label">README.md — Oshada Geethanjana</span>
  </div>
  <div class="readme-body">
    <button class="copy-btn" onclick="copyMd()">copy raw md</button>

    <div class="hero">
      <div class="avatar-ring">💻</div>
      <div class="hero-text">
        <h1>Hi, I'm <span>Oshada</span> 👋</h1>
        <div class="badges">
          <span class="badge-inline">Founder</span>
          <span class="badge-inline">AI Enthusiast</span>
          <span class="badge-inline">PHP Developer</span>
          <span class="badge-inline">Tech Explorer</span>
          <span class="badge-inline">IT Student @ SLIATE</span>
        </div>
      </div>
    </div>

    <div class="section-label">whoami</div>
    <div class="about-block">
      <div class="line"><span class="ico">▸</span><span>Building <span class="val"><a href="https://www.whitecoder.online">WhiteCoder</a></span> — full-service digital agency: web dev, UI/UX, and custom software.</span></div>
      <div class="line"><span class="ico b">▸</span><span>Founder of <span class="val"><a href="https://www.hndstudy.online">HND Study Hub</a></span> — free education for 6,000+ HND students in Sri Lanka.</span></div>
      <div class="line"><span class="ico a">▸</span><span>Shipped <span class="val">50+ projects</span> — AI tools, SaaS platforms, network tools, and more.</span></div>
      <div class="line"><span class="ico r">▸</span><span>IT Student @ <span class="val">SLIATE</span> · Obsessed with AI & smart application development.</span></div>
    </div>

    <div class="section-label">impact</div>
    <div class="stats-row">
      <div class="stat-card green"><div class="s-label">// projects built</div><div class="s-val">50+</div></div>
      <div class="stat-card blue"><div class="s-label">// users reached</div><div class="s-val">6K+</div></div>
      <div class="stat-card amber"><div class="s-label">// years building</div><div class="s-val">3+</div></div>
    </div>

    <div class="section-label">selected works</div>
    <div class="projects-grid">

      <div class="pc flagship">
        <div class="pc-head">
          <div class="pc-title"><a href="https://copilot.whitecoder.online/">WhiteCoder Copilot</a></div>
          <span class="status live"><span class="live-dot"></span>Live</span>
        </div>
        <div class="pc-cat">🤖 Flagship AI · Copilot</div>
        <div class="pc-desc">All-in-one AI assistant — code, content, ideas, automation. The core of the WhiteCoder ecosystem.</div>
        <div class="tech-tags"><span class="tag ai">AI</span><span class="tag js">JavaScript</span><span class="tag api">API</span></div>
      </div>

      <div class="pc saas">
        <div class="pc-head">
          <div class="pc-title"><a href="https://folio.whitecoder.online/">FOLIO by WhiteCoder</a></div>
          <span class="status live"><span class="live-dot"></span>Live</span>
        </div>
        <div class="pc-cat">⚡ SaaS Platform · Portfolio Builder</div>
        <div class="pc-desc">Modern SaaS portfolio builder with customizable themes, dashboards, and glass-style UI.</div>
        <div class="tech-tags"><span class="tag php">PHP</span><span class="tag mysql">MySQL</span><span class="tag css">CSS</span></div>
      </div>

      <div class="pc full">
        <div class="pc-head">
          <div class="pc-title"><a href="https://wcprobe.whitecoder.online/">WCProbe</a></div>
          <span class="status live"><span class="live-dot"></span>Live</span>
        </div>
        <div class="pc-cat">🔍 Network Tool · Cyber</div>
        <div class="pc-desc">Advanced IP & domain analysis — DNS, SSL, MX, reverse DNS, geo-location with dual DNS engines.</div>
        <div class="tech-tags"><span class="tag php">PHP</span><span class="tag api">API</span><span class="tag js">JavaScript</span></div>
      </div>

      <div class="pc saas">
        <div class="pc-head">
          <div class="pc-title"><a href="https://cinehub.whitecoder.online/">CineHub Pro</a></div>
          <span class="status live"><span class="live-dot"></span>Live</span>
        </div>
        <div class="pc-cat">🎬 Streaming Platform</div>
        <div class="pc-desc">Self-hosted movie & TV streaming platform with TMDB API, PWA support, and dark-mode UI.</div>
        <div class="tech-tags"><span class="tag php">PHP</span><span class="tag api">TMDB API</span><span class="tag pwa">PWA</span></div>
      </div>

      <div class="pc edu">
        <div class="pc-head">
          <div class="pc-title"><a href="https://www.hndstudy.online">HND Study Hub</a></div>
          <span class="status live"><span class="live-dot"></span>Live</span>
        </div>
        <div class="pc-cat">📚 EdTech · Founder Project</div>
        <div class="pc-desc">Free education portal serving 6,000+ HND students across Sri Lanka. Study materials & notes.</div>
        <div class="tech-tags"><span class="tag php">PHP</span><span class="tag html">HTML</span><span class="tag css">CSS</span></div>
      </div>

      <div class="pc ai">
        <div class="pc-head">
          <div class="pc-title"><a href="https://resumeiq.whitecoder.online/">ResumeIQ</a></div>
          <span class="status live"><span class="live-dot"></span>Live</span>
        </div>
        <div class="pc-cat">🤖 AI Tool · CV Analyzer</div>
        <div class="pc-desc">AI-powered resume analyzer — ATS suggestions, line-by-line evaluation, cover letter generator.</div>
        <div class="tech-tags"><span class="tag ai">AI</span><span class="tag js">JavaScript</span><span class="tag api">API</span></div>
      </div>

      <div class="pc ai">
        <div class="pc-head">
          <div class="pc-title"><a href="https://profileai.click/">ProfileAI</a></div>
          <span class="status live"><span class="live-dot"></span>Live</span>
        </div>
        <div class="pc-cat">🤖 AI Tool · Image Processing</div>
        <div class="pc-desc">Instant AI background remover — creates clean, professional profile pictures for social media & resumes.</div>
        <div class="tech-tags"><span class="tag ai">AI</span><span class="tag js">JavaScript</span></div>
      </div>

      <div class="pc ai">
        <div class="pc-head">
          <div class="pc-title"><a href="https://resume-ai-nine-phi.vercel.app/">Resume.AI</a></div>
          <span class="status live"><span class="live-dot"></span>Live</span>
        </div>
        <div class="pc-cat">🤖 AI Tool · Resume Builder</div>
        <div class="pc-desc">Modern AI resume builder — smart editing, clean UI, fully responsive for quick professional CVs.</div>
        <div class="tech-tags"><span class="tag ai">AI</span><span class="tag js">JavaScript</span></div>
      </div>

      <div class="pc full">
        <div class="pc-head">
          <div class="pc-title"><a href="https://www.whitecoder.online/demos/pos_system/">Smart POS System</a></div>
          <span class="status demo">Demo</span>
        </div>
        <div class="pc-cat">🛒 Full Stack · POS</div>
        <div class="pc-desc">Modern point-of-sale for shops — product management, barcode, real-time stock, fast billing.</div>
        <div class="tech-tags"><span class="tag php">PHP</span><span class="tag mysql">MySQL</span></div>
      </div>

      <div class="pc ui">
        <div class="pc-head">
          <div class="pc-title"><a href="https://www.whitecoder.online/demos/simple_interface_restaurant_webpage_01/">Restaurant Webpage</a></div>
          <span class="status demo">Demo</span>
        </div>
        <div class="pc-cat">🍽️ Web Template</div>
        <div class="pc-desc">Clean responsive restaurant website template — menus, services, contact. HTML/CSS/JS.</div>
        <div class="tech-tags"><span class="tag html">HTML</span><span class="tag css">CSS</span><span class="tag js">JS</span></div>
      </div>

      <div class="pc ui">
        <div class="pc-head">
          <div class="pc-title"><a href="https://www.whitecoder.online/demos/simple_creative_login_form_01/">Creative Login Form</a></div>
          <span class="status demo">Demo</span>
        </div>
        <div class="pc-cat">🎨 UI Component</div>
        <div class="pc-desc">Creative login form with smooth structure, clean UI design and fully responsive layout.</div>
        <div class="tech-tags"><span class="tag html">HTML</span><span class="tag css">CSS</span></div>
      </div>

      <div class="pc startup">
        <div class="pc-head">
          <div class="pc-title">BroCode Creations</div>
          <span class="status dev">In Dev</span>
        </div>
        <div class="pc-cat">🚀 Startup · Tech Hub</div>
        <div class="pc-desc">Modern digital solutions & tech hub focused on scalable innovations and creative development.</div>
        <div class="tech-tags"><span class="tag js">JavaScript</span><span class="tag api">Full Stack</span></div>
      </div>

    </div>

    <div class="section-label">tech stack</div>
    <div class="tech-grid">
      <div class="tech-pill"><span class="dot-s" style="background:#777bb3"></span>PHP</div>
      <div class="tech-pill"><span class="dot-s" style="background:#e34f26"></span>HTML5</div>
      <div class="tech-pill"><span class="dot-s" style="background:#1572b6"></span>CSS3</div>
      <div class="tech-pill"><span class="dot-s" style="background:#f7df1e"></span>JavaScript</div>
      <div class="tech-pill"><span class="dot-s" style="background:#3776ab"></span>Python</div>
      <div class="tech-pill"><span class="dot-s" style="background:#00758f"></span>MySQL</div>
      <div class="tech-pill"><span class="dot-s" style="background:#f24e1e"></span>Figma</div>
      <div class="tech-pill"><span class="dot-s" style="background:#0078d7"></span>VS Code</div>
      <div class="tech-pill"><span class="dot-s" style="background:#f05033"></span>Git</div>
    </div>

    <div class="section-label">connect</div>
    <div class="connect-row">
      <a class="connect-btn" href="https://www.whitecoder.online" target="_blank">🌐 whitecoder.online</a>
      <a class="connect-btn" href="https://www.hndstudy.online" target="_blank">📚 hndstudy.online</a>
      <a class="connect-btn" href="https://www.linkedin.com/in/oshanda-geethanjana-725574336/" target="_blank">💼 LinkedIn</a>
      <a class="connect-btn" href="https://github.com/oshandageethanjana" target="_blank">🐙 GitHub</a>
    </div>

    <div class="footer-line"><span>// 50+ projects shipped</span> · Negombo, Sri Lanka 🇱🇰 · 2025</div>
  </div>
</div>

<div id="raw" style="display:none">
# Hi there, I'm Oshada Geethanjana 👋

> *"Learning by doing — Code. Break. Rebuild. Repeat."*

**Founder · AI Enthusiast · PHP Developer · IT Student @ SLIATE**

---

### 🧭 whoami

- 🚀 Founder of **[WhiteCoder](https://www.whitecoder.online)** — full-service digital agency: web dev, UI/UX & custom software
- 📚 Founder of **[HND Study Hub](https://www.hndstudy.online)** — free education for 6,000+ HND students in Sri Lanka
- 📦 Shipped **50+ projects** — AI tools, SaaS platforms, network tools & more
- 🎓 IT Student at **SLIATE** · Obsessed with AI & smart application development
- 💡 Philosophy: *"Learning by doing."*

---

### 📊 Impact

| 🟢 Projects Built | 🔵 Users Reached | 🟡 Years Building |
|:---:|:---:|:---:|
| **50+** | **6K+** | **3+** |

---

### 🚀 Selected Works

#### 🤖 Flagship AI
| Project | Description | Stack | Status |
|---|---|---|---|
| [**WhiteCoder Copilot**](https://copilot.whitecoder.online/) | All-in-one AI assistant — code, content, ideas, automation | `AI` `JavaScript` `API` | 🟢 Live |

#### ⚡ SaaS & Platforms
| Project | Description | Stack | Status |
|---|---|---|---|
| [**FOLIO by WhiteCoder**](https://folio.whitecoder.online/) | Modern SaaS portfolio builder with dashboards & glass UI | `PHP` `MySQL` `CSS` | 🟢 Live |
| [**CineHub Pro**](https://cinehub.whitecoder.online/) | Self-hosted movie & TV streaming platform with TMDB API | `PHP` `TMDB API` `PWA` | 🟢 Live |
| [**WhiteCoder**](https://www.whitecoder.online) | Full-service digital infrastructure & web development agency | `PHP` `UI/UX` | 🟢 Live |

#### 🔍 Tools & Utilities
| Project | Description | Stack | Status |
|---|---|---|---|
| [**WCProbe**](https://wcprobe.whitecoder.online/) | Advanced IP & domain analysis — DNS, SSL, MX, geo-location | `PHP` `API` `JavaScript` | 🟢 Live |
| [**Smart POS System**](https://www.whitecoder.online/demos/pos_system/) | POS for shops — inventory, barcode, real-time stock, billing | `PHP` `MySQL` | 🔵 Demo |

#### 🤖 AI Tools
| Project | Description | Stack | Status |
|---|---|---|---|
| [**ResumeIQ**](https://resumeiq.whitecoder.online/) | AI resume analyzer — ATS suggestions & cover letter generator | `AI` `JavaScript` `API` | 🟢 Live |
| [**ProfileAI**](https://profileai.click/) | Instant AI background remover & professional profile maker | `AI` `JavaScript` | 🟢 Live |
| [**Resume.AI**](https://resume-ai-nine-phi.vercel.app/) | Modern AI resume builder — smart editing & clean UI | `AI` `JavaScript` | 🟢 Live |

#### 📚 EdTech
| Project | Description | Stack | Status |
|---|---|---|---|
| [**HND Study Hub**](https://www.hndstudy.online) | Free education portal for 6,000+ HND students in Sri Lanka | `PHP` `HTML` `CSS` | 🟢 Live |

#### 🎨 UI / Templates
| Project | Description | Stack | Status |
|---|---|---|---|
| [**Restaurant Webpage**](https://www.whitecoder.online/demos/simple_interface_restaurant_webpage_01/) | Clean responsive restaurant website template | `HTML` `CSS` `JS` | 🔵 Demo |
| [**Creative Login Form**](https://www.whitecoder.online/demos/simple_creative_login_form_01/) | Creative login UI with smooth structure & responsive layout | `HTML` `CSS` | 🔵 Demo |

#### 🚀 In Development
| Project | Description | Stack | Status |
|---|---|---|---|
| **BroCode Creations** | Modern digital solutions & tech hub — scalable innovations | `JavaScript` `Full Stack` | 🟡 In Dev |

---

### 🛠️ Tech Stack

![PHP](https://img.shields.io/badge/php-%23777BB4.svg?style=for-the-badge&logo=php&logoColor=white)
![HTML5](https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/css3-%231572B6.svg?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E)
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![MySQL](https://img.shields.io/badge/mysql-%2300f.svg?style=for-the-badge&logo=mysql&logoColor=white)
![Figma](https://img.shields.io/badge/figma-%23F24E1E.svg?style=for-the-badge&logo=figma&logoColor=white)
![VS Code](https://img.shields.io/badge/Visual%20Studio%20Code-0078d7.svg?style=for-the-badge&logo=visual-studio-code&logoColor=white)
![Git](https://img.shields.io/badge/git-%23F05033.svg?style=for-the-badge&logo=git&logoColor=white)

---

### 📊 GitHub Stats

![Oshada's GitHub Stats](https://github-readme-stats.vercel.app/api?username=oshandageethanjana&show_icons=true&theme=github_dark&hide_border=true&count_private=true)

![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=oshandageethanjana&layout=compact&theme=github_dark&hide_border=true)

---

### 📫 Connect with me

[![Website](https://img.shields.io/badge/WhiteCoder-0d1117?style=for-the-badge&logo=google-chrome&logoColor=3fb950)](https://www.whitecoder.online)
[![EdTech](https://img.shields.io/badge/HND%20Study%20Hub-0d1117?style=for-the-badge&logo=google-chrome&logoColor=58a6ff)](https://www.hndstudy.online)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/oshanda-geethanjana-725574336/)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/oshandageethanjana)

---

<p align="center"><i>// 50+ projects shipped · Negombo, Sri Lanka 🇱🇰</i></p>
</div>

<script>
function copyMd(){
  const t = document.getElementById('raw').innerText;
  navigator.clipboard.writeText(t).then(()=>{
    const b = document.querySelector('.copy-btn');
    b.textContent='✓ copied!';
    b.style.color='#3fb950';
    setTimeout(()=>{b.textContent='copy raw md';b.style.color='#7d8590';},2000);
  });
}
</script>

