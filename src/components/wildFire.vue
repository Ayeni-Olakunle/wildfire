<template>
  <div id="app1">
    <div class="subHolder">
      <div class="holdAdding">
        <h1>Todo App</h1>
        <input
          type="text"
          v-model="todoText"
          placeholder="Add Todo..."
          class="inputAdding"
          id="adding"
        />
        <button @click="todoApp()" class="butinAdd">Add Task</button>
      </div>
      <ul id="ul">
        <li v-for:="todo in todos" class="todoList">
          {{ todo.text }}
          <div>
            <img @click="editMe" class="img" src="../assets/edit.png" /><img
              @click="removeNow"
              class="delet"
              src="../assets/delete.png"
            />
          </div>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "TaskNow",
  data() {
    return {
      todoText: "",
      // del:"D",
      todos: [],
    };
  },
  methods: {
    todoApp() {
      let adding = document.getElementById("adding");
      if (adding.value != "") {
        this.todos.push({ text: this.todoText });
        this.todoText = "";
      } else {
        alert("Please fill out the input");
      }
    },
    editMe() {
      let ul = document.getElementById("ul");
      let todoList = ul.getElementsByClassName("todoList");
      for (let i = 0; i < todoList.length; i++) {
        const editDis = todoList[i];
        editDis.onclick = () => {
          this.todoText = editDis.textContent;
          editDis.remove();
        };
      }
    },
    removeNow() {
      let ul = document.getElementById("ul");
      let todoList = ul.getElementsByClassName("todoList");
      for (let i = 0; i < todoList.length; i++) {
        const del = todoList[i];
        del.onclick = () => {
          del.remove();
        };
      }
    },
  },
};
</script>

<style scoped>
#app1 {
  display: flex;
  justify-content: center;
  width: 50%;
}
.subHolder {
  width: 100%;
  height: auto;
  background-color: #f2f2f2;
  padding: 30px 10px;
  border-radius: 10px;
}
.adding {
  background-color: white;
  padding: 5px;
}
.inputAdding {
  width: 70%;
  padding: 15px 20px;
  font-size: 17px;
  border: none;
  outline: none;
  margin: 20px;
  border-radius: 50px;
}
.butinAdd {
  font-size: 17px;
  padding: 15px 30px;
  border: none;
  background-color: #319fff;
  color: white;
  cursor: pointer;
  transition: 0.5s;
  border-radius: 50px;
}
.butinAdd:hover {
  background-color: #1d7ccf;
}
#ul {
  background-color: white;
  margin: 20px 0px;
  padding: 10px;
  text-align: left;
  list-style: none;
}
.todoList {
  font-size: 18px;
  background-color: aliceblue;
  padding: 10px;
  margin: 10px 0px;
  display: flex;
  justify-content: space-between;
}
.todoList:hover {
  padding: 15px 10px;
  background-color: #1d7ccf;
}
.img {
  width: 20px;
  margin-right: 15px;
  cursor: pointer;
}
.delet {
  width: 20px;
  cursor: pointer;
}
</style>
