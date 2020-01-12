<template>
  <div id="app">
    <div class="todo-wrapper">
      <div class="todo-container">
        <todo-list :todos="todos" />
        <div class="todo-creat-btn-container">
           <todo-create @formSubmitted="createTodo"/>
        </div>
      </div>
    </div>
   
  </div>
</template>

<script>
import TodoList from "@/components/TodoList";
import TodoCreate from "@/components/TodoCreate";

export default {
  name: "app",
  components: {
    TodoList,
    TodoCreate
  },
  data() {
    return {
      
      todos: [
        {
          _id: "1",
          title: "Walk the Dog",
          description: "Go somewhere and have a lot of fun"
        },
        {
          _id: "2",
          title: "Some Title",
          description: "Some bullocks"
        },
        {
          _id: "3",
          title: "The Big Bully",
          description: "Lloyd Banks V5 Mixtape"
        }
      ]
    };
  },
  methods:{
 createTodo(todo){
    this.todos.push(todo)
  }
  }
 

};
</script>

<style lang="scss" >
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  // text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.app-form{
    .label{
        display:block;
        font-size: 18px;
        font-weight: bold;
    }
    form-input{
        padding:10px;
        font-size:17px;
    }
    for-control{
        margin-bottom: 10px;
    }
}


.is-primary{
  background-color: #47ca47 !important;
}
.form-input {
    padding: 5px;
}
.app-button {
  font-size: 20px;
  padding: 10px;
  border-radius: 5px;
  background-color: #795899;
  color: #ffffff;
  font-weight: bold;
  &:hover{
    cursor: pointer;
  }
}

.todo {
  &-wrapper {
    display: flex;
    justify-content: center;
    width: 100%;
  }
  &-creat-btn-container{
    margin: auto 10px 10px;

  }
  &-container {
    width: 400px;
    min-height: 400px;
    background-color: #ededed;
    border-radius: 5px;
    display: flex;
    flex-direction: column;

  }
}
</style>
