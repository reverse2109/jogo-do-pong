# meu-primeiro-repositorio

// Random Ball Placement
var xBall = Math.floor(Math.random() * 300) + 50;
var yBall = 50;
var xSpeed = (2, 7);
var ySpeed = (-7, -2);

// Canvas
function setup() {
  createCanvas(400, 400);
}

//Background

function draw() {

  // Background
  background(0);

  // Paddle
  fill('#ffffff');
  rect(mouseX, 375, 90, 15);

  //Functions
  move();
  display();
  bounce();
  //resetBall();
  paddle();
  
}
// Ball Functions
function move() {
  xBall += xSpeed;
  yBall += ySpeed;
}


function bounce() {

  if (xBall < 10 ||
    xBall > 400 - 10) {
    xSpeed *= -1;
  }
  if (yBall < 10 ||
    yBall > 400 - 10) {
    ySpeed *= -1;
  }
}
//}

function display() {
  fill(127423974);
  ellipse(xBall, yBall, 20, 20);
}

// Bounce off Paddle
function paddle() {
  if ((xBall > mouseX &&
      xBall < mouseX + 90) &&
    (yBall + 10 >= 375)) {
    xSpeed *= -1;
    ySpeed *= -1;

  }
}
