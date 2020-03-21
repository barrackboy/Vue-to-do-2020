<template>
  <div v-if="!editMode" class="todo-item">
      <div class="todo-item-content">
        <div class="todo-item-content-title">{{title}}</div>
        <div class="todo-item-content-description">{{description}}</div>
      </div>
      <button @click="editMode = true" class="app-button is-warning">Edit</button>
      <button @click="deleteTodo" class="app-button is-danger">Delete</button>
    </div>
    <div v-else class="todo-item">
      <form class="app-form" action>
      <div class="form-control">
        <label for class="label">Title</label>
        <input v-bind:value="title" class="form-input" type="text" />
      </div>
      <div class="form-control form-control-last">
        <label for class="label">Description</label>
        <textarea
       v-bind:value="description"
        cols="30"
        rows="2"
        class="form-input">

        </textarea> 
        
      </div>
     <button @click.prevent="editTodo" class="app-button is-warning">Update</button>
      <button @click.prevent="editMode = false" class="app-button is-danger">Cancel</button>

    </form>
    </div>
</template>




<script>
export default {
  // props: ['title', 'description'],
  props:{
    title:{
      type: String,
      required:true,
      default:'Default Title'
    },
    description:{
      type: String,
      required:false,
      default:'Default Description'
    }
  }, 
  data(){
    return{
      editMode:false
    }
  },
  methods:{
    editTodo(){
      alert('editing todo')
    },
     deleteTodo(){
      alert('deleting todo')
    }
  }
}
</script>
<style lang="scss" scoped>
.app-button{
  font-size: 15px;
  &.is-warning{
    margin-right: 5px;
  }
}
.todo {
  &-item {
    background-color: gray;
    min-height: 70px;
    margin: 10px;
    padding: 10px;
    color: #fff;
    border-radius: 5px;

    &-content {
      margin-bottom: 10px;
      &-title {
        font-weight: bold;
      }
      &-description {
        font-size: 19px;
      }
    }
  }
}
</style>