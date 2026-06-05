<style>
  @keyframes scan {
    0% { top: 0; opacity: 0; }
    10% { opacity: 1; }
    90% { opacity: 1; }
    100% { top: 100%; opacity: 0; }
  }
  @keyframes cursor {
    0%, 100% { opacity: 1; }
    50% { opacity: 0; }
  }
  @keyframes pop {
    0% { opacity: 0; transform: scale(0.3) rotateX(90deg); }
    60% { opacity: 1; transform: scale(1.08) rotateX(0); }
    100% { opacity: 1; transform: scale(1) rotateX(0); }
  }
  @keyframes glow {
    0%, 100% { text-shadow: 0 0 8px rgba(220,20,60,0.4); }
    50% { text-shadow: 0 0 25px rgba(220,20,60,0.8), 0 0 50px rgba(220,20,60,0.3); }
  }
  @keyframes glitch {
    0%, 100% { clip-path: inset(0 0 0 0); }
    5% { clip-path: inset(20% 0 60% 0); }
    10% { clip-path: inset(40% 0 30% 0); }
    15% { clip-path: inset(10% 0 70% 0); }
    20% { clip-path: inset(0 0 0 0); }
  }
  @keyframes progress {
    0% { width: 0%; }
    100% { width: 100%; }
  }
  @keyframes shimmer {
    0% { background-position: -200% 0; }
    100% { background-position: 200% 0; }
  }
  @keyframes flicker {
    0%, 100% { opacity: 1; }
    3% { opacity: 0.8; }
    6% { opacity: 1; }
    7% { opacity: 0.9; }
    10% { opacity: 1; }
    76% { opacity: 1; }
    78% { opacity: 0.85; }
    80% { opacity: 1; }
  }
  @keyframes hex-float {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-3px); }
  }
  @keyframes bin-scroll {
    0% { background-position: 0 0; }
    100% { background-position: 0 40px; }
  }
  @keyframes reveal {
    0% { opacity: 0; transform: translateY(20px); }
    100% { opacity: 1; transform: translateY(0); }
  }

  .decoder {
    background: #050505;
    border: 1px solid #1a1a1a;
    padding: 28px 20px 20px;
    margin: 16px auto;
    font-family: 'Courier New', monospace;
    position: relative;
    overflow: hidden;
    max-width: 720px;
  }
  .decoder::before {
    content: '';
    position: absolute;
    left: 0;
    width: 100%;
    height: 2px;
    background: linear-gradient(90deg, transparent, rgba(220,20,60,0.5), transparent);
    pointer-events: none;
    animation: scan 4s ease-in-out infinite;
  }
  .decoder .corner { position: absolute; width: 12px; height: 12px; border-color: #dc143c; border-style: solid; }
  .decoder .tl { top: -1px; left: -1px; border-width: 2px 0 0 2px; }
  .decoder .tr { top: -1px; right: -1px; border-width: 2px 2px 0 0; }
  .decoder .bl { bottom: -1px; left: -1px; border-width: 0 0 2px 2px; }
  .decoder .br { bottom: -1px; right: -1px; border-width: 0 2px 2px 0; }

  .decoder .label {
    font-size: 9px;
    color: #444;
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 14px;
    text-align: center;
  }
  .decoder .label span { color: #dc143c; }

  .decode-row {
    display: flex;
    justify-content: center;
    gap: 8px;
    flex-wrap: wrap;
  }
  .decode-cell {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 8px 14px;
    background: #080808;
    border: 1px solid #1a1a1a;
    min-width: 70px;
    opacity: 0;
    animation: pop 0.6s ease-out forwards;
  }
  .decode-cell:nth-child(1) { animation-delay: 0.3s; }
  .decode-cell:nth-child(2) { animation-delay: 0.5s; }
  .decode-cell:nth-child(3) { animation-delay: 0.7s; }
  .decode-cell:nth-child(4) { animation-delay: 0.9s; }
  .decode-cell:nth-child(5) { animation-delay: 1.1s; }
  .decode-cell:nth-child(6) { animation-delay: 1.3s; }

  .decode-cell .hex {
    font-size: 11px;
    color: #555;
    letter-spacing: 1px;
    margin-bottom: 2px;
  }
  .decode-cell .arrow {
    font-size: 9px;
    color: #dc143c;
    margin: 1px 0;
    animation: hex-float 2s ease-in-out infinite;
  }
  .decode-cell .letter {
    font-size: 32px;
    font-weight: 900;
    color: #dc143c;
    letter-spacing: 2px;
    animation: glow 2s ease-in-out infinite, flicker 5s ease-in-out infinite;
  }

  .status-row {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-top: 16px;
    gap: 12px;
    opacity: 0;
    animation: reveal 0.5s ease-out 2s forwards;
  }
  .status-row .stat {
    font-size: 9px;
    color: #444;
    letter-spacing: 2px;
    text-transform: uppercase;
  }
  .status-row .stat span { color: #dc143c; }
  .bar-wrap {
    flex: 1;
    height: 2px;
    background: #111;
    overflow: hidden;
  }
  .bar-wrap .bar {
    height: 100%;
    width: 0%;
    background: linear-gradient(90deg, #dc143c, #ff1468, #dc143c);
    background-size: 200% 100%;
    animation: progress 2.5s ease-out 0.5s forwards, shimmer 1.5s linear infinite;
  }

  .label-top {
    text-align: center;
    font-family: 'Courier New', monospace;
    font-size: 10px;
    color: #444;
    letter-spacing: 2px;
    margin-bottom: 6px;
    opacity: 0;
    animation: reveal 0.4s ease-out 0.1s forwards;
  }

  .section {
    margin: 20px 0;
    font-family: 'Courier New', monospace;
  }
  .section-header {
    color: #555;
    font-size: 10px;
    letter-spacing: 1px;
    margin-bottom: 6px;
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .section-header .addr {
    color: #dc143c;
    font-size: 10px;
    min-width: 52px;
  }
  .section-header .sep {
    color: #2a2a2a;
  }
  .section-header .name {
    color: #888;
    letter-spacing: 2px;
  }
  .section-header .glitch {
    display: inline-block;
    animation: glitch 8s ease-in-out infinite;
  }

  .term-box {
    background: #050505;
    border: 1px solid #1a1a1a;
    padding: 14px 18px;
    font-size: 12px;
    line-height: 1.8;
    color: #666;
    position: relative;
    overflow: hidden;
    transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
    transform-style: preserve-3d;
  }
  .term-box:hover {
    transform: perspective(1000px) rotateX(1.5deg) rotateY(-1.5deg) translateZ(8px);
    border-color: #dc143c;
    box-shadow: 0 8px 30px rgba(220,20,60,0.1), -4px 4px 15px rgba(220,20,60,0.05);
  }
  .term-box .key { color: #dc143c; }
  .term-box .str { color: #ce9178; }
  .term-box .val { color: #888; }
  .term-box .type { color: #569cd6; }

  .stats-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    justify-content: center;
  }
  .stat-card {
    background: #050505;
    border: 1px solid #1a1a1a;
    min-width: 280px;
    flex: 1;
    transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
    transform-style: preserve-3d;
  }
  .stat-card:hover {
    transform: perspective(1000px) rotateY(3deg) translateZ(12px) scale(1.02);
    filter: brightness(1.1);
  }
  .stat-card img { width: 100%; display: block; }

  .project-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 8px;
  }
  .project-card {
    background: #050505;
    border: 1px solid #1a1a1a;
    padding: 12px 14px;
    text-decoration: none;
    color: #e0e0e0;
    transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
    display: flex;
    flex-direction: column;
    gap: 4px;
    transform-style: preserve-3d;
    position: relative;
    overflow: hidden;
  }
  .project-card::before {
    content: '';
    position: absolute;
    left: 0;
    top: 0;
    width: 3px;
    height: 100%;
    background: #1a1a1a;
    transition: background 0.3s;
  }
  .project-card:hover::before { background: #dc143c; }
  .project-card:hover {
    transform: perspective(1000px) rotateY(2deg) translateZ(10px) scale(1.01);
    border-color: #dc143c;
  }
  .project-card .name {
    color: #dc143c;
    font-size: 12px;
    font-weight: 700;
    letter-spacing: 0.5px;
  }
  .project-card .desc { color: #666; font-size: 11px; line-height: 1.4; }
  .project-card .meta { display: flex; gap: 10px; font-size: 10px; color: #444; margin-top: 2px; }
  .project-card .meta span { display: flex; align-items: center; gap: 3px; }
  .project-card .lang-dot { width: 7px; height: 7px; border-radius: 50%; display: inline-block; }

  .badges {
    display: flex;
    flex-wrap: wrap;
    gap: 5px;
    justify-content: center;
  }
  .badge {
    display: inline-block;
    padding: 5px 12px;
    font-size: 9px;
    font-weight: 700;
    letter-spacing: 1px;
    text-transform: uppercase;
    text-decoration: none;
    border: 1px solid;
    transition: all 0.3s ease;
    transform-style: preserve-3d;
  }
  .badge:hover { transform: perspective(500px) translateZ(6px) scale(1.04); }
  .badge-p { background: transparent; color: #dc143c; border-color: #dc143c; }
  .badge-p:hover { background: #dc143c; color: #000; }
  .badge-m { background: transparent; color: #666; border-color: #333; cursor: default; }
  .badge-g { background: transparent; color: #00c853; border-color: #00c853; }

  .footer-q {
    color: #444;
    font-style: italic;
    font-size: 12px;
    padding: 10px 14px;
    border-left: 2px solid #dc143c;
    background: #050505;
    font-family: 'Courier New', monospace;
  }
</style>

<div align="center">

<div class="label-top">// REVERSE_ENGINEERING //</div>

<div class="decoder">
  <div class="corner tl"></div>
  <div class="corner tr"></div>
  <div class="corner bl"></div>
  <div class="corner br"></div>
  <div class="label">decoding <span>identity</span></div>

  <div class="decode-row">
    <div class="decode-cell"><div class="hex">0x45</div><div class="arrow">▼</div><div class="letter">E</div></div>
    <div class="decode-cell"><div class="hex">0x54</div><div class="arrow">▼</div><div class="letter">T</div></div>
    <div class="decode-cell"><div class="hex">0x52</div><div class="arrow">▼</div><div class="letter">R</div></div>
    <div class="decode-cell"><div class="hex">0x4E</div><div class="arrow">▼</div><div class="letter">N</div></div>
    <div class="decode-cell"><div class="hex">0x4B</div><div class="arrow">▼</div><div class="letter">K</div></div>
    <div class="decode-cell"><div class="hex">0x5A</div><div class="arrow">▼</div><div class="letter">Z</div></div>
  </div>

  <div class="status-row">
    <div class="stat">DECODING</div>
    <div class="bar-wrap"><div class="bar"></div></div>
    <div class="stat"><span>0x</span>100%</div>
  </div>
</div>

<div style="margin:4px 0 10px;opacity:0;animation:reveal 0.5s ease-out 2.2s forwards">
  <span style="color:#888;font-size:12px;letter-spacing:1px;font-family:'Courier New',monospace">
    // reverse.engineer  |  bot_eng  |  eth/goba
  </span>
</div>

<div style="opacity:0;animation:reveal 0.5s ease-out 2.4s forwards">
  <div class="badges">
    <a class="badge badge-p" href="https://etrnkz.vercel.app">PORTFOLIO</a>
    <a class="badge badge-p" href="https://t.me/etrnkz">TELEGRAM</a>
    <a class="badge badge-p" href="https://linkedin.com/in/etrnkz">LINKEDIN</a>
    <a class="badge badge-p" href="https://github.com/etrnkz">GITHUB</a>
    <span class="badge badge-g">STATUS: AVAILABLE_FOR_WORK</span>
  </div>
</div>

</div>

<br/>

<div class="section">
  <div class="section-header">
    <span class="addr">0x0000</span>
    <span class="sep">│</span>
    <span class="name">whoami</span>
  </div>
  <div class="term-box">
    <span class="type">class</span> <span class="key">ETRNKZ</span>:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;<span class="key">name</span> = <span class="str">"Etrnkz"</span><br>
    &nbsp;&nbsp;&nbsp;&nbsp;<span class="key">roles</span> = [<span class="str">"Reverse Engineer"</span>, <span class="str">"Backend Developer"</span>]<br>
    &nbsp;&nbsp;&nbsp;&nbsp;<span class="key">locale</span> = <span class="str">"Ethiopia / Goba"</span><br>
    <br>
    &nbsp;&nbsp;&nbsp;&nbsp;<span class="key">specialization</span> = {<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="str">"core"</span>:  [<span class="val">"Task Automation"</span>, <span class="val">"Bot Engineering"</span>, <span class="val">"API Wrapping"</span>],<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="str">"lang"</span>:  [<span class="val">"Python"</span>, <span class="val">"JavaScript"</span>, <span class="val">"TypeScript"</span>, <span class="val">"Rust"</span>, <span class="val">"Prolog"</span>],<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="str">"stack"</span>: [<span class="val">"Node.js"</span>, <span class="val">"Docker"</span>, <span class="val">"PostgreSQL"</span>, <span class="val">"Telegram API"</span>],<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="str">"focus"</span>: [<span class="val">"Reverse Engineering"</span>, <span class="val">"Security Research"</span>, <span class="val">"Unofficial APIs"</span>],<br>
    &nbsp;&nbsp;&nbsp;&nbsp;}<br>
    <br>
    &nbsp;&nbsp;&nbsp;&nbsp;<span class="key">def</span> <span style="color:#dcdcaa">status</span>(<span class="key">self</span>):<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="key">return</span> <span class="str">"Available for work — DM on Telegram"</span>
  </div>
</div>

<div class="section">
  <div class="section-header">
    <span class="addr">0x0010</span>
    <span class="sep">│</span>
    <span class="name">3D contribution</span>
  </div>
  <div class="term-box" style="text-align:center;padding:20px">
    <img src="https://isometric-contributions-spectrewolf8.onrender.com/api/graph?username=etrnkz&theme=dark&stats=true&credit=false" alt="3D Contributions" width="100%" style="border:1px solid #1a1a1a" />
  </div>
</div>

<div class="section">
  <div class="section-header">
    <span class="addr">0x0020</span>
    <span class="sep">│</span>
    <span class="name">github analytics</span>
  </div>
  <div class="stats-grid">
    <div class="stat-card"><img src="https://github-readme-stats.vercel.app/api?username=etrnkz&show_icons=true&theme=dark&bg_color=0a0a0a&border_color=dc143c&border_radius=0&title_color=dc143c&icon_color=dc143c&text_color=888&hide_border=true&count_private=true" alt="Stats" /></div>
    <div class="stat-card"><img src="https://github-readme-stats.vercel.app/api/top-langs/?username=etrnkz&layout=compact&theme=dark&bg_color=0a0a0a&border_color=dc143c&border_radius=0&title_color=dc143c&text_color=888&hide_border=true" alt="Languages" /></div>
  </div>
  <div class="stat-card" style="width:100%;margin-top:8px"><img src="https://github-readme-activity-graph.vercel.app/graph?username=etrnkz&bg_color=0a0a0a&color=dc143c&line=dc143c&point=fff&area=true&area_color=dc143c20&border_color=dc143c&title_color=dc143c&hide_border=true" alt="Activity" /></div>
</div>

<div class="section">
  <div class="section-header">
    <span class="addr">0x0030</span>
    <span class="sep">│</span>
    <span class="name">tech stack</span>
  </div>
  <div class="badges">
    <span class="badge badge-p">PYTHON</span>
    <span class="badge badge-p">JAVASCRIPT</span>
    <span class="badge badge-p">TYPESCRIPT</span>
    <span class="badge badge-p">RUST</span>
    <span class="badge badge-p">NODE.JS</span>
    <span class="badge badge-p">PROLOG</span>
    <span class="badge badge-p">DOCKER</span>
    <span class="badge badge-p">POSTGRESQL</span>
  </div>
</div>

<div class="section">
  <div class="section-header">
    <span class="addr">0x0040</span>
    <span class="sep">│</span>
    <span class="name glitch">featured projects</span>
  </div>
  <div class="project-grid">
    <a class="project-card" href="https://github.com/etrnkz/chatgpt-unofficial-api">
      <div class="name">chatgpt-unofficial-api</div>
      <div class="desc">Unofficial Node.js client for ChatGPT. No login required for chat.</div>
      <div class="meta"><span><span class="lang-dot" style="background:#f1e05a"></span> JavaScript</span><span>★ 1</span></div>
    </a>
    <a class="project-card" href="https://github.com/etrnkz/gemini-unofficial-api">
      <div class="name">gemini-unofficial-api</div>
      <div class="desc">Reverse-engineered Node.js client for Google Gemini.</div>
      <div class="meta"><span><span class="lang-dot" style="background:#f1e05a"></span> JavaScript</span><span>★ 1</span></div>
    </a>
    <a class="project-card" href="https://github.com/etrnkz/NullCrypt">
      <div class="name">NullCrypt</div>
      <div class="desc">Encryption tool built in Rust</div>
      <div class="meta"><span><span class="lang-dot" style="background:#dea584"></span> Rust</span><span>★ 1</span></div>
    </a>
    <a class="project-card" href="https://github.com/etrnkz/black-box-unoffcial-api">
      <div class="name">black-box-unofficial-api</div>
      <div class="desc">Unofficial API client for Blackbox AI</div>
      <div class="meta"><span><span class="lang-dot" style="background:#3572A5"></span> Python</span><span>★ 1</span></div>
    </a>
    <a class="project-card" href="https://github.com/etrnkz/fancy-Agent">
      <div class="name">fancy-Agent</div>
      <div class="desc">AI agent framework</div>
      <div class="meta"><span><span class="lang-dot" style="background:#3572A5"></span> Python</span><span>★ 1</span></div>
    </a>
    <a class="project-card" href="https://github.com/etrnkz/freeDogs">
      <div class="name">freeDogs</div>
      <div class="desc">Telegram clicker automation bot</div>
      <div class="meta"><span><span class="lang-dot" style="background:#3572A5"></span> Python</span><span>★ 3</span></div>
    </a>
  </div>
</div>

<div class="section">
  <div class="section-header">
    <span class="addr">0x0050</span>
    <span class="sep">│</span>
    <span class="name">recent activity</span>
  </div>
  <!--RECENT_ACTIVITY_START-->
  <div class="term-box" style="text-align:center;color:#444;padding:16px">> fetching latest activity...</div>
  <!--RECENT_ACTIVITY_END-->
</div>

<br/>

<div align="center">

  <div style="font-size:13px;color:#888;font-family:'Courier New',monospace;margin-bottom:12px;letter-spacing:1px">
    &nbsp;&nbsp;`$ <span style="color:#dc143c">Let's build something.</span>`
  </div>

  <div class="badges">
    <a class="badge badge-p" href="https://t.me/etrnkz">DM ON TELEGRAM</a>
    <a class="badge badge-p" href="mailto:">EMAIL</a>
    <span class="badge badge-m">VISITORS: --</span>
  </div>

  <br/>

  <div class="footer-q">
    "I don't break things — I understand how they work."
  </div>

  <br/>

  <div style="font-size:9px;color:#333;font-family:'Courier New',monospace;letter-spacing:1px">
    [ process exited with code 0x0 ]
  </div>

</div>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:1a0000,50:111111,100:0a0a0a&height=100&section=footer&reversal=false" width="100%"/>
