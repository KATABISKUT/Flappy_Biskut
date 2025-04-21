<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Flappy Bird Clone</title>
  <style>
    
#insta-promo {
  position: absolute;
  bottom: 10px;
  right: 10px;
  font-size: 14px;
  color: #555;
  background: rgba(255, 255, 255, 0.8);
  padding: 6px 10px;
  border-radius: 8px;
  text-decoration: none;
  font-family: Arial, sans-serif;
  display: flex;
  align-items: center;
  z-index: 1000;
}

#insta-promo:hover {
  background: #ffcc00;
  color: black;
}
  
  * { margin: 0; padding: 0; box-sizing: border-box; }
    body, html { width: 100%; height: 100%; overflow: hidden; background: #70c5ce; }
    canvas { display: block; margin: auto; background-color: #70c5ce; }
    #main-menu, #game-over-menu, #settings-menu, #skin-menu {
      position: absolute;
      top: 50%; left: 50%;
      transform: translate(-50%, -50%);
      display: none;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      background: white;
      padding: 20px;
      border-radius: 10px;
    }
    #main-menu button, #game-over-menu button, #settings-menu button, #skin-menu button {
      padding: 15px;
      margin: 10px;
      font-size: 18px;
      cursor: pointer;
      background-color: #ffcc00;
      border: none;
    }
    .skin-option {
      width: 40px;
      height: 40px;
      margin: 10px;
      border: 2px solid transparent;
      cursor: pointer;
    }
    .skin-option.selected {
      border-color: red;
    }
    #skin-options {
      display: flex;
      gap: 10px;
      margin-bottom: 10px;
    }
  </style>
</head>
<a id="insta-promo" href="https://instagram.com/h3z_katabiskut" target="_blank">
  <img src="https://cdn-icons-png.flaticon.com/512/174/174855.png" alt="Instagram" style="width: 18px; vertical-align: middle; margin-right: 6px;">
  @h3z_katabiskut
</a>
<body>

<canvas id="gameCanvas" width="360" height="600"></canvas>

<div id="main-menu">
  <button id="start-btn">Start Game</button>
  <button id="skin-btn">Change Skin</button>
  <button id="settings-btn">Settings</button>
</div>

<div id="skin-menu">
  <h2>Select Your Bird</h2>
  <div id="skin-options">
    <img src="https://i.ibb.co/WsxwY8m/bird.png" class="skin-option" data-skin="bird1">
    <img src="https://i.ibb.co/vD8pn4C/bird2.png" class="skin-option" data-skin="bird2">
  </div>
  <button id="back-from-skin-btn">Back</button>
</div>

<div id="game-over-menu">
  <h2>Game Over</h2>
  <p id="score-text">Score: 0</p>
  <p id="high-score-text">High Score: 0</p>
  <button id="restart-btn">Restart</button>
  <button id="main-menu-btn">Main Menu</button>
</div>

<div id="settings-menu">
  <h2>Settings</h2>
  <p>Select Difficulty:</p>
  <label><input type="radio" name="difficulty" value="easy"> Easy</label><br>
  <label><input type="radio" name="difficulty" value="normal" checked> Normal</label><br>
  <label><input type="radio" name="difficulty" value="hard"> Hard</label><br><br>
  <button id="close-settings-btn">Close</button>
</div>

