<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Shreelakshmi G Bhat — start page</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:wght@400;500;600&family=IBM+Plex+Sans:wght@400;500;600&display=swap');

  :root{
    --paper:#FAF8F2;
    --paper-raised:#FFFFFF;
    --ink:#15171C;
    --muted:#6A6E78;
    --faint:#9A9DA6;
    --line:#E4E0D5;
    --line-strong:#D2CDBE;
    --green:#2EA043;

    --lang-python:#3572A5;
    --lang-c:#555555;
    --lang-cpp:#F34B7D;
    --lang-html:#E34C26;
    --lang-ts:#3178C6;
    --lang-js:#D4B106;
    --lang-ipynb:#DA5B0B;
    --lang-other:#B8B3A4;
  }

  *{box-sizing:border-box;}
  html{scroll-behavior:smooth;}
  body{
    margin:0;
    background:var(--paper);
    color:var(--ink);
    font-family:'IBM Plex Sans', sans-serif;
    -webkit-font-smoothing:antialiased;
  }
  a{color:inherit;}

  .wrap{
    max-width:880px;
    margin:0 auto;
    padding:0 28px;
  }

  /* ---------- HERO ---------- */
  .hero{padding:72px 0 40px;}
  .eyebrow{
    font-family:'IBM Plex Mono', monospace;
    font-size:12.5px;
    letter-spacing:.12em;
    color:var(--muted);
    text-transform:uppercase;
    margin-bottom:22px;
  }
  .eyebrow::before{content:"$ whoami";display:block;color:var(--faint);margin-bottom:4px;}
  h1{
    font-family:'IBM Plex Mono', monospace;
    font-weight:600;
    font-size:clamp(34px, 6vw, 58px);
    line-height:1.05;
    margin:0 0 18px;
    letter-spacing:-0.01em;
  }
  .tagline{
    font-size:18px;
    line-height:1.55;
    color:#3A3D45;
    max-width:560px;
    margin:0 0 30px;
  }
  .stats{
    display:flex;
    flex-wrap:wrap;
    gap:0;
    border-top:1px solid var(--line);
    border-bottom:1px solid var(--line);
  }
  .stat{
    padding:14px 22px 14px 0;
    margin-right:22px;
    font-family:'IBM Plex Mono', monospace;
  }
  .stat:not(:last-child){border-right:1px solid var(--line);}
  .stat b{font-size:19px;font-weight:600;}
  .stat span{display:block;font-size:11.5px;color:var(--muted);text-transform:uppercase;letter-spacing:.08em;margin-top:2px;}

  /* ---------- SECTION LABELS ---------- */
  .section{padding:52px 0;}
  .section-head{
    display:flex;
    align-items:baseline;
    justify-content:space-between;
    margin-bottom:22px;
  }
  .section-title{
    font-family:'IBM Plex Mono', monospace;
    font-size:13px;
    letter-spacing:.14em;
    text-transform:uppercase;
    color:var(--ink);
    font-weight:600;
  }
  .section-note{
    font-size:13px;
    color:var(--faint);
    font-family:'IBM Plex Mono', monospace;
  }

  /* ---------- LANGUAGE SPECTRUM (signature) ---------- */
  .spectrum-bar{
    display:flex;
    width:100%;
    height:34px;
    border-radius:4px;
    overflow:hidden;
    border:1px solid var(--line-strong);
  }
  .seg{
    height:100%;
    cursor:pointer;
    transition:filter .15s ease, transform .15s ease;
    position:relative;
  }
  .seg:hover{filter:brightness(1.12);}
  .seg.dim{filter:grayscale(1) brightness(1.5) opacity(.35);}
  .seg.active::after{
    content:"";
    position:absolute;inset:0;
    box-shadow:inset 0 0 0 2px var(--ink);
  }

  .legend{
    display:flex;
    flex-wrap:wrap;
    gap:8px 18px;
    margin-top:16px;
  }
  .legend-item{
    display:flex;
    align-items:center;
    gap:7px;
    font-family:'IBM Plex Mono', monospace;
    font-size:12.5px;
    color:var(--muted);
    cursor:pointer;
    padding:4px 0;
    user-select:none;
  }
  .legend-item.active{color:var(--ink);font-weight:600;}
  .dot{width:9px;height:9px;border-radius:50%;flex-shrink:0;}
  .legend-clear{
    font-family:'IBM Plex Mono', monospace;
    font-size:12.5px;
    color:var(--faint);
    text-decoration:underline;
    cursor:pointer;
    margin-left:auto;
    visibility:hidden;
  }
  .legend-clear.show{visibility:visible;}

  /* ---------- FEATURED GRID ---------- */
  .grid{
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:1px;
    background:var(--line);
    border:1px solid var(--line);
  }
  .card{
    background:var(--paper-raised);
    padding:22px 24px;
    display:flex;
    flex-direction:column;
    gap:10px;
  }
  .card-top{display:flex;align-items:center;justify-content:space-between;}
  .card-name{
    font-family:'IBM Plex Mono', monospace;
    font-weight:600;
    font-size:15.5px;
  }
  .card-name a{text-decoration:none;border-bottom:1px solid var(--line-strong);}
  .card-name a:hover{border-color:var(--ink);}
  .card-desc{font-size:13.8px;line-height:1.55;color:var(--muted);flex-grow:1;}
  .card-meta{
    display:flex;
    align-items:center;
    gap:14px;
    font-family:'IBM Plex Mono', monospace;
    font-size:12px;
    color:var(--faint);
  }
  .lang-tag{display:flex;align-items:center;gap:5px;}

  /* ---------- REPO LOG ---------- */
  .log{border-top:1px solid var(--line);}
  .log-row{
    display:grid;
    grid-template-columns:34px 1fr auto;
    gap:16px;
    align-items:baseline;
    padding:13px 0;
    border-bottom:1px solid var(--line);
    transition:opacity .15s ease;
  }
  .log-row.hidden{display:none;}
  .log-dot{
    width:9px;height:9px;border-radius:50%;
    align-self:center;
    justify-self:center;
  }
  .log-main{min-width:0;}
  .log-name{
    font-family:'IBM Plex Mono', monospace;
    font-size:14px;
    font-weight:600;
    text-decoration:none;
  }
  .log-name:hover{color:var(--green);}
  .log-priv{
    font-family:'IBM Plex Mono', monospace;
    font-size:10.5px;
    color:var(--faint);
    border:1px solid var(--line-strong);
    border-radius:3px;
    padding:1px 5px;
    margin-left:8px;
    vertical-align:middle;
  }
  .log-desc{font-size:13px;color:var(--muted);margin-top:2px;line-height:1.4;}
  .log-meta{
    font-family:'IBM Plex Mono', monospace;
    font-size:11.5px;
    color:var(--faint);
    text-align:right;
    white-space:nowrap;
  }
  .log-meta .stars{color:var(--muted);margin-right:10px;}

  /* ---------- FOOTER ---------- */
  footer{
    padding:50px 0 70px;
    border-top:1px solid var(--line);
    margin-top:20px;
  }
  .footer-row{
    display:flex;
    flex-wrap:wrap;
    justify-content:space-between;
    align-items:flex-end;
    gap:20px;
  }
  .footer-links{display:flex;gap:24px;flex-wrap:wrap;}
  .footer-links a{
    font-family:'IBM Plex Mono', monospace;
    font-size:13px;
    text-decoration:none;
    border-bottom:1px solid var(--line-strong);
    padding-bottom:1px;
  }
  .footer-links a:hover{border-color:var(--ink);}
  .footer-loc{
    font-family:'IBM Plex Mono', monospace;
    font-size:12px;
    color:var(--faint);
  }

  @media (max-width:640px){
    .hero{padding:48px 0 30px;}
    .grid{grid-template-columns:1fr;}
    .stat{padding-right:16px;margin-right:16px;}
    .log-row{grid-template-columns:20px 1fr;}
    .log-meta{grid-column:1/-1;text-align:left;padding-left:32px;margin-top:-4px;}
  }

  :focus-visible{outline:2px solid var(--green);outline-offset:2px;}
