;Pasos para crear un juego en 2d, donde vamos a a ver paso a paso como se desarrolla este.

EL HTML DEL JUEGO
podemos resumir esto en crear una pagina html donde vamos a utilizar java script para crear el juego
vamos a crear la bola y la vamos a hacer mover, la bola se dibuja cada 10 milisegundos, por eso hace parecer que esta se moviera.
El codigo hasta este punto es el siguiente.


!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <title>Gamedev Canvas Workshop</title>
    <style>
    	* { padding: 0; margin: 0; }
    	canvas { background: #eee; display: block; margin: 0 auto; }
    </style>
</head>
<body>

<canvas id="myCanvas" width="480" height="320"></canvas>

<script>
var canvas = document.getElementById("myCanvas");
var ctx = canvas.getContext("2d");
var x = canvas.width/2;
var y = canvas.height-30;
var dx = 2;
var dy = -2;

function drawBall() {
    ctx.beginPath();
    ctx.arc(x, y, 10, 0, Math.PI*2);
    ctx.fillStyle = "#0095DD";
    ctx.fill();
    ctx.closePath();
}

function draw() {
    ctx.clearRect(0, 0, canvas.width, canvas.height);
    drawBall();
    x += dx;
    y += dy;
}

setInterval(draw, 10);
</script>

</body>
</html>
