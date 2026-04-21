<!DOCTYPE html>
<html lang="mn">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0">
<title>Манзушир хийд · Manzushir Monastery</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Noto+Serif:ital,wght@0,400;0,600;1,400&family=Noto+Sans+JP:wght@300;400;500&family=Noto+Sans+KR:wght@300;400;500&family=Noto+Sans+SC:wght@300;400;500&display=swap" rel="stylesheet">
<style>
:root {
  --gold: #C9A84C;
  --gold-light: #E8C97A;
  --dark: #0F0D09;
  --stone: #2A2620;
  --warm: #1A1612;
  --cream: #F5EDD8;
  --muted: #9A8E7A;
  --red: #8B2020;
}

* { box-sizing: border-box; margin: 0; padding: 0; }

body {
  background: var(--dark);
  color: var(--cream);
  font-family: 'Noto Serif', Georgia, serif;
  min-height: 100vh;
  overflow-x: hidden;
}

/* ── LANG SELECTOR ── */
.lang-bar {
  position: fixed;
  top: 0; left: 0; right: 0;
  z-index: 100;
  background: rgba(15,13,9,0.92);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid rgba(201,168,76,0.2);
  display: flex;
  justify-content: center;
  gap: 4px;
  padding: 10px 16px;
}

.lang-btn {
  background: transparent;
  border: 1px solid rgba(201,168,76,0.25);
  border-radius: 6px;
  color: var(--muted);
  font-size: 12px;
  font-family: inherit;
  padding: 6px 12px;
  cursor: pointer;
  transition: all 0.2s;
  white-space: nowrap;
}
.lang-btn:hover { border-color: var(--gold); color: var(--gold-light); }
.lang-btn.active {
  background: var(--gold);
  border-color: var(--gold);
  color: var(--dark);
  font-weight: 600;
}

/* ── HERO ── */
.hero {
  margin-top: 52px;
  position: relative;
  height: 60vw;
  max-height: 420px;
  min-height: 260px;
  overflow: hidden;
}

.hero-gallery {
  display: flex;
  height: 100%;
  transition: transform 0.6s cubic-bezier(0.4,0,0.2,1);
}

.hero-slide {
  min-width: 100%;
  height: 100%;
  position: relative;
  overflow: hidden;
}

.hero-slide img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}

.hero-slide.historic img {
  filter: sepia(0.8) contrast(1.1) brightness(0.85);
}

.slide-label {
  position: absolute;
  bottom: 12px;
  left: 14px;
  background: rgba(15,13,9,0.75);
  border: 1px solid rgba(201,168,76,0.35);
  border-radius: 4px;
  padding: 4px 10px;
  font-size: 11px;
  letter-spacing: 0.08em;
  color: var(--gold-light);
}

.hero-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(to bottom, transparent 40%, rgba(15,13,9,0.85) 100%);
  pointer-events: none;
}

.hero-nav {
  position: absolute;
  bottom: 14px;
  right: 14px;
  display: flex;
  gap: 6px;
}

.hero-dot {
  width: 6px; height: 6px;
  border-radius: 50%;
  background: rgba(201,168,76,0.35);
  border: none;
  cursor: pointer;
  transition: all 0.2s;
  padding: 0;
}
.hero-dot.active { background: var(--gold); transform: scale(1.3); }

.hero-arrows {
  position: absolute;
  top: 50%; transform: translateY(-50%);
  width: 100%;
  display: flex;
  justify-content: space-between;
  padding: 0 10px;
  pointer-events: none;
}
.hero-arrow {
  pointer-events: all;
  background: rgba(15,13,9,0.5);
  border: 1px solid rgba(201,168,76,0.3);
  border-radius: 50%;
  width: 36px; height: 36px;
  color: var(--gold-light);
  font-size: 16px;
  cursor: pointer;
  display: flex; align-items: center; justify-content: center;
  transition: all 0.2s;
}
.hero-arrow:hover { background: rgba(201,168,76,0.2); }

/* ── TITLE BLOCK ── */
.title-block {
  background: var(--warm);
  border-bottom: 1px solid rgba(201,168,76,0.15);
  padding: 24px 20px 20px;
  text-align: center;
}

