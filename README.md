<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Electricity Bill Calculator</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f6fb;
      margin: 20px;
    }
    table, td, th {
      border: 1px solid black;
      border-collapse: collapse;
      padding: 8px;
    }
    table {
      width: 100%;
      margin-top: 10px;
    }
    h1 {
      font-size: 22px;
      margin-bottom: 10px;
    }
    label {
      display: inline-block;
      width: 200px;
      font-weight: bold;
    }
    input[type="number"], input[type="text"] {
      width: 100%;
      padding: 8px;
      margin-bottom: 18px;
      border: 1px solid #bdc3c7;
      border-radius: 5px;
      font-size: 16px;
    }
    button {
      width: 100%;
      padding: 10px;
      background: #2980b9;
      color: #fff;
      border: none;
      border-radius: 5px;
      font-size: 16px;
      cursor: pointer;
      transition: background 0.2s;
    }
  </style>
</head>
<body>

  <h1>Electricity Bill Calculator</h1>

  <label>Month:</label>
  <input type="text" id="month"><br><br>

  <label>Power Consumption</label>
  <input type="number" id="power_consumption"><br><br>

  <label>cost_per_kwh</label>
  <input type="number" id="cost_per_kwh"><br><br>

  <button onclick="calculate()">Calculate</button>

  <h2>Result:</h2>
  <table>
    <tr>
      <th>Month</th>
      <th>Power Consumption</th>
      <th>Cost Per kWh</th>
      <th>Result</th>
    </tr>
    <tbody id="resultTable"></tbody>
  </table>

  <script>
    function calculate() {
      let month = document.getElementById("month").value;
      let power_consumption = +document.getElementById("power_consumption").value;
      let cost_per_kwh = +document.getElementById("cost_per_kwh").value;
      let result = power_consumption * cost_per_kwh;

      let table = document.getElementById("resultTable");
      let row = table.insertRow();
      row.insertCell(0).innerHTML = month;
      row.insertCell(1).innerHTML = power_consumption;
      row.insertCell(2).innerHTML = cost_per_kwh;
      row.insertCell(3).innerHTML = "₱ " + result.toFixed(2);
    }
  </script>

</body>
</html>