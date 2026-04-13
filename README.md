<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>To-Do List</title>

  <!-- CSS -->
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f4f4;
      display: flex;
      justify-content: center;
      padding: 40px;
    }

    .container {
      background: white;
      padding: 20px;
      border-radius: 10px;
      width: 350px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }

    h2 {
      text-align: center;
    }

    input, select, button {
      width: 100%;
      padding: 10px;
      margin-top: 10px;
    }

    button {
      background: #333;
      color: white;
      border: none;
      cursor: pointer;
    }

    ul {
      list-style: none;
      padding: 0;
      margin-top: 20px;
    }

    li {
      padding: 10px;
      border-radius: 5px;
      margin-bottom: 10px;
      cursor: pointer;
    }

    /* Prioridades */
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

    /* Tarefa concluída */
    .done {
      text-decoration: line-through;
      opacity: 0.6;
    }
  </style>
</head>

<body>

  <div class="container">
    <h2>To-Do List</h2>

    <!-- Campo de entrada -->
    <input type="text" id="taskInput" placeholder="Digite uma tarefa">

    <!-- Prioridade -->
    <select id="priority">
      <option value="alta">Alta</option>
      <option value="media">Média</option>
      <option value="baixa">Baixa</option>
    </select>

    <!-- Botão -->
    <button onclick="addTask()">Adicionar</button>

    <!-- Lista de tarefas -->
    <ul id="taskList"></ul>
  </div>

  <!-- JavaScript -->
  <script>
    function addTask() {
      const input = document.getElementById("taskInput");
      const priority = document.getElementById("priority").value;
      const list = document.getElementById("taskList");

      // Evita tarefa vazia
      if (input.value.trim() === "") return;

      // Cria elemento da tarefa
      const li = document.createElement("li");
      li.textContent = input.value;

      // Adiciona prioridade (cor)
      li.classList.add(priority);

      // Marca como concluída ao clicar
      li.addEventListener("click", function () {
        li.classList.toggle("done");
      });

      // Adiciona na lista
      list.appendChild(li);

      // Limpa campo
      input.value = "";
    }
  </script>

</body>
</html>