.ornament {
  color: var(--gold);
  font-size: 18px;
  letter-spacing: 6px;
  margin-bottom: 10px;
  display: block;
}

.main-title {
  font-size: clamp(22px, 6vw, 32px);
  font-weight: 600;
  color: var(--cream);
  line-height: 1.2;
  letter-spacing: 0.02em;
  margin-bottom: 6px;
}

.sub-title {
  font-size: 13px;
  color: var(--gold);
  letter-spacing: 0.12em;
  font-style: italic;
}

.established {
  display: inline-block;
  margin-top: 12px;
  padding: 4px 14px;
  border: 1px solid rgba(201,168,76,0.3);
  border-radius: 20px;
  font-size: 11px;
  color: var(--muted);
  letter-spacing: 0.1em;
}

/* ── AUDIO PLAYER ── */
.audio-section {
  background: var(--stone);
  padding: 16px 20px;
  display: flex;
  align-items: center;
  gap: 14px;
  border-bottom: 1px solid rgba(201,168,76,0.1);
}

.audio-icon {
  width: 44px; height: 44px;
  border-radius: 50%;
  border: 1.5px solid var(--gold);
  display: flex; align-items: center; justify-content: center;
  font-size: 18px;
  cursor: pointer;
  transition: all 0.2s;
  flex-shrink: 0;
  background: transparent;
  color: var(--gold);
}
.audio-icon:hover { background: rgba(201,168,76,0.12); }
.audio-icon.playing {
  background: var(--gold);
  color: var(--dark);
}

.audio-info { flex: 1; min-width: 0; }
.audio-label { font-size: 12px; color: var(--muted); margin-bottom: 2px; letter-spacing: 0.05em; }
.audio-progress {
  height: 3px;
  background: rgba(201,168,76,0.15);
  border-radius: 3px;
  overflow: hidden;
}
.audio-bar {
  height: 100%;
  background: var(--gold);
  width: 0%;
  transition: width 0.3s;
  border-radius: 3px;
}

.audio-stop {
  background: transparent;
  border: 1px solid rgba(201,168,76,0.25);
  border-radius: 6px;
  color: var(--muted);
  font-size: 11px;
  padding: 5px 10px;
  cursor: pointer;
  transition: all 0.2s;
  white-space: nowrap;
}
.audio-stop:hover { border-color: var(--red); color: #cc6666; }

/* ── CONTENT ── */
.content-body {
  padding: 28px 20px;
  max-width: 680px;
  margin: 0 auto;
}

.section {
  margin-bottom: 28px;
  animation: fadeUp 0.5s ease both;
}

@keyframes fadeUp {
  from { opacity: 0; transform: translateY(16px); }
  to   { opacity: 1; transform: translateY(0); }
}

.section-label {
  font-size: 10px;
  letter-spacing: 0.18em;
  color: var(--gold);
  text-transform: uppercase;
  margin-bottom: 10px;
  display: flex;
  align-items: center;
  gap: 8px;
}
.section-label::after {
  content: '';
  flex: 1;
  height: 1px;
  background: rgba(201,168,76,0.2);
}

.section-text {
  font-size: 15px;
  line-height: 1.85;
  color: #D8CEBA;
}

.highlight-box {
  border-left: 2px solid var(--gold);
  padding: 10px 16px;
  background: rgba(201,168,76,0.06);
  border-radius: 0 6px 6px 0;
  margin: 16px 0;
  font-size: 14px;
  color: var(--gold-light);
  font-style: italic;
  line-height: 1.7;
}

.facts-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 10px;
  margin-top: 14px;
}

.fact-card {
  background: rgba(201,168,76,0.05);
  border: 1px solid rgba(201,168,76,0.15);
  border-radius: 8px;
  padding: 14px;
  text-align: center;
}
.fact-num {
  font-size: 24px;
  font-weight: 600;
  color: var(--gold);
  display: block;
  margin-bottom: 4px;
}
.fact-lbl {
  font-size: 11px;
  color: var(--muted);
  line-height: 1.4;
}

