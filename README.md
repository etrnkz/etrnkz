<div align="center">

<!-- Decoder SVG — self-contained animation, safe from GitHub style sanitizer -->
<svg viewBox="0 0 640 200" width="100%" style="max-width:660px" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <style>
      @keyframes scan { 0%{opacity:0;transform:translateY(0)}10%{opacity:1}90%{opacity:1}100%{opacity:0;transform:translateY(160px)} }
      @keyframes pop { 0%{opacity:0;transform:scale(.3)}60%{opacity:1;transform:scale(1.08)}100%{opacity:1;transform:scale(1)} }
      @keyframes glow { 0%,100%{opacity:.6}50%{opacity:1} }
      @keyframes float { 0%,100%{transform:translateY(0)}50%{transform:translateY(-2px)} }
      @keyframes fill { 0%{width:0}100%{width:100%} }
      @keyframes shimmer { 0%{transform:translateX(-100%)}100%{transform:translateX(200%)} }
      .scanline { animation:scan 4s ease-in-out infinite }
      .c1 { animation:pop .5s ease-out .2s both }
      .c2 { animation:pop .5s ease-out .4s both }
      .c3 { animation:pop .5s ease-out .6s both }
      .c4 { animation:pop .5s ease-out .8s both }
      .c5 { animation:pop .5s ease-out 1s both }
      .c6 { animation:pop .5s ease-out 1.2s both }
      .arrow { animation:float 2s ease-in-out infinite }
      .glow { animation:glow 2s ease-in-out infinite }
      .bar-fill { animation:fill 2.5s ease-out .5s both }
      .bar-shimmer { animation:shimmer 1.5s linear infinite }
    </style>
  </defs>

  <!-- Background -->
  <rect x="0" y="0" width="640" height="198" fill="#050505" rx="0" stroke="#1a1a1a" stroke-width="1"/>

  <!-- Corner decorations -->
  <path d="M0,0 h15 M0,0 v15" stroke="#dc143c" stroke-width="2" fill="none"/>
  <path d="M640,0 h-15 M640,0 v15" stroke="#dc143c" stroke-width="2" fill="none"/>
  <path d="M0,198 h15 M0,198 v-15" stroke="#dc143c" stroke-width="2" fill="none"/>
  <path d="M640,198 h-15 M640,198 v-15" stroke="#dc143c" stroke-width="2" fill="none"/>

  <!-- Label -->
  <text x="320" y="30" text-anchor="middle" font-family="'Courier New',monospace" font-size="9" fill="#444" letter-spacing="3">
    decoding <tspan fill="#dc143c">identity</tspan>
  </text>

  <!-- Scan line -->
  <line class="scanline" x1="0" y1="0" x2="640" y2="0" stroke="rgba(220,20,60,.4)" stroke-width="1.5"/>

  <!-- Cells -->
  <!-- 0x45 → E -->
  <g class="c1">
    <rect x="50" y="52" width="70" height="82" fill="#080808" stroke="#1a1a1a" stroke-width="1"/>
    <text x="85" y="75" text-anchor="middle" font-family="'Courier New',monospace" font-size="11" fill="#555">0x45</text>
    <text class="arrow" x="85" y="90" text-anchor="middle" font-family="monospace" font-size="9" fill="#dc143c">▼</text>
    <text class="glow" x="85" y="122" text-anchor="middle" font-family="'Courier New',monospace" font-size="32" font-weight="900" fill="#dc143c">E</text>
  </g>

  <!-- 0x54 → T -->
  <g class="c2">
    <rect x="128" y="52" width="70" height="82" fill="#080808" stroke="#1a1a1a" stroke-width="1"/>
    <text x="163" y="75" text-anchor="middle" font-family="'Courier New',monospace" font-size="11" fill="#555">0x54</text>
    <text class="arrow" x="163" y="90" text-anchor="middle" font-family="monospace" font-size="9" fill="#dc143c">▼</text>
    <text class="glow" x="163" y="122" text-anchor="middle" font-family="'Courier New',monospace" font-size="32" font-weight="900" fill="#dc143c">T</text>
  </g>

  <!-- 0x52 → R -->
  <g class="c3">
    <rect x="206" y="52" width="70" height="82" fill="#080808" stroke="#1a1a1a" stroke-width="1"/>
    <text x="241" y="75" text-anchor="middle" font-family="'Courier New',monospace" font-size="11" fill="#555">0x52</text>
    <text class="arrow" x="241" y="90" text-anchor="middle" font-family="monospace" font-size="9" fill="#dc143c">▼</text>
    <text class="glow" x="241" y="122" text-anchor="middle" font-family="'Courier New',monospace" font-size="32" font-weight="900" fill="#dc143c">R</text>
  </g>

  <!-- 0x4E → N -->
  <g class="c4">
    <rect x="284" y="52" width="70" height="82" fill="#080808" stroke="#1a1a1a" stroke-width="1"/>
    <text x="319" y="75" text-anchor="middle" font-family="'Courier New',monospace" font-size="11" fill="#555">0x4E</text>
    <text class="arrow" x="319" y="90" text-anchor="middle" font-family="monospace" font-size="9" fill="#dc143c">▼</text>
    <text class="glow" x="319" y="122" text-anchor="middle" font-family="'Courier New',monospace" font-size="32" font-weight="900" fill="#dc143c">N</text>
  </g>

  <!-- 0x4B → K -->
  <g class="c5">
    <rect x="362" y="52" width="70" height="82" fill="#080808" stroke="#1a1a1a" stroke-width="1"/>
    <text x="397" y="75" text-anchor="middle" font-family="'Courier New',monospace" font-size="11" fill="#555">0x4B</text>
    <text class="arrow" x="397" y="90" text-anchor="middle" font-family="monospace" font-size="9" fill="#dc143c">▼</text>
    <text class="glow" x="397" y="122" text-anchor="middle" font-family="'Courier New',monospace" font-size="32" font-weight="900" fill="#dc143c">K</text>
  </g>

  <!-- 0x5A → Z -->
  <g class="c6">
    <rect x="440" y="52" width="70" height="82" fill="#080808" stroke="#1a1a1a" stroke-width="1"/>
    <text x="475" y="75" text-anchor="middle" font-family="'Courier New',monospace" font-size="11" fill="#555">0x5A</text>
    <text class="arrow" x="475" y="90" text-anchor="middle" font-family="monospace" font-size="9" fill="#dc143c">▼</text>
    <text class="glow" x="475" y="122" text-anchor="middle" font-family="'Courier New',monospace" font-size="32" font-weight="900" fill="#dc143c">Z</text>
  </g>

  <!-- Status row -->
  <text x="20" y="170" font-family="'Courier New',monospace" font-size="9" fill="#444" letter-spacing="2">DECODING</text>
  <text x="620" y="170" text-anchor="end" font-family="'Courier New',monospace" font-size="9" fill="#444" letter-spacing="2">
    <tspan fill="#dc143c">0x</tspan>100%
  </text>

  <!-- Progress bar background -->
  <rect x="100" y="164" width="420" height="2" fill="#111"/>
  <!-- Progress bar fill -->
  <rect class="bar-fill" x="100" y="164" width="420" height="2" fill="#dc143c"/>
  <!-- Progress bar shimmer -->
  <rect class="bar-shimmer" x="100" y="164" width="100" height="2" fill="rgba(255,255,255,.15)"/>
