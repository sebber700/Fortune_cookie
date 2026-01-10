<!DOCTYPE html>
<html lang="da">
<head>
  <meta charset="UTF-8" />
  <title>Fortune Cookie</title>
  <style>
    body {
      margin: 0;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: #fef6f0;
      font-family: "Georgia", serif;
      overflow: hidden;
    }

    .cookie-container {
      position: relative;
      width: 200px;
      height: 200px;
    }

    /* Cookie stykker */
    .cookie-left,
    .cookie-right {
      position: absolute;
      top: 0;
      width: 100px;
      height: 100px;
      background: #d4a15b;
      border-radius: 50%;
      transform-origin: center bottom;
      box-shadow: inset -3px -3px 5px rgba(0,0,0,0.2);
    }

    .cookie-left { left: 0; }
    .cookie-right { right: 0; }

    /* Cookie animation */
    .crack .cookie-left {
      animation: leftCrack 1s forwards;
    }
    .crack .cookie-right {
      animation: rightCrack 1s forwards;
    }

    @keyframes leftCrack {
      0% { transform: rotate(0deg); }
      100% { transform: rotate(-45deg) translateX(-20px) translateY(20px); }
    }

    @keyframes rightCrack {
      0% { transform: rotate(0deg); }
      100% { transform: rotate(45deg) translateX(20px) translateY(20px); }
    }

    /* Paper with fortune */
    .fortune-paper {
      position: absolute;
      top: 50%;
      left: 50%;
      width: 180px;
      padding: 15px;
      background: #fff9e6;
      background-image: repeating-linear-gradient(white, white 4px, #eee 4px, #eee 5px);
      box-shadow: 0 2px 8px rgba(0,0,0,0.2);
      border: 1px solid #e0d4b0;
      border-radius: 4px;
      transform: translate(-50%, -50%) scale(0);
      opacity: 0;
      text-align: center;
      font-size: 1.2rem;
      line-height: 1.4;
    }

    .crack .fortune-paper {
      animation: showPaper 1s 1s forwards;
    }

    @keyframes showPaper {
      0% { transform: translate(-50%, -50%) scale(0); opacity: 0; }
      60% { transform: translate(-50%, -60%) scale(1.1); opacity: 1; }
      100% { transform: translate(-50%, -50%) scale(1); opacity: 1; }
    }
  </style>
</head>
<body>

  <div class="cookie-container" id="cookieContainer">
    <div class="cookie-left"></div>
    <div class="cookie-right"></div>
    <div class="fortune-paper" id="fortuneText"></div>
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

    // Vælg en tilfældig fortune
    const random = fortunes[Math.floor(Math.random() * fortunes.length)];

    // Sæt teksten
    document.getElementById("fortuneText").textContent = random;

    // Start animation
    const cookie = document.getElementById("cookieContainer");
    setTimeout(() => {
      cookie.classList.add("crack");
    }, 500); // vent 0.5s før animation
  </script>

</body>
</html>
