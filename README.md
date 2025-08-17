# FF-news-
Ye Hai aapka apna saathi 
<!doctype html>
<html lang="hi">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>FF NEWS – ब्रेकिंग</title>
<style>
  :root {
    --size: 1080px;
    --pad: 24px;
    --font: system-ui, -apple-system, Segoe UI, Roboto, Arial, Noto Sans, "Nirmala UI", sans-serif;
    --red: #d90429;
    --red-dark: #a0031f;
    --yellow: #ffc400;
    --yellow-dark: #d7a700;
    --white: #ffffff;
  }

  html, body { margin: 0; padding: 0; background: #111; font-family: var(--font); }
  body {
    width: var(--size); height: var(--size); margin: 0 auto; position: relative; overflow: hidden;
    box-shadow: 0 0 0 2px #000 inset;
    background:
      radial-gradient(120% 80% at 10% 0%, #1c3b83 0%, #0a1a3d 50%, #020611 100%),
      linear-gradient(135deg, #00122c 0%, #001a45 60%, #020611 100%);
  }

  .light { position: absolute; inset: 0;
    background:
      radial-gradient(40% 20% at 80% 10%, rgba(255,255,255,0.08), rgba(255,255,255,0) 60%),
      radial-gradient(20% 12% at 20% 0%, rgba(255,255,255,0.06), rgba(255,255,255,0) 60%);
    pointer-events: none;
  }

  /* Welcome Page */
  .welcome {
    position: absolute; inset: 0;
    display: grid;
    place-items: center;
    background: radial-gradient(circle at center, #111 0%, #000 100%);
    color: #ffffff;
    text-align: center;
    z-index: 100;
    opacity: 0;
    transform: scale(0.9);
    animation: welcomeIn 1.2s forwards;
    padding: 0 40px;
    line-height: 1.4;
  }

  .main-title {
    font-size: 54px;
    font-weight: 900;
    color: #ffcc00;
    text-shadow: 2px 2px 5px rgba(0,0,0,0.5);
  }

  .news-text {
    margin-top: 20px;
    font-size: 28px;
    font-weight: 600;
    color: #f2f2f2;
    background: rgba(255,255,255,0.05);
    padding: 15px 20px;
    border-left: 6px solid #ff5733;
    text-align: left;
    max-width: 900px;
    border-radius: 6px;
  }

  .birthday-highlight {
    margin-top: 25px;
    font-size: 36px;
    font-weight: 900;
    background: linear-gradient(90deg, #ffcc00, #ff5733, #33ff57, #3357ff);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    text-shadow: 1px 1px 3px rgba(0,0,0,0.5);
    animation: blinkHighlight 1.5s infinite;
  }

  @keyframes welcomeIn {
    0% { opacity: 0; transform: scale(0.9); }
    100% { opacity: 1; transform: scale(1); }
  }

  @keyframes blinkHighlight {
    0%,50%,100% {opacity:1;}
    25%,75% {opacity:0.5;}
  }

  /* Top bar */
  .topbar {
    position: absolute; left: 0; top: 0; right: 0; height: 120px;
    background: linear-gradient(180deg, var(--red) 0%, var(--red-dark) 100%);
    display: flex; align-items: center; padding: 0 var(--pad);
    box-shadow: 0 4px 0 rgba(0,0,0,0.35);
  }
  .topbar .label {
    display: inline-flex; align-items: center; gap: 12px;
    font-weight: 900; color: var(--white); text-transform: uppercase; letter-spacing: 1px;
    font-size: 44px; padding: 10px 18px;
    background: linear-gradient(180deg, #ff3147 0%, #b70024 100%);
    clip-path: polygon(0 0, 94% 0, 100% 50%, 94% 100%, 0 100%);
    margin-right: 18px;
  }
  .topbar .headline {
    color: var(--white); font-weight: 800; font-size: 32px; line-height: 1.2;
    text-shadow: 0 2px 0 rgba(0,0,0,0.35);
  }

  /* Logo */
  .logo {
    position: absolute; top: 140px; left: var(--pad);
    width: 220px; height: 140px;
    background: linear-gradient(135deg, #0d47a1 0%, #042a73 100%);
    border: 6px solid var(--white);
    box-shadow: 0 10px 20px rgba(0,0,0,0.35);
    display: grid; place-items: center;
  }
  .logo .ff { color: var(--white); font-size: 54px; font-weight: 900; letter-spacing: 1px; line-height: 0.9; }
  .logo .news { margin-top: -6px; font-weight: 900; font-size: 32px; color: var(--yellow); letter-spacing: 2px; }

  /* Live pill */
  .live { position: absolute; top: 160px; right: var(--pad); display: flex; align-items: center; gap: 12px; }
  .live .pill {
    background: linear-gradient(180deg, #ff4757 0%, #b30017 100%);
    color: var(--white); font-weight: 900; padding: 8px 14px; border-radius: 999px;
    letter-spacing: 1px; text-transform: uppercase;
    box-shadow: 0 0 0 3px rgba(255,255,255,0.15);
    animation: blink 1s infinite;
  }
  @keyframes blink { 0%,50%,100% {opacity:1;} 25%,75% {opacity:0.5;} }
  .live .time { color: var(--white); font-weight: 700; font-size: 26px; text-shadow: 0 2px 0 rgba(0,0,0,0.35); }

  /* Main card */
  .card {
    position: absolute; left: var(--pad); right: var(--pad); top: 300px; bottom: 280px;
    background: rgba(255,255,255,0.06); border: 1px solid rgba(255,255,255,0.2);
    backdrop-filter: blur(2px); box-shadow: inset 0 0 0 2px rgba(255,255,255,0.04);
    display: grid; padding: 20px;
  }
  .maintext { color: var(--white); display: grid; align-content: center; gap: 14px; padding-right: 10px; }
  .maintext .kicker { color: #ffbaba; font-weight: 900; letter-spacing: 1px; text-transform: uppercase; font-size: 22px; animation: blinkKicker 1s infinite; }
  @keyframes blinkKicker { 0%, 50%, 100% { opacity: 1; } 25%, 75% { opacity: 0.5; } }
  .maintext h1 { margin: 0; font-size: 38px; line-height: 1.15; font-weight: 900; text-shadow: 0 2px 0 rgba(0,0,0,0.35); }
  .maintext p { margin: 0; font-size: 26px; line-height: 1.3; font-weight: 600; color: #f2f2f2; }

  /* Yellow ticker */
  .ticker {
    position: absolute; left: 0; right: 0; height: 90px; bottom: 200px;
    background: linear-gradient(180deg, var(--yellow) 0%, var(--yellow-dark) 100%);
    display: flex; flex-direction: column; justify-content: center; padding: 0 var(--pad);
    box-shadow: 0 -4px 0 rgba(0,0,0,0.35);
  }
  .ticker .tag {
    font-weight: 900; text-transform: uppercase; background: #111; color: var(--yellow);
    padding: 10px 14px; margin-right: 14px; clip-path: polygon(0 0, 92% 0, 100% 50%, 92% 100%, 0 100%); letter-spacing: 1px;
  }
  .ticker .text { font-weight: 800; font-size: 28px; color: #111; }

  /* Bottom crawls */
  .crawl {
    position: absolute; left: 0; right: 0; bottom: 50px; height: 130px;
    background: linear-gradient(180deg, #0f0f0f 0%, #030303 100%);
    border-top: 4px solid #202020; color: var(--white);
    display: grid; grid-template-rows: 60px 1fr;
  }
  .crawl .row1 { display: flex; align-items: center; gap: 16px; padding: 0 var(--pad); }
  .crawl .row1 .brand { font-weight: 900; font-size: 28px; letter-spacing: 1px; }
  .crawl .row1 .slug { font-weight: 800; font-size: 24px; color: #c0c0c0; }
  .crawl .marquee { overflow: hidden; position: relative; border-top: 2px solid #222; height: 35px; }
  .crawl .track {
    position: absolute; white-space: nowrap; will-change: transform;
    animation: slide 28s linear infinite; font-weight: 800; font-size: 28px; padding-left: 100%;
  }
  @keyframes slide { 0% { transform: translateX(0); } 100% { transform: translateX(-100%); } }

  /* Advertisement bar */
  .adbar {
    position: absolute; left: 0; right: 0; bottom: 0; height: 50px;
    background: linear-gradient(90deg, #ffcc00 0%, #ffaa00 100%);
    border-top: 3px solid #000; overflow: hidden;
  }
  .adtrack {
    position: absolute; white-space: nowrap; will-change: transform;
    animation: adslide 20s linear infinite;
    font-weight: 900; font-size: 22px; color: #000; padding-left: 100%;
  }
  @keyframes adslide { 0% { transform: translateX(0); } 100% { transform: translateX(-100%); } }

  /* Word wrap helper */
  .wrap { word-wrap: break-word; overflow-wrap: break-word; }
</style>
</head>
<body>

<div class="light"></div>

<!-- Welcome Page -->
<div class="welcome" id="welcome">
  <div class="main-title">Welcome to Pandey FF News</div>
  <div class="news-text">
    <strong>Nikhil Bhaiya</strong> को समूह की तरफ से <strong>जन्मदिन</strong> की हार्दिक बधाई।  
    आपका योगदान सराहनीय है, खेलों में आगे बढ़ते रहें और Free Fire ग्रुप को अपना योगदान देते रहें। 🔥💪
  </div>
  <div class="news-text" style="margin-top:15px; background: rgba(255,255,255,0.03); border-left:6px solid #33ff57;">
    सभी Free Fire खिलाड़ियों को <strong>जन्माष्टमी</strong> की शुभकामनाएँ। कृष्ण लीला और खेलों का मज़ा एकसाथ! 🌸🎉
  </div>
  <div class="birthday-highlight">🎂 HAPPY BIRTHDAY! & 🌼 HAPPY JANMASHTAMI! 🎉</div>
</div>

<!-- TOP BREAKING BAR -->
<div class="topbar">
  <div class="label">ब्रेकिंग न्यूज़</div>
  <div class="headline wrap">
    आज तीन बजे से शुरू हो सकता है फ्री फायर गेम, सभी खिलाड़ी घर पर मौजूद, कुछ खिलाड़ियों को बैठना पड़ सकता है बेंच पर, पहले आओ पहले पाओ की रणनीति पर कराया जाएगा मैच।
  </div>
</div>

<!-- FF NEWS LOGO -->
<div class="logo" title="FF NEWS">
  <div class="ff">FF</div>
  <div class="news">NEWS</div>
</div>

<!-- LIVE -->
<div class="live">
  <div class="pill">LIVE</div>
  <div class="time" id="time">--:--</div>
</div>

<!-- MAIN CONTENT -->
<div class="card">
  <div class="maintext">
    <div class="kicker">BIG BREAKING</div>
    <h1 class="wrap">
      कैप्टन वैभव पांडेय और जैकी चाचा के अनुरोध पर जल्द शुरू हो सकता है आज का रोमांचक गेम।
    </h1>
    <p class="wrap">
      मुंशी बाबा स्पोर्ट क्लब में हलचल तेज़।  
      सभी खिलाड़ी मैदान में जुटे हुए हैं, और गौरव भैया की निगाहें पूरे गेम पर टिकी हुई हैं।  
      सभी उत्साहित हैं कि मैच जल्द से जल्द शुरू हो सके।  
    </p>
  </div>
</div>

<!-- YELLOW TICKER -->
<div class="ticker">
  <div class="tag">UPDATE</div>
  <div class="text wrap">वैभव वॉरियर्स ने ऋषभ सुपर किंग्स को सीरीज में 3-2 से हराया।</div>
</div>

<!-- BOTTOM CRAWLS -->
<div class="crawl">
  <div class="row1">
    <div class="brand">FF NEWS</div>
    <div class="slug">Breaking</div>
  </div>
  <div class="marquee">
    <div class="track">
      कप्तान ऋषभ पांडेय ने हार के बाद बड़ा बयान जारी किया, बताया कि इंटरनेट था हार का बड़ा कारण। 
      शाम को भी एक मैच हुआ जिसमें पाँच-पाँच खिलाड़ियों ने प्रतिभाग लिया, जिसमें वैभव वॉरियर्स की हार हुई। 
      अंश को शामिल करके कोई फायदा नहीं मिला, टीम को जीत नहीं दिला पा रहे। 
      कल समोसे ना आने के कारण बहुत सारे लोग सदमे में, आज हो सकता है बड़ा ऐलान, निखिल भैया के जन्मदिन पर मिल सकता है सभी प्लेयर को बड़ा तोहफा, मिल सकती है बड़ी पार्टी।
    </div>
  </div>
  <div class="marquee">
    <div class="track">
      जल्द हो सकता है इस महीने फ्री फायर कस्टम का अंत, आने वाले समय की परीक्षाएँ हैं मुख्य कारण। 
      इस महीने हो सकते हैं बड़े अवार्ड्स का ऐलान, Most Valuable Player बन सकते हैं Gaurav Pandey और Most Noob Player बन सकते हैं Bhole Pandey, मुख्य प्रतियोगी हैं श्री अंश, संदीप और अन्य सभी खिलाड़ी। 
      इस महीने का मोस्ट प्लेएबल प्लेयर बन सकते हैं गौरव पांडेय, लगातार खेल में अच्छा प्रदर्शन करते रहने पर मिल सकता है बड़ा इनाम। पिछले दिन गौरव पांडेय ने उत्तर प्रदेश पुलिस में उत्कृष्ट रिस्पांस टाइम बनाने का अवार्ड भी प्राप्त किया है, वैभव पांडेय ने बधाई देते हुए कहा कि आज गौरव भैया को इस खुशी में बड़ी पार्टी देनी पड़ेगी। 
      लगातार प्रदर्शन में कमी रहने के कारण वैभव पांडेय ने कल राजा पांडेय को टीम से किया बाहर, राजा पांडेय का बयान जल्द छोड़ सकते हैं टीम और बना सकते हैं अपनी नई टीम।
    </div>
  </div>
</div>

<!-- AD BAR -->
<div class="adbar">
  <div class="adtrack">
    आप Free Fire खेलते हो और kill नहीं होते? कोई बात नहीं, Vikas Chachak के भरोसे Poja Paanpukar, हर Match का MVP बनो!
    Yadav Samosa! जो खाया आज, लगाओ कल जैसा; आप Free Fire खेलते हैं, स्क्रीन रुक रही है? कोई बात नहीं, Paji Powder लगाएँ, स्क्रीन एकदम धड़कन-तड़तड़ चलेगी!
    FF News के साथ बने रहें और पाएँ अपने पसंदीदा खिलाड़ियों की लेटेस्ट खबरें और अपडेट्स!
    Free Fire में अपने कौशल को सुधारने के लिए, आज ही हमारे साथ जुड़ें और पाएँ विशेषज्ञों से सीखने का अवसर!
  </div>
</div>

<!-- MUSIC -->
<audio id="bgm" autoplay loop>
  <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
  आपका ब्राउज़र ऑडियो सपोर्ट नहीं करता।
</audio>

<script>
  // Hide welcome page after 3 seconds
  setTimeout(() => {
    const welcome = document.getElementById('welcome');
    welcome.style.transition = "opacity 1s";
    welcome.style.opacity = 0;
    setTimeout(()=>welcome.style.display="none",1000);
  }, 3000);

  // Live time
  function updateTime(){
    const t = new Date();
    const h = t.getHours().toString().padStart(2,'0');
    const m = t.getMinutes().toString().padStart(2,'0');
    document.getElementById('time').textContent = h+":"+m;
  }
  setInterval(updateTime,1000);
  updateTime();
</script>
</body>
</html>
