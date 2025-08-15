# quer-ficar-cmg...
paia de fazer...
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>quer ficar cmg</title>
<style>
    body {
        font-family: Arial, sans-serif;
        text-align: center;
        margin-top: 30px;
        background-color: #f0f0f0;
    }
    #caixa {
        background: white;
        padding: 25px;
        border-radius: 15px;
        box-shadow: 0 0 15px rgba(0,0,0,0.2);
        display: inline-block;
        max-width: 90%;
    }
    #pergunta {
        font-size: 28px;
        margin-bottom: 25px;
        font-weight: bold;
    }
    .btn {
        padding: 15px 30px;
        font-size: 22px;
        margin: 12px;
        border: none;
        cursor: pointer;
        border-radius: 10px;
        transition: transform 0.2s;
        width: 40%;
    }
    .btn:hover {
        transform: scale(1.1);
    }
    .sim {
        background-color: #28a745;
        color: white;
    }
    .nao {
        background-color: #dc3545;
        color: white;
    }
</style>
</head>
<body>

<div id="caixa">
    <div id="pergunta">Você gosta de mim?</div>
    <button class="btn sim" id="btnSim">Sim</button>
    <button class="btn nao" id="btnNao">Não</button>
</div>

<script>
    const perguntas = [
        { texto: "Você gosta de mim?", sim: "eu também", nao: "tem certeza?" },
        { texto: "tem certeza?", sim: "ufaa, eu também", nao: "mesmo?" },
        { texto: "mesmo?", sim: "ufaa, eu também", nao: "malvada!" },
        { texto: "malvada!", sim: "ufaa, eu também", nao: "por favor?" },
        { texto: "por favor?", sim: "ufaa, eu também", nao: "nossa T-T" },
        { texto: "nossa T-T", sim: "ufaa, eu também", nao: "por favor?" }
    ];

    let etapa = 0;
    let tamanhoSim = 22; // tamanho inicial da fonte do botão "Sim"

    const perguntaEl = document.getElementById("pergunta");
    const btnSim = document.getElementById("btnSim");
    const btnNao = document.getElementById("btnNao");

    function mostrarPergunta(texto) {
        perguntaEl.textContent = texto;
    }

    function mostrarResposta(texto) {
        perguntaEl.textContent = texto;
        btnSim.style.display = "none";
        btnNao.style.display = "none";
    }

    function resetBotoes() {
        btnSim.style.display = "inline-block";
        btnNao.style.display = "inline-block";
    }

    btnSim.addEventListener("click", () => {
        mostrarResposta("ufaa, eu também");
    });

    btnNao.addEventListener("click", () => {
        etapa++;
        if (etapa >= perguntas.length) {
            etapa = perguntas.length - 1;
            tamanhoSim += 10; // aumenta o botão "Sim"
            btnSim.style.fontSize = tamanhoSim + "px";
        }
        mostrarPergunta(perguntas[etapa].texto);
        resetBotoes();
    });
</script>

</body>
</html>
