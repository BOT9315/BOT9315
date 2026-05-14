<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Ankush · BOT9315</title>
<link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;600;700&family=Orbitron:wght@700;900&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">
<style>
*{box-sizing:border-box;margin:0;padding:0}
:root{
  --bg:#050b18;--bg2:#0c1428;--card:#0f1c35;--border:#1a2e4a;
  --cyan:#00e5ff;--green:#00ff7f;--purple:#b56bff;--orange:#ff6b35;--gold:#ffd700;
  --text:#dde6f5;--muted:#4a6080;
}
html,body{min-height:100%;overflow-x:hidden}
body{
  background:var(--bg);color:var(--text);
  font-family:'Fira Code',monospace;
  background-image:
    radial-gradient(ellipse 80% 50% at 20% 10%,rgba(0,229,255,.06) 0,transparent 60%),
    radial-gradient(ellipse 60% 40% at 80% 90%,rgba(181,107,255,.06) 0,transparent 60%);
}
#cvs{position:fixed;inset:0;z-index:0;pointer-events:none}
body::after{
  content:'';position:fixed;inset:0;z-index:1;pointer-events:none;
  background:repeating-linear-gradient(0deg,transparent 0,transparent 3px,rgba(0,0,0,.04) 3px,rgba(0,0,0,.04) 4px);
}
.wrap{position:relative;z-index:2;max-width:860px;margin:0 auto;padding:2rem 1.5rem 5rem}

/* HERO */
.hero{text-align:center;padding:3rem 0 2.5rem}

/* AVATAR */
.av-outer{width:130px;height:130px;margin:0 auto 1.6rem;position:relative;display:flex;align-items:center;justify-content:center}
.spin-ring{position:absolute;inset:0;border-radius:50%;background:conic-gradient(var(--cyan),var(--purple),var(--green),var(--orange),var(--cyan));animation:spinR 2.5s linear infinite}
.av-inner{position:absolute;inset:4px;border-radius:50%;background:var(--bg2);display:flex;align-items:center;justify-content:center;overflow:hidden}
.av-inner img{width:100%;height:100%;object-fit:cover;border-radius:50%;display:block}
@keyframes spinR{to{transform:rotate(360deg)}}

/* GLITCH */
.gname{font-family:'Orbitron',monospace;font-size:clamp(2rem,8vw,4rem);font-weight:900;color:var(--cyan);position:relative;display:inline-block;text-shadow:0 0 30px rgba(0,229,255,.45);animation:flk 10s infinite}
.gname::before,.gname::after{content:attr(data-t);position:absolute;inset:0}
.gname::before{color:var(--purple);animation:g1 5s infinite;clip-path:polygon(0 0,100% 0,100% 40%,0 40%)}
.gname::after{color:var(--green);animation:g2 5s infinite;clip-path:polygon(0 62%,100% 62%,100% 100%,0 100%)}
@keyframes g1{0%,100%{transform:translate(0)}6%{transform:translate(-4px,2px)}12%{transform:translate(4px,-2px)}17%{transform:translate(0)}}
@keyframes g2{0%,100%{transform:translate(0)}8%{transform:translate(4px,1px)}14%{transform:translate(-4px,-1px)}19%{transform:translate(0)}}
@keyframes flk{0%,94%,100%{opacity:1}95%{opacity:.8}97%{opacity:1}98.5%{opacity:.9}}

.subtitle{font-size:1rem;color:var(--green);letter-spacing:.18em;margin:.7rem 0 1.2rem;text-shadow:0 0 20px rgba(0,255,127,.35)}
.typing{font-size:.9rem;color:var(--muted);min-height:1.5em}
.cur{animation:bl 1s step-end infinite;color:var(--cyan)}
@keyframes bl{0%,100%{opacity:1}50%{opacity:0}}

.links{display:flex;gap:.7rem;flex-wrap:wrap;justify-content:center;margin-top:1.6rem}
.lbtn{display:flex;align-items:center;gap:.35rem;padding:.42rem 1rem;border:1px solid var(--border);border-radius:8px;font-size:.75rem;color:var(--text);text-decoration:none;background:var(--card);transition:all .2s;font-family:'Fira Code',monospace;letter-spacing:.05em}
.lbtn:hover{border-color:var(--cyan);color:var(--cyan);box-shadow:0 0 18px rgba(0,229,255,.25);transform:translateY(-2px)}

