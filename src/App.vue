<template>
  <div id="app">
    <h2 class="p-2 mt-2 mb-3 d-flex align-items-center">
      <img width="50" class="mr-2" src="./assets/logo.png" alt="Vue.js Logo" />
      To Do App
    </h2>
    <div id="toDoList">
      <div class="form">
        <input type="text" />
        <button class="btn btn-custom-add">
          <i class="fas fa-plus"></i>
        </button>
      </div>

      <div class="toDos">
        <ul>
          <li v-for="(toDo, index) in toDoList" :key="index">
            <h5>{{ toDo.description }}</h5>
            <button class="btn btn-danger">
              <i class="far fa-trash-alt"></i>
            </button>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
const newTodo = description => ({
  description,
  done: false
});

export default {
  name: "App",
  data: () => ({
    toDoList: [
      newTodo("Fazer lição"),
      newTodo("Trabalho da faculdade"),
      newTodo("Fazer lição")
    ]
  })
};
</script>

<style>
@import url("https://fonts.googleapis.com/css?family=Source+Sans+Pro:300,400,600&display=swap");

:root {
  --primary-color: #000112;
  --secondary-color: #cec3f2;
}

body {
  background-color: var(--primary-color);
  color: var(--secondary-color);
}

#app {
  font-family: "Source Sans Pro", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  height: 100%;
  width: 100%;

  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-start;
}

#toDoList {
  color: var(--primary-color);
  background: var(--secondary-color);
  padding: 20px;
  width: 350px;
  min-height: 450px;
  border-radius: 30px;
}

.form {
  display: flex;
  justify-content: space-around;
  align-items: center;
}

.form input {
  padding: 5px;
  border-radius: 4px;
  outline: 0;
  box-shadow: none;
  width: 70%;
  transition: box-shadow 0.1s;
}

.form input:focus {
  box-shadow: 1px 1px 2px 1px #0004;
}

.form .btn-custom-add {
  width: 20%;
  border: 2px solid var(--primary-color);
  background-color: transparent;
  color: var(--primary-color-color);
  transition: background 0.2s, color 0.2s;
}

.form .btn-custom-add:hover {
  background-color: var(--primary-color);
  color: var(--secondary-color);
}

.form .btn-custom-add i {
  transition: transform 0.2s;
}

.form .btn-custom-add:hover i {
  transform: rotate(180deg);
}

.btn-danger {
  transition: background 0.15s;
}

ul {
  list-style: none;
  padding: 4px;
  margin-top: 4px;
}

ul li {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 6px;
  margin-bottom: 4px;
}
</style>
