<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hourly Rate Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin-top: 50px;
        }
        input {
            margin: 10px;
            padding: 5px;
            width: 100px;
        }
        button {
            padding: 10px;
            cursor: pointer;
        }
        #result {
            margin-top: 20px;
            font-size: 18px;
        }
        .green-text {
            color: green;
        }
    </style>
</head>
<body>

    <h2>Hourly Rate Calculator</h2>

    <label for="start">Start Time:</label>
    <input type="time" id="start" required>

    <label for="end">End Time:</label>
    <input type="time" id="end" required>

    <button onclick="calculateCost()">Calculate</button>

    <div id="result"></div>

    <script>
        function calculateCost() {
            const startTime = document.getElementById('start').value;
            const endTime = document.getElementById('end').value;
            const costPerHour = 7;

            const startDatetime = new Date(`2000-01-01T${startTime}`);
            const endDatetime = new Date(`2000-01-01T${endTime}`);

            const timeDifference = (endDatetime - startDatetime) / 3600000; // Convert milliseconds to hours

            const totalCost = timeDifference * costPerHour;

            document.getElementById('result').innerHTML = `The total cost for the given time period is: <span class="green-text">${totalCost.toFixed(2)} euros</span>`;
        }
    </script>

</body>
</html>
# -
