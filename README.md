# Online-xerox-kioski-
Online Xerox &amp; Printing Service
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Online Xerox Kiosk</title>
<script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
<style>
body{font-family:Arial;margin:0;background:#f2f5f9}
header{background:#0d6efd;color:#fff;padding:18px;text-align:center}
.container{max-width:600px;margin:30px auto;background:#fff;padding:25px;border-radius:12px;box-shadow:0 5px 15px rgba(0,0,0,0.1)}
label{font-weight:bold;display:block;margin-top:15px}
input,select{width:100%;padding:10px;margin-top:5px;border:1px solid #ccc;border-radius:8px}
.radio-group{margin-top:8px}
button{margin-top:20px;background:#0d6efd;color:#fff;border:none;padding:12px;width:100%;border-radius:10px;font-size:16px;cursor:pointer}
button:hover{background:#084298}
.result{margin-top:20px;padding:15px;background:#e9f2ff;border-radius:10px;font-size:18px;text-align:center}
.qrbox{text-align:center;margin-top:20px}
footer{text-align:center;margin-top:20px;color:#555}
</style>
</head>
<body>
<header>
<h1>Quick Print Online Xerox</h1>
<p>Scan QR → Upload → Print</p>
</header>

<div class="container">
<div class="qrbox">
<h3>Scan to Upload File</h3>
<div id="qrcode"></div>
<p>Scan this code using phone camera</p>
</div>

<form id="xeroxForm">
<label>Upload Document</label>
<input type="file" id="file" required />

<label>Number of Copies</label>
<input type="number" id="copies" min="1" value="1" required />

<label>Printing Type</label>
<div class="radio-group">
<input type="radio" name="side" value="single" checked> Single Side<br>
<input type="radio" name="side" value="double"> Double Side
</div>

<button type="button" onclick="calculateCost()">Calculate Cost</button>
</form>

<div class="result" id="result">Total Cost: ₹0</div>
</div>

<footer>
<p>© 2026 Quick Print Xerox Kiosk</p>
</footer>

<script>
// Generate QR code of current page link
new QRCode(document.getElementById("qrcode"), window.location.href);

function calculateCost(){
let copies = parseInt(document.getElementById('copies').value);
let pricePerCopy = 2;
let cost = copies * pricePerCopy;
document.getElementById('result').innerHTML = "Total Cost: ₹" + cost + " (₹2 per copy)";
}
</script>
</body>
</html>
