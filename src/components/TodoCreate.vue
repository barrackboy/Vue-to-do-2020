<template>
  <modal>
    <form class="app-form" action>
      <div class="form-control">
        <label for class="label">Title</label>
        <input v-model="form.title" class="form-input" type="text" />
      </div>
      <div class="form-control">
        <label for class="label">Description</label>
        <textarea
        v-model="form.description"
        cols="30"
        rows="5"
        class="form-input">

        </textarea>
        
      </div>
      <button @click="submitForm" type="button" class="app-button is-primary">Confirm</button>
    </form>
  </modal>
</template>

<script>
import Modal from "@/components/Modal";
export default {
  components: {
    Modal
  },
  data() {
    return {
      form: {
        title: "",
        description: ""
      }
    };
  },
  computed:{
      isFormValid(){
        //  if (this.form.title && this.form.description){
        //      return true
        //  }else{
        //      return false
        //  }
         return this.form.title && this.form.description ? true : false
      }
  },
  methods: {
    submitForm() {
        if (this.isFormValid){
       this.$emit('formSubmitted',{...this.form})
        this.form.title=''
        this.form.description=''
    
        }
    },
    resetForm(){
        this.form.title=''
        this.form.description=''

    }
  }
};
</script>