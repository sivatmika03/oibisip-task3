<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Temperature Converter</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="converter">
        <h1>Temperature Converter</h1>
        <label for="inputTemp">Enter Temperature:</label>
        <input type="number" id="inputTemp" placeholder="Enter temperature..." />
        <select id="inputUnit">
            <option value="celsius">Celsius</option>
            <option value="fahrenheit">Fahrenheit</option>
        </select>
        <button id="convertButton">Convert</button>
        <p id="result"></p>
    </div>
    <script src="script.js"></script>
</body>
</html>

body {
    font-family: Arial, sans-serif;
    background-color: #f2f2f2;
    text-align: center;
    margin: 0;
    padding: 0;
}

.converter {
    background-color: #ffffff;
    border-radius: 10px;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.2);
    padding: 20px;
    margin: 50px auto;
    max-width: 400px;
}

h1 {
    font-size: 24px;
}

label {
    font-size: 18px;
}

input[type="number"] {
    width: 100%;
    padding: 10px;
    margin: 10px 0;
    border: 1px solid #ccc;
    border-radius: 5px;
}

select {
    width: 100%;
    padding: 10px;
    margin: 10px 0;
    border: 1px solid #ccc;
    border-radius: 5px;
}

button {
    background-color: #007bff;
    color: #fff;
    border: none;
    padding: 10px 20px;
    font-size: 18px;
    border-radius: 5px;
    cursor: pointer;
}

button:hover {
    background-color: #0056b3;
}

p#result {
    font-size: 24px;
    font-weight: bold;
    margin-top: 20px;
}

document.getElementById("convertButton").addEventListener("click", function() {
    // Get user input
    const inputTemp = parseFloat(document.getElementById("inputTemp").value);
    const inputUnit = document.getElementById("inputUnit").value;

    // Perform conversion
    let result;
    if (inputUnit === "celsius") {
        // Convert Celsius to Fahrenheit
        result = (inputTemp * 9/5) + 32;
    } else {
        // Convert Fahrenheit to Celsius
        result = (inputTemp - 32) * 5/9;
    }

    // Display the result
    document.getElementById("result").textContent = `Result: ${result.toFixed(2)}° ${inputUnit === "celsius" ? "Fahrenheit" : "Celsius"}`;
});
