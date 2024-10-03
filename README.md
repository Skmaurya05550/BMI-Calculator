# BMI Calculator

This project is a simple **Body Mass Index (BMI) Calculator** built using HTML, CSS, and JavaScript. The user inputs their weight (in kg) and height (in cm), and the calculator computes their BMI along with the corresponding health category.

## Features

- Input fields for weight and height
- Calculates BMI based on the inputs
- Displays the BMI category (Underweight, Normal weight, Overweight, or Obesity)
- Responsive design with a background image and user-friendly interface

## Preview

### Calculator Interface
![BMI Calculator Interface](https://i.ibb.co/f0d37VL/images.jpg)

### How It Works
![BMI Calculator GIF](https://example.com/your-gif-link.gif) <!-- Replace with the actual GIF link -->

## How to Use

1. Enter your **weight** in kilograms.
2. Enter your **height** in centimeters.
3. Click the **Calculate BMI** button to get your BMI and health category.

### Example:

- Weight: `55 kg`
- Height: `169 cm`
- Result: `BMI: 19.27 (Normal weight)`

## Code Overview

### HTML

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BMI Calculator</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <h1>BMI Calculator</h1>
    <input type="number" id="weight" placeholder="Weight in kg" min="1" required>
    <input type="number" id="height" placeholder="Height in cm" min="1" required>
    <br>
    <button onclick="calculateBMI()">Calculate BMI</button>
    <div id="output">
        <p>BMI: <span id="bmiValue"></span></p>
        <p>Category: <span id="bmiCategory"></span></p>
    </div>
    <script>
        function calculateBMI() {
            const weight = parseFloat(document.getElementById('weight').value);
            const heightCm = parseFloat(document.getElementById('height').value);

            if (isNaN(weight) || isNaN(heightCm) || weight <= 0 || heightCm <= 0) {
                alert("Please enter valid weight and height values.");
                return;
            }

            const heightM = heightCm / 100;
            const bmi = (weight / (heightM * heightM)).toFixed(2);

            document.getElementById('bmiValue').textContent = bmi;

            let category = '';
            if (bmi < 18.5) {
                category = 'Underweight';
            } else if (bmi >= 18.5 && bmi < 24.9) {
                category = 'Normal weight';
            } else if (bmi >= 25 && bmi < 29.9) {
                category = 'Overweight';
            } else {
                category = 'Obesity';
            }

            document.getElementById('bmiCategory').textContent = category;
        }
    </script>
</body>






</html>

