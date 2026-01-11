<!DOCTYPE html>
<html lang="da">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Fortune Cookie</title>

<style>
/* ---------- RESET ---------- */
* {
  box-sizing: border-box;
}

/* ---------- BODY ---------- */
body {
  margin: 0;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background:
    repeating-radial-gradient(
      circle at 0 0,
      #c43a2f 0,
      #c43a2f 20px,
      #a92c23 21px,
      #a92c23 40px
    );
  font-family: Georgia, serif;
  overflow: hidden;
}

/* ---------- SCENE ---------- */
.scene {
  position: relative;
  width: 360px;
  height: 420px;
}

/* ---------- COOKIE ---------- */
.cookie {
  position: absolute;
  left: 50%;
  top: 180px;
  width: 320px;
  transform: translateX(-50%);
  transition: opacity 0.8s ease, transform 1.2s ease;
}

#cookieBroken {
  opacity: 0;
}

/* ---------- ROLLED PAPER ---------- */
.paper-roll {
  position: absolute;
  left: 50%;
  top: 200px;
  width: 34px;
  height: 90px;
  background: linear-gradient(
    to right,
    #fefcea,
    #e6dfc8,
    #fefcea
  );
  border-radius: 18px;
  transform: translateX(-50%) translateY(40px);
  opacity: 0;
  box-shadow: inset -2px 0 3px rgba(0,0,0,0.25);
  transition: transform 2.5s ease, opacity 1s ease;
}

.paper-roll.show {
  opacity: 1;
  transform: translateX(-50%) translateY(-70px);
}

/* ---------- UNROLLED PAPER ---------- */
.paper {
  position: absolute;
  top: 40px;
  left: 50%;
  width: 300px;
  padding: 22px 20px;
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
  box-shadow: 0 6px 14px rgba(0,0,0,0.25);
  text-align: center;
}

.paper.show {
  transform: translateX(-50%) scaleY(1);
}

.paper p {
  margin: 0;
  font-size: 1.25rem;
  line-height: 1.45;
  opacity: 0;
  transition: opacity 1s ease;
}

.paper.show p {
  opacity: 1;
}
</style>
</head>

<body>

<div class="scene">

  <img src="cookie-whole.svg"
       class="cookie"
       id="cookieWhole"
       alt="Fortune cookie">

  <img src="cookie-broken.png"
       class="cookie"
       id="cookieBroken"
       alt="Broken fortune cookie">

  <div class="paper-roll" id="paperRoll"></div>

  <div class="paper" id="paper">
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

// vælg fortune
document.getElementById("fortuneText").textContent =
  fortunes[Math.floor(Math.random() * fortunes.length)];

// animation sequence
setTimeout(() => {
  document.getElementById("cookieWhole").style.opacity = 0;
  document.getElementById("cookieBroken").style.opacity = 1;
}, 900);

setTimeout(() => {
  document.getElementById("paperRoll").classList.add("show");
}, 1600);

setTimeout(() => {
  document.getElementById("paper").classList.add("show");
}, 3200);
</script>

</body>
</html>