</svg>

<br/>

<span style="color:#888;font-size:12px;letter-spacing:1px;font-family:'Courier New',monospace">
  // reverse.engineer  |  bot_eng  |  eth/goba
</span>

<br/><br/>

<!-- Social badges — inline styles, no class dependencies -->
<div>
  <a href="https://etrnkz.vercel.app">
    <span style="display:inline-block;padding:5px 12px;font-size:9px;font-weight:700;letter-spacing:1px;text-transform:uppercase;border:1px solid #dc143c;color:#dc143c;background:transparent;text-decoration:none;margin:2px">PORTFOLIO</span>
  </a>
  <a href="https://t.me/etrnkz">
    <span style="display:inline-block;padding:5px 12px;font-size:9px;font-weight:700;letter-spacing:1px;text-transform:uppercase;border:1px solid #dc143c;color:#dc143c;background:transparent;text-decoration:none;margin:2px">TELEGRAM</span>
  </a>
  <a href="https://linkedin.com/in/etrnkz">
    <span style="display:inline-block;padding:5px 12px;font-size:9px;font-weight:700;letter-spacing:1px;text-transform:uppercase;border:1px solid #dc143c;color:#dc143c;background:transparent;text-decoration:none;margin:2px">LINKEDIN</span>
  </a>
  <a href="https://github.com/etrnkz">
    <span style="display:inline-block;padding:5px 12px;font-size:9px;font-weight:700;letter-spacing:1px;text-transform:uppercase;border:1px solid #dc143c;color:#dc143c;background:transparent;text-decoration:none;margin:2px">GITHUB</span>
  </a>
  <span style="display:inline-block;padding:5px 12px;font-size:9px;font-weight:700;letter-spacing:1px;text-transform:uppercase;border:1px solid #00c853;color:#00c853;background:transparent;margin:2px">STATUS: AVAILABLE_FOR_WORK</span>
