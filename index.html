<!DOCTYPE html>
<html lang="zh-TW">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>2026 薪資條產生器</title>
<script src="https://cdnjs.cloudflare.com/ajax/libs/html2canvas/1.4.1/html2canvas.min.js"></script>
<style>
  * { box-sizing: border-box; margin: 0; padding: 0; }
  body {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
    font-size: 14px;
    background: #f5f5f0;
    color: #1a1a1a;
    min-height: 100vh;
    padding: 32px 16px;
  }
  h1 {
    font-size: 18px;
    font-weight: 500;
    margin-bottom: 20px;
    color: #1a1a1a;
  }
  .page { max-width: 600px; margin: 0 auto; }

  /* controls */
  .controls {
    background: #fff;
    border: 1px solid #e2e2e2;
    border-radius: 12px;
    padding: 16px;
    display: flex;
    gap: 12px;
    flex-wrap: wrap;
    align-items: flex-end;
    margin-bottom: 16px;
  }
  .field { display: flex; flex-direction: column; gap: 4px; }
  .field label { font-size: 11px; color: #888; text-transform: uppercase; letter-spacing: .4px; }
  .field select, .field input {
    padding: 7px 10px;
    border: 1px solid #ddd;
    border-radius: 8px;
    background: #fff;
    color: #1a1a1a;
    font-size: 13px;
    outline: none;
  }
  .field select:focus, .field input:focus { border-color: #999; }

  /* payslip card */
  #slip {
    background: #fff;
    border: 1px solid #e2e2e2;
    border-radius: 12px;
    overflow: hidden;
    margin-bottom: 14px;
  }
  .slip-header {
    background: #1a1a1a;
    color: #fff;
    padding: 20px 24px;
  }
  .slip-header .co {
    font-size: 10px;
    opacity: .5;
    margin-bottom: 5px;
    text-transform: uppercase;
    letter-spacing: .8px;
  }
  .slip-header .title {
    font-size: 20px;
    font-weight: 500;
    margin-bottom: 3px;
  }
  .slip-header .meta {
    font-size: 11px;
    opacity: .5;
    display: flex;
    gap: 16px;
    flex-wrap: wrap;
    margin-top: 6px;
  }
  .slip-body { padding: 18px 24px; background: #fff; }
  .slip-section {
    font-size: 10px;
    font-weight: 600;
    color: #aaa;
    text-transform: uppercase;
    letter-spacing: .6px;
    margin: 14px 0 6px;
  }
  .slip-section:first-child { margin-top: 0; }
  .slip-row {
    display: flex;
    justify-content: space-between;
    align-items: baseline;
    padding: 7px 0;
    border-bottom: 1px solid #f0f0f0;
    font-size: 13px;
  }
  .slip-row:last-child { border-bottom: none; }
  .slip-row .k { color: #888; }
  .slip-row .v { font-weight: 500; font-variant-numeric: tabular-nums; }
  .slip-row.subtotal .k { color: #1a1a1a; font-weight: 600; }
  .slip-row.subtotal .v { color: #1a1a1a; }

  /* month calendar */
  .month-row {
    display: grid;
    grid-template-columns: repeat(6, 1fr);
    gap: 4px;
    padding: 4px 0;
  }
  .mbox {
    border-radius: 6px;
    padding: 5px 4px;
    text-align: center;
    font-size: 10px;
  }
  .mbox-normal { background: #f3f3f3; color: #888; }
  .mbox-bonus  { background: #dbeeff; color: #1a5fa8; }
  .mbox-current{ background: #1a5fa8; color: #fff; }
  .month-legend {
    display: flex;
    gap: 14px;
    font-size: 10px;
    color: #aaa;
    margin-top: 6px;
  }
  .month-legend span b { margin-right: 3px; }

  /* totals */
  .slip-total {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 14px 24px;
    background: #f5f5f5;
    border-top: 1px solid #e8e8e8;
  }
  .slip-total .left .k { font-size: 12px; color: #888; }
  .slip-total .left .ksub { font-size: 10px; color: #bbb; margin-top: 2px; }
  .slip-total .v { font-size: 24px; font-weight: 500; color: #1a1a1a; }

  .slip-avg {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 12px 24px;
    background: #eef6ff;
    border-top: 1px solid #c8dff5;
  }
  .slip-avg .left .k { font-size: 11px; color: #2563a8; }
  .slip-avg .left .ksub { font-size: 10px; color: #82aacc; margin-top: 2px; }
  .slip-avg .v { font-size: 20px; font-weight: 500; color: #1a4f8a; }

  .slip-note {
    padding: 12px 24px 14px;
    background: #fff;
    border-top: 1px solid #f0f0f0;
  }
  .slip-note .note-label {
    font-size: 10px;
    font-weight: 600;
    color: #aaa;
    text-transform: uppercase;
    letter-spacing: .6px;
    margin-bottom: 6px;
  }
  .slip-note textarea {
    width: 100%;
    min-height: 56px;
    resize: vertical;
    border: 1px solid #e8e8e8;
    border-radius: 6px;
    padding: 8px 10px;
    font-family: inherit;
    font-size: 12px;
    color: #1a1a1a;
    background: #fafafa;
    outline: none;
    line-height: 1.6;
  }
  .slip-note textarea:focus { border-color: #bbb; background: #fff; }
  .slip-note textarea::placeholder { color: #bbb; }
  /* printed note (no textarea border) */
  .note-print {
    display: none;
    font-size: 12px;
    color: #444;
    line-height: 1.7;
    white-space: pre-wrap;
    min-height: 20px;
  }
  .slip-footer {
    display: flex;
    justify-content: space-between;
    padding: 9px 24px;
    font-size: 10px;
    color: #bbb;
    background: #fff;
    border-top: 1px solid #f0f0f0;
  }

  /* buttons */
  .actions { display: flex; gap: 10px; }
  .btn {
    cursor: pointer;
    font-family: inherit;
    font-size: 13px;
    padding: 8px 16px;
    border-radius: 8px;
    border: 1px solid #ddd;
    background: #fff;
    color: #1a1a1a;
    display: flex;
    align-items: center;
    gap: 6px;
    transition: background .1s;
  }
  .btn:hover { background: #f5f5f5; }
  .btn-primary {
    background: #1a1a1a;
    color: #fff;
    border-color: transparent;
  }
  .btn-primary:hover { opacity: .85; }
  .btn:disabled { opacity: .5; cursor: default; }
  #feedback {
    font-size: 12px;
    color: #1a8a3a;
    margin-top: 8px;
    height: 18px;
  }
</style>
</head>
<body>
<div class="page">
  <h1>2026 薪資條產生器</h1>

  <!-- 控制列 -->
  <div class="controls">
    <div class="field">
      <label>姓名</label>
      <input type="text" id="nameInput" value="王大明" style="width:100px"/>
    </div>
    <div class="field">
      <label>G 職等</label>
      <select id="gSel" style="width:84px"></select>
    </div>
    <div class="field">
      <label>P 等級</label>
      <select id="pSel" style="width:84px"></select>
    </div>
    <div class="field">
      <label>英語加給</label>
      <select id="engSel" style="width:110px">
        <option value="0">無</option>
        <option value="600">Level A</option>
        <option value="1200">Level B</option>
        <option value="2000">Level C</option>
        <option value="2600">Level D</option>
        <option value="3200">Level E</option>
      </select>
    </div>
    <div class="field">
      <label>季度</label>
      <select id="seasonSel" style="width:100px">
        <option value="Q1">Q1（1月）</option>
        <option value="Q2">Q2（4月）</option>
        <option value="Q3">Q3（7月）</option>
        <option value="Q4">Q4（10月）</option>
      </select>
    </div>
  </div>

  <!-- 薪資條 -->
  <div id="slip">
    <div class="slip-header">
      <div class="co">2026 薪資條</div>
      <div class="title" id="shName">王大明</div>
      <div class="meta">
        <span id="shGP">—</span>
        <span id="shSeason">—</span>
        <span id="shDate">—</span>
      </div>
    </div>

    <div class="slip-body">
      <div class="slip-section">固定薪資</div>
      <div class="slip-row">
        <span class="k">基礎薪資（<span id="sbG">—</span>）</span>
        <span class="v" id="sbBase">—</span>
      </div>
      <div class="slip-row" id="engRow">
        <span class="k">英語能力加給</span>
        <span class="v" id="sbEng">—</span>
      </div>
      <div class="slip-row subtotal">
        <span class="k">月薪小計</span>
        <span class="v" id="sbNormal">—</span>
      </div>

      <div class="slip-section">季度績效紅利</div>
      <div class="slip-row">
        <span class="k">P 等級（<span id="sbP">—</span>）</span>
        <span class="v" id="sbQB">—</span>
      </div>

      <div class="slip-section">全年發薪概覽</div>
      <div class="month-row" id="monthRow"></div>
      <div class="month-legend">
        <span><b style="color:#1a5fa8">■</b> 本季（當月）</span>
        <span><b style="color:#82aacc">■</b> 一般發放月</span>
        <span><b style="color:#ccc">■</b> 一般月</span>
      </div>
    </div>

    <div class="slip-total">
      <div class="left">
        <div class="k">本月實領（發放月）</div>
        <div class="ksub">月薪 + 季度紅利</div>
      </div>
      <div class="v" id="stTotal">—</div>
    </div>
    <div class="slip-avg">
      <div class="left">
        <div class="k">每月平均（紅利攤算）</div>
        <div class="ksub">月薪 + 紅利 ÷ 3</div>
      </div>
      <div class="v" id="stAvg">—</div>
    </div>
    <div class="slip-note">
      <div class="note-label">人資備註</div>
      <textarea id="noteInput" placeholder="可輸入備註事項，例如：調薪生效日、特殊說明、簽核備忘…"></textarea>
      <div class="note-print" id="notePrint"></div>
    </div>

    <div class="slip-footer">
      <span>紅利發放：4/10、7/10、10/10、翌年 1/10</span>
      <span id="sfDate">—</span>
    </div>
  </div>

  <!-- 操作按鈕 -->
  <div class="actions">
    <button class="btn" onclick="copyText()">
      <svg width="14" height="14" viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.5">
        <rect x="5" y="5" width="9" height="9" rx="1.5"/>
        <path d="M3 11V3a1 1 0 011-1h8"/>
      </svg>
      複製文字
    </button>
    <button class="btn btn-primary" id="imgBtn" onclick="downloadImg()">
      <svg width="14" height="14" viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.5">
        <rect x="2" y="2" width="12" height="12" rx="2"/>
        <path d="M2 10.5l3-3 2.5 2.5 2-2 4.5 4"/>
        <circle cx="5.5" cy="5.5" r="1"/>
      </svg>
      截圖下載
    </button>
  </div>
  <div id="feedback"></div>
</div>

<script>
const P_LEVELS = ['P0','P20','P30','P40','P60','P80','P100','P120','P140','P160',
  'P180','P200','P220','P240','P260','P280','P300','P320','P340','P360',
  'P380','P400','P420','P440','P460'];

const G_BASE = {
  G0:29500, G1:30000, G2:31000, G3:31500, G4:32000,
  G5:34000, G6:36000, G7:38000, G8:40000, G9:43000,
  G10:45000, G11:48000, G12:52000, G13:55000, G14:58000,
  G15:62000, G16:65000, G17:69000, G18:74000, G19:78000, G20:83000
};

const QB = {
  G0: [null,null,1500,3000,4500,9000,6300,10800,13050,15300,17550,19800,22050,24300,null,null,null,null,null,null,null,null,null,null,null],
  G1: [null,null,1950,3900,5850,7800,10050,12300,14550,16800,19050,21300,23550,25800,28050,null,null,null,null,null,null,null,null,null,null],
  G2: [null,null,1950,3900,5850,7800,10500,13200,15900,18600,21300,24000,26700,29400,32100,34800,null,null,null,null,null,null,null,null,null],
  G3: [null,null,1500,4500,7500,10500,13500,16500,19500,22500,25500,28500,31500,34500,37500,40500,43500,null,null,null,null,null,null,null,null],
  G4: [null,null,3000,6000,9000,12000,15000,18000,21000,24000,27000,30000,33000,36000,39000,42000,45000,48000,null,null,null,null,null,null,null],
  G5: [null,null,3000,6000,9000,12000,15000,18000,21000,24000,27000,30000,33000,36000,39000,42000,45000,48000,51000,null,null,null,null,null,null],
  G6: [null,null,3000,6000,9000,12000,15000,18000,21000,24000,27000,30000,33000,36000,39000,42000,45000,48000,51000,54000,null,null,null,null,null],
  G7: [null,null,3000,6000,9000,12000,15000,18000,21000,24000,27000,30000,33000,36000,39000,42000,45000,48000,51000,54000,57000,null,null,null,null],
  G8: [null,null,3000,6000,9000,12000,15000,18000,21000,24000,27000,30000,33000,36000,39000,42000,45000,48000,51000,54000,57000,60000,null,null,null],
  G9: [null,null,3000,6000,9000,12000,15000,18000,21000,24000,27000,30000,33000,36000,39000,42000,45000,48000,51000,54000,57000,60000,63000,null,null],
  G10:[null,null,3000,6000,9000,12000,15000,18000,21000,24000,27000,30000,33000,36000,39000,42000,45000,48000,51000,54000,57000,60000,63000,66000,null],
  G11:[null,null,3600,7200,10800,14400,18000,21600,25200,28800,32400,36000,39600,43200,46800,50400,54000,57600,61200,64800,68400,72000,75600,79200,82800],
  G12:[null,null,3600,7200,10800,14400,18000,21600,25200,28800,32400,36000,39600,43200,46800,50400,54000,57600,61200,64800,68400,72000,75600,79200,82800],
  G13:[null,null,3600,7200,10800,14400,18000,21600,25200,28800,32400,36000,39600,43200,46800,50400,54000,57600,61200,64800,68400,72000,75600,79200,82800],
  G14:[null,null,3600,7200,10800,14400,18000,21600,25200,28800,32400,36000,39600,43200,46800,50400,54000,57600,61200,64800,68400,72000,75600,79200,82800],
  G15:[null,null,4500,9000,13500,18000,22500,27000,31500,36000,40500,45000,49500,54000,58500,63000,67500,72000,76500,81000,85500,90000,94500,99000,103500],
  G16:[null,null,4500,9000,13500,18000,22500,27000,31500,36000,40500,45000,49500,54000,58500,63000,67500,72000,76500,81000,85500,90000,94500,99000,103500],
  G17:[null,null,4500,9000,13500,18000,22500,27000,31500,36000,40500,45000,49500,54000,58500,63000,67500,72000,76500,81000,85500,90000,94500,99000,103500],
  G18:[null,null,4500,9000,13500,18000,22500,27000,31500,36000,40500,45000,49500,54000,58500,63000,67500,72000,76500,81000,85500,90000,94500,99000,103500],
  G19:[null,null,5400,10800,16200,21600,27000,32400,37800,43200,48600,54000,59400,64800,70200,75600,81000,86400,91800,97200,102600,108000,113400,118800,124200],
  G20:[null,null,5400,10800,16200,21600,27000,32400,37800,43200,48600,54000,59400,64800,70200,75600,81000,86400,91800,97200,102600,108000,113400,118800,124200]
};

const MONTHS = ['1月','2月','3月','4月','5月','6月','7月','8月','9月','10月','11月','12月'];
const BONUS_IDX = [0, 3, 6, 9];
const SEASON_MONTH = { Q1:0, Q2:3, Q3:6, Q4:9 };
const G_KEYS = Object.keys(G_BASE);

const fmt = n => '$' + (Math.round(n) || 0).toLocaleString('zh-TW');

// Build G dropdown
const gSel = document.getElementById('gSel');
G_KEYS.forEach(g => {
  const o = document.createElement('option');
  o.value = g; o.textContent = g;
  gSel.appendChild(o);
});
gSel.value = 'G15';

// Build P dropdown
const pSel = document.getElementById('pSel');
function buildP(g, curIdx) {
  pSel.innerHTML = '';
  QB[g].forEach((v, i) => {
    if (v === null) return;
    const o = document.createElement('option');
    o.value = i; o.textContent = P_LEVELS[i];
    pSel.appendChild(o);
  });
  if (curIdx != null) pSel.value = String(curIdx);
}
buildP('G15', 6);

function update() {
  const g       = gSel.value;
  const pIdx    = parseInt(pSel.value);
  const eng     = parseInt(document.getElementById('engSel').value) || 0;
  const season  = document.getElementById('seasonSel').value;
  const name    = document.getElementById('nameInput').value || '—';
  const curMonth = SEASON_MONTH[season];

  const base  = G_BASE[g];
  const qb    = QB[g][pIdx];
  const normal = base + eng;
  const bMonth = qb != null ? normal + qb : normal;
  const avg    = qb != null ? Math.round(normal + qb / 3) : normal;

  // Header
  document.getElementById('shName').textContent   = name;
  document.getElementById('shGP').textContent     = g + ' / ' + P_LEVELS[pIdx];
  document.getElementById('shSeason').textContent = season + ' 發放月';
  document.getElementById('shDate').textContent   = '2026 年 ' + MONTHS[curMonth];

  // Body
  document.getElementById('sbG').textContent    = g;
  document.getElementById('sbBase').textContent = fmt(base);
  document.getElementById('sbP').textContent    = P_LEVELS[pIdx];
  document.getElementById('sbQB').textContent   = qb != null ? fmt(qb) : '不適用';
  document.getElementById('sbNormal').textContent = fmt(normal);

  const engRow = document.getElementById('engRow');
  if (eng > 0) {
    engRow.style.display = 'flex';
    document.getElementById('sbEng').textContent = fmt(eng);
  } else {
    engRow.style.display = 'none';
  }

  // Month calendar
  const mr = document.getElementById('monthRow');
  mr.innerHTML = MONTHS.map((m, i) => {
    const isBonus   = BONUS_IDX.includes(i);
    const isCurrent = i === curMonth;
    const val       = isBonus ? bMonth : normal;
    const cls       = isCurrent ? 'mbox mbox-current' : isBonus ? 'mbox mbox-bonus' : 'mbox mbox-normal';
    return `<div class="${cls}">
      <div style="margin-bottom:2px">${m}</div>
      <div style="font-weight:600">${(val / 1000).toFixed(1)}K</div>
    </div>`;
  }).join('');

  // Totals
  document.getElementById('stTotal').textContent = fmt(bMonth);
  document.getElementById('stAvg').textContent   = fmt(avg);

  // Footer date
  const now = new Date();
  document.getElementById('sfDate').textContent =
    '產生於 ' + now.getFullYear() + '/' + (now.getMonth() + 1) + '/' + now.getDate();
}

// ── Text copy ──
function buildText() {
  const g      = gSel.value;
  const pIdx   = parseInt(pSel.value);
  const eng    = parseInt(document.getElementById('engSel').value) || 0;
  const season = document.getElementById('seasonSel').value;
  const name   = document.getElementById('nameInput').value || '—';
  const base   = G_BASE[g];
  const qb     = QB[g][pIdx];
  const normal = base + eng;
  const bMonth = qb != null ? normal + qb : normal;
  const avg    = qb != null ? Math.round(normal + qb / 3) : normal;
  const line   = '─'.repeat(32);
  let t = `2026 薪資條\n${name}　${g} / ${P_LEVELS[pIdx]}　${season}\n${line}\n`;
  t += `基礎薪資（${g}）\t${fmt(base)}\n`;
  if (eng > 0) t += `英語能力加給\t+${fmt(eng)}\n`;
  t += `月薪小計\t\t${fmt(normal)}\n${line}\n`;
  t += `季度績效紅利（${P_LEVELS[pIdx]}）\t${qb != null ? fmt(qb) : '不適用'}\n${line}\n`;
  t += `本月實領（發放月）\t${fmt(bMonth)}\n`;
  t += `每月平均（攤算）\t${fmt(avg)}\n${line}\n`;
  t += `紅利發放：4/10、7/10、10/10、翌年1/10`;
  const note = document.getElementById('noteInput').value.trim();
  if (note) t += `\n${line}\n人資備註：\n${note}`;
  return t;
}

function copyText() {
  navigator.clipboard.writeText(buildText()).then(() => {
    showFeedback('已複製到剪貼板 ✓');
  });
}

// ── Screenshot download ──
function downloadImg() {
  const btn = document.getElementById('imgBtn');
  const textarea = document.getElementById('noteInput');
  const notePrint = document.getElementById('notePrint');

  // swap textarea → plain div for html2canvas
  const noteVal = textarea.value;
  textarea.style.display = 'none';
  notePrint.style.display = noteVal ? 'block' : 'none';
  notePrint.textContent = noteVal;

  btn.disabled = true;
  btn.textContent = '產生中…';

  html2canvas(document.getElementById('slip'), {
    scale: 3,
    backgroundColor: '#ffffff',
    useCORS: true,
    logging: false
  }).then(canvas => {
    const a = document.createElement('a');
    a.download = '薪資條_' + (document.getElementById('nameInput').value || '員工') + '.png';
    a.href = canvas.toDataURL('image/png');
    a.click();
    restore();
    showFeedback('截圖已下載 ✓');
  }).catch(() => {
    restore();
    showFeedback('截圖失敗，請再試一次');
  });

  function restore() {
    textarea.style.display = '';
    notePrint.style.display = 'none';
    btn.disabled = false;
    btn.innerHTML = `<svg width="14" height="14" viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.5">
      <rect x="2" y="2" width="12" height="12" rx="2"/>
      <path d="M2 10.5l3-3 2.5 2.5 2-2 4.5 4"/>
      <circle cx="5.5" cy="5.5" r="1"/>
    </svg> 截圖下載`;
  }
}

function showFeedback(msg) {
  const el = document.getElementById('feedback');
  el.textContent = msg;
  setTimeout(() => el.textContent = '', 2800);
}

// Event listeners
gSel.addEventListener('change', () => { buildP(gSel.value, null); update(); });
pSel.addEventListener('change', update);
document.getElementById('engSel').addEventListener('change', update);
document.getElementById('seasonSel').addEventListener('change', update);
document.getElementById('nameInput').addEventListener('input', update);

update();
</script>
</body>
</html>

