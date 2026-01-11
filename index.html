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

.scene {
  position: relative;
  width: 360px;
  height: 360px;
}

/* COOKIE */
.cookie {
  position: absolute;
  left: 50%;
  top: 50%;
  width: 320px;
  transform: translate(-50%, -50%);
  transition: opacity 0.8s ease, transform 1.2s ease;
}

/* Start state */
#cookieBroken {
  opacity: 0;
  transform: translate(-50%, -50%) scale(0.98);
}

/* PAPER */
.paper {
  position: absolute;
  left: 50%;
  top: 50%;
  width: 36px;
  height: 90px;
  background: linear-gradient(
    to right,
    #fefcea,
    #e6dfc8,
    #fefcea
  );
  border-radius: 18px;
  transform: translate(-50%, 20px);
  opacity: 0;
  transition: transform 2.5s ease, opacity 1s ease;
  box-shadow: inset -2px 0 3px rgba(0,0,0,0.25);
}

/* Paper slides up */
.paper.show {
  opacity: 1;
  transform: translate(-50%, -90px);
}

/* UNROLLED PAPER */
.fortune {
  position: absolute;
  top: 40px;
  left: 50%;
  width: 280px;
  padding: 18px 20px;
  background:
    repeating-linear-gradient(
      #fffdf3,
      #fffdf3 4px,
      #f1ecd8 5px
    );
  border-radius: 4px;
  transform: translateX(-50%) scaleY(0);
  transform-origin: top;
  transition: transform 1.4s ease;
  box-shadow: 0 4px 12px rgba(0,0,0,0.2);
  text-align: center;
}

.fortune.show {
  transform: translateX(-50%) scaleY(1);
}

.fortune p {
  margin: 0;
  font-size: 1.2rem;
  line-height: 1.4;
  opacity: 0;
  transition: opacity 1s ease;
}

.fortune.show p {
  opacity: 1;
}
</style>
</head>

<body>

<div class="scene">

  <!-- HEL COOKIE -->
  <img src="cookie-whole.svg"
       id="cookieWhole"
       class="cookie"
       alt="Fortune cookie">

  <!-- KNÆKKET COOKIE -->
  <img src="cookie-broken.svg"
       id="cookieBroken"
       class="cookie"
       alt="Broken fortune cookie">

  <!-- RULLET PAPIR -->
  <div class="paper" id="paper"></div>

  <!-- PAPIR MED TEKST -->
  <div class="fortune" id="fortune">
    <p id="fortuneText"></p>
  </div>

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
document.getElementById("fortuneText").textContent =
  fortunes[Math.floor(Math.random() * fortunes.length)];

// 1. Crack cookie
setTimeout(() => {
  document.getElementById("cookieWhole").style.opacity = 0;
  document.getElementById("cookieBroken").style.opacity = 1;
}, 900);

// 2. Paper slides up (rolled)
setTimeout(() => {
  document.getElementById("paper").classList.add("show");
}, 1700);

// 3. Paper unrolls
setTimeout(() => {
  document.getElementById("fortune").classList.add("show");
}, 3200);
</script>

</body>
</html>
