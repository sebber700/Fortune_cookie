<!DOCTYPE html>
<html lang="da">
<head>
<meta charset="UTF-8">
<title>Fortune Cookie</title>

<style>
body {
  margin: 0;
  height: 100vh;
  background: #fdf6ec;
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: Georgia, serif;
  overflow: hidden;
}

/* Container */
.scene {
  position: relative;
  width: 260px;
  height: 260px;
}

/* COOKIE */
.cookie {
  position: absolute;
  bottom: 60px;
  left: 50%;
  width: 180px;
  height: 90px;
  background: #d8a15d;
  border-radius: 0 0 120px 120px;
  transform: translateX(-50%);
  box-shadow:
    inset 0 -6px 8px rgba(0,0,0,0.2),
    0 8px 10px rgba(0,0,0,0.15);
  transform-origin: center bottom;
  animation: crack 1.2s ease forwards;
  animation-delay: 0.8s;
}

@keyframes crack {
  0% { transform: translateX(-50%) rotate(0deg); }
  100% { transform: translateX(-50%) rotate(-12deg); }
}

/* PAPER (ROLLED) */
.paper {
  position: absolute;
  bottom: 90px;
  left: 50%;
  width: 22px;
  height: 60px;
  background: linear-gradient(
    to right,
    #fefcea,
    #e8e1c8,
    #fefcea
  );
  border-radius: 12px;
  transform: translateX(-50%) scaleY(0);
  transform-origin: bottom;
  box-shadow: inset -2px 0 3px rgba(0,0,0,0.25);
  animation: paperUp 2s ease forwards;
  animation-delay: 1.6s;
}

/* UNROLL */
.paper.open {
  width: 200px;
  height: auto;
  padding: 16px 18px;
  border-radius: 4px;
  background:
    repeating-linear-gradient(
      #fffdf3,
      #fffdf3 4px,
      #f1ecd8 5px
    );
  box-shadow: 0 4px 12px rgba(0,0,0,0.2);
  transform: translateX(-50%) scaleY(1);
}

@keyframes paperUp {
  0% { transform: translateX(-50%) scaleY(0); }
  100% { transform: translateX(-50%) scaleY(1); }
}

/* TEXT */
.fortune {
  opacity: 0;
  font-size: 1.2rem;
  line-height: 1.4;
  text-align: center;
}

.paper.open .fortune {
  animation: textFade 1.2s ease forwards;
  animation-delay: 0.6s;
}

@keyframes textFade {
  to { opacity: 1; }
}
</style>
</head>

<body>

<div class="scene">
  <div class="paper" id="paper">
    <div class="fortune" id="fortune"></div>
  </div>
  <div class="cookie"></div>
</div>

<script>
const fortunes = [
  "Du er mere elsket, end du tror.",
  "I dag sker der noget, der får dig til at smile.",
  "Dit hjerte ved allerede, hvad der er rigtigt.",
  "En lille glæde er på vej til dig.",
  "Du gør en større forskel, end du kan se.",
  "Nogen tænker på dig lige nu.",
  "Det, du håber på, er tættere på, end det føles.",
  "Du er præcis nok, som du er.",
  "Dine bedste dage er ikke bag dig.",
  "Kærlighed finder dig, når du mindst venter det.",
  "I dag er et godt tidspunkt at være blid ved dig selv.",
  "Din energi gør verden lidt varmere.",
  "Noget smukt vokser stille i dit liv.",
  "Du er en persons yndlingsmenneske.",
  "Følg det, der giver ro i maven.",
  "Et ja venter på dig i fremtiden.",
  "Du er på rette vej – også på de langsomme dage.",
  "Din tilstedeværelse betyder mere, end ord kan sige.",
  "Små skridt fører også til store steder.",
  "Du fortjener alt det gode, der kommer."
];

// Random fortune
document.getElementById("fortune").textContent =
  fortunes[Math.floor(Math.random() * fortunes.length)];

// Unroll paper after slide-up
setTimeout(() => {
  document.getElementById("paper").classList.add("open");
}, 3200);
</script>

</body>
</html>