</div>

</div>

<br/>

<!-- 0x0000 | whoami -->
<div style="margin:20px 0;font-family:'Courier New',monospace">
  <div style="color:#555;font-size:10px;letter-spacing:1px;margin-bottom:6px;display:flex;align-items:center;gap:8px">
    <span style="color:#dc143c;font-size:10px;min-width:52px">0x0000</span>
    <span style="color:#2a2a2a">│</span>
    <span style="color:#888;letter-spacing:2px">whoami</span>
  </div>
  <div style="background:#050505;border:1px solid #1a1a1a;padding:14px 18px;font-size:12px;line-height:1.8;color:#666">
    <span style="color:#569cd6">class</span> <span style="color:#dc143c;font-weight:700">ETRNKZ</span>:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#dc143c">name</span> = <span style="color:#ce9178">"Etrnkz"</span><br>
    &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#dc143c">roles</span> = [<span style="color:#ce9178">"Reverse Engineer"</span>, <span style="color:#ce9178">"Backend Developer"</span>]<br>
    &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#dc143c">locale</span> = <span style="color:#ce9178">"Ethiopia / Goba"</span><br>
    <br>
    &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#dc143c">specialization</span> = {<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#ce9178">"core"</span>:  [<span style="color:#888">"Task Automation"</span>, <span style="color:#888">"Bot Engineering"</span>, <span style="color:#888">"API Wrapping"</span>],<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#ce9178">"lang"</span>:  [<span style="color:#888">"Python"</span>, <span style="color:#888">"JavaScript"</span>, <span style="color:#888">"TypeScript"</span>, <span style="color:#888">"Rust"</span>, <span style="color:#888">"Prolog"</span>],<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#ce9178">"stack"</span>: [<span style="color:#888">"Node.js"</span>, <span style="color:#888">"Docker"</span>, <span style="color:#888">"PostgreSQL"</span>, <span style="color:#888">"Telegram API"</span>],<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#ce9178">"focus"</span>: [<span style="color:#888">"Reverse Engineering"</span>, <span style="color:#888">"Security Research"</span>, <span style="color:#888">"Unofficial APIs"</span>],<br>
    &nbsp;&nbsp;&nbsp;&nbsp;}<br>
    <br>
    &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#dc143c">def</span> <span style="color:#dcdcaa">status</span>(<span style="color:#dc143c">self</span>):<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#dc143c">return</span> <span style="color:#ce9178">"Available for work — DM on Telegram"</span>
  </div>
