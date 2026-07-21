# wangzhe-<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>抹山集 × 王者荣耀 · 峡谷解腻挑战赛</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Noto+Sans+SC:wght@300;400;500;700;900&display=swap" rel="stylesheet">
<style>
/* ── Reset & Base ── */
*, *::before, *::after { margin:0; padding:0; box-sizing:border-box; }
:root {
  --brand: #3b6b2a;
  --brand-light: #8dc078;
  --brand-dark: #26441c;
  --brand-glow: rgba(59,107,42,.15);
  --gold: #f5a623;
  --gold-light: #fef3c7;
  --bg: #f6f3ef;
  --card: #ffffff;
  --text: #2c2c2c;
  --text-mid: #5a5a5a;
  --text-light: #8b8b8b;
  --border: #eae5df;
  --radius: 16px;
  --radius-sm: 10px;
  --shadow: 0 2px 16px rgba(0,0,0,.06);
  --shadow-lg: 0 8px 32px rgba(0,0,0,.08);
}
html { scroll-behavior: smooth; }
body {
  font-family: 'Noto Sans SC', -apple-system, sans-serif;
  background: var(--bg);
  color: var(--text);
  line-height: 1.7;
  -webkit-font-smoothing: antialiased;
  padding-bottom: 60px;
  overflow-x: hidden;
}

/* ── Animations ── */
@keyframes fadeUp {
  from { opacity:0; transform:translateY(24px); }
  to   { opacity:1; transform:translateY(0); }
}
@keyframes fadeIn {
  from { opacity:0; }
  to   { opacity:1; }
}
@keyframes float {
  0%,100% { transform:translateY(0); }
  50%     { transform:translateY(-6px); }
}
@keyframes pulseGlow {
  0%,100% { box-shadow:0 0 0 0 var(--brand-glow); }
  50%     { box-shadow:0 0 0 12px transparent; }
}
@keyframes shimmer {
  0%   { background-position:-200% 0; }
  100% { background-position:200% 0; }
}
@keyframes scaleIn {
  from { opacity:0; transform:scale(.92); }
  to   { opacity:1; transform:scale(1); }
}
@keyframes slideDown {
  from { opacity:0; transform:translateY(-12px); }
  to   { opacity:1; transform:translateY(0); }
}

/* ── Header ── */
.header {
  background: linear-gradient(160deg, var(--brand-dark) 0%, #1f3a16 40%, var(--brand) 100%);
  padding: 48px 24px 64px;
  text-align: center;
  position: relative;
  overflow: hidden;
}
.header::before {
  content: '';
  position: absolute; inset: 0;
  background:
    radial-gradient(circle at 15% 70%, rgba(141,192,120,.15) 0%, transparent 50%),
    radial-gradient(circle at 85% 30%, rgba(245,166,35,.10) 0%, transparent 40%);
  pointer-events:none;
}
.header::after {
  content: '';
  position: absolute; bottom: 0; left: 0; right: 0; height: 48px;
  background: linear-gradient(to top, var(--bg), transparent);
  pointer-events:none;
}
.header-grid {
  position: absolute; inset: 0;
  background-image:
    linear-gradient(rgba(255,255,255,.03) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255,255,255,.03) 1px, transparent 1px);
  background-size: 48px 48px;
  pointer-events:none;
}
.header-badge {
  display: inline-flex; align-items: center; gap: 8px;
  background: rgba(255,255,255,.08);
  backdrop-filter: blur(6px);
  border: 1px solid rgba(255,255,255,.15);
  border-radius: 100px;
  padding: 4px 16px 4px 6px;
  position: relative; z-index: 2;
  animation: slideDown .5s ease both;
}
.header-badge::before {
  content: ''; display: inline-block; width: 6px; height: 6px;
  border-radius: 50%; background: var(--gold);
  animation: pulseGlow 2s infinite;
}
.badge-text { font-size: 12px; font-weight: 500; color: rgba(255,255,255,.85); letter-spacing: 2px; }
.badge-divider { width: 3px; height: 3px; border-radius: 50%; background: rgba(255,255,255,.3); }
.badge-game {
  font-size: 12px; font-weight: 600; color: var(--gold); letter-spacing: 1px;
  display: inline-flex; align-items: center; gap: 3px;
}

