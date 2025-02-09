Hi there! 👋

🚀 About Me

I am a passionate developer and innovator with expertise in:

Literally i wanted to tell but i can't so Sorry

🔥 Current Projects

Sorry But i never wanted to reveal Now..beacuse i want to learn and learn.

🌟 Connect With Me

GitHub: Your GitHub Profile

LinkedIn: Your LinkedIn Profile

Twitter: Your Twitter Handle

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sliding Game</title>
    <style>
        body { display: flex; justify-content: center; align-items: center; height: 100vh; background: #f4f4f4; }
        .game { display: grid; grid-template-columns: repeat(4, 80px); gap: 5px; }
        .tile { width: 80px; height: 80px; background: #3498db; color: white; display: flex; align-items: center; justify-content: center; font-size: 24px; cursor: pointer; }
    </style>
</head>
<body>
    <div class="game" id="game"></div>
    <script>
        const game = document.getElementById('game');
        let numbers = [...Array(15).keys()].map(n => n + 1).concat('');
        numbers.sort(() => Math.random() - 0.5);
        function render() {
            game.innerHTML = '';
            numbers.forEach(num => {
                const tile = document.createElement('div');
                tile.className = 'tile';
                tile.textContent = num;
                tile.onclick = () => move(num);
                game.appendChild(tile);
            });
        }
        function move(num) {
            const index = numbers.indexOf(num);
            const emptyIndex = numbers.indexOf('');
            const validMoves = [emptyIndex - 1, emptyIndex + 1, emptyIndex - 4, emptyIndex + 4];
            if (validMoves.includes(index)) {
                [numbers[index], numbers[emptyIndex]] = [numbers[emptyIndex], numbers[index]];
                render();
            }
        }
        render();
    </script>
</body>
</html>