</div>

<!-- 0x0010 | 3D contribution -->
<div style="margin:20px 0;font-family:'Courier New',monospace">
  <div style="color:#555;font-size:10px;letter-spacing:1px;margin-bottom:6px;display:flex;align-items:center;gap:8px">
    <span style="color:#dc143c;font-size:10px;min-width:52px">0x0010</span>
    <span style="color:#2a2a2a">│</span>
    <span style="color:#888;letter-spacing:2px">3D contribution</span>
  </div>
  <div style="background:#050505;border:1px solid #1a1a1a;padding:20px;text-align:center">
    <img src="https://github-readme-activity-graph.vercel.app/graph?username=etrnkz&bg_color=0a0a0a&color=dc143c&line=dc143c&point=fff&area=true&area_color=dc143c20&border_color=dc143c&title_color=dc143c&hide_border=true" alt="Activity Graph" width="100%" style="max-width:700px;border:1px solid #1a1a1a"/>
  </div>
</div>

<!-- 0x0020 | github analytics -->
<div style="margin:20px 0;font-family:'Courier New',monospace">
  <div style="color:#555;font-size:10px;letter-spacing:1px;margin-bottom:6px;display:flex;align-items:center;gap:8px">
    <span style="color:#dc143c;font-size:10px;min-width:52px">0x0020</span>
    <span style="color:#2a2a2a">│</span>
    <span style="color:#888;letter-spacing:2px">github analytics</span>
  </div>
  <table>
    <tr>
      <td style="padding:2px;vertical-align:top">
        <img src="https://github-readme-stats.vercel.app/api?username=etrnkz&show_icons=true&theme=dark&bg_color=0a0a0a&border_color=dc143c&border_radius=0&title_color=dc143c&icon_color=dc143c&text_color=888&hide_border=true&count_private=true" alt="Stats"/>
      </td>
      <td style="padding:2px;vertical-align:top">
        <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=etrnkz&layout=compact&theme=dark&bg_color=0a0a0a&border_color=dc143c&border_radius=0&title_color=dc143c&text_color=888&hide_border=true" alt="Languages"/>
      </td>
    </tr>
  </table>
</div>

<!-- 0x0030 | tech stack -->
<div style="margin:20px 0;font-family:'Courier New',monospace">
  <div style="color:#555;font-size:10px;letter-spacing:1px;margin-bottom:6px;display:flex;align-items:center;gap:8px">
    <span style="color:#dc143c;font-size:10px;min-width:52px">0x0030</span>
    <span style="color:#2a2a2a">│</span>
    <span style="color:#888;letter-spacing:2px">tech stack</span>
  </div>
  <div>
    <span style="display:inline-block;padding:5px 12px;font-size:9px;font-weight:700;letter-spacing:1px;text-transform:uppercase;border:1px solid #dc143c;color:#dc143c;margin:2px">PYTHON</span>
    <span style="display:inline-block;padding:5px 12px;font-size:9px;font-weight:700;letter-spacing:1px;text-transform:uppercase;border:1px solid #dc143c;color:#dc143c;margin:2px">JAVASCRIPT</span>
    <span style="display:inline-block;padding:5px 12px;font-size:9px;font-weight:700;letter-spacing:1px;text-transform:uppercase;border:1px solid #dc143c;color:#dc143c;margin:2px">TYPESCRIPT</span>
    <span style="display:inline-block;padding:5px 12px;font-size:9px;font-weight:700;letter-spacing:1px;text-transform:uppercase;border:1px solid #dc143c;color:#dc143c;margin:2px">RUST</span>
    <span style="display:inline-block;padding:5px 12px;font-size:9px;font-weight:700;letter-spacing:1px;text-transform:uppercase;border:1px solid #dc143c;color:#dc143c;margin:2px">NODE.JS</span>
    <span style="display:inline-block;padding:5px 12px;font-size:9px;font-weight:700;letter-spacing:1px;text-transform:uppercase;border:1px solid #dc143c;color:#dc143c;margin:2px">PROLOG</span>
    <span style="display:inline-block;padding:5px 12px;font-size:9px;font-weight:700;letter-spacing:1px;text-transform:uppercase;border:1px solid #dc143c;color:#dc143c;margin:2px">DOCKER</span>
    <span style="display:inline-block;padding:5px 12px;font-size:9px;font-weight:700;letter-spacing:1px;text-transform:uppercase;border:1px solid #dc143c;color:#dc143c;margin:2px">POSTGRESQL</span>
  </div>
