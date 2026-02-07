<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Sana Özelsin Balım 💖</title>
  <link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
  <script src="https://cdn.jsdelivr.net/npm/tsparticles@2.12.0/tsparticles.bundle.min.js"></script>
  <style>
    * { margin:0; padding:0; box-sizing:border-box; }
    body {
      height: 100vh;
      background: linear-gradient(135deg, #ff9a9e 0%, #fecfef 50%, #fad0c4 100%);
      font-family: 'Poppins', sans-serif;
      color: #fff;
      overflow: hidden;
      display: flex;
      justify-content: center;
      align-items: center;
      text-align: center;
    }
    #tsparticles { position: fixed; inset: 0; z-index: 1; }
    .content {
      position: relative;
      z-index: 10;
      padding: 20px;
      max-width: 90%;
    }
    h1 {
      font-family: 'Great Vibes', cursive;
      font-size: 4.5rem;
      margin-bottom: 10px;
      text-shadow: 0 0 20px rgba(255, 105, 180, 0.8);
      animation: glow 2s infinite alternate;
    }
    .typewriter {
      font-size: 1.8rem;
      margin: 20px 0;
      min-height: 80px;
    }
    .message {
      font-size: 1.4rem;
      line-height: 1.6;
      margin: 30px 0;
      opacity: 0;
      transform: translateY(30px);
      transition: all 1.2s ease;
    }
    .message.show { opacity: 1; transform: translateY(0); }
    .heart { color: #ff4757; font-size: 1.6rem; animation: beat 1.2s infinite; }
    @keyframes glow {
      from { text-shadow: 0 0 10px #ff9a9e; }
      to   { text-shadow: 0 0 30px #ff4757, 0 0 50px #ff6b81; }
    }
    @keyframes beat {
      0%,100% { transform: scale(1); }
      50%     { transform: scale(1.3); }
    }
    @media (max-width: 600px) {
      h1 { font-size: 3.5rem; }
      .typewriter { font-size: 1.5rem; }
    }
  </style>
</head>
<body>

<div id="tsparticles"></div>

<div class="content">
  <h1>Canım Benim 💕</h1>
  
  <div class="typewriter" id="typewriter"></div>
  
  <p class="message" id="msg1">Sen benim <span class="heart">güzelim</span>, <span class="heart">her şeyim</span>, <span class="heart">ömrüm</span> ve <span class="heart">balım</span>'sın ❤️</p>
  
  <p class="message" id="msg2">Seni gördüğüm ilk andan beri kalbim sadece senin için atıyor.</p>
  
  <p class="message" id="msg3">Dünyada senden daha güzel, senden daha tatlı, senden daha değerli bir şey yok.</p>
  
  <p class="message" id="msg4">Her nefeste seni seviyorum, her saniyede sana aşığım.</p>
  
  <p class="message" id="msg5">İyi ki varsın, iyi ki benimsin yavrum 💖 Sonsuza kadar seninim.</p>
</div>

<script>
// Particle kalpler (kalp yağmuru efekti)
tsParticles.load("tsparticles", {
  particles: {
    number: { value: 50, density: { enable: true, value_area: 800 } },
    color: { value: ["#ff4757", "#ff6b81", "#ff9a9e", "#ffffff"] },
    shape: { type: "heart" },
    opacity: { value: 0.7, random: true },
    size: { value: 12, random: true },
    move: {
      enable: true,
      speed: 2.5,
      direction: "bottom",
      random: true,
      straight: false,
      out_mode: "out",
      bounce: false
    }
  },
  interactivity: { detectsOn: "canvas", events: { onhover: { enable: true, mode: "repulse" } } },
  detectRetina: true
});

// Typewriter efekti
const texts = [
  "Seni çok seviyorum...",
  "Balım benim ❤️",
  "Ömrüm sensin...",
  "Güzelim, her şeyim..."
];
let textIndex = 0;
let charIndex = 0;
const typewriterEl = document.getElementById("typewriter");

function type() {
  if (charIndex < texts[textIndex].length) {
    typewriterEl.innerHTML += texts[textIndex].charAt(charIndex);
    charIndex++;
    setTimeout(type, 100);
  } else {
    setTimeout(erase, 2000);
  }
}

function erase() {
  if (charIndex > 0) {
    typewriterEl.innerHTML = texts[textIndex].substring(0, charIndex - 1);
    charIndex--;
    setTimeout(erase, 60);
  } else {
    textIndex = (textIndex + 1) % texts.length;
    setTimeout(type, 500);
  }
}
type();

// Mesajları sırayla göster (scroll olmasın diye delay ile)
setTimeout(() => document.getElementById("msg1").classList.add("show"), 3000);
setTimeout(() => document.getElementById("msg2").classList.add("show"), 5000);
setTimeout(() => document.getElementById("msg3").classList.add("show"), 7000);
setTimeout(() => document.getElementById("msg4").classList.add("show"), 9000);
setTimeout(() => document.getElementById("msg5").classList.add("show"), 11000);

</script>
</body>
</html>
