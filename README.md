<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rock Paper Scissors</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
        }
        button {
            margin: 10px;
            padding: 10px 20px;
            font-size: 16px;
            cursor: pointer;
        }
        #result {
            font-size: 20px;
            font-weight: bold;
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <h1>Rock Paper Scissors</h1>
    <button onclick="play('rock')">Rock</button>
    <button onclick="play('paper')">Paper</button>
    <button onclick="play('scissors')">Scissors</button>
    <div id="result"></div>

    <script>
        function play(playerChoice) {
            const choices = ['rock', 'paper', 'scissors'];
            const computerChoice = choices[Math.floor(Math.random() * choices.length)];

            let result = '';
            if (playerChoice === computerChoice) {
                result = "It's a tie!";
            } else if (
                (playerChoice === 'rock' && computerChoice === 'scissors') ||
                (playerChoice === 'paper' && computerChoice === 'rock') ||
                (playerChoice === 'scissors' && computerChoice === 'paper')
            ) {
                result = "You win!";
            } else {
                result = "Computer wins!";
            }

            document.getElementById('result').innerText = `You chose ${playerChoice}, computer chose ${computerChoice}. ${result}`;
        }
    </script>
</body>
</html>
