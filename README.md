# thaihat31.github.io
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>BMI Calculator</title>
    <style>
        body { font-family: Arial, sans-serif; max-width: 400px; margin: 40px auto; }
        h2 { text-align: center; }
        label { display: block; margin-top: 12px; }
        input { width: 100%; padding: 8px; margin-top: 4px; }
        button { margin-top: 16px; padding: 10px; width: 100%; cursor: pointer; }
        #result { margin-top: 20px; font-weight: bold; text-align: center; }
    </style>
</head>
<body>
    <h2>BMI Calculator</h2>
    <label>Height (cm)</label>
    <input type="number" id="height" placeholder="Enter your height" />

    <label>Weight (kg)</label>
    <input type="number" id="weight" placeholder="Enter your weight" />

    <button onclick="calculateBMI()">Calculate BMI</button>

    <div id="result"></div>

    <script>
        function calculateBMI() {
            const height = parseFloat(document.getElementById('height').value);
            const weight = parseFloat(document.getElementById('weight').value);

            if (!height || !weight) {
                document.getElementById('result').innerText = 'Please enter valid numbers!';
                return;
            }

            const bmi = weight / ((height / 100) ** 2);
            let status = '';

            if (bmi < 18.5) status = 'Underweight';
            else if (bmi < 24.9) status = 'Normal weight';
            else if (bmi < 29.9) status = 'Overweight';
            else status = 'Obesity';

            document.getElementById('result').innerText = `Your BMI: ${bmi.toFixed(2)} (Status: ${status})`;
        }
    </script>
</body>
</html>
