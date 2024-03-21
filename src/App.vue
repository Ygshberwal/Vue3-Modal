<template>
  <h2>{{ title }}</h2>
  <input type="text" ref="name">
  <button @click="handleClick">Click me</button>
  <!-- header and text can be exported to Modal -->
  <p>Welcome...</p>
  <div v-if="showModal">
    <Modal :header=header :text=text theme="dark" @close="toggleModal"/>
  </div>
  <button @click.alt="toggleModal">Open Modal (Alt)</button>
  
</template>

<script>
import Modal from './components/Modal.vue'
export default {
  name: 'App',
  components:{ Modal },
  data(){
    return{
      title:'This is my First Vue app :) ',
      header:"Sign in for the Giveaway!",
      text:"Grab the Opportunity ASAP",
      showModal:false
    }
  },
  methods:{
    handleClick(){
      console.log(this.$refs.name)
      this.$refs.name.classList.add("active")   //add a class ative to that element
      this.$refs.name.focus()
    },
    toggleModal(){
      this.showModal=!this.showModal
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
