
<!DOCTYPE html>
<html lang="pt-BR">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Aceitas?</title>

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: #ffc8dd;
            font-family: 'Arial', sans-serif;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
        }

        .container {
            text-align: center;
        }

        h1 {
            color: #590d22;
            font-size: 30px;
            margin-bottom: 40px;
        }

        .botoes {
            display: flex;
            justify-content: center;
            gap: 25px;
        }

        button {
            background-color: #ffb3c1;
            color: #590d22;
            border: 2px solid #590d22;
            border-radius: 10px;
            padding: 12px 30px;
            font-size: 18px;
            font-weight: bold;
            cursor: pointer;
        }

        #nao {
            position: absolute;
        }

        button:hover {
            background-color: #ff8fab;
        }

        .mensagem {
            color: #590d22;
            font-size: 22px;
            margin-top: 25px;
            font-weight: bold;
        }
    </style>
</head>

<body>

    <div class="container">

        <h1>Quer namorar comigo? ❤️</h1>

        <div class="botoes">

            <button id="sim" onclick="aceitou()">
                Sim ❤️
            </button>

            <button id="nao">
                Não 😢
            </button>

        </div>

        <div id="mensagem" class="mensagem"></div>

    </div>

    <script>

        const botaoNao = document.getElementById("nao");

        function fugir() {

            const largura = window.innerWidth - botaoNao.offsetWidth;
            const altura = window.innerHeight - botaoNao.offsetHeight;

            const x = Math.random() * largura;
            const y = Math.random() * altura;

            botaoNao.style.left = x + "px";
            botaoNao.style.top = y + "px";
        }

        botaoNao.addEventListener("mouseover", fugir);

        botaoNao.addEventListener("touchstart", function(event) {
            event.preventDefault();
            fugir();
        });

        function aceitou() {

            document.getElementById("mensagem").innerHTML =
                "Eu te amo, meu amor! ❤️ Lanchinho mais tarde? 🥰";

            botaoNao.style.display = "none";

            document.getElementById("sim").style.display = "none";
        }

    </script>

</body>
</html>
