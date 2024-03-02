<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Pac-Man Animation</title>
<style>
  .pacman-container {
    position: relative;
    width: 100px;
    height: 100px;
    background-color: black;
    border-radius: 50%;
    overflow: hidden;
  }
  
  .pacman {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: yellow;
    border-radius: 50%;
    animation: eat 0.5s infinite alternate;
  }
  
  @keyframes eat {
    0% {
      transform: rotate(45deg);
    }
    100% {
      transform: rotate(-45deg);
    }
  }
</style>
</head>
<body>
<div class="pacman-container">
  <div class="pacman"></div>
</div>
</body>
</html>

