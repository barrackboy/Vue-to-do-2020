<template>
  <div id="app">
    <div class="todo-wrapper">
      <div class="todo-container">
        <todo-list :todos="todos" />
        <div class="todo-creat-btn-container">
          <div 
          @click="isModalOpen = true "
           
          class="app-button">Create</div>
        </div>
      </div>
    </div>
    <Modal 
    @modalClosed="isModalOpen = false"
    :isOpen="isModalOpen" />
  </div>
</template>

<script>
import TodoList from "@/components/TodoList";
import Modal from "@/components/Modal";

export default {
  name: "app",
  components: {
    TodoList,
    Modal
  },
  data() {
    return {
      isModalOpen:false,
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
  // methods:{
  //   openModal(){
  //     this.isModalOpen = true
  //   },
  //   closeModal(){
  //     this.isModalOpen=false
  //   }
  // }
};
</script>

<style lang="scss" >
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
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
