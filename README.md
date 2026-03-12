<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Toro Craft Beer — Menu</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,700;1,400&family=DM+Sans:wght@300;400;500&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0E0600;
    --card: #1A0A02;
    --border: rgba(196,130,10,0.2);
    --amber: #C4820A;
    --gold: #E8A820;
    --cream: #FDF0DC;
    --muted: #9B7A55;
    --red: #E03A1E;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    font-family: 'DM Sans', sans-serif;
    color: var(--cream);
    min-height: 100vh;
    padding-bottom: 60px;
  }

  /* background texture */
  body::before {
    content: '';
    position: fixed; inset: 0;
    background-image: radial-gradient(rgba(196,130,10,0.04) 1px, transparent 1px);
    background-size: 24px 24px;
    pointer-events: none;
    z-index: 0;
  }

  .wrap {
    max-width: 480px;
    margin: 0 auto;
    padding: 0 16px;
    position: relative;
    z-index: 1;
  }

  /* ── HEADER ── */
  .header {
    text-align: center;
    padding: 44px 0 28px;
  }

  .logo-ring {
    width: 80px; height: 80px;
    border-radius: 50%;
    background: linear-gradient(135deg, #3A1200, #9A5A08);
    border: 2px solid var(--amber);
    display: flex; align-items: center; justify-content: center;
    font-size: 36px;
    margin: 0 auto 16px;
    box-shadow: 0 0 0 4px rgba(196,130,10,0.12), 0 8px 32px rgba(0,0,0,0.5);
  }

  .brand {
    font-family: 'Playfair Display', serif;
    font-size: 28px;
    font-weight: 700;
    letter-spacing: 2px;
    color: var(--cream);
  }

  .brand em {
    display: block;
    font-style: italic;
    font-size: 14px;
    color: var(--amber);
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-top: 2px;
    font-family: 'Space Mono', monospace;
    font-weight: 400;
  }

  .address {
    margin-top: 10px;
    font-size: 12px;
    color: var(--muted);
    font-family: 'Space Mono', monospace;
    letter-spacing: 1px;
  }

  /* best seller badge */
  .bs-badge {
    display: inline-flex;
    align-items: center;
    gap: 5px;
    background: rgba(224,58,30,0.15);
    border: 1px solid rgba(224,58,30,0.4);
    color: #FF6B4A;
    font-size: 10px;
    font-family: 'Space Mono', monospace;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    padding: 4px 10px;
    border-radius: 100px;
    margin-top: 14px;
  }

  /* ── CATEGORY SECTION ── */
  .cat {
    margin-top: 24px;
  }

  .cat-header {
    display: flex;
    align-items: center;
    gap: 10px;
    padding: 11px 16px;
    background: rgba(196,130,10,0.08);
    border: 1px solid var(--border);
    border-radius: 12px 12px 0 0;
    cursor: pointer;
    user-select: none;
    transition: background 0.2s;
  }

  .cat-header:hover { background: rgba(196,130,10,0.14); }

  .cat-icon { font-size: 20px; flex-shrink: 0; }

  .cat-name {
    font-family: 'Playfair Display', serif;
    font-size: 17px;
    font-weight: 700;
    color: var(--cream);
    flex: 1;
  }

  .cat-toggle {
    font-size: 14px;
    color: var(--amber);
    transition: transform 0.3s;
    font-family: 'Space Mono', monospace;
  }

  .cat-toggle.open { transform: rotate(180deg); }

  .cat-body {
    border: 1px solid var(--border);
    border-top: none;
    border-radius: 0 0 12px 12px;
    overflow: hidden;
    display: none;
  }

  .cat-body.open { display: block; }

  /* ── MENU ITEM ── */
  .item {
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    gap: 12px;
    padding: 11px 16px;
    border-bottom: 1px solid rgba(255,255,255,0.04);
    transition: background 0.15s;
  }

  .item:last-child { border-bottom: none; }
  .item:hover { background: rgba(255,255,255,0.025); }

  .item-left { flex: 1; }

  .item-name {
    font-size: 14px;
    color: var(--cream);
    line-height: 1.4;
  }

  .item-name .star {
    display: inline-block;
    background: rgba(224,58,30,0.2);
    color: #FF6B4A;
    font-size: 9px;
    font-family: 'Space Mono', monospace;
    padding: 1px 6px;
    border-radius: 4px;
    margin-left: 6px;
    vertical-align: middle;
    letter-spacing: 1px;
  }

  .item-price {
    font-family: 'Space Mono', monospace;
    font-size: 13px;
    color: var(--amber);
    font-weight: 700;
    white-space: nowrap;
    flex-shrink: 0;
    margin-top: 1px;
  }

  .item-price .range {
    display: block;
    font-size: 11px;
    color: var(--muted);
    font-weight: 400;
    text-align: right;
    margin-top: 2px;
  }

  /* ── OPEN HOURS ── */
  .hours-card {
    margin-top: 24px;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 20px;
    text-align: center;
  }

  .hours-card .h-label {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    letter-spacing: 2px;
    color: var(--muted);
    text-transform: uppercase;
    margin-bottom: 8px;
  }

  .hours-card .h-time {
    font-family: 'Playfair Display', serif;
    font-size: 26px;
    font-style: italic;
    color: var(--gold);
  }

  .hours-card .h-sub {
    font-size: 13px;
    color: var(--muted);
    margin-top: 4px;
  }

  /* ── FOOTER ── */
  .footer {
    text-align: center;
    margin-top: 32px;
    padding-top: 24px;
    border-top: 1px solid var(--border);
  }

  .footer .ig {
    font-family: 'Space Mono', monospace;
    font-size: 13px;
    color: var(--amber);
    letter-spacing: 1px;
  }

  .footer .tagline {
    font-size: 12px;
    color: var(--muted);
    margin-top: 6px;
    font-style: italic;
  }
</style>
</head>
<body>
<div class="wrap">

  <!-- HEADER -->
  <div class="header">
    <div class="logo-ring">🍺</div>
    <div class="brand">TORO<em>Craft Beer</em></div>
    <div class="address">📍 143 Lê Lợi, Đà Nẵng</div>
    <div class="bs-badge">⭐ Best Seller đánh dấu đỏ</div>
  </div>

  <!-- 🐟 CÁ -->
  <div class="cat">
    <div class="cat-header" onclick="toggle(this)">
      <span class="cat-icon">🐟</span>
      <span class="cat-name">Món Cá</span>
      <span class="cat-toggle">▼</span>
    </div>
    <div class="cat-body">
      <div class="item"><div class="item-left"><div class="item-name">Cá cơm tráng chiên mắm</div></div><div class="item-price">70.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Cá đét chiên mắm</div></div><div class="item-price">80.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Cá chuồn mít nướng mọi</div></div><div class="item-price">80.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Cá đét chiên sốt mặn me<span class="star">BEST</span></div></div><div class="item-price">80.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Cà gió khô tiêu<span class="star">BEST</span></div></div><div class="item-price">160.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Bạch tuộc xào dưa cải</div></div><div class="item-price">90.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Bạch chỉ sả tắc<span class="star">BEST</span></div></div><div class="item-price">100.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Điệm heo nướng</div></div><div class="item-price">120.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Lưỡi heo chấm ruốc<span class="star">BEST</span></div></div><div class="item-price">100.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Ba chỉ xào dưa cải</div></div><div class="item-price">130.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Bao tử trâu xì</div></div><div class="item-price">130.000</div></div>
    </div>
  </div>

  <!-- 🐷 HEO -->
  <div class="cat">
    <div class="cat-header" onclick="toggle(this)">
      <span class="cat-icon">🐷</span>
      <span class="cat-name">Món Heo</span>
      <span class="cat-toggle">▼</span>
    </div>
    <div class="cat-body">
      <div class="item"><div class="item-left"><div class="item-name">Chà cua um măng</div></div><div class="item-price">120.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Hoành thánh nước</div></div><div class="item-price">100.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Mắt cá ngộ um</div></div><div class="item-price">80.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Khô qua chả cua<span class="star">BEST</span></div></div><div class="item-price">130.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Bao tị hầm tiêu & Mỳ tôm</div></div><div class="item-price">130.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Cà gió hầm thước cắc</div></div><div class="item-price">170.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Kẹ gà hầm thước thắc<span class="star">BEST</span></div></div><div class="item-price">220.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Lẩu cá bông lau</div></div><div class="item-price">180.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Lẩu thải sần (nhỏ / lớn)</div></div><div class="item-price"><span class="range">140.000 – 200.000</span></div></div>
      <div class="item"><div class="item-left"><div class="item-name">Lẩu gà trứng non ớt hiểm (nhỏ / lớn)</div></div><div class="item-price"><span class="range">220.000 – 290.000</span></div></div>
    </div>
  </div>

  <!-- 🥩 BÒ -->
  <div class="cat">
    <div class="cat-header" onclick="toggle(this)">
      <span class="cat-icon">🥩</span>
      <span class="cat-name">Món Bò</span>
      <span class="cat-toggle">▼</span>
    </div>
    <div class="cat-body">
      <div class="item"><div class="item-left"><div class="item-name">Gú bò nướng</div></div><div class="item-price">120.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Bụp bò đầm tỏi<span class="star">BEST</span></div></div><div class="item-price">130.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Bò bít tết tiêu đen</div></div><div class="item-price">150.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Bò Toro<span class="star">BEST</span></div></div><div class="item-price">150.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Bò thổng mùi</div></div><div class="item-price">150.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Bò lúc lắc + khoai tây chiên<span class="star">BEST</span></div></div><div class="item-price">150.000</div></div>
    </div>
  </div>

  <!-- 🐔 GÀ -->
  <div class="cat">
    <div class="cat-header" onclick="toggle(this)">
      <span class="cat-icon">🐔</span>
      <span class="cat-name">Món Gà</span>
      <span class="cat-toggle">▼</span>
    </div>
    <div class="cat-body">
      <div class="item"><div class="item-left"><div class="item-name">Trứng gà non chạy tỏi</div></div><div class="item-price">30.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Gà xào sả ớt</div></div><div class="item-price">90.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Gà rang muối HK<span class="star">BEST</span></div></div><div class="item-price">130.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Gà chiên cay<span class="star">BEST</span></div></div><div class="item-price">130.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Gà rang muối mắm</div></div><div class="item-price">130.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Gà non chạy tỏi</div></div><div class="item-price">130.000</div></div>
    </div>
  </div>

  <!-- 🦐 TÔM · MỰC -->
  <div class="cat">
    <div class="cat-header" onclick="toggle(this)">
      <span class="cat-icon">🦐</span>
      <span class="cat-name">Tôm · Mực</span>
      <span class="cat-toggle">▼</span>
    </div>
    <div class="cat-body">
      <div class="item"><div class="item-left"><div class="item-name">Tôm sốt me<span class="star">BEST</span></div></div><div class="item-price">140.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Tôm sốt Thái</div></div><div class="item-price">140.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Tôm chiên bột bông</div></div><div class="item-price">120.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Mực chiên mắm</div></div><div class="item-price">120.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Mực chào thánh</div></div><div class="item-price">130.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Mực khô nướng<span class="star">BEST</span></div></div><div class="item-price">130.000</div></div>
    </div>
  </div>

  <!-- 🥗 SALAD · RAU GỎI -->
  <div class="cat">
    <div class="cat-header" onclick="toggle(this)">
      <span class="cat-icon">🥗</span>
      <span class="cat-name">Salad · Rau Gỏi</span>
      <span class="cat-toggle">▼</span>
    </div>
    <div class="cat-body">
      <div class="item"><div class="item-left"><div class="item-name">Dưa thuốc tỏi chưa bi</div></div><div class="item-price">40.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Cải thìa xào tỏi</div></div><div class="item-price">60.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Rau muống xào tỏi</div></div><div class="item-price">60.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Bắp cải thập cẩm</div></div><div class="item-price">60.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Gỏi tôm thịt<span class="star">BEST</span></div></div><div class="item-price">80.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Khổ qua xào trứng</div></div><div class="item-price">80.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Gỏi tôm chả hông</div></div><div class="item-price">80.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Gỏi toái cà cơm tráng</div></div><div class="item-price">80.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Khổ qua chả bông<span class="star">BEST</span></div></div><div class="item-price">90.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Khổ qua là Salad</div></div><div class="item-price">95.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Xúc xích nướng TH lọp</div></div><div class="item-price">110.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Luôn ngồng xông khói + Salad</div></div><div class="item-price">115.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Kho qua nầm thi lọp</div></div><div class="item-price">110.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Kẹo đậu</div></div><div class="item-price">90.000</div></div>
    </div>
  </div>

  <!-- 🫙 KHAI VỊ -->
  <div class="cat">
    <div class="cat-header" onclick="toggle(this)">
      <span class="cat-icon">🫙</span>
      <span class="cat-name">Khai Vị</span>
      <span class="cat-toggle">▼</span>
    </div>
    <div class="cat-body">
      <div class="item"><div class="item-left"><div class="item-name">Nêm chua</div></div><div class="item-price">10.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Khoai tây chiên</div></div><div class="item-price">40.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Đậu phụng muối</div></div><div class="item-price">50.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Top Mỡ</div></div><div class="item-price">60.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Đầu hồ chiên giòn</div></div><div class="item-price">60.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Bánh mì xào tép</div></div><div class="item-price">70.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Trứng tôm</div></div><div class="item-price">70.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Trứng cuốn</div></div><div class="item-price">70.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Pho mắt xốt rồng khôi</div></div><div class="item-price">70.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Phò mắt nghệm màn</div></div><div class="item-price">70.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Tứng cắt chiên màn</div></div><div class="item-price">70.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Hoành thánh chiên<span class="star">BEST</span></div></div><div class="item-price">80.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Đầu tủ hành Cg tôm kho</div></div><div class="item-price">80.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Lớp xương dài loan</div></div><div class="item-price">110.000</div></div>
    </div>
  </div>

  <!-- 🎋 ĐỒNG QUÊ -->
  <div class="cat">
    <div class="cat-header" onclick="toggle(this)">
      <span class="cat-icon">🎋</span>
      <span class="cat-name">Đồng Quê</span>
      <span class="cat-toggle">▼</span>
    </div>
    <div class="cat-body">
      <div class="item"><div class="item-left"><div class="item-name">Ốc bươu xào xa</div></div><div class="item-price">80.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Ốc bươu xào thầu đậu</div></div><div class="item-price">80.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Ốc ti thiền hà</div></div><div class="item-price">80.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Bắt sào sả ớt</div></div><div class="item-price">90.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Luôn sào thầu đậu<span class="star">BEST</span></div></div><div class="item-price">110.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Luôn xào thầu đậu</div></div><div class="item-price">120.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Bắt rán sào sả ớt</div></div><div class="item-price">140.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Luôn sào xốt banh ti rắng</div></div><div class="item-price">140.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Chim cút thìu</div></div><div class="item-price">100.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Chim cút thiên mắm</div></div><div class="item-price">100.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Chim cút chiên mắm</div></div><div class="item-price">100.000</div></div>
    </div>
  </div>

  <!-- 🍝 PASTA · PÂTÉ -->
  <div class="cat">
    <div class="cat-header" onclick="toggle(this)">
      <span class="cat-icon">🍝</span>
      <span class="cat-name">Pasta · Pâté</span>
      <span class="cat-toggle">▼</span>
    </div>
    <div class="cat-body">
      <div class="item"><div class="item-left"><div class="item-name">Pate Toro & Bánh mì bò<span class="star">BEST</span></div></div><div class="item-price">80.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Combo Pâté + Pasta</div></div><div class="item-price">120.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Combo chả + Pate</div></div><div class="item-price">120.000</div></div>
    </div>
  </div>

  <!-- 🍚 CƠM · MÌ -->
  <div class="cat">
    <div class="cat-header" onclick="toggle(this)">
      <span class="cat-icon">🍚</span>
      <span class="cat-name">Cơm · Mì</span>
      <span class="cat-toggle">▼</span>
    </div>
    <div class="cat-body">
      <div class="item"><div class="item-left"><div class="item-name">Mỳ ăn cặp đôi</div></div><div class="item-price">65.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Cơm chiên bò hải tắc</div></div><div class="item-price">70.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Cơm chén bò hải tắc</div></div><div class="item-price">80.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Cơm chia nhỏ</div></div><div class="item-price">180.000</div></div>
      <div class="item"><div class="item-left"><div class="item-name">Cơm chiên bo hải tắc (lớn)</div></div><div class="item-price">160.000</div></div>
    </div>
  </div>

  <!-- HOURS -->
  <div class="hours-card">
    <div class="h-label">Giờ mở cửa · Opening Hours</div>
    <div class="h-time">5:00 PM — Late</div>
    <div class="h-sub">Mở cửa mỗi ngày · Open daily</div>
  </div>

  <!-- FOOTER -->
  <div class="footer">
    <div class="ig">@toro.craftbeer.danang</div>
    <div class="tagline">143 Lê Lợi · Đà Nẵng · Craft Beer & Real Food</div>
  </div>

</div>

<script>
function toggle(header) {
  const body = header.nextElementSibling;
  const arrow = header.querySelector('.cat-toggle');
  const isOpen = body.classList.contains('open');
  body.classList.toggle('open', !isOpen);
  arrow.classList.toggle('open', !isOpen);
}

// Open best sellers section by default
document.querySelectorAll('.cat-header')[2].click(); // Món Bò open by default
</script>
</body>
</html>
