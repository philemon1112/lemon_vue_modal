<template>
  <h2>{{ title }}</h2>
  <div v-if="showModal">
    <Modal theme="" @close="toggleModal" >
      <template v-slot:links>
        <a href="#">Signup here</a>
        <a href="#">Login here</a>
      </template>
      <h1>Signup Modal</h1>
      <p>This is signup modal, please work with us</p>
    </Modal>
  </div>

  <div v-if="showModalTwo">
    <Modal theme="sale" @close="toggleModalTwo" >
      <h1>Signup To the Newslater</h1>
      <p>Get recent updates and news about our products</p>
    </Modal>
  </div>

  <p>Welcome ..</p>
  <button @click="toggleModal">Show Modal</button>
  <button @click="toggleModalTwo">Show Modal rwo</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: {
    Modal
  },
  data() {
    return {
      title: 'My First vuejs App',
      showModal: false,
      showModalTwo: false
    }
  },
  methods: {
    handleClick() {
      console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()
    },
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo
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

h2{
  border-bottom: 1px solid black;
  display: inline-block;
  padding-bottom: 6px;
}
</style>
