<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>CipherCrack Pro — Parallel SHA-256 Engine</title>
<link href="https://fonts.googleapis.com/css2?family=Share+Tech+Mono&family=Rajdhani:wght@300;400;600;700&display=swap" rel="stylesheet"/>
<style>
:root {
  --bg:#020408; --surface:#080d14; --surface2:#0c1420;
  --border:#0f2a3a; --border2:#1a3f5a;
  --accent:#00d4ff; --accent2:#00ff88; --accent3:#ff3366; --accent4:#ffcc00;
  --text:#c8e8f8; --muted:#3a6070;
  --glow:0 0 20px #00d4ff44; --glow2:0 0 20px #00ff8844;
}
*{box-sizing:border-box;margin:0;padding:0;}
body{background:var(--bg);color:var(--text);font-family:'Share Tech Mono',monospace;min-height:100vh;overflow-x:hidden;cursor:crosshair;}
body::before{content:'';position:fixed;inset:0;background-image:linear-gradient(rgba(0,212,255,0.025) 1px,transparent 1px),linear-gradient(90deg,rgba(0,212,255,0.025) 1px,transparent 1px);background-size:40px 40px;pointer-events:none;z-index:0;}
body::after{content:'';position:fixed;inset:0;background:repeating-linear-gradient(0deg,transparent,transparent 2px,rgba(0,0,0,0.07) 2px,rgba(0,0,0,0.07) 4px);pointer-events:none;z-index:1;}
.page{position:relative;z-index:2;max-width:960px;margin:0 auto;padding:2rem 1.5rem 4rem;}

