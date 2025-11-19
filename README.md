<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<title>MyStocks - Hisse Takip</title>
<style>
    body {
        margin: 0;
        background: #0d1117;
        font-family: Arial;
        color: #ffffff;
    }
    .container {
        max-width: 900px;
        margin: 25px auto;
        padding: 20px;
        background: #161b22;
        border-radius: 12px;
        box-shadow: 0 0 15px rgba(0,0,0,0.4);
    }
    h2 {
        text-align: center;
        color: #58a6ff;
        font-size: 28px;
    }
    input {
        width: 70%;
        padding: 12px;
        border: 1px solid #30363d;
        border-radius: 6px;
        background: #0d1117;
        color: white;
    }
    button {
        padding: 12px 20px;
        background: #238636;
        border: none;
        color: white;
        border-radius: 6px;
        cursor: pointer;
    }
    button:hover {
        background: #2ea043;
    }
    table {
        width: 100%;
        margin-top: 20px;
        border-collapse: collapse;
        color: #fff;
    }
    th, td {
        padding: 14px;
        border-bottom: 1px solid #30363d;
    }
    .remove {
        color: #ff5555;
        font-weight: bold;
        cursor: pointer;
    }
</style>
</head>
<body>

<div class="container">
    <h2>📈 MyStocks - Hisse Takip</h2>

    <input id="symbol" placeholder="Hisse sembolü (AAPL, TSLA, NVDA)">
    <button onclick="addStock()">Ekle</button>

    <table id="stockTable">
        <tr>
            <th>Hisse</th>
            <th>Fiyat</th>
            <th>Durum</th>
            <th>Sil</th>
        </tr>
    </table>
</div>

<script>
function addStock(){
    const s = document.getElementById("symbol").value.toUpperCase();
    if(!s) return;

    let row = `
        <tr id="${s}">
            <td>${s}</td>
            <td class="price">Bekleniyor...</td>
            <td>Takipte</td>
            <td class="remove" onclick="removeStock('${s}')">X</td>
        </tr>
    `;
    document.getElementById("stockTable").innerHTML += row;
    document.getElementById("symbol").value = "";
}

function removeStock(sym){
    document.getElementById(sym).remove();
}
</script>

</body>
</html>
