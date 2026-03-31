<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Studio Lux - Agendamento</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f8f4f9;
      margin: 0;
      padding: 0;
    }

    header {
      background: #d63384;
      color: white;
      text-align: center;
      padding: 20px;
    }

    .container {
      max-width: 500px;
      margin: 30px auto;
      background: white;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }

    label {
      display: block;
      margin-top: 10px;
      font-weight: bold;
    }

    input, select, button {
      width: 100%;
      padding: 10px;
      margin-top: 5px;
      border-radius: 5px;
      border: 1px solid #ccc;
    }

    button {
      background: #d63384;
      color: white;
      border: none;
      margin-top: 15px;
      cursor: pointer;
      font-size: 16px;
    }

    button:hover {
      background: #b82c6d;
    }

    .success {
      text-align: center;
      color: green;
      margin-top: 15px;
      display: none;
    }
  </style>
</head>
<body>

<header>
  <h1>Studio Lux</h1>
  <p>Agende seu horário</p>
</header>

<div class="container">
  <form id="agendamentoForm">
    
    <label>Nome:</label>
    <input type="text" id="nome" required>

    <label>Telefone:</label>
    <input type="tel" id="telefone" required>

    <label>Serviço:</label>
    <select id="servico" required>
      <option value="">Selecione</option>
      <option>Unhas</option>
      <option>Cabelo</option>
      <option>Cílios</option>
    </select>

    <label>Profissional (opcional):</label>
    <input type="text" id="profissional">

    <label>Data:</label>
    <input type="date" id="data" required>

    <label>Horário:</label>
    <input type="time" id="hora" required>

    <button type="submit">Agendar</button>

    <p class="success" id="mensagem">Agendamento realizado com sucesso!</p>
  </form>
</div>

<script>
  const form = document.getElementById("agendamentoForm");
  const mensagem = document.getElementById("mensagem");

  form.addEventListener("submit", function(event) {
    event.preventDefault();

    const nome = document.getElementById("nome").value;
    const servico = document.getElementById("servico").value;
    const data = document.getElementById("data").value;
    const hora = document.getElementById("hora").value;

    console.log("Novo agendamento:", {
      nome,
      servico,
      data,
      hora
    });

    mensagem.style.display = "block";
    form.reset();
  });
</script>

</body>
</html>
