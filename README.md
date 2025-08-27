<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>Shalimar Lotto - Results</title>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
<style>
  :root{
    --bg1:#0b0710;
    --bg2:#2a0b1a;
    --accent:#ffdd00;
    --accent-dark:#ff7300;
    --neon:#6cf;
    --card: rgba(255,255,255,0.05);
    --glass: rgba(255,255,255,0.04);
    --muted: rgba(255,255,255,0.65);
    --danger: #ff6b6b;
  }

  *{box-sizing:border-box;margin:0;padding:0;font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif}
  html,body{height:100%}
  body{
    background: radial-gradient(1200px 600px at 10% 10%, rgba(255,45,85,0.06), transparent 10%),
                radial-gradient(1000px 400px at 90% 90%, rgba(50,50,255,0.04), transparent 10%),
                linear-gradient(135deg,var(--bg1), #19101a 40%, #200f12 100%);
    color:#fff;
    -webkit-font-smoothing:antialiased;
    -moz-osx-font-smoothing:grayscale;
    padding-bottom:60px;
  }

  .container{max-width:1120px;margin:0 auto;padding:18px}

  header{
    position:sticky;top:0;z-index:40;margin-bottom:10px;
    background: linear-gradient(180deg, rgba(0,0,0,0.45), rgba(0,0,0,0.12));
    border-radius:12px;padding:18px;backdrop-filter: blur(8px);
    box-shadow: 0 8px 30px rgba(0,0,0,0.6);
  }

  .logo{ text-align:center;margin-bottom:6px }
  .logo h1{ font-size:34px; color:var(--accent); text-shadow:0 6px 22px rgba(255,221,0,0.08); letter-spacing:1px }
  .logo p{ color:var(--muted); margin-top:6px; font-size:14px }

  /* Centered session buttons (tabs) */
  .tabs{ display:flex; justify-content:center; gap:18px; margin-top:12px }
  .tab-btn{
    padding:12px 34px; border-radius:999px; font-weight:700; font-size:15px;
    border:none; cursor:pointer; background: linear-gradient(180deg, rgba(255,255,255,0.04), rgba(255,255,255,0.02));
    color:rgba(255,255,255,0.9); box-shadow: 0 6px 18px rgba(0,0,0,0.5); transition: all .28s ease;
  }
  .tab-btn:hover{ transform: translateY(-4px); box-shadow: 0 12px 30px rgba(0,0,0,0.6) }
  .tab-btn.active{
    background: linear-gradient(90deg,var(--accent),var(--accent-dark));
    color: #111827; box-shadow: 0 10px 30px rgba(255,140,0,0.12);
  }

  .current-time{
    margin:20px auto; max-width:880px; text-align:center;
    background: linear-gradient(90deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
    padding:12px 18px; border-radius:10px; font-size:16px;
    display:flex; justify-content:center; align-items:center; gap:10px;
    box-shadow: 0 8px 30px rgba(0,0,0,0.5);
  }
  .current-time i{ color:var(--accent) }

  /* Sections */
  .result-section{
    margin-top:26px; background: linear-gradient(180deg, rgba(255,255,255,0.02), transparent);
    border-radius:14px; padding:22px; display:none; animation: fadeIn .5s ease both;
    box-shadow: 0 14px 40px rgba(6,6,12,0.6);
  }
  .result-section.active{ display:block }

  @keyframes fadeIn{ from{opacity:0;transform:translateY(18px)} to{opacity:1;transform:none} }

  .section-title{ text-align:center; color:var(--accent); font-size:28px; margin-bottom:6px; text-shadow:0 6px 30px rgba(255,221,0,0.06) }

  .next-result{ text-align:center;color:var(--muted); margin-bottom:18px; font-weight:600 }

  /* Satta */
  .satta-result-container{ display:flex; flex-direction:column; align-items:center; gap:20px }
  .today-satta-result{
    width:100%; max-width:540px; padding:22px;border-radius:14px;
    background: linear-gradient(180deg, rgba(255,221,0,0.14), rgba(255,115,0,0.06));
    color:#091026; text-align:center; box-shadow: 0 12px 30px rgba(255,140,0,0.06);
  }
  .today-satta-result h3{ font-size:20px; margin-bottom:8px }
  .satta-number{ font-size:64px; font-weight:900; letter-spacing:4px; margin:6px 0;
    display:inline-block; padding:10px 22px; border-radius:10px; background:linear-gradient(90deg,#fff8d2,#ffe2a8); color:#1a2a6c; box-shadow: 0 10px 30px rgba(0,0,0,0.15);
    transform-origin: center;
    animation: pop 900ms cubic-bezier(.2,.9,.2,1);
  }
  @keyframes pop{ 0%{transform:scale(.92)} 60%{transform:scale(1.02)} 100%{transform:scale(1)} }

  .satta-date{ color: rgba(0,0,0,0.6); font-weight:600; margin-top:6px }

  /* history table */
  .history{ margin-top:26px }
  .history h3{ text-align:center; color:var(--accent); margin-bottom:12px }
  .history-table{ width:100%; border-collapse:collapse; font-size:14px; overflow:hidden; border-radius:10px; background:var(--glass) }
  .history-table th, .history-table td{ padding:10px 12px; text-align:center; border-bottom:1px solid rgba(255,255,255,0.03) }
  .history-table th{ color:var(--accent); font-weight:700; background: linear-gradient(180deg, rgba(0,0,0,0.15), transparent) }
  .empty-result{ color:var(--danger); font-style:italic }

  .history-controls{ display:flex; gap:12px; justify-content:center; margin-bottom:12px; flex-wrap:wrap }
  .history-btn{ padding:8px 16px; border-radius:999px; border:none; cursor:pointer; background: rgba(255,255,255,0.03); color:#fff; font-weight:700 }
  .history-btn.active{ background: linear-gradient(90deg,var(--accent),var(--accent-dark)); color:#111827 }

  /* Lottery Cards */
  .result-cards{ display:grid; grid-template-columns:repeat(3,1fr); gap:16px; align-items:start }
  .result-card{
    background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
    border-radius:12px; padding:18px; text-align:center; box-shadow: 0 10px 28px rgba(3,3,12,0.6);
  }
  .result-card h3{ color:var(--accent); margin-bottom:12px }
  .session-results{ display:flex; justify-content:center; gap:12px; align-items:center; flex-wrap:wrap }

  .session-card{ min-width:86px; border-radius:10px; padding:12px 10px; background:rgba(255,255,255,0.02) }
  .session-card h4{ color:var(--accent); margin-bottom:8px }
  .session-number{
    font-size:36px; font-weight:800; width:56px; height:56px; display:flex; align-items:center; justify-content:center;
    border-radius:10px; background: linear-gradient(180deg, rgba(255,255,255,0.03), rgba(255,255,255,0.01));
    box-shadow: 0 8px 20px rgba(0,0,0,0.4);
    transform-style: preserve-3d;
  }

  /* Flip animation for numbers */
  .flip { perspective:600px; display:inline-block; }
  .flip .face {
    display:block; border-radius:8px; min-width:56px;
    transition: transform .5s cubic-bezier(.2,.9,.2,1);
    transform-origin: center;
  }
  .flip.flip-in .face { transform: rotateX(-90deg); }
  .flip.flip-out .face { transform: rotateX(0deg); }

  .result-number.big { font-size:34px; font-weight:900; color:var(--accent); padding:10px 14px; border-radius:10px; background:linear-gradient(90deg, rgba(255,221,0,0.06), rgba(255,115,0,0.03)); }

  .closed-message{ text-align:center;padding:20px;border-radius:12px;background: linear-gradient(90deg, rgba(255,255,255,0.02), transparent) }

  .date-selector{ display:flex; justify-content:center; gap:8px; align-items:center; margin:12px 0; flex-wrap:wrap }
  select,input[type="date"]{ padding:8px 12px; border-radius:999px; border:none; background:rgba(255,255,255,0.03); color:#fff; font-weight:600 }
  .btn-primary{ padding:8px 14px; border-radius:999px; border:none; cursor:pointer; background: linear-gradient(90deg,var(--accent),var(--accent-dark)); color:#111827; font-weight:800 }

  footer{ margin-top:26px; text-align:center; padding:14px; color:var(--muted); font-size:13px }
  footer .hidden-admin{ color:transparent; text-shadow: 0 0 0 rgba(255,255,255,0.12); cursor:pointer; display:inline-block }

  /* modal */
  .modal-backdrop{ position:fixed; inset:0; display:none; align-items:center; justify-content:center; z-index:80; background: linear-gradient(0deg, rgba(0,0,0,0.6), rgba(0,0,0,0.6)) }
  .modal{ width:90%; max-width:520px; background: linear-gradient(180deg, rgba(8,8,16,0.95), rgba(4,4,10,0.96)); border-radius:12px; padding:18px; box-shadow: 0 18px 60px rgba(0,0,0,0.7) }
  .modal h3{ color:var(--accent); margin-bottom:10px }
  .modal label{ display:block; margin-top:8px; color:var(--muted); font-weight:700 }
  .modal input, .modal select{ width:100%; padding:10px 12px; margin-top:6px; border-radius:8px; border:none; background:rgba(255,255,255,0.03); color:#fff }
  .modal .row{ display:flex; gap:8px }
  .modal .row .col{ flex:1 }
  .modal .actions{ display:flex; gap:8px; justify-content:flex-end; margin-top:12px }

  /* small screens */
  @media (max-width:900px){
    .result-cards{ grid-template-columns:1fr; }
    .tabs{ flex-wrap:wrap; gap:10px }
    .satta-number{ font-size:48px }
    .session-number{ font-size:28px; width:48px; height:48px }
  }
</style>
</head>
<body>
  <header>
    <div class="container">
      <div class="logo">
        <h1>SHALIMAR LOTTO</h1>
        <p class="subtitle"><span style="color:var(--accent)">Instant Results</span> • Trusted Since 2010</p>
      </div>

      <div class="tabs">
        <button class="tab-btn active" data-tab="satta">Satta Result (4:00 PM)</button>
        <button class="tab-btn" data-tab="lottery">Lottery Result (Every 15 min)</button>
      </div>
    </div>
  </header>

  <main class="container">
    <div class="current-time">
      <i class="fas fa-clock"></i>
      <div>Current Time (IST): <strong id="time">Loading...</strong></div>
    </div>

    <!-- Satta Section -->
    <section id="satta" class="result-section active">
      <h2 class="section-title">Satta Results</h2>
      <div class="next-result">Next Result: Today at <strong>4:00 PM IST</strong></div>

      <div class="satta-result-container">
        <div class="today-satta-result" aria-live="polite">
          <h3>Today's Satta Result</h3>
          <div class="satta-number" id="today-satta-number">--</div>
          <div class="satta-date" id="satta-date">Check after 4:00 PM</div>
        </div>

        <div class="history">
          <h3>Previous Results</h3>
          <div class="history-controls">
            <button class="history-btn active" data-days="7">Last 7 Days</button>
            <button class="history-btn" data-days="30">Last 30 Days</button>
            <button class="history-btn" data-days="90">Last 90 Days</button>
            <button class="history-btn" data-days="365">Full History (1 year)</button>
          </div>

          <table class="history-table" aria-live="polite">
            <thead>
              <tr><th>Date</th><th>Result</th><th>Day</th></tr>
            </thead>
            <tbody id="satta-history"></tbody>
          </table>
        </div>
      </div>
    </section>

    <!-- Lottery Section -->
    <section id="lottery" class="result-section">
      <h2 class="section-title">Lottery Results</h2>
      <div class="next-result">Next Result: <strong id="next-lottery-time">Calculating...</strong></div>

      <div id="lottery-closed-message" class="closed-message" style="display:none">
        <h3><i class="fas fa-moon"></i> Lottery Closed</h3>
        <p>Lottery results are available from <strong>9:00 AM</strong> to <strong>9:00 PM IST</strong>.</p>
      </div>

      <div id="lottery-results-container">
        <div class="result-cards">
          <div class="result-card">
            <h3>Current Session</h3>
            <div class="session-results">
              <div class="session-card">
                <h4>A</h4>
                <div class="session-number flip" id="flip-a"><span class="face" id="current-lottery-a">-</span></div>
              </div>
              <div class="session-card">
                <h4>B</h4>
                <div class="session-number flip" id="flip-b"><span class="face" id="current-lottery-b">-</span></div>
              </div>
              <div class="session-card">
                <h4>C</h4>
                <div class="session-number flip" id="flip-c"><span class="face" id="current-lottery-c">-</span></div>
              </div>
            </div>
            <div class="result-time" style="margin-top:12px;color:var(--muted)">Updated: <span id="lottery-update-time">-</span></div>
          </div>

          <div class="result-card">
            <h3>Previous Session</h3>
            <div class="session-results">
              <div class="session-card"><h4>A</h4><div class="session-number" id="previous-lottery-a">-</div></div>
              <div class="session-card"><h4>B</h4><div class="session-number" id="previous-lottery-b">-</div></div>
              <div class="session-card"><h4>C</h4><div class="session-number" id="previous-lottery-c">-</div></div>
            </div>
            <div class="result-time" id="previous-lottery-time" style="margin-top:12px;color:var(--muted)">-</div>
          </div>

          <div class="result-card">
            <h3>Next Draw In</h3>
            <div class="result-number big" id="countdown">--:--</div>
            <div class="result-time" style="margin-top:10px;color:var(--muted)">Minutes : Seconds</div>
          </div>
        </div>

        <div class="history" style="margin-top:18px">
          <h3>Lottery History</h3>

          <div class="history-controls">
            <button class="history-btn active" data-days="1">Today</button>
            <button class="history-btn" data-days="7">Last 7 Days</button>
            <button class="history-btn" data-days="30">Last 30 Days</button>
            <button class="history-btn" data-days="365">Full History (1 year)</button>
          </div>

          <div class="date-selector">
            <span style="color:var(--muted)">Or select specific date:</span>
            <select id="year-select"></select>
            <select id="month-select"></select>
            <select id="day-select"></select>
            <button id="date-search-btn" class="btn-primary">Search</button>
          </div>

          <table class="history-table">
            <thead>
              <tr><th>Date</th><th>Time</th><th>Session A</th><th>Session B</th><th>Session C</th><th>Slot</th></tr>
            </thead>
            <tbody id="lottery-history"></tbody>
          </table>
        </div>
      </div>
    </section>

    <footer>
      <div>© <span id="yearNow"></span> <span class="hidden-admin" id="hidden-admin-trigger" title="Click 3 times quickly">Instant Results</span> Shalimar Lotto. All rights reserved.</div>
      <div class="disclaimer">This website is for entertainment purposes only. Please play responsibly.</div>
    </footer>
  </main>

  <!-- Modals -->
  <div class="modal-backdrop" id="modal-backdrop">
    <div class="modal" role="dialog" aria-modal="true" aria-labelledby="modal-title">
      <div id="modal-content"></div>
    </div>
  </div>

<script>
/* -------------------------
  Utility: IST "now" function
   - returns a Date object representing current IST time
--------------------------*/
function nowIST() {
  // Create a string in IST timezone then convert back to Date to avoid user's local TZ issues
  const istStr = new Date().toLocaleString('en-US', { timeZone: 'Asia/Kolkata' });
  return new Date(istStr);
}

/* -------------------------
  Storage keys & admin key
--------------------------*/
const SATTA_KEY = 'shalimar_satta_history';       // stores daily satta {dateISO:result}
const LOTTERY_KEY = 'shalimar_lottery_history';   // array of {dateISO, A,B,C}
const ADMIN_SECRET = 'shalimar123'; // change as needed

/* -------------------------
  DOM refs
--------------------------*/
const timeEl = document.getElementById('time');
const yearNow = document.getElementById('yearNow'); yearNow.textContent = new Date().getFullYear();

const todaySattaNumEl = document.getElementById('today-satta-number');
const sattaDateEl = document.getElementById('satta-date');
const sattaHistoryTbody = document.getElementById('satta-history');

const nextLotteryTimeEl = document.getElementById('next-lottery-time');
const countdownEl = document.getElementById('countdown');

const currentA = document.getElementById('current-lottery-a');
const currentB = document.getElementById('current-lottery-b');
const currentC = document.getElementById('current-lottery-c');
const prevA = document.getElementById('previous-lottery-a');
const prevB = document.getElementById('previous-lottery-b');
const prevC = document.getElementById('previous-lottery-c');

const lotteryUpdateTime = document.getElementById('lottery-update-time');
const previousLotteryTime = document.getElementById('previous-lottery-time');

const lotteryHistoryTbody = document.getElementById('lottery-history');

const modalBackdrop = document.getElementById('modal-backdrop');
const modalContent = document.getElementById('modal-content');

/* -------------------------
  Tab switching
--------------------------*/
document.querySelectorAll('.tab-btn').forEach(btn=>{
  btn.addEventListener('click',()=>{
    document.querySelectorAll('.tab-btn').forEach(b=>b.classList.remove('active'));
    btn.classList.add('active');
    const tab=btn.getAttribute('data-tab');
    document.querySelectorAll('.result-section').forEach(sec=>sec.classList.remove('active'));
    document.getElementById(tab).classList.add('active');
  });
});

/* -------------------------
  Generate / populate history (1 year)
--------------------------*/
function loadJSON(key, fallback){
  try{ const v = localStorage.getItem(key); return v? JSON.parse(v): fallback; } catch(e){ return fallback; }
}
function saveJSON(key,obj){ localStorage.setItem(key, JSON.stringify(obj)); }

/* Ensure there is initial history (only once) */
function ensureInitialHistory(){
  // If lottery history doesn't exist, create a 1-year seeded history (but keep size reasonable: store up to ~12000 entries)
  let lh = loadJSON(LOTTERY_KEY, null);
  if(!lh || !Array.isArray(lh) || lh.length===0){
    lh = seedLotteryOneYear();
    saveJSON(LOTTERY_KEY, lh);
  }
  // Satta: daily entries for 1 year
  let sh = loadJSON(SATTA_KEY, null);
  if(!sh || typeof sh !== 'object'){
    sh = seedSattaOneYear();
    saveJSON(SATTA_KEY, sh);
  }
}
function seedLotteryOneYear(){
  const out = [];
  const end = nowIST();
  const start = new Date(end); start.setFullYear(end.getFullYear()-1);
  for(let d = new Date(start); d <= end; d.setDate(d.getDate()+1)){
    // add entries for all days (including Sundays) between 9 and 21 every 15 minutes
    for(let h=9; h<21; h++){
      for(let m=0; m<60; m+=15){
        const dt = new Date(d); dt.setHours(h,m,0,0);
        if(dt <= end){
          out.push({
            dateISO: dt.toISOString(),
            A: Math.floor(Math.random()*10),
            B: Math.floor(Math.random()*10),
            C: Math.floor(Math.random()*10),
            slot: `${String(h).padStart(2,'0')}:${String(m).padStart(2,'0')}`
          });
        }
      }
    }
  }
  // keep only last ~12000 entries
  if(out.length > 20000) return out.slice(out.length-20000);
  return out;
}
function seedSattaOneYear(){
  const out = {};
  const end = nowIST();
  const start = new Date(end); start.setFullYear(end.getFullYear()-1);
  for(let d = new Date(start); d <= end; d.setDate(d.getDate()+1)){
    const dt = new Date(d); dt.setHours(16,0,0,0);
    if(dt <= end){
      out[new Date(d).toISOString().slice(0,10)] = String(Math.floor(Math.random()*100)).padStart(2,'0');
    }
  }
  return out;
}

/* -------------------------
  Satta: daily result logic
--------------------------*/
function updateSattaDisplay(now){
  const hh = now.getHours();
  const todayKey = now.toISOString().slice(0,10);
  const sattaStore = loadJSON(SATTA_KEY,{});
  if(hh >= 16){
    // ensure today's result exists
    if(!sattaStore[todayKey]){
      sattaStore[todayKey] = String(Math.floor(Math.random()*100)).padStart(2,'0');
      saveJSON(SATTA_KEY, sattaStore);
    }
    todaySattaNumEl.textContent = sattaStore[todayKey];
    sattaDateEl.textContent = now.toLocaleDateString('en-IN', { year:'numeric', month:'long', day:'numeric' });
  } else {
    todaySattaNumEl.textContent = 'XX';
    sattaDateEl.textContent = 'Check after 4:00 PM';
  }
}

/* Generate satta history table (days param) */
function generateSattaHistory(days=7){
  const store = loadJSON(SATTA_KEY,{});
  // collect keys, sort desc
  const keys = Object.keys(store).sort((a,b)=> b.localeCompare(a));
  const toShow = keys.slice(0, days);
  sattaHistoryTbody.innerHTML = '';
  if(toShow.length===0){
    sattaHistoryTbody.innerHTML = `<tr><td colspan="3" class="empty-result">No satta results available</td></tr>`;
    return;
  }
  toShow.forEach(k=>{
    const dt = new Date(k);
    const dateStr = dt.toLocaleDateString('en-IN', { day:'numeric', month:'short', year:'numeric' });
    const dow = dt.toLocaleDateString('en-IN', { weekday:'short' });
    const row = document.createElement('tr');
    row.innerHTML = `<td>${dateStr}</td><td>${store[k]}</td><td>${dow}</td>`;
    sattaHistoryTbody.appendChild(row);
  });
}

/* -------------------------
  Lottery utilities
--------------------------*/
function isWithinLotteryHours(now){
  const h = now.getHours();
  return (h >= 9 && h < 21);
}

// returns next draw Date object in IST
function nextDrawIST(now){
  const n = new Date(now);
  if(!isWithinLotteryHours(now)){
    // next is tomorrow 9:00 AM
    const nxt = new Date(now);
    nxt.setDate(nxt.getDate() + 1);
    nxt.setHours(9,0,0,0);
    return nxt;
  }
  const m = now.getMinutes();
  const nextSlotMin = Math.ceil((m+0.0001) / 15) * 15;
  if(nextSlotMin === 60){
    const nxt = new Date(now);
    nxt.setHours(now.getHours()+1, 0, 0, 0);
    return nxt;
  } else {
    const nxt = new Date(now);
    nxt.setMinutes(nextSlotMin, 0, 0);
    return nxt;
  }
}

/* Flip animation helper */
function flipDigit(containerId, newVal){
  const container = document.getElementById(containerId);
  if(!container) return;
  const face = container.querySelector('.face') || container;
  // create a quick flip effect: rotateX
  face.style.transform = 'rotateX(-90deg)';
  setTimeout(()=> {
    face.textContent = newVal;
    face.style.transform = 'rotateX(0deg)';
  }, 220);
}

/* Save lottery entry */
function saveLotteryEntry(dt, A,B,C){
  const history = loadJSON(LOTTERY_KEY, []);
  history.push({
    dateISO: dt.toISOString(),
    A, B, C,
    slot: `${String(dt.getHours()).padStart(2,'0')}:${String(dt.getMinutes()).padStart(2,'0')}`
  });
  // keep last 20000 records
  if(history.length > 20000) history.splice(0, history.length - 20000);
  saveJSON(LOTTERY_KEY, history);
}

/* Update current/previous displays from history (most recent entries) */
function refreshCurrentFromHistory(){
  const history = loadJSON(LOTTERY_KEY, []);
  if(history.length === 0) return;
  // find last entry in IST <= now
  const now = nowIST();
  const entries = history.filter(e => new Date(e.dateISO) <= now);
  if(entries.length === 0) return;
  const last = entries[entries.length-1];
  const prev = entries.length > 1 ? entries[entries.length-2] : null;
  flipDigit('flip-a', last.A);
  flipDigit('flip-b', last.B);
  flipDigit('flip-c', last.C);
  currentA.textContent = last.A; currentB.textContent = last.B; currentC.textContent = last.C;
  lotteryUpdateTime.textContent = new Date(last.dateISO).toLocaleTimeString('en-IN', { hour:'2-digit', minute:'2-digit', hour12:true });
  if(prev){
    prevA.textContent = prev.A; prevB.textContent = prev.B; prevC.textContent = prev.C;
    previousLotteryTime.textContent = `Updated: ${new Date(prev.dateISO).toLocaleTimeString('en-IN', { hour:'2-digit', minute:'2-digit', hour12:true })}`;
  }
}

/* Generate today's or filtered lottery history */
function generateLotteryHistory(days=1, specificDate=null){
  const history = loadJSON(LOTTERY_KEY, []);
  lotteryHistoryTbody.innerHTML = '';
  const now = nowIST();
  let filtered = [];
  if(specificDate){
    const key = specificDate.toISOString().slice(0,10);
    filtered = history.filter(e => e.dateISO.slice(0,10) === key);
  } else {
    const start = new Date(now); start.setDate(now.getDate() - (days-1));
    filtered = history.filter(e => new Date(e.dateISO) >= start);
  }
  // newest first
  filtered.reverse();
  if(filtered.length === 0){
    lotteryHistoryTbody.innerHTML = `<tr><td colspan="6" class="empty-result">No lottery results available for this period</td></tr>`;
    return;
  }
  filtered.forEach(entry=>{
    const dt = new Date(entry.dateISO);
    const dStr = dt.toLocaleDateString('en-IN', { day:'numeric', month:'short', year:'numeric' });
    const tStr = dt.toLocaleTimeString('en-IN', { hour:'2-digit', minute:'2-digit', hour12:true });
    const tr = document.createElement('tr');
    tr.innerHTML = `<td>${dStr}</td><td>${tStr}</td><td>${entry.A}</td><td>${entry.B}</td><td>${entry.C}</td><td>${entry.slot}</td>`;
    lotteryHistoryTbody.appendChild(tr);
  });
}

/* Generate a new draw (should be executed exactly at draw times OR via admin) */
function performDraw(manualDate=null, manualA=null, manualB=null, manualC=null){
  const now = manualDate ? new Date(manualDate) : nowIST();
  if(!isWithinLotteryHours(now) && !manualDate) return;
  const A = manualA !== null ? manualA : Math.floor(Math.random()*10);
  const B = manualB !== null ? manualB : Math.floor(Math.random()*10);
  const C = manualC !== null ? manualC : Math.floor(Math.random()*10);
  saveLotteryEntry(now, A, B, C);
  refreshCurrentFromHistory();
  generateLotteryHistory(1);
}

/* Countdown update */
function updateCountdownAndNextTime(){
  const now = nowIST();
  const nxt = nextDrawIST(now);
  // display next draw human readable
  nextLotteryTimeEl.textContent = nxt.toLocaleTimeString('en-IN', { hour:'2-digit', minute:'2-digit', hour12:true });
  // countdown
  let diff = Math.max(0, Math.floor((nxt - now)/1000));
  const mm = String(Math.floor(diff/60)).padStart(2,'0');
  const ss = String(diff % 60).padStart(2,'0');
  countdownEl.textContent = `${mm}:${ss}`;
  // show/hide lottery container
  const container = document.getElementById('lottery-results-container');
  const closed = document.getElementById('lottery-closed-message');
  if(isWithinLotteryHours(now)){
    container.style.display = 'block'; closed.style.display='none';
  } else { container.style.display='none'; closed.style.display='block' }
}

/* Initialize dropdowns for date search */
function populateDateDropdowns(){
  const yearSel = document.getElementById('year-select');
  const monthSel = document.getElementById('month-select');
  const daySel = document.getElementById('day-select');
  const now = nowIST();
  yearSel.innerHTML = '';
  for(let y = now.getFullYear(); y >= now.getFullYear()-2; y--){
    const opt = document.createElement('option'); opt.value=y; opt.textContent=y; yearSel.appendChild(opt);
  }
  const months = ['January','February','March','April','May','June','July','August','September','October','November','December'];
  monthSel.innerHTML = '';
  months.forEach((m,i)=>{ const o=document.createElement('option'); o.value=i+1; o.textContent=m; if(i===now.getMonth()) o.selected=true; monthSel.appendChild(o) });
  function fillDays(){
    const y = Number(yearSel.value); const mo = Number(monthSel.value);
    const days = new Date(y, mo, 0).getDate();
    daySel.innerHTML='';
    for(let d=1; d<=days; d++){
      const o=document.createElement('option'); o.value=d; o.textContent=d;
      if(d===now.getDate() && mo===now.getMonth()+1 && y===now.getFullYear()) o.selected=true;
      daySel.appendChild(o);
    }
  }
  yearSel.addEventListener('change', fillDays); monthSel.addEventListener('change', fillDays);
  fillDays();
}

/* -------------------------
  History button handlers
--------------------------*/
document.querySelectorAll('#satta .history-btn').forEach(btn=>{
  btn.addEventListener('click', ()=> {
    document.querySelectorAll('#satta .history-btn').forEach(b=>b.classList.remove('active'));
    btn.classList.add('active');
    const days = Number(btn.getAttribute('data-days'));
    generateSattaHistory(days);
  });
});
document.querySelectorAll('#lottery .history-btn').forEach(btn=>{
  btn.addEventListener('click', ()=> {
    document.querySelectorAll('#lottery .history-btn').forEach(b=>b.classList.remove('active'));
    btn.classList.add('active');
    const days = Number(btn.getAttribute('data-days'));
    generateLotteryHistory(days);
  });
});
document.getElementById('date-search-btn').addEventListener('click', ()=>{
  const y = Number(document.getElementById('year-select').value);
  const m = Number(document.getElementById('month-select').value)-1;
  const d = Number(document.getElementById('day-select').value);
  const sdate = new Date(y,m,d);
  generateLotteryHistory(0, sdate);
});

/* -------------------------
  Admin: hidden trigger and modal content
--------------------------*/
let adminClicks = 0, lastClickAt = 0;
const adminTrigger = document.getElementById('hidden-admin-trigger');
adminTrigger.addEventListener('click', ()=>{
  const now = Date.now();
  if(now - lastClickAt < 700) adminClicks++; else adminClicks = 1;
  lastClickAt = now;
  if(adminClicks >= 3) openAdminLogin();
});

function openModal(html){
  modalContent.innerHTML = html;
  modalBackdrop.style.display='flex';
}
function closeModal(){ modalBackdrop.style.display='none'; modalContent.innerHTML=''; }

/* Admin login UI */
function openAdminLogin(){
  openModal(`
    <h3 id="modal-title">Admin Login</h3>
    <label>Enter Secret Key</label>
    <input id="admin-key" type="password" placeholder="Secret Key" />
    <div style="margin-top:10px;display:flex;gap:8px;justify-content:flex-end">
      <button class="btn-primary" id="admin-submit">Unlock</button>
      <button id="admin-cancel" style="padding:8px 12px;border-radius:8px;border:none;background:rgba(255,255,255,0.03);color:#fff">Cancel</button>
    </div>
  `);
  document.getElementById('admin-cancel').addEventListener('click', closeModal);
  document.getElementById('admin-submit').addEventListener('click', ()=>{
    const v = document.getElementById('admin-key').value;
    if(v === ADMIN_SECRET) { openAdminPanel(); } else { alert('Invalid key'); }
  });
}

/* Admin panel UI for manual operations */
function openAdminPanel(){
  openModal(`
    <h3>Admin Panel</h3>
    <label>Manual Satta - Set today's result (00-99)</label>
    <input id="admin-satta-val" placeholder="e.g. 07" maxlength="2" />
    <label style="margin-top:8px">Manual Lottery - Set draw for specific date/time (IST)</label>
    <div class="row">
      <div class="col"><input id="admin-lottery-dt" type="datetime-local" /></div>
    </div>
    <div style="display:flex;gap:8px;margin-top:8px">
      <input id="admin-lottery-a" placeholder="A (0-9)" maxlength="1" />
      <input id="admin-lottery-b" placeholder="B (0-9)" maxlength="1" />
      <input id="admin-lottery-c" placeholder="C (0-9)" maxlength="1" />
    </div>
    <div style="display:flex;gap:8px;margin-top:10px;justify-content:flex-end">
      <button class="btn-primary" id="admin-save">Save</button>
      <button id="admin-close" style="padding:8px 12px;border-radius:8px;border:none;background:rgba(255,255,255,0.03);color:#fff">Close</button>
    </div>
    <div style="margin-top:12px;color:var(--muted);font-size:13px">Manual draws are stored immediately and will reflect in history and current displays.</div>
  `);
  document.getElementById('admin-close').addEventListener('click', closeModal);
  document.getElementById('admin-save').addEventListener('click', ()=>{
    // Satta manual
    const sv = document.getElementById('admin-satta-val').value.trim();
    if(sv){
      if(!/^\d{1,2}$/.test(sv)) { alert('Satta must be 00-99'); return; }
      const padded = String(Number(sv)).padStart(2,'0');
      const todayKey = nowIST().toISOString().slice(0,10);
      const sh = loadJSON(SATTA_KEY,{});
      sh[todayKey] = padded;
      saveJSON(SATTA_KEY, sh);
      updateSattaDisplay(nowIST());
      generateSattaHistory(7);
      alert('Satta updated');
    }
    // Lottery manual
    const dtVal = document.getElementById('admin-lottery-dt').value;
    const aVal = document.getElementById('admin-lottery-a').value.trim();
    const bVal = document.getElementById('admin-lottery-b').value.trim();
    const cVal = document.getElementById('admin-lottery-c').value.trim();
    if(dtVal && (aVal!=='' || bVal!=='' || cVal!=='')){
      // dtVal is local datetime - we need to treat it as IST user typically enters IST, so convert to Date as local then shift to IST by constructing with the value parts
      const manualDt = new Date(dtVal);
      // Use the manual values (if missing, generate random)
      const A = aVal !== '' ? Number(aVal) : Math.floor(Math.random()*10);
      const B = bVal !== '' ? Number(bVal) : Math.floor(Math.random()*10);
      const C = cVal !== '' ? Number(cVal) : Math.floor(Math.random()*10);
      // Save
      saveLotteryEntry(manualDt, A,B,C);
      refreshCurrentFromHistory();
      generateLotteryHistory(1);
      alert('Manual lottery draw saved');
    }
    closeModal();
  });
}

/* close modal on backdrop click */
modalBackdrop.addEventListener('click', (e)=>{
  if(e.target === modalBackdrop) closeModal();
});

/* -------------------------
  Timers: clock, countdown, scheduled draws
--------------------------*/
function tickAll(){
  const now = nowIST();
  timeEl.textContent = now.toLocaleTimeString('en-IN', { hour:'2-digit', minute:'2-digit', second:'2-digit', hour12:true });
  // update satta display
  updateSattaDisplay(now);
  // countdown & next
  updateCountdownAndNextTime();
  // update current/prev displays (from history)
  refreshCurrentFromHistory();
  // update history shown by active buttons
  // (no-op here)
}

// schedule draws at exact 15-min marks; we check every second and perform draw on transition
let lastDrawISO = null;
function checkAndPerformDraw(){
  const now = nowIST();
  if(!isWithinLotteryHours(now)) return;
  const minutes = now.getMinutes();
  const seconds = now.getSeconds();
  // If we are exactly at a draw minute (multiple of 15) and seconds close to 0, perform draw
  if(minutes % 15 === 0 && seconds < 2){
    // ensure not already performed for this slot
    const slotISO = new Date(now); slotISO.setSeconds(0,0);
    const iso = slotISO.toISOString();
    if(iso !== lastDrawISO){
      performDraw(slotISO);
      lastDrawISO = iso;
    }
  }
}

/* periodic refreshes */
function startIntervals(){
  tickAll();
  setInterval(tickAll, 1000); // clock & countdown
  setInterval(checkAndPerformDraw, 800); // check draws frequently
  // also refresh displays every 10s to keep UI in sync
  setInterval(()=>{ refreshCurrentFromHistory(); generateLotteryHistory(1); }, 10000);
}

/* -------------------------
  Init
--------------------------*/
function init(){
  ensureInitialHistory();
  // show last saved results immediately
  refreshCurrentFromHistory();
  generateLotteryHistory(1);
  generateSattaHistory(7);
  populateDateDropdowns();
  startIntervals();
}
init();

/* Expose some functions for debugging (optional) */
window._shalimar = {
  performDraw, saveLotteryEntry, loadJSON, saveJSON
};
</script>
</body>
</html>
