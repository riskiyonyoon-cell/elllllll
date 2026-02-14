<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>Happy Valentine bb 💗</title>

<style>
* {
  box-sizing: border-box;
  font-family: 'Segoe UI', sans-serif;
}

body {
  margin: 0;
  height: 100vh;
  background: linear-gradient(180deg, #ffdde1, #ee9ca7);
  display: flex;
  justify-content: center;
  align-items: center;
}

.phone {
  width: 100%;
  max-width: 390px;
  aspect-ratio: 9 / 16;
  background: #ffffff;
  border-radius: 28px;
  padding: 22px;
  box-shadow: 0 25px 50px rgba(0,0,0,0.25);
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  overflow: hidden;
}

h1 {
  text-align: center;
  color: #ff4d6d;
  margin-bottom: 10px;
  font-size: 20px;
}

#text {
  flex: 1;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  font-size: 15px; /* DIPERKECIL */
  line-height: 1.6;
  color: #333;
  padding: 10px;
  transition: opacity 0.3s ease;
}

img {
  width: 100%;
  border-radius: 18px;
  margin-top: 14px;
  display: none;
  box-shadow: 0 15px 30px rgba(0,0,0,0.25);
}

button {
  width: 100%;
  padding: 14px;
  border: none;
  border-radius: 14px;
  font-size: 15px;
  margin-top: 10px;
  cursor: pointer;
}

#yes {
  display: none;
  background: #ff4d6d;
  color: #fff;
}

#no {
  background: #f2f2f2;
  color: #aaa;
  position: relative;
}

#next {
  display: none;
  background: #ff4d6d;
  color: #fff;
}

#dm {
  display: none;
  background: linear-gradient(45deg, #833ab4, #fd1d1d);
  color: white;
}

.love {
  font-size: 20px;
}
</style>
</head>

<body>

<audio autoplay loop>
  <source src="https://www.bensound.com/bensound-music/bensound-love.mp3">
</audio>

<div class="phone">
  <div>
    <h1>HAPPY VALENTINE 💕</h1>
    <div id="text">
      Kamu mau terus sama aku nggak? 🥺💗
    </div>

    <img id="photo"
      src="https://i.pinimg.com/1200x/18/6d/cc/186dcc5a78117799b7238a19ed441091.jpg"
      alt="aku & el">
  </div>

  <div>
    <button id="yes">YES 💗</button>
    <button id="no">NO ❌</button>
    <button id="next">Next 💗</button>
    <button id="dm" onclick="goDM()">Balas Sekarang 💌</button>
  </div>
</div>

<script>
const texts = [
  "Hey El… 💗",
  "I made this slowly, with you on my mind.",
  "Sometimes life feels loud, but you make it quiet.",
  "Capek sama dunia itu nyata, tapi kamu selalu bikin lega.",
  "Talking to you feels safe. No pressure. No pretending.",
  "Lowkey… kamu adalah bagian favorit dari hariku.",
  "I don’t need perfect moments, just moments with you.",
  "You’re soft in a way that calms me down.",
  "You are loved. More than you think.",
  "I choose you. Still. Every time.",
  "So… can I stay with you a little longer? 🌷"
];

let index = 0;

const textEl = document.getElementById("text");
const photo = document.getElementById("photo");
const yesBtn = document.getElementById("yes");
const noBtn = document.getElementById("no");
const nextBtn = document.getElementById("next");
const dmBtn = document.getElementById("dm");

// NO kabur + munculin YES
noBtn.onmouseover = () => {
  noBtn.style.transform =
    `translate(${Math.random()*80 - 40}px, ${Math.random()*40 - 20}px)`;
  yesBtn.style.display = "block";
};

// YES ditekan → mulai cerita
yesBtn.onclick = () => {
  yesBtn.style.display = "none";
  noBtn.style.display = "none";
  nextBtn.style.display = "block";
  textEl.innerHTML = texts[0];
};

// NEXT teks
nextBtn.onclick = () => {
  index++;
  textEl.style.opacity = 0;

  setTimeout(() => {
    if (index < texts.length) {
      textEl.innerHTML = texts[index];
      textEl.style.opacity = 1;
    } else {
      nextBtn.style.display = "none";
      photo.style.display = "block";
      dmBtn.style.display = "block";
      textEl.innerHTML = `
        <div class="love">
          💗💗💗💗💗<br>
          Happy Valentine, El.<br>
          I love you.
        </div>`;
      textEl.style.opacity = 1;
    }
  }, 250);
};

// DM IG
function goDM() {
  const message = encodeURIComponent(
    "happy valentine el 🤍\n\n" +
    "aku udah baca semuanya.\n" +
    "sekarang aku mau DM kamu 💗"
  );

  window.open(
    "https://www.instagram.com/direct/new/?username=drugstprn&text=" + message,
    "_blank"
  );
}
</script>

</body>
</html>

