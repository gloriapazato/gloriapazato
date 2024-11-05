## Olá, eu Sou a Glória Pazato

- 🔭 Desenvolvedora de Software 
- 🔭 UFSM
- Apaixonada por tecnologia e pelo impacto positivo que um software de qualidade pode proporcionar, Glória se dedica a entregar produtos que realmente façam a diferença para os usuários. Sua expertise em desenvolvimento e testes automatizados, juntamente com sua capacidade analítica, permite que ela antecipe problemas e contribua para soluções ágeis e eficazes.Sempre disposta a aprender e a enfrentar novos desafios, Glória busca se aprofundar cada vez mais na área de desenvolvimento, visando crescer como profissional e expandir seu impacto no setor de tecnologia.

<div> 
  <a href="https://github.com/gloriapazato">
</div>
  
<div style= "display: inline_block"><br>
  <img algin="center" alt="Gloria-C" height ="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/c/c-original.svg" />
    <img algin="center" alt="Gloria-Js" height ="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" />
  <img algin="center" alt="Gloria-Ts" height ="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/typescript/typescript-original.svg" />
    <img  algin="center" alt="Gloria-Docker" height ="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/docker/docker-original.svg" />
</div>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Snake Game</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #333;
        }
        canvas {
            border: 2px solid #fff;
        }
    </style>
</head>
<body>
    <canvas id="game" width="400" height="400"></canvas>
    <script>
        const canvas = document.getElementById('game');
        const context = canvas.getContext('2d');

        const box = 20;
        let snake = [];
        snake[0] = { x: 9 * box, y: 10 * box };
        let direction;
        let food = {
            x: Math.floor(Math.random() * 19 + 1) * box,
            y: Math.floor(Math.random() * 19 + 1) * box
        };
        let score = 0;

        document.addEventListener('keydown', setDirection);

        function setDirection(event) {
            if (event.keyCode === 37 && direction !== 'RIGHT') direction = 'LEFT';
            else if (event.keyCode === 38 && direction !== 'DOWN') direction = 'UP';
            else if (event.keyCode === 39 && direction !== 'LEFT') direction = 'RIGHT';
            else if (event.keyCode === 40 && direction !== 'UP') direction = 'DOWN';
        }

        function collision(newHead, snake) {
            for (let i = 0; i < snake.length; i++) {
                if (newHead.x === snake[i].x && newHead.y === snake[i].y) return true;
            }
            return false;
        }

        function draw() {
            context.fillStyle = '#333';
            context.fillRect(0, 0, canvas.width, canvas.height);

            for (let i = 0; i < snake.leng