/* ── DIVIDER ── */
.gold-divider {
  text-align: center;
  color: var(--gold);
  font-size: 14px;
  letter-spacing: 8px;
  margin: 6px 0 28px;
  opacity: 0.5;
}

/* ── FOOTER ── */
.footer {
  background: var(--warm);
  border-top: 1px solid rgba(201,168,76,0.15);
  padding: 20px;
  text-align: center;
}
.footer p { font-size: 11px; color: var(--muted); line-height: 1.8; }
.footer a { color: var(--gold); text-decoration: none; }

/* ── LANG SPECIFIC FONTS ── */
[data-lang="ja"] .section-text,
[data-lang="ja"] .main-title { font-family: 'Noto Sans JP', sans-serif; }
[data-lang="ko"] .section-text,
[data-lang="ko"] .main-title { font-family: 'Noto Sans KR', sans-serif; }
[data-lang="zh"] .section-text,
[data-lang="zh"] .main-title { font-family: 'Noto Sans SC', sans-serif; }
</style>
</head>
<body>

<!-- LANG BAR -->
<div class="lang-bar">
  <button class="lang-btn active" onclick="setLang('mn')">🇲🇳 Монгол</button>
  <button class="lang-btn" onclick="setLang('en')">🇬🇧 English</button>
  <button class="lang-btn" onclick="setLang('ja')">🇯🇵 日本語</button>
  <button class="lang-btn" onclick="setLang('ko')">🇰🇷 한국어</button>
  <button class="lang-btn" onclick="setLang('zh')">🇨🇳 中文</button>
</div>

<!-- HERO GALLERY -->
<div class="hero">
  <div class="hero-gallery" id="gallery">

    <!-- Slide 1: Historic -->
    <div class="hero-slide historic">
      <!-- Replace src with your actual historic photo -->
      <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/a8/Manzushir_Khiid.jpg/1280px-Manzushir_Khiid.jpg" alt="Манзушир хийд — түүхэн зураг" onerror="this.src=''; this.parentElement.style.background='#2A2620'">
      <div class="hero-overlay"></div>
      <div class="slide-label" id="slide-label-0">1930-аад он</div>
    </div>

    <!-- Slide 2: Current -->
    <div class="hero-slide">
      <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/6d/Manzushir_monastery.jpg/1280px-Manzushir_monastery.jpg" alt="Манзушир хийд — өнөөдөр" onerror="this.src=''; this.parentElement.style.background='#1A1612'">
      <div class="hero-overlay"></div>
      <div class="slide-label" id="slide-label-1">Өнөөдөр</div>
    </div>

    <!-- Slide 3: Landscape -->
    <div class="hero-slide">
      <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/3e/Bogdkhan_uul.jpg/1280px-Bogdkhan_uul.jpg" alt="Богдхан уул" onerror="this.src=''; this.parentElement.style.background='#0F1A12'">
      <div class="hero-overlay"></div>
      <div class="slide-label" id="slide-label-2">Богдхан уул</div>
    </div>

  </div>

  <div class="hero-arrows">
    <button class="hero-arrow" onclick="prevSlide()">‹</button>
    <button class="hero-arrow" onclick="nextSlide()">›</button>
  </div>
  <div class="hero-nav" id="hero-nav"></div>
</div>

<!-- TITLE -->
<div class="title-block" data-lang="mn">
  <span class="ornament">✦ ✦ ✦</span>
  <h1 class="main-title" id="main-title">Манзушир хийд</h1>
  <p class="sub-title" id="sub-title">Богдхан уулын нандин дурсгал</p>
  <span class="established" id="established">1733 онд байгуулагдсан</span>
</div>

<!-- AUDIO -->
<div class="audio-section">
  <button class="audio-icon" id="audio-btn" onclick="toggleAudio()">▶</button>
  <div class="audio-info">
    <div class="audio-label" id="audio-label">Аудио тайлбар сонсох</div>
    <div class="audio-progress"><div class="audio-bar" id="audio-bar"></div></div>
  </div>
  <button class="audio-stop" onclick="stopAudio()">■ Зогсоох</button>
