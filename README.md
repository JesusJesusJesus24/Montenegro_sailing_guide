<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Черногория — маршрут на яхте · Сила Ветра</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,500;0,600;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
:root {
  --sea: #1a4d6b;
  --sea-mid: #2a7ba0;
  --sea-light: #d4eaf5;
  --sand: #f5f0e8;
  --sand-dark: #e8dfc8;
  --text: #1c2b35;
  --text-mid: #4a6272;
  --text-light: #8aa5b5;
  --accent: #c47b3a;
  --accent-light: #f0dfc5;
  --white: #ffffff;
  --border: rgba(26,77,107,0.12);
  --radius: 12px;
}
* { box-sizing: border-box; margin: 0; padding: 0; }
body {
  font-family: 'DM Sans', sans-serif;
  background: var(--sand);
  color: var(--text);
  line-height: 1.6;
}

/* HEADER */
.hero {
  background: var(--sea);
  color: white;
  padding: 3rem 2rem 2.5rem;
  text-align: center;
  position: relative;
  overflow: hidden;
}
.hero::before {
  content: '';
  position: absolute;
  bottom: -2px; left: 0; right: 0;
  height: 40px;
  background: var(--sand);
  clip-path: ellipse(55% 100% at 50% 100%);
}
.hero-eyebrow {
  font-family: 'DM Sans', sans-serif;
  font-size: 11px;
  font-weight: 500;
  letter-spacing: .18em;
  text-transform: uppercase;
  color: rgba(255,255,255,0.55);
  margin-bottom: 12px;
}
.hero h1 {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(2.2rem, 6vw, 3.5rem);
  font-weight: 500;
  line-height: 1.15;
  margin-bottom: 10px;
}
.hero h1 em { font-style: italic; color: rgba(255,255,255,0.7); }
.hero-sub {
  font-size: 14px;
  color: rgba(255,255,255,0.6);
  margin-top: 6px;
}
.route-summary {
  display: flex;
  justify-content: center;
  gap: 24px;
  margin-top: 28px;
  flex-wrap: wrap;
}
.rs-item {
  text-align: center;
}
.rs-num {
  font-family: 'Cormorant Garamond', serif;
  font-size: 2rem;
  font-weight: 600;
  color: white;
  line-height: 1;
}
.rs-label {
  font-size: 11px;
  color: rgba(255,255,255,0.5);
  letter-spacing: .06em;
  text-transform: uppercase;
  margin-top: 2px;
}

/* ВАЖНАЯ ИНФО */
.info-strip {
  background: var(--accent-light);
  border-bottom: 1px solid var(--sand-dark);
  padding: 12px 2rem;
  display: flex;
  gap: 24px;
  flex-wrap: wrap;
  justify-content: center;
  font-size: 12.5px;
  color: var(--text-mid);
}
.info-strip b { color: var(--text); }

/* NAV */
.nav-wrap {
  position: sticky;
  top: 0;
  z-index: 100;
  background: var(--white);
  border-bottom: 1px solid var(--border);
  padding: 0 1rem;
  overflow-x: auto;
  white-space: nowrap;
  scrollbar-width: none;
}
.nav-wrap::-webkit-scrollbar { display: none; }
.day-nav {
  display: inline-flex;
  gap: 4px;
  padding: 10px 0;
}
.dnb {
  display: inline-block;
  padding: 6px 16px;
  border-radius: 20px;
  border: none;
  background: transparent;
  color: var(--text-mid);
  cursor: pointer;
  font-family: 'DM Sans', sans-serif;
  font-size: 13px;
  font-weight: 500;
  transition: all .15s;
  white-space: nowrap;
}
.dnb:hover { background: var(--sea-light); color: var(--sea); }
.dnb.on { background: var(--sea); color: white; }

/* CONTENT */
.main { max-width: 820px; margin: 0 auto; padding: 2rem 1.25rem 4rem; }
.day-section { display: none; }
.day-section.vis { display: block; }

/* DAY HEADER */
.day-hdr {
  display: flex;
  gap: 16px;
  align-items: flex-start;
  margin-bottom: 1.5rem;
  padding-bottom: 1.5rem;
  border-bottom: 1px solid var(--border);
}
.day-circle {
  width: 52px; height: 52px;
  border-radius: 50%;
  background: var(--sea);
  color: white;
  display: flex; align-items: center; justify-content: center;
  font-family: 'Cormorant Garamond', serif;
  font-size: 20px;
  font-weight: 600;
  flex-shrink: 0;
}
.day-title-block h2 {
  font-family: 'Cormorant Garamond', serif;
  font-size: 1.8rem;
  font-weight: 500;
  line-height: 1.2;
  color: var(--text);
}
.tags { margin-top: 6px; display: flex; gap: 6px; flex-wrap: wrap; }
.tag {
  display: inline-block;
  padding: 2px 10px;
  border-radius: 20px;
  font-size: 11px;
  font-weight: 500;
  background: var(--sea-light);
  color: var(--sea);
  letter-spacing: .03em;
}
.tag.amber { background: var(--accent-light); color: var(--accent); }

/* BADGES */
.badges {
  display: flex; gap: 10px; flex-wrap: wrap;
  margin-bottom: 1.75rem;
}
.badge {
  display: flex; align-items: center; gap: 7px;
  padding: 8px 14px;
  border: 1px solid var(--border);
  border-radius: 10px;
  background: var(--white);
  font-size: 13px;
  color: var(--text-mid);
}
.badge strong { color: var(--text); font-weight: 500; }
.badge .ico { font-size: 14px; }

/* SECTIONS */
.sec-label {
  font-size: 10px;
  font-weight: 500;
  letter-spacing: .12em;
  text-transform: uppercase;
  color: var(--text-light);
  margin-bottom: 10px;
  margin-top: 1.75rem;
  display: flex;
  align-items: center;
  gap: 8px;
}
.sec-label::after {
  content: '';
  flex: 1;
  height: 1px;
  background: var(--border);
}