.header h1 {
  font-size: clamp(36px, 8vw, 52px); font-weight: 900; color: #fff;
  line-height: 1.12; position: relative; z-index: 2; letter-spacing: 4px;
  margin-top: 18px;
  animation: fadeUp .7s ease .15s both;
}
.header h1 em {
  font-style: normal;
  background: linear-gradient(135deg, var(--brand-light) 0%, #fff 40%, var(--gold) 100%);
  -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;
  background-size: 200% auto;
  animation: shimmer 3s ease-in-out infinite;
}
.header-sub {
  font-size: 14px; color: rgba(255,255,255,.55); margin-top: 10px;
  position: relative; z-index: 2; letter-spacing: 3px; font-weight: 300;
  animation: fadeUp .6s ease .3s both;
}
.header-illus {
  position: relative; z-index: 2; margin-top: 28px;
  display: flex; justify-content: center; gap: 12px;
  animation: fadeUp .6s ease .4s both;
}
.header-illus .item {
  background: rgba(255,255,255,.07); border: 1px solid rgba(255,255,255,.1);
  border-radius: 14px; padding: 14px 14px; text-align: center;
  flex: 1; max-width: 110px;
  transition: background .3s, transform .3s, border-color .3s;
  cursor: default;
}
.header-illus .item:hover {
  background: rgba(255,255,255,.13);
  transform: translateY(-4px);
  border-color: rgba(255,255,255,.2);
}
.header-illus .item.wide { max-width: 130px; }
.header-illus .item .icon { font-size: 30px; margin-bottom: 6px; display: block; }
.header-illus .item .label { font-size: 11px; color: rgba(255,255,255,.65); font-weight: 400; }

/* ── Container ── */
.container { max-width: 900px; margin: -32px auto 0; padding: 0 20px; position: relative; z-index: 3; }

/* ── Sections ── */
.section {
  background: var(--card); border-radius: var(--radius); box-shadow: var(--shadow);
  margin-bottom: 18px; overflow: hidden;
  border: 1px solid rgba(0,0,0,.04);
  opacity: 0;
  animation: fadeUp .5s ease forwards;
}
.section-title {
  display: flex; align-items: center; gap: 10px;
  padding: 20px 24px 14px; font-size: 17px; font-weight: 700;
  color: var(--brand-dark); border-bottom: 1px solid #f0ebe5;
}
.section-title .st-icon { font-size: 22px; }
.section-body { padding: 16px 24px 22px; }

/* ── Info Tags ── */
.info-tags { display: flex; flex-wrap: wrap; gap: 10px; margin-bottom: 16px; }
.tag {
  display: inline-flex; align-items: center; gap: 6px;
  background: #f4f8f1; border: 1px solid #dde8d5;
  border-radius: 100px; padding: 6px 16px;
  font-size: 13px; color: var(--brand); font-weight: 500;
  transition: background .2s, border-color .2s;
}
.tag:hover { background: #e8f0e3; border-color: var(--brand-light); }
.tag .t-icon { font-size: 14px; }

.body-text { font-size: 14px; color: var(--text-mid); line-height: 1.85; margin-bottom: 14px; }

/* ── Flow Steps ── */
.flow-steps { display: flex; gap: 12px; margin-top: 14px; }
.flow-step {
  flex: 1; background: #f6f9f4; border-radius: var(--radius-sm);
  padding: 14px 10px; text-align: center; border: 1px solid #e4ede0;
  transition: transform .25s, box-shadow .25s, background .25s;
}
.flow-step:hover {
  transform: translateY(-3px);
  box-shadow: 0 6px 16px rgba(59,107,42,.12);
  background: #f0f7ed;
}
.flow-step .fs-num {
  display: inline-flex; align-items: center; justify-content: center;
  width: 30px; height: 30px; border-radius: 50%;
  background: var(--brand); color: #fff; font-size: 12px; font-weight: 700; margin-bottom: 8px;
  transition: transform .3s, background .3s;
}
.flow-step:hover .fs-num { transform: scale(1.12); }
.flow-step .fs-title { font-size: 14px; font-weight: 600; color: var(--text); }
.flow-step .fs-desc { font-size: 11px; color: var(--text-light); line-height: 1.4; margin-top: 3px; }
.flow-step.highlight { background: #e7f0e0; border-color: var(--brand-light); }
.flow-step.highlight .fs-num { background: var(--gold); }

/* ── Zone List ── */
.zone-list { display: flex; gap: 12px; flex-wrap: wrap; }
.zone-item {
  display: flex; gap: 14px; background: #f8fbf6;
  border-radius: var(--radius-sm); padding: 16px; border: 1px solid #eaf1e4;
  transition: transform .25s, box-shadow .25s, border-color .25s;
  flex: 1; min-width: 280px;
}
.zone-item:hover {
  transform: translateY(-2px);
  border-color: var(--brand-light);
  box-shadow: 0 4px 12px rgba(59,107,42,.08);
}
.zone-icon {
  width: 52px; height: 52px; border-radius: var(--radius-sm);
  display: flex; align-items: center; justify-content: center;
  font-size: 26px; flex-shrink: 0;
  transition: transform .3s;
}
.zone-item:hover .zone-icon { transform: scale(1.08); }
.zone-icon.z1 { background: linear-gradient(135deg,#e8f0e3,#c8dcc0); }
.zone-icon.z2 { background: linear-gradient(135deg,#fef3c7,#fde68a); }
.zone-info { flex: 1; min-width: 0; }
.zone-info .z-name { font-size: 15px; font-weight: 600; color: var(--text); }
.zone-info .z-desc { font-size: 13px; color: var(--text-light); line-height: 1.5; margin-top: 3px; }
.zone-info .z-items { margin-top: 6px; }
.zone-info .z-items li {
  font-size: 12px; color: var(--text-mid); padding-left: 14px; position: relative;
  line-height: 1.7; list-style: none;
}
.zone-info .z-items li::before { content: '·'; position: absolute; left: 0; color: var(--brand); font-weight: 700; }

/* ── Info Rows ── */
.info-row { display: flex; align-items: flex-start; padding: 12px 0; border-bottom: 1px solid #edf1e8; }
.info-row:last-child { border-bottom: none; }
.info-label { flex: 0 0 80px; font-size: 13px; font-weight: 600; color: var(--brand); }
.info-value { font-size: 14px; color: var(--text); flex: 1; }

/* ── Sub Title ── */
.sub-title { font-size: 15px; font-weight: 600; color: var(--text); margin-bottom: 10px; display: flex; align-items: center; gap: 6px; }

/* ── Table ── */
.table-wrap { overflow-x: auto; margin-top: 8px; }
.price-tbl { width: 100%; border-collapse: separate; border-spacing: 0; font-size: 14px; border-radius: 10px; overflow: hidden; }
.price-tbl thead tr { background: var(--brand); }
.price-tbl th { color: #fff; padding: 10px 14px; font-weight: 600; text-align: center; font-size: 13px; letter-spacing: 1px; }
.price-tbl td { padding: 10px 14px; text-align: center; border-bottom: 1px solid #eaf1e4; transition: background .2s; }
.price-tbl tbody tr { transition: background .2s; }
.price-tbl tbody tr:hover td { background: #f0f7ed !important; }
.price-tbl tbody tr:last-child td { border-bottom: none; }
.price-tbl tbody tr:nth-child(even) td { background: #f7faf3; }

/* ── Prize Chips ── */
.prize-chips { display: flex; flex-wrap: wrap; gap: 10px; }
.prize-chip {
  background: #f4f8f1; border: 1px solid #dde8d5; border-radius: 100px;
  padding: 7px 18px; display: inline-flex; align-items: center; gap: 6px;
  font-size: 13px; color: var(--text);
  transition: transform .2s, box-shadow .2s, background .2s;
}
.prize-chip:hover {
  transform: translateY(-2px);
  box-shadow: 0 3px 10px rgba(59,107,42,.10);
  background: #edf6e7;
}
.prize-chip .pc-icon { font-size: 16px; }
.prize-chip .pc-price { font-size: 11px; color: var(--text-light); margin-left: 2px; }
.prize-chip.gold { background: var(--gold-light); border-color: #fde68a; font-weight: 600; color: #92400e; }
.prize-chip.free { background: #f0f0f0; border-color: #ddd; color: #888; }
.prize-chip.free .pc-price { color: #aaa; }

/* ── Timeline ── */
.timeline { position: relative; padding-left: 32px; margin-top: 16px; }
.timeline::before {
  content: ''; position: absolute; left: 14px; top: 4px; bottom: 4px;
  width: 2px; background: linear-gradient(to bottom, var(--brand-light), var(--brand));
}
.tl-item { position: relative; margin-bottom: 22px; }
.tl-item:last-child { margin-bottom: 0; }
.tl-item::before {
  content: ''; position: absolute; left: -21px; top: 5px;
  width: 16px; height: 16px; border-radius: 50%;
  background: var(--brand); border: 3px solid #dde8d5;
  transition: transform .3s, box-shadow .3s;
}
.tl-item:hover::before {
  transform: scale(1.25);
  box-shadow: 0 0 0 5px rgba(59,107,42,.12);
}
.tl-date { font-size: 12px; font-weight: 500; color: var(--brand); letter-spacing: 1px; }
.tl-text { font-size: 14px; font-weight: 500; color: var(--text); margin-top: 2px; }
.tl-sub { font-size: 12px; color: var(--text-light); margin-top: 2px; }

/* ── Coser Cards ── */
.coser-cards { display: grid; grid-template-columns: repeat(2, 1fr); gap: 10px; }
.coser-card {
  display: flex; gap: 12px; background: #f8fbf6;
  border-radius: var(--radius-sm); padding: 14px; align-items: flex-start;
  border: 1px solid #eaf1e4;
  transition: transform .25s, box-shadow .25s, border-color .25s;
}
.coser-card:hover {
  transform: translateY(-2px);
  border-color: var(--brand-light);
  box-shadow: 0 4px 14px rgba(59,107,42,.10);
}
.cc-rank {
  flex-shrink: 0; width: 28px; height: 28px; border-radius: 50%;
  display: flex; align-items: center; justify-content: center;
  font-size: 12px; font-weight: 700; margin-top: 1px;
  transition: transform .3s;
}
.coser-card:hover .cc-rank { transform: scale(1.15); }
.cc-rank.r1 { background: #fef3c7; color: #92400e; }
.cc-rank.r2 { background: #e0f2fe; color: #1e40af; }
.cc-rank.r3 { background: #e8f0e3; color: var(--brand); }
.cc-rank.r4 { background: #fce7f3; color: #9d174d; }
.cc-info { flex: 1; min-width: 0; }
.cc-info .cc-name { font-size: 14px; font-weight: 600; color: var(--text); }
.cc-info .cc-reason { font-size: 12px; color: var(--text-light); line-height: 1.5; margin-top: 3px; }

/* ── Tip Box ── */
.tip-box {
  background: #edf4e7; border: 1px solid #d4e5c9; border-radius: var(--radius-sm);
  padding: 14px 18px; display: flex; gap: 10px; align-items: flex-start; margin-top: 16px;
  transition: background .2s;
}
.tip-box:hover { background: #e6f0de; }
.tip-box .tip-icon { font-size: 18px; flex-shrink: 0; margin-top: 1px; }
.tip-box .tip-text { font-size: 13px; color: var(--brand); line-height: 1.7; }

/* ── Budget ── */
.budget-list { }
.budget-item {
  display: flex; justify-content: space-between; align-items: center;
  padding: 12px 0; border-bottom: 1px solid #edf1e8; font-size: 14px;
  transition: padding-left .2s;
}
.budget-item:hover { padding-left: 8px; }
.budget-item:last-child { border-bottom: none; }
.budget-item .bi-label { font-weight: 500; color: var(--text); }
.budget-item .bi-label .bi-note { font-size: 12px; color: var(--text-light); font-weight: 400; display: block; margin-top: 1px; }
.budget-item .bi-price { font-weight: 600; color: var(--brand); flex-shrink: 0; margin-left: 20px; font-variant-numeric: tabular-nums; }
.budget-item .bi-status {
  font-size: 10px; padding: 1px 8px; border-radius: 100px;
  font-weight: 500; margin-right: 8px;
}
.budget-item .bi-status.prepaid { background: #e0f2fe; color: #0369a1; }
.budget-item .bi-status.pending { background: #fef3c7; color: #92400e; }
.budget-item.total {
  border-top: 2px solid var(--brand); margin-top: 8px; padding-top: 14px;
  background: #f4f8f1;
  border-radius: 0 0 var(--radius-sm) var(--radius-sm);
  margin-left: -24px; margin-right: -24px; padding-left: 24px; padding-right: 24px;
}
.budget-item.total:hover { padding-left: 32px; }
.budget-item.total .bi-label { font-weight: 700; color: var(--brand-dark); font-size: 15px; }
.budget-item.total .bi-price { font-size: 18px; color: var(--brand-dark); }

/* Prepayment Summary */
.prepaid-summary {
  background: #f0f5ee;
  border: 1px solid #d4e5c9;
  border-radius: var(--radius-sm);
  padding: 14px 18px;
  margin-top: 14px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.prepaid-summary .ps-label { font-size: 13px; font-weight: 600; color: var(--brand-dark); }
.prepaid-summary .ps-label small { font-weight: 400; display: block; font-size: 11px; color: var(--text-light); margin-top: 1px; }
.prepaid-summary .ps-price { font-size: 18px; font-weight: 700; color: var(--brand-dark); }

/* ── Responsive ── */
@media (max-width:640px) {
  .header { padding: 36px 16px 48px; }
  .header-illus .item { padding: 10px 8px; max-width: 80px; }
  .header-illus .item.wide { max-width: 100px; }
  .header-illus .item .icon { font-size: 24px; }
  .container { padding: 0 12px; }
  .section-title { padding: 16px 16px 12px; font-size: 15px; }
  .section-body { padding: 12px 16px 16px; }
  .flow-steps { flex-wrap: wrap; }
  .flow-step { min-width: calc(33.33% - 8px); }
  .zone-list { flex-direction: column; }
  .zone-item { min-width: 0; }
  .coser-cards { grid-template-columns: 1fr; }
  .budget-item.total { margin-left: -16px; margin-right: -16px; padding-left: 16px; padding-right: 16px; }
  .budget-item.total:hover { padding-left: 24px; }
  .prepaid-summary { flex-direction: column; align-items: flex-start; gap: 6px; }
}
@media (min-width:641px) and (max-width:900px) {
  .coser-cards { grid-template-columns: 1fr; }
}
</style>
</head>
<body>

<!-- ═══ Header ═══ -->
<header class="header">
  <div class="header-grid"></div>
  <div class="header-badge">
    <span class="badge-text">抹山集</span>
    <span class="badge-divider"></span>
    <span class="badge-game">⚔ 王者荣耀</span>
  </div>
  <h1>峡谷解腻<em>站</em></h1>
  <p class="header-sub">2026.8.2  ·  万达广场中庭</p>
  <div class="header-illus">
    <div class="item"><span class="icon">🎮</span><span class="label">王者比赛</span></div>
    <div class="item wide"><span class="icon">🎁</span><span class="label">盲盒100%中奖</span></div>
    <div class="item"><span class="icon">📸</span><span class="label">Coser合影</span></div>
    <div class="item"><span class="icon">☕</span><span class="label">抹茶特饮</span></div>
  </div>
</header>

<!-- ═══ Content ═══ -->
<div class="container">

  <!-- 活动概览 -->
  <div class="section" style="animation-delay:.1s;">
    <div class="section-title"><span class="st-icon">📋</span> 活动概览</div>
    <div class="section-body">
      <div class="info-tags">
        <span class="tag"><span class="t-icon">📅</span> 8月2日</span>
        <span class="tag"><span class="t-icon">📍</span> 万达广场中庭</span>
        <span class="tag"><span class="t-icon">🎯</span> 品牌展位</span>
        <span class="tag"><span class="t-icon">🔄</span> 拍照发圈抽盲盒</span>
      </div>
      <p class="body-text">
        万达广场8月2日举办王者荣耀线下赛，抹山集以合作品牌身份在场内设置展位。配置盲盒装置 + Coser全程坐镇，在比赛现场完成品牌曝光、打卡合影与UGC转化。
      </p>
      <div style="font-size:13px;font-weight:500;color:var(--brand);margin-bottom:8px;">用户参与流程</div>
      <div class="flow-steps">
        <div class="flow-step">
          <div class="fs-num">01</div>
          <div class="fs-title">围观比赛</div>
          <div class="fs-desc">商场客流被吸引</div>
        </div>
        <div class="flow-step highlight">
          <div class="fs-num">02</div>
          <div class="fs-title">找Coser合影</div>
          <div class="fs-desc">发小红书/抖音</div>
        </div>
        <div class="flow-step">
          <div class="fs-num">03</div>
          <div class="fs-title">抽盲盒</div>
          <div class="fs-desc">100%中奖</div>
        </div>
      </div>
    </div>
  </div>

  <!-- 展位规划 -->
  <div class="section" style="animation-delay:.2s;">
    <div class="section-title"><span class="st-icon">🏪</span> 展位分区规划</div>
    <div class="section-body">
      <div class="zone-list">
        <div class="zone-item">
          <div class="zone-icon z1">🎁</div>
          <div class="zone-info">
            <div class="z-name">A区 · 盲盒装置区</div>
            <div class="z-desc">现有盲盒装置，凭发圈记录抽取</div>
            <ul class="z-items"><li>奖品展示 + 规则立牌</li></ul>
          </div>
        </div>
        <div class="zone-item">
          <div class="zone-icon z2">📸</div>
          <div class="zone-info">
            <div class="z-name">B区 · Coser打卡区</div>
            <div class="z-desc">Coser全程在此引导、配合合影</div>
            <ul class="z-items"><li>品牌打卡背景墙 + 补光灯 + 手持牌</li></ul>
          </div>
        </div>
      </div>
      <div class="tip-box">
        <span class="tip-icon">💡</span>
        <span class="tip-text">两个区域紧邻布置，Coser同时可帮盲盒区引流，形成"找Coser合影 → 发圈 → 抽盲盒"的自然动线。</span>
      </div>
    </div>
  </div>

  <!-- Coser安排 -->
  <div class="section" style="animation-delay:.3s;">
    <div class="section-title"><span class="st-icon">🧝</span> Coser安排</div>
    <div class="section-body">
      <p class="body-text">
        使用主办方的Coser资源，由主办方统一安排人员及角色。Coser在展位B区引导引流、合影打卡，同时配合完成预热视频拍摄及现场活动引导。
      </p>
      <div class="info-row">
        <div class="info-label">工作</div>
        <div class="info-value">出镜拍摄预热短视频 + 品牌引流 + 合影打卡，引导发小红书/抖音带话题</div>
      </div>
      <div class="info-row">
        <div class="info-label">时间</div>
        <div class="info-value">8月2日 具体时间暂定，妆造由主办方负责。</div>
      </div>
      <div class="info-row" style="border-bottom:none;">
        <div class="info-label">预算</div>
        <div class="info-value"><strong style="color:var(--brand);font-size:16px;">2,000元</strong>（主办方Coser费用，用完为止）</div>
      </div>

      <div class="sub-title" style="margin-top:18px;">🏆 推荐角色 · 皮肤</div>
      <p style="font-size:13px;color:var(--text-light);margin-bottom:12px;">建议选择与品牌调性（抹茶绿）契合的英雄皮肤，由主办方根据实际情况确定。</p>
      <div class="coser-cards">
        <div class="coser-card">
          <div class="cc-rank r1">1</div>
          <div class="cc-info">
            <div class="cc-name">大乔 · 白鹤梁神女</div>
            <div class="cc-reason">白+墨绿配色，国风鱼鳞纹路，与抹茶绿品牌色调一致，拍照出片</div>
          </div>
        </div>
        <div class="coser-card">
          <div class="cc-rank r2">2</div>
          <div class="cc-info">
            <div class="cc-name">貂蝉 · 遇见胡旋</div>
            <div class="cc-reason">敦煌绿+金配色，华丽度高，路人辨识度强</div>
          </div>
        </div>
        <div class="coser-card">
          <div class="cc-rank r3">3</div>
          <div class="cc-info">
            <div class="cc-name">西施 · 游龙清影</div>
            <div class="cc-reason">清雅国风，绿色系为主，服装成本低</div>
          </div>
        </div>
        <div class="coser-card">
          <div class="cc-rank r4">4</div>
          <div class="cc-info">
            <div class="cc-name">瑶 · 时之祈愿</div>
            <div class="cc-reason">年轻玩家接受度高，互动感好</div>
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- 盲盒装置 -->
  <div class="section" style="animation-delay:.4s;">
    <div class="section-title"><span class="st-icon">🎁</span> 盲盒装置 · 拍照发圈即可抽奖</div>
    <div class="section-body">
      <div class="info-row">
        <div class="info-label">参与条件</div>
        <div class="info-value">与Coser合影并发小红书/抖音，带话题 <strong style="color:var(--brand);">#抹山集#</strong></div>
      </div>
      <div class="info-row" style="border-bottom:none;">
        <div class="info-label">核销</div>
        <div class="info-value">出示已发内容页面 → 抽取盲盒（每人限1次）</div>
      </div>
      <div class="sub-title" style="margin-top:16px;">🎰 奖品明细</div>
      <div class="prize-chips">
        <span class="prize-chip"><span class="pc-icon">☕</span> 买一送一 ×15 </span>
        <span class="prize-chip free"><span class="pc-icon">🔖</span> 8折券 ×5 <span class="pc-price"></span></span>
        <span class="prize-chip"><span class="pc-icon">🎉</span> 免单券 ×5 </span>
        <span class="prize-chip"><span class="pc-icon">🍪</span> 小糕点/土豆片 ×20 </span>
        <span class="prize-chip gold">共45份 · 100%中奖</span>
      </div>
      <div class="tip-box" style="margin-top:14px;">
        <span class="tip-icon">💡</span>
        <span class="tip-text">买一送一券可用于抹茶特饮核销；8折券为赠送、不计入成本。</span>
      </div>
    </div>
  </div>

  <!-- 预热推广 -->
  <div class="section" style="animation-delay:.5s;">
    <div class="section-title"><span class="st-icon">📱</span> 预热推广：预赛视频拍摄</div>
    <div class="section-body">
      <p class="body-text">
        7月25日拍摄、抖音+小红书同步投放。花果园购物中心负一楼中厅，拍摄预赛情况，凸显抹山集的运动适配性。
      </p>
      <div class="info-row">
        <div class="info-label">饮品准备</div>
        <div class="info-value">提供40杯抹山集饮品用于拍摄现场展示</div>
      </div>
      <div class="timeline">
        <div class="tl-item">
          <div class="tl-date">7月25日</div>
          <div class="tl-text">拍摄及发布</div>
          <div class="tl-sub">花果园购物中心负一楼中厅</div>
        </div>
        <div class="tl-item">
          <div class="tl-date">8月2日</div>
          <div class="tl-text">活动当天</div>
          <div class="tl-sub">Coser引导 + 盲盒运营</div>
        </div>
      </div>
    </div>
  </div>

  <!-- 人员配置 -->
  <div class="section" style="animation-delay:.6s;">
    <div class="section-title"><span class="st-icon">👥</span> 人员配置</div>
    <div class="section-body">
      <div class="table-wrap">
        <table class="price-tbl">
          <thead><tr><th>岗位</th><th>人数</th><th>职责</th></tr></thead>
          <tbody>
            <tr><td><strong>Coser（主办方提供）</strong></td><td>若干</td><td>出镜拍摄 + 引导引流 + 合影打卡 + 现场氛围</td></tr>
            <tr><td><strong>盲盒核销员</strong></td><td>1人</td><td>核验发圈记录、发放盲盒、登记奖品</td></tr>
            <tr><td><strong>机动/摄影</strong></td><td>1人</td><td>现场拍照、物料看管、支援各岗位</td></tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>

  <!-- 物料清单 -->
  <div class="section" style="animation-delay:.7s;">
    <div class="section-title"><span class="st-icon">📦</span> 物料清单</div>
    <div class="section-body">
      <div class="table-wrap">
        <table class="price-tbl">
          <thead><tr><th>物料</th><th>数量</th><th>备注</th></tr></thead>
          <tbody>
            <tr><td>盲盒装置</td><td>1套</td><td>已有，直接搬运</td></tr>
            <tr><td>展位背景板</td><td>1块</td><td>抹茶绿主色+Logo</td></tr>
            <tr><td>打卡背景墙</td><td>1面</td><td>"峡谷解腻站"主题</td></tr>
            <tr><td>Coser手持牌</td><td>4块</td><td>英雄台词+Slogan，2名Coser各2块</td></tr>
            <tr><td>补光灯</td><td>1台</td><td>已有</td></tr>
            <tr><td>主办方饮品</td><td>140杯</td><td>品牌提供给主办方作为赞助</td></tr>
            <tr><td>盲盒奖券/奖品</td><td>45份</td><td>买一送一15+8折券5(赠送)+免单券5+糕点土豆片20</td></tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>

  <!-- 预算明细 -->
  <div class="section" style="animation-delay:.8s;">
    <div class="section-title"><span class="st-icon">💰</span> 预算明细</div>
    <div class="section-body">
      <div class="budget-list">
        <div class="budget-item">
          <span class="bi-label">
            ① 盲盒奖品
            <small class="bi-note">买一送一✖️15+8折券✖️5(赠送)+免单券✖️5+糕点土豆片✖️20</small>
          </span>
          <span class="bi-price">270元</span>
        </div>
        <div class="budget-item">
          <span class="bi-label">
            ② 主办方饮品
            <small class="bi-note">140杯</small>
          </span>
          <span class="bi-price">980元</span>
        </div>
        <div class="budget-item">
          <span class="bi-label">
            ③ 备用金
            
          </span>
          <span class="bi-price">600元</span>
        </div>

        <div class="budget-item">
          <span class="bi-label">
            ④ Coser费用
            <small class="bi-note">主办方提供Coser资源</small>
          </span>
          <span class="bi-price">2,000元</span>
        </div>

        <div class="budget-item total">
          <span class="bi-label">总计</span>
          <span class="bi-price">3,850元</span>
        </div>
      </div>
    </div>
  </div>

</div>

</body>
</html>
