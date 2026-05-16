<style>


@import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;500;700&family=Clash+Display:wght@400;600;700&display=swap');
*{box-sizing:border-box;margin:0;padding:0}
body{background:#080b14;color:#c9d1e0;font-family:'JetBrains Mono',monospace;min-height:100vh;overflow-x:hidden}
.wrap{max-width:900px;margin:0 auto;padding:2rem 1.5rem 4rem}

.topbar{display:flex;align-items:center;justify-content:space-between;padding:.6rem 1rem;background:#0d1117;border:1px solid #1e2740;border-radius:8px;margin-bottom:2rem;font-size:11px;color:#4a5568;animation:fadeUp .5s ease both}
.topbar-dots{display:flex;gap:6px}
.dot-r{width:10px;height:10px;border-radius:50%;background:#ff5f57}
.dot-y{width:10px;height:10px;border-radius:50%;background:#febc2e}
.dot-g{width:10px;height:10px;border-radius:50%;background:#28c840}
.topbar-title{font-size:11px;color:#4a5568;letter-spacing:.06em}

.hero{display:grid;grid-template-columns:1fr auto;gap:1.5rem;align-items:start;margin-bottom:1.5rem;animation:fadeUp .5s .05s ease both}
.hero-left{}
.prompt-line{font-size:11px;color:#4ade80;letter-spacing:.12em;margin-bottom:.75rem;display:flex;align-items:center;gap:8px}
.prompt-line::before{content:'▶';font-size:9px;color:#4ade80}
.hero-name{font-family:'JetBrains Mono',monospace;font-size:clamp(2rem,5vw,3.4rem);font-weight:700;color:#e2e8f0;line-height:1.05;letter-spacing:-.02em;margin-bottom:.5rem}
.hero-name .accent{color:#38bdf8}
.hero-name .blink{display:inline-block;width:3px;height:.85em;background:#38bdf8;margin-left:4px;vertical-align:middle;animation:blink 1.1s step-end infinite}
@keyframes blink{0%,100%{opacity:1}50%{opacity:0}}
.hero-sub{font-size:12px;color:#64748b;letter-spacing:.04em;line-height:1.7}
.hero-sub span{color:#94a3b8}

.avatar{width:90px;height:90px;border-radius:10px;background:#0d1117;border:1px solid #1e3a5f;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:4px;flex-shrink:0;position:relative}
.avatar-initials{font-size:1.5rem;font-weight:700;color:#38bdf8;letter-spacing:-.02em}
.avatar-online{position:absolute;top:-4px;right:-4px;width:12px;height:12px;border-radius:50%;background:#4ade80;border:2px solid #080b14;animation:pulse 2s ease infinite}
@keyframes pulse{0%,100%{transform:scale(1);opacity:1}50%{transform:scale(.8);opacity:.6}}

.stats-row{display:grid;grid-template-columns:repeat(4,minmax(0,1fr));gap:.75rem;margin-bottom:1.5rem;animation:fadeUp .5s .1s ease both}
.stat-card{background:#0d1117;border:1px solid #1e2740;border-radius:8px;padding:.85rem 1rem;text-align:center;cursor:default;transition:border-color .2s}
.stat-card:hover{border-color:#38bdf8}
.stat-num{font-size:1.3rem;font-weight:700;color:#38bdf8;margin-bottom:2px}
.stat-lbl{font-size:10px;color:#4a5568;letter-spacing:.08em;text-transform:uppercase}

.visitor-bar{background:#0d1117;border:1px solid #1e2740;border-radius:8px;padding:.85rem 1.25rem;margin-bottom:1.5rem;display:flex;align-items:center;gap:1rem;animation:fadeUp .5s .12s ease both}
.vis-icon{font-size:18px;color:#a78bfa;flex-shrink:0}
.vis-label{font-size:11px;color:#64748b;flex:1}
.vis-count{font-size:1.1rem;font-weight:700;color:#a78bfa;min-width:60px;text-align:right}
.vis-progress{flex:2;height:4px;background:#1e2740;border-radius:2px;overflow:hidden}
.vis-fill{height:100%;background:#a78bfa;border-radius:2px;animation:grow 1.5s .8s ease both;transform-origin:left}
@keyframes grow{from{width:0}to{width:var(--w)}}
.vis-today{font-size:10px;color:#4ade80;background:rgba(74,222,128,.08);border:1px solid rgba(74,222,128,.2);padding:2px 8px;border-radius:4px;white-space:nowrap}

.section-hd{font-size:10px;color:#38bdf8;letter-spacing:.15em;text-transform:uppercase;margin-bottom:.75rem;display:flex;align-items:center;gap:.5rem}
.section-hd::after{content:'';flex:1;height:1px;background:#1e2740}

.code-block{background:#0d1117;border:1px solid #1e2740;border-radius:8px;padding:1.25rem;margin-bottom:1.5rem;font-size:12px;line-height:1.85;overflow-x:auto;animation:fadeUp .5s .15s ease both}
.ln{color:#2a3a50;margin-right:1rem;user-select:none;display:inline-block;min-width:16px;text-align:right}
.kw{color:#c792ea}.fn{color:#82aaff}.str{color:#c3e88d}.key{color:#38bdf8}.num{color:#f78c6c}.cm{color:#3a4f6e}.brace{color:#89ddff}

.two-col{display:grid;grid-template-columns:1fr 1fr;gap:.75rem;margin-bottom:1.5rem;animation:fadeUp .5s .2s ease both}
.panel{background:#0d1117;border:1px solid #1e2740;border-radius:8px;padding:1.1rem}
.chip-wrap{display:flex;flex-wrap:wrap;gap:5px;margin-top:.65rem}
.chip{font-size:10.5px;padding:3px 9px;border-radius:3px;border:1px solid #1e2740;color:#94a3b8;background:#111827;transition:all .18s;cursor:default}
.chip:hover{border-color:#38bdf8;color:#38bdf8;background:rgba(56,189,248,.06)}
.chip.pu{border-color:#312a5e;color:#a78bfa;background:rgba(167,139,250,.05)}
.chip.pu:hover{border-color:#a78bfa;background:rgba(167,139,250,.1)}
.chip.gn{border-color:#1a3320;color:#4ade80;background:rgba(74,222,128,.04)}
.chip.gn:hover{border-color:#4ade80}

.activity{background:#0d1117;border:1px solid #1e2740;border-radius:8px;padding:1.1rem;margin-bottom:1.5rem;animation:fadeUp .5s .25s ease both}
.act-grid{display:grid;grid-template-columns:repeat(7,1fr);gap:4px;margin-top:.75rem}
.act-cell{aspect-ratio:1;border-radius:2px;background:#111827;transition:background .15s;cursor:default}
.act-cell:hover{background:#38bdf8 !important}
.act-lv0{background:#111827}
.act-lv1{background:#1e3a5f}
.act-lv2{background:#1a5276}
.act-lv3{background:#1a8aad}
.act-lv4{background:#38bdf8}

.doing-grid{display:grid;grid-template-columns:1fr 1fr;gap:.6rem;margin-top:.65rem}
.doing-item{display:flex;align-items:flex-start;gap:8px;font-size:12px;color:#64748b;line-height:1.55;padding:.6rem .75rem;background:#0a0e1a;border:1px solid #1a2235;border-radius:6px;transition:border-color .2s}
.doing-item:hover{border-color:#38bdf8}
.doing-dot{width:5px;height:5px;border-radius:50%;flex-shrink:0;margin-top:5px}

.status-list{margin-top:.65rem}
.status-row{display:flex;align-items:center;gap:10px;padding:.55rem 0;border-bottom:1px solid #111827;font-size:12px;color:#64748b}
.status-row:last-child{border-bottom:none}
.status-row i{font-size:15px;color:#38bdf8;width:20px}
.sbadge{margin-left:auto;font-size:9.5px;padding:1px 7px;border-radius:3px;font-weight:500;letter-spacing:.04em}
.sb-green{background:rgba(74,222,128,.08);color:#4ade80;border:1px solid rgba(74,222,128,.18)}
.sb-blue{background:rgba(56,189,248,.08);color:#38bdf8;border:1px solid rgba(56,189,248,.18)}
.sb-pu{background:rgba(167,139,250,.08);color:#a78bfa;border:1px solid rgba(167,139,250,.18)}

.skill-bars{margin-top:.75rem;display:flex;flex-direction:column;gap:.6rem}
.skill-row{display:flex;align-items:center;gap:.75rem}
.skill-name{font-size:11px;color:#94a3b8;width:90px;flex-shrink:0}
.skill-track{flex:1;height:5px;background:#1a2235;border-radius:3px;overflow:hidden}
.skill-fill{height:100%;border-radius:3px;animation:grow 1.2s ease both}
.skill-pct{font-size:10px;color:#4a5568;width:28px;text-align:right}

.footer{display:flex;align-items:center;justify-content:space-between;padding-top:1.5rem;border-top:1px solid #1e2740;margin-top:.5rem;animation:fadeUp .5s .4s ease both}
.footer-cmd{font-size:11px;color:#2a3a50}
.action-btns{display:flex;gap:.5rem}
.btn{font-family:'JetBrains Mono',monospace;font-size:11px;padding:6px 14px;border-radius:5px;border:1px solid #1e2740;background:#0d1117;color:#94a3b8;cursor:pointer;transition:all .2s;display:flex;align-items:center;gap:5px}
.btn:hover{border-color:#38bdf8;color:#38bdf8;background:rgba(56,189,248,.06)}
.btn.primary{border-color:#1e3a5f;background:rgba(56,189,248,.08);color:#38bdf8}
.btn.primary:hover{background:rgba(56,189,248,.15)}

@keyframes fadeUp{from{opacity:0;transform:translateY(14px)}to{opacity:1;transform:translateY(0)}}
@media(max-width:560px){.stats-row{grid-template-columns:repeat(2,1fr)}.two-col,.doing-grid{grid-template-columns:1fr}.hero{grid-template-columns:1fr}.avatar{display:none}}
</style>

<div class="wrap">

<div class="topbar">
  <div class="topbar-dots"><div class="dot-r"></div><div class="dot-y"></div><div class="dot-g"></div></div>
  <span class="topbar-title">nisar-ahmed / README.md</span>
  <span style="font-size:11px;color:#4ade80">● live</span>
</div>

<div class="hero">
  <div class="hero-left">
    <div class="prompt-line"> &nbsp;|&nbsp; full-stack developer &nbsp;|&nbsp; open source</div>
    <div class="hero-name">Hi, I'm <span class="accent">Nisar</span><span class="blink"></span></div>
    <div class="hero-sub" style="margin-top:.5rem">
      <span>Co-Founder @ Inbyo Tech</span> &nbsp;·&nbsp; BSCS @ University of Balochistan<br>
      Building digital products with <span>React · Node.js · Django</span>
    </div>
  </div>
  <div class="avatar">
    <div class="avatar-online"></div>
    <div class="avatar-initials">NA</div>
    <div style="font-size:9px;color:#4a5568;letter-spacing:.06em">online</div>
  </div>
</div>

<div class="stats-row">
  <div class="stat-card"><div class="stat-num" id="s-repos">0</div><div class="stat-lbl">Repos</div></div>
  <div class="stat-card"><div class="stat-num" id="s-commits">0</div><div class="stat-lbl">Commits</div></div>
  <div class="stat-card"><div class="stat-num" id="s-prs">0</div><div class="stat-lbl">Pull Reqs</div></div>
  <div class="stat-card"><div class="stat-num" id="s-stars">0</div><div class="stat-lbl">Stars</div></div>
</div>

<div class="visitor-bar">
  <i class="ti ti-eye vis-icon" aria-hidden="true"></i>
  <div class="vis-label">
    <div style="font-size:11px;color:#94a3b8;margin-bottom:3px">Profile visitors</div>
    <div class="vis-progress"><div class="vis-fill" style="--w:72%;width:0"></div></div>
  </div>
  <div class="vis-count" id="v-count">0</div>
  <div class="vis-today" id="v-today">+0 today</div>
</div>

<div class="code-block">
  <div class="section-hd" style="margin-bottom:1rem">about.js</div>
  <div><span class="ln">1</span><span class="cm">// who am I?</span></div>
  <div><span class="ln">2</span><span class="kw">const</span> <span class="fn">nisar</span> <span class="brace">=</span> <span class="brace">{</span></div>
  <div><span class="ln">3</span>&nbsp;&nbsp;<span class="key">name</span><span class="brace">:</span> <span class="str">"Nisar Ahmed"</span><span class="brace">,</span></div>
  <div><span class="ln">4</span>&nbsp;&nbsp;<span class="key">location</span><span class="brace">:</span> <span class="str">"Quetta"</span><span class="brace">,</span></div>
  <div><span class="ln">5</span>&nbsp;&nbsp;<span class="key">role</span><span class="brace">:</span> <span class="str">"Co-Founder @ Inbyo Tech"</span><span class="brace">,</span></div>
  <div><span class="ln">6</span>&nbsp;&nbsp;<span class="key">education</span><span class="brace">:</span> <span class="str">"BSCS @ University of Balochistan"</span><span class="brace">,</span></div>
  <div><span class="ln">7</span>&nbsp;&nbsp;<span class="key">languages</span><span class="brace">:</span> <span class="brace">[</span><span class="str">"JS"</span><span class="brace">,</span> <span class="str">"C#"</span><span class="brace">,</span> <span class="str">"C"</span><span class="brace">,</span> <span class="str">"HTML"</span><span class="brace">,</span> <span class="str">"CSS"</span><span class="brace">]</span><span class="brace">,</span></div>
  <div><span class="ln">8</span>&nbsp;&nbsp;<span class="key">learning</span><span class="brace">:</span> <span class="brace">[</span><span class="str">"React"</span><span class="brace">,</span> <span class="str">"Node.js"</span><span class="brace">,</span> <span class="str">"System Design"</span><span class="brace">]</span><span class="brace">,</span></div>
  <div><span class="ln">9</span>&nbsp;&nbsp;<span class="key">openToWork</span><span class="brace">:</span> <span class="num">true</span><span class="brace">,</span></div>
  <div><span class="ln">10</span><span class="brace">}</span><span class="brace">;</span></div>
  <div style="margin-top:.5rem"><span class="ln">11</span></div>
  <div><span class="ln">12</span><span class="fn">console</span><span class="brace">.</span><span class="fn">log</span><span class="brace">(</span><span class="str">"Let's build something great together!"</span><span class="brace">)</span><span class="brace">;</span></div>
</div>

<div class="two-col">
  <div class="panel">
    <div class="section-hd">tech stack</div>
    <div style="font-size:10px;color:#4a5568;margin-bottom:.3rem;margin-top:.5rem">Frontend</div>
    <div class="chip-wrap"><span class="chip">JavaScript</span><span class="chip">React</span><span class="chip">HTML5</span><span class="chip">CSS3</span><span class="chip">Tailwind</span></div>
    <div style="font-size:10px;color:#4a5568;margin:.6rem 0 .3rem">Backend</div>
    <div class="chip-wrap"><span class="chip">Node.js</span><span class="chip">Django</span><span class="chip">REST API</span></div>
    <div style="font-size:10px;color:#4a5568;margin:.6rem 0 .3rem">Languages</div>
    <div class="chip-wrap"><span class="chip pu">C#</span><span class="chip pu">C</span><span class="chip pu">Python</span></div>
    <div style="font-size:10px;color:#4a5568;margin:.6rem 0 .3rem">Tools</div>
    <div class="chip-wrap"><span class="chip gn">Git</span><span class="chip gn">GitHub</span><span class="chip gn">VS Code</span><span class="chip gn">Linux</span></div>
  </div>
  <div class="panel">
    <div class="section-hd">skill levels</div>
    <div class="skill-bars">
      <div class="skill-row"><span class="skill-name">JavaScript</span><div class="skill-track"><div class="skill-fill" style="width:82%;background:#38bdf8;animation-delay:.1s"></div></div><span class="skill-pct">82%</span></div>
      <div class="skill-row"><span class="skill-name">HTML/CSS</span><div class="skill-track"><div class="skill-fill" style="width:90%;background:#4ade80;animation-delay:.15s"></div></div><span class="skill-pct">90%</span></div>
      <div class="skill-row"><span class="skill-name">React</span><div class="skill-track"><div class="skill-fill" style="width:65%;background:#38bdf8;animation-delay:.2s"></div></div><span class="skill-pct">65%</span></div>
      <div class="skill-row"><span class="skill-name">Node.js</span><div class="skill-track"><div class="skill-fill" style="width:60%;background:#4ade80;animation-delay:.25s"></div></div><span class="skill-pct">60%</span></div>
      <div class="skill-row"><span class="skill-name">Django</span><div class="skill-track"><div class="skill-fill" style="width:70%;background:#a78bfa;animation-delay:.3s"></div></div><span class="skill-pct">70%</span></div>
      <div class="skill-row"><span class="skill-name">C / C#</span><div class="skill-track"><div class="skill-fill" style="width:55%;background:#a78bfa;animation-delay:.35s"></div></div><span class="skill-pct">55%</span></div>
    </div>
  </div>
</div>

<div class="panel" style="margin-bottom:1.5rem;animation:fadeUp .5s .22s ease both">
  <div class="section-hd">what i do</div>
  <div class="doing-grid" style="margin-top:.65rem">
    <div class="doing-item"><div class="doing-dot" style="background:#38bdf8"></div><span>Design and ship user-friendly full-stack web apps</span></div>
    <div class="doing-item"><div class="doing-dot" style="background:#a78bfa"></div><span>Build & co-found digital products at Inbyo Tech</span></div>
    <div class="doing-item"><div class="doing-dot" style="background:#4ade80"></div><span>Contribute to open-source and dev communities</span></div>
    <div class="doing-item"><div class="doing-dot" style="background:#fb923c"></div><span>Study system design and scalable architecture</span></div>
  </div>
</div>

<div class="activity">
  <div class="section-hd">contribution activity</div>
  <div class="act-grid" id="act-grid"></div>
  <div style="display:flex;justify-content:flex-end;gap:4px;margin-top:.5rem;align-items:center">
    <span style="font-size:10px;color:#2a3a50">less</span>
    <div style="width:10px;height:10px;border-radius:2px;background:#111827"></div>
    <div style="width:10px;height:10px;border-radius:2px;background:#1e3a5f"></div>
    <div style="width:10px;height:10px;border-radius:2px;background:#1a8aad"></div>
    <div style="width:10px;height:10px;border-radius:2px;background:#38bdf8"></div>
    <span style="font-size:10px;color:#2a3a50">more</span>
  </div>
</div>

<div class="panel" style="margin-bottom:1.5rem;animation:fadeUp .5s .3s ease both">
  <div class="section-hd">currently</div>
  <div class="status-list">
    <div class="status-row"><i class="ti ti-building" aria-hidden="true"></i><span>Building products at Inbyo Tech</span><span class="sbadge sb-green">active</span></div>
    <div class="status-row"><i class="ti ti-book" aria-hidden="true"></i><span>Expanding in React & Node.js</span><span class="sbadge sb-blue">learning</span></div>
    <div class="status-row"><i class="ti ti-brand-github" aria-hidden="true"></i><span>Contributing to open source</span><span class="sbadge sb-green">ongoing</span></div>
    <div class="status-row"><i class="ti ti-server" aria-hidden="true"></i><span>Exploring system design patterns</span><span class="sbadge sb-pu">exploring</span></div>
    <div class="status-row"><i class="ti ti-briefcase" aria-hidden="true"></i><span>Open to collaboration & freelance</span><span class="sbadge sb-green">open</span></div>
  </div>
</div>

<div class="footer">
  <span class="footer-cmd"><span style="color:#38bdf8">~/nisar</span> $ git push origin main</span>
  <div class="action-btns">
    <button class="btn" onclick="this.innerHTML='<i class=\'ti ti-check\'></i> copied!'">
      <i class="ti ti-copy" aria-hidden="true"></i> copy profile
    </button>
    <button class="btn primary" onclick="sendPrompt('Generate a full GitHub README.md in markdown for Nisar Ahmed based on his profile')">
      <i class="ti ti-brand-github" aria-hidden="true"></i> generate README ↗
    </button>
  </div>
</div>

</div>

<script>
(function(){
  var targets={repos:34,commits:287,prs:12,stars:48};
  var dur=1200,steps=40,delay=dur/steps;
  Object.keys(targets).forEach(function(k){
    var el=document.getElementById('s-'+k),end=targets[k],cur=0;
    var t=setInterval(function(){
      cur=Math.min(cur+Math.ceil(end/steps),end);
      el.textContent=cur;
      if(cur>=end)clearInterval(t);
    },delay);
  });

  var vis=3841,todayVis=47;
  var vEl=document.getElementById('v-count'),tEl=document.getElementById('v-today');
  var vc=0,tc=0;
  var vt=setInterval(function(){
    vc=Math.min(vc+Math.ceil(vis/steps),vis);
    tc=Math.min(tc+Math.ceil(todayVis/steps),todayVis);
    vEl.textContent=vc.toLocaleString();
    tEl.textContent='+'+tc+' today';
    if(vc>=vis)clearInterval(vt);
  },delay);

  var levels=[0,1,2,3,4];
  var weights=[.35,.25,.2,.12,.08];
  function pick(){var r=Math.random(),c=0;for(var i=0;i<weights.length;i++){c+=weights[i];if(r<c)return levels[i];}return 0;}
  var grid=document.getElementById('act-grid');
  for(var i=0;i<84;i++){
    var d=document.createElement('div');
    var lv=pick();
    d.className='act-cell act-lv'+lv;
    d.title=lv===0?'No contributions':lv+' contribution'+(lv>1?'s':'');
    grid.appendChild(d);
  }
})();
</script>
