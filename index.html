<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no"/>
<title>Purple Snake Mobile 💜</title>

<style>
  body {
    margin: 0;
    background: linear-gradient(135deg, #6a0dad, #a64dff);
    display: flex;
    flex-direction: column;
    align-items: center;
    font-family: Arial, sans-serif;
    color: white;
    height: 100vh;
    overflow: hidden;
    touch-action: none;
  }

  h1 { margin: 10px; }
  .score { font-size: 18px; margin-bottom: 5px; }

  canvas {
    background: rgba(255,255,255,0.12);
    border-radius: 15px;
    box-shadow: 0 15px 35px rgba(0,0,0,0.4);
    width: 90vw;
    max-width: 320px;
    height: 90vw;
    max-height: 320px;
  }

  .center {
    position: absolute;
    top: 35%;
    text-align: center;
  }

  button {
    padding: 10px 20px;
    border: none;
    border-radius: 12px;
    margin: 5px;
    font-size: 16px;
    cursor: pointer;
  }

  .start, .retry {
    background: white;
    color: #6a0dad;
  }

  .message {
    display: none;
    max-width: 320px;
    background: rgba(255,255,255,0.12);
    padding: 20px;
    border-radius: 20px;
    backdrop-filter: blur(10px);
  }

  .controls {
    margin-top: 10px;
    display: grid;
    grid-template-columns: repeat(3, 60px);
    grid-template-rows: repeat(2, 60px);
    gap: 10px;
  }

  .btn {
    background: white;
    color: #6a0dad;
    border-radius: 10px;
    font-size: 18px;
  }
</style>
</head>

<body>

<h1>🐍 Purple Snake</h1>
<div class="score" id="score">Score: 0</div>

<canvas id="game" width="300" height="300"></canvas>

<div class="controls">
  <div></div>
  <button class="btn" onclick="setDir('UP')">⬆</button>
  <div></div>

  <button class="btn" onclick="setDir('LEFT')">⬅</button>
  <div></div>
  <button class="btn" onclick="setDir('RIGHT')">➡</button>

  <div></div>
  <button class="btn" onclick="setDir('DOWN')">⬇</button>
  <div></div>
</div>

<!-- START -->
<div class="center" id="startScreen">
  <button class="start" onclick="startGame()">Start ▶️</button>
</div>

<!-- WIN -->
<div class="center message" id="winScreen">
  <h2 id="crushText">💜 Hi Crush</h2>
  <p>
    I just wanted to say I really admire you and the way you carry yourself 💜<br><br>
    I hope you're doing well.
  </p>
  <button class="retry" onclick="retry()">Play Again 🔁</button>
</div>

<!-- LOSE -->
<div class="center message" id="loseScreen">
  <h2>💀 Game Over</h2>
  <p>Try again?</p>
  <button class="retry" onclick="retry()">Retry 🔁</button>
</div>

<script>
const canvas = document.getElementById("game");
const ctx = canvas.getContext("2d");

const scoreEl = document.getElementById("score");
const startScreen = document.getElementById("startScreen");
const winScreen = document.getElementById("winScreen");
const loseScreen = document.getElementById("loseScreen");

let box = 15;
let snake, dir, food, score, running, speed;

/* CHANGE NAME HERE */
let crushName = "Crush";
document.getElementById("crushText").innerText = "💜 Hi " + crushName;

function init() {
  snake = [{x: 150, y: 150}];
  dir = "RIGHT";
  food = spawnFood();
  score = 0;
  running = false;
  speed = 120;
  scoreEl.innerText = "Score: 0";
}

init();

/* KEYBOARD */
document.addEventListener("keydown", e => {
  if (!running) return;
  if (e.key === "ArrowUp") setDir("UP");
  if (e.key === "ArrowDown") setDir("DOWN");
  if (e.key === "ArrowLeft") setDir("LEFT");
  if (e.key === "ArrowRight") setDir("RIGHT");
});

function setDir(newDir) {
  if (newDir === "UP" && dir !== "DOWN") dir = "UP";
  if (newDir === "DOWN" && dir !== "UP") dir = "DOWN";
  if (newDir === "LEFT" && dir !== "RIGHT") dir = "LEFT";
  if (newDir === "RIGHT" && dir !== "LEFT") dir = "RIGHT";
}

/* FIXED FOOD SPAWN */
function spawnFood() {
  let newFood;
  do {
    newFood = {
      x: Math.floor(Math.random() * 20) * box,
      y: Math.floor(Math.random() * 20) * box
    };
  } while (snake.some(s => s.x === newFood.x && s.y === newFood.y));
  return newFood;
}

function startGame() {
  startScreen.style.display = "none";
  loseScreen.style.display = "none";
  winScreen.style.display = "none";
  running = true;
  draw();
}

function retry() {
  init();
  startGame();
}

/* SWIPE */
let startX, startY;

document.addEventListener("touchstart", e => {
  startX = e.touches[0].clientX;
  startY = e.touches[0].clientY;
});

document.addEventListener("touchend", e => {
  if (!running) return;

  let dx = e.changedTouches[0].clientX - startX;
  let dy = e.changedTouches[0].clientY - startY;

  if (Math.abs(dx) > Math.abs(dy)) {
    dx > 0 ? setDir("RIGHT") : setDir("LEFT");
  } else {
    dy > 0 ? setDir("DOWN") : setDir("UP");
  }
});

function draw() {
  if (!running) return;

  ctx.clearRect(0, 0, 300, 300);

  snake.forEach((s, i) => {
    ctx.fillStyle = i === 0 ? "#e6ccff" : "#b266ff";
    ctx.fillRect(s.x, s.y, box, box);
  });

  ctx.fillStyle = "#fff";
  ctx.fillRect(food.x, food.y, box, box);

  let head = {...snake[0]};

  if (dir === "UP") head.y -= box;
  if (dir === "DOWN") head.y += box;
  if (dir === "LEFT") head.x -= box;
  if (dir === "RIGHT") head.x += box;

  /* EAT */
  if (head.x === food.x && head.y === food.y) {
    score++;
    scoreEl.innerText = "Score: " + score;
    food = spawnFood();

    /* SPEED UP */
    if (score % 2 === 0 && speed > 60) {
      speed -= 5;
    }

    /* WIN */
    if (score >= 5) {
      running = false;
      winScreen.style.display = "block";
      return;
    }

  } else {
    snake.pop();
  }

  /* COLLISION */
  if (
    head.x < 0 || head.x >= 300 ||
    head.y < 0 || head.y >= 300 ||
    snake.some(s => s.x === head.x && s.y === head.y)
  ) {
    running = false;
    loseScreen.style.display = "block";
    return;
  }

  snake.unshift(head);

  setTimeout(draw, speed);
}
</script>

</body>
</html>
