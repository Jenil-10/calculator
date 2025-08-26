# calculator
name- jenil pio
register number-212223220040
# program
```
### index.html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Modern Calculator</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="calculator">
        <h1>🧮 Simple Calculator</h1>
        <div class="input-section">
            <div class="input-group">
                <label for="number1">First Number</label>
                <input type="number" id="number1" placeholder="0" step="any">
            </div>
            <div class="input-group">
                <label for="number2">Second Number</label>
                <input type="number" id="number2" placeholder="0" step="any">
            </div>
        </div>
        <div class="operation-section">
            <h3>Select Operation</h3>
            <div class="operation-grid">
                <button class="operation-btn" data-operation="add"><span>➕</span> Addition</button>
                <button class="operation-btn" data-operation="subtract"><span>➖</span> Subtraction</button>
                <button class="operation-btn" data-operation="multiply"><span>✖️</span> Multiplication</button>
                <button class="operation-btn" data-operation="divide"><span>➗</span> Division</button>
            </div>
        </div>
        <div class="calculate-section">
            <button class="calculate-btn" onclick="calculate()">🚀 Calculate Result</button>
        </div>
        <div class="result-section" id="resultSection">
            <div class="result-label">Result</div>
            <div class="result-display" id="result">Ready to calculate...</div>
        </div>
    </div>
    <script src="script.js"></script>
</body>
</html>

### style.css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    background: linear-gradient(135deg, #1e3c72 0%, #2a5298 100%);
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 20px;
}

.calculator {
    background: linear-gradient(145deg, #2d3748, #1a202c);
    padding: 35px;
    border-radius: 25px;
    box-shadow: 0 25px 50px rgba(0, 0, 0, 0.3),
                inset 0 1px 0 rgba(255, 255, 255, 0.1);
    max-width: 450px;
    width: 100%;
    border: 1px solid rgba(255, 255, 255, 0.1);
}

.calculator h1 {
    text-align: center;
    color: #f7fafc;
    margin-bottom: 35px;
    font-size: 2.2rem;
    font-weight: 700;
    text-shadow: 0 2px 4px rgba(0, 0, 0, 0.3);
}

.input-section {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
    margin-bottom: 30px;
}

.input-group {
    position: relative;
}

.input-group label {
    display: block;
    margin-bottom: 8px;
    color: #cbd5e0;
    font-weight: 600;
    font-size: 14px;
    text-transform: uppercase;
    letter-spacing: 0.5px;
}

.input-group input {
    width: 100%;
    padding: 16px 20px;
    background: rgba(255, 255, 255, 0.05);
    border: 2px solid rgba(255, 255, 255, 0.1);
    border-radius: 15px;
    font-size: 18px;
    color: #f7fafc;
    transition: all 0.3s ease;
    backdrop-filter: blur(10px);
}

.input-group input::placeholder {
    color: #a0aec0;
}

.input-group input:focus {
    outline: none;
    border-color: #4299e1;
    background: rgba(255, 255, 255, 0.1);
    box-shadow: 0 0 0 3px rgba(66, 153, 225, 0.1);
}

.operation-section {
    margin-bottom: 30px;
}

.operation-section h3 {
    color: #cbd5e0;
    font-weight: 600;
    font-size: 14px;
    text-transform: uppercase;
    letter-spacing: 0.5px;
    margin-bottom: 15px;
    text-align: center;
}

.operation-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 12px;
}

.operation-btn {
    padding: 18px 24px;
    background: rgba(255, 255, 255, 0.05);
    border: 2px solid rgba(255, 255, 255, 0.1);
    border-radius: 15px;
    cursor: pointer;
    font-size: 16px;
    font-weight: 600;
    transition: all 0.3s ease;
    color: #e2e8f0;
    backdrop-filter: blur(10px);
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 8px;
}

.operation-btn:hover {
    background: rgba(255, 255, 255, 0.1);
    border-color: #4299e1;
    transform: translateY(-2px);
}

.operation-btn.active {
    background: linear-gradient(135deg, #4299e1, #3182ce);
    border-color: #4299e1;
    color: #fff;
    box-shadow: 0 8px 25px rgba(66, 153, 225, 0.3);
}

.calculate-section {
    margin-bottom: 25px;
}

.calculate-btn {
    width: 100%;
    padding: 20px;
    background: linear-gradient(135deg, #48bb78, #38a169);
    color: #fff;
    border: none;
    border-radius: 15px;
    font-size: 18px;
    font-weight: 700;
    cursor: pointer;
    transition: all 0.3s ease;
    text-transform: uppercase;
    letter-spacing: 1px;
    box-shadow: 0 8px 25px rgba(72, 187, 120, 0.3);
}

.calculate-btn:hover {
    transform: translateY(-3px);
    box-shadow: 0 12px 35px rgba(72, 187, 120, 0.4);
}

.calculate-btn:active {
    transform: translateY(-1px);
}

.result-section {
    background: rgba(0, 0, 0, 0.2);
    padding: 25px;
    border-radius: 15px;
    border: 1px solid rgba(255, 255, 255, 0.1);
    backdrop-filter: blur(10px);
}

.result-label {
    color: #cbd5e0;
    font-weight: 600;
    font-size: 14px;
    text-transform: uppercase;
    letter-spacing: 0.5px;
    margin-bottom: 10px;
}

.result-display {
    font-size: 20px;
    color: #f7fafc;
    font-weight: 600;
    min-height: 30px;
    display: flex;
    align-items: center;
    word-break: break-all;
}

.result-section.error .result-display {
    color: #fc8181;
}

.result-section.success .result-display {
    color: #68d391;
}

@media (max-width: 520px) {
    .calculator {
        padding: 25px 20px;
    }
    .calculator h1 {
        font-size: 1.8rem;
    }
    .input-section {
        grid-template-columns: 1fr;
        gap: 15px;
    }
    .operation-grid {
        grid-template-columns: 1fr;
    }
}

### script.js
let selectedOperation = null;

document.querySelectorAll('.operation-btn').forEach(btn => {
    btn.addEventListener('click', function() {
        document.querySelectorAll('.operation-btn').forEach(b => b.classList.remove('active'));
        this.classList.add('active');
        selectedOperation = this.dataset.operation;
    });
});

document.querySelectorAll('input').forEach(input => {
    input.addEventListener('keypress', function(e) {
        if (e.key === 'Enter') {
            calculate();
        }
    });
});

function calculate() {
    const num1 = parseFloat(document.getElementById('number1').value);
    const num2 = parseFloat(document.getElementById('number2').value);
    const resultElement = document.getElementById('result');
    const resultSection = document.getElementById('resultSection');

    resultSection.classList.remove('error', 'success');

    if (isNaN(num1) || isNaN(num2)) {
        resultElement.textContent = '⚠️ Please enter valid numbers in both fields';
        resultSection.classList.add('error');
        return;
    }

    if (!selectedOperation) {
        resultElement.textContent = '⚠️ Please select an operation first';
        resultSection.classList.add('error');
        return;
    }

    let result;
    let operationSymbol;

    switch (selectedOperation) {
        case 'add':
            result = num1 + num2;
            operationSymbol = '+';
            break;
        case 'subtract':
            result = num1 - num2;
            operationSymbol = '−';
            break;
        case 'multiply':
            result = num1 * num2;
            operationSymbol = '×';
            break;
        case 'divide':
            if (num2 === 0) {
                resultElement.textContent = '❌ Cannot divide by zero';
                resultSection.classList.add('error');
                return;
            }
            result = num1 / num2;
            operationSymbol = '÷';
            break;
        default:
            resultElement.textContent = '❌ Invalid operation selected';
            resultSection.classList.add('error');
            return;
    }

    const formattedResult = Number.isInteger(result)
        ? result.toLocaleString()
        : parseFloat(result.toFixed(8)).toLocaleString();

    resultElement.textContent = `${num1.toLocaleString()} ${operationSymbol} ${num2.toLocaleString()} = ${formattedResult}`;
    resultSection.classList.add('success');
}
```
# output
![WhatsApp Image 2025-08-26 at 8 41 21 PM](https://github.com/user-attachments/assets/f8ca8470-3946-4e46-9a71-66e00d262b71)
