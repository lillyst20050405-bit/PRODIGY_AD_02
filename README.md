# PRODIGY_AD_02
TO-DO LIST

<!DOCTYPE html>
<html lang="en">
    
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>To-Do List App</title>
</head>

<style>

    body {
      font-family: 'Segoe UI', sans-serif;
      background: #f1f5f8;
      display: flex;
      justify-content: center;
      padding-top: 50px;
    }

    .container {
     background: white;
     padding: 20px 30px;
     border-radius: 10px;
     box-shadow: 0 0 15px rgba(0,0,0,0.1);
     width: 350px;
    }

    h2 {
     text-align: center;
     color: #333;
    }

    .input-section {
     display: flex;
     gap: 10px;
     margin-bottom: 20px;
    }

    input[type="text"] {
     flex: 1;
     padding: 10px;
     border: 1px solid #bbb;
     border-radius: 5px;
    }

    button {
     padding: 10px 15px;
     background-color: #007bff;
     color: white;
     border: none;
     border-radius: 5px;
     cursor: pointer;
    }

    ul {
     list-style: none;
     padding: 0;
    }

    li {
     display: flex;
     justify-content: space-between;
     background: #f9f9f9;
     margin: 5px 0;
     padding: 10px;
     border-radius: 5px;
    }

    li span {
     flex: 1;
    }

    li button {
     background: transparent;
     color: #007bff;
     border: none;
     margin-left: 10px;
     cursor: pointer;
    }

</style>

<body>

  <div class="container">
    <h2>To-Do List</h2>
    <div class="input-section">
      <input type="text" id="taskInput" placeholder="Enter a new task" />
      <button onclick="addTask()">Add</button>
    </div>
    <ul id="taskList"></ul>
  </div>

</body>

<script>

    let taskList = document.getElementById("taskList");

        function addTask() {
             let taskInput = document.getElementById("taskInput");
             let taskText = taskInput.value.trim();

     if (taskText === "") return;

    let li = document.createElement("li");

    let span = document.createElement("span");
    span.innerText = taskText;

    let editBtn = document.createElement("button");
    editBtn.innerText = "Edit";
    editBtn.onclick = () => {
        let newText = prompt("Edit your task", span.innerText);
        if (newText) span.innerText = newText;
    };

    let deleteBtn = document.createElement("button");
    deleteBtn.innerText = "Delete";
    deleteBtn.onclick = () => taskList.removeChild(li);

    li.appendChild(span);
    li.appendChild(editBtn);
    li.appendChild(deleteBtn);

    taskList.appendChild(li);
    taskInput.value = "";
    }
 </script>
</html>
