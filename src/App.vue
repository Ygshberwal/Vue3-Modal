<template>
  <h2>{{ title }}</h2>
  <input type="text" ref="name">
  <button @click="handleClick">Click me</button>
  <!-- header and text can be exported to Modal -->
  <p>Welcome...</p>
  <Teleport to=".modals" v-if="showModal">
    <Modal  theme="dark" @close="toggleModal">
      <template v-slot:links>
        <a href="#">Sign Up now</a>
        <a href="#">More info..</a>
      </template>
      <h1>Sign in for the Giveaway!!!</h1>
      <p>Grab the Opportunity ASAP</p>
    </Modal>
  </Teleport>

  <Teleport to=".modals" v-if="showModal2">
    <Modal theme="dark" @close="toggleModal2">
      
      <h1>Sign for the newsletter</h1>
      <p>For updates and promo vodes!</p>
    </Modal>
  </Teleport>

  <button @click.alt="toggleModal">Open Modal (Alt)</button>
  <button @click="toggleModal2">Open Modal</button>
  
</template>

<script>
import Modal from './components/Modal.vue'
export default {
  name: 'App',
  components:{ Modal },
  data(){
    return{
      title:'This is my First Vue app :) ',
      showModal:false,
      showModal2:false
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
    },
    toggleModal2(){
      this.showModal2=!this.showModal2
    }
  }
}
</script>

<style>
#app, .modals{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
