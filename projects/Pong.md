---
layout: project
type: project
image: img/pong/pong-header.png
title: "Pong Game"
date: 2025
published: true
labels:
  - HTML
  - JavaScript
summary: "A simple Pong game created using HTML, CSS, and JavaScript."
---

<img class="img-fluid" src="../img/pong/pong-header.png">

Pong is one of the earliest arcade video games, and this project recreates it using basic web development technologies. The game is interactive and playable directly in the browser. It demonstrates fundamental coding concepts such as animations, user input, and collision detection.

## Game Code

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Pong Game</title>
  <style>
    body {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
      background-color: #000;
      color: #fff;
      font-family: Arial, sans-serif;
    }
    canvas {
      border: 2px solid #fff;
    }
  </style>
</head>
<body>
  <canvas id="pongCanvas" width="800" height="400"></canvas>

  <script>
    const canvas = document.getElementById("pongCanvas");
    const ctx = canvas.getContext("2d");

    // Paddle dimensions
    const paddleWidth = 10;
    const paddleHeight = 100;

    // Ball dimensions
    const ballSize = 10;

    // Paddle positions
    const player = { x: 0, y: canvas.height / 2 - paddleHeight / 2, score: 0 };
    const ai = { x: canvas.width - paddleWidth, y: canvas.height / 2 - paddleHeight / 2, score: 0 };

    // Ball position and velocity
    const ball = { x: canvas.width / 2, y: canvas.height / 2, vx: 4, vy: 4 };

    // Draw paddles, ball, and score
    function drawRect(x, y, w, h, color) {
      ctx.fillStyle = color;
      ctx.fillRect(x, y, w, h);
    }

    function drawCircle(x, y, r, color) {
      ctx.fillStyle = color;
      ctx.beginPath();
      ctx.arc(x, y, r, 0, Math.PI * 2);
      ctx.closePath();
      ctx.fill();
    }

    function drawText(text, x, y) {
      ctx.fillStyle = "#fff";
      ctx.font = "20px Arial";
      ctx.fillText(text, x, y);
    }

    function update() {
      // Ball movement
      ball.x += ball.vx;
      ball.y += ball.vy;

      // Ball collision with top and bottom
      if (ball.y <= 0 || ball.y >= canvas.height - ballSize) {
        ball.vy *= -1;
      }

      // Ball collision with paddles
      if (
        (ball.x <= player.x + paddleWidth &&
          ball.y >= player.y &&
          ball.y <= player.y + paddleHeight) ||
        (ball.x + ballSize >= ai.x &&
          ball.y >= ai.y &&
          ball.y <= ai.y + paddleHeight)
      ) {
        ball.vx *= -1;
      }

      // Ball goes out of bounds
      if (ball.x <= 0) {
        ai.score++;
        resetBall();
      } else if (ball.x >= canvas.width) {
        player.score++;
        resetBall();
      }

      // AI movement
      ai.y += (ball.y - (ai.y + paddleHeight / 2)) * 0.1;

      // Keep AI paddle within canvas
      ai.y = Math.max(Math.min(ai.y, canvas.height - paddleHeight), 0);
    }

    function resetBall() {
      ball.x = canvas.width / 2;
      ball.y = canvas.height / 2;
      ball.vx = 4 * (Math.random() > 0.5 ? 1 : -1);
      ball.vy = 4 * (Math.random() > 0.5 ? 1 : -1);
    }

    function render() {
      // Clear canvas
      ctx.clearRect(0, 0, canvas.width, canvas.height);

      // Draw paddles, ball, and score
      drawRect(player.x, player.y, paddleWidth, paddleHeight, "#fff");
      drawRect(ai.x, ai.y, paddleWidth, paddleHeight, "#fff");
      drawCircle(ball.x, ball.y, ballSize, "#fff");
      drawText(`Player: ${player.score}`, 20, 20);
      drawText(`AI: ${ai.score}`, canvas.width - 100, 20);
    }

    function gameLoop() {
      update();
      render();
      requestAnimationFrame(gameLoop);
    }

    // Event listener for player paddle movement
    document.addEventListener("mousemove", (e) => {
      const rect = canvas.getBoundingClientRect();
      player.y = e.clientY - rect.top - paddleHeight / 2;
      player.y = Math.max(Math.min(player.y, canvas.height - paddleHeight), 0);
    });

    // Start the game
    gameLoop();
  </script>
</body>
</html>
```

## How to Play
- Use your mouse to move the player's paddle up and down.
- Prevent the ball from passing your paddle while trying to get it past the AI.

Source: <a href="https://github.com/your-username/pong-game"><i class="large github icon"></i>your-username/pong-game</a>