/* SECTION */
.stitle{font-family:'Orbitron',monospace;font-size:.85rem;font-weight:700;color:var(--cyan);letter-spacing:.22em;text-transform:uppercase;border-left:3px solid var(--cyan);padding-left:.7rem;margin:2.8rem 0 1.2rem;text-shadow:0 0 15px rgba(0,229,255,.4)}

/* TERMINAL */
.term{background:#040a14;border:1px solid var(--border);border-radius:12px;overflow:hidden}
.tbar{background:var(--card);padding:.55rem 1rem;display:flex;align-items:center;gap:.45rem;border-bottom:1px solid var(--border)}
.dot{width:11px;height:11px;border-radius:50%}
.d1{background:#ff5f57}.d2{background:#ffbd2e}.d3{background:#28ca41}
.tbody{padding:1.1rem 1.3rem;font-size:.78rem;line-height:2.1;min-height:160px}
.tl{display:block;white-space:nowrap;overflow:hidden}
.tp{color:var(--green)}.tc{color:var(--cyan)}.to{color:var(--muted)}.tv{color:var(--gold)}

/* SKILLS */
.skills{display:flex;flex-direction:column;gap:.8rem}
.srow{display:grid;grid-template-columns:120px 1fr 42px;align-items:center;gap:.75rem}
.slbl{font-size:.78rem;color:var(--muted)}
.strk{height:7px;border-radius:99px;background:var(--border);overflow:hidden}
.sfill{height:100%;border-radius:99px;width:0;transition:width 1.6s cubic-bezier(.4,0,.2,1)}
.py{background:linear-gradient(90deg,#3b82f6,#00e5ff)}
.fl{background:linear-gradient(90deg,#10b981,#00ff7f)}
.js{background:linear-gradient(90deg,#f59e0b,#ffd700)}
.ht{background:linear-gradient(90deg,#ef4444,#ff6b35)}
.cs{background:linear-gradient(90deg,#8b5cf6,#ec4899)}
.spct{font-size:.72rem;color:var(--cyan);text-align:right}

/* STATS */
.sgrid{display:grid;grid-template-columns:repeat(auto-fit,minmax(170px,1fr));gap:1rem}
.sc{background:var(--card);border:1px solid var(--border);border-radius:12px;padding:1.2rem;text-align:center;position:relative;overflow:hidden;transition:all .25s}
.sc:hover{transform:translateY(-4px);border-color:var(--cyan);box-shadow:0 0 24px rgba(0,229,255,.2)}
.sc::before{content:'';position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(90deg,var(--cyan),var(--purple))}
.snum{font-family:'Orbitron',monospace;font-size:2rem;font-weight:900;color:var(--cyan)}
.slb{font-size:.7rem;color:var(--muted);margin-top:.25rem;letter-spacing:.12em}

/* HEATMAP */
.hmap{display:flex;gap:3px;flex-wrap:wrap;padding:.75rem;background:var(--card);border:1px solid var(--border);border-radius:10px}
.hc{width:11px;height:11px;border-radius:2px;cursor:pointer;transition:transform .1s}
.hc:hover{transform:scale(1.7)}

/* PIE */
.pie-wrap{background:var(--card);border:1px solid var(--border);border-radius:12px;padding:1.2rem;display:flex;gap:1.5rem;align-items:center;flex-wrap:wrap}
.pie-legend{display:flex;flex-direction:column;gap:.5rem;flex:1;min-width:140px}
.ple{display:flex;align-items:center;gap:.5rem;font-size:.75rem;color:var(--text)}
.plc{width:10px;height:10px;border-radius:2px;flex-shrink:0}
.plv{margin-left:auto;color:var(--muted)}

/* FILTER + REPOS */
.ftabs{display:flex;gap:.5rem;flex-wrap:wrap;margin-bottom:1rem}
.ft{padding:.3rem .85rem;border-radius:99px;border:1px solid var(--border);font-size:.72rem;cursor:pointer;background:var(--card);color:var(--muted);transition:all .2s;font-family:'Fira Code',monospace}
.ft.active,.ft:hover{border-color:var(--cyan);color:var(--cyan);background:rgba(0,229,255,.08)}
.rgrid{display:grid;grid-template-columns:repeat(auto-fill,minmax(250px,1fr));gap:1rem}
.rcard{background:var(--card);border:1px solid var(--border);border-radius:12px;padding:1.15rem;cursor:pointer;transition:all .25s;position:relative;overflow:hidden;text-decoration:none;display:block;color:inherit}
.rcard:hover{transform:translateY(-5px) scale(1.01);border-color:var(--green);box-shadow:0 0 24px rgba(0,255,127,.18)}
.rcard.pin::after{content:'📌 PINNED';position:absolute;top:.5rem;right:.65rem;font-size:.58rem;color:var(--gold);letter-spacing:.08em}
.rcard.pin{border-color:rgba(181,107,255,.3)}
.rname{font-family:'Space Mono',monospace;font-size:.82rem;font-weight:700;color:var(--cyan);margin-bottom:.4rem;word-break:break-word;padding-right:3.5rem}
.rdesc{font-size:.73rem;color:var(--muted);line-height:1.55;margin-bottom:.75rem;min-height:2.1em}
.rmeta{display:flex;gap:.7rem;flex-wrap:wrap;align-items:center}
.rl{font-size:.68rem;padding:.14rem .5rem;border-radius:99px;font-weight:600}
.rPython{background:rgba(59,130,246,.15);color:#60a5fa;border:1px solid rgba(59,130,246,.4)}
.rHTML{background:rgba(239,68,68,.15);color:#f87171;border:1px solid rgba(239,68,68,.4)}
.rJavaScript{background:rgba(245,158,11,.15);color:#fbbf24;border:1px solid rgba(245,158,11,.4)}
.rCSS{background:rgba(139,92,246,.15);color:#c4b5fd;border:1px solid rgba(139,92,246,.4)}
.rdef{background:rgba(16,185,129,.15);color:#6ee7b7;border:1px solid rgba(16,185,129,.4)}
.rstar{font-size:.68rem;color:var(--gold)}
.ldr{text-align:center;padding:2.5rem;color:var(--muted);font-size:.82rem}
.spin{width:32px;height:32px;border:3px solid var(--border);border-top-color:var(--cyan);border-radius:50%;animation:spinR .8s linear infinite;margin:0 auto 1rem}

/* GAME */
.gwrap{background:var(--card);border:1px solid var(--border);border-radius:16px;padding:1.5rem;text-align:center;position:relative;overflow:hidden}
.gwrap::before{content:'';position:absolute;inset:0;border-radius:16px;background:radial-gradient(ellipse at 50% 0%,rgba(0,229,255,.05),transparent 60%);pointer-events:none}
.gtitle{font-family:'Orbitron',monospace;font-size:.85rem;color:var(--cyan);margin-bottom:.8rem;letter-spacing:.18em}
#gsc{font-family:'Orbitron',monospace;color:var(--green);font-size:.95rem;margin-bottom:.5rem}
#gcv{border:1px solid var(--border);border-radius:8px;background:#030910;display:block;margin:0 auto;max-width:100%;image-rendering:pixelated}
#gmsg{font-size:.75rem;color:var(--gold);min-height:1.2em;margin-top:.5rem}
.gctrl{font-size:.7rem;color:var(--muted);margin-top:.3rem}
.sbtn{background:linear-gradient(135deg,var(--cyan),var(--purple));border:none;border-radius:8px;color:#000;font-family:'Orbitron',monospace;font-size:.78rem;font-weight:700;padding:.5rem 1.5rem;cursor:pointer;margin-top:.7rem;transition:opacity .2s,transform .1s}
.sbtn:hover{opacity:.88;transform:scale(1.04)}

.foot{text-align:center;padding:2.5rem 0 0;color:var(--muted);font-size:.72rem}
.foot em{color:var(--green)}

@media(max-width:560px){.srow{grid-template-columns:90px 1fr 34px}}
</style>
</head>
<body>
<canvas id="cvs"></canvas>
<div class="wrap">

<!-- HERO -->
<div class="hero">
  <div class="av-outer">
    <div class="spin-ring"></div>
    <div class="av-inner" id="avInner">
      <!-- Avatar loaded via JS to handle CORS gracefully -->
    </div>
  </div>
  <h1 class="gname" data-t="Ankush">Ankush</h1>
  <div class="subtitle">⟨ BOT9315 ⟩ &nbsp;·&nbsp; Full Stack Developer</div>
  <div class="typing" id="typ"><span class="cur">█</span></div>
  <div class="links">
    <a class="lbtn" href="https://www.linkedin.com/public-profile/settings" target="_blank">🔗 LinkedIn</a>
    <a class="lbtn" href="https://www.instagram.com/iimankush_" target="_blank">📸 Instagram</a>
    <a class="lbtn" href="https://leetcode.com/u/Ankush123009/" target="_blank">⚡ LeetCode</a>
    <a class="lbtn" href="https://www.hackerrank.com/profile/akrk053" target="_blank">🏆 HackerRank</a>
    <a class="lbtn" href="https://github.com/BOT9315" target="_blank">🐙 GitHub</a>
  </div>
</div>

<!-- TERMINAL -->
<div class="term">
  <div class="tbar">
    <div class="dot d1"></div><div class="dot d2"></div><div class="dot d3"></div>
    <span style="margin-left:.5rem;font-size:.72rem;color:var(--muted)">ankush@bot9315:~$</span>
  </div>
  <div class="tbody" id="tb"></div>
</div>

<!-- SKILLS -->
<div class="stitle">// Tech Stack</div>
<div class="skills">
  <div class="srow"><span class="slbl">Python</span><div class="strk"><div class="sfill py" data-w="90"></div></div><span class="spct">90%</span></div>
  <div class="srow"><span class="slbl">Flask</span><div class="strk"><div class="sfill fl" data-w="80"></div></div><span class="spct">80%</span></div>
  <div class="srow"><span class="slbl">JavaScript</span><div class="strk"><div class="sfill js" data-w="70"></div></div><span class="spct">70%</span></div>
  <div class="srow"><span class="slbl">HTML</span><div class="strk"><div class="sfill ht" data-w="85"></div></div><span class="spct">85%</span></div>
  <div class="srow"><span class="slbl">CSS</span><div class="strk"><div class="sfill cs" data-w="75"></div></div><span class="spct">75%</span></div>
</div>

<!-- STATS -->
<div class="stitle">// GitHub Stats</div>
<div class="sgrid">
  <div class="sc"><div class="snum" id="sR">—</div><div class="slb">REPOSITORIES</div></div>
  <div class="sc"><div class="snum" id="sS">—</div><div class="slb">TOTAL STARS</div></div>
  <div class="sc"><div class="snum" id="sF">—</div><div class="slb">TOTAL FORKS</div></div>
  <div class="sc"><div class="snum" id="sL">—</div><div class="slb">LANGUAGES</div></div>
</div>

<!-- HEATMAP -->
<div class="stitle">// Activity Pulse</div>
<div class="hmap" id="hmap"></div>

<!-- PIE -->
<div class="stitle">// Language Breakdown</div>
<div class="pie-wrap">
  <canvas id="pieC" width="140" height="140" style="flex-shrink:0"></canvas>
  <div class="pie-legend" id="pieLeg"><div class="ldr" style="padding:.5rem">Loading…</div></div>
</div>

<!-- REPOS -->
<div class="stitle">// All Projects</div>
<div class="ftabs" id="ftabs">
  <div class="ft active" data-l="all">All</div>
  <div class="ft" data-l="Python">Python</div>
  <div class="ft" data-l="HTML">HTML</div>
  <div class="ft" data-l="JavaScript">JavaScript</div>
</div>
<div id="rc"><div class="ldr"><div class="spin"></div>Fetching repositories…</div></div>

<!-- GAME -->
<div class="stitle">// Mini Game</div>
<div class="gwrap">
  <div class="gtitle">🐍 SNAKE — Catch the commits</div>
  <div id="gsc">SCORE: 0 &nbsp;|&nbsp; BEST: 0</div>
  <canvas id="gcv" width="280" height="280"></canvas>
  <div id="gmsg">Press START or SPACE to play</div>
  <div class="gctrl">Arrow keys / WASD &nbsp;·&nbsp; Mobile: swipe</div>
  <button class="sbtn" onclick="startGame()">▶ START</button>
</div>

<div class="foot">crafted with <em>♥</em> &nbsp;·&nbsp; BOT9315 &nbsp;·&nbsp; &copy; <span id="yr"></span></div>
</div>

<script>
// ═══ AVATAR with graceful fallback ═══
(function(){
  const inner = document.getElementById('avInner');
  const svgFallback = `<svg width="122" height="122" viewBox="0 0 122 122" xmlns="http://www.w3.org/2000/svg">
    <defs>
      <radialGradient id="bg" cx="50%" cy="40%" r="60%">
        <stop offset="0%" stop-color="#1a3a6a"/>
        <stop offset="100%" stop-color="#0a0e1a"/>
      </radialGradient>
    </defs>
    <circle cx="61" cy="61" r="61" fill="url(#bg)"/>
    <!-- head -->
    <circle cx="61" cy="45" r="22" fill="#1e3d75"/>
    <ellipse cx="61" cy="43" rx="13" ry="14" fill="#2a6fdb"/>
    <!-- eyes -->
    <circle cx="55" cy="41" r="4" fill="#00e5ff"/>
    <circle cx="67" cy="41" r="4" fill="#00e5ff"/>
    <circle cx="55" cy="41" r="2" fill="#003850"/>
    <circle cx="67" cy="41" r="2" fill="#003850"/>
    <!-- smile -->
    <path d="M55 50 Q61 56 67 50" stroke="#00ff7f" stroke-width="2" fill="none" stroke-linecap="round"/>
    <!-- body -->
    <ellipse cx="61" cy="88" rx="26" ry="18" fill="#1e3d75"/>
    <ellipse cx="61" cy="82" rx="18" ry="12" fill="#2a6fdb"/>
    <!-- code icon -->
    <text x="61" y="86" text-anchor="middle" font-family="monospace" font-size="11" fill="#00e5ff" font-weight="bold">&lt;/&gt;</text>
    <!-- label -->
    <rect x="25" y="104" width="72" height="14" rx="7" fill="#00e5ff" opacity=".15"/>
    <text x="61" y="115" text-anchor="middle" font-family="monospace" font-size="9" fill="#00e5ff" font-weight="bold">BOT9315</text>
  </svg>`;

  const img = new Image();
  img.crossOrigin = 'anonymous';
  img.onload = function(){
    inner.innerHTML = '';
    img.style.cssText = 'width:100%;height:100%;object-fit:cover;border-radius:50%;display:block';
    inner.appendChild(img);
  };
  img.onerror = function(){
    inner.innerHTML = svgFallback;
  };
  img.src = 'https://avatars.githubusercontent.com/u/218440354?v=4';
  // Show fallback immediately, replace if/when image loads
  inner.innerHTML = svgFallback;
})();

// ═══ STARFIELD ═══
const cvs=document.getElementById('cvs'),ctx=cvs.getContext('2d');
let W,H,pts=[];
function initS(){
  W=cvs.width=innerWidth;H=cvs.height=innerHeight;
  pts=Array.from({length:220},()=>({
    x:Math.random()*W,y:Math.random()*H,r:Math.random()*1.3+.2,
    dy:Math.random()*.2+.05,o:Math.random(),do:Math.random()*.02-.01,
    c:Math.random()<.08?'0,229,255':'180,210,255'
  }));
}
function drawS(){
  ctx.clearRect(0,0,W,H);
  pts.forEach(p=>{
    p.o=Math.max(.05,Math.min(1,p.o+p.do));
    if(Math.random()<.001)p.do*=-1;
    p.y+=p.dy;if(p.y>H){p.y=0;p.x=Math.random()*W}
    ctx.beginPath();ctx.arc(p.x,p.y,p.r,0,Math.PI*2);
    ctx.fillStyle=`rgba(${p.c},${p.o})`;ctx.fill();
  });
  if(Math.random()<.004){
    const sx=Math.random()*W,sy=Math.random()*H*.5;
    const g=ctx.createLinearGradient(sx,sy,sx+90,sy+35);
    g.addColorStop(0,'rgba(0,229,255,0)');g.addColorStop(.5,'rgba(0,229,255,.7)');g.addColorStop(1,'rgba(0,229,255,0)');
    ctx.beginPath();ctx.moveTo(sx,sy);ctx.lineTo(sx+90,sy+35);
    ctx.strokeStyle=g;ctx.lineWidth=1.5;ctx.stroke();
  }
  requestAnimationFrame(drawS);
}
initS();drawS();window.addEventListener('resize',initS);

// ═══ TYPING ═══
const phrases=['Building AI-Powered Healthcare Systems 🤖','Python | Flask | JavaScript | HTML | CSS','Open Source Enthusiast 🌍','Solving real problems, one commit at a time.','async def life(): await coffee(); code()','print("Hello, World! 👋")'];
let pi=0,ci=0,del=false,pause=0;
const typ=document.getElementById('typ');
(function tick(){
  const cur=phrases[pi];
  if(!del){ci++;typ.innerHTML=cur.slice(0,ci)+'<span class="cur">█</span>';if(ci===cur.length){del=true;pause=55}}
  else{if(pause-->0){setTimeout(tick,30);return}ci--;typ.innerHTML=cur.slice(0,ci)+'<span class="cur">█</span>';if(ci===0){del=false;pi=(pi+1)%phrases.length}}
  setTimeout(tick,del?28:72);
})();

// ═══ TERMINAL ═══
const lines=[
  ['p','$ ','c','whoami'],
  ['o','','o','→ Ankush | Full Stack Dev | BOT9315'],
  ['p','$ ','c','cat skills.txt'],
  ['o','','v','Python ██████████ Flask ████████░░ JS ███████░░░'],
  ['p','$ ','c','git log --oneline -4'],
  ['o','','o','a1b2c3  🚀 AI-Driven Healthcare Anomaly Detection'],
  ['o','','o','d4e5f6  💊 MedSafe AI Real-Time Monitoring'],
  ['o','','o','7g8h9i  🐍 Rock-Paper-Scissors Python Game'],
  ['o','','o','0j1k2l  🐦 Flappy Bird Clone'],
  ['p','$ ','c','echo $STATUS'],
  ['o','','v','Open to exciting opportunities! 🎯'],
];
const tb=document.getElementById('tb');let ti=0;
(function addLine(){
  if(ti>=lines.length){ti=0;setTimeout(()=>{tb.innerHTML='';addLine()},1800);return}
  const [a,b,c,d]=lines[ti++];
  const s=document.createElement('span');s.className='tl';
  s.innerHTML=`<span class="t${a}">${b}</span><span class="t${c}">${d}</span>`;
  tb.appendChild(s);tb.scrollTop=tb.scrollHeight;
  setTimeout(addLine,650);
})();

// ═══ SKILLS ═══
setTimeout(()=>document.querySelectorAll('.sfill').forEach(e=>e.style.width=e.dataset.w+'%'),500);

// ═══ HEATMAP ═══
const hmap=document.getElementById('hmap');
const lvls=['#0c1428','#003d2b','#005c3b','#00a66a','#00ff7f'];
for(let i=0;i<364;i++){
  const d=document.createElement('div');d.className='hc';
  d.style.background=lvls[Math.random()<.28?0:Math.floor(Math.random()*5)];
  hmap.appendChild(d);
}

// ═══ GITHUB API ═══
const PINNED=['AI-Driven-Healthcare-Anomaly-Detection-System','Text-to-handwriting-master','Rock-Paper-Scissors-Game-using-python-code','Flappy-Bird-Game','MedSafe-AI-Real-Time-Healthcare-Monitoring-System'];
const FALLBACK=[
  {name:'AI-Driven-Healthcare-Anomaly-Detection-System',description:'AI-powered anomaly detection for healthcare data',language:'Python',stargazers_count:0,forks_count:0,html_url:'https://github.com/BOT9315/AI-Driven-Healthcare-Anomaly-Detection-System'},
  {name:'MedSafe-AI-Real-Time-Healthcare-Monitoring-System',description:'Real-time AI healthcare monitoring system',language:'Python',stargazers_count:0,forks_count:0,html_url:'https://github.com/BOT9315/MedSafe-AI-Real-Time-Healthcare-Monitoring-System'},
  {name:'Text-to-handwriting-master',description:'Convert digital text into beautiful handwriting style',language:'HTML',stargazers_count:0,forks_count:0,html_url:'https://github.com/BOT9315/Text-to-handwriting-master'},
  {name:'Flappy-Bird-Game',description:'Classic Flappy Bird game built with Python',language:'Python',stargazers_count:0,forks_count:0,html_url:'https://github.com/BOT9315/Flappy-Bird-Game'},
  {name:'Rock-Paper-Scissors-Game-using-python-code',description:'Fun Rock Paper Scissors game — FREE for all!',language:'Python',stargazers_count:0,forks_count:0,html_url:'https://github.com/BOT9315/Rock-Paper-Scissors-Game-using-python-code'},
  {name:'Weather-App',description:'Python-based weather application with live data',language:'Python',stargazers_count:0,forks_count:0,html_url:'https://github.com/BOT9315'},
  {name:'Portfolio-Website',description:'Personal portfolio built with HTML & CSS',language:'HTML',stargazers_count:0,forks_count:0,html_url:'https://github.com/BOT9315'},
  {name:'Flask-REST-API',description:'RESTful API built with Flask framework',language:'Python',stargazers_count:0,forks_count:0,html_url:'https://github.com/BOT9315'},
  {name:'To-Do-App',description:'Task manager web application',language:'JavaScript',stargazers_count:0,forks_count:0,html_url:'https://github.com/BOT9315'},
  {name:'Calculator',description:'Modern calculator with CSS animations',language:'HTML',stargazers_count:0,forks_count:0,html_url:'https://github.com/BOT9315'},
];
let allRepos=[];

async function fetchRepos(){
  try{
    const r=await fetch('https://api.github.com/users/BOT9315/repos?per_page=100&sort=updated',{headers:{Accept:'application/vnd.github.v3+json'}});
    if(!r.ok)throw new Error();
    allRepos=await r.json();
  }catch{allRepos=FALLBACK}
  renderStats();renderRepos('all');drawPie();
}

function animN(id,target){
  let v=0;const el=document.getElementById(id);
  const step=Math.max(1,Math.ceil(target/40));
  const t=setInterval(()=>{v=Math.min(v+step,target);el.textContent=v;if(v>=target)clearInterval(t)},35);
}
function renderStats(){
  const stars=allRepos.reduce((a,r)=>a+(r.stargazers_count||0),0);
  const forks=allRepos.reduce((a,r)=>a+(r.forks_count||0),0);
  const langs=new Set(allRepos.map(r=>r.language).filter(Boolean)).size;
  animN('sR',allRepos.length);animN('sS',stars);animN('sF',forks);animN('sL',langs);
}
function lClass(l){return{Python:'rPython',HTML:'rHTML',JavaScript:'rJavaScript',CSS:'rCSS'}[l]||'rdef'}
function renderRepos(filter){
  let list=filter==='all'?allRepos:allRepos.filter(r=>r.language===filter);
  list=list.slice().sort((a,b)=>(PINNED.includes(a.name)?0:1)-(PINNED.includes(b.name)?0:1));
  const rc=document.getElementById('rc');
  if(!list.length){rc.innerHTML='<div class="ldr">No repos found.</div>';return}
  rc.innerHTML=`<div class="rgrid">${list.map(r=>`
    <a class="rcard${PINNED.includes(r.name)?' pin':''}" href="${r.html_url||'https://github.com/BOT9315/'+r.name}" target="_blank">
      <div class="rname">📁 ${r.name.replace(/-/g,' ')}</div>
      <div class="rdesc">${r.description||'A project by Ankush · BOT9315'}</div>
      <div class="rmeta">
        ${r.language?`<span class="rl ${lClass(r.language)}">${r.language}</span>`:''}
        ${r.stargazers_count?`<span class="rstar">⭐ ${r.stargazers_count}</span>`:''}
        ${r.forks_count?`<span class="rstar" style="color:var(--cyan)">🍴 ${r.forks_count}</span>`:''}
      </div>
    </a>`).join('')}</div>`;
}
document.getElementById('ftabs').addEventListener('click',e=>{
  const t=e.target.closest('.ft');if(!t)return;
  document.querySelectorAll('.ft').forEach(x=>x.classList.remove('active'));
  t.classList.add('active');renderRepos(t.dataset.l);
});

// ═══ PIE ═══
function drawPie(){
  const lm={};allRepos.forEach(r=>{if(r.language)lm[r.language]=(lm[r.language]||0)+1});
  const total=Object.values(lm).reduce((a,b)=>a+b,0)||1;
  const clrs=['#00e5ff','#b56bff','#00ff7f','#ffd700','#ff6b35','#ec4899','#60a5fa'];
  const entries=Object.entries(lm).sort((a,b)=>b[1]-a[1]);
  const pc=document.getElementById('pieC'),pg=pc.getContext('2d');
  let angle=-Math.PI/2;
  entries.forEach(([,cnt],i)=>{
    const sl=(cnt/total)*Math.PI*2;
    pg.beginPath();pg.moveTo(70,70);pg.arc(70,70,65,angle,angle+sl);pg.closePath();
    pg.fillStyle=clrs[i%clrs.length];pg.fill();
    pg.strokeStyle='#050b18';pg.lineWidth=2;pg.stroke();
    angle+=sl;
  });
  pg.beginPath();pg.arc(70,70,30,0,Math.PI*2);pg.fillStyle='#050b18';pg.fill();
  pg.fillStyle='#00e5ff';pg.font='bold 8px monospace';pg.textAlign='center';
  pg.fillText('LANGS',70,68);pg.fillText(entries.length,70,78);
  document.getElementById('pieLeg').innerHTML=entries.map(([l,c],i)=>`
    <div class="ple">
      <div class="plc" style="background:${clrs[i%clrs.length]}"></div>
      <span>${l}</span>
      <span class="plv">${Math.round(c/total*100)}%</span>
    </div>`).join('');
}

fetchRepos();

// ═══ SNAKE ═══
const gc=document.getElementById('gcv'),gx=gc.getContext('2d');
const CELL=14,COLS=20,ROWS=20;
let snake,dir,food,score,hi=0,gloop,running=false;
function rCell(){return{x:Math.floor(Math.random()*COLS),y:Math.floor(Math.random()*ROWS)}}
function pFood(){do{food=rCell()}while(snake.some(s=>s.x===food.x&&s.y===food.y))}
function startGame(){
  snake=[{x:10,y:10},{x:9,y:10},{x:8,y:10}];
  dir={x:1,y:0};score=0;running=true;pFood();
  document.getElementById('gmsg').textContent='';
  clearInterval(gloop);gloop=setInterval(tick,115);
}
function tick(){
  const h={x:(snake[0].x+dir.x+COLS)%COLS,y:(snake[0].y+dir.y+ROWS)%ROWS};
  if(snake.some(s=>s.x===h.x&&s.y===h.y)){clearInterval(gloop);running=false;document.getElementById('gmsg').textContent=`💀 GAME OVER · Score: ${score}`;return}
  snake.unshift(h);
  if(h.x===food.x&&h.y===food.y){score++;if(score>hi)hi=score;document.getElementById('gsc').textContent=`SCORE: ${score}  |  BEST: ${hi}`;pFood()}
  else snake.pop();
  drawG();
}
function drawG(){
  gx.fillStyle='#030910';gx.fillRect(0,0,gc.width,gc.height);
  gx.strokeStyle='#0a1525';gx.lineWidth=.5;
  for(let i=0;i<COLS;i++){gx.beginPath();gx.moveTo(i*CELL,0);gx.lineTo(i*CELL,gc.height);gx.stroke()}
  for(let j=0;j<ROWS;j++){gx.beginPath();gx.moveTo(0,j*CELL);gx.lineTo(gc.width,j*CELL);gx.stroke()}
  gx.shadowColor='#ff6b35';gx.shadowBlur=10;gx.fillStyle='#ff6b35';
  gx.fillRect(food.x*CELL+2,food.y*CELL+2,CELL-4,CELL-4);gx.shadowBlur=0;
  snake.forEach((s,i)=>{
    if(i===0){gx.shadowColor='#00e5ff';gx.shadowBlur=14}
    const t=i/snake.length;
    gx.fillStyle=i===0?'#00e5ff':`hsl(${155+t*55},100%,${58-t*22}%)`;
    gx.fillRect(s.x*CELL+1,s.y*CELL+1,CELL-2,CELL-2);gx.shadowBlur=0;
  });
}
document.addEventListener('keydown',e=>{
  const m={ArrowUp:{x:0,y:-1},ArrowDown:{x:0,y:1},ArrowLeft:{x:-1,y:0},ArrowRight:{x:1,y:0},w:{x:0,y:-1},s:{x:0,y:1},a:{x:-1,y:0},d:{x:1,y:0}};
  if(e.key===' '){if(!running)startGame();e.preventDefault();return}
  const nd=m[e.key];if(nd&&!(nd.x===-dir.x&&nd.y===-dir.y)){dir=nd;e.preventDefault()}
});
let tx=null,ty=null;
gc.addEventListener('touchstart',e=>{tx=e.touches[0].clientX;ty=e.touches[0].clientY},{passive:true});
gc.addEventListener('touchend',e=>{
  if(!tx||!ty)return;
  const dx=e.changedTouches[0].clientX-tx,dy=e.changedTouches[0].clientY-ty;
  if(Math.abs(dx)>Math.abs(dy)){const nd=dx>0?{x:1,y:0}:{x:-1,y:0};if(nd.x!==dir.x)dir=nd}
  else{const nd=dy>0?{x:0,y:1}:{x:0,y:-1};if(nd.y!==dir.y)dir=nd}
  tx=ty=null;
},{passive:true});
drawG();
document.getElementById('yr').textContent=new Date().getFullYear();
</script>
</body>
</html>
