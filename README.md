<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <title>Jogo da Kitsune</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      background-color: #fce4ec;
      color: #333;
      text-align: center;
      padding: 40px;
    }
    input, button {
      padding: 10px;
      margin: 10px;
      border-radius: 8px;
      border: none;
      font-size: 16px;
    }
    button {
      background-color: #ff69b4;
      color: white;
      cursor: pointer;
    }
    button:hover {
      background-color: #e055a4;
    }
    .resultado {
      margin-top: 20px;
      font-size: 18px;
    }
    #mensagemBotao {
      display: none;
      margin-top: 20px;
    }
  </style>
</head>
<body>
  <h1>Jogo da kity</h1>
  <p>Seja bem vindo, thugu!</p>
  <p>Tente adivinhar minhas coisas favoritas!</p>

  <input type="text" id="flor" placeholder="Flor favorita"><br>
  <input type="text" id="cor" placeholder="Cor favorita"><br>
  <input type="text" id="fruta" placeholder="Fruta favorita"><br>

  <button onclick="verificarRespostas()">Enviar</button>

  <div class="resultado" id="resultado"></div>

  <div id="mensagemBotao">
    <button onclick="mostrarMensagem()">Clique aqui para receber sua mensagem surpresa!</button>
  </div>

  <script>
    function verificarRespostas() {
      const flor = document.getElementById("flor").value.toLowerCase().trim();
      const cor = document.getElementById("cor").value.toLowerCase().trim();
      const fruta = document.getElementById("fruta").value.toLowerCase().trim();

      let acertos = 0;

      if (["rosa", "rosa cor de rosa", "rosa pink", "rosas"].includes(flor)) acertos++;
      if (cor === "preto") acertos++;
      if (fruta === "morango") acertos++;

      let mensagem = "";

      if (acertos === 3) {
        mensagem = "Mentira, que fofo! Você me conhece bem!";
        document.getElementById("mensagemBotao").style.display = "block";
      } else {
        document.getElementById("mensagemBotao").style.display = "none";
        if (acertos === 2) mensagem = "Tá quase! N desiste!";
        else if (acertos === 1) mensagem = "Você acertou uma... tem mto pra descobrir";
        else mensagem = "Hmm... nada certo! Vamos ter q passar mais tempo juntos!";
      }

      document.getElementById("resultado").innerHTML = `Você acertou ${acertos} de 3.<br>${mensagem}`;
    }

    function mostrarMensagem() {
      alert("Feioso, gst de vc");
    }
  </script>
</body>
</html>