/* MARINA CARD */
.marina-card {
  background: var(--white);
  border: 1px solid var(--border);
  border-radius: var(--radius);
  overflow: hidden;
  margin-bottom: 1rem;
}
.marina-top {
  background: var(--sea);
  color: white;
  padding: 12px 18px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 8px;
}
.marina-name {
  font-family: 'Cormorant Garamond', serif;
  font-size: 1.15rem;
  font-weight: 500;
}
.vhf-badge {
  background: rgba(255,255,255,0.15);
  border: 1px solid rgba(255,255,255,0.3);
  border-radius: 6px;
  padding: 3px 10px;
  font-size: 12px;
  font-weight: 500;
  letter-spacing: .05em;
}
.marina-body {
  padding: 14px 18px;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 8px 20px;
}
.md-row { font-size: 13px; color: var(--text-mid); line-height: 1.5; }
.md-row b { color: var(--text); font-weight: 500; }
.md-row a { color: var(--sea-mid); text-decoration: none; }
.md-row a:hover { text-decoration: underline; }

/* TWO MARINAS */
.two-marinas { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; margin-bottom: 1rem; }
@media (max-width: 580px) { .two-marinas { grid-template-columns: 1fr; } }

/* RESTAURANTS */
.resto-list { background: var(--white); border: 1px solid var(--border); border-radius: var(--radius); overflow: hidden; margin-bottom: 1rem; }
.resto-item { display: flex; gap: 12px; padding: 12px 16px; border-bottom: 1px solid var(--border); align-items: flex-start; }
.resto-item:last-child { border-bottom: none; }
.resto-num {
  width: 24px; height: 24px; border-radius: 50%;
  background: var(--sea-light); color: var(--sea);
  display: flex; align-items: center; justify-content: center;
  font-size: 11px; font-weight: 500;
  flex-shrink: 0; margin-top: 2px;
}
.resto-name { font-size: 14px; font-weight: 500; color: var(--text); }
.resto-name a { color: var(--sea); text-decoration: none; }
.resto-name a:hover { text-decoration: underline; }
.resto-desc { font-size: 12.5px; color: var(--text-mid); margin-top: 3px; line-height: 1.5; }

/* ACTIVITIES */
.act-list { list-style: none; background: var(--white); border: 1px solid var(--border); border-radius: var(--radius); overflow: hidden; margin-bottom: 1rem; }
.act-list li { display: flex; gap: 10px; padding: 10px 16px; border-bottom: 1px solid var(--border); font-size: 13.5px; color: var(--text-mid); align-items: flex-start; line-height: 1.5; }
.act-list li:last-child { border-bottom: none; }
.act-ico { flex-shrink: 0; width: 20px; text-align: center; font-size: 14px; margin-top: 1px; }

/* NOTE */
.note {
  background: var(--sea-light);
  border: 1px solid rgba(42,123,160,0.2);
  border-radius: 10px;
  padding: 11px 15px;
  font-size: 13px;
  color: var(--sea);
  margin-top: 1rem;
  line-height: 1.5;
}
.note.amber {
  background: var(--accent-light);
  border-color: rgba(196,123,58,0.2);
  color: #8a5520;
}

