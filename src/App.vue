<template>
  <h1>{{ title }}</h1>
  <input type="text" ref="name">
  <button @click="handleClick">Click Me</button>
  <div v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <h1>Hello Vue</h1>
      <p>Vue in action </p>
      <template v-slot:links>
        <a href="#">Sign In</a>
        <a href="#">Read More</a>
      </template>
    </Modal>
  </div>
  <div v-if="showModalTwo">
    <Modal theme="sale" @close="toggleModalTwo">
      <h1>Hello Vue</h1>
      <p>Vue in action </p>
    </Modal>
  </div>
  <p>Welcome ...</p>
  <button @click="toggleModal">Open Modal</button>
  <button @click="toggleModalTwo">Open Modal Two</button>
</template>

<script>
import Modal from "./components/Modal.vue"

export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: "Hello Vue",
      header: "Welcome!",
      text: "Welcome to Vue Masterclass.",
      showModal: false,
      showModalTwo: false
    }
  },
  methods: {
    handleClick() {
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

