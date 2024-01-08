<template>
  <h2>{{ title }}</h2>
  <Modal :header="header" :description="description" theme="sale" />
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
      header: 'Signup Modal',
      description: 'This is signup modal, please work with us'
    }
  },
  methods: {
    handleClick() {
      console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()
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
  border: 1px solid black;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