</div>

<!-- 0x0040 | featured projects -->
<div style="margin:20px 0;font-family:'Courier New',monospace">
  <div style="color:#555;font-size:10px;letter-spacing:1px;margin-bottom:6px;display:flex;align-items:center;gap:8px">
    <span style="color:#dc143c;font-size:10px;min-width:52px">0x0040</span>
    <span style="color:#2a2a2a">│</span>
    <span style="color:#888;letter-spacing:2px">featured projects</span>
  </div>
  <table>
    <tr>
      <td style="width:50%;padding:4px;vertical-align:top">
        <a href="https://github.com/etrnkz/chatgpt-unofficial-api" style="display:flex;flex-direction:column;gap:4px;padding:12px 14px;background:#050505;border:1px solid #1a1a1a;text-decoration:none;border-left:3px solid #1a1a1a">
          <span style="color:#dc143c;font-size:12px;font-weight:700;letter-spacing:.5px">chatgpt-unofficial-api</span>
          <span style="color:#666;font-size:11px;line-height:1.4">Unofficial Node.js client for ChatGPT. No login required for chat.</span>
          <span style="font-size:10px;color:#444;margin-top:2px">● JavaScript ★ 1</span>
        </a>
      </td>
      <td style="width:50%;padding:4px;vertical-align:top">
        <a href="https://github.com/etrnkz/gemini-unofficial-api" style="display:flex;flex-direction:column;gap:4px;padding:12px 14px;background:#050505;border:1px solid #1a1a1a;text-decoration:none;border-left:3px solid #1a1a1a">
          <span style="color:#dc143c;font-size:12px;font-weight:700;letter-spacing:.5px">gemini-unofficial-api</span>
          <span style="color:#666;font-size:11px;line-height:1.4">Reverse-engineered Node.js client for Google Gemini.</span>
          <span style="font-size:10px;color:#444;margin-top:2px">● JavaScript ★ 1</span>
        </a>
      </td>
    </tr>
    <tr>
      <td style="width:50%;padding:4px;vertical-align:top">
        <a href="https://github.com/etrnkz/NullCrypt" style="display:flex;flex-direction:column;gap:4px;padding:12px 14px;background:#050505;border:1px solid #1a1a1a;text-decoration:none;border-left:3px solid #1a1a1a">
          <span style="color:#dc143c;font-size:12px;font-weight:700;letter-spacing:.5px">NullCrypt</span>
          <span style="color:#666;font-size:11px;line-height:1.4">Encryption tool built in Rust</span>
          <span style="font-size:10px;color:#444;margin-top:2px">● Rust ★ 1</span>
        </a>
      </td>
      <td style="width:50%;padding:4px;vertical-align:top">
        <a href="https://github.com/etrnkz/black-box-unoffcial-api" style="display:flex;flex-direction:column;gap:4px;padding:12px 14px;background:#050505;border:1px solid #1a1a1a;text-decoration:none;border-left:3px solid #1a1a1a">
          <span style="color:#dc143c;font-size:12px;font-weight:700;letter-spacing:.5px">black-box-unofficial-api</span>
          <span style="color:#666;font-size:11px;line-height:1.4">Unofficial API client for Blackbox AI</span>
          <span style="font-size:10px;color:#444;margin-top:2px">● Python ★ 1</span>
        </a>
      </td>
    </tr>
    <tr>
      <td style="width:50%;padding:4px;vertical-align:top">
        <a href="https://github.com/etrnkz/fancy-Agent" style="display:flex;flex-direction:column;gap:4px;padding:12px 14px;background:#050505;border:1px solid #1a1a1a;text-decoration:none;border-left:3px solid #1a1a1a">
          <span style="color:#dc143c;font-size:12px;font-weight:700;letter-spacing:.5px">fancy-Agent</span>
          <span style="color:#666;font-size:11px;line-height:1.4">AI agent framework</span>
          <span style="font-size:10px;color:#444;margin-top:2px">● Python ★ 1</span>
        </a>
      </td>
      <td style="width:50%;padding:4px;vertical-align:top">
        <a href="https://github.com/etrnkz/freeDogs" style="display:flex;flex-direction:column;gap:4px;padding:12px 14px;background:#050505;border:1px solid #1a1a1a;text-decoration:none;border-left:3px solid #1a1a1a">
          <span style="color:#dc143c;font-size:12px;font-weight:700;letter-spacing:.5px">freeDogs</span>
          <span style="color:#666;font-size:11px;line-height:1.4">Telegram clicker automation bot</span>
          <span style="font-size:10px;color:#444;margin-top:2px">● Python ★ 3</span>
        </a>
      </td>
    </tr>
  </table>
