<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Virtuoso: Hardware Trainer</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Barlow+Condensed:wght@400;600;700&family=JetBrains+Mono:wght@400;700&display=swap" rel="stylesheet">
    <style>
        *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
        :root { --gold: #fbbf24; --amber: #f59e0b; --bg: #0c0c0e; --neck: #6b4a34; }
        body {
            font-family: 'Barlow Condensed', sans-serif;
            background: var(--bg);
            color: #fff;
            overflow: hidden;
            user-select: none;
            -webkit-user-select: none;
            height: 100vh;
            width: 100vw;
        }
        canvas { position: fixed; inset: 0; display: block; z-index: 5; }
       
        .screen {
            position: fixed; inset: 0; z-index: 100;
            display: flex; flex-direction: column; align-items: center; justify-content: center;
            transition: opacity .5s ease, visibility .5s;
        }
        .screen.hidden { opacity: 0; visibility: hidden; pointer-events: none; }
        #splash { background: radial-gradient(circle at center, #2a1f18 0%, #000 100%); }
        #result { background: rgba(0, 0, 0, .98); backdrop-filter: blur(30px); overflow-y: auto; padding: 2rem 0; }
       
        .glass {
            background: rgba(255, 255, 255, .02);
            border: 1px solid rgba(255, 255, 255, .08);
            border-radius: 2rem;
            padding: 3rem;
            text-align: center;
            max-width: 700px;
            width: 95%;
            margin: auto;
        }
       
        .input-box {
            background: rgba(255,255,255,0.05);
            border: 1px solid rgba(255,255,255,0.1);
            border-radius: 12px;
            padding: 1rem;
            color: #fff;
            font-family: 'Barlow Condensed', sans-serif;
            font-size: 1.2rem;
            text-align: center;
            margin-bottom: 1.5rem;
            width: 100%;
            max-width: 300px;
            outline: none;
        }
        .input-box:focus { border-color: var(--gold); background: rgba(255,255,255,0.08); }


        .btn {
            font-family: 'Barlow Condensed', sans-serif;
            font-weight: 700; font-size: 1rem; letter-spacing: .2em; text-transform: uppercase;
            color: #000; background: linear-gradient(135deg, #fcd34d, #d97706);
            border: none; border-radius: 999px; padding: 1.1rem 3.5rem; cursor: pointer;
            box-shadow: 0 8px 32px rgba(245, 158, 11, .3);
            transition: all .2s;
        }
        .btn:hover { transform: translateY(-3px); box-shadow: 0 12px 48px rgba(245, 158, 11, .5); }
       
        #splash-title {
            font-family: 'Bebas Neue', sans-serif;
            font-size: clamp(4rem, 12vw, 8rem); letter-spacing: .05em;
            background: linear-gradient(to bottom, #fff, #b5835a);
            -webkit-background-clip: text; background-clip: text; -webkit-text-fill-color: transparent;
            margin-bottom: 0.5rem;
        }
        #splash-sub { color: #b5835a; letter-spacing: 0.6em; text-transform: uppercase; font-size: 0.8rem; margin-bottom: 2rem; }


        #hud { position: fixed; inset: 0; pointer-events: none; z-index: 20; }
        #top-bar { padding: 2rem; display: flex; justify-content: space-between; }
        #score-num { font-family: 'JetBrains Mono', monospace; font-size: 2.5rem; color: var(--gold); }
        #combo-wrap { position: absolute; left: 50%; top: 20%; transform: translateX(-50%); text-align: center; opacity: 0; transition: opacity 0.3s; }
        #combo-num { font-family: 'Bebas Neue', sans-serif; font-size: 5rem; line-height: 1; }


        #key-guide {
            position: fixed; bottom: 1.5rem; width: 100%;
            display: flex; justify-content: center; gap: 3rem;
            font-size: 0.65rem; color: rgba(255,255,255,0.4);
            letter-spacing: 0.2em; text-transform: uppercase;
            font-weight: 600;
        }


        #countdown {
            position: fixed; inset: 0; z-index: 90; display: flex; align-items: center; justify-content: center;
            font-family: 'Bebas Neue', sans-serif; font-size: 15rem; color: var(--gold); pointer-events: none; opacity: 0;
        }


        .result-header { margin-bottom: 2rem; }
        #result-name { color: var(--gold); font-family: 'Bebas Neue'; font-size: 1.5rem; letter-spacing: 0.1em; display: block; }
        #result-rank { font-size: 8rem; color: #fff; font-family: 'Bebas Neue'; line-height: 0.9; margin: 0.5rem 0; text-shadow: 0 0 30px rgba(251, 191, 36, 0.3); }
        #coach-comment { font-size: 1.2rem; line-height: 1.5; color: #e5e7eb; max-width: 550px; margin: 0 auto 2.5rem; font-style: italic; }


        .dashboard { display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; text-align: left; }
        .panel { background: rgba(255,255,255,0.03); border-radius: 1.25rem; padding: 1.5rem; border: 1px solid rgba(255,255,255,0.05); }
        .panel-h { font-family: 'Bebas Neue'; font-size: 1.2rem; color: var(--gold); letter-spacing: 0.1em; margin-bottom: 1rem; text-transform: uppercase; border-bottom: 1px solid rgba(255,255,255,0.1); padding-bottom: 0.5rem; }


        .metric-row { display: flex; justify-content: space-between; align-items: baseline; margin-bottom: 0.8rem; }
        .metric-lbl { font-size: 0.75rem; color: rgba(255,255,255,0.5); text-transform: uppercase; letter-spacing: 0.1em; }
        .metric-val { font-family: 'JetBrains Mono'; font-size: 1.1rem; color: #fff; }


        .insight-item { display: flex; align-items: flex-start; gap: 0.75rem; margin-bottom: 0.8rem; font-size: 0.9rem; }
        .insight-icon { width: 6px; height: 6px; border-radius: 50%; margin-top: 6px; flex-shrink: 0; }
        .icon-pos { background: #10b981; box-shadow: 0 0 8px #10b981; }
        .icon-neg { background: #f43f5e; box-shadow: 0 0 8px #f43f5e; }


        .lb-minimal { margin-top: 2rem; border-top: 1px solid rgba(255,255,255,0.1); padding-top: 1.5rem; }
        .lb-row { display: flex; justify-content: space-between; font-size: 0.85rem; padding: 0.4rem 0.5rem; border-radius: 4px; }
        .lb-row:nth-child(even) { background: rgba(255,255,255,0.02); }
        .lb-row.active { background: rgba(251, 191, 36, 0.1); color: var(--gold); font-weight: 700; }


        @media (max-width: 600px) {
            .dashboard { grid-template-columns: 1fr; }
        }
    </style>
</head>
<body>
    <div id="splash" class="screen">
        <h1 id="splash-title">VIRTUOSO</h1>
        <p id="splash-sub">Hardware Placement Trainer</p>
        <input type="text" id="player-name" class="input-box" placeholder="ENTER YOUR NAME" maxlength="12">
        <button class="btn" id="start-btn">Begin Session</button>
    </div>


    <div id="result" class="screen hidden">
        <div class="glass">
            <div class="result-header">
                <span id="result-name">MASTER PERFORMANCE</span>
                <div id="result-rank">A</div>
                <p id="coach-comment">"..."</p>
            </div>
           
            <div class="dashboard">
                <div class="panel">
                    <h3 class="panel-h">Performance Summary</h3>
                    <div class="metric-row">
                        <span class="metric-lbl">Notes Hit</span>
                        <span class="metric-val" id="m-note-acc">0%</span>
                    </div>
                    <div class="metric-row" title="Input cleanliness: Correct hits vs total physical inputs.">
                        <span class="metric-lbl">Cleanliness</span>
                        <span class="metric-val" id="m-input-acc">0%</span>
                    </div>
                    <div class="metric-row">
                        <span class="metric-lbl">Max Streak</span>
                        <span class="metric-val" id="m-streak">0</span>
                    </div>
                    <div class="metric-row">
                        <span class="metric-lbl">Perfect Timing</span>
                        <span class="metric-val" id="m-perfect">0</span>
                    </div>
                </div>


                <div class="panel">
                    <h3 class="panel-h">Coach's Focus Areas</h3>
                    <div id="insight-list"></div>
                </div>
            </div>


            <div class="lb-minimal">
                <h3 class="panel-h" style="border: none; text-align: center;">Leaderboard</h3>
                <div id="leaderboard-list"></div>
            </div>
           
            <button class="btn" id="retry-btn" style="width: 100%; margin-top: 2rem;">New Practice Session</button>
        </div>
    </div>


    <div id="countdown"></div>


    <div id="hud">
        <div id="top-bar">
            <div>
                <h2 style="font-family: 'Bebas Neue'; font-size: 1.8rem;">Ode to Joy</h2>
                <p style="font-size: 0.7rem; letter-spacing: 0.2em; opacity: 0.5;">PLACEMENT TRAINING</p>
            </div>
            <div id="score-num">000000</div>
        </div>
        <div id="combo-wrap">
            <div style="font-size: 0.8rem; letter-spacing: 0.4em; opacity: 0.5;">STREAK</div>
            <div id="combo-num">×0</div>
        </div>
    </div>


    <div id="key-guide">
        <span>S4 (A): 6 | 1-5</span>
        <span>S3 (E): Y | Q-T</span>
        <span>S2 (C): H | A-G</span>
        <span>S1 (G): N | Z-B</span>
    </div>


    <canvas id="c"></canvas>


    <script type="module">
        import { initializeApp } from 'https://www.gstatic.com/firebasejs/11.6.1/firebase-app.js';
        import { getAuth, signInAnonymously, signInWithCustomToken, onAuthStateChanged } from 'https://www.gstatic.com/firebasejs/11.6.1/firebase-auth.js';
        import { getFirestore, collection, addDoc, getDocs, doc, setDoc } from 'https://www.gstatic.com/firebasejs/11.6.1/firebase-firestore.js';


        'use strict';
        const canvas = document.getElementById('c');
        const ctx = canvas.getContext('2d');
        const splashEl = document.getElementById('splash');
        const resultEl = document.getElementById('result');
        const cdEl = document.getElementById('countdown');
        const scoreEl = document.getElementById('score-num');
        const comboEl = document.getElementById('combo-num');
        const comboWrap = document.getElementById('combo-wrap');
        const nameInput = document.getElementById('player-name');


        // FIX 3: Fully safe Firebase initialization guard
        let firebaseConfig = null;
        try { firebaseConfig = (typeof __firebase_config !== 'undefined' && __firebase_config) ? JSON.parse(__firebase_config) : null; } catch(e) {}
        const app = firebaseConfig ? initializeApp(firebaseConfig) : null;
        const auth = app ? getAuth(app) : null;
        const db = app ? getFirestore(app) : null;
        const appId = typeof __app_id !== 'undefined' ? __app_id : 'virtuoso-arduino';


        // FIX 1: Timing constants (units: beats)
        const EARLY_WINDOW = 0.3;
        const LATE_WINDOW = 0.45;
        const PERFECT_WINDOW = 0.12;
        const INPUT_DEBOUNCE = 50;


        let user = null;
        if (auth) {
            onAuthStateChanged(auth, (u) => { user = u; });
        }


        const initAuth = async () => {
          if (!auth) return;
          if (typeof __initial_auth_token !== 'undefined' && __initial_auth_token) {
            await signInWithCustomToken(auth, __initial_auth_token);
          } else {
            await signInAnonymously(auth);
          }
        };
        initAuth();


        const STRS = [
            { id: 3, label: 'A', freq: 440.00, col: '#c4b5fd', rgb: '196,181,253', keys: ['6','1','2','3','4','5'] },
            { id: 2, label: 'E', freq: 329.63, col: '#6ee7b7', rgb: '110,231,183', keys: ['y','q','w','e','r','t'] },
            { id: 1, label: 'C', freq: 261.63, col: '#fcd34d', rgb: '252,211,77',  keys: ['h','a','s','d','f','g'] },
            { id: 0, label: 'G', freq: 392.00, col: '#fca5a5', rgb: '252,165,165', keys: ['n','z','x','c','v','b'] }
        ];


        const KEYMAP = {};
        STRS.forEach(s => s.keys.forEach((k, i) => KEYMAP[k] = { sid: s.id, fret: i }));


        const BEAT_OFFSET = 1.0;
        const RAW_SONG = [
            {s:2,f:0,b:0}, {s:2,f:0,b:1}, {s:2,f:1,b:2}, {s:2,f:3,b:3},
            {s:2,f:3,b:4}, {s:2,f:1,b:5}, {s:2,f:0,b:6}, {s:1,f:2,b:7},
            {s:1,f:0,b:8}, {s:1,f:0,b:9}, {s:1,f:2,b:10}, {s:2,f:0,b:11},
            {s:2,f:0,b:12.5}, {s:1,f:2,b:13}, {s:1,f:2,b:14},
            {s:2,f:0,b:16}, {s:2,f:0,b:17}, {s:2,f:1,b:18}, {s:2,f:3,b:19},
            {s:2,f:3,b:20}, {s:2,f:1,b:21}, {s:2,f:0,b:22}, {s:1,f:2,b:23},
            {s:1,f:0,b:24}, {s:1,f:0,b:25}, {s:1,f:2,b:26}, {s:2,f:0,b:27},
            {s:1,f:2,b:28.5}, {s:1,f:0,b:29}, {s:1,f:0,b:30},
            {s:1,f:2,b:32}, {s:1,f:2,b:33}, {s:2,f:0,b:34}, {s:1,f:0,b:35},
            {s:1,f:2,b:36}, {s:2,f:0,b:37}, {s:2,f:1,b:37.5}, {s:2,f:0,b:38}, {s:1,f:0,b:39},
            {s:1,f:2,b:40}, {s:2,f:0,b:41}, {s:2,f:1,b:41.5}, {s:2,f:0,b:42}, {s:1,f:2,b:43}, {s:1,f:0,b:44}, {s:1,f:2,b:45}, {s:0,f:0,b:46},
            {s:2,f:0,b:48}, {s:2,f:0,b:49}, {s:2,f:1,b:50}, {s:2,f:3,b:51},
            {s:2,f:3,b:52}, {s:2,f:1,b:53}, {s:2,f:0,b:54}, {s:1,f:2,b:55}, // FIX 2: Corrected beat 53: F natural (fret 1) instead of F#
            {s:1,f:0,b:56}, {s:1,f:0,b:57}, {s:1,f:2,b:58}, {s:2,f:0,b:59},
            {s:1,f:2,b:60.5}, {s:1,f:0,b:61}, {s:1,f:0,b:62}
        ];


        const SONG = RAW_SONG.map(n => ({ ...n, b: n.b + BEAT_OFFSET }));


        let phase = 'splash', beat = 0, lastMs = performance.now();
        let score = 0, combo = 0, maxCombo = 0, hits = 0, totalPerfects = 0, totalMisses = 0, wrongInputs = 0;
        let noteStates = SONG.map(() => 'pending'), performanceLog = [], particles = [], vibs = [0,0,0,0];
        let lastKeyTime = {};
        let W, H, neckX, neckY, neckW, neckH, fretW, stringY;


        function layout() {
            W = canvas.width = window.innerWidth;
            H = canvas.height = window.innerHeight;
            neckW = Math.min(W * 0.9, 1300);
            neckH = neckW * 0.22;
            neckX = (W - neckW) / 2;
            neckY = (H - neckH) / 2;
            fretW = neckW / 6;
            stringY = STRS.map((_, i) => neckY + (neckH / 5) * (i + 1));
        }


        const getNotePos = (sid, fret) => ({
            x: neckX + (fret * fretW) + (fretW / 2),
            y: stringY[3 - sid]
        });


        let aCtx, masterGain;
        async function initAudio() {
            if (aCtx) return;
            aCtx = new (window.AudioContext || window.webkitAudioContext)();
            masterGain = aCtx.createGain();
            masterGain.gain.value = 0.4;
            masterGain.connect(aCtx.destination);
        }


        function playNote(sid, fret) {
            if (!aCtx) return;
            const s = STRS.find(x => x.id === sid);
            const freq = s.freq * Math.pow(2, fret / 12);
            const duration = 1.0;
            const sampleRate = aCtx.sampleRate;
            const length = Math.floor(duration * sampleRate);
            const buffer = aCtx.createBuffer(1, length, sampleRate);
            const data = buffer.getChannelData(0);
            const period = Math.floor(sampleRate / freq);
            const delayLine = new Float32Array(period);
            for (let i = 0; i < period; i++) delayLine[i] = Math.random() * 2 - 1;
            let p = 0;
            for (let i = 0; i < length; i++) {
                const x0 = delayLine[p], x1 = delayLine[(p + 1) % period];
                const val = 0.5 * (x0 + x1) * 0.99;
                data[i] = x0; delayLine[p] = val; p = (p + 1) % period;
            }
            const source = aCtx.createBufferSource();
            source.buffer = buffer;
            const g = aCtx.createGain();
            g.gain.setValueAtTime(0.6, aCtx.currentTime);
            g.gain.exponentialRampToValueAtTime(0.01, aCtx.currentTime + duration);
            source.connect(g); g.connect(masterGain); source.start();
            vibs[3 - sid] = 8;
        }


        function drawNeck() {
            // FIX: Lighter guitar neck
            ctx.fillStyle = '#6b4a34';
            ctx.fillRect(neckX, neckY, neckW, neckH);
            ctx.fillStyle = 'rgba(0,0,0,0.25)';
            ctx.fillRect(neckX, neckY, fretW, neckH);
            for(let i=0; i<=6; i++) {
                const x = neckX + i * fretW;
                const isNut = i === 1;
                ctx.lineWidth = isNut ? 14 : 6;
                ctx.strokeStyle = isNut ? '#eee' : '#999';
                if (i === 0) { ctx.strokeStyle = 'rgba(255,255,255,0.1)'; ctx.lineWidth = 2; }
                ctx.beginPath(); ctx.moveTo(x, neckY); ctx.lineTo(x, neckY + neckH); ctx.stroke();
                if (i === 0) {
                    ctx.fillStyle = 'rgba(255,255,255,0.3)';
                    ctx.font = '700 13px Barlow Condensed'; ctx.textAlign = 'center';
                    ctx.fillText('OPEN', neckX + fretW/2, neckY - 12);
                } else if (i < 6) {
                    ctx.fillStyle = 'rgba(255,255,255,0.15)';
                    ctx.font = '700 12px Barlow Condensed'; ctx.textAlign = 'center';
                    ctx.fillText('FRET ' + i, neckX + i*fretW + fretW/2, neckY - 12);
                }
            }
            STRS.forEach((s, i) => {
                const y = stringY[i], v = vibs[i];
                ctx.strokeStyle = 'rgba(0,0,0,0.3)'; ctx.lineWidth = 2 + i*0.5;
                ctx.beginPath(); ctx.moveTo(neckX, y + 2); ctx.lineTo(neckX + neckW, y + 2); ctx.stroke();
                // FIX: Darker gray strings
                ctx.strokeStyle = 'rgba(120,120,120,0.9)';
                ctx.lineWidth = 1.5 + i*0.2;
                ctx.beginPath(); ctx.moveTo(neckX, y);
                if (v > 0.5) for(let x=neckX; x<neckX+neckW; x+=10) ctx.lineTo(x, y + Math.sin(x*0.1) * v);
                else ctx.lineTo(neckX + neckW, y);
                ctx.stroke();
            });
        }


        function drawNotes() {
            let activeIndex = -1, minDiff = Infinity;
            SONG.forEach((n, i) => {
                const d = n.b - beat;
                // FIX 4: Unit wording fix - timing in beats
                if (noteStates[i] === 'pending' && d > -LATE_WINDOW && d < minDiff) { minDiff = d; activeIndex = i; }
            });
            SONG.forEach((n, i) => {
                const diff = n.b - beat;
                if (diff < -LATE_WINDOW || diff > 2.5 || noteStates[i] !== 'pending') return;
                const pos = getNotePos(n.s, n.f), s = STRS.find(st => st.id === n.s), isActive = (i === activeIndex);
                const alpha = isActive ? 1.0 : Math.max(0.2, 0.5 - diff * 0.2), radius = isActive ? 28 + Math.sin(Date.now() * 0.01) * 3 : 22;
                const clusterCount = SONG.filter((other, idx) => noteStates[idx] === 'pending' && Math.abs(other.b - n.b) < 0.2).length;
                if (diff > 0) {
                    ctx.strokeStyle = `rgba(${isActive ? s.rgb : '120,120,120'}, ${isActive ? 0.8 : 0.2})`;
                    ctx.lineWidth = isActive ? 5 : 2;
                    ctx.beginPath(); ctx.arc(pos.x, pos.y, radius + diff * 50, 0, Math.PI * 2); ctx.stroke();
                }
                ctx.fillStyle = isActive ? s.col : `rgba(80, 80, 80, ${alpha})`;
                ctx.beginPath(); ctx.arc(pos.x, pos.y, radius, 0, Math.PI * 2); ctx.fill();
                if (isActive) {
                    ctx.strokeStyle = 'white'; ctx.lineWidth = 3;
                    ctx.beginPath(); ctx.arc(pos.x, pos.y, radius - 5, 0, Math.PI * 2); ctx.stroke();
                }
                ctx.fillStyle = isActive ? '#000' : `rgba(0, 0, 0, ${alpha})`;
                ctx.font = `bold ${isActive ? 15 : 13}px monospace`; ctx.textAlign = 'center'; ctx.textBaseline = 'middle';
                ctx.fillText(s.keys[n.f].toUpperCase(), pos.x, pos.y);
                if (clusterCount > 1) {
                    const bx = pos.x + radius + 10, by = pos.y - radius - 2;
                    ctx.fillStyle = 'rgba(251, 191, 36, 0.9)'; ctx.beginPath(); ctx.roundRect(bx - 12, by - 8, 24, 16, 4); ctx.fill();
                    ctx.fillStyle = '#000'; ctx.font = 'bold 10px JetBrains Mono'; ctx.fillText(clusterCount + 'x', bx, by);
                }
            });
        }


        class Particle {
            constructor(x, y, col) {
                this.x = x; this.y = y;
                this.vx = (Math.random() - 0.5) * 12; this.vy = (Math.random() - 0.5) * 12;
                this.life = 1.0; this.col = col;
            }
            update() { this.x += this.vx; this.y += this.vy; this.life -= 0.025; }
            draw() { ctx.fillStyle = `rgba(${this.col}, ${this.life})`; ctx.beginPath(); ctx.arc(this.x, this.y, 4, 0, Math.PI*2); ctx.fill(); }
        }


        function handleInput(sid, fret) {
            if (phase !== 'playing') return;
           
            const now = Date.now();
            const keyId = `${sid}-${fret}`;
            if (lastKeyTime[keyId] && now - lastKeyTime[keyId] < INPUT_DEBOUNCE) return;
            lastKeyTime[keyId] = now;


            playNote(sid, fret);
           
            // FIX 1: Robust repeated-note logic (signed offset in beats: (+) late, (-) early)
            let best = -1;
            for (let i = 0; i < SONG.length; i++) {
                const n = SONG[i];
                if (noteStates[i] !== 'pending' || n.s !== sid || n.f !== fret) continue;
                const offset = beat - n.b;
                if (offset >= -EARLY_WINDOW && offset <= LATE_WINDOW) {
                    best = i; break; // Earliest eligible note found
                }
            }


            if (best >= 0) {
                const diff = Math.abs(SONG[best].b - beat);
                const isP = diff < PERFECT_WINDOW;
                noteStates[best] = 'hit';
                performanceLog[best] = { type: isP ? 'perfect' : 'good', string: sid, fret: fret, timing: diff };
                hits++; combo++; if (combo > maxCombo) maxCombo = combo;
                if (isP) totalPerfects++;
                score += Math.round(150 * (1 - diff));
                const pos = getNotePos(sid, fret);
                const s = STRS.find(st => st.id === sid);
                for(let i=0; i<12; i++) particles.push(new Particle(pos.x, pos.y, s.rgb));
                updateHUD();
            } else {
                wrongInputs++;
                score = Math.max(0, score - 25);
                combo = 0;
                updateHUD();
            }
        }


        function updateHUD() {
            scoreEl.textContent = score.toString().padStart(6, '0');
            comboEl.textContent = '×' + combo;
            comboWrap.style.opacity = combo > 0 ? 1 : 0;
        }


        function checkMisses() {
            SONG.forEach((n, i) => {
                // FIX 4: Unit wording fix - timing in beats
                if (noteStates[i] === 'pending' && beat > n.b + LATE_WINDOW) {
                    noteStates[i] = 'missed';
                    performanceLog[i] = { type: 'miss', string: n.s, fret: n.f, timing: 1.0 };
                    totalMisses++;
                    combo = 0;
                    score = Math.max(0, score - 50);
                    updateHUD();
                }
            });
        }


        async function saveScore(name) {
            // FIX 3: Robust guard for Firebase service availability
            if (!user || !db || !auth) return;
            try {
                await addDoc(collection(db, 'artifacts', appId, 'public', 'data', 'leaderboard'), {
                    name, score, accuracy: Math.round((hits / SONG.length) * 100), timestamp: Date.now()
                });
                await loadLeaderboard();
            } catch (e) {}
        }


        async function loadLeaderboard() {
            if (!db) {
                document.getElementById('leaderboard-list').innerHTML = '<p style="opacity:0.5;font-size:0.7rem;">OFFLINE MODE</p>';
                return;
            }
            const listEl = document.getElementById('leaderboard-list');
            try {
                const q = collection(db, 'artifacts', appId, 'public', 'data', 'leaderboard');
                const snap = await getDocs(q);
                let data = [];
                snap.forEach(doc => data.push(doc.data()));
                data.sort((a, b) => b.score - a.score);
                data = data.slice(0, 5);
                const pName = nameInput.value.trim();
                listEl.innerHTML = data.map((d, i) => `
                    <div class="lb-row ${d.name === pName ? 'active' : ''}">
                        <span>#${i+1} ${d.name}</span>
                        <span style="font-family:JetBrains Mono">${d.score.toLocaleString()}</span>
                    </div>
                `).join('');
            } catch (e) { listEl.innerHTML = '<p>Error loading rankings.</p>'; }
        }


        function analyzeSession(name, noteAcc, inputAcc) {
            const insightList = document.getElementById('insight-list');
            const commentBox = document.getElementById('coach-comment');
            insightList.innerHTML = '';
           
            const mid = Math.floor(performanceLog.length / 2);
            const firstHalfMisses = performanceLog.slice(0, mid).filter(p => p.type === 'miss').length;
            const secondHalfMisses = performanceLog.slice(mid).filter(p => p.type === 'miss').length;
           
            const stringStats = [0, 1, 2, 3].map(id => {
                const notes = performanceLog.filter(p => p.string === id);
                const hits = notes.filter(p => p.type !== 'miss').length;
                return { id, acc: notes.length ? hits / notes.length : 1 };
            });
            const worstString = stringStats.sort((a, b) => a.acc - b.acc)[0];
            const bestString = stringStats.sort((a, b) => b.acc - a.acc)[0];


            let rank = 'C', coachMsg = "";
           
            if (noteAcc >= 98 && inputAcc >= 95) rank = 'S';
            else if (noteAcc >= 85 && inputAcc >= 80) rank = 'A';
            else if (noteAcc >= 70 || inputAcc >= 60) rank = 'B';
            else rank = 'C';


            if (rank === 'S') coachMsg = `"${name}, that was absolutely flawless. Your hands are moving with surgical precision."`;
            else if (noteAcc > 90 && inputAcc < 70) coachMsg = `"${name}, you hit almost everything, but your fingerwork is a bit noisy. Focus on 'one press, one note' precision."`;
            else if (noteAcc < 75 && inputAcc > 90) coachMsg = `"${name}, you are very precise when you play, but you're missing opportunities. Trust your speed more!"`;
            else if (rank === 'A') coachMsg = `"${name}, excellent precision! You really captured the soul of this piece today."`;
            else if (rank === 'B') coachMsg = `"${name}, you're making great progress. Your placement is steady, just work on those quicker transitions."`;
            else coachMsg = `"${name}, every master starts somewhere. Let's focus on hitting the big notes first and cleaning up the technique later."`;


            if (secondHalfMisses < firstHalfMisses && noteAcc < 90) coachMsg += " I noticed you settled into a much better groove in the second half.";
           
            commentBox.textContent = coachMsg;
            document.getElementById('result-rank').textContent = rank;


            document.getElementById('m-note-acc').textContent = noteAcc + '%';
            document.getElementById('m-input-acc').textContent = inputAcc + '%';
            document.getElementById('m-streak').textContent = maxCombo;
            document.getElementById('m-perfect').textContent = totalPerfects;
           
            const validHits = performanceLog.filter(p => p.type !== 'miss');
            const avgTiming = validHits.length ? validHits.reduce((a, b) => a + b.timing, 0) / validHits.length : 1.0;
           
            const addInsight = (text, isPos) => {
                const div = document.createElement('div');
                div.className = 'insight-item';
                div.innerHTML = `<div class="insight-icon ${isPos ? 'icon-pos' : 'icon-neg'}"></div><span>${text}</span>`;
                insightList.appendChild(div);
            };


            if (inputAcc > 90) addInsight("Surgical finger placement.", true);
            if (avgTiming < 0.08) addInsight("Pro-level rhythmic timing.", true);
            if (firstHalfMisses === 0) addInsight("Perfect confidence in the intro.", true);
            if (bestString.acc > 0.95 && hits > 10) addInsight(`Dominating the ${STRS.find(s=>s.id===bestString.id).label} string.`, true);


            if (wrongInputs > hits * 0.3) addInsight("Try to minimize stray inputs.", false);
            if (secondHalfMisses > firstHalfMisses + 4) addInsight("Stay focused until the final bar.", false);
            if (worstString.acc < 0.6) addInsight(`Tough string today: ${STRS.find(s=>s.id===worstString.id).label}.`, false);
            if (totalMisses > 12) addInsight("Practice the bridge section slow.", false);
        }


        function startCountdown() {
            phase = 'countdown';
            beat = -1.5; score = 0; combo = 0; maxCombo = 0; hits = 0; totalPerfects = 0; totalMisses = 0; wrongInputs = 0;
            noteStates = SONG.map(() => 'pending'); performanceLog = []; lastKeyTime = {};
            updateHUD();
            let n = 3; cdEl.style.opacity = '1';
            const tick = () => {
                if (n > 0) { cdEl.textContent = n--; setTimeout(tick, 900); }
                else {
                    cdEl.textContent = 'GO!';
                    setTimeout(() => {
                        cdEl.style.opacity = '0'; phase = 'playing'; lastMs = performance.now(); beat = 0;
                    }, 500);
                }
            };
            tick();
        }


        function endGame() {
            phase = 'results';
            const name = nameInput.value.trim() || 'Player';
           
            const noteAcc = Math.round((hits / SONG.length) * 100);
            const totalPresses = hits + wrongInputs;
            const inputAcc = Math.round((hits / (totalPresses || 1)) * 100);


            document.getElementById('result-name').textContent = `${name.toUpperCase()}'S PERFORMANCE`;
            analyzeSession(name, noteAcc, inputAcc);
            saveScore(name);
            if (!db) loadLeaderboard();
            resultEl.classList.remove('hidden');
        }


        function loop(ms) {
            const dt = (ms - lastMs) / 1000;
            lastMs = ms;
            if (phase === 'playing') {
                beat += dt * (72/60);
                checkMisses();
                if (beat > SONG[SONG.length-1].b + 2.5) endGame();
            }
            ctx.clearRect(0,0,W,H);
            drawNeck(); drawNotes();
            particles.forEach((p, i) => { p.update(); p.draw(); if (p.life <= 0) particles.splice(i, 1); });
            vibs = vibs.map(v => v * 0.85);
            requestAnimationFrame(loop);
        }


        window.addEventListener('keydown', e => {
            const k = e.key.toLowerCase();
            if (!e.repeat && KEYMAP[k]) handleInput(KEYMAP[k].sid, KEYMAP[k].fret);
        });
       
        document.getElementById('start-btn').onclick = async () => {
            if (!nameInput.value.trim()) { nameInput.style.borderColor = '#ef4444'; return; }
            await initAudio(); splashEl.classList.add('hidden'); startCountdown();
        };


        document.getElementById('retry-btn').onclick = () => {
            resultEl.classList.add('hidden');
            splashEl.classList.remove('hidden');
            nameInput.value = '';
            nameInput.style.borderColor = 'rgba(255,255,255,0.1)';
        };


        window.addEventListener('resize', layout);
        layout(); requestAnimationFrame(loop);
    </script>
</body>
</html>