.header{text-align:center;padding:2.5rem 0 2rem;position:relative;}
.header-badge{display:inline-block;font-family:'Rajdhani',sans-serif;font-size:11px;font-weight:600;letter-spacing:4px;color:var(--accent);border:1px solid var(--border2);padding:5px 16px;border-radius:2px;margin-bottom:1.25rem;text-transform:uppercase;position:relative;overflow:hidden;}
.header-badge::before{content:'';position:absolute;left:0;top:0;bottom:0;width:3px;background:var(--accent);box-shadow:var(--glow);}
.header h1{font-family:'Rajdhani',sans-serif;font-size:clamp(36px,6vw,68px);font-weight:700;letter-spacing:-1px;line-height:1;color:#fff;margin-bottom:0.4rem;}
.c{color:var(--accent);text-shadow:var(--glow);}
.pro{font-size:0.45em;color:var(--muted);letter-spacing:2px;}
.header-sub{font-size:11px;color:var(--muted);letter-spacing:3px;text-transform:uppercase;}
.corner{position:absolute;width:18px;height:18px;}
.corner-tl{top:0;left:0;border-top:2px solid var(--accent);border-left:2px solid var(--accent);}
.corner-tr{top:0;right:0;border-top:2px solid var(--accent);border-right:2px solid var(--accent);}
.corner-bl{bottom:0;left:0;border-bottom:2px solid var(--accent);border-left:2px solid var(--accent);}
.corner-br{bottom:0;right:0;border-bottom:2px solid var(--accent);border-right:2px solid var(--accent);}

.worker-bar{display:flex;gap:6px;align-items:center;background:var(--surface);border:1px solid var(--border);border-radius:4px;padding:10px 16px;margin-bottom:1rem;}
.worker-label{font-size:10px;letter-spacing:2px;color:var(--muted);text-transform:uppercase;margin-right:8px;white-space:nowrap;}
.worker-pills{display:flex;gap:6px;flex:1;flex-wrap:wrap;}
.worker-pill{flex:1;min-width:60px;height:28px;border-radius:3px;border:1px solid var(--border2);background:var(--bg);display:flex;align-items:center;justify-content:center;font-size:10px;color:var(--muted);letter-spacing:1px;transition:all 0.3s;position:relative;overflow:hidden;}
.worker-pill.active{border-color:var(--accent);background:rgba(0,212,255,0.08);color:var(--accent);box-shadow:inset 0 0 10px rgba(0,212,255,0.1);}
.worker-pill.active::before{content:'';position:absolute;top:0;left:-100%;width:60%;height:100%;background:linear-gradient(90deg,transparent,rgba(0,212,255,0.2),transparent);animation:shimmer 1.5s infinite;}
.worker-pill.done{border-color:var(--accent2);background:rgba(0,255,136,0.08);color:var(--accent2);}
.worker-pill.paused{border-color:var(--accent4);background:rgba(255,204,0,0.08);color:var(--accent4);}
.worker-pill.winner{border-color:var(--accent2);background:rgba(0,255,136,0.18);color:var(--accent2);box-shadow:0 0 12px rgba(0,255,136,0.35);}
@keyframes shimmer{to{left:200%;}}

.main-grid{display:grid;grid-template-columns:1fr 1fr;gap:1rem;margin-bottom:1rem;}
.panel{background:var(--surface);border:1px solid var(--border);border-radius:4px;padding:1.5rem;position:relative;transition:border-color 0.3s,box-shadow 0.3s;animation:fadeUp 0.4s ease both;}
.panel:nth-child(1){animation-delay:0.05s;}
.panel:nth-child(2){animation-delay:0.1s;}
.panel.full{grid-column:1/-1;}
.panel.running{border-color:rgba(0,212,255,0.35);box-shadow:0 0 30px rgba(0,212,255,0.06);}
.panel.paused-panel{border-color:rgba(255,204,0,0.35);box-shadow:0 0 30px rgba(255,204,0,0.06);}
@keyframes fadeUp{from{opacity:0;transform:translateY(10px);}to{opacity:1;transform:translateY(0);}}

.panel-header{display:flex;align-items:center;gap:10px;margin-bottom:1.25rem;padding-bottom:0.75rem;border-bottom:1px solid var(--border);}
.panel-dot{width:6px;height:6px;border-radius:50%;background:var(--accent);box-shadow:var(--glow);flex-shrink:0;}
.panel-dot.green{background:var(--accent2);box-shadow:var(--glow2);}
.panel-label{font-family:'Rajdhani',sans-serif;font-size:11px;font-weight:600;letter-spacing:3px;color:var(--muted);text-transform:uppercase;}

.field{margin-bottom:1rem;}
.field-label{font-size:10px;letter-spacing:2px;color:var(--muted);text-transform:uppercase;margin-bottom:8px;display:block;}
input[type=password],input[type=text],select,textarea{width:100%;background:var(--bg);border:1px solid var(--border);border-radius:3px;color:var(--text);padding:10px 14px;font-family:'Share Tech Mono',monospace;font-size:13px;outline:none;transition:border-color 0.2s,box-shadow 0.2s;appearance:none;}
input:focus,select:focus,textarea:focus{border-color:var(--accent);box-shadow:0 0 0 2px rgba(0,212,255,0.08);}
select option{background:#0a0a0a;}
textarea{resize:none;min-height:90px;line-height:1.8;font-size:12px;}

.tabs{display:flex;gap:6px;margin-bottom:1rem;}
.tab-btn{flex:1;padding:8px;border:1px solid var(--border);border-radius:3px;background:transparent;color:var(--muted);font-family:'Rajdhani',sans-serif;font-size:12px;font-weight:600;letter-spacing:2px;text-transform:uppercase;cursor:pointer;transition:all 0.2s;}
.tab-btn:hover{border-color:var(--border2);color:var(--text);}
.tab-btn.active{background:rgba(0,212,255,0.08);border-color:var(--accent);color:var(--accent);}

.btn-row{display:flex;gap:8px;margin-top:1.25rem;flex-wrap:wrap;}
.btn{padding:10px 18px;border-radius:3px;font-family:'Rajdhani',sans-serif;font-size:13px;font-weight:700;letter-spacing:2px;text-transform:uppercase;cursor:pointer;border:1px solid;transition:all 0.18s;}
.btn-start{background:rgba(0,212,255,0.1);border-color:var(--accent);color:var(--accent);flex:1;}
.btn-start:hover{background:rgba(0,212,255,0.22);box-shadow:var(--glow);}
.btn-pause{background:rgba(255,204,0,0.1);border-color:var(--accent4);color:var(--accent4);flex:1;display:none;}
.btn-pause:hover{background:rgba(255,204,0,0.22);}
.btn-resume{background:rgba(0,255,136,0.1);border-color:var(--accent2);color:var(--accent2);flex:1;display:none;}
.btn-resume:hover{background:rgba(0,255,136,0.22);box-shadow:var(--glow2);}
.btn-stop{background:rgba(255,51,102,0.1);border-color:var(--accent3);color:var(--accent3);display:none;padding:10px 14px;}
.btn-stop:hover{background:rgba(255,51,102,0.22);}
.btn-reset{background:transparent;border-color:var(--border2);color:var(--muted);padding:10px 14px;}
.btn-reset:hover{border-color:var(--muted);color:var(--text);}

.stats-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:8px;}
.stat-card{background:var(--bg);border:1px solid var(--border);border-radius:4px;padding:0.9rem 1rem;position:relative;overflow:hidden;}
.stat-card::before{content:'';position:absolute;top:0;left:0;right:0;height:2px;}
.stat-card.blue::before{background:var(--accent);box-shadow:var(--glow);}
.stat-card.green::before{background:var(--accent2);box-shadow:var(--glow2);}
.stat-card.yellow::before{background:var(--accent4);}
.stat-card.red::before{background:var(--accent3);}
.stat-lbl{font-size:9px;letter-spacing:2px;color:var(--muted);text-transform:uppercase;margin-bottom:6px;}
.stat-val{font-family:'Rajdhani',sans-serif;font-size:26px;font-weight:700;line-height:1;}
.stat-val.cyan{color:var(--accent);text-shadow:var(--glow);}
.stat-val.green{color:var(--accent2);text-shadow:var(--glow2);}
.stat-val.yellow{color:var(--accent4);}
.stat-val.white{color:#fff;}

.prog-section{margin-top:1rem;padding-top:1rem;border-top:1px solid var(--border);}
.prog-header{display:flex;justify-content:space-between;align-items:center;margin-bottom:8px;}
.prog-track{height:5px;background:var(--border);border-radius:3px;overflow:hidden;margin-bottom:10px;}
.prog-bar{height:5px;border-radius:3px;width:0%;background:linear-gradient(90deg,var(--accent),var(--accent2));box-shadow:0 0 8px rgba(0,212,255,0.5);transition:width 0.25s;}
.prog-bar.paused-bar{background:linear-gradient(90deg,var(--accent4),#ff9900);box-shadow:0 0 8px rgba(255,204,0,0.4);}

.guess-display{font-size:20px;color:var(--accent);letter-spacing:5px;min-height:28px;font-family:'Share Tech Mono',monospace;word-break:break-all;margin-top:4px;}
.guess-display.paused{color:var(--accent4);}

.status-row{display:flex;align-items:center;gap:8px;margin-top:1rem;padding-top:1rem;border-top:1px solid var(--border);}
.status-dot{width:8px;height:8px;border-radius:50%;background:var(--muted);transition:all 0.3s;flex-shrink:0;}
@keyframes pulseC{0%,100%{box-shadow:0 0 4px var(--accent);}50%{box-shadow:0 0 14px var(--accent);}}
@keyframes pulseY{0%,100%{box-shadow:0 0 4px var(--accent4);}50%{box-shadow:0 0 14px var(--accent4);}}
.pulse-cyan{animation:pulseC 1s ease-in-out infinite;}
.pulse-yellow{animation:pulseY 1s ease-in-out infinite;}
.status-txt{font-family:'Rajdhani',sans-serif;font-size:13px;letter-spacing:2px;text-transform:uppercase;}
.checkpoint-txt{margin-left:auto;font-size:10px;color:var(--muted);}

.pause-indicator{display:none;background:rgba(255,204,0,0.05);border:1px solid rgba(255,204,0,0.3);border-radius:4px;padding:10px 16px;margin-bottom:1rem;font-size:12px;color:var(--accent4);letter-spacing:1px;gap:10px;align-items:center;}
.pause-indicator.show{display:flex;}

.result-banner{display:none;background:rgba(0,255,136,0.05);border:1px solid var(--accent2);border-radius:4px;padding:1.25rem 1.5rem;margin-bottom:1rem;position:relative;overflow:hidden;gap:1.5rem;align-items:center;}
.result-banner::before{content:'';position:absolute;left:0;top:0;bottom:0;width:4px;background:var(--accent2);box-shadow:var(--glow2);}
.result-banner.show{display:flex;}
.result-lbl{font-size:10px;letter-spacing:2px;color:var(--accent2);margin-bottom:4px;}
.result-pwd{font-family:'Rajdhani',sans-serif;font-size:34px;font-weight:700;color:#fff;letter-spacing:3px;}

.hash-box{background:var(--bg);border:1px solid var(--border);border-radius:3px;padding:9px 13px;font-size:10px;color:var(--muted);word-break:break-all;letter-spacing:1px;margin-top:8px;min-height:40px;line-height:1.7;}

.terminal{background:#020509;border:1px solid var(--border);border-radius:4px;overflow:hidden;}
.terminal-bar{background:var(--surface2);border-bottom:1px solid var(--border);padding:8px 14px;display:flex;align-items:center;gap:8px;}
.t-dot{width:10px;height:10px;border-radius:50%;}
.t-dot.r{background:#ff5f56;}.t-dot.y{background:#ffbd2e;}.t-dot.g{background:#27c93f;}
.terminal-title{font-family:'Rajdhani',sans-serif;font-size:11px;letter-spacing:2px;color:var(--muted);flex:1;margin-left:4px;}
.wc-badge{font-size:10px;color:var(--accent);border:1px solid var(--border2);padding:2px 8px;border-radius:2px;letter-spacing:1px;}
.terminal-body{padding:1rem 1.25rem;min-height:180px;max-height:260px;overflow-y:auto;font-size:12px;line-height:2;}
.terminal-body::-webkit-scrollbar{width:4px;}
.terminal-body::-webkit-scrollbar-thumb{background:var(--border2);border-radius:2px;}
.t-prompt{color:var(--muted);}
.t-info{color:#4a8faa;}
.t-success{color:var(--accent2);font-weight:700;font-size:13px;}
.t-fail{color:var(--accent3);}
.t-worker{color:#1e6e3a;}
.t-pause{color:var(--accent4);}
.t-hash{color:#1e3f50;font-size:10px;word-break:break-all;}
.t-sep{color:#0d2030;}
.blink{animation:blink 1s step-end infinite;}
@keyframes blink{50%{opacity:0;}}

@media(max-width:640px){
  .main-grid{grid-template-columns:1fr;}
  .header h1{font-size:36px;}
}
</style>
</head>
<body>
<div class="page">

  <div class="header">
    <div class="corner corner-tl"></div><div class="corner corner-tr"></div>
    <div class="corner corner-bl"></div><div class="corner corner-br"></div>
    <div class="header-badge">Parallel SHA-256 · Web Workers · Pause/Resume · v3.1</div>
    <h1>CIPHER<span class="c">CRACK</span> <span class="pro">PRO</span></h1>
    <p class="header-sub">Multi-threaded Brute Force Engine — Educational Demo</p>
  </div>

  <div class="worker-bar">
    <span class="worker-label">Workers</span>
    <div class="worker-pills" id="worker-pills"></div>
  </div>

  <div class="pause-indicator" id="pause-indicator">
    <span>⏸</span>
    <span>Attack paused — all workers suspended. Click Resume to continue from checkpoint.</span>
  </div>

  <div class="result-banner" id="result-banner">
    <div style="font-size:28px;filter:drop-shadow(0 0 10px #00ff88)">⬡</div>
    <div>
      <div class="result-lbl">PASSWORD CRACKED</div>
      <div class="result-pwd" id="result-pwd">—</div>
    </div>
  </div>

  <div class="main-grid">

    <div class="panel" id="config-panel">
      <div class="panel-header">
        <div class="panel-dot"></div>
        <span class="panel-label">Target Config</span>
      </div>

      <div class="field">
        <label class="field-label">Target Password (max 5 chars)</label>
        <input type="password" id="pwd" placeholder="Enter password to crack..." maxlength="5"/>
        <div class="hash-box" id="hash-preview">// sha-256 hash will appear here as you type</div>
      </div>

      <div class="field">
        <label class="field-label">Attack Mode</label>
        <div class="tabs">
          <button class="tab-btn active" id="tab-brute" onclick="setMode('brute')">Brute Force</button>
          <button class="tab-btn" id="tab-dict" onclick="setMode('dict')">Dictionary</button>
        </div>
      </div>

      <div id="brute-opts">
        <div class="field">
          <label class="field-label">Charset</label>
          <select id="charset">
            <option value="lower">a-z  (26 chars) — fastest</option>
            <option value="alpha">a-z A-Z  (52 chars)</option>
            <option value="alnum">Alphanumeric  (62 chars)</option>
            <option value="full">Full printable  (94 chars)</option>
          </select>
        </div>
        <div class="field">
          <label class="field-label">Parallel Workers</label>
          <select id="worker-count" onchange="rebuildWorkerPills()">
            <option value="2">2 Workers</option>
            <option value="4" selected>4 Workers (recommended)</option>
            <option value="6">6 Workers</option>
            <option value="8">8 Workers</option>
          </select>
        </div>
      </div>

      <div id="dict-opts" style="display:none;">
        <div class="field">
          <label class="field-label">Wordlist (one per line)</label>
          <textarea id="wordlist" placeholder="password&#10;hello&#10;admin&#10;123456&#10;qwerty&#10;abc&#10;test&#10;pass&#10;root&#10;user"></textarea>
        </div>
      </div>

      <div class="btn-row">
        <button class="btn btn-start"  id="btn-start"  onclick="startCrack()">&#9654; Execute</button>
        <button class="btn btn-pause"  id="btn-pause"  onclick="pauseCrack()">&#9646;&#9646; Pause</button>
        <button class="btn btn-resume" id="btn-resume" onclick="resumeCrack()">&#9654; Resume</button>
        <button class="btn btn-stop"   id="btn-stop"   onclick="stopCrack()">&#9632;</button>
        <button class="btn btn-reset"  onclick="resetAll()">&#8635;</button>
      </div>
    </div>

    <div class="panel">
      <div class="panel-header">
        <div class="panel-dot green"></div>
        <span class="panel-label">Live Metrics</span>
      </div>
      <div class="stats-grid">
        <div class="stat-card blue">
          <div class="stat-lbl">Total Attempts</div>
          <div class="stat-val cyan" id="s-attempts">0</div>
        </div>
        <div class="stat-card green">
          <div class="stat-lbl">Speed</div>
          <div class="stat-val green" id="s-speed">0/s</div>
        </div>
        <div class="stat-card yellow">
          <div class="stat-lbl">Elapsed</div>
          <div class="stat-val yellow" id="s-time">0.0s</div>
        </div>
        <div class="stat-card red">
          <div class="stat-lbl">Progress</div>
          <div class="stat-val white" id="s-pct">0%</div>
        </div>
      </div>
      <div class="prog-section">
        <div class="prog-header">
          <span class="field-label" style="margin:0;">Scan progress</span>
          <span style="font-size:10px;color:var(--muted);" id="prog-detail">// idle</span>
        </div>
        <div class="prog-track"><div class="prog-bar" id="prog-bar"></div></div>
        <div class="field-label" style="margin-bottom:4px;">Current guess</div>
        <div class="guess-display" id="guess-display">&nbsp;</div>
      </div>
      <div class="status-row">
        <div class="status-dot" id="status-dot"></div>
        <span class="status-txt" id="status-txt">Idle</span>
        <span class="checkpoint-txt" id="checkpoint-txt"></span>
      </div>
    </div>

    <div class="panel full" style="padding:0;">
      <div class="terminal">
        <div class="terminal-bar">
          <div class="t-dot r"></div><div class="t-dot y"></div><div class="t-dot g"></div>
          <span class="terminal-title">CIPHERCRACK PRO — ENGINE OUTPUT</span>
          <span class="wc-badge" id="wc-badge">4 WORKERS</span>
        </div>
        <div class="terminal-body" id="log">
          <div><span class="t-prompt">root@ciphercrack:~$ </span><span class="t-info blink">_</span></div>
        </div>
      </div>
    </div>

  </div>
</div>

<script>
/* ─────────────────────────────────────────────────────────
   WORKER SOURCE (inlined as Blob — no external file needed)

   How it works:
   - Each worker receives a charset slice (startChar..endChar)
   - For every length 1..maxLen it iterates: first char from
     its slice, remaining chars across the full charset
   - Pause = sets a flag; the loop polls it via setTimeout(0)
   - Resume = clears the flag, loop continues automatically
   ───────────────────────────────────────────────────────── */
const WORKER_SRC = `
'use strict';

var paused = false;

async function sha256hex(str) {
  var enc = new TextEncoder();
  var buf = await crypto.subtle.digest('SHA-256', enc.encode(str));
  var arr = new Uint8Array(buf);
  var hex = '';
  for (var i = 0; i < arr.length; i++) {
    hex += ('0' + arr[i].toString(16)).slice(-2);
  }
  return hex;
}

function yieldToMessages() {
  return new Promise(function(resolve) { setTimeout(resolve, 0); });
}

self.onmessage = async function(e) {
  var d = e.data;
  if (d.type === 'pause')  { paused = true;  return; }
  if (d.type === 'resume') { paused = false; return; }
  if (d.type === 'stop')   { self.close();   return; }

  if (d.type === 'crack') {
    var charset   = d.charset;
    var maxLen    = d.maxLen;
    var target    = d.targetHash;
    var startChar = d.startChar;
    var endChar   = d.endChar;
    var id        = d.id;
    var clen      = charset.length;
    var attempts  = 0;

    for (var len = 1; len <= maxLen; len++) {
      for (var fi = startChar; fi < endChar; fi++) {

        if (len === 1) {
          /* pause check */
          while (paused) { await yieldToMessages(); }
          attempts++;
          var w1 = charset[fi];
          var h1 = await sha256hex(w1);
          self.postMessage({ type:'progress', id:id, attempts:attempts, current:w1 });
          if (h1 === target) {
            self.postMessage({ type:'found', id:id, password:w1, attempts:attempts });
            return;
          }
          continue;
        }

        /* Build indices array for positions 1..(len-1) */
        var indices = [];
        for (var x = 0; x < len - 1; x++) indices.push(0);

        while (true) {
          while (paused) { await yieldToMessages(); }

          /* Build word */
          var word = charset[fi];
          for (var k = 0; k < len - 1; k++) word += charset[indices[k]];

          attempts++;

          if (attempts % 120 === 0) {
            self.postMessage({ type:'progress', id:id, attempts:attempts, current:word });
            await yieldToMessages(); /* let pause msgs arrive */
          }

          var h = await sha256hex(word);
          if (h === target) {
            self.postMessage({ type:'found', id:id, password:word, attempts:attempts });
            return;
          }

          /* Increment rightmost index */
          var pos = len - 2;
          while (pos >= 0) {
            indices[pos]++;
            if (indices[pos] < clen) { break; }
            indices[pos] = 0;
            pos--;
          }
          if (pos < 0) break; /* exhausted this first-char slice */
        }
      }
    }
    self.postMessage({ type:'done', id:id, attempts:attempts });
  }
};
`;

/* ──────────────────────────────────────────
   Charsets
   ────────────────────────────────────────── */
var CHARSETS = {
  lower: 'abcdefghijklmnopqrstuvwxyz',
  alpha: 'abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ',
  alnum: 'abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789',
  full:  'abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789!@#$%^&*()-_=+[]{}|;:\'",.<>?/`~'
};

/* ──────────────────────────────────────────
   App state
   ────────────────────────────────────────── */
var mode       = 'brute';
var workers    = [];
var wAttempts  = [];
var totalAtt   = 0;
var numWorkers = 4;
var startTime  = 0;
var timerRef   = null;
var isRunning  = false;
var isPaused   = false;
var doneCount  = 0;
var accTime    = 0;   /* accumulated running seconds before last pause */
var blobURL    = null;
var activeWorkerCount = 0; /* how many workers were actually spawned */

function getWorkerURL() {
  if (!blobURL) {
    var blob = new Blob([WORKER_SRC], { type: 'application/javascript' });
    blobURL = URL.createObjectURL(blob);
  }
  return blobURL;
}

/* ──────────────────────────────────────────
   SHA-256 for main thread (hash preview)
   ────────────────────────────────────────── */
async function sha256hex(str) {
  var buf = await crypto.subtle.digest('SHA-256', new TextEncoder().encode(str));
  return Array.from(new Uint8Array(buf)).map(function(b){ return ('0'+b.toString(16)).slice(-2); }).join('');
}

document.getElementById('pwd').addEventListener('input', async function() {
  var v = this.value;
  var el = document.getElementById('hash-preview');
  if (!v) { el.textContent = '// sha-256 hash will appear here as you type'; return; }
  el.textContent = '...';
  el.textContent = await sha256hex(v);
});

/* ──────────────────────────────────────────
   Worker pill UI
   ────────────────────────────────────────── */
function rebuildWorkerPills() {
  numWorkers = parseInt(document.getElementById('worker-count').value);
  document.getElementById('wc-badge').textContent = numWorkers + ' WORKERS';
  var c = document.getElementById('worker-pills');
  c.innerHTML = '';
  for (var i = 0; i < numWorkers; i++) {
    var d = document.createElement('div');
    d.className = 'worker-pill';
    d.id = 'wp-' + i;
    d.textContent = 'W'+(i+1)+' · idle';
    c.appendChild(d);
  }
}
rebuildWorkerPills();

function setPill(id, state, label) {
  var el = document.getElementById('wp-' + id);
  if (!el) return;
  el.className = 'worker-pill' + (state ? ' '+state : '');
  el.textContent = 'W'+(id+1)+' · '+label;
}

/* ──────────────────────────────────────────
   Mode switch
   ────────────────────────────────────────── */
function setMode(m) {
  mode = m;
  document.getElementById('tab-brute').classList.toggle('active', m==='brute');
  document.getElementById('tab-dict').classList.toggle('active',  m==='dict');
  document.getElementById('brute-opts').style.display = m==='brute' ? '' : 'none';
  document.getElementById('dict-opts').style.display  = m==='dict'  ? '' : 'none';
}

/* ──────────────────────────────────────────
   Logging
   ────────────────────────────────────────── */
function log(msg, cls) {
  cls = cls || 't-info';
  var el = document.getElementById('log');
  var div = document.createElement('div');
  div.innerHTML = '<span class="t-prompt">$ </span><span class="'+cls+'">'+msg+'</span>';
  el.appendChild(div);
  el.scrollTop = el.scrollHeight;
}

/* ──────────────────────────────────────────
   UI state helpers
   ────────────────────────────────────────── */
function setStatus(txt, color, pulse) {
  var dot   = document.getElementById('status-dot');
  var label = document.getElementById('status-txt');
  label.textContent = txt;
  label.style.color = color || 'var(--muted)';
  dot.style.background = color || 'var(--muted)';
  dot.className = 'status-dot' + (pulse ? ' pulse-'+pulse : '');
}

function setProgress(pct, current) {
  if (pct >= 0) {
    var p = Math.min(100, Math.max(0, pct));
    document.getElementById('prog-bar').style.width = p+'%';
    document.getElementById('s-pct').textContent = Math.round(p)+'%';
  }
  if (current !== undefined) {
    document.getElementById('prog-detail').textContent = 'scanning: '+current;
    document.getElementById('guess-display').textContent = current;
  }
}

function showButtons(state) {
  document.getElementById('btn-start').style.display  = state==='idle'    ? '' : 'none';
  document.getElementById('btn-pause').style.display  = state==='running' ? '' : 'none';
  document.getElementById('btn-resume').style.display = state==='paused'  ? '' : 'none';
  document.getElementById('btn-stop').style.display   = (state==='running'||state==='paused') ? '' : 'none';
}

function updateStats() {
  var elapsed = accTime + (isPaused ? 0 : (Date.now() - startTime) / 1000);
  var total   = 0;
  for (var i = 0; i < wAttempts.length; i++) total += wAttempts[i];
  totalAtt = total;
  var spd = elapsed > 0 ? Math.round(total / elapsed) : 0;

  document.getElementById('s-attempts').textContent =
    total >= 1000000 ? (total/1000000).toFixed(2)+'M' :
    total >= 1000    ? (total/1000).toFixed(1)+'K' : String(total);

  document.getElementById('s-speed').textContent =
    spd >= 1000 ? Math.round(spd/1000)+'K/s' : spd+'/s';

  document.getElementById('s-time').textContent = elapsed.toFixed(1)+'s';
}

function killAllWorkers() {
  for (var i = 0; i < workers.length; i++) {
    try { workers[i].terminate(); } catch(e) {}
  }
  workers = [];
}

function finishUp() {
  showButtons('idle');
  document.getElementById('config-panel').classList.remove('running','paused-panel');
  document.getElementById('pause-indicator').classList.remove('show');
}

/* ──────────────────────────────────────────
   DICTIONARY ATTACK (main thread)
   ────────────────────────────────────────── */
async function runDictionary(targetHash) {
  var raw   = document.getElementById('wordlist').value;
  var words = raw.split('\n').map(function(w){ return w.trim(); }).filter(function(w){ return w.length > 0; });

  if (!words.length) {
    log('ERROR: wordlist is empty.', 't-fail');
    finishUp(); return;
  }

  log('loaded '+words.length+' words.', 't-info');
  wAttempts = [0];
  setPill(0, 'active', 'running');

  for (var i = 0; i < words.length; i++) {
    if (!isRunning) return;

    while (isPaused) {
      await new Promise(function(r){ setTimeout(r, 80); });
    }

    wAttempts[0] = i + 1;
    var pct = ((i+1) / words.length) * 100;
    setProgress(pct, words[i]);

    if (i % 25 === 0) await new Promise(function(r){ setTimeout(r, 0); });

    var h = await sha256hex(words[i]);
    if (h === targetHash) {
      clearInterval(timerRef);
      updateStats();
      isRunning = false;
      showCracked(words[i], undefined);
      return;
    }
  }

  clearInterval(timerRef);
  updateStats();
  isRunning = false;
  showNotFound();
}

/* ──────────────────────────────────────────
   BRUTE FORCE — Web Workers
   ────────────────────────────────────────── */
function runBrute(targetHash, pwdLen) {
  var cs    = CHARSETS[document.getElementById('charset').value];
  var slice = Math.ceil(cs.length / numWorkers);

  doneCount = 0;
  workers   = [];
  wAttempts = [];
  activeWorkerCount = 0;

  for (var i = 0; i < numWorkers; i++) {
    var startChar = i * slice;
    var endChar   = Math.min(cs.length, (i+1) * slice);
    if (startChar >= cs.length) continue;

    activeWorkerCount++;
    wAttempts.push(0);
    var workerIdx = wAttempts.length - 1;

    log('W'+(i+1)+' → chars ['+cs[startChar]+'..'+cs[endChar-1]+']', 't-worker');
    setPill(i, 'active', 'running');

    var w = new Worker(getWorkerURL());
    workers.push(w);

    /* IIFE to capture i and workerIdx correctly */
    (function(wid, widx, worker) {
      worker.onmessage = function(e) {
        var d = e.data;

        if (d.type === 'progress') {
          wAttempts[widx] = d.attempts;
          document.getElementById('guess-display').textContent = d.current;
          document.getElementById('prog-detail').textContent = 'W'+(wid+1)+': '+d.current;
        }
        else if (d.type === 'found') {
          if (!isRunning) return; /* another worker already found it */
          wAttempts[widx] = d.attempts;
          isRunning = false;
          killAllWorkers();
          clearInterval(timerRef);
          updateStats();
          showCracked(d.password, wid);
        }
        else if (d.type === 'done') {
          wAttempts[widx] = d.attempts;
          setPill(wid, 'done', 'done');
          doneCount++;
          if (doneCount >= activeWorkerCount) {
            if (!isRunning) return;
            isRunning = false;
            clearInterval(timerRef);
            updateStats();
            showNotFound();
          }
        }
      };

      worker.onerror = function(err) {
        log('W'+(wid+1)+' error: '+(err.message||'unknown'), 't-fail');
      };

      worker.postMessage({
        type:       'crack',
        charset:    cs,
        maxLen:     pwdLen,
        targetHash: targetHash,
        startChar:  startChar,
        endChar:    endChar,
        id:         wid
      });
    })(i, workerIdx, w);
  }
}

/* ──────────────────────────────────────────
   START
   ────────────────────────────────────────── */
async function startCrack() {
  var pwd = document.getElementById('pwd').value;
  if (!pwd)        { log('ERROR: enter a target password.', 't-fail'); return; }
  if (pwd.length > 5) { log('ERROR: max 5 characters for demo speed.', 't-fail'); return; }

  /* Clear everything */
  document.getElementById('log').innerHTML = '';
  document.getElementById('result-banner').classList.remove('show');
  document.getElementById('pause-indicator').classList.remove('show');
  document.getElementById('config-panel').classList.remove('running','paused-panel');
  document.getElementById('checkpoint-txt').textContent = '';
  document.getElementById('prog-bar').className = 'prog-bar';
  document.getElementById('prog-bar').style.width = '0%';
  document.getElementById('guess-display').className = 'guess-display';
  document.getElementById('guess-display').innerHTML = '&nbsp;';
  document.getElementById('s-pct').textContent = '0%';
  document.getElementById('prog-detail').textContent = '// idle';

  numWorkers = parseInt(document.getElementById('worker-count').value);
  isRunning  = true;
  isPaused   = false;
  doneCount  = 0;
  totalAtt   = 0;
  accTime    = 0;
  startTime  = Date.now();

  var targetHash = await sha256hex(pwd);

  log('='.repeat(52), 't-sep');
  log('CIPHERCRACK PRO v3.1 — ENGINE START', 't-info');
  log('mode     : '+(mode==='brute' ? 'BRUTE FORCE ('+numWorkers+' WORKERS)' : 'DICTIONARY'), 't-info');
  log('target   : '+pwd.length+' char(s)', 't-info');
  log('sha-256  : <span class="t-hash">'+targetHash+'</span>', 't-info');
  log('-'.repeat(52), 't-sep');

  showButtons('running');
  document.getElementById('config-panel').classList.add('running');
  setStatus('Running', 'var(--accent)', 'cyan');

  timerRef = setInterval(updateStats, 250);

  if (mode === 'dict') {
    runDictionary(targetHash);
  } else {
    runBrute(targetHash, pwd.length);
  }
}

/* ──────────────────────────────────────────
   PAUSE
   ────────────────────────────────────────── */
function pauseCrack() {
  if (!isRunning || isPaused) return;
  isPaused = true;

  workers.forEach(function(w){ w.postMessage({ type:'pause' }); });

  accTime  += (Date.now() - startTime) / 1000;
  clearInterval(timerRef);
  updateStats();

  document.getElementById('config-panel').classList.remove('running');
  document.getElementById('config-panel').classList.add('paused-panel');
  document.getElementById('pause-indicator').classList.add('show');
  document.getElementById('prog-bar').classList.add('paused-bar');
  document.getElementById('guess-display').classList.add('paused');
  document.getElementById('checkpoint-txt').textContent = 'checkpoint @ '+totalAtt.toLocaleString()+' attempts';

  showButtons('paused');
  setStatus('Paused', 'var(--accent4)', 'yellow');

  for (var i = 0; i < numWorkers; i++) {
    var el = document.getElementById('wp-'+i);
    if (el && el.classList.contains('active')) setPill(i, 'paused', 'paused');
  }
  log('PAUSED at '+totalAtt.toLocaleString()+' attempts — checkpoint saved.', 't-pause');
}

/* ──────────────────────────────────────────
   RESUME
   ────────────────────────────────────────── */
function resumeCrack() {
  if (!isPaused) return;
  isPaused  = false;
  startTime = Date.now();

  workers.forEach(function(w){ w.postMessage({ type:'resume' }); });

  document.getElementById('config-panel').classList.remove('paused-panel');
  document.getElementById('config-panel').classList.add('running');
  document.getElementById('pause-indicator').classList.remove('show');
  document.getElementById('prog-bar').classList.remove('paused-bar');
  document.getElementById('guess-display').classList.remove('paused');
  document.getElementById('checkpoint-txt').textContent = '';

  showButtons('running');
  setStatus('Running', 'var(--accent)', 'cyan');

  for (var i = 0; i < numWorkers; i++) {
    var el = document.getElementById('wp-'+i);
    if (el && el.classList.contains('paused')) setPill(i, 'active', 'running');
  }
  log('RESUMED from checkpoint.', 't-info');
  timerRef = setInterval(updateStats, 250);
}

/* ──────────────────────────────────────────
   STOP
   ────────────────────────────────────────── */
function stopCrack() {
  if (!isRunning && !isPaused) return;
  isRunning = false;
  isPaused  = false;
  workers.forEach(function(w){ w.postMessage({ type:'stop' }); });
  killAllWorkers();
  clearInterval(timerRef);
  accTime += (Date.now() - startTime) / 1000;
  updateStats();
  setStatus('Stopped', 'var(--accent3)', null);
  for (var i = 0; i < numWorkers; i++) setPill(i, '', 'idle');
  log('ABORTED by user.', 't-fail');
  finishUp();
}

/* ──────────────────────────────────────────
   RESET
   ────────────────────────────────────────── */
function resetAll() {
  isRunning = false; isPaused = false;
  killAllWorkers();
  clearInterval(timerRef);
  wAttempts = []; totalAtt = 0; accTime = 0;

  document.getElementById('log').innerHTML =
    '<div><span class="t-prompt">root@ciphercrack:~$ </span><span class="t-info blink">_</span></div>';
  document.getElementById('s-attempts').textContent = '0';
  document.getElementById('s-speed').textContent    = '0/s';
  document.getElementById('s-time').textContent     = '0.0s';
  document.getElementById('s-pct').textContent      = '0%';
  document.getElementById('prog-bar').style.width   = '0%';
  document.getElementById('prog-bar').className     = 'prog-bar';
  document.getElementById('prog-detail').textContent = '// idle';
  document.getElementById('guess-display').innerHTML  = '&nbsp;';
  document.getElementById('guess-display').className  = 'guess-display';
  document.getElementById('result-banner').classList.remove('show');
  document.getElementById('pause-indicator').classList.remove('show');
  document.getElementById('config-panel').classList.remove('running','paused-panel');
  document.getElementById('checkpoint-txt').textContent = '';

  showButtons('idle');
  setStatus('Idle', null, null);
  rebuildWorkerPills();
}

/* ──────────────────────────────────────────
   OUTCOMES
   ────────────────────────────────────────── */
function showCracked(password, workerIdx) {
  var elapsed = accTime.toFixed(2);
  var spd     = accTime > 0 ? Math.round(totalAtt / accTime).toLocaleString() : 'N/A';

  log('='.repeat(52), 't-sep');
  log('[ SUCCESS ]  HASH MATCHED!', 't-success');
  if (workerIdx !== undefined) log('[ WORKER  ]  cracked by W'+(workerIdx+1), 't-success');
  log('[ RESULT  ]  password = "'+password+'"', 't-success');
  log('[ STATS   ]  '+totalAtt.toLocaleString()+' attempts in '+elapsed+'s', 't-success');
  log('[ SPEED   ]  ~'+spd+' hashes/sec', 't-success');

  setProgress(100, password);
  setStatus('Cracked!', 'var(--accent2)', null);
  document.getElementById('result-pwd').textContent = '"'+password+'"';
  document.getElementById('result-banner').classList.add('show');

  for (var i = 0; i < numWorkers; i++) {
    setPill(i, i===workerIdx ? 'winner' : 'done', i===workerIdx ? 'found it!' : 'done');
  }
  finishUp();
}

function showNotFound() {
  log('='.repeat(52), 't-sep');
  log('[ FAILED ]  password not found — try a wider charset.', 't-fail');
  setStatus('Not Found', 'var(--accent3)', null);
  for (var i = 0; i < numWorkers; i++) setPill(i, '', 'idle');
  finishUp();
}
</script>
</body>
</html>