/* MARINA TABLE (overall) */
.summary-table {
  width: 100%;
  border-collapse: collapse;
  background: var(--white);
  border: 1px solid var(--border);
  border-radius: var(--radius);
  overflow: hidden;
  font-size: 13px;
  margin-top: 1.5rem;
}
.summary-table th {
  background: var(--sea);
  color: rgba(255,255,255,0.8);
  font-weight: 500;
  font-size: 11px;
  letter-spacing: .06em;
  text-transform: uppercase;
  padding: 10px 14px;
  text-align: left;
}
.summary-table td {
  padding: 10px 14px;
  border-bottom: 1px solid var(--border);
  color: var(--text-mid);
  vertical-align: middle;
}
.summary-table tr:last-child td { border-bottom: none; }
.summary-table td:first-child { color: var(--text); font-weight: 500; }
.vhf-pill {
  display: inline-block;
  padding: 2px 8px;
  background: var(--sea-light);
  color: var(--sea);
  border-radius: 4px;
  font-size: 12px;
  font-weight: 500;
}
.price-free { color: #2d7a3e; font-weight: 500; }

/* FOOTER */
footer {
  text-align: center;
  padding: 2rem 1rem;
  font-size: 12px;
  color: var(--text-light);
  border-top: 1px solid var(--border);
  margin-top: 2rem;
}
footer a { color: var(--sea-mid); text-decoration: none; }
</style>
</head>
<body>

<div class="hero">
  <div class="hero-eyebrow">Сила Ветра · Парусный маршрут</div>
  <h1>Черногория<br><em>на двух яхтах</em></h1>
  <div class="hero-sub">Тиват · Котор · Херцег-Нови · Бигово · Будва · Луштица</div>
  <div class="route-summary">
    <div class="rs-item"><div class="rs-num">7</div><div class="rs-label">дней</div></div>
    <div class="rs-item"><div class="rs-num">~85</div><div class="rs-label">морских миль</div></div>
    <div class="rs-item"><div class="rs-num">6</div><div class="rs-label">стоянок</div></div>
    <div class="rs-item"><div class="rs-num">2</div><div class="rs-label">яхты</div></div>
  </div>
</div>

<div class="info-strip">
  <span>📻 <b>Черногорский VTS:</b> каналы 11 и 16</span>
  <span>⚡ <b>Скорость в заливе:</b> 10 уз, в проливах — 6 уз</span>
  <span>💶 <b>Валюта:</b> евро</span>
  <span>✈️ <b>Аэропорт:</b> Тиват (TIV) — 10 мин до марины</span>
  <span>🌦 <b>Прогноз:</b> <a href="https://meteo.hr/prognoze_e.php?section=prognoze_specp&param=jadran" target="_blank">meteo.hr</a></span>
</div>

<div class="nav-wrap">
  <div class="day-nav">
    <button class="dnb on" onclick="sw(1)">День 1 · Тиват</button>
    <button class="dnb" onclick="sw(2)">День 2 · Котор</button>
    <button class="dnb" onclick="sw(3)">День 3 · Херцег-Нови</button>
    <button class="dnb" onclick="sw(4)">День 4 · Бигово</button>
    <button class="dnb" onclick="sw(5)">День 5 · Будва</button>
    <button class="dnb" onclick="sw(6)">День 6 · Луштица</button>
    <button class="dnb" onclick="sw(7)">День 7 · Тиват</button>
    <button class="dnb" onclick="sw(8)">📋 Сводка</button>
  </div>
</div>

<div class="main">

<!-- ДЕНЬ 1 -->
<div class="day-section vis" id="d1">
  <div class="day-hdr">
    <div class="day-circle">1</div>
    <div class="day-title-block">
      <h2>Тиват — Porto Montenegro</h2>
      <div class="tags"><span class="tag">Старт</span><span class="tag amber">Заезд · 16:30</span></div>
    </div>
  </div>
  <div class="badges">
    <div class="badge"><span class="ico">⛵</span> Переход: <strong>0 миль</strong></div>
    <div class="badge"><span class="ico">📍</span> Встреча: <strong>Marina Montenegro, 16:30</strong></div>
    <div class="badge"><span class="ico">✈️</span> До аэропорта: <strong>10 мин такси</strong></div>
  </div>

  <div class="sec-label">Марина</div>
  <div class="marina-card">
    <div class="marina-top">
      <div class="marina-name">Porto Montenegro (Marina Montenegro)</div>
      <div class="vhf-badge">VHF 71</div>
    </div>
    <div class="marina-body">
      <div class="md-row">📞 <b>+382 32 661 061</b></div>
      <div class="md-row">📧 <a href="mailto:marinabooking@portomontenegro.com">marinabooking@portomontenegro.com</a></div>
      <div class="md-row">⛽ Заправка: <b><a href="mailto:bunkering@portomontenegro.com">bunkering@portomontenegro.com</a></b></div>
      <div class="md-row">💰 Стоянка ~12 м, высокий сезон: <b>€55–80 / ночь</b></div>
      <div class="md-row">📍 GPS: <b>42°26'N 18°41'E</b></div>
      <div class="md-row">🕐 Дежурство: <b>24/7</b></div>
      <div class="md-row">🌐 <a href="https://portomontenegro.com/ru/" target="_blank">portomontenegro.com</a></div>
      <div class="md-row">🚿 Душ/туалет: <b>есть</b></div>
    </div>
  </div>

  <div class="sec-label">Рестораны</div>
  <div class="resto-list">
    <div class="resto-item">
      <div class="resto-num">1</div>
      <div>
        <div class="resto-name"><a href="https://maps.app.goo.gl/XQ3NpqSxG3c4hXfn9" target="_blank">One Restaurant — Porto Montenegro</a></div>
        <div class="resto-desc">Прямо в марине, средиземноморская кухня, морепродукты. Вид на мегаяхты.</div>
      </div>
    </div>
    <div class="resto-item">
      <div class="resto-num">2</div>
      <div>
        <div class="resto-name"><a href="https://maps.app.goo.gl/VUuQU8YkAe4HXPJR9" target="_blank">Waikiki Beach Club — Seljanovo</a></div>
        <div class="resto-desc">5 мин от марины. Черногорская кухня, пляжная атмосфера.</div>
      </div>
    </div>
    <div class="resto-item">
      <div class="resto-num">3</div>
      <div>
        <div class="resto-name"><a href="https://maps.app.goo.gl/1Gk3qDhcJpiqXWXc7" target="_blank">Супермаркет Porto Montenegro Village</a></div>
        <div class="resto-desc">Закупка провизии на яхту — прямо внутри комплекса.</div>
      </div>
    </div>
  </div>

  <div class="sec-label">Программа дня</div>
  <ul class="act-list">
    <li><span class="act-ico">🛥</span>Заселение на лодки с 16:30, знакомство с командой и капитаном</li>
    <li><span class="act-ico">🛒</span>Закупка продуктов в супермаркете Porto Montenegro Village</li>
    <li><span class="act-ico">📋</span>Инструктаж по технике безопасности от капитана</li>
    <li><span class="act-ico">🚶</span>Вечерняя прогулка по набережной Porto Montenegro — рестораны, бары, галереи</li>
    <li><span class="act-ico">🏊</span>Бассейн и пляж в марине — отличный старт отдыха</li>
  </ul>
  <div class="note">💡 Аэропорт Тиват в 10 минутах езды. При задержке рейса — позвоните на VHF 71, дежурство круглосуточное.</div>
</div>

<!-- ДЕНЬ 2 -->
<div class="day-section" id="d2">
  <div class="day-hdr">
    <div class="day-circle">2</div>
    <div class="day-title-block">
      <h2>Тиват → Котор</h2>
      <div class="tags"><span class="tag">День на воде</span></div>
    </div>
  </div>
  <div class="badges">
    <div class="badge"><span class="ico">⛵</span> Переход: <strong>~10 морских миль</strong></div>
    <div class="badge"><span class="ico">⏱</span> Ходовое время: <strong>~2–2.5 часа</strong></div>
    <div class="badge"><span class="ico">🧭</span> Курс: <strong>Восток, вглубь залива</strong></div>
  </div>
  <div class="note">🏛 По пути — остров Богоматери на скале (42°28.979'N, 18°41.339'E) и остров Св. Георгия. Идеальная фотоостановка, можно зайти на дингии.</div>

  <div class="sec-label">Марина</div>
  <div class="marina-card">
    <div class="marina-top">
      <div class="marina-name">Марина Котор (Port of Kotor)</div>
      <div class="vhf-badge">VHF 17 / 16</div>
    </div>
    <div class="marina-body">
      <div class="md-row">📞 <b>+382 32 325 573</b></div>
      <div class="md-row">📧 <a href="mailto:portofkotor@t-com.me">portofkotor@t-com.me</a></div>
      <div class="md-row">💰 Стоянка ~12 м, высокий сезон: <b>€40–70 / ночь</b></div>
      <div class="md-row">📍 GPS: <b>42°25.47'N 18°46.05'E</b></div>
      <div class="md-row">🕐 Дежурство: <b>24/7</b></div>
      <div class="md-row">⚓ Мест: <b>80 (яхты 8–300 м)</b></div>
      <div class="md-row">⛽ Заправка: <b>севернее марины (обозначена на карте)</b></div>
      <div class="md-row">🚿 Душ/туалет: <b>нет в марине</b></div>
      <div class="md-row">🌐 <a href="https://www.portofkotor.com/en/" target="_blank">portofkotor.com</a></div>
    </div>
  </div>

  <div class="sec-label">Рестораны</div>
  <div class="resto-list">
    <div class="resto-item">
      <div class="resto-num">1</div>
      <div>
        <div class="resto-name"><a href="https://maps.app.goo.gl/VkK1Gxb3N5MNWEsS9" target="_blank">Galion Restaurant</a></div>
        <div class="resto-desc">У стен старого города, вид на залив. Морепродукты, ризотто, отличная карта вин. Один из лучших в Которе.</div>
      </div>
    </div>
    <div class="resto-item">
      <div class="resto-num">2</div>
      <div>
        <div class="resto-name"><a href="https://maps.app.goo.gl/xC8JnpJujm5CuBfj9" target="_blank">Konoba Portun</a></div>
        <div class="resto-desc">Семейный ресторан у гавани. Свежепойманная рыба ежедневно, осьминог, каламари — must try.</div>
      </div>
    </div>
    <div class="resto-item">
      <div class="resto-num">3</div>
      <div>
        <div class="resto-name"><a href="https://maps.app.goo.gl/nJzrYs1YVGbYZbkv8" target="_blank">Pescaria Dekaderon</a></div>
        <div class="resto-desc">На набережной. Устрицы, чёрный ризотто, сеабасс гриль. Один из лучших fine-dining в Которе.</div>
      </div>
    </div>
    <div class="resto-item">
      <div class="resto-num">4</div>
      <div>
        <div class="resto-name"><a href="https://maps.app.goo.gl/KSk3qSY9fQv8sJ9A9" target="_blank">Konoba Bonaca</a></div>
        <div class="resto-desc">Таверна в старом городе, любимая местными. Телятина под сачем, чевапи. Очень душевно.</div>
      </div>
    </div>
  </div>

  <div class="sec-label">Что делать</div>
  <ul class="act-list">
    <li><span class="act-ico">🏛</span>Прогулка по старому городу — брусчатка, венецианские дворики, площадь оружия</li>
    <li><span class="act-ico">🏰</span>Подъём на крепость Сан-Джованни — вход €8 (с 8:00 до 21:00), до/после — бесплатно. Лучший вид на залив</li>
    <li><span class="act-ico">🚶</span>Бесплатная тропа через южный вход — более дикая, но не менее красивая</li>
    <li><span class="act-ico">⛪</span>Спуск на восток к монастырю в долине + возврат по серпантину</li>
    <li><span class="act-ico">🎭</span>Морской музей Котора в старом городе (~€4)</li>
  </ul>
  <div class="note">💡 В Которе много круизных туристов — лучше гулять рано утром или вечером. Марина небольшая — вызывайте заблаговременно на VHF 17.</div>
</div>

<!-- ДЕНЬ 3 -->
<div class="day-section" id="d3">
  <div class="day-hdr">
    <div class="day-circle">3</div>
    <div class="day-title-block">
      <h2>Котор → Херцег-Нови</h2>
      <div class="tags"><span class="tag">День на воде</span><span class="tag">"Город тысячи ступеней"</span></div>
    </div>
  </div>
  <div class="badges">
    <div class="badge"><span class="ico">⛵</span> Переход: <strong>~15 морских миль</strong></div>
    <div class="badge"><span class="ico">⏱</span> Ходовое время: <strong>~3–4 часа</strong></div>
    <div class="badge"><span class="ico">🧭</span> Курс: <strong>Запад, через залив</strong></div>
  </div>
  <div class="note amber">⚠️ При проходе через пролив Вериге — ограничение 6 узлов. Мониторьте VTS Черногории: каналы 11 и 16.</div>

  <div class="sec-label">Марины — 2 варианта</div>
  <div class="two-marinas">
    <div class="marina-card">
      <div class="marina-top" style="background:#0f6e56">
        <div class="marina-name">Lazure Marina & Hotel ⭐</div>
        <div class="vhf-badge">звонить</div>
      </div>
      <div class="marina-body">
        <div class="md-row">📞 <b>+382 69 360 571</b></div>
        <div class="md-row">💰 Стоянка: <b>€50–90 / ночь</b></div>
        <div class="md-row">📍 GPS: <b>42°27.207'N 18°33.604'E</b></div>
        <div class="md-row">🏖 Бонус: <b>пляжный бар, СПА, 5★ отель</b></div>
      </div>
    </div>
    <div class="marina-card">
      <div class="marina-top" style="background:#4a6272">
        <div class="marina-name">Городская марина</div>
        <div class="vhf-badge">звонить</div>
      </div>
      <div class="marina-body">
        <div class="md-row">📞 <b>+382 68 022 011</b></div>
        <div class="md-row">👤 <b>Владимир</b></div>
        <div class="md-row">💰 Стоянка: <b>€30–50 / ночь</b></div>
        <div class="md-row">🚶 До центра: <b>5 минут пешком</b></div>
      </div>
    </div>
  </div>

  <div class="sec-label">Рестораны</div>
  <div class="resto-list">
    <div class="resto-item">
      <div class="resto-num">1</div>
      <div>
        <div class="resto-name"><a href="https://maps.app.goo.gl/Yd4R5b4A7mnSHJrL8" target="_blank">Feral Tavern</a></div>
        <div class="resto-desc">Лучший чёрный ризотто в Херцег-Нови. Рыба, пасты, супы. Щедрые порции, средиземноморская атмосфера.</div>
      </div>
    </div>
    <div class="resto-item">
      <div class="resto-num">2</div>
      <div>
        <div class="resto-name"><a href="https://maps.app.goo.gl/jK8F1D1uBpZXc2aZ9" target="_blank">Ресторан Lazure Hotel</a></div>
        <div class="resto-desc">При 5★ отеле. Авторские блюда, вид на марину. Чуть выше среднего по цене, но того стоит.</div>
      </div>
    </div>
    <div class="resto-item">
      <div class="resto-num">3</div>
      <div>
        <div class="resto-name"><a href="https://maps.app.goo.gl/Y3Gbf9U1sUV4NQiV9" target="_blank">Peter's Pie & Coffee</a></div>
        <div class="resto-desc">Šetalište Pet Danica, 18. Вегетарианское меню, десерты, отличный кофе. Для завтрака или кофе-брейка.</div>
      </div>
    </div>
    <div class="resto-item">
      <div class="resto-num">4</div>
      <div>
        <div class="resto-name"><a href="https://maps.app.goo.gl/7bBsEFckD1KHxQRm9" target="_blank">Yachting Club 32</a></div>
        <div class="resto-desc">На набережной Pet Danica, вид на марину. Морепродукты, черногорская кухня, коктейли. 8:00–00:00.</div>
      </div>
    </div>
  </div>

  <div class="sec-label">Что делать</div>
  <ul class="act-list">
    <li><span class="act-ico">🚤</span>Подводный бункер для субмарин напротив города — подойти на лодке лагом, зайти внутрь (обозначен на карте Силы Ветра)</li>
    <li><span class="act-ico">🌲</span>Савинская дубрава — заповедный парк на холме, тихий и уютный, рядом с монастырём Савина</li>
    <li><span class="act-ico">⛪</span>Монастырь Савина — главный православный центр залива. Пальмы, апельсиновые деревья. Основан в XIII в.</li>
    <li><span class="act-ico">🍷</span>Винодельня Savina Winery — дегустация €20–30 / чел. Тел: +382 69 042 022. <a href="http://castelsavina.me" target="_blank">castelsavina.me</a></li>
    <li><span class="act-ico">🌅</span>Закат с верхней террасы городского кафе Gradske Kafane</li>
    <li><span class="act-ico">🏙</span>Прогулка по «городу тысячи ступеней» — все улицы ведут вверх к горе Орьен</li>
  </ul>
  <div class="note">💡 Херцег-Нови — самый западный город залива. Отсюда завтра выходим в открытое море. Проверьте прогноз накануне на <a href="https://meteo.hr" target="_blank">meteo.hr</a>.</div>
</div>

<!-- ДЕНЬ 4 -->
<div class="day-section" id="d4">
  <div class="day-hdr">
    <div class="day-circle">4</div>
    <div class="day-title-block">
      <h2>Херцег-Нови → Бигово</h2>
      <div class="tags"><span class="tag">Открытое море</span><span class="tag amber">Тихая бухта</span></div>
    </div>
  </div>
  <div class="badges">
    <div class="badge"><span class="ico">⛵</span> Переход: <strong>~15 морских миль</strong></div>
    <div class="badge"><span class="ico">⏱</span> Ходовое время: <strong>~3 часа</strong></div>
    <div class="badge"><span class="ico">🧭</span> Курс: <strong>Юг, через пролив в открытое море</strong></div>
  </div>
  <div class="note amber">⚠️ Выход из залива Которского — при южных ветрах возможно сильное волнение! Следите за прогнозом на <a href="https://meteo.hr/prognoze_e.php?section=prognoze_specp&param=jadran" target="_blank">meteo.hr</a></div>

  <div class="sec-label">Стоянка</div>
  <div class="marina-card">
    <div class="marina-top" style="background:#2d6a4f">
      <div class="marina-name">Бигово — буи / якорная стоянка</div>
      <div class="vhf-badge" style="background:rgba(255,255,255,0.15)">VHF нет</div>
    </div>
    <div class="marina-body">
      <div class="md-row">⚓ Якорная стоянка: <b>бухта Траште, глубина 5–6 м</b></div>
      <div class="md-row">🪝 Буи Grispolis: <b>бесплатно при ужине в ресторане</b></div>
      <div class="md-row">🪝 Причал: <b>бесплатно при наличии места (3.5 м у торца)</b></div>
      <div class="md-row">💰 Стоянка: <b class="price-free">фактически бесплатно</b></div>
      <div class="md-row">🌊 Защита: <b>отличная со всех сторон, кроме NW</b></div>
      <div class="md-row">🛒 Магазин: <b>есть в деревне, базовый набор</b></div>
    </div>
  </div>

  <div class="sec-label">Рестораны</div>
  <div class="resto-list">
    <div class="resto-item">
      <div class="resto-num">1</div>
      <div>
        <div class="resto-name"><a href="https://maps.app.goo.gl/3MKEzPmRF3XW6n3T9" target="_blank">Konoba Grispolis</a></div>
        <div class="resto-desc">Главный ресторан деревни. Свежая рыба — камбала, ракушки, осьминог. Буи у пирса бесплатны при ужине здесь.</div>
      </div>
    </div>
    <div class="resto-item">
      <div class="resto-num">2</div>
      <div>
        <div class="resto-name">Второй ресторан (деревня)</div>
        <div class="resto-desc">Маленькое местное заведение. Простая домашняя еда, тихая атмосфера.</div>
      </div>
    </div>
  </div>

  <div class="sec-label">Что делать</div>
  <ul class="act-list">
    <li><span class="act-ico">🤿</span>Снорклинг в кристально чистой воде бухты — скалистое дно, много рыбы</li>
    <li><span class="act-ico">🏚</span>Прогулка к заброшенному югославскому военному санаторию на полуострове</li>
    <li><span class="act-ico">👁</span>Смотровая площадка на мысу с видом на залив Траште</li>
    <li><span class="act-ico">🎣</span>Рыбалка прямо с борта или с пирса</li>
    <li><span class="act-ico">🧘</span>Полный отдых — тишина, минимум туристов, чистейшее море</li>
  </ul>
  <div class="note">💡 Самая умиротворённая стоянка маршрута. В высокий сезон буи разбирают быстро — приходите до 15:00.</div>
</div>

<!-- ДЕНЬ 5 -->
<div class="day-section" id="d5">
  <div class="day-hdr">
    <div class="day-circle">5</div>
    <div class="day-title-block">
      <h2>Бигово → Свети-Стефан → Будва</h2>
      <div class="tags"><span class="tag">День на воде</span><span class="tag amber">Ночёвка в Будве</span></div>
    </div>
  </div>
  <div class="badges">
    <div class="badge"><span class="ico">⛵</span> Переход: <strong>~15 морских миль</strong></div>
    <div class="badge"><span class="ico">⏱</span> Ходовое время: <strong>~3–4 часа</strong></div>
    <div class="badge"><span class="ico">🧭</span> Курс: <strong>Юг вдоль берега</strong></div>
  </div>
  <div class="note">📸 Свети-Стефан виден по пути — легендарный островок-отель. Остановитесь ненадолго на якорь, сделайте фото с воды.</div>

  <div class="sec-label">Марина</div>
  <div class="marina-card">
    <div class="marina-top">
      <div class="marina-name">Dukley Marina Budva</div>
      <div class="vhf-badge">VHF 8 · 156.4 MHz</div>
    </div>
    <div class="marina-body">
      <div class="md-row">📞 <b>+382 33 453 296</b></div>
      <div class="md-row">👤 Контакт: <b>Jelena Jovanović</b></div>
      <div class="md-row">💰 Стоянка ~12 м, высокий сезон: <b>€80–150 / ночь</b></div>
      <div class="md-row">📍 GPS: <b>42°16'49"N 18°50'18.6"E</b></div>
      <div class="md-row">🛂 Погранконтроль: <b>1 мая — 1 ноября (8:00–22:00)</b></div>
      <div class="md-row">⛽ Заправка: <b>есть</b></div>
      <div class="md-row">⚓ Мест: <b>до 300, макс. осадка 4 м</b></div>
      <div class="md-row">🌐 <a href="https://www.dukleymarina.com" target="_blank">dukleymarina.com</a></div>
    </div>
  </div>

  <div class="sec-label">Рестораны</div>
  <div class="resto-list">
    <div class="resto-item">
      <div class="resto-num">1</div>
      <div>
        <div class="resto-name"><a href="https://maps.app.goo.gl/4kS8vPNFj4JdKwwx7" target="_blank">Stari Grad Restaurant</a></div>
        <div class="resto-desc">В Старом городе. Рагу из осьминога, морепродукты, черногорские вина. Аутентичная атмосфера.</div>
      </div>
    </div>
    <div class="resto-item">
      <div class="resto-num">2</div>
      <div>
        <div class="resto-name"><a href="https://maps.app.goo.gl/pDz8Z5jEY3mDVPQr9" target="_blank">Jadran Restaurant</a></div>
        <div class="resto-desc">На набережной у воды. Свежая рыба, черногорская и средиземноморская кухня.</div>
      </div>
    </div>
    <div class="resto-item">
      <div class="resto-num">3</div>
      <div>
        <div class="resto-name"><a href="https://maps.app.goo.gl/q1t4m1G9u6VvuJ9Z9" target="_blank">Astoria Budva</a></div>
        <div class="resto-desc">Популярный ресторан в центре. Большой выбор рыбы, разумные цены.</div>
      </div>
    </div>
  </div>

  <div class="sec-label">Что делать</div>
  <ul class="act-list">
    <li><span class="act-ico">🏰</span>Старый город Будвы — венецианские укрепления, узкие улочки, Цитадель (вход €2.5)</li>
    <li><span class="act-ico">🏖</span>Лучшие пляжи Будванской Ривьеры: Mogren, Slovenska Plaza, Bečići</li>
    <li><span class="act-ico">📸</span>Свети-Стефан с обзорной точки на шоссе (15 мин на такси)</li>
    <li><span class="act-ico">🌙</span>Ночная жизнь Будвы — самая живая на всём побережье</li>
    <li><span class="act-ico">🛍</span>Шопинг и рестораны по набережной Slovenska obala</li>
  </ul>
  <div class="note amber">💡 Dukley Marina — одна из самых дорогих стоянок маршрута. Бронируйте заранее — в высокий сезон мест не хватает. Подход строго по фарватеру между знаками.</div>
</div>

<!-- ДЕНЬ 6 -->
<div class="day-section" id="d6">
  <div class="day-hdr">
    <div class="day-circle">6</div>
    <div class="day-title-block">
      <h2>Будва → Луштица Bay</h2>
      <div class="tags"><span class="tag">День на воде</span><span class="tag">Возврат в залив</span></div>
    </div>
  </div>
  <div class="badges">
    <div class="badge"><span class="ico">⛵</span> Переход: <strong>~15 морских миль</strong></div>
    <div class="badge"><span class="ico">⏱</span> Ходовое время: <strong>~3–4 часа</strong></div>
    <div class="badge"><span class="ico">🧭</span> Курс: <strong>Север, обратно в залив Траште</strong></div>
  </div>

  <div class="sec-label">Марина</div>
  <div class="marina-card">
    <div class="marina-top">
      <div class="marina-name">Marina Luštica Bay</div>
      <div class="vhf-badge">VHF 68</div>
    </div>
    <div class="marina-body">
      <div class="md-row">📞 <b>+382 77 200 104</b></div>
      <div class="md-row">📧 <a href="mailto:info@lusticabay.com">info@lusticabay.com</a></div>
      <div class="md-row">💰 Стоянка ~12 м, высокий сезон: <b>€58–80 / ночь</b></div>
      <div class="md-row">📍 Расположение: <b>бухта Траште, п-ов Луштица</b></div>
      <div class="md-row">⚓ Мест: <b>115 (до 45 м длиной)</b></div>
      <div class="md-row">🕐 Охрана: <b>24/7 + видеонаблюдение</b></div>
      <div class="md-row">⛽ Заправка: <b>есть</b></div>
      <div class="md-row">🏨 Рядом: <b>5★ The Chedi Hotel, пляж, рестораны</b></div>
      <div class="md-row">🌐 <a href="https://lusticabay.com" target="_blank">lusticabay.com</a></div>
    </div>
  </div>
  <div class="note">🛟 Два мощных волнолома (7 м высотой) — идеальная защита даже в шторм. Условия внутри всегда спокойные.</div>

  <div class="sec-label">Рестораны</div>
  <div class="resto-list">
    <div class="resto-item">
      <div class="resto-num">1</div>
      <div>
        <div class="resto-name"><a href="https://maps.app.goo.gl/e9Xc5r4asCBNrZTJ9" target="_blank">The Chedi Restaurant — Luštica Bay</a></div>
        <div class="resto-desc">Ресторан 5★ отеля у марины. Средиземноморская кухня высшего уровня, потрясающий вид на залив.</div>
      </div>
    </div>
    <div class="resto-item">
      <div class="resto-num">2</div>
      <div>
        <div class="resto-name"><a href="https://maps.app.goo.gl/ry4MDWq2bHWYGpZe7" target="_blank">Marina Village Restaurants</a></div>
        <div class="resto-desc">Несколько ресторанов и баров прямо на набережной марины. Пекарня, кафе, морепродукты.</div>
      </div>
    </div>
    <div class="resto-item">
      <div class="resto-num">3</div>
      <div>
        <div class="resto-name"><a href="https://maps.app.goo.gl/xYFxkXPbMxuFpSs77" target="_blank">Konoba Ćatovića Mlini — Morinj</a></div>
        <div class="resto-desc">~20 мин такси. Ресторан в старой мельнице. 200 лет в семье Ćatović. Лучшие мидии и устрицы залива. Тел: +382 32 373 030</div>
      </div>
    </div>
  </div>

  <div class="sec-label">Что делать</div>
  <ul class="act-list">
    <li><span class="act-ico">🧗</span>Подъём на смотровую точку полуострова — панорама всего залива и открытого моря</li>
    <li><span class="act-ico">🏊</span>Пляж прямо у марины — чистая вода без толп</li>
    <li><span class="act-ico">🚴</span>Велопрогулка по полуострову — прокат организует марина</li>
    <li><span class="act-ico">🛶</span>Каякинг и SUP от марины</li>
    <li><span class="act-ico">🌅</span>Вечерняя прогулка по Marina Village — бутики, кафе, набережная</li>
  </ul>
</div>

<!-- ДЕНЬ 7 -->
<div class="day-section" id="d7">
  <div class="day-hdr">
    <div class="day-circle">7</div>
    <div class="day-title-block">
      <h2>Луштица → Porto Montenegro</h2>
      <div class="tags"><span class="tag amber">Финальный день</span><span class="tag">Выселение ~9:00</span></div>
    </div>
  </div>
  <div class="badges">
    <div class="badge"><span class="ico">⛵</span> Переход: <strong>~15 морских миль</strong></div>
    <div class="badge"><span class="ico">⏱</span> Ходовое время: <strong>~3–5 часов</strong></div>
    <div class="badge"><span class="ico">🏁</span> Выселение: <strong>до 9:00 в субботу</strong></div>
  </div>
  <div class="note">🦪 По пути — устричные фермы залива (42°29.1'N, 18°44.5'E). Свежие мидии и устрицы прямо с воды — идеальный прощальный перекус на борту.</div>

  <div class="sec-label">Марина (возврат)</div>
  <div class="marina-card">
    <div class="marina-top">
      <div class="marina-name">Porto Montenegro — финальная швартовка</div>
      <div class="vhf-badge">VHF 71</div>
    </div>
    <div class="marina-body">
      <div class="md-row">📞 <b>+382 32 661 061</b></div>
      <div class="md-row">🕐 Выселение: <b>до 9:00 в субботу</b></div>
      <div class="md-row">🚿 Душ перед отъездом: <b>есть в марине</b></div>
      <div class="md-row">✈️ До аэропорта Тиват: <b>10 мин такси</b></div>
    </div>
  </div>

  <div class="sec-label">Прощальный обед</div>
  <div class="resto-list">
    <div class="resto-item">
      <div class="resto-num">1</div>
      <div>
        <div class="resto-name"><a href="https://maps.app.goo.gl/vJLNf1UqCwxBCjBN7" target="_blank">Konoba Portun — Dobrota</a></div>
        <div class="resto-desc">На набережной Которского залива. Лучший seafood в расслабленной атмосфере. Идеально для финального обеда перед отлётом.</div>
      </div>
    </div>
    <div class="resto-item">
      <div class="resto-num">2</div>
      <div>
        <div class="resto-name"><a href="https://maps.app.goo.gl/Vc2n3p2FdRERRFpD7" target="_blank">One Restaurant Porto Montenegro</a></div>
        <div class="resto-desc">Финальный ужин в шаговой доступности от марины. Морепродукты, хорошая карта вин, вид на яхты.</div>
      </div>
    </div>
  </div>

  <div class="sec-label">Программа последнего дня</div>
  <ul class="act-list">
    <li><span class="act-ico">🌅</span>Ранний выход из Луштицы — утренний залив без туристов</li>
    <li><span class="act-ico">🦪</span>Остановка на устричной ферме — мидии и устрицы прямо с воды</li>
    <li><span class="act-ico">⛵</span>Неспешный переход — последний раз под парусами по Которскому заливу</li>
    <li><span class="act-ico">🛍</span>Шопинг в Porto Montenegro Village перед отлётом</li>
    <li><span class="act-ico">📸</span>Финальные фото с яхты перед выселением</li>
  </ul>
  <div class="note">⛵ Спасибо за путешествие с Силой Ветра! Оставьте отзыв о поездке и капитанах — нам важно ваше мнение.</div>
</div>

<!-- СВОДКА -->
<div class="day-section" id="d8">
  <div class="day-hdr">
    <div class="day-circle" style="font-size:16px">📋</div>
    <div class="day-title-block">
      <h2>Сводка по маршруту</h2>
      <div class="tags"><span class="tag">Все марины и VHF</span></div>
    </div>
  </div>

  <table class="summary-table">
    <thead>
      <tr>
        <th>День</th>
        <th>Маршрут</th>
        <th>Миль / часов</th>
        <th>Марина</th>
        <th>VHF</th>
        <th>Телефон</th>
        <th>Стоянка (~12 м)</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>1</td>
        <td>Тиват — старт</td>
        <td>—</td>
        <td>Porto Montenegro</td>
        <td><span class="vhf-pill">71</span></td>
        <td>+382 32 661 061</td>
        <td>€55–80</td>
      </tr>
      <tr>
        <td>2</td>
        <td>Тиват → Котор</td>
        <td>~10 / ~2.5ч</td>
        <td>Port of Kotor</td>
        <td><span class="vhf-pill">17/16</span></td>
        <td>+382 32 325 573</td>
        <td>€40–70</td>
      </tr>
      <tr>
        <td>3</td>
        <td>Котор → Херцег-Нови</td>
        <td>~15 / ~3.5ч</td>
        <td>Lazure Marina / Гор. марина</td>
        <td><span class="vhf-pill">звонить</span></td>
        <td>+382 69 360 571</td>
        <td>€30–90</td>
      </tr>
      <tr>
        <td>4</td>
        <td>Херцег-Нови → Бигово</td>
        <td>~15 / ~3ч</td>
        <td>Буи Grispolis / якорь</td>
        <td>—</td>
        <td>—</td>
        <td><span class="price-free">бесплатно</span></td>
      </tr>
      <tr>
        <td>5</td>
        <td>Бигово → Будва</td>
        <td>~15 / ~3.5ч</td>
        <td>Dukley Marina Budva</td>
        <td><span class="vhf-pill">8</span></td>
        <td>+382 33 453 296</td>
        <td>€80–150</td>
      </tr>
      <tr>
        <td>6</td>
        <td>Будва → Луштица</td>
        <td>~15 / ~3.5ч</td>
        <td>Marina Luštica Bay</td>
        <td><span class="vhf-pill">68</span></td>
        <td>+382 77 200 104</td>
        <td>€58–80</td>
      </tr>
      <tr>
        <td>7</td>
        <td>Луштица → Тиват</td>
        <td>~15 / ~4ч</td>
        <td>Porto Montenegro</td>
        <td><span class="vhf-pill">71</span></td>
        <td>+382 32 661 061</td>
        <td>—</td>
      </tr>
    </tbody>
  </table>

  <div class="sec-label" style="margin-top:2rem">Полезные контакты и ссылки</div>
  <div class="marina-card">
    <div class="marina-body">
      <div class="md-row">🌦 Прогноз погоды: <b><a href="https://meteo.hr/prognoze_e.php?section=prognoze_specp&param=jadran" target="_blank">meteo.hr — Адриатика</a></b></div>
      <div class="md-row">🗺 Карта маршрута: <b><a href="https://www.google.com/maps/d/u/0/edit?mid=1HnqdljgLLVhDIB8YScIfHew2JvuYGao" target="_blank">Google Maps · Черногория</a></b></div>
      <div class="md-row">📻 VTS Черногории: <b>каналы 11 и 16</b></div>
      <div class="md-row">⚡ Скорость: <b>10 уз в заливе, 6 уз в проливах Кумбор и Вериге</b></div>
      <div class="md-row">🛂 Таможня: <b>Porto Montenegro, VHF 71 (круглосуточно)</b></div>
      <div class="md-row">⛽ Заправка Тиват: <b>+382 32 661 096 · bunkering@portomontenegro.com</b></div>
    </div>
  </div>

  <div class="note amber" style="margin-top:1rem">⚠️ Все цены на стоянку ориентировочные для высокого сезона (июнь–сентябрь). Уточняйте актуальные тарифы напрямую в маринах перед выходом.</div>
</div>

</div><!-- /main -->

<footer>
  Составлено для <strong>Сила Ветра</strong> · Черногория · 7 дней, ~85 морских миль<br>
  <a href="https://www.google.com/maps/d/u/0/edit?mid=1HnqdljgLLVhDIB8YScIfHew2JvuYGao" target="_blank">Карта маршрута на Google Maps</a>
</footer>

<script>
function sw(n) {
  document.querySelectorAll('.day-section').forEach(function(d){ d.classList.remove('vis'); });
  document.querySelectorAll('.dnb').forEach(function(b){ b.classList.remove('on'); });
  document.getElementById('d'+n).classList.add('vis');
  document.querySelectorAll('.dnb')[n-1].classList.add('on');
  window.scrollTo({top: 0, behavior: 'smooth'});
}
</script>
</body>
</html>