<script>
  const canvas = document.getElementById("gameCanvas");
  const ctx = canvas.getContext("2d");

  const bird = {
    x: 50,
    y: 150,
    width: 29,
    height: 29,
    gravity: 0.4,
    lift: -9,
    velocity: 0,
    image: new Image(),
    skin: 'bird1',
    draw: function() {
      this.image.src = this.skin === 'bird1'
        ? "https://i.ibb.co/WsxwY8m/bird.png"
        : "https://i.ibb.co/vD8pn4C/bird2.png";
      ctx.drawImage(this.image, this.x, this.y, this.width, this.height);
    }
  };

  const pipes = [];
  let frame = 0;
  let score = 0;
  let highScore = localStorage.getItem("highScore") || 0;
  let gameOver = false;
  let canFlap = true;

  let currentDifficulty = "normal";
  const difficultySettings = {
    easy: { pipeSpeed: 1.5, gap: 300 },
    normal: { pipeSpeed: 2, gap: 250 },
    hard: { pipeSpeed: 3, gap: 180 }
  };
  let pipeSpeed = difficultySettings.normal.pipeSpeed;
  let gap = difficultySettings.normal.gap;

  const pipeWidth = 50;

  const restartBtn = document.getElementById("restart-btn");
  const startBtn = document.getElementById("start-btn");
  const skinBtn = document.getElementById("skin-btn");
  const settingsBtn = document.getElementById("settings-btn");
  const mainMenuBtn = document.getElementById("main-menu-btn");
  const mainMenu = document.getElementById("main-menu");
  const gameOverMenu = document.getElementById("game-over-menu");
  const settingsMenu = document.getElementById("settings-menu");
  const closeSettingsBtn = document.getElementById("close-settings-btn");

  const skinMenu = document.getElementById("skin-menu");
  const skinOptions = document.querySelectorAll(".skin-option");
  const backFromSkinBtn = document.getElementById("back-from-skin-btn");

  const scoreText = document.getElementById("score-text");
  const highScoreText = document.getElementById("high-score-text");

  function showMainMenu() {
  mainMenu.style.display = "flex";
  gameOverMenu.style.display = "none";
  canvas.style.display = "none";
  document.getElementById("insta-promo").style.display = "flex";
}

  function startGame() {
  bird.y = 150;
  bird.velocity = 0;
  pipes.length = 0;
  score = 0;
  gameOver = false;
  frame = 0;
  canFlap = true;

  pipeSpeed = difficultySettings[currentDifficulty].pipeSpeed;
  gap = difficultySettings[currentDifficulty].gap;

  mainMenu.style.display = "none";
  gameOverMenu.style.display = "none";
  settingsMenu.style.display = "none";
  canvas.style.display = "block";
  document.getElementById("insta-promo").style.display = "none";
  animate();
}

  function drawPipes() {
    pipes.forEach(pipe => {
      ctx.fillStyle = "green";
      ctx.fillRect(pipe.x, 0, pipeWidth, pipe.top);
      ctx.fillRect(pipe.x, pipe.top + gap, pipeWidth, canvas.height - pipe.top - gap);
    });
  }

  function updatePipes() {
    if (frame % 90 === 0) {
      const top = Math.random() * (canvas.height - gap);
      pipes.push({ x: canvas.width, top });
    }

    pipes.forEach((pipe, index) => {
      pipe.x -= pipeSpeed;

      if (pipe.x + pipeWidth < bird.x && !pipe.passed) {
        score++;
        pipe.passed = true;
      }

      if (pipe.x + pipeWidth < 0) {
        pipes.splice(index, 1);
      }
    });
  }

  function detectCollision() {
    if (bird.y + bird.height >= canvas.height || bird.y <= 0) {
      gameOver = true;
    }

    pipes.forEach(pipe => {
      if (
        bird.x + bird.width > pipe.x &&
        bird.x < pipe.x + pipeWidth &&
        (bird.y < pipe.top || bird.y + bird.height > pipe.top + gap)
      ) {
        gameOver = true;
      }
    });
  }

  function animate() {
    if (gameOver) {
      if (score > highScore) {
        highScore = score;
        localStorage.setItem("highScore", highScore);
      }
      scoreText.textContent = "Score: " + score;
      highScoreText.textContent = "High Score: " + highScore;

      gameOverMenu.style.display = "flex";
      return;
    }

    ctx.clearRect(0, 0, canvas.width, canvas.height);

    bird.velocity += bird.gravity;
    bird.y += bird.velocity;

    if (bird.velocity > 0) canFlap = true;

    drawPipes();
    bird.draw();
    updatePipes();
    detectCollision();

    ctx.fillStyle = "white";
    ctx.font = "20px Arial";
    ctx.fillText("Score: " + score, 10, 30);

    frame++;
    requestAnimationFrame(animate);
  }

  function flap() {
    if (!gameOver && canFlap) {
      bird.velocity = bird.lift;
      canFlap = false;
    }
  }

  document.addEventListener("click", flap);
  document.addEventListener("touchstart", flap);

  restartBtn.addEventListener("click", startGame);
  mainMenuBtn.addEventListener("click", showMainMenu);
  startBtn.addEventListener("click", startGame);

  skinBtn.addEventListener("click", () => {
    skinMenu.style.display = "flex";
    mainMenu.style.display = "none";
  });

  backFromSkinBtn.addEventListener("click", () => {
    skinMenu.style.display = "none";
    mainMenu.style.display = "flex";
  });

  settingsBtn.addEventListener("click", () => {
    settingsMenu.style.display = "flex";
    mainMenu.style.display = "none";
  });

  closeSettingsBtn.addEventListener("click", () => {
    settingsMenu.style.display = "none";
    mainMenu.style.display = "flex";
  });

  document.querySelectorAll("input[name='difficulty']").forEach(radio => {
    radio.addEventListener("change", function () {
      currentDifficulty = this.value;
    });
  });

  skinOptions.forEach(option => {
    option.addEventListener("click", function () {
      skinOptions.forEach(o => o.classList.remove("selected"));
      this.classList.add("selected");
      bird.skin = this.dataset.skin;
    });
  });

  showMainMenu();
</script>
</body>
</html>