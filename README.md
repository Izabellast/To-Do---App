<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>To-Do List</title>

  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f4f4;
      display: flex;
      justify-content: center;
      padding: 40px;
      margin: 0;
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
      margin-bottom: 10px;
    }

    input, select, button {
      width: 100%;
      padding: 10px;
      margin-top: 10px;
      box-sizing: border-box;
    }

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
      transition: 0.2s;
    }

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

    .done {
      text-decoration: line-through;
      opacity: 0.6;
    }
  </style>
</head>

<body>

  <div class="container">

    <h2>To-Do List</h2>

    <input type="text" id="taskInput" placeholder="Digite uma tarefa">

    <select id="priority">
      <option value="alta">Alta</option>
      <option value="media">Média</option>
      <option value="baixa">Baixa</option>
    </select>

    <button onclick="addTask()">Adicionar</button>

    <ul id="taskList"></ul>

  </div>

  <script>
    function addTask() {

      const input = document.getElementById("taskInput");
      const priority = document.getElementById("priority").value;
      const list = document.getElementById("taskList");

      if (input.value.trim() === "") return;

      const li = document.createElement("li");
      li.textContent = input.value;

      li.classList.add(priority);

      li.addEventListener("click", function () {
        li.classList.toggle("done");
      });

      list.appendChild(li);

      input.value = "";
    }
  </script>

</body>
</html>
