<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Moving Quote Calculator</title>
  <style>
    body { font-family: Arial, sans-serif; max-width: 600px; margin: auto; padding: 20px; }
    h2 { color: #333; }
    label { display: block; margin-top: 10px; }
    input { width: 100%; padding: 8px; margin-top: 5px; }
    button { margin-top: 20px; padding: 10px 20px; background-color: #007bff; color: white; border: none; cursor: pointer; }
    button:hover { background-color: #0056b3; }
    .result { margin-top: 20px; font-weight: bold; }
  </style>
</head>
<body>
  <h2>Moving Quote Calculator</h2>
  <label for="callout">Distance from Cranbourne to Pickup (km):</label>
  <input type="number" id="callout" placeholder="e.g. 110">

  <label for="travel">Distance from Pickup to Drop-off (km):</label>
  <input type="number" id="travel" placeholder="e.g. 130">

  <label for="hours">Labour Hours (min 2):</label>
  <input type="number" id="hours" min="2" placeholder="e.g. 2">

  <button onclick="calculateQuote()">Calculate Quote</button>

  <div class="result" id="result"></div>

  <script>
    function calculateQuote() {
      const callout = parseFloat(document.getElementById('callout').value) || 0;
      const travel = parseFloat(document.getElementById('travel').value) || 0;
      const hours = Math.max(2, parseFloat(document.getElementById('hours').value) || 2);

      const calloutFee = callout * 1;
      const travelCost = travel * 2;
      const labourCost = 2 * 40 * hours;
      const total = calloutFee + travelCost + labourCost;

      document.getElementById('result').innerText = `Total Estimated Cost: $${total.toFixed(2)}`;
    }
  </script>
</body>
</html>
