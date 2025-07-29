<!DOCTYPE html>
<html>
<head>
    <title>Simple Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin-top: 50px;
        }
        input, select, button {
            margin: 10px;
            padding: 8px;
            font-size: 16px;
        }
    </style>
</head>
<body>

    <h2>Simple Calculator</h2>

    <input type="number" id="num1" placeholder="First number">
    
    <select id="operator">
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="*">*</option>
        <option value="/">/</option>
    </select>
    
    <input type="number" id="num2" placeholder="Second number">
    
    <button onclick="calculate()">Calculate</button>
    
    <h3 id="result">Result: </h3>

    <script>
        function calculate() {
            const num1 = parseFloat(document.getElementById('num1').value);
            const num2 = parseFloat(document.getElementById('num2').value);
            const operator = document.getElementById('operator').value;
            let result;

            if (isNaN(num1) || isNaN(num2)) {
                document.getElementById('result').innerText = "Result: Please enter valid numbers.";
                return;
            }

            switch (operator) {
                case '+':
                    result = num1 + num2;
                    break;
                case '-':
                    result = num1 - num2;
                    break;
                case '*':
                    result = num1 * num2;
                    break;
                case '/':
                    result = num2 !== 0 ? num1 / num2 : "Error (Divide by zero)";
                    break;
                default:
                    result = "Invalid operator";
            }

            document.getElementById('result').innerText = "Result: " + result;
        }
    </script>

</body>
</html>