</div>

<!-- CONTENT -->
<div class="content-body" id="content-body" data-lang="mn">

  <div class="section">
    <div class="section-label" id="lbl-history">Түүх</div>
    <p class="section-text" id="txt-history">
      Богд хан уул нь Монгол Улсын түүхэн, байгалийн нөөцийн хувьд онцгой ач холбогдолтой газар бөгөөд дэлхийн анхны дархан цаазат уулын статустай 1783 оноос эхлэн хамгаалалтад авсан газар юм.Улсын төв архивын албан баримтад 12-13 дугаар зууны үед Хэрэйд аймгийн Ван хаан Тоорил Богд хан уулыг тахиж, Туулын хар шугуйгаар нутаглаж байхдаа “Унасан газар угаасан усаа” гэх монгол хүний сэтгэлээр өөрийн эрх хэмжээнд онголон дархалсан түүхтэй. Манзуширын хийдийн анхны сүмийг Манзушир ламтны анхдугаар дүрийн хувилгаан Лувсанжамбалданзан 1733 онд Богд  хан уулын энгэрт бариулснаар Манзуширын хийдийн суурь тавигджээ.   200 гаруй жилийн түүхтэй Манзуширын хийдийг 1937 онд нураан буулгах үед 21 барилга байгууламжтай байжээ. Хийдийн сүүлчийн хутагт Цэрэндорж тэргүүтэй нэр бүхий 50 гаруй ламыг баривчлан 1937 онд цаазалжээ.
    </p>
    <div class="highlight-box" id="txt-quote">
      "Тухайг үедээ 20 дуган, 300 гаруй лам нартай, хийд нь шашин, соёл, боловсролын томоохон төв байсан."
    </div>
    <p class="section-text" id="txt-history2">
      1937 онд социалист засгийн газрын үед хийдийг бүрэн устгаж, ихэнх лам нарыг цаазалж эсвэл хилс хэрэгт буруутган шоронд хорьжээ. Зөвхөн нэг дуган болон музей хэлбэрт хадгалагдаж үлдсэн.
    </p>
  </div>

  <div class="facts-grid">
    <div class="fact-card">
      <span class="fact-num">1733</span>
      <span class="fact-lbl" id="fact1-lbl">Байгуулагдсан он</span>
    </div>
    <div class="fact-card">
      <span class="fact-num">300+</span>
      <span class="fact-lbl" id="fact2-lbl">Оргил үеийн лам нарын тоо</span>
    </div>
    <div class="fact-card">
      <span class="fact-num">20</span>
      <span class="fact-lbl" id="fact3-lbl">Дуганы тоо</span>
    </div>
    <div class="fact-card">
      <span class="fact-num">1990</span>
      <span class="fact-lbl" id="fact4-lbl">Сэргээн засварлалт эхэлсэн он</span>
    </div>
  </div>

  <div class="gold-divider">· · ·</div>

  <div class="section">
    <div class="section-label" id="lbl-location">Нэрний учир</div>
    <p class="section-text" id="txt-location">
      Богд хан уулын магтаалд “Өвөр талдаа хийдтэй, Өргөн их шажинтай, Махгалын шүтээнтэй, Манзушир ламын хийдтэй” хэмээн магтан дуулдаг. Манзушир гэдэг нь “Оюун билгийн тэнгэрийг сахих бурхан” гэсэн утгатай. “Манзуширын хувилгаан” НТӨ II зуунд Жагар орноо тодорч, түүнээс хойш Энэтхэгт хоёр, Төвдөд найм, Монгол таван удаа тодрон залгамжлагдсан түүхтэй. 
    </p>
  </div>

  <div class="section">
    <div class="section-label" id="lbl-today">Одоо</div>
    <p class="section-text" id="txt-today">
      Өнөөдөр Манзушир хийд нь музей болон шашны хэлбэрээр үйл ажиллагаа явуулж байна. Жил бүр мянга мянган жуулчин, сүсэгтэн зорин ирдэг. Хийдийн музейд буддын урлагийн олдвор, түүхэн гэрэл зургууд хадгалагдаж байна.
    </p>
  </div>

