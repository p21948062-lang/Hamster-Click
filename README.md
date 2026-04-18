<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<title>🐹 Hamster Clicker</title>
<style>
body {
  margin: 0;
  background: #0f0f0f;
  color: white;
  font-family: Arial;
  text-align: center;
}

h1 {
  margin-top: 20px;
}

#hamster {
  font-size: 120px;
  cursor: pointer;
  margin: 30px;
}

#score {
  font-size: 30px;
}

.shop {
  margin-top: 20px;
  padding: 10px;
}

button {
  padding: 10px 15px;
  margin: 5px;
  font-size: 16px;
  cursor: pointer;
}

.upgrade {
  background: #222;
  border: 1px solid #555;
  color: white;
}
</style>
</head>
<body>

<h1>🐹 Hamster Clicker</h1>

<div id="score">Очки: 0</div>

<div id="hamster" onclick="clickHamster()">🐹</div>

<div class="shop">
  <h2>🛒 Магазин</h2>

  <button class="upgrade" onclick="buyClick()">+1 за клик (10)</button>
  <button class="upgrade" onclick="buyAuto()">Автоклик (50)</button>
</div>

<script>
let score = 0;
let clickPower = 1;
let autoClick = 0;

function clickHamster() {
  score += clickPower;
  update();
}

function buyClick() {
  if (score >= 10) {
    score -= 10;
    clickPower++;
    update();
  }
}

function buyAuto() {
  if (score >= 50) {
    score -= 50;
    autoClick++;
    update();
  }
}

setInterval(() => {
  score += autoClick;
  update();
}, 1000);

function update() {
  document.getElementById("score").innerText = "Очки: " + score;
}
</script>

</body
