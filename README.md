<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Flappy Bird</title>
    <style>
        canvas {
            border: 1px solid black;
            display: block;
            margin: 0 auto;
        }
    </style>
</head>
<body>
    <canvas id="canvas" width="480" height="320"></canvas>

    <script>
        var canvas = document.getElementById("canvas");
        var ctx = canvas.getContext("2d");

        // Bird properties
        var bird = {
            x: 50,
            y: canvas.height / 2,
            radius: 20,
            velocity: 0,
            gravity: 0.5
        };

        // Draw bird
        function drawBird() {
            ctx.beginPath();
            ctx.arc(bird.x, bird.y, bird.radius, 0, Math.PI * 2);
            ctx.fillStyle = "yellow";
            ctx.fill();
            ctx.closePath();
        }

        // Draw background
        function drawBackground() {
            ctx.fillStyle = "lightblue";
            ctx.fillRect(0, 0, canvas.width, canvas.height);
        }

        // Game loop
        function draw() {
            drawBackground();
            drawBird();

            // Update bird position
            bird.velocity += bird.gravity;
            bird.y += bird.velocity;

            requestAnimationFrame(draw);
        }

        draw(); // Start the game loop
    </script>
</body>
</html>