</div>

<!-- 0x0050 | recent activity -->
<div style="margin:20px 0;font-family:'Courier New',monospace">
  <div style="color:#555;font-size:10px;letter-spacing:1px;margin-bottom:6px;display:flex;align-items:center;gap:8px">
    <span style="color:#dc143c;font-size:10px;min-width:52px">0x0050</span>
    <span style="color:#2a2a2a">│</span>
    <span style="color:#888;letter-spacing:2px">recent activity</span>
  </div>
  <!--RECENT_ACTIVITY_START-->
  <div style="background:#050505;border:1px solid #1a1a1a;padding:16px;text-align:center;color:#444;font-size:12px">> fetching latest activity...</div>
  <!--RECENT_ACTIVITY_END-->
</div>

<br/>

<div align="center">

  <div style="font-size:13px;color:#888;font-family:'Courier New',monospace;margin-bottom:12px;letter-spacing:1px">
    &nbsp;&nbsp;`$ <span style="color:#dc143c">Let's build something.</span>`
  </div>

  <div>
    <a href="https://t.me/etrnkz">
      <span style="display:inline-block;padding:5px 12px;font-size:9px;font-weight:700;letter-spacing:1px;text-transform:uppercase;border:1px solid #dc143c;color:#dc143c;margin:2px">DM ON TELEGRAM</span>
    </a>
    <a href="mailto:">
      <span style="display:inline-block;padding:5px 12px;font-size:9px;font-weight:700;letter-spacing:1px;text-transform:uppercase;border:1px solid #dc143c;color:#dc143c;margin:2px">EMAIL</span>
    </a>
    <span style="display:inline-block;padding:5px 12px;font-size:9px;font-weight:700;letter-spacing:1px;text-transform:uppercase;border:1px solid #333;color:#666;margin:2px">VISITORS: --</span>
  </div>

  <br/>

  <div style="color:#444;font-style:italic;font-size:12px;padding:10px 14px;border-left:2px solid #dc143c;background:#050505;font-family:'Courier New',monospace;max-width:400px;margin:0 auto">
    "I don't break things — I understand how they work."
  </div>

  <br/>

  <div style="font-size:9px;color:#333;font-family:'Courier New',monospace;letter-spacing:1px">
    [ process exited with code 0x0 ]
  </div>

</div>
