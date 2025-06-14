# Web-Development-3
Prepare for resume 
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Blue Calculator</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background-color: #e0f7ff;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }
    .calculator {
      background-color: #2196f3;
      padding: 20px;
      border-radius: 20px;
      box-shadow: 0px 0px 20px rgba(0,0,0,0.3);
      width: 280px;
    }
    #display {
      width: 100%;
      height: 50px;
      border: none;
      border-radius: 10px;
      font-size: 1.5em;
      padding: 10px;
      text-align: right;
      background-color: #e3f2fd;
      color: #000;
      margin-bottom: 15px;
    }
    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 10px;
    }
    button {
      padding: 20px;
      font-size: 1.2em;
      border: none;
      border-radius: 10px;
      background-color: #1976d2;
      color: #fff;
      cursor: pointer;
      transition: background-color 0.3s ease;
    }
    button:hover {
      background-color: #1565c0;
    }
    .equal {
      grid-column: span 2;
      background-color: #4caf50;
    }
    .equal:hover {
      background-color: #43a047;
    }
  </style>
</head>
<body>
  <div class="calculator">
    <input type="text" id="display" disabled value="0">
    <div class="buttons">
      <button onclick="appendValue('7')">7</button>
      <button onclick="appendValue('8')">8</button>
      <button onclick="appendValue('9')">9</button>
      <button onclick="appendValue('+')">+</button>

      <button onclick="appendValue('4')">4</button>
      <button onclick="appendValue('5')">5</button>
      <button onclick="appendValue('6')">6</button>
      <button onclick="appendValue('-')">-</button>

      <button onclick="appendValue('1')">1</button>
      <button onclick="appendValue('2')">2</button>
      <button onclick="appendValue('3')">3</button>
      <button onclick="calculate()" class="equal">=</button>

      <button onclick="appendValue('0')">0</button>
      <button onclick="clearDisplay()">C</button>
    </div>
  </div>

  <script>
    let display = document.getElementById('display');

    function appendValue(value) {
      if (display.value === "0") {
        display.value = value;
      } else {
        display.value += value;
      }
    }

    function clearDisplay() {
      display.value = "0";
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
