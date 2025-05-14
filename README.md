<!DOCTYPE html>
<html lang="ar">
<head>
  <meta charset="UTF-8">
  <title>حساب زاوية ميل السطح</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      direction: rtl;
      background-color: #f2f2f2;
      text-align: center;
      padding: 50px;
    }
    .container {
      background: #fff;
      padding: 30px;
      border-radius: 10px;
      width: 300px;
      margin: auto;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }
    input, button {
      margin: 10px 0;
      padding: 10px;
      width: 90%;
      border-radius: 5px;
      border: 1px solid #ccc;
    }
    .result {
      margin-top: 20px;
      font-weight: bold;
    }
  </style>
</head>
<body>

  <div class="container">
    <h2>حساب زاوية ميل السطح</h2>
    <label>الارتفاع (ارتفاع السطح):</label>
    <input type="number" id="height" placeholder="مثال: 3" step="any">
    
    <label>القاعدة (الطول الأفقي):</label>
    <input type="number" id="base" placeholder="مثال: 4" step="any">
    
    <button onclick="calculateTilt()">احسب الزاوية</button>
    
    <div class="result" id="result"></div>
  </div>

  <script>
    function calculateTilt() {
      const height = parseFloat(document.getElementById("height").value);
      const base = parseFloat(document.getElementById("base").value);
      const resultDiv = document.getElementById("result");

      if (isNaN(height) || isNaN(base) || base === 0) {
        resultDiv.textContent = "يرجى إدخال قيم صحيحة.";
        return;
      }

      const angleRad = Math.atan(height / base);
      const angleDeg = angleRad * (180 / Math.PI);

      resultDiv.textContent = "زاوية الميل: " + angleDeg.toFixed(2) + "°";
    }
  </script>

</body>
</html>
