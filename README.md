# repository-1
the new project
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Simple Calculator</title>

<style>
    body {
        background: #f2f2f2;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        font-family: Arial, sans-serif;
    }

    .calculator {
        background: #222;
        padding: 20px;
        border-radius: 10px;
        box-shadow: 0 0 10px rgba(0,0,0,0.3);
    }

    #display {
        width: 100%;
        height: 60px;
        font-size: 30px;
        text-align: right;
        padding: 10px;
        border: none;
        border-radius: 8px;
        margin-bottom: 15px;
        background: #fff;
    }

    .buttons {
        display: grid;
        grid-template-columns: repeat(4, 70px);
        gap: 10px;
    }

    button {
        height: 60px;
        font-size: 22px;
        border: none;
        border-radius: 8px;
        cursor: pointer;
        background: #444;
        color: white;
        transition: 0.2s;
    }

    button:hover {
        background: #555;
    }

    .operator {
        background: #ff9500;
    }

    .operator:hover {
        background: #e08900;
    }

    .clear {
        background: #d9534f;
    }

    .clear:hover {
        background: #c9302c;
    }
</style>

</head>
<body>

<div class="calculator">
    <input type="text" id="display" disabled>

    <div class="buttons">
        <button class="clear" onclick="clearDisplay()">C</button>
        <button onclick="deleteLast()">⌫</button>
        <button onclick="appendValue('%')">%</button>
        <button class="operator" onclick="appendValue('/')">÷</button>

        <button onclick="appendValue('7')">7</button>
        <button onclick="appendValue('8')">8</button>
        <button onclick="appendValue('9')">9</button>
        <button class="operator" onclick="appendValue('*')">×</button>

        <button onclick="appendValue('4')">4</button>
        <button onclick="appendValue('5')">5</button>
        <button onclick="appendValue('6')">6</button>
        <button class="operator" onclick="appendValue('-')">−</button>

        <button onclick="appendValue('1')">1</button>
        <button onclick="appendValue('2')">2</button>
        <button onclick="appendValue('3')">3</button>
        <button class="operator" onclick="appendValue('+')">+</button>

        <button onclick="appendValue('0')" style="grid-column: span 2;">0</button>
        <button onclick="appendValue('.')">.</button>
        <button class="operator" onclick="calculate()">=</button>
    </div>
</div>

<script>
    const display = document.getElementById("display");

    function appendValue(value) {
        display.value += value;
    }

    function clearDisplay() {
        display.value = "";
    }

    function deleteLast() {
        display.value = display.value.slice(0, -1);
    }

    function calculate() {
        try {
            display.value = eval(display.value);
        } catch {
            display.value = "Error";
        }
    }
</script>

</body>
</html>