</div>

<div class="footer">
  <p id="footer-text">© Манзушир хийдийн дижитал мэдээлэл · Богдхан уул, Монгол улс</p>
</div>

<script>
// ─── CONTENT DATA ───────────────────────────────────────────────
const LANG = {
  mn: {
    htmlLang: 'mn',
    mainTitle: 'Манзушир хийд',
    subTitle: 'Богдхан уулын түүх соёлын хосломол өв',
    established: '1733 онд байгуулагдсан',
    audioLabel: 'Аудио тайлбар сонсох',
    audioLang: null, // MP3 файл ашиглана → audio/mn.mp3
    audioSrc: 'audio/mn.mp3  ',
    lblHistory: 'Түүх',
    txtHistory: 'Манзушир хийд нь 1733 онд Богдхан уулын өвөрт байгуулагдсан бөгөөд Монголын буддын шашны хамгийн нэр хүндтэй хийдүүдийн нэг байв. Хийдийн нэр нь мэргэн ухааны Бурхан болох Манзушрийн нэрнээс гаралтай.',
    txtQuote: '"Оргил үедээ 20 дуган, 300 гаруй лам нартай, хийд нь шашин, соёл, боловсролын томоохон төв байсан."',
    txtHistory2: '1937 онд социалист засгийн газрын хавчлагын үед хийдийг бүрэн устгаж, ихэнх лам нарыг цаазалж эсвэл хилс хэрэгт буруутган шоронд хорьжээ. Зөвхөн нэг дуган болон музей хэлбэрт хадгалагдаж үлдсэн.',
    fact1: 'Байгуулагдсан он', fact2: 'Оргил үеийн лам нарын тоо', fact3: 'Дуганы тоо', fact4: 'Сэргээн засварлалт эхэлсэн он',
    lblLocation: 'Байршил',
    txtLocation: 'Хийд нь Улаанбаатараас баруун өмнө зүгт 42 км зайд, Богдхан уулын байгалийн цогцолборт газрын хойд хэсэгт оршдог. Өндөр ногоон ой, уулын гоо сайхан хүрээлэгдсэн энэ газар нь жуулчдад байгаль үзэх, тайван амрах боломж олгодог.',
    lblToday: 'Өнөөдөр',
    txtToday: 'Өнөөдөр Манзушир хийд нь музей болон шашны газар хэлбэрээр үйл ажиллагаа явуулж байна. Жил бүр мянга мянган жуулчин, сүсэгтэн энд зорчдог. Хийдийн музейд буддын урлагийн олдвор, түүхэн гэрэл зургууд хадгалагдаж байна.',
    footer: '© Манзушир хийдийн дижитал мэдээлэл · Богдхан уул, Монгол улс',
    slideLabels: ['1930-аад он', 'Өнөөдөр', 'Богдхан уул'],
    stopBtn: '■ Зогсоох',
  },
  en: {
    htmlLang: 'en',
    mainTitle: 'Manzushir Monastery',
    subTitle: 'Sacred Heritage of Bogdkhan Mountain',
    established: 'Founded in 1733',
    audioLabel: 'Listen to audio guide',
    audioLang: 'en-US',
    audioSrc: null,
    lblHistory: 'History',
    txtHistory: 'Manzushir Monastery was founded in 1733 at the foot of Bogdkhan Mountain and became one of the most important Buddhist monasteries in Mongolia. Its name derives from Mañjuśrī, the Bodhisattva of wisdom.',
    txtQuote: '"At its peak, the monastery housed over 300 monks across 20 temples, serving as a major center of religion, culture, and education."',
    txtHistory2: 'In 1937, during the Stalinist purges, the monastery was completely destroyed and most of its monks were executed or imprisoned on false charges. Only one temple survived, preserved as a museum.',
    fact1: 'Year founded', fact2: 'Monks at peak', fact3: 'Temples', fact4: 'Restoration began',
    lblLocation: 'Location',
    txtLocation: 'The monastery is located 42 km southwest of Ulaanbaatar, in the northern section of the Bogdkhan Mountain Natural Reserve. Surrounded by dense forest and mountain scenery, it offers visitors a peaceful retreat into nature.',
    lblToday: 'Today',
    txtToday: 'Today, Manzushir functions as both a museum and an active religious site. Thousands of tourists and pilgrims visit each year. The museum preserves Buddhist art, historical artifacts, and photographs from the monastery\'s past.',
    footer: '© Manzushir Monastery Digital Guide · Bogdkhan Mountain, Mongolia',
    slideLabels: ['1930s — Historic', 'Present Day', 'Bogdkhan Mountain'],
    stopBtn: '■ Stop',
  },
  ja: {
    htmlLang: 'ja',
    mainTitle: 'マンズシル寺院',
    subTitle: 'ボグドハーン山の聖なる遺産',
    established: '1733年創建',
    audioLabel: '音声ガイドを聴く',
    audioLang: 'ja-JP',
    audioSrc: null,
    lblHistory: '歴史',
    txtHistory: 'マンズシル寺院は1733年にボグドハーン山のふもとに創建され、モンゴル仏教の最も重要な寺院のひとつとなりました。寺院の名前は知恵の菩薩・文殊菩薩（マンジュシュリー）に由来しています。',
    txtQuote: '「最盛期には20の寺殿に300人以上の僧侶が暮らし、宗教・文化・教育の重要な中心地として栄えました。」',
    txtHistory2: '1937年、スターリン主義の粛清の中で寺院は完全に破壊され、多くの僧侶が処刑または投獄されました。一つの仏殿のみが博物館として保存されています。',
    fact1: '創建年', fact2: '最盛期の僧侶数', fact3: '寺殿の数', fact4: '修復開始年',
    lblLocation: '場所',
    txtLocation: 'ウランバートルから南西42kmに位置し、ボグドハーン山自然保護区の北部にあります。深い森と山の景色に囲まれ、静かな自然の中での参拝と休息が楽しめます。',
    lblToday: '現在',
    txtToday: '現在、マンズシルは博物館と宗教施設として運営されています。毎年数千人の観光客と巡礼者が訪れます。博物館には仏教美術品、歴史的遺物、当時の写真が保管されています。',
    footer: '© マンズシル寺院デジタルガイド · ボグドハーン山、モンゴル',
    slideLabels: ['1930年代 — 歴史的写真', '現在の姿', 'ボグドハーン山'],
    stopBtn: '■ 停止',
  },
  ko: {
    htmlLang: 'ko',
    mainTitle: '만주시르 사원',
    subTitle: '복드한 산의 신성한 유산',
    established: '1733년 설립',
    audioLabel: '오디오 가이드 듣기',
    audioLang: 'ko-KR',
    audioSrc: null,
    lblHistory: '역사',
    txtHistory: '만주시르 사원은 1733년 복드한 산 기슭에 세워졌으며, 몽골 불교에서 가장 중요한 사원 중 하나가 되었습니다. 사원의 이름은 지혜의 보살인 문수보살(만주슈리)에서 유래했습니다.',
    txtQuote: '"전성기에는 20개의 법당에 300명 이상의 승려가 거주하며 종교, 문화, 교육의 주요 중심지로 번성했습니다."',
    txtHistory2: '1937년 스탈린주의 탄압 기간에 사원은 완전히 파괴되었고 대부분의 승려들이 처형되거나 투옥되었습니다. 단 하나의 법당만이 박물관으로 보존되어 남아 있습니다.',
    fact1: '설립 연도', fact2: '전성기 승려 수', fact3: '법당 수', fact4: '복원 시작 연도',
    lblLocation: '위치',
    txtLocation: '사원은 울란바토르에서 남서쪽으로 42km 떨어진 복드한 산 자연보호구역 북쪽에 위치합니다. 울창한 숲과 아름다운 산세에 둘러싸여 자연 속에서 평화로운 시간을 보낼 수 있습니다.',
    lblToday: '현재',
    txtToday: '현재 만주시르는 박물관과 종교 시설로 운영되고 있습니다. 매년 수천 명의 관광객과 순례자가 방문합니다. 박물관에는 불교 예술품, 역사적 유물, 사원의 과거 사진이 보관되어 있습니다.',
    footer: '© 만주시르 사원 디지털 가이드 · 복드한 산, 몽골',
    slideLabels: ['1930년대 — 역사 사진', '현재 모습', '복드한 산'],
    stopBtn: '■ 정지',
  },
  zh: {
    htmlLang: 'zh',
    mainTitle: '满珠希礼寺',
    subTitle: '博格达汗山的神圣遗产',
    established: '建于1733年',
    audioLabel: '收听语音导览',
    audioLang: 'zh-CN',
    audioSrc: null,
    lblHistory: '历史',
    txtHistory: '满珠希礼寺建于1733年，坐落于博格达汗山脚下，是蒙古最重要的佛教寺院之一。寺院名称来源于智慧菩萨文殊菩萨（曼殊室利）。',
    txtQuote: '"鼎盛时期，寺院拥有20座庙宇和300余名喇嘛，是宗教、文化和教育的重要中心。"',
    txtHistory2: '1937年，在斯大林主义镇压期间，寺院被彻底摧毁，大多数喇嘛遭到处决或以莫须有的罪名入狱。仅有一座庙宇作为博物馆保存至今。',
    fact1: '建立年份', fact2: '鼎盛期喇嘛人数', fact3: '庙宇数量', fact4: '修复开始年份',
    lblLocation: '地理位置',
    txtLocation: '寺院位于乌兰巴托西南42公里处，坐落于博格达汗山自然保护区北部。四周被茂密森林和秀美山景环绕，为游客提供亲近自然、宁静休憩的好去处。',
    lblToday: '今日现状',
    txtToday: '如今，满珠希礼寺作为博物馆和宗教场所运营。每年有数千名游客和朝圣者前来参观。博物馆收藏着佛教艺术品、历史文物和寺院昔日的珍贵照片。',
    footer: '© 满珠希礼寺数字导览 · 博格达汗山，蒙古国',
    slideLabels: ['1930年代 — 历史照片', '现状', '博格达汗山'],
    stopBtn: '■ 停止',
  }
};

