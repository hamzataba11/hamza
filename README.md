<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>آلة حاسبة</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f5f5f5;
        }
        #calculator {
            background-color: #fff;
            border-radius: 10px;
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.1);
            padding: 20px;
            width: 300px;
        }
        #display {
            width: 100%;
            height: 50px;
            margin-bottom: 20px;
            font-size: 24px;
            text-align: left;
            padding: 5px;
            border: 1px solid #ddd;
            border-radius: 5px;
        }
        .buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 10px;
        }
        button {
            height: 50px;
            font-size: 18px;
            border: none;
            border-radius: 5px;
            background-color: #f0f0f0;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        button:hover {
            background-color: #e0e0e0;
        }
        .operator {
            background-color: #ff9800;
            color: white;
        }
        .operator:hover {
            background-color: #f57c00;
        }
        .equals {
            background-color: #4caf50;
            color: white;
        }
        .equals:hover {
            background-color: #388e3c;
        }
    </style>
</head>
<body>
    <div id="calculator">
        <input type="text" id="display" readonly>
        <div class="buttons">
            <button onclick="appendToDisplay('7')">7</button>
            <button onclick="appendToDisplay('8')">8</button>
            <button onclick="appendToDisplay('9')">9</button>
            <button onclick="appendToDisplay('+')" class="operator">+</button>
            <button onclick="appendToDisplay('4')">4</button>
            <button onclick="appendToDisplay('5')">5</button>
            <button onclick="appendToDisplay('6')">6</button>
            <button onclick="appendToDisplay('-')" class="operator">-</button>
            <button onclick="appendToDisplay('1')">1</button>
            <button onclick="appendToDisplay('2')">2</button>
            <button onclick="appendToDisplay('3')">3</button>
            <button onclick="appendToDisplay('*')" class="operator">×</button>
            <button onclick="clearDisplay()">C</button>
            <button onclick="appendToDisplay('0')">0</button>
            <button onclick="calculate()" class="equals">=</button>
            <button onclick="appendToDisplay('/')" class="operator">÷</button>
        </div>
    </div>

    <script>
        let currentInput = "";
        
        function appendToDisplay(value) {
            currentInput += value;
            document.getElementById("display").value = currentInput;
        }
        
        function clearDisplay() {
            currentInput = "";
            document.getElementById("display").value = "";
        }
        
        function calculate() {
            try {
                const result = eval(currentInput);
                document.getElementById("display").value = result;
                currentInput = result.toString();
            } catch (error) {
                alert("عملية غير صالحة!");
                clearDisplay();
            }
        }
    </script>
</body>
</html>