</style>
</head>
<body>

<div class="wrap">

  <!-- HERO -->
  <section class="hero">
    <div class="eyebrow">Shreelakshmigbhat · PES University, CSE · Bengaluru</div>
    <h1>Shreelakshmi&nbsp;G&nbsp;Bhat</h1>
    <p class="tagline">Thirty-five repositories spanning ML pipelines, systems programming, and real-time multiplayer backends — this page reads them the way a language spectrum reads a codebase.</p>
    <div class="stats">
      <div class="stat"><b>35</b><span>Repositories</span></div>
      <div class="stat"><b>14</b><span>Stars earned</span></div>
      <div class="stat"><b>11</b><span>Followers</span></div>
      <div class="stat"><b>12</b><span>Following</span></div>
    </div>
  </section>

  <!-- SIGNATURE: LANGUAGE SPECTRUM -->
  <section class="section" id="spectrum-section">
    <div class="section-head">
      <div class="section-title">Language spectrum</div>
      <div class="section-note">click a segment to filter the log</div>
    </div>
    <div class="spectrum-bar" id="spectrumBar">
      <div class="seg" data-lang="python" style="width:20.8%;background:var(--lang-python);" title="Python — 5 repos"></div>
      <div class="seg" data-lang="html" style="width:20.8%;background:var(--lang-html);" title="HTML — 5 repos"></div>
      <div class="seg" data-lang="c" style="width:16.7%;background:var(--lang-c);" title="C — 4 repos"></div>
      <div class="seg" data-lang="cpp" style="width:12.5%;background:var(--lang-cpp);" title="C++ — 3 repos"></div>
      <div class="seg" data-lang="js" style="width:12.5%;background:var(--lang-js);" title="JavaScript — 3 repos"></div>
      <div class="seg" data-lang="ts" style="width:8.3%;background:var(--lang-ts);" title="TypeScript — 2 repos"></div>
      <div class="seg" data-lang="ipynb" style="width:8.4%;background:var(--lang-ipynb);" title="Jupyter Notebook — 2 repos"></div>
    </div>
    <div class="legend" id="legend">
      <div class="legend-item" data-lang="python"><span class="dot" style="background:var(--lang-python)"></span>Python · 5</div>
      <div class="legend-item" data-lang="html"><span class="dot" style="background:var(--lang-html)"></span>HTML · 5</div>
      <div class="legend-item" data-lang="c"><span class="dot" style="background:var(--lang-c)"></span>C · 4</div>
      <div class="legend-item" data-lang="cpp"><span class="dot" style="background:var(--lang-cpp)"></span>C++ · 3</div>
      <div class="legend-item" data-lang="js"><span class="dot" style="background:var(--lang-js)"></span>JavaScript · 3</div>
      <div class="legend-item" data-lang="ts"><span class="dot" style="background:var(--lang-ts)"></span>TypeScript · 2</div>
      <div class="legend-item" data-lang="ipynb"><span class="dot" style="background:var(--lang-ipynb)"></span>Jupyter · 2</div>
      <div class="legend-clear" id="legendClear">clear filter</div>
    </div>
  </section>

  <!-- FEATURED -->
  <section class="section">
    <div class="section-head">
      <div class="section-title">Featured builds</div>
    </div>
    <div class="grid">

      <div class="card">
        <div class="card-top"><span class="card-name"><a href="https://github.com/Shreelakshmigbhat/HotelEcho" target="_blank" rel="noopener">HotelEcho</a></span></div>
        <div class="card-desc">Predicts hotel ratings from customer reviews using machine learning, with an interactive Streamlit dashboard.</div>
        <div class="card-meta"><span class="lang-tag"><span class="dot" style="background:var(--lang-python)"></span>Python</span><span>★ 1</span></div>
      </div>

      <div class="card">
        <div class="card-top"><span class="card-name"><a href="https://github.com/Shreelakshmigbhat/CarVision-CNN-yolo" target="_blank" rel="noopener">CarVision-CNN-yolo</a></span></div>
        <div class="card-desc">Car detection with YOLOv8 — model setup, dataset loading, training, and real-time inference using Ultralytics' YOLO library.</div>
        <div class="card-meta"><span class="lang-tag"><span class="dot" style="background:var(--lang-python)"></span>Python</span><span>★ 1</span></div>
      </div>

      <div class="card">
        <div class="card-top"><span class="card-name"><a href="https://github.com/Shreelakshmigbhat/CodeCompass" target="_blank" rel="noopener">CodeCompass</a></span></div>
        <div class="card-desc">Adaptive LLM recommendation framework — evaluates Python code competency and learns difficulty-aware prompt–model pairings via Random Forest classification.</div>
        <div class="card-meta"><span>★ 1</span></div>
      </div>

      <div class="card">
        <div class="card-top"><span class="card-name"><a href="https://github.com/Shreelakshmigbhat/VelocityTorqueNation1" target="_blank" rel="noopener">VelocityTorqueNation1</a></span></div>
        <div class="card-desc">Real-time distributed multiplayer racing game — socket networking, server coordination, hash-based load balancing, distributed leaderboard.</div>
        <div class="card-meta"><span class="lang-tag"><span class="dot" style="background:var(--lang-ts)"></span>TypeScript</span><span>★ 1</span></div>
      </div>

      <div class="card">
        <div class="card-top"><span class="card-name"><a href="https://github.com/Shreelakshmigbhat/Compresso-Huffman-coding" target="_blank" rel="noopener">Compresso-Huffman-coding</a></span></div>
        <div class="card-desc">A file zipper built on Huffman coding — lossless compression using binary trees and min-heaps over frequency tables.</div>
        <div class="card-meta"><span class="lang-tag"><span class="dot" style="background:var(--lang-c)"></span>C</span><span>★ 1</span></div>
      </div>

      <div class="card">
        <div class="card-top"><span class="card-name"><a href="https://github.com/Shreelakshmigbhat/SVDimageLA" target="_blank" rel="noopener">SVDimageLA</a></span></div>
        <div class="card-desc">A Python tool applying Singular Value Decomposition to images — linear algebra made visible.</div>
        <div class="card-meta"><span class="lang-tag"><span class="dot" style="background:var(--lang-ipynb)"></span>Jupyter</span><span>★ 1 · ⑂ 1</span></div>
      </div>

    </div>
  </section>

  <!-- FULL LOG -->
  <section class="section">
    <div class="section-head">
      <div class="section-title">Full log</div>
      <div class="section-note" id="logCount">30 repositories</div>
    </div>
    <div class="log" id="log">

      <div class="log-row" data-lang="python"><span class="log-dot" style="background:var(--lang-python)"></span><div class="log-main"><a class="log-name" href="https://github.com/Shreelakshmigbhat/HotelEcho" target="_blank" rel="noopener">HotelEcho</a><div class="log-desc">Hotel rating prediction from reviews, with a Streamlit dashboard.</div></div><div class="log-meta"><span class="stars">★ 1</span>21 min ago</div></div>

      <div class="log-row" data-lang="python"><span class="log-dot" style="background:var(--lang-python)"></span><div class="log-main"><a class="log-name" href="https://github.com/Shreelakshmigbhat/GhostMesh" target="_blank" rel="noopener">GhostMesh</a><span class="log-priv">private</span><div class="log-desc">MIT-licensed Python project.</div></div><div class="log-meta">2 hrs ago</div></div>

      <div class="log-row" data-lang="other"><span class="log-dot" style="background:var(--lang-other)"></span><div class="log-main"><a class="log-name" href="https://github.com/Shreelakshmigbhat/SkillXchange" target="_blank" rel="noopener">SkillXchange</a><span class="log-priv">private</span></div><div class="log-meta">yesterday</div></div>

      <div class="log-row" data-lang="c"><span class="log-dot" style="background:var(--lang-c)"></span><div class="log-main"><a class="log-name" href="https://github.com/Shreelakshmigbhat/Compresso-Huffman-coding" target="_blank" rel="noopener">Compresso-Huffman-coding</a><div class="log-desc">File compressor built on Huffman coding, binary trees and min-heaps.</div></div><div class="log-meta"><span class="stars">★ 1</span>yesterday</div></div>

      <div class="log-row" data-lang="python"><span class="log-dot" style="background:var(--lang-python)"></span><div class="log-main"><a class="log-name" href="https://github.com/Shreelakshmigbhat/CarVision-CNN-yolo" target="_blank" rel="noopener">CarVision-CNN-yolo</a><div class="log-desc">Car detection with YOLOv8, training and real-time inference.</div></div><div class="log-meta"><span class="stars">★ 1</span>yesterday</div></div>

      <div class="log-row" data-lang="other"><span class="log-dot" style="background:var(--lang-other)"></span><div class="log-main"><a class="log-name" href="https://github.com/Shreelakshmigbhat/Shreelakshmigbhat" target="_blank" rel="noopener">Shreelakshmigbhat</a><div class="log-desc">Profile README repository.</div></div><div class="log-meta">yesterday</div></div>

      <div class="log-row" data-lang="html"><span class="log-dot" style="background:var(--lang-html)"></span><div class="log-main"><a class="log-name" href="https://github.com/Shreelakshmigbhat/Gkraj_portfolio" target="_blank" rel="noopener">Gkraj_portfolio</a><span class="log-priv">private</span></div><div class="log-meta">2 days ago</div></div>

      <div class="log-row" data-lang="ts"><span class="log-dot" style="background:var(--lang-ts)"></span><div class="log-main"><a class="log-name" href="https://github.com/Shreelakshmigbhat/shreelakshmigbhat-portfolio" target="_blank" rel="noopener">shreelakshmigbhat-portfolio</a><span class="log-priv">private</span></div><div class="log-meta">4 days ago</div></div>

      <div class="log-row" data-lang="other"><span class="log-dot" style="background:var(--lang-other)"></span><div class="log-main"><a class="log-name" href="https://github.com/Shreelakshmigbhat/CodeCompass" target="_blank" rel="noopener">CodeCompass</a><div class="log-desc">Adaptive LLM recommendation framework, Random Forest–based.</div></div><div class="log-meta"><span class="stars">★ 1</span>4 days ago</div></div>

      <div class="log-row" data-lang="cpp"><span class="log-dot" style="background:var(--lang-cpp)"></span><div class="log-main"><a class="log-name" href="https://github.com/Shreelakshmigbhat/my_Leetcode_sols" target="_blank" rel="noopener">my_Leetcode_sols</a><span class="log-priv">private</span><div class="log-desc">LeetCode solutions, synced via LeetHub v2.</div></div><div class="log-meta">4 days ago</div></div>

      <div class="log-row" data-lang="other"><span class="log-dot" style="background:var(--lang-other)"></span><div class="log-main"><a class="log-name" href="https://github.com/Shreelakshmigbhat/SE_lab_PES2UG24CS478_Sec_H" target="_blank" rel="noopener">SE_lab_PES2UG24CS478_Sec_H</a></div><div class="log-meta">5 days ago</div></div>

      <div class="log-row" data-lang="html"><span class="log-dot" style="background:var(--lang-html)"></span><div class="log-main"><a class="log-name" href="https://github.com/Shreelakshmigbhat/eGOV-monorepo-ML-final" target="_blank" rel="noopener">eGOV-monorepo-ML-final</a><div class="log-desc">Forked from Guna-meda/eGOV-monorepo.</div></div><div class="log-meta">3 wks ago</div></div>

      <div class="log-row" data-lang="html"><span class="log-dot" style="background:var(--lang-html)"></span><div class="log-main"><a class="log-name" href="https://github.com/Shreelakshmigbhat/eGov-ML-stuff" target="_blank" rel="noopener">eGov-ML-stuff</a><span class="log-priv">private</span></div><div class="log-meta"><span class="stars">★ 2</span>Jul 22</div></div>

      <div class="log-row" data-lang="python"><span class="log-dot" style="background:var(--lang-python)"></span><div class="log-main"><a class="log-name" href="https://github.com/Shreelakshmigbhat/SOCLens" target="_blank" rel="noopener">SOCLens</a></div><div class="log-meta"><span class="stars">★ 1</span>Jun 30</div></div>

      <div class="log-row" data-lang="ipynb"><span class="log-dot" style="background:var(--lang-ipynb)"></span><div class="log-main"><a class="log-name" href="https://github.com/Shreelakshmigbhat/ML-repo-for-eGov" target="_blank" rel="noopener">ML-repo-for-eGov</a><span class="log-priv">private</span></div><div class="log-meta">Jun 29</div></div>

      <div class="log-row" data-lang="cpp"><span class="log-dot" style="background:var(--lang-cpp)"></span><div class="log-main"><a class="log-name" href="https://github.com/Shreelakshmigbhat/DSA" target="_blank" rel="noopener">DSA</a><span class="log-priv">private</span></div><div class="log-meta"><span class="stars">★ 1</span>Jun 28</div></div>

      <div class="log-row" data-lang="js"><span class="log-dot" style="background:var(--lang-js)"></span><div class="log-main"><a class="log-name" href="https://github.com/Shreelakshmigbhat/AI-Rephraser" target="_blank" rel="noopener">AI-Rephraser</a></div><div class="log-meta">Jun 27</div></div>

      <div class="log-row" data-lang="html"><span class="log-dot" style="background:var(--lang-html)"></span><div class="log-main"><a class="log-name" href="https://github.com/Shreelakshmigbhat/ML-repo--eGov" target="_blank" rel="noopener">ML-repo--eGov</a><span class="log-priv">private</span></div><div class="log-meta">Jun 15</div></div>

      <div class="log-row" data-lang="other"><span class="log-dot" style="background:var(--lang-other)"></span><div class="log-main"><a class="log-name" href="https://github.com/Shreelakshmigbhat/eGOV-monorepo" target="_blank" rel="noopener">eGOV-monorepo</a><span class="log-priv">private</span></div><div class="log-meta">Jun 14</div></div>

      <div class="log-row" data-lang="html"><span class="log-dot" style="background:var(--lang-html)"></span><div class="log-main"><a class="log-name" href="https://github.com/Shreelakshmigbhat/eGov-ML-repo" target="_blank" rel="noopener">eGov-ML-repo</a><span class="log-priv">private</span></div><div class="log-meta"><span class="stars">★ 1</span>Jun 12</div></div>

      <div class="log-row" data-lang="cpp"><span class="log-dot" style="background:var(--lang-cpp)"></span><div class="log-main"><a class="log-name" href="https://github.com/Shreelakshmigbhat/Smart_room_safety_system" target="_blank" rel="noopener">Smart_room_safety_system</a><div class="log-desc">Forked from amritap0200/smart-room-system.</div></div><div class="log-meta"><span class="stars">★ 1</span>Apr 16</div></div>

      <div class="log-row" data-lang="c"><span class="log-dot" style="background:var(--lang-c)"></span><div class="log-main"><a class="log-name" href="https://github.com/Shreelakshmigbhat/PES2UG24CS478-pes-vcs" target="_blank" rel="noopener">PES2UG24CS478-pes-vcs</a><div class="log-desc">Building a version control system for file management. Public template, forked.</div></div><div class="log-meta">Apr 15</div></div>

      <div class="log-row" data-lang="c"><span class="log-dot" style="background:var(--lang-c)"></span><div class="log-main"><a class="log-name" href="https://github.com/Shreelakshmigbhat/Randomized-algos" target="_blank" rel="noopener">Randomized-algos</a></div><div class="log-meta"><span class="stars">★ 1</span>Apr 15</div></div>

      <div class="log-row" data-lang="c"><span class="log-dot" style="background:var(--lang-c)"></span><div class="log-main"><a class="log-name" href="https://github.com/Shreelakshmigbhat/OS-Jackfruit" target="_blank" rel="noopener">OS-Jackfruit</a><div class="log-desc">Forked from shivangjhalani/OS-Jackfruit.</div></div><div class="log-meta"><span class="stars">★ 1</span>Apr 12</div></div>

      <div class="log-row" data-lang="ts"><span class="log-dot" style="background:var(--lang-ts)"></span><div class="log-main"><a class="log-name" href="https://github.com/Shreelakshmigbhat/VelocityTorqueNation1" target="_blank" rel="noopener">VelocityTorqueNation1</a><div class="log-desc">Real-time distributed multiplayer racing game with socket networking.</div></div><div class="log-meta"><span class="stars">★ 1</span>Apr 12</div></div>

      <div class="log-row" data-lang="python"><span class="log-dot" style="background:var(--lang-python)"></span><div class="log-main"><a class="log-name" href="https://github.com/Shreelakshmigbhat/SDN-PacketDroppingSimulator" target="_blank" rel="noopener">SDN-PacketDroppingSimulator</a></div><div class="log-meta"><span class="stars">★ 1</span>Apr 10</div></div>

      <div class="log-row" data-lang="js"><span class="log-dot" style="background:var(--lang-js)"></span><div class="log-main"><a class="log-name" href="https://github.com/Shreelakshmigbhat/Racing-game-socket-programming-real-time-leader-board" target="_blank" rel="noopener">Racing-game-socket-programming</a></div><div class="log-meta"><span class="stars">★ 1</span>Mar 22</div></div>

      <div class="log-row" data-lang="ipynb"><span class="log-dot" style="background:var(--lang-ipynb)"></span><div class="log-main"><a class="log-name" href="https://github.com/Shreelakshmigbhat/SVDimageLA" target="_blank" rel="noopener">SVDimageLA</a><div class="log-desc">SVD applied to images.</div></div><div class="log-meta"><span class="stars">★ 1 · ⑂ 1</span>Mar 20</div></div>

      <div class="log-row" data-lang="other"><span class="log-dot" style="background:var(--lang-other)"></span><div class="log-main"><a class="log-name" href="https://github.com/Shreelakshmigbhat/nextjs-ai-chatbot" target="_blank" rel="noopener">nextjs-ai-chatbot</a><span class="log-priv">private</span></div><div class="log-meta"><span class="stars">★ 1</span>Feb 9</div></div>

      <div class="log-row" data-lang="js"><span class="log-dot" style="background:var(--lang-js)"></span><div class="log-main"><a class="log-name" href="https://github.com/Shreelakshmigbhat/VelocityTorqueNation" target="_blank" rel="noopener">VelocityTorqueNation</a></div><div class="log-meta"><span class="stars">★ 2 · ⑂ 1</span>Nov 16, 2025</div></div>

    </div>
  </section>

  <footer>
    <div class="footer-row">
      <div class="footer-links">
        <a href="https://github.com/Shreelakshmigbhat" target="_blank" rel="noopener">github.com/Shreelakshmigbhat</a>
        <a href="mailto:shreelakshmigbhat@gmail.com">shreelakshmigbhat@gmail.com</a>
        <a href="https://www.linkedin.com/in/shreelakshmi-bhat-36a792355/" target="_blank" rel="noopener">linkedin</a>
      </div>
      <div class="footer-loc">PES University · Bengaluru</div>
    </div>
  </footer>