// ─── GALLERY ────────────────────────────────────────────────────
let currentSlide = 0;
const totalSlides = 3;
let autoTimer;

function buildDots() {
  const nav = document.getElementById('hero-nav');
  for (let i = 0; i < totalSlides; i++) {
    const d = document.createElement('button');
    d.className = 'hero-dot' + (i === 0 ? ' active' : '');
    d.onclick = () => goSlide(i);
    nav.appendChild(d);
  }
}

function goSlide(n) {
  currentSlide = (n + totalSlides) % totalSlides;
  document.getElementById('gallery').style.transform = `translateX(-${currentSlide * 100}%)`;
  document.querySelectorAll('.hero-dot').forEach((d, i) => d.classList.toggle('active', i === currentSlide));
  updateSlideLabels();
  clearTimeout(autoTimer);
  autoTimer = setTimeout(nextSlide, 4500);
}

function nextSlide() { goSlide(currentSlide + 1); }
function prevSlide() { goSlide(currentSlide - 1); }

function updateSlideLabels() {
  const labels = LANG[currentLang].slideLabels;
  labels.forEach((lbl, i) => {
    const el = document.getElementById('slide-label-' + i);
    if (el) el.textContent = lbl;
  });
}

buildDots();
autoTimer = setTimeout(nextSlide, 4500);

