<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Evaluador de Proyectos</title>

<style>
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    font-family: 'Segoe UI', sans-serif;
    background: linear-gradient(135deg, #0f2027, #203a43, #2c5364);
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: flex-start;
}

/* CONTENEDOR */
.container {
    width: 100%;
    max-width: 420px;
    margin: 20px;
    background: #ffffff;
    padding: 20px;
    border-radius: 12px;
    box-shadow: 0 10px 30px rgba(0,0,0,0.3);
}

/* TITULO */
h2 {
    text-align: center;
    color: #2c5364;
    font-size: 20px;
    margin-bottom: 20px;
}

/* LABEL */
label {
    font-size: 13px;
    font-weight: bold;
    color: #555;
}

/* INPUT */
input {
    width: 100%;
    padding: 14px;
    margin: 6px 0 15px;
    border-radius: 10px;
    border: 1px solid #ccc;
    font-size: 16px;
}

/* BOTONES */
button {
    width: 100%;
    padding: 14px;
    border-radius: 10px;
    border: none;
    font-size: 16px;
    font-weight: bold;
    margin-top: 8px;
    cursor: pointer;
}

/* BOTÓN PRINCIPAL */
#btn {
    background: #2c5364;
    color: white;
}

/* BOTÓN RESET */
#resetBtn {
    background: #ecf0f1;
}

/* RESULTADO */
.result {
    margin-top: 20px;
    padding: 15px;
    border-radius: 10px;
    background: #f4f6f8;
    font-size: 14px;
    line-height: 1.5;
}

/* COLORES */
.good { color: #1b8a3b; font-weight: bold; }
.bad { color: #c0392b; font-weight: bold; }
.neutral { color: #555; font-weight: bold; }

/* TABLET */
@media (min-width: 600px) {
    .container {
        max-width: 500px;
        padding: 25px;
    }

    h2 {
        font-size: 22px;
    }
}

/* DESKTOP */
@media (min-width: 900px) {
    body {
        align-items: center;
    }

    .container {
        max-width: 550px;
        padding: 30px;
    }

    h2 {
        font-size: 24px;
    }
}
</style>
</head>

<body>

<div class="container">
    <h2>Evaluador de Proyectos</h2>

    <label>Inversión Inicial</label>
    <input id="investment" placeholder="Ej: 1000">

    <label>Flujos de Caja</label>
    <input id="cashflows" placeholder="Ej: 300,400,500">

    <label>Tasa de Descuento</label>
    <input id="rate" placeholder="Ej: 0.1">

    <button id="btn">Evaluar Proyecto</button>
    <button id="resetBtn">Limpiar / Reiniciar</button>

    <div class="result" id="result"></div>
</div>

<script>

document.getElementById("btn").addEventListener("click", evaluate);
document.getElementById("resetBtn").addEventListener("click", resetForm);

function resetForm() {
    document.getElementById("investment").value = "";
    document.getElementById("cashflows").value = "";
    document.getElementById("rate").value = "";
    document.getElementById("result").innerHTML = "";
}

function npv(rate, cashflows) {
    let total = 0;
    for (let t = 0; t < cashflows.length; t++) {
        total += cashflows[t] / Math.pow(1 + rate, t);
    }
    return total;
}

function irr(cashflows) {
    let rate = 0.1;

    for (let i = 0; i < 1000; i++) {
        let f = 0;
        let df = 0;

        for (let t = 0; t < cashflows.length; t++) {
            f += cashflows[t] / Math.pow(1 + rate, t);
            df += -t * cashflows[t] / Math.pow(1 + rate, t + 1);
        }

        if (df === 0) return null;

        let newRate = rate - f / df;

        if (Math.abs(newRate - rate) < 1e-6) {
            return newRate;
        }

        rate = newRate;
    }

    return null;
}

function evaluate() {

    const investment = parseFloat(document.getElementById("investment").value);
    const rawFlows = document.getElementById("cashflows").value;
    const rate = parseFloat(document.getElementById("rate").value);

    if (isNaN(investment) || !rawFlows || isNaN(rate)) {
        alert("Completa todos los campos correctamente");
        return;
    }

    let flows = rawFlows.split(",").map(x => parseFloat(x.trim()));

    if (flows.some(isNaN)) {
        alert("Flujos inválidos");
        return;
    }

    const cashflows = [-investment, ...flows];

    const npvValue = npv(rate, cashflows);
    const irrValue = irr(cashflows);

    let irrText = irrValue !== null
        ? (irrValue * 100).toFixed(2) + "%"
        : "No calculable";

    let decision, css, explanation;

    if (npvValue > 0) {
        decision = "✔ Conviene invertir";
        css = "good";
        explanation = `Generas valor de ${npvValue.toFixed(2)}. TIR (${irrText}) > tasa (${(rate*100).toFixed(2)}%).`;
    } else if (npvValue < 0) {
        decision = "✖ No conviene invertir";
        css = "bad";
        explanation = `Faltan ${Math.abs(npvValue).toFixed(2)}. TIR (${irrText}) < tasa (${(rate*100).toFixed(2)}%).`;
    } else {
        decision = "➖ Proyecto indiferente";
        css = "neutral";
        explanation = "Recuperas exactamente lo invertido.";
    }

    document.getElementById("result").innerHTML = `
        <p><strong>VAN:</strong> ${npvValue.toFixed(2)}</p>
        <p><strong>TIR:</strong> ${irrText}</p>
        <p class="${css}">${decision}</p>
        <hr>
        <p>${explanation}</p>
    `;
}

</script>

</body>
</html>