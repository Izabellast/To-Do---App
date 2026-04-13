<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>To-Do List</title>

  <!-- ===================== CSS ===================== -->
  <style>
    /* Estilo geral da página */
    body {
      font-family: Arial, sans-serif;
      background: #f4f4f4;
      display: flex;
      justify-content: center;
      padding: 40px;
      margin: 0;
    }

    /* Caixa principal do app */
    .container {
      background: white;
      padding: 20px;
      border-radius: 10px;
      width: 350px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }

    /* Título */
    h2 {
      text-align: center;
      margin-bottom: 10px;
    }

    /* Inputs e botão */
    input, select, button {
      width: 100%;
      padding: 10px;
      margin-top: 10px;
      box-sizing: border-box;
    }

    /* Botão */
    button {
      background: #333;
      color: white;
      border: none;
      cursor: pointer;
      transition: 0.2s;
    }

    button:hover {
      background: #555;
    }

    /* Lista */
    ul {
      list-style: none;
      padding: 0;
      margin-top: 20px;
    }

    /* Item da lista */
    li {
      padding: 10px;
      border-radius: 5px;
      margin-bottom: 10px;
      cursor: pointer;
      transition: 0.2s;
    }

    /* ===================== PRIORIDADES ===================== */

    .alta {
      background: #ffcccc;
      border-left: 5px solid red;
    }

    .media {
      background: #fff0b3;
      border-left: 5px solid orange;
    }

    .baixa {
      background: #ccffcc;
      border-left: 5px solid green;
    }

    /* ===================== CONCLUÍDA ===================== */

    .done {
      text-decoration: line-through;
      opacity: 0.6;
    }
  </style>
</head>

<body>

  <!-- ===================== HTML ===================== -->
  <div class="container">

    <h2>To-Do List</h2>

    <!-- Campo de entrada -->
    <input type="text" id="taskInput" placeholder="Digite uma tarefa">

    <!-- Seleção de prioridade -->
    <select id="priority">
      <option value="alta">Alta</option>
      <option value="media">Média</option>
      <option value="baixa">Baixa</option>
    </select>

    <!-- Botão de ação -->
    <button onclick="addTask()">Adicionar</button>

    <!-- Lista de tarefas -->
    <ul id="taskList"></ul>

  </div>

  <!-- ===================== JAVASCRIPT ===================== -->
  <script>
    function addTask() {

      // Captura o input da tarefa
      const input = document.getElementById("taskInput");

      // Captura prioridade selecionada
      const priority = document.getElementById("priority").value;

      // Captura a lista
      const list = document.getElementById("taskList");

      // Evita tarefas vazias
      if (input.value.trim() === "") return;

      // Cria novo item de lista
      const li = document.createElement("li");

      // Define texto da tarefa
      li.textContent = input.value;

      // Aplica classe de prioridade (cor)
      li.classList.add(priority);

      // Evento de clique para marcar como concluída
      li.addEventListener("click", function () {
        li.classList.toggle("done");
      });

      // Adiciona item na lista
      list.appendChild(li);

      // Limpa campo de input
      input.value = "";
    }
  </script>

</body>
</html>
