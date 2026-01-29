<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Moon Hopper</title>
  <style>
    body {
      margin: 0;
      background: radial-gradient(circle at top, #0b1026, #000);
      overflow: hidden;
      font-family: Arial, sans-serif;
      color: white;
      text-align: center;
    }

    canvas {
      display: block;
      margin: 0 auto;
      background: transparent;
    }

    #overlay {
      position: absolute;
      top: 40%;
      width: 100%;
      font-size: 24px;
      pointer-events: none;
    }
  </style>
</head>
<body>

<canvas id="game" width="420" height="600"></canvas>
<div id="overlay"></div>

<script>
const canvas = document.getElementById("game");
const ctx = canvas.getContext("2d");
const overlay = document.getElementById("overlay");

let gameOver = false;
let score = 0;

// Bunny (player)
const bunny = {
  x: 100,
  y: 300,
  r: 15,
  velocity: 0,
  gravity: 0.4,
  jump: -7
};

// Rings (obstacles)
let rings = [];
let frame = 0;

function spawnRing() {
  const gap = 140;
  const top = Math.random() * 250 + 50;
  rings.push({
    x: canvas.width,
    top,
    bottom: top + gap,
    passed: false
  });
}

// Input
document.addEventListener("keydown", e => {
  if (e.code === "Space") flap();
});
document.addEventListener("click", flap);

function flap() {
  if (gameOver) {
    reset();
  } else {
    bunny.velocity = bunny.jump;
  }
}

// Reset game
function reset() {
  rings = [];
  bunny.y = 300;
  bunny.velocity = 0;
  score = 0;
  frame = 0;
  gameOver = false;
  overlay.innerHTM
