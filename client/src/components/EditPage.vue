<template>
  <section id="edit-task-page">
         <div class="limiter">
            <div class="container-login100" style="background-image: url('../assets/images/bg-01.jpg');">
               <div class="wrap-login100 p-l-110 p-r-110 p-t-62 p-b-33">
                  <span class="close">
                     <a @click="backHome" href="#">
                        <svg width="30px" height="30px" viewBox="0 0 16 16" class="bi bi-x-circle" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
                           <path fill-rule="evenodd" d="M8 15A7 7 0 1 0 8 1a7 7 0 0 0 0 14zm0 1A8 8 0 1 0 8 0a8 8 0 0 0 0 16z"/>
                           <path fill-rule="evenodd" d="M4.646 4.646a.5.5 0 0 1 .708 0L8 7.293l2.646-2.647a.5.5 0 0 1 .708.708L8.707 8l2.647 2.646a.5.5 0 0 1-.708.708L8 8.707l-2.646 2.647a.5.5 0 0 1-.708-.708L7.293 8 4.646 5.354a.5.5 0 0 1 0-.708z"/>
                         </svg>
                     </a>
                  </span>
                  
                  <form @submit.prevent="editTaskData" class="login100-form validate-form flex-sb flex-w">
                     <span class="login100-form-title">
                        Edit Task
                     </span>

                     <div class="p-t-31 p-b-9">
                        <span class="txt1">
                           Title
                        </span>
                     </div>

                     <div class="wrap-input100 validate-input" data-validate="Title is required">
                        <input v-model="title" class="input100" type="text" name="title">
                        <span class="focus-input100"></span>
                     </div>

                     <div class="p-t-31 p-b-9">
                        <span class="txt1">
                           Description
                        </span>
                     </div>

                     <div class="wrap-input100 validate-input" data-validate="Description is required">
                        <input v-model="description" class="input100" type="text" name="description">
                        
                        <span class="focus-input100"></span>
                     </div>

                     <div class="w-full text-center p-t-55">
                        
                     </div>
                     
                     <div class="container-login100-form-btn m-t-17">
                        <button class="login100-form-btn">
                           Edit Task
                        </button>
                     </div>
                  </form>
               </div>
            </div>
         </div>
      </section>
</template>

<script>
export default {
    name: 'EditPage',
    data() {
       return {
          id: this.editTask.id,
          title: this.editTask.title,
          description: this.editTask.description,
       }
    },
    props: ['editTask'],
    methods: {
       editTaskData() {
          let payload = {
             id: this.editTask.id,
             title: this.title,
             description: this.description
          }
          this.$emit('editTaskData', payload)
       },
       backHome() {
            let payload = {
               page: 'home-page'
            }
            this.$emit('changePage', payload)
         }
    }
}
</script>

<style>

</style>