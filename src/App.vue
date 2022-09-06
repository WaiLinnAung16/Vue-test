<template>
  <h1>Hi</h1>
  <div v-if="showModal">
    <Modal :header="header" :content="content" :theme="theme" @close="showModal=false">
      <h1>{{header[0]}}</h1>
      <p>{{content[0]}}</p>
    </Modal>
  </div>
  <div v-if="showDeleteModal">
    <Modal :header="header" :content="content" :theme="theme" @close="showDeleteModal=false">
      <h1>{{header[1]}}</h1>
      <p>{{content[1]}}</p>
    </Modal>
  </div>
  <button @click="showModal=!showModal,theme='success'">LogIn Modal</button>
  <button @click="showDeleteModal=!showDeleteModal,theme='danger'">Delete Modal</button>
</template>

<script>
import Modal from "./components/Modal-div.vue"
export default {
  data(){
      return{
        header:['LogIn Success','Are u sure want to Delete?'],
        content:["Welcome","Please Make sure..."],
        theme:['success','danger'],
        showModal:false,
        showDeleteModal:false
      }
  },
  components:{
    Modal
  },
  methods:{
    // clickHandler(){
    //   this.$refs.name.focus()
    //   this.$refs.title.textContent = "Hello"
    // }
  }
}
</script>

<style scoped>

</style>