// ─── LANGUAGE ───────────────────────────────────────────────────
let currentLang = 'mn';

function setLang(lang) {
  stopAudio();
  currentLang = lang;
  const d = LANG[lang];
  document.documentElement.lang = d.htmlLang;

  document.querySelectorAll('.lang-btn').forEach(b => b.classList.remove('active'));
  document.querySelector(`.lang-btn[onclick="setLang('${lang}')"]`).classList.add('active');

  document.getElementById('main-title').textContent   = d.mainTitle;
  document.getElementById('sub-title').textContent    = d.subTitle;
  document.getElementById('established').textContent  = d.established;
  document.getElementById('audio-label').textContent  = d.audioLabel;
  document.getElementById('lbl-history').childNodes[0].textContent = d.lblHistory + ' ';
  document.getElementById('txt-history').textContent  = d.txtHistory;
  document.getElementById('txt-quote').textContent    = d.txtQuote;
  document.getElementById('txt-history2').textContent = d.txtHistory2;
  document.getElementById('fact1-lbl').textContent    = d.fact1;
  document.getElementById('fact2-lbl').textContent    = d.fact2;
  document.getElementById('fact3-lbl').textContent    = d.fact3;
  document.getElementById('fact4-lbl').textContent    = d.fact4;
  document.getElementById('lbl-location').childNodes[0].textContent = d.lblLocation + ' ';
  document.getElementById('txt-location').textContent = d.txtLocation;
  document.getElementById('lbl-today').childNodes[0].textContent = d.lblToday + ' ';
  document.getElementById('txt-today').textContent    = d.txtToday;
  document.getElementById('footer-text').textContent  = d.footer;
  document.getElementById('content-body').dataset.lang = lang;
  document.querySelector('.title-block').dataset.lang  = lang;
  document.querySelector('.audio-stop').textContent    = d.stopBtn;

  updateSlideLabels();

  // Re-animate
  document.querySelectorAll('.section').forEach((s, i) => {
    s.style.animation = 'none';
    setTimeout(() => { s.style.animation = `fadeUp 0.5s ease ${i * 0.08}s both`; }, 10);
  });
}

