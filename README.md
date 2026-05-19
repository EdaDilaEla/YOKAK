[index.html](https://github.com/user-attachments/files/28015458/index.html)
# YOKAK
YÖKAK kalite güvencesi süreçlerine ilişkin doküman, kanıt ve raporların yer aldığı çalışma alanı.
<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>YÖKAK Akreditasyon Yönetim Sistemi — Mudanya Üniversitesi</title>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/tabler-icons/3.19.0/webfont/tabler-icons.min.css">
<style>
  :root {
    --navy: #0c2340;
    --navy-light: #1a3a5c;
    --blue: #378ADD;
    --green: #27500A;
    --green-light: #639922;
    --orange: #633806;
    --orange-light: #BA7517;
    --red: #72243E;
    --red-light: #C4365A;
    --bg: #f5f6fa;
    --surface: #ffffff;
    --surface2: #f0f2f7;
    --border: #e2e6ef;
    --border2: #d0d5e5;
    --text1: #1a2236;
    --text2: #5a6782;
    --text3: #9ba5be;
    --success-bg: #eaf3de; --success-text: #27500A;
    --info-bg: #e6f1fb; --info-text: #0C447C;
    --warn-bg: #faeeda; --warn-text: #633806;
    --danger-bg: #fbeaf0; --danger-text: #72243E;
    --radius: 10px;
    --radius-sm: 6px;
    --shadow: 0 1px 4px rgba(0,0,0,.08);
    --shadow-md: 0 4px 16px rgba(0,0,0,.1);
  }
  * { box-sizing: border-box; margin: 0; padding: 0; }
  body { font-family: 'Segoe UI', system-ui, -apple-system, sans-serif; background: var(--bg); color: var(--text1); font-size: 14px; }
  a { color: inherit; text-decoration: none; }

  /* ── APP SHELL ── */
  .app { display: flex; height: 100vh; overflow: hidden; }

  /* ── SIDEBAR ── */
  .sb { width: 220px; background: var(--navy); display: flex; flex-direction: column; flex-shrink: 0; box-shadow: 2px 0 12px rgba(0,0,0,.15); }
  .sb-logo { padding: 1.1rem 1rem; border-bottom: 1px solid rgba(255,255,255,.08); }
  .sb-logo-title { font-size: 12.5px; font-weight: 600; color: #fff; line-height: 1.4; letter-spacing: .01em; }
  .sb-logo-sub { font-size: 10px; color: #5a8aad; margin-top: 3px; }
  .sb-logo-badge { display: inline-block; margin-top: 7px; font-size: 9px; background: rgba(55,138,221,.25); color: #7ab8e8; padding: 2px 8px; border-radius: 20px; letter-spacing: .03em; }
  .sb-nav { flex: 1; padding: .5rem 0; overflow-y: auto; }
  .sb-nav::-webkit-scrollbar { width: 3px; }
  .sb-nav::-webkit-scrollbar-thumb { background: rgba(255,255,255,.1); border-radius: 2px; }
  .nsec { padding: .6rem 1rem .2rem; font-size: 9px; text-transform: uppercase; letter-spacing: .1em; color: rgba(122,163,196,.35); font-weight: 600; }
  .ni { display: flex; align-items: center; gap: 8px; padding: .45rem 1rem; cursor: pointer; font-size: 12px; color: #7aa3c4; transition: all .15s; border-left: 2px solid transparent; position: relative; }
  .ni:hover { color: #c2d9ed; background: rgba(255,255,255,.05); }
  .ni.active { background: rgba(55,138,221,.18); color: #85bde8; border-left-color: var(--blue); }
  .ni i { font-size: 15px; flex-shrink: 0; }
  .ni .nb { margin-left: auto; background: rgba(255,255,255,.1); color: #6a9cbf; font-size: 9px; padding: 1px 6px; border-radius: 20px; }
  .sb-foot { padding: .75rem 1rem; border-top: 1px solid rgba(255,255,255,.07); font-size: 11px; color: #4a7a9b; display: flex; align-items: center; gap: 7px; }

  /* ── MAIN ── */
  .main { flex: 1; display: flex; flex-direction: column; overflow: hidden; background: var(--bg); }
  .topbar { padding: .875rem 1.5rem; background: var(--surface); border-bottom: 1px solid var(--border); display: flex; align-items: center; justify-content: space-between; flex-shrink: 0; box-shadow: var(--shadow); }
  .pt { font-size: 16px; font-weight: 600; color: var(--text1); }
  .ps { font-size: 11px; color: var(--text3); margin-top: 2px; }
  .tact { display: flex; gap: 8px; }
  .btnp { background: var(--navy); color: #fff; border: none; border-radius: var(--radius-sm); padding: .45rem 1rem; font-size: 12px; cursor: pointer; display: flex; align-items: center; gap: 5px; font-weight: 500; transition: background .15s; }
  .btnp:hover { background: var(--navy-light); }
  .btns { background: var(--surface); color: var(--text2); border: 1px solid var(--border); border-radius: var(--radius-sm); padding: .45rem 1rem; font-size: 12px; cursor: pointer; display: flex; align-items: center; gap: 5px; transition: all .15s; }
  .btns:hover { background: var(--surface2); }
  .content { flex: 1; overflow-y: auto; padding: 1.5rem; }

  /* ── VIEWS ── */
  .view { display: none; }
  .view.active { display: block; }

  /* ── CARDS ── */
  .cards { display: grid; grid-template-columns: repeat(4, 1fr); gap: 12px; margin-bottom: 1.25rem; }
  .card { background: var(--surface); border-radius: var(--radius); padding: 1rem 1.1rem; border: 1px solid var(--border); box-shadow: var(--shadow); }
  .card-icon { width: 36px; height: 36px; border-radius: var(--radius-sm); display: flex; align-items: center; justify-content: center; margin-bottom: .6rem; font-size: 18px; }
  .card-lbl { font-size: 10px; color: var(--text3); text-transform: uppercase; letter-spacing: .06em; margin-bottom: 4px; font-weight: 600; }
  .card-val { font-size: 24px; font-weight: 700; color: var(--text1); }
  .card-sub { font-size: 10px; color: var(--text3); margin-top: 3px; }
  .card-bar { height: 4px; border-radius: 2px; margin-top: 8px; background: var(--surface2); overflow: hidden; }
  .card-bar-fill { height: 100%; border-radius: 2px; transition: width .4s ease; }

  /* ── SECTION PROGRESS GRID ── */
  .sec-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; margin-bottom: 1.25rem; }
  .sec-card { background: var(--surface); border-radius: var(--radius); padding: 1rem; border: 1px solid var(--border); box-shadow: var(--shadow); }
  .sc-head { display: flex; align-items: center; gap: 8px; margin-bottom: .6rem; }
  .sc-badge { padding: 3px 10px; border-radius: 5px; font-size: 11px; font-weight: 700; }
  .sc-title { font-size: 12px; font-weight: 600; color: var(--text1); flex: 1; }
  .sc-pct { font-size: 13px; font-weight: 700; }
  .sc-bar { height: 5px; background: var(--surface2); border-radius: 3px; overflow: hidden; margin-bottom: .5rem; }
  .sc-bar-fill { height: 100%; border-radius: 3px; transition: width .4s ease; }
  .sc-sub { display: flex; justify-content: space-between; align-items: center; font-size: 11px; padding: 2px 0; border-bottom: 1px solid var(--border); }
  .sc-sub:last-child { border-bottom: none; }
  .sc-sub-name { color: var(--text2); }
  .sc-sub-val { color: var(--text3); font-weight: 600; }

  /* ── PANEL ── */
  .panel { background: var(--surface); border-radius: var(--radius); border: 1px solid var(--border); margin-bottom: 1rem; overflow: hidden; box-shadow: var(--shadow); }
  .ph { padding: .75rem 1rem; border-bottom: 1px solid var(--border); display: flex; align-items: center; justify-content: space-between; background: var(--surface2); }
  .ph-title { font-size: 13px; font-weight: 600; color: var(--text1); display: flex; align-items: center; gap: 7px; }

  /* ── TABLE ── */
  table.dt { width: 100%; border-collapse: collapse; font-size: 12px; }
  .dt th { padding: .55rem 1rem; text-align: left; font-size: 10px; font-weight: 700; text-transform: uppercase; letter-spacing: .06em; color: var(--text3); background: var(--surface2); border-bottom: 1px solid var(--border); }
  .dt td { padding: .55rem 1rem; border-bottom: 1px solid var(--border); color: var(--text1); vertical-align: middle; }
  .dt tr:last-child td { border-bottom: none; }
  .dt tr:hover td { background: #f8f9fc; }

  /* ── BADGE ── */
  .badge { display: inline-flex; align-items: center; padding: 2px 8px; border-radius: 20px; font-size: 10px; font-weight: 600; }
  .b-g { background: var(--success-bg); color: var(--success-text); }
  .b-b { background: var(--info-bg); color: var(--info-text); }
  .b-y { background: var(--warn-bg); color: var(--warn-text); }
  .b-r { background: var(--danger-bg); color: var(--danger-text); }
  .b-gray { background: var(--surface2); color: var(--text3); border: 1px solid var(--border); }

  /* ── TABS ── */
  .tab-row { display: flex; gap: 0; border-bottom: 1px solid var(--border); margin-bottom: 1rem; }
  .tab { padding: .6rem 1.1rem; font-size: 12px; font-weight: 500; cursor: pointer; color: var(--text3); border-bottom: 2px solid transparent; margin-bottom: -1px; transition: all .15s; }
  .tab:hover { color: var(--text2); }
  .tab.active { color: var(--blue); border-bottom-color: var(--blue); font-weight: 600; }

  /* ── CHECKLIST ── */
  .cl-filters { display: flex; gap: 6px; margin-bottom: 1rem; flex-wrap: wrap; align-items: center; }
  .cf { font-size: 11px; padding: 4px 10px; border-radius: 20px; cursor: pointer; border: 1px solid var(--border); color: var(--text2); background: var(--surface); transition: all .15s; font-weight: 500; }
  .cf:hover { border-color: var(--blue); color: var(--blue); }
  .cf.active { background: var(--navy); color: #fff; border-color: var(--navy); }
  .cl-sec-group { margin-bottom: 1rem; }
  .cl-sec-head { display: flex; align-items: center; gap: 8px; padding: .5rem .75rem; border-radius: var(--radius-sm); margin-bottom: 4px; }
  .cl-sub-head { display: flex; align-items: center; gap: 6px; padding: .35rem .75rem .35rem 1.5rem; font-size: 11px; font-weight: 600; color: var(--text2); margin-bottom: 2px; }
  .cl-item { display: flex; align-items: flex-start; gap: 8px; padding: .45rem .75rem .45rem 2.25rem; border-radius: var(--radius-sm); transition: background .12s; }
  .cl-item:hover { background: var(--surface2); }
  .cl-no { width: 22px; height: 22px; border-radius: 50%; background: var(--surface2); display: flex; align-items: center; justify-content: center; font-size: 9px; color: var(--text3); flex-shrink: 0; font-weight: 700; border: 1px solid var(--border); }
  .cl-text { flex: 1; font-size: 12px; color: var(--text1); line-height: 1.45; padding-top: 2px; }
  .cl-olcut { font-size: 10px; color: var(--text3); margin-top: 2px; }
  select.st-sel { font-size: 10px; padding: 3px 6px; border: 1px solid var(--border); border-radius: var(--radius-sm); background: var(--surface); color: var(--text2); cursor: pointer; font-weight: 600; transition: border-color .15s; }
  select.st-sel:focus { outline: none; }

  /* ── BIDR FORM ── */
  .bidr-sec { border: 1px solid var(--border); border-radius: var(--radius); margin-bottom: .75rem; overflow: hidden; box-shadow: var(--shadow); }
  .bs-head { display: flex; align-items: center; gap: 8px; padding: .7rem 1rem; cursor: pointer; background: var(--surface2); transition: background .15s; user-select: none; }
  .bs-head:hover { background: #e8ebf4; }
  .bs-badge { width: 28px; height: 28px; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 12px; font-weight: 700; flex-shrink: 0; }
  .bs-title { font-size: 12px; font-weight: 600; color: var(--text1); }
  .bs-count { margin-left: auto; font-size: 10px; color: var(--text3); }
  .bs-body { padding: 1rem; display: none; }
  .bs-body.open { display: block; }
  .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; margin-bottom: 10px; }
  .full { grid-column: 1 / -1; }
  .fl { font-size: 11px; color: var(--text2); margin-bottom: 4px; font-weight: 600; }
  input.fi, select.fs, textarea.fta { width: 100%; padding: .45rem .7rem; font-size: 12px; border: 1px solid var(--border); border-radius: var(--radius-sm); background: var(--surface); color: var(--text1); transition: border-color .15s; }
  input.fi:focus, select.fs:focus, textarea.fta:focus { outline: none; border-color: var(--blue); box-shadow: 0 0 0 3px rgba(55,138,221,.1); }
  textarea.fta { resize: vertical; min-height: 70px; line-height: 1.55; }
  .ev-add { display: flex; align-items: center; gap: 5px; padding: .35rem .7rem; border: 1px dashed var(--border2); border-radius: var(--radius-sm); font-size: 11px; color: var(--text3); cursor: pointer; background: none; transition: all .15s; }
  .ev-add:hover { background: var(--surface2); color: var(--text2); border-color: var(--blue); }

  /* ── AI PANEL ── */
  .ai-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; }
  .ai-card { border: 1px solid var(--border); border-radius: var(--radius); overflow: hidden; box-shadow: var(--shadow); }
  .ai-head { padding: .75rem 1rem; border-bottom: 1px solid var(--border); display: flex; align-items: center; gap: 8px; background: var(--surface2); }
  .ai-logo { width: 28px; height: 28px; border-radius: 7px; display: flex; align-items: center; justify-content: center; font-size: 12px; font-weight: 700; flex-shrink: 0; }
  .ai-name { font-size: 12px; font-weight: 600; color: var(--text1); }
  .ai-sub { font-size: 10px; color: var(--text3); }
  .ai-msgs { padding: .75rem; min-height: 200px; max-height: 260px; overflow-y: auto; display: flex; flex-direction: column; gap: 6px; background: var(--surface); }
  .msg-b { background: var(--surface2); color: var(--text1); padding: .55rem .75rem; border-radius: var(--radius-sm); font-size: 11px; line-height: 1.55; max-width: 92%; border: 1px solid var(--border); }
  .msg-u { background: var(--info-bg); color: var(--info-text); padding: .55rem .75rem; border-radius: var(--radius-sm); font-size: 11px; line-height: 1.55; max-width: 85%; align-self: flex-end; border: 1px solid rgba(55,138,221,.2); }
  .ai-qbtns { display: flex; flex-wrap: wrap; gap: 4px; padding: .6rem .75rem; border-top: 1px solid var(--border); background: var(--surface2); }
  .qb { font-size: 10px; padding: 3px 9px; background: var(--surface); border: 1px solid var(--border); border-radius: 20px; cursor: pointer; color: var(--text2); font-weight: 500; transition: all .15s; }
  .qb:hover { background: var(--info-bg); color: var(--info-text); border-color: var(--blue); }
  .ai-inp-row { padding: .6rem .75rem; border-top: 1px solid var(--border); display: flex; gap: 6px; background: var(--surface); }
  .ai-inp { flex: 1; padding: .4rem .65rem; font-size: 11px; border: 1px solid var(--border); border-radius: var(--radius-sm); background: var(--surface); color: var(--text1); }
  .ai-inp:focus { outline: none; border-color: var(--blue); }
  .ai-send { padding: .4rem .8rem; font-size: 11px; background: var(--navy); color: #fff; border: none; border-radius: var(--radius-sm); cursor: pointer; font-weight: 600; }
  .ai-send:hover { background: var(--navy-light); }

  /* ── PUKÖ ── */
  .puko-grid { display: grid; grid-template-columns: repeat(4, 1fr); gap: 10px; margin-bottom: 1.25rem; }
  .pk { background: var(--surface); border: 1px solid var(--border); border-radius: var(--radius); padding: .875rem; text-align: center; box-shadow: var(--shadow); }
  .pk-circle { width: 42px; height: 42px; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 18px; font-weight: 700; margin: 0 auto .6rem; }
  .pk-label { font-size: 13px; font-weight: 700; color: var(--text1); margin-bottom: 3px; }
  .pk-sub { font-size: 10px; color: var(--text3); }

  /* ── PROGRESS BAR ── */
  .prog { height: 4px; background: var(--surface2); border-radius: 2px; overflow: hidden; }
  .prog-fill { height: 100%; border-radius: 2px; transition: width .4s; }

  /* ── RESPONSIVE ── */
  @media (max-width: 900px) {
    .cards { grid-template-columns: 1fr 1fr; }
    .sec-grid { grid-template-columns: 1fr; }
    .ai-grid { grid-template-columns: 1fr; }
    .sb { width: 180px; }
  }
  @media (max-width: 650px) {
    .sb { display: none; }
    .cards { grid-template-columns: 1fr 1fr; }
  }

  /* ── SCROLLBAR ── */
  .content::-webkit-scrollbar { width: 5px; }
  .content::-webkit-scrollbar-thumb { background: var(--border2); border-radius: 3px; }
  .content::-webkit-scrollbar-thumb:hover { background: var(--text3); }
</style>
</head>
<body>

<div class="app">

<!-- ───── SIDEBAR ───── -->
<div class="sb">
  <div class="sb-logo">
    <div class="sb-logo-title">YÖKAK Akreditasyon<br>Yönetim Sistemi</div>
    <div class="sb-logo-sub">Mudanya Üniversitesi</div>
    <div class="sb-logo-badge">KK.R.1 · 22 Birim · 61 Madde</div>
  </div>
  <div class="sb-nav">
    <div class="nsec">Genel</div>
    <div class="ni active" onclick="sv('dash',this)"><i class="ti ti-layout-dashboard"></i>Genel Bakış</div>
    <div class="ni" onclick="sv('birimler',this)"><i class="ti ti-building"></i>Tüm Birimler<span class="nb">22</span></div>
    <div class="nsec">Akreditasyon</div>
    <div class="ni" onclick="sv('cl',this)"><i class="ti ti-list-check"></i>Checklist<span class="nb">61</span></div>
    <div class="ni" onclick="sv('bidr',this)"><i class="ti ti-file-plus"></i>BIDR Oluştur</div>
    <div class="nsec">Kriterler</div>
    <div class="ni" onclick="sv('secA',this)"><i class="ti ti-crown"></i>A — Liderlik<span class="nb">34</span></div>
    <div class="ni" onclick="sv('secB',this)"><i class="ti ti-school"></i>B — Eğitim<span class="nb">16</span></div>
    <div class="ni" onclick="sv('secC',this)"><i class="ti ti-microscope"></i>C — AR-GE<span class="nb">7</span></div>
    <div class="ni" onclick="sv('secD',this)"><i class="ti ti-heart-handshake"></i>D — Toplumsal<span class="nb">4</span></div>
    <div class="nsec">Araçlar</div>
    <div class="ni" onclick="sv('ai',this)"><i class="ti ti-robot"></i>YZ Asistanı</div>
  </div>
  <div class="sb-foot"><i class="ti ti-user-circle" style="font-size:18px"></i>Dr. Öğr. Üyesi E. İlhan</div>
</div>

<!-- ───── MAIN ───── -->
<div class="main">
  <div class="topbar">
    <div>
      <div class="pt" id="pt">Genel Bakış</div>
      <div class="ps" id="ps">2025–2026 · YÖKAK Kurumsal Akreditasyon · KK.R.1</div>
    </div>
    <div class="tact">
      <button class="btns" onclick="sv('birimler',document.querySelectorAll('.ni')[1])"><i class="ti ti-building"></i>Birimler</button>
      <button class="btns" onclick="sv('cl',document.querySelectorAll('.ni')[2])"><i class="ti ti-list-check"></i>Checklist</button>
      <button class="btnp" onclick="sv('bidr',document.querySelectorAll('.ni')[3])"><i class="ti ti-plus"></i>Yeni BIDR</button>
    </div>
  </div>

  <div class="content">

  <!-- ══ DASHBOARD ══ -->
  <div class="view active" id="view-dash">
    <div class="cards">
      <div class="card">
        <div class="card-icon" style="background:#e6f0fa"><i class="ti ti-building" style="color:#0c2340"></i></div>
        <div class="card-lbl">Toplam Birim</div>
        <div class="card-val">22</div>
        <div class="card-sub">11 Akademik · 11 İdari</div>
        <div class="card-bar"><div class="card-bar-fill" style="width:100%;background:var(--blue)"></div></div>
      </div>
      <div class="card">
        <div class="card-icon" style="background:var(--success-bg)"><i class="ti ti-circle-check" style="color:var(--green)"></i></div>
        <div class="card-lbl">Tamamlandı</div>
        <div class="card-val" id="cnt-done">0</div>
        <div class="card-sub" id="pct-done">%0 / 61 madde</div>
        <div class="card-bar"><div class="card-bar-fill" id="done-bar" style="background:var(--green-light)"></div></div>
      </div>
      <div class="card">
        <div class="card-icon" style="background:var(--info-bg)"><i class="ti ti-refresh" style="color:var(--blue)"></i></div>
        <div class="card-lbl">Devam Ediyor</div>
        <div class="card-val" id="cnt-dev">0</div>
        <div class="card-sub">Aktif görevler</div>
        <div class="card-bar"><div class="card-bar-fill" id="dev-bar" style="background:var(--blue)"></div></div>
      </div>
      <div class="card">
        <div class="card-icon" style="background:var(--warn-bg)"><i class="ti ti-file-check" style="color:var(--orange)"></i></div>
        <div class="card-lbl">BIDR Teslim</div>
        <div class="card-val" id="cnt-bidr">2</div>
        <div class="card-sub">22 birimden teslim</div>
        <div class="card-bar"><div class="card-bar-fill" style="width:9%;background:var(--orange-light)"></div></div>
      </div>
    </div>

    <div class="sec-grid">
      <div class="sec-card">
        <div class="sc-head">
          <span class="sc-badge" style="background:#E6F0FA;color:#0c2340">A</span>
          <span class="sc-title">Liderlik, Yönetişim ve Kalite</span>
          <span class="sc-pct" id="pct-A" style="color:#0c2340">%0</span>
        </div>
        <div class="sc-bar"><div class="sc-bar-fill" id="bar-A" style="background:var(--blue);width:0%"></div></div>
        <div id="subs-A"></div>
      </div>
      <div class="sec-card">
        <div class="sc-head">
          <span class="sc-badge" style="background:#EAF3DE;color:#27500A">B</span>
          <span class="sc-title">Eğitim ve Öğretim</span>
          <span class="sc-pct" id="pct-B" style="color:#27500A">%0</span>
        </div>
        <div class="sc-bar"><div class="sc-bar-fill" id="bar-B" style="background:var(--green-light);width:0%"></div></div>
        <div id="subs-B"></div>
      </div>
      <div class="sec-card">
        <div class="sc-head">
          <span class="sc-badge" style="background:#FAEEDA;color:#633806">C</span>
          <span class="sc-title">Araştırma ve Geliştirme</span>
          <span class="sc-pct" id="pct-C" style="color:#633806">%0</span>
        </div>
        <div class="sc-bar"><div class="sc-bar-fill" id="bar-C" style="background:var(--orange-light);width:0%"></div></div>
        <div id="subs-C"></div>
      </div>
      <div class="sec-card">
        <div class="sc-head">
          <span class="sc-badge" style="background:#FBEAF0;color:#72243E">D</span>
          <span class="sc-title">Toplumsal Katkı</span>
          <span class="sc-pct" id="pct-D" style="color:#72243E">%0</span>
        </div>
        <div class="sc-bar"><div class="sc-bar-fill" id="bar-D" style="background:var(--red-light);width:0%"></div></div>
        <div id="subs-D"></div>
      </div>
    </div>

    <div class="puko-grid">
      <div class="pk"><div class="pk-circle" style="background:#E6F0FA;color:#0c2340">P</div><div class="pk-label">Planla</div><div class="pk-sub">Hedefler & Takvim</div></div>
      <div class="pk"><div class="pk-circle" style="background:#EAF3DE;color:#27500A">U</div><div class="pk-label">Uygula</div><div class="pk-sub">Faaliyetler & Kanıtlar</div></div>
      <div class="pk"><div class="pk-circle" style="background:#FAEEDA;color:#633806">K</div><div class="pk-label">Kontrol Et</div><div class="pk-sub">İzleme & Değerlendirme</div></div>
      <div class="pk"><div class="pk-circle" style="background:#FBEAF0;color:#72243E">Ö</div><div class="pk-label">Önlem Al</div><div class="pk-sub">İyileştirme & Güncelleme</div></div>
    </div>
  </div>

  <!-- ══ BİRİMLER ══ -->
  <div class="view" id="view-birimler">
    <div class="tab-row">
      <div class="tab active" onclick="switchTab('akademik',this)">📚 Akademik Birimler (11)</div>
      <div class="tab" onclick="switchTab('idari',this)">🏛️ İdari Birimler (11)</div>
    </div>
    <div id="tab-akademik">
      <div class="panel">
        <div class="ph">
          <div class="ph-title"><i class="ti ti-books"></i>Akademik Programlar</div>
          <select class="fs" style="width:auto;font-size:11px" onchange="renderAkademik(this.value)">
            <option value="">Tümü</option><option value="Türkçe">Türkçe</option><option value="İngilizce">İngilizce</option>
          </select>
        </div>
        <div style="overflow-x:auto">
        <table class="dt">
          <thead><tr><th>Program Adı</th><th>Dil</th><th>BIDR</th><th>İlerleme</th><th>İşlem</th></tr></thead>
          <tbody id="tbody-akademik"></tbody>
        </table>
        </div>
      </div>
    </div>
    <div id="tab-idari" style="display:none">
      <div class="panel">
        <div class="ph"><div class="ph-title"><i class="ti ti-building-community"></i>İdari Birimler — Direktörlükler</div></div>
        <div style="overflow-x:auto">
        <table class="dt">
          <thead><tr><th>Birim Adı</th><th>BIDR</th><th>İlerleme</th><th>İşlem</th></tr></thead>
          <tbody id="tbody-idari"></tbody>
        </table>
        </div>
      </div>
    </div>
  </div>

  <!-- ══ CHECKLİST ══ -->
  <div class="view" id="view-cl">
    <div class="cl-filters">
      <span class="cf active" onclick="filterCL('tumu',this)">Tümü (61)</span>
      <span class="cf" onclick="filterCL('A',this)">A — Liderlik (34)</span>
      <span class="cf" onclick="filterCL('B',this)">B — Eğitim (16)</span>
      <span class="cf" onclick="filterCL('C',this)">C — AR-GE (7)</span>
      <span class="cf" onclick="filterCL('D',this)">D — Toplumsal (4)</span>
      <span class="cf" onclick="filterCL('Tamamlandı',this)" style="margin-left:auto">✓ Tamamlandı</span>
      <span class="cf" onclick="filterCL('Devam Ediyor',this)">● Devam</span>
      <span class="cf" onclick="filterCL('Başlanmadı',this)">○ Başlanmadı</span>
    </div>
    <div id="cl-body"></div>
  </div>

  <!-- ══ BIDR ══ -->
  <div class="view" id="view-bidr">
    <div class="panel" style="margin-bottom:1rem">
      <div class="ph"><div class="ph-title"><i class="ti ti-file-description"></i>BIDR — Temel Bilgiler</div></div>
      <div style="padding:1rem">
        <div class="form-row">
          <div><div class="fl">Birim / Program</div><select class="fs" id="bidr-birim"></select></div>
          <div><div class="fl">Akademik Yıl</div><select class="fs"><option>2025–2026</option><option>2024–2025</option></select></div>
          <div><div class="fl">Sorumlu Kişi</div><input class="fi" value="Dr. Öğr. Üyesi Eda İlhan"></div>
          <div><div class="fl">Hazırlama Tarihi</div><input class="fi" type="date" value="2026-05-18"></div>
          <div class="full"><div class="fl">Birim Genel Değerlendirmesi</div><textarea class="fta" placeholder="Birimin bu dönemdeki genel performansını ve öne çıkan gelişmeleri özetleyiniz..."></textarea></div>
        </div>
      </div>
    </div>
    <div id="bidr-sections"></div>
    <div style="display:flex;gap:8px;padding-top:.875rem;border-top:1px solid var(--border)">
      <button class="btnp"><i class="ti ti-device-floppy"></i>Taslak Kaydet</button>
      <button class="btnp" style="background:#27500A"><i class="ti ti-send"></i>BIDR'ı Tamamla ve Gönder</button>
      <button class="btns" onclick="sv('ai',document.querySelectorAll('.ni')[9])"><i class="ti ti-robot"></i>YZ ile Geliştir</button>
    </div>
  </div>

  <!-- ══ KRİTER GÖRÜNÜMLERI ══ -->
  <div class="view" id="view-secA"></div>
  <div class="view" id="view-secB"></div>
  <div class="view" id="view-secC"></div>
  <div class="view" id="view-secD"></div>

  <!-- ══ YZ ASİSTANI ══ -->
  <div class="view" id="view-ai">
    <div style="background:var(--info-bg);border:1px solid rgba(55,138,221,.2);border-radius:var(--radius);padding:.75rem 1rem;margin-bottom:1rem;font-size:12px;color:var(--info-text);display:flex;align-items:center;gap:8px">
      <i class="ti ti-info-circle" style="font-size:18px;flex-shrink:0"></i>
      <span>22 birim için BIDR geliştirme, kanıt analizi ve kriter değerlendirmesi yapabilirsiniz.</span>
    </div>
    <div class="ai-grid">
      <div class="ai-card">
        <div class="ai-head">
          <div class="ai-logo" style="background:#E6F0FA;color:#0c2340">C</div>
          <div><div class="ai-name">Claude — Anthropic</div><div class="ai-sub">YÖKAK Uzmanı Modu</div></div>
          <span class="badge b-g" style="margin-left:auto">● Bağlı</span>
        </div>
        <div class="ai-msgs" id="ai-msgs">
          <div class="msg-b">Merhaba! Mudanya Üniversitesi'nin 11 akademik + 11 idari birimi için BIDR hazırlamanıza, kanıt eksiklerini tespit etmenize ve kriter analizleri yapmanıza yardımcı olurum. Ne ile başlayalım?</div>
        </div>
        <div class="ai-qbtns">
          <span class="qb" onclick="addAI('Kütüphane Direktörlüğü için A.1 kanıt listesi')">Kütüphane A.1</span>
          <span class="qb" onclick="addAI('Kariyer Direktörlüğü D kriteri faaliyetleri')">Kariyer D kriteri</span>
          <span class="qb" onclick="addAI('İnsan Kaynakları biriminin B.4 katkısı nedir?')">İK — B.4</span>
          <span class="qb" onclick="addAI('22 birim için BIDR önceliklendirme öner')">Önceliklendirme</span>
        </div>
        <div class="ai-inp-row">
          <input class="ai-inp" id="ai-inp" type="text" placeholder="Birim veya kriter hakkında sorunuzu yazın...">
          <button class="ai-send" onclick="sendAI()">Gönder</button>
        </div>
      </div>
      <div class="ai-card">
        <div class="ai-head">
          <div class="ai-logo" style="background:#EAF3DE;color:#27500A">G</div>
          <div><div class="ai-name">ChatGPT — OpenAI</div><div class="ai-sub">GPT-4o</div></div>
          <span class="badge b-gray" style="margin-left:auto">Bağlantı Yok</span>
        </div>
        <div class="ai-msgs" style="align-items:center;justify-content:center">
          <div style="text-align:center;color:var(--text3)"><i class="ti ti-plug-off" style="font-size:28px;display:block;margin-bottom:.5rem"></i>API anahtarı gerekli.<br><small>Ayarlar menüsünden yapılandırın.</small></div>
        </div>
        <div class="ai-qbtns"><span class="qb">API Bağla</span></div>
        <div class="ai-inp-row">
          <input class="ai-inp" disabled placeholder="Bağlantı bekleniyor..." style="background:var(--surface2)">
          <button class="ai-send" disabled style="opacity:.4;cursor:not-allowed">Gönder</button>
        </div>
      </div>
    </div>
  </div>

  </div><!-- /content -->
</div><!-- /main -->
</div><!-- /app -->

<script>
// ════════════════ DATA ════════════════
var AKADEMIK=[
  {id:1,ad:'Ekonomi ve Finans',dil:'Türkçe',bidr:'Başlanmadı'},
  {id:2,ad:'Ekonomi ve Finans',dil:'İngilizce',bidr:'Başlanmadı'},
  {id:3,ad:'Gastronomi ve Mutfak Sanatları',dil:'Türkçe',bidr:'Başlanmadı'},
  {id:4,ad:'Görsel İletişim Tasarımı',dil:'Türkçe',bidr:'Başlanmadı'},
  {id:5,ad:'İngiliz Dili ve Edebiyatı',dil:'İngilizce',bidr:'Başlanmadı'},
  {id:6,ad:'İşletme',dil:'Türkçe',bidr:'Devam Ediyor'},
  {id:7,ad:'İşletme',dil:'İngilizce',bidr:'Devam Ediyor'},
  {id:8,ad:'Lojistik Yönetimi',dil:'Türkçe',bidr:'Başlanmadı'},
  {id:9,ad:'Psikoloji',dil:'Türkçe',bidr:'Başlanmadı'},
  {id:10,ad:'Psikoloji',dil:'İngilizce',bidr:'Başlanmadı'},
  {id:11,ad:'Yönetim Bilişim Sistemleri',dil:'Türkçe',bidr:'Başlanmadı'},
];
var IDARI=[
  {ad:'Öğrenci İşleri Direktörlüğü',bidr:'Başlanmadı'},
  {ad:'Bilgi Teknolojileri Direktörlüğü',bidr:'Başlanmadı'},
  {ad:'İdari ve Destek Hizmetleri Direktörlüğü',bidr:'Başlanmadı'},
  {ad:'Sağlık, Kültür ve Sportif Faaliyetler Direktörlüğü',bidr:'Başlanmadı'},
  {ad:'Mali İşler Direktörlüğü',bidr:'Başlanmadı'},
  {ad:'Kütüphane Direktörlüğü',bidr:'Başlanmadı'},
  {ad:'İnsan Kaynakları Direktörlüğü',bidr:'Başlanmadı'},
  {ad:'Yapı ve Teknik İşler Direktörlüğü',bidr:'Başlanmadı'},
  {ad:'Kurumsal İletişim Direktörlüğü',bidr:'Başlanmadı'},
  {ad:'Kariyer Direktörlüğü',bidr:'Başlanmadı'},
  {ad:'Rektörlük',bidr:'Başlanmadı'},
];
var DATA={
  A:{title:'LİDERLİK, YÖNETİŞİM VE KALİTE',color:'#0c2340',bg:'#E6F0FA',bar:'#378ADD',
    subs:{'A.1':{title:'Liderlik ve Kalite',items:[
      {no:1,m:'Liderlik yaklaşımlarının geliştirilmesi',o:'A.1.2'},
      {no:2,m:'Sürdürülebilirlik raporunun hazırlanması',o:'A.1.3'},
      {no:3,m:'Kurumsal dönüşüm kapasitesinin değerlendirilmesi',o:'A.1.3'},
      {no:4,m:'Fakülte / MYO / İdari Birim BİDR hazırlanması',o:'A.1.4'},
      {no:5,m:'BİDR iç tetkiki',o:'A.1.4'},
      {no:6,m:'Kalite takviminin hazırlanması',o:'A.1.4'},
      {no:7,m:"YÖKAK kanıtlarının Teams/OneDrive'a yüklenmesi",o:'A.1.4'},
      {no:8,m:'Fakülte düzeyinde kalite değerlendirme toplantısı',o:'A.1.4'},
      {no:9,m:'PUKÖ değerlendirmesi ve eksiklerin belirlenmesi',o:'A.1.4'},
      {no:10,m:'Kanıtların toplanması ve arşivlenmesi',o:'A.1.4'},
      {no:11,m:'Çalışmaların üst yönetime raporlanması',o:'A.1.4'},
      {no:12,m:'Kalite Güvencesi Sistemi ve Kalite Politikası',o:'A.1.4'},
      {no:13,m:'Web sayfalarının güncellenmesi',o:'A.1.5'},
      {no:14,m:"Akademik danışmanlık saatlerinin web'de yayımlanması",o:'A.1.5'}
    ]},
    'A.2':{title:'Misyon ve Stratejik Amaçlar',items:[
      {no:15,m:'Stratejik planın web sitesinde yayımlanması',o:'A.2.1'},
      {no:16,m:'Stratejik amaç-hedefler (BSC / Performans Göstergeleri)',o:'A.2.2'},
      {no:17,m:'Faaliyet raporlarının hazırlanması (Güz ve Bahar)',o:'A.2.3'},
      {no:18,m:'Performans Yönetimi',o:'A.2.3'}
    ]},
    'A.3':{title:'Yönetim Sistemleri',items:[
      {no:19,m:'Bilgi Yönetim Sistemi (EBYS) süreçleri',o:'A.3.1'},
      {no:20,m:'Personel akademik eğitim ihtiyaçlarının belirlenmesi',o:'A.3.2'},
      {no:21,m:'Akademik Teşvik Yönergesi ve KPI belirlenmesi',o:'A.3.2'},
      {no:22,m:'Finansal kaynakların yönetimi ve bütçe planlaması',o:'A.3.3'},
      {no:23,m:'İş akış şemaları ve süreç dokümantasyonu',o:'A.3.4'}
    ]},
    'A.4':{title:'Paydaş Katılımı',items:[
      {no:24,m:'İdari ve akademik anket sonuçlarının analizi (2025)',o:'A.4.1'},
      {no:25,m:'Akademik Danışma Kurulu iyileştirme planı',o:'A.4.1'},
      {no:26,m:'Personel memnuniyet anketleri',o:'A.4.1'},
      {no:27,m:'Öğrenci temsilcilerinin komisyonlara katılması',o:'A.4.1'},
      {no:28,m:'Öğrenci e-posta kullanımının yaygınlaştırılması',o:'A.4.2'},
      {no:29,m:'Öğrenci memnuniyet anketleri (2025)',o:'A.4.2'},
      {no:30,m:"Kariyer ve Mezunlar Ofisi Yönergesi güncellenmesi",o:'A.4.3'},
      {no:31,m:'Mezun takip sistemi oluşturulması',o:'A.4.3'},
      {no:32,m:"Kariyer danışmanlık sisteminin web'de tutulması",o:'A.4.3'}
    ]},
    'A.5':{title:'Uluslararasılaşma',items:[
      {no:33,m:'Uluslararasılaşma süreçleri ve kaynak planlaması',o:'A.5.1–A.5.2'},
      {no:34,m:'Uluslararasılaşma verilerinin raporlanması',o:'A.5.3'}
    ]}}
  },
  B:{title:'EĞİTİM VE ÖĞRETİM',color:'#27500A',bg:'#EAF3DE',bar:'#639922',
    subs:{'B.1':{title:'Program Tasarımı, Değerlendirmesi ve Güncellenmesi',items:[
      {no:35,m:'Programların TYYÇ uyumu ve ders dağılımı',o:'B.1.1–B.1.2'},
      {no:36,m:'Program tasarımı ve onayı',o:'B.1.1–B.1.2'},
      {no:37,m:'Ders ve program kazanımı matrislerinin kontrolü',o:'B.1.3'},
      {no:38,m:'Öğrenci iş yükü analizi ve AKTS uyumu',o:'B.1.4'},
      {no:39,m:'Programların periyodik izlenmesi ve güncellenmesi',o:'B.1.5'},
      {no:40,m:'Eğitim-öğretim yönetim altyapısı',o:'B.1.6'}
    ]},
    'B.2':{title:'Programların Yürütülmesi',items:[
      {no:41,m:'Öğretim yöntem ve tekniklerinin çeşitlendirilmesi',o:'B.2.1'},
      {no:42,m:'Öğretim yetkinliği ve gelişimi',o:'B.2.1'},
      {no:43,m:'Uzaktan eğitim TYYÇ ile uyumu',o:'B.2.1'},
      {no:44,m:'Ölçme-değerlendirme ve sınav politikası',o:'B.2.2'},
      {no:45,m:'Öğrenci kabulü ve önceki öğrenmenin tanınması',o:'B.2.3'},
      {no:46,m:'Diploma ve yeterlilik belgesi süreçleri',o:'B.2.4'}
    ]},
    'B.3':{title:'Öğrenme Kaynakları ve Akademik Destek',items:[
      {no:47,m:'Öğrenme ortamları, kütüphane ve altyapı',o:'B.3.1–B.3.3'},
      {no:48,m:'Dezavantajlı gruplara yönelik faaliyetler',o:'B.3.4'},
      {no:49,m:'Seminer, konferans ve etkinlik takvimi',o:'B.3.5'}
    ]},
    'B.4':{title:'Öğretim Kadrosu',items:[
      {no:50,m:'Akademik personel atama ve yükseltme kriterleri',o:'B.4.1'}
    ]}}
  },
  C:{title:'ARAŞTIRMA VE GELİŞTİRME',color:'#633806',bg:'#FAEEDA',bar:'#BA7517',
    subs:{'C.1':{title:'Araştırma Süreçlerinin Yönetimi ve Kaynakları',items:[
      {no:51,m:'BAP süreçleri bilgilendirme toplantısı',o:'C.1.1'},
      {no:52,m:'Araştırma süreçleri ve organizasyonel yapı',o:'C.1.1'},
      {no:53,m:'Doktora programları ve imkânların değerlendirilmesi',o:'C.1.3'}
    ]},
    'C.2':{title:'Araştırma Yetkinliği, İş Birlikleri ve Destekler',items:[
      {no:54,m:'TTO bilgilendirme toplantısı',o:'C.2.1–C.2.2'},
      {no:55,m:'Araştırmacı yetkinlikleri geliştirme etkinlikleri',o:'C.2.1'},
      {no:56,m:'Ulusal ve uluslararası araştırma iş birlikleri',o:'C.2.2'}
    ]},
    'C.3':{title:'Araştırma Performansı',items:[
      {no:57,m:'Araştırma performansı izleme ve çıktılar raporu',o:'C.3.1–C.3.2'}
    ]}}
  },
  D:{title:'TOPLUMSAL KATKI',color:'#72243E',bg:'#FBEAF0',bar:'#C4365A',
    subs:{'D.1':{title:'Toplumsal Katkı Süreçlerinin Yönetimi ve Kaynakları',items:[
      {no:58,m:'Toplumsal katkı raporlama ve politika belgesi',o:'D.1.1–D.2.1'},
      {no:59,m:'Toplumsal katkı süreçleri ve organizasyonel yapı',o:'D.1.1'},
      {no:60,m:'Toplumsal katkı kaynakları ve altyapısı',o:'D.1.2'}
    ]},
    'D.2':{title:'Toplumsal Katkı Performansı',items:[
      {no:61,m:'Toplumsal katkı performansının izlenmesi',o:'D.2.1'}
    ]}}
  }
};

// ════════ STATE ════════
var statuses={};
for(var s in DATA) for(var k in DATA[s].subs) DATA[s].subs[k].items.forEach(function(it){statuses[it.no]='Başlanmadı';});
var statusOpts=['Başlanmadı','Planlandı','Devam Ediyor','Tamamlandı'];
function stColor(s){return{Tamamlandı:'#27500A','Devam Ediyor':'#0C447C',Planlandı:'#633806',Başlanmadı:'#888'}[s]||'#888';}
function bidrBadge(s){return{Tamamlandı:'b-g','Devam Ediyor':'b-b',Planlandı:'b-y',Başlanmadı:'b-gray'}[s]||'b-gray';}

// ════════ DASHBOARD ════════
function updateDashboard(){
  var done=0,dev=0;
  Object.values(statuses).forEach(function(s){if(s==='Tamamlandı')done++;if(s==='Devam Ediyor')dev++;});
  document.getElementById('cnt-done').textContent=done;
  document.getElementById('cnt-dev').textContent=dev;
  document.getElementById('pct-done').textContent='%'+Math.round(done/61*100)+' / 61 madde';
  document.getElementById('done-bar').style.width=Math.round(done/61*100)+'%';
  document.getElementById('dev-bar').style.width=Math.round(dev/61*100)+'%';
  ['A','B','C','D'].forEach(function(sec){
    var all=[]; for(var k in DATA[sec].subs) all=all.concat(DATA[sec].subs[k].items);
    var d=all.filter(function(it){return statuses[it.no]==='Tamamlandı';}).length;
    var pct=Math.round(d/all.length*100);
    document.getElementById('pct-'+sec).textContent='%'+pct;
    document.getElementById('bar-'+sec).style.width=pct+'%';
    var html='';
    for(var k in DATA[sec].subs){
      var sub=DATA[sec].subs[k];
      var sd=sub.items.filter(function(it){return statuses[it.no]==='Tamamlandı';}).length;
      html+='<div class="sc-sub"><span class="sc-sub-name">'+k+' '+sub.title.substring(0,24)+'…</span><span class="sc-sub-val">'+sd+'/'+sub.items.length+'</span></div>';
    }
    document.getElementById('subs-'+sec).innerHTML=html;
  });
}

// ════════ BİRİMLER ════════
function renderAkademik(filter){
  var html='';
  AKADEMIK.forEach(function(b){
    if(filter&&b.dil!==filter)return;
    var pcts=[0,5,8,12,3,22,18,4,7,6,10];
    var pct=pcts[b.id-1]||0;
    html+='<tr>';
    html+='<td style="font-weight:600">'+b.ad+'</td>';
    html+='<td><span class="badge '+(b.dil==='İngilizce'?'b-b':'b-g')+'">'+b.dil+'</span></td>';
    html+='<td><span class="badge '+bidrBadge(b.bidr)+'">'+b.bidr+'</span></td>';
    html+='<td style="min-width:120px"><div style="display:flex;align-items:center;gap:6px"><div class="prog" style="flex:1"><div class="prog-fill" style="width:'+pct+'%;background:#378ADD"></div></div><span style="font-size:10px;color:var(--text3);white-space:nowrap">%'+pct+'</span></div></td>';
    html+='<td><button class="btns" style="padding:3px 10px;font-size:11px" onclick="openBIDR(\''+b.ad+' ('+b.dil+')\')"><i class="ti ti-edit"></i> BIDR Aç</button></td>';
    html+='</tr>';
  });
  document.getElementById('tbody-akademik').innerHTML=html;
}
function renderIdari(){
  var html='';
  IDARI.forEach(function(b,i){
    var pcts=[3,0,5,0,8,12,4,0,6,9,15];
    var pct=pcts[i]||0;
    html+='<tr>';
    html+='<td style="font-weight:600">'+b.ad+'</td>';
    html+='<td><span class="badge '+bidrBadge(b.bidr)+'">'+b.bidr+'</span></td>';
    html+='<td style="min-width:120px"><div style="display:flex;align-items:center;gap:6px"><div class="prog" style="flex:1"><div class="prog-fill" style="width:'+pct+'%;background:#7B4DA8"></div></div><span style="font-size:10px;color:var(--text3)">%'+pct+'</span></div></td>';
    html+='<td><button class="btns" style="padding:3px 10px;font-size:11px" onclick="openBIDR(\''+b.ad+'\')"><i class="ti ti-edit"></i> BIDR Aç</button></td>';
    html+='</tr>';
  });
  document.getElementById('tbody-idari').innerHTML=html;
}
function switchTab(t,el){
  document.querySelectorAll('.tab').forEach(function(e){e.classList.remove('active');});
  el.classList.add('active');
  document.getElementById('tab-akademik').style.display=t==='akademik'?'block':'none';
  document.getElementById('tab-idari').style.display=t==='idari'?'block':'none';
}
function openBIDR(name){
  sv('bidr',document.querySelectorAll('.ni')[3]);
  var sel=document.getElementById('bidr-birim');
  for(var i=0;i<sel.options.length;i++){if(sel.options[i].value===name){sel.value=name;break;}}
}

// ════════ CHECKLİST ════════
function setSt(no,val){
  statuses[no]=val;
  var el=document.querySelector('#row-'+no+' .st-sel');
  if(el){el.style.borderColor=stColor(val);el.style.color=stColor(val);}
  updateDashboard();
}
var clFilter='tumu';
function filterCL(f,el){
  clFilter=f;
  document.querySelectorAll('.cf').forEach(function(e){e.classList.remove('active');});
  el.classList.add('active');
  buildCL(f);
}
function buildCL(filter){
  var html='';
  for(var sec in DATA){
    var d=DATA[sec];
    var all=[]; for(var k in d.subs) all=all.concat(d.subs[k].items);
    var show=filter==='tumu'||filter===sec||(all.some(function(it){return statuses[it.no]===filter;}));
    if(!show) continue;
    html+='<div class="cl-sec-group"><div class="cl-sec-head" style="background:'+d.bg+'"><span style="background:'+d.color+';color:#fff;padding:3px 10px;border-radius:5px;font-size:11px;font-weight:700">'+sec+'</span><span style="font-size:12px;font-weight:700;color:var(--text1)">'+d.title+'</span></div>';
    for(var k in d.subs){
      var sub=d.subs[k];
      var items=sub.items.filter(function(it){return filter==='tumu'||filter===sec||statuses[it.no]===filter;});
      if(!items.length) continue;
      html+='<div class="cl-sub-head"><span style="background:'+d.bg+';color:'+d.color+';padding:2px 7px;border-radius:4px;font-size:10px;font-weight:700">'+k+'</span>'+sub.title+'</div>';
      items.forEach(function(it){
        var st=statuses[it.no];
        html+='<div class="cl-item" id="row-'+it.no+'"><div class="cl-no">'+it.no+'</div><div class="cl-text">'+it.m+'<div class="cl-olcut"><i class="ti ti-tag" style="font-size:9px"></i> '+it.o+'</div></div><select class="st-sel" onchange="setSt('+it.no+',this.value)" style="border-color:'+stColor(st)+';color:'+stColor(st)+'">';
        statusOpts.forEach(function(o){html+='<option'+(o===st?' selected':'')+'>'+o+'</option>';});
        html+='</select></div>';
      });
    }
    html+='</div>';
  }
  document.getElementById('cl-body').innerHTML=html;
}

// ════════ BIDR ════════
function buildBIDRSelect(){
  var sel=document.getElementById('bidr-birim');
  sel.innerHTML='<option value="">— Birim Seçiniz —</option>';
  var og1=document.createElement('optgroup'); og1.label='📚 Akademik Birimler';
  AKADEMIK.forEach(function(b){var o=document.createElement('option');o.value=b.ad+' ('+b.dil+')';o.textContent=b.ad+' ('+b.dil+')';og1.appendChild(o);});
  var og2=document.createElement('optgroup'); og2.label='🏛️ İdari Birimler';
  IDARI.forEach(function(b){var o=document.createElement('option');o.value=b.ad;o.textContent=b.ad;og2.appendChild(o);});
  sel.appendChild(og1); sel.appendChild(og2);
}
function buildBIDRSections(){
  var html='';
  for(var sec in DATA){
    var d=DATA[sec]; var cnt=0;
    for(var k in d.subs) cnt+=d.subs[k].items.length;
    html+='<div class="bidr-sec"><div class="bs-head" onclick="toggleBS(this)"><div class="bs-badge" style="background:'+d.bg+';color:'+d.color+'">'+sec+'</div><div class="bs-title">'+sec+'. '+d.title+'</div><div class="bs-count">'+cnt+' madde</div><i class="ti ti-chevron-down" style="font-size:14px;color:var(--text3);margin-left:8px"></i></div><div class="bs-body'+(sec==='A'?' open':'')+'">';
    for(var k in d.subs){
      var sub=d.subs[k];
      html+='<div style="margin-bottom:.75rem"><div class="fl" style="color:'+d.color+'">'+k+' — '+sub.title+'</div><textarea class="fta" placeholder="'+k+' kapsamındaki faaliyetler, sonuçlar ve kanıtlar..."></textarea></div>';
    }
    html+='<button class="ev-add"><i class="ti ti-paperclip"></i>Kanıt Ekle</button>';
    html+='</div></div>';
  }
  document.getElementById('bidr-sections').innerHTML=html;
}
function toggleBS(h){h.nextElementSibling.classList.toggle('open');}

// ════════ KRİTER GÖRÜNÜMLERİ ════════
function buildSecView(sec){
  var d=DATA[sec]; var el=document.getElementById('view-sec'+sec);
  var allItems=[]; for(var k in d.subs) allItems=allItems.concat(d.subs[k].items);
  var done=allItems.filter(function(it){return statuses[it.no]==='Tamamlandı';}).length;
  var html='<div style="display:flex;align-items:center;gap:12px;padding:1rem;background:'+d.bg+';border-radius:var(--radius);margin-bottom:1rem;border:1px solid var(--border)">';
  html+='<div style="width:44px;height:44px;border-radius:50%;background:'+d.color+';color:#fff;display:flex;align-items:center;justify-content:center;font-size:18px;font-weight:700;flex-shrink:0">'+sec+'</div>';
  html+='<div><div style="font-size:15px;font-weight:700;color:var(--text1)">'+sec+'. '+d.title+'</div><div style="font-size:11px;color:var(--text3);margin-top:3px">'+allItems.length+' madde · '+done+' tamamlandı</div></div></div>';
  for(var k in d.subs){
    var sub=d.subs[k];
    html+='<div class="panel" style="margin-bottom:.875rem"><div class="ph"><div class="ph-title"><span style="background:'+d.bg+';color:'+d.color+';padding:3px 10px;border-radius:5px;font-size:11px;font-weight:700">'+k+'</span>'+sub.title+'</div></div>';
    sub.items.forEach(function(it){
      var st=statuses[it.no];
      html+='<div class="cl-item" id="sv-'+it.no+'"><div class="cl-no">'+it.no+'</div><div class="cl-text">'+it.m+'<div class="cl-olcut"><i class="ti ti-tag" style="font-size:9px"></i> '+it.o+'</div></div><select class="st-sel" onchange="setSt('+it.no+',this.value)" style="border-color:'+stColor(st)+';color:'+stColor(st)+'">';
      statusOpts.forEach(function(o){html+='<option'+(o===st?' selected':'')+'>'+o+'</option>';});
      html+='</select></div>';
    });
    html+='</div>';
  }
  el.innerHTML=html;
}

// ════════ NAVİGASYON ════════
var pageTitles={
  dash:['Genel Bakış','2025–2026 · YÖKAK Kurumsal Akreditasyon · KK.R.1'],
  birimler:['Tüm Birimler','11 Akademik · 11 İdari · Mudanya Üniversitesi'],
  cl:['Checklist — 61 Madde','A.1–D.2 Kriterleri · Durum Takibi'],
  bidr:['BIDR Oluştur','22 Birim İçin Birim İç Değerlendirme Raporu'],
  secA:['A — Liderlik, Yönetişim ve Kalite','34 Madde · A.1 Liderlik – A.5 Uluslararasılaşma'],
  secB:['B — Eğitim ve Öğretim','16 Madde · B.1 Program Tasarımı – B.4 Öğretim Kadrosu'],
  secC:['C — Araştırma ve Geliştirme','7 Madde · C.1 Yönetim – C.3 Performans'],
  secD:['D — Toplumsal Katkı','4 Madde · D.1 Yönetim – D.2 Performans'],
  ai:['YZ Asistanı','Claude & ChatGPT · BIDR Destek Modülü'],
};
function sv(id,navEl){
  document.querySelectorAll('.view').forEach(function(v){v.classList.remove('active');});
  document.querySelectorAll('.ni').forEach(function(n){n.classList.remove('active');});
  document.getElementById('view-'+id).classList.add('active');
  if(navEl) navEl.classList.add('active');
  var t=pageTitles[id]||[id,''];
  document.getElementById('pt').textContent=t[0];
  document.getElementById('ps').textContent=t[1];
  if(id==='cl') buildCL(clFilter);
  if(id==='birimler'){renderAkademik('');renderIdari();}
  if(id.startsWith('sec')) buildSecView(id.replace('sec',''));
  updateDashboard();
}

// ════════ YZ ASİSTANI ════════
var aiR={
  'Kütüphane Direktörlüğü için A.1 kanıt listesi':'Kütüphane Direktörlüğü A.1 kanıtları: (1) Kütüphane hizmet politika belgesi, (2) Yıllık faaliyet raporu, (3) Kullanıcı memnuniyet anketi sonuçları, (4) Dijital kaynak erişim istatistikleri, (5) Eğitim-seminer tutanakları. Bu belgeler A.1.4 maddesi için doğrudan kanıt teşkil eder.',
  'Kariyer Direktörlüğü D kriteri faaliyetleri':'D kriteri için Kariyer Direktörlüğü katkıları: Mezun takip sistemi verileri, iş dünyası etkinlikleri, staj protokolleri, kariyer fuarı raporu, işveren memnuniyet anketi. Bu birim özellikle A.4.3 maddelerinde de belirleyici rol oynamaktadır.',
  'İnsan Kaynakları biriminin B.4 katkısı nedir?':'İK Direktörlüğü B.4 (Öğretim Kadrosu) kapsamında: atama-yükseltme kriterlerini belgelemeli, akademik gelişim planlarını kayıt altına almalı, hizmet içi eğitim belgelerini arşivlemelidir. Madde 50 için doğrudan kanıt sağlayan birimdir.',
  '22 birim için BIDR önceliklendirme öner':'Öncelik sırası: (1) İşletme bölümleri — devam ediyor, (2) Öğrenci İşleri ve İK Direktörlüğü — A.4 kritik, (3) Kütüphane — B.3 kanıtları hazır, (4) Kariyer Direktörlüğü — A.4.3 ve D.1, (5) Tüm akademik bölümler B.1–B.2 için eş zamanlı.'
};
function addAI(text){
  var msgs=document.getElementById('ai-msgs');
  var u=document.createElement('div'); u.className='msg-u'; u.textContent=text; msgs.appendChild(u);
  setTimeout(function(){
    var b=document.createElement('div'); b.className='msg-b';
    b.textContent=aiR[text]||'Bu konu için daha detaylı analiz yapabilirim. Hangi kriteri veya birimi inceleyelim?';
    msgs.appendChild(b); msgs.scrollTop=msgs.scrollHeight;
  },600);
  msgs.scrollTop=msgs.scrollHeight;
}
function sendAI(){
  var inp=document.getElementById('ai-inp'); var t=inp.value.trim(); if(!t) return;
  addAI(t); inp.value='';
}
document.getElementById('ai-inp').addEventListener('keydown',function(e){if(e.key==='Enter')sendAI();});

// ════════ INIT ════════
buildBIDRSelect();
buildBIDRSections();
buildCL('tumu');
renderAkademik('');
renderIdari();
updateDashboard();
</script>
</body>
</html>