</div>

<script>
  const segs = document.querySelectorAll('.seg');
  const legendItems = document.querySelectorAll('.legend-item');
  const rows = document.querySelectorAll('.log-row');
  const clearBtn = document.getElementById('legendClear');
  const logCount = document.getElementById('logCount');
  let activeLang = null;

  function applyFilter(lang){
    activeLang = (activeLang === lang) ? null : lang;

    segs.forEach(s => {
      s.classList.toggle('active', activeLang && s.dataset.lang === activeLang);
      s.classList.toggle('dim', activeLang && s.dataset.lang !== activeLang);
    });
    legendItems.forEach(li => li.classList.toggle('active', activeLang && li.dataset.lang === activeLang));

    let visible = 0;
    rows.forEach(r => {
      const show = !activeLang || r.dataset.lang === activeLang;
      r.classList.toggle('hidden', !show);
      if(show) visible++;
    });

    clearBtn.classList.toggle('show', !!activeLang);
    logCount.textContent = activeLang ? visible + ' matching repositories' : '30 repositories';

    if(activeLang){
      document.getElementById('log').scrollIntoView({behavior:'smooth', block:'start'});
    }
  }

  segs.forEach(s => s.addEventListener('click', () => applyFilter(s.dataset.lang)));
  legendItems.forEach(li => li.addEventListener('click', () => applyFilter(li.dataset.lang)));
  clearBtn.addEventListener('click', () => applyFilter(activeLang));
</script>

</body>
</html>
