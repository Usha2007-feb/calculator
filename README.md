# calculator

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculator</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f4f4f4;
        }
        .calculator {
            width: 250px;
            background: #222;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.3);
        }
        .display {
            width: 100%;
            height: 50px;
            background: #333;
            color: white;
            text-align: right;
            padding: 10px;
            font-size: 1.5em;
            border-radius: 5px;
            margin-bottom: 10px;
        }
        .buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 10px;
        }
        button {
            padding: 15px;
            font-size: 1.2em;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            background: #444;
            color: white;
        }
        button:active {
            background: #666;
        }
        .equal {
            grid-column: span 2;
            background: #f39c12;
        }
    </style>
</head>
<body>
    <div class="calculator">
        <div class="display" id="display">0</div>
        <div class="buttons">
            <button onclick="clearDisplay()">C</button>
            <button onclick="appendValue('/')">/</button>
            <button onclick="appendValue('*')">*</button>
            <button onclick="appendValue('-')">-</button>
            <button onclick="appendValue('7')">7</button>
            <button onclick="appendValue('8')">8</button>
            <button onclick="appendValue('9')">9</button>
            <button onclick="appendValue('+')">+</button>
            <button onclick="appendValue('4')">4</button>
            <button onclick="appendValue('5')">5</button>
            <button onclick="appendValue('6')">6</button>
            <button onclick="appendValue('1')">1</button>
            <button onclick="appendValue('2')">2</button>
            <button onclick="appendValue('3')">3</button>
            <button onclick="appendValue('0')">0</button>
            <button onclick="appendValue('.')">.</button>
            <button class="equal" onclick="calculate()">=</button>
        </div>
    </div>
    <script>
        let display = document.getElementById('display');
        function appendValue(value) {
            if (display.innerText === '0') {
                display.innerText = value;
            } else {
                display.innerText += value;
            }
        }
        function clearDisplay() {
            display.innerText = '0';
        }
        function calculate() {
            try {
                display.innerText = eval(display.innerText);
            } catch {
                display.innerText = 'Error';
            }
        }
    </script>
</body>
</html>