// ─── AUDIO ──────────────────────────────────────────────────────
let audioEl = null;
let synth = window.speechSynthesis;
let isPlaying = false;
let progressTimer = null;

function toggleAudio() {
  if (isPlaying) { stopAudio(); return; }
  const d = LANG[currentLang];
  const btn = document.getElementById('audio-btn');

  stopAudio();

  if (d.audioSrc) {
    // MP3 file (Mongolian)
    audioEl = new Audio(d.audioSrc);
    audioEl.addEventListener('timeupdate', () => {
      if (audioEl.duration) {
        document.getElementById('audio-bar').style.width = (audioEl.currentTime / audioEl.duration * 100) + '%';
      }
    });
    audioEl.addEventListener('ended', () => { isPlaying = false; btn.textContent = '▶'; btn.classList.remove('playing'); document.getElementById('audio-bar').style.width = '0%'; });
    audioEl.play().catch(() => {
      // Fallback to speech if file missing
      speakText(d.txtHistory + ' ' + d.txtHistory2 + ' ' + d.txtLocation + ' ' + d.txtToday, 'mn-MN');
    });
  } else {
    // Web Speech API
    const text = d.txtHistory + ' ' + d.txtHistory2 + ' ' + d.txtLocation + ' ' + d.txtToday;
    speakText(text, d.audioLang);
  }

  isPlaying = true;
  btn.textContent = '■';
  btn.classList.add('playing');
}

function speakText(text, lang) {
  if (!synth) return;
  const utt = new SpeechSynthesisUtterance(text);
  utt.lang = lang;
  utt.rate = 0.88;
  utt.pitch = 1;

  let startTime = Date.now();
  const estDuration = text.length * 60; // rough estimate ms

  progressTimer = setInterval(() => {
    const pct = Math.min(99, (Date.now() - startTime) / estDuration * 100);
    document.getElementById('audio-bar').style.width = pct + '%';
  }, 300);

  utt.onend = () => {
    clearInterval(progressTimer);
    isPlaying = false;
    document.getElementById('audio-btn').textContent = '▶';
    document.getElementById('audio-btn').classList.remove('playing');
    document.getElementById('audio-bar').style.width = '0%';
  };
  synth.speak(utt);
}

function stopAudio() {
  if (audioEl) { audioEl.pause(); audioEl.currentTime = 0; audioEl = null; }
  if (synth) synth.cancel();
  clearInterval(progressTimer);
  isPlaying = false;
  document.getElementById('audio-btn').textContent = '▶';
  document.getElementById('audio-btn').classList.remove('playing');
  document.getElementById('audio-bar').style.width = '0%';
}
</script>
</body>
</html>