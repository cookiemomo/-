<!DOCTYPE html>
<html lang="zh-TW">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>過敏性鼻炎的日常照護</title>
<link href="https://fonts.googleapis.com/css2?family=Noto+Sans+TC:wght@400;500;700;900&family=Nunito:wght@700;900&display=swap" rel="stylesheet">
<style>
  :root {
    --green-dark: #2d6a4f;
    --green-mid: #40916c;
    --green-soft: #74c69d;
    --green-pale: #d8f3dc;
    --green-lightest: #f0faf3;
    --teal: #52b788;
    --amber: #e9c46a;
    --amber-dark: #f4a261;
    --red-soft: #e07a5f;
    --blue-soft: #a8dadc;
    --blue-mid: #457b9d;
    --cream: #fefae0;
    --white: #ffffff;
    --text-dark: #1b4332;
    --text-mid: #3a7d44;
    --text-body: #374151;
    --text-light: #6b7280;
    --shadow: 0 4px 24px rgba(45,106,79,0.10);
    --shadow-card: 0 2px 12px rgba(45,106,79,0.08);
    --radius: 20px;
    --radius-sm: 12px;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  html, body {
    background: #c8d6cb;
    font-family: 'Noto Sans TC', sans-serif;
    color: var(--text-body);
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: flex-start;
  }

  .phone-frame {
    width: 390px;
    min-height: 100vh;
    background: #f4faf6;
    box-shadow: 0 8px 48px rgba(0,0,0,0.25);
    overflow: hidden;
  }

  @media (max-width: 430px) {
    html, body { background: #f4faf6; display: block; }
    .phone-frame { width: 100%; box-shadow: none; }
  }

  /* ── HERO ── */
  .hero {
    background: linear-gradient(135deg, var(--green-dark) 0%, var(--green-mid) 60%, var(--teal) 100%);
    color: white;
    padding: 48px 24px 60px;
    text-align: center;
    position: relative;
    overflow: hidden;
  }
  .hero::before {
    content: '';
    position: absolute;
    inset: 0;
    background: radial-gradient(ellipse at 80% 20%, rgba(255,255,255,0.08) 0%, transparent 60%),
                radial-gradient(ellipse at 10% 80%, rgba(116,198,157,0.2) 0%, transparent 50%);
  }
  .hero-badge {
    display: inline-block;
    background: rgba(255,255,255,0.2);
    border: 1px solid rgba(255,255,255,0.35);
    border-radius: 100px;
    padding: 6px 18px;
    font-size: 13px;
    font-weight: 500;
    letter-spacing: 0.05em;
    margin-bottom: 16px;
    backdrop-filter: blur(4px);
  }
  .hero h1 {
    font-size: clamp(26px, 6vw, 40px);
    font-weight: 900;
    line-height: 1.25;
    margin-bottom: 8px;
    position: relative;
  }
  .hero h1 span { color: var(--green-soft); }
  .hero-sub {
    font-size: 15px;
    opacity: 0.88;
    line-height: 1.7;
    max-width: 420px;
    margin: 0 auto 28px;
    position: relative;
  }
  .allergen-pills {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 8px;
    position: relative;
  }
  .pill {
    background: rgba(255,255,255,0.18);
    border: 1px solid rgba(255,255,255,0.3);
    border-radius: 100px;
    padding: 5px 14px;
    font-size: 13px;
    backdrop-filter: blur(4px);
    display: flex;
    align-items: center;
    gap: 5px;
  }

  /* ── GOALS BAR ── */
  .goals-bar {
    background: white;
    margin: -20px 16px 0;
    border-radius: var(--radius);
    padding: 20px 24px;
    box-shadow: var(--shadow);
    position: relative;
    z-index: 10;
    display: flex;
    gap: 16px;
    flex-wrap: wrap;
  }
  .goal-item {
    display: flex;
    align-items: center;
    gap: 10px;
    flex: 1;
    min-width: 160px;
  }
  .goal-icon {
    width: 40px; height: 40px;
    background: var(--green-pale);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 18px;
    flex-shrink: 0;
  }
  .goal-text { font-size: 14px; font-weight: 600; color: var(--text-dark); line-height: 1.4; }

  /* ── SECTION LAYOUT ── */
  .main { padding: 24px 16px 48px; max-width: 680px; margin: 0 auto; }
  .section-label {
    font-size: 12px;
    font-weight: 700;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--green-mid);
    margin: 32px 0 12px;
  }

  /* ── TIP CARDS ── */
  .tip-card {
    background: white;
    border-radius: var(--radius);
    box-shadow: var(--shadow-card);
    margin-bottom: 14px;
    overflow: hidden;
    transition: box-shadow 0.2s;
  }
  .tip-card:hover { box-shadow: 0 6px 28px rgba(45,106,79,0.14); }
  .tip-header {
    display: flex;
    align-items: center;
    padding: 18px 20px;
    cursor: pointer;
    gap: 14px;
    user-select: none;
    -webkit-tap-highlight-color: transparent;
  }
  .tip-num {
    width: 36px; height: 36px;
    background: var(--green-dark);
    color: white;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: 900;
    font-size: 16px;
    flex-shrink: 0;
  }
  .tip-title {
    flex: 1;
    font-size: 16px;
    font-weight: 700;
    color: var(--text-dark);
  }
  .tip-emoji { font-size: 22px; }
  .tip-chevron {
    font-size: 14px;
    color: var(--green-soft);
    transition: transform 0.3s;
  }
  .tip-card.open .tip-chevron { transform: rotate(180deg); }
  .tip-body {
    max-height: 0;
    overflow: hidden;
    transition: max-height 0.4s cubic-bezier(0.4, 0, 0.2, 1);
  }
  .tip-card.open .tip-body { max-height: 800px; }
  .tip-inner { padding: 0 20px 20px; border-top: 1px solid var(--green-pale); padding-top: 16px; }
  .tip-desc { font-size: 14px; color: var(--text-light); line-height: 1.7; margin-bottom: 14px; }
  .tag {
    display: inline-block;
    border-radius: 6px;
    padding: 3px 10px;
    font-size: 12px;
    font-weight: 700;
    margin-bottom: 8px;
  }
  .tag-suggest { background: var(--green-pale); color: var(--green-dark); }
  .tag-warn { background: #fff3e0; color: #b45309; }
  .tag-note { background: #e0f2fe; color: #0369a1; }
  .list-items { margin: 6px 0 12px 0; list-style: none; }
  .list-items li {
    display: flex;
    align-items: flex-start;
    gap: 8px;
    padding: 5px 0;
    font-size: 14px;
    line-height: 1.6;
    color: var(--text-body);
  }
  .list-items li::before {
    content: '•';
    color: var(--green-soft);
    font-weight: 900;
    flex-shrink: 0;
    margin-top: 1px;
  }
  .highlight-box {
    background: var(--green-lightest);
    border-left: 3px solid var(--green-soft);
    border-radius: 0 10px 10px 0;
    padding: 10px 14px;
    font-size: 13px;
    color: var(--text-dark);
    margin-top: 10px;
    line-height: 1.6;
  }
  .warn-box {
    background: #fff8f0;
    border-left: 3px solid var(--amber-dark);
    border-radius: 0 10px 10px 0;
    padding: 10px 14px;
    font-size: 13px;
    color: #92400e;
    margin-top: 10px;
    line-height: 1.6;
  }

  /* ── SELF-CHECK ── */
  .self-check-card {
    background: linear-gradient(135deg, #1b4332, var(--green-mid));
    border-radius: var(--radius);
    padding: 24px 20px;
    color: white;
    margin-bottom: 14px;
  }
  .self-check-title { font-size: 17px; font-weight: 800; margin-bottom: 4px; }
  .self-check-sub { font-size: 13px; opacity: 0.8; margin-bottom: 16px; }
  .check-q {
    display: flex;
    align-items: flex-start;
    gap: 10px;
    margin-bottom: 10px;
    font-size: 14px;
    line-height: 1.5;
    opacity: 0.9;
  }
  .check-q::before { content: '💭'; flex-shrink: 0; }
  .self-check-result {
    background: rgba(255,255,255,0.15);
    border-radius: 12px;
    padding: 14px;
    font-size: 13px;
    line-height: 1.6;
    margin-top: 14px;
    border: 1px solid rgba(255,255,255,0.2);
  }

  /* ── TASK CHECKLIST ── */
  .task-card {
    background: white;
    border-radius: var(--radius);
    padding: 24px 20px;
    box-shadow: var(--shadow-card);
    margin-bottom: 14px;
  }
  .task-header {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 18px;
  }
  .task-icon {
    width: 44px; height: 44px;
    background: var(--cream);
    border-radius: 12px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 22px;
  }
  .task-title { font-size: 17px; font-weight: 800; color: var(--text-dark); }
  .task-subtitle { font-size: 12px; color: var(--text-light); }
  .task-progress-bar {
    background: var(--green-pale);
    border-radius: 100px;
    height: 8px;
    margin-bottom: 18px;
    overflow: hidden;
  }
  .task-progress-fill {
    background: linear-gradient(90deg, var(--green-mid), var(--green-soft));
    height: 100%;
    border-radius: 100px;
    transition: width 0.5s cubic-bezier(0.4,0,0.2,1);
    width: 0%;
  }
  .task-item {
    display: flex;
    align-items: center;
    gap: 14px;
    padding: 14px 0;
    border-bottom: 1px solid var(--green-lightest);
    cursor: pointer;
    -webkit-tap-highlight-color: transparent;
    transition: opacity 0.2s;
  }
  .task-item:last-child { border-bottom: none; }
  .task-cb {
    width: 26px; height: 26px;
    border: 2.5px solid #d1d5db;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
    transition: all 0.25s;
    background: white;
  }
  .task-item.checked .task-cb {
    background: var(--green-mid);
    border-color: var(--green-mid);
  }
  .task-cb-tick { display: none; color: white; font-size: 14px; font-weight: 900; }
  .task-item.checked .task-cb-tick { display: block; }
  .task-text { font-size: 15px; color: var(--text-body); font-weight: 500; flex: 1; line-height: 1.4; }
  .task-item.checked .task-text { color: var(--green-mid); text-decoration: line-through; opacity: 0.7; }
  .task-done-msg {
    text-align: center;
    padding: 14px;
    background: var(--green-pale);
    border-radius: 12px;
    font-size: 14px;
    font-weight: 700;
    color: var(--green-dark);
    margin-top: 12px;
    display: none;
  }

  /* ── SCORE SLIDER ── */
  .score-card {
    background: white;
    border-radius: var(--radius);
    padding: 24px 20px;
    box-shadow: var(--shadow-card);
    margin-bottom: 14px;
  }
  .score-header {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 8px;
  }
  .score-star {
    width: 44px; height: 44px;
    background: #fef9c3;
    border-radius: 12px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 22px;
  }
  .score-title { font-size: 17px; font-weight: 800; color: var(--text-dark); }
  .score-desc { font-size: 13px; color: var(--text-light); margin-bottom: 20px; }
  .slider-wrap { padding: 0 4px; }
  input[type=range] {
    -webkit-appearance: none;
    width: 100%;
    height: 8px;
    background: linear-gradient(90deg, var(--green-mid) var(--val, 50%), var(--green-pale) var(--val, 50%));
    border-radius: 100px;
    outline: none;
    cursor: pointer;
  }
  input[type=range]::-webkit-slider-thumb {
    -webkit-appearance: none;
    width: 28px; height: 28px;
    background: white;
    border: 3px solid var(--green-mid);
    border-radius: 50%;
    box-shadow: 0 2px 8px rgba(64,145,108,0.3);
    transition: transform 0.15s;
  }
  input[type=range]:active::-webkit-slider-thumb { transform: scale(1.2); }
  .slider-labels {
    display: flex;
    justify-content: space-between;
    margin-top: 8px;
    font-size: 12px;
    color: var(--text-light);
  }
  .score-display {
    text-align: center;
    margin-top: 20px;
    padding: 16px;
    background: var(--green-lightest);
    border-radius: 14px;
  }
  .score-num {
    font-size: 48px;
    font-weight: 900;
    color: var(--green-dark);
    font-family: 'Nunito', sans-serif;
    line-height: 1;
  }
  .score-emoji { font-size: 30px; margin: 6px 0; }
  .score-label { font-size: 14px; font-weight: 600; color: var(--text-mid); }

  /* ── DOCTOR NOTE ── */
  .doctor-note {
    background: #fff8f0;
    border: 1.5px solid #fcd34d;
    border-radius: var(--radius);
    padding: 18px 20px;
    display: flex;
    gap: 12px;
    align-items: flex-start;
    margin-bottom: 14px;
  }
  .doctor-note-icon { font-size: 24px; flex-shrink: 0; }
  .doctor-note-text { font-size: 14px; color: #78350f; line-height: 1.7; }
  .doctor-note-text strong { font-weight: 700; color: #92400e; }

  /* ── FOOTER ── */
  footer {
    background: #3b2a1a;
    text-align: center;
    padding: 32px 28px;
    color: #e8d5b7;
  }
  footer .footer-title {
    font-size: 12px;
    font-weight: 700;
    letter-spacing: 0.04em;
    color: #f5e6cc;
    margin-bottom: 12px;
  }
  footer .footer-divider {
    width: 40px;
    height: 1px;
    background: rgba(245,230,204,0.3);
    margin: 0 auto 12px;
  }
  footer .footer-body {
    font-size: 12px;
    line-height: 2;
    opacity: 0.8;
    word-break: keep-all;
  }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to   { opacity: 1; transform: translateY(0); }
  }
  .animate-in { animation: fadeUp 0.5s ease both; }
  .delay-1 { animation-delay: 0.1s; }
  .delay-2 { animation-delay: 0.2s; }
  .delay-3 { animation-delay: 0.3s; }
  .confetti-pop {
    animation: confettiPop 0.4s cubic-bezier(0.34,1.56,0.64,1);
  }
  @keyframes confettiPop {
    0%   { transform: scale(0.8); }
    60%  { transform: scale(1.15); }
    100% { transform: scale(1); }
  }
</style>
</head>
<body>
<div class="phone-frame">

<!-- HERO -->
<div class="hero">
  <div class="hero-badge">🌿 過敏性鼻炎衛教</div>
  <h1>環境也會影響<span>鼻子</span>？<br>過敏性鼻炎的日常照護</h1>
  <p class="hero-sub">過敏性鼻炎不只和體質有關，生活環境中的刺激，也會影響鼻子的穩定度。</p>
  <div class="allergen-pills">
    <div class="pill">🪲 塵蟎（最常見）</div>
    <div class="pill">🍄 黴菌</div>
    <div class="pill">🌸 花粉</div>
    <div class="pill">🐱 寵物毛屑</div>
    <div class="pill">❄️ 冷空氣與溫差</div>
  </div>
</div>

<!-- GOALS BAR -->
<div class="goals-bar animate-in">
  <div class="goal-item">
    <div class="goal-icon">🛡️</div>
    <div class="goal-text">減少過敏原接觸</div>
  </div>
  <div class="goal-item">
    <div class="goal-icon">💧</div>
    <div class="goal-text">維持鼻腔穩定、適度濕潤</div>
  </div>
</div>

<!-- MAIN CONTENT -->
<div class="main">

  <div class="section-label">🛠 六大照護重點</div>

  <!-- TIP 1 -->
  <div class="tip-card animate-in delay-1" id="tip1">
    <div class="tip-header" onclick="toggleTip('tip1')">
      <div class="tip-num">1</div>
      <div class="tip-title">控制濕度，減少塵蟎與黴菌</div>
      <div class="tip-emoji">💨</div>
      <div class="tip-chevron">▼</div>
    </div>
    <div class="tip-body">
      <div class="tip-inner">
        <p class="tip-desc">台灣氣候潮濕，容易讓塵蟎與黴菌大量滋生，是過敏症狀加劇的主因之一。</p>
        <span class="tag tag-suggest">✅ 建議</span>
        <ul class="list-items">
          <li>室內濕度維持在 <strong>40%–50%</strong></li>
          <li>可使用除濕機或空調調節濕度</li>
        </ul>
        <div class="warn-box">⚠️ 注意：濕度太低（&lt;30%）會讓鼻黏膜乾燥，反而更敏感</div>
      </div>
    </div>
  </div>

  <!-- TIP 2 -->
  <div class="tip-card animate-in delay-1" id="tip2">
    <div class="tip-header" onclick="toggleTip('tip2')">
      <div class="tip-num">2</div>
      <div class="tip-title">寢具清潔（過敏最關鍵）</div>
      <div class="tip-emoji">🛏️</div>
      <div class="tip-chevron">▼</div>
    </div>
    <div class="tip-body">
      <div class="tip-inner">
        <p class="tip-desc">床鋪是塵蟎最多的地方，做好寢具清潔對改善過敏症狀非常有效。</p>
        <span class="tag tag-suggest">✅ 建議</span>
        <ul class="list-items">
          <li>每週清洗床單、枕頭套</li>
          <li>使用溫熱水（約 <strong>55°C 以上</strong>）清洗</li>
          <li>定期更換或使用防蟎寢具</li>
        </ul>
        <span class="tag tag-note">📌 特別注意</span>
        <div class="highlight-box">絨毛玩具、厚棉被也容易藏塵蟎，記得一起處理！</div>
      </div>
    </div>
  </div>

  <!-- TIP 3 -->
  <div class="tip-card animate-in delay-2" id="tip3">
    <div class="tip-header" onclick="toggleTip('tip3')">
      <div class="tip-num">3</div>
      <div class="tip-title">減少灰塵與過敏原堆積</div>
      <div class="tip-emoji">🧹</div>
      <div class="tip-chevron">▼</div>
    </div>
    <div class="tip-body">
      <div class="tip-inner">
        <p class="tip-desc">容易累積過敏原的物品：地毯、布沙發、厚窗簾、絨毛玩具，應盡量減少。</p>
        <span class="tag tag-suggest">✅ 建議</span>
        <ul class="list-items">
          <li>減少布料家具</li>
          <li>定期擦拭桌面與地板</li>
          <li>使用吸塵器清潔（效果更好）</li>
        </ul>
      </div>
    </div>
  </div>

  <!-- TIP 4 -->
  <div class="tip-card animate-in delay-2" id="tip4">
    <div class="tip-header" onclick="toggleTip('tip4')">
      <div class="tip-num">4</div>
      <div class="tip-title">避免冷空氣與溫差刺激</div>
      <div class="tip-emoji">🌡️</div>
      <div class="tip-chevron">▼</div>
    </div>
    <div class="tip-body">
      <div class="tip-inner">
        <p class="tip-desc">鼻子對「溫度變化」非常敏感，你是否有這些情況？</p>
        <span class="tag tag-note">📋 常見狀況</span>
        <ul class="list-items">
          <li>一進冷氣房就鼻塞</li>
          <li>早上起床特別容易打噴嚏</li>
        </ul>
        <span class="tag tag-suggest">✅ 建議</span>
        <ul class="list-items">
          <li>冷氣溫度不要過低（避免過冷）</li>
          <li>避免冷風直接吹臉</li>
          <li>進出冷氣房可戴口罩</li>
        </ul>
      </div>
    </div>
  </div>

  <!-- TIP 5 -->
  <div class="tip-card animate-in delay-3" id="tip5">
    <div class="tip-header" onclick="toggleTip('tip5')">
      <div class="tip-num">5</div>
      <div class="tip-title">外出後清潔（阻斷過敏原帶入）</div>
      <div class="tip-emoji">🚶</div>
      <div class="tip-chevron">▼</div>
    </div>
    <div class="tip-body">
      <div class="tip-inner">
        <p class="tip-desc">花粉、灰塵會附著在身體上帶回家，外出回家後的清潔習慣很重要。</p>
        <span class="tag tag-suggest">✅ 建議</span>
        <ul class="list-items">
          <li>回家後洗手、洗臉</li>
          <li>換衣服</li>
          <li>花粉多或空污嚴重時戴口罩</li>
        </ul>
      </div>
    </div>
  </div>

  <!-- TIP 6 -->
  <div class="tip-card animate-in delay-3" id="tip6">
    <div class="tip-header" onclick="toggleTip('tip6')">
      <div class="tip-num">6</div>
      <div class="tip-title">鼻腔清潔（輔助保養）</div>
      <div class="tip-emoji">💧</div>
      <div class="tip-chevron">▼</div>
    </div>
    <div class="tip-body">
      <div class="tip-inner">
        <p class="tip-desc">當鼻子有分泌物或接觸到過敏原時，可使用生理食鹽水（約接近體溫）清潔鼻腔。</p>
        <span class="tag tag-suggest">✅ 功能</span>
        <ul class="list-items">
          <li>沖掉灰塵、花粉</li>
          <li>減少刺激物堆積</li>
          <li>維持鼻腔濕潤</li>
        </ul>
        <div class="warn-box">⚠️ 若有嚴重鼻塞、鼻出血、耳朵不適，應先諮詢醫師或專業人員。</div>
      </div>
    </div>
  </div>

  <!-- SELF-CHECK -->
  <div class="section-label">🧠 自我覺察</div>
  <div class="self-check-card animate-in">
    <div class="self-check-title">🌿 想一想，環境正在影響你嗎？</div>
    <div class="self-check-sub">以下情況你有幾個？</div>
    <div class="check-q" id="cq1" onclick="highlightQ(this)">你是不是一進冷氣房就鼻塞？</div>
    <div class="check-q" id="cq2" onclick="highlightQ(this)">早上起床特別容易打噴嚏？</div>
    <div class="check-q" id="cq3" onclick="highlightQ(this)">房間潮濕時症狀變嚴重？</div>
    <div class="self-check-result">
      💡 如果你有其中幾項，<strong>這代表「環境正在影響你的鼻子」</strong>。做好環境控制，就能有效減少症狀！
    </div>
  </div>

  <!-- TASK CHECKLIST -->
  <div class="section-label">📋 今日護鼻任務</div>
  <div class="task-card animate-in">
    <div class="task-header">
      <div class="task-icon">📝</div>
      <div>
        <div class="task-title">今日護鼻任務</div>
        <div class="task-subtitle">請完成以下 3 項</div>
      </div>
    </div>
    <div class="task-progress-bar">
      <div class="task-progress-fill" id="taskProgress"></div>
    </div>
    <div class="task-item" id="task-a" onclick="toggleTask('task-a')">
      <div class="task-cb"><span class="task-cb-tick">✓</span></div>
      <div class="task-text">🌡️ 檢查房間濕度（是否過潮）</div>
    </div>
    <div class="task-item" id="task-b" onclick="toggleTask('task-b')">
      <div class="task-cb"><span class="task-cb-tick">✓</span></div>
      <div class="task-text">🛏️ 整理床鋪或清潔床邊灰塵</div>
    </div>
    <div class="task-item" id="task-c" onclick="toggleTask('task-c')">
      <div class="task-cb"><span class="task-cb-tick">✓</span></div>
      <div class="task-text">❄️ 避免冷氣直接吹臉</div>
    </div>
    <div class="task-done-msg" id="taskDoneMsg">🎉 太棒了！今日任務全部完成！你的鼻子感謝你！</div>
  </div>

  <!-- SCORE SLIDER -->
  <div class="section-label">📊 自我評估</div>
  <div class="score-card animate-in">
    <div class="score-header">
      <div class="score-star">⭐</div>
      <div>
        <div class="score-title">今天鼻子舒服嗎？</div>
      </div>
    </div>
    <p class="score-desc">幫自己的鼻子打個分數（0–10 分）</p>
    <div class="slider-wrap">
      <input type="range" min="0" max="10" value="5" id="scoreSlider" oninput="updateScore(this.value)">
      <div class="slider-labels">
        <span>0<br>😣 非常不舒服</span>
        <span style="text-align:center">5<br>😐</span>
        <span style="text-align:right">10<br>😄 完全沒症狀</span>
      </div>
    </div>
    <div class="score-display">
      <div class="score-num" id="scoreNum">5</div>
      <div class="score-emoji" id="scoreEmoji">😐</div>
      <div class="score-label" id="scoreLabel">普通，繼續維持今天的照護！</div>
    </div>
  </div>

  <!-- DOCTOR NOTE -->
  <div class="doctor-note animate-in">
    <div class="doctor-note-icon">🩺</div>
    <div class="doctor-note-text">
      <strong>就醫提醒：</strong>若有嚴重鼻塞、鼻出血、耳朵不適等情況，請勿自行處理，應優先諮詢醫師或專業醫療人員。
    </div>
  </div>

</div>

<footer>
  <div class="footer-title">中國醫藥大學 · 健康照護學院 · 健康照護科學研究所</div>
  <div class="footer-divider"></div>
  <div class="footer-body">
    本內容為研究計畫之衛教素材，僅供健康教育與研究參考使用<br>
    不作為醫療診斷或治療依據，實際診療請諮詢中醫師
  </div>
</footer>
</div><!-- /phone-frame -->

<script>
// ── TIP ACCORDION ──
function toggleTip(id) {
  const card = document.getElementById(id);
  const isOpen = card.classList.contains('open');
  // close all
  document.querySelectorAll('.tip-card').forEach(c => c.classList.remove('open'));
  if (!isOpen) card.classList.add('open');
}

// ── TASK CHECKLIST ──
function toggleTask(id) {
  const item = document.getElementById(id);
  item.classList.toggle('checked');
  if (item.classList.contains('checked')) item.classList.add('confetti-pop');
  setTimeout(() => item.classList.remove('confetti-pop'), 400);
  updateProgress();
}
function updateProgress() {
  const total = document.querySelectorAll('.task-item').length;
  const done  = document.querySelectorAll('.task-item.checked').length;
  const pct   = (done / total) * 100;
  document.getElementById('taskProgress').style.width = pct + '%';
  const msg = document.getElementById('taskDoneMsg');
  if (done === total) {
    msg.style.display = 'block';
    msg.classList.add('confetti-pop');
  } else {
    msg.style.display = 'none';
  }
}

// ── SCORE SLIDER ──
const scoreData = [
  { emoji: '😣', label: '非常不舒服，好好休息並多喝水', color: '#ef4444' },
  { emoji: '😣', label: '很不舒服，建議盡快就醫評估', color: '#ef4444' },
  { emoji: '😟', label: '有些不適，注意環境控制', color: '#f97316' },
  { emoji: '😟', label: '稍感不適，繼續做好照護', color: '#f97316' },
  { emoji: '😐', label: '普通，繼續維持今天的照護！', color: '#eab308' },
  { emoji: '😐', label: '普通，繼續維持今天的照護！', color: '#eab308' },
  { emoji: '🙂', label: '還不錯，繼續保持好習慣！', color: '#84cc16' },
  { emoji: '🙂', label: '蠻舒服的，照護做得很好！', color: '#22c55e' },
  { emoji: '😊', label: '相當舒服，太棒了！', color: '#10b981' },
  { emoji: '😄', label: '非常舒服，繼續保持！', color: '#059669' },
  { emoji: '🥳', label: '完全沒有症狀，今天最棒！', color: '#047857' },
];
function updateScore(val) {
  const v = parseInt(val);
  document.getElementById('scoreNum').textContent = v;
  document.getElementById('scoreEmoji').textContent = scoreData[v].emoji;
  document.getElementById('scoreLabel').textContent = scoreData[v].label;
  document.getElementById('scoreNum').style.color = scoreData[v].color;
  // update slider track
  const slider = document.getElementById('scoreSlider');
  slider.style.setProperty('--val', (v / 10 * 100) + '%');
  slider.style.background = `linear-gradient(90deg, ${scoreData[v].color} ${v/10*100}%, #d8f3dc ${v/10*100}%)`;
}
updateScore(5);

// ── SELF-CHECK HIGHLIGHT ──
function highlightQ(el) {
  el.style.opacity = el.style.opacity === '0.5' ? '0.9' : '0.5';
}
</script>

</body>
</html>
