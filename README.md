# rzroheet-calculator
<!DOCTYPE html>
<html>
<head>
    <title>RZROHEET | Delivery Calculator</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', sans-serif;
        }

        body {
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            background: linear-gradient(-45deg, #1e3c72, #2a5298, #0f2027, #203a43);
            background-size: 400% 400%;
            animation: gradientBG 10s ease infinite;
        }

        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(15px);
            padding: 40px;
            width: 380px;
            border-radius: 20px;
            box-shadow: 0 8px 32px rgba(0,0,0,0.3);
            color: white;
            text-align: center;
        }

        .logo {
            width: 80px;
            height: 80px;
            background: white;
            color: #1e3c72;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-size: 14px;
            margin: 0 auto 20px;
            letter-spacing: 1px;
        }

        h2 {
            margin-bottom: 20px;
        }

        input {
            width: 100%;
            padding: 12px;
            margin: 10px 0;
            border-radius: 8px;
            border: none;
            outline: none;
            font-size: 14px;
        }

        button {
            width: 100%;
            padding: 12px;
            margin-top: 15px;
            border-radius: 8px;
            border: none;
            background: #00c6ff;
            background: linear-gradient(to right, #00c6ff, #0072ff);
            color: white;
            font-weight: bold;
            cursor: pointer;
            transition: 0.3s;
        }

        button:hover {
            transform: scale(1.05);
        }

        .result {
            margin-top: 20px;
            font-size: 15px;
            line-height: 1.6;
        }

        .footer {
            margin-top: 15px;
            font-size: 12px;
            opacity: 0.8;
        }

    </style>
</head>

<body>

<div class="card">
    <div class="logo">RZROHEET</div>
    <h2>Delivery % Calculator</h2>

    <input type="number" id="total" placeholder="Enter Total Delivery">
    <input type="number" id="dac" placeholder="Enter DAC Delivery">
    <input type="number" id="manual" placeholder="Enter Manual Delivery">

    <button onclick="calculate()">Calculate</button>

    <div class="result" id="output"></div>
    <div class="footer">© 2026 RZROHEET</div>
</div>

<script>
    function calculate() {
        let total = parseFloat(document.getElementById("total").value);
        let dac = parseFloat(document.getElementById("dac").value);
        let manual = parseFloat(document.getElementById("manual").value);

        if (isNaN(total) || total <= 0) {
            alert("Please enter valid Total Delivery");
            return;
        }

        let dacPercent = ((dac / total) * 100).toFixed(2);
        let manualPercent = ((manual / total) * 100).toFixed(2);
        let remainingPercent = (100 - dacPercent - manualPercent).toFixed(2);

        document.getElementById("output").innerHTML =
            "📦 DAC Delivery: " + dacPercent + "%<br>" +
            "🛠 Manual Delivery: " + manualPercent + "%<br>" +
            "📊 Remaining: " + remainingPercent + "%";
    }
</script>

</body>
</html>
