<template>
<h1>{{ title }}</h1>
<input type="text" ref="name">
<button @click="handleClick">Click Me</button>
<div v-if="showModal">
  <Modal :header="header" :text="text" theme="sale" @close="toggleModal"/>
</div>
<p>Welcome ...</p>
<button @click="toggleModal">Open Modal</button>
</template>

<script>
import Modal from "./components/Modal.vue"

export default {
  name: 'App',
  components:{Modal},
  data(){
    return{
      title:"Hello Vue",
      header:"Welcome!",
      text:"Welcome to Vue Masterclass.",
      showModal:false
    }
  },
  methods:{
    handleClick(){
      this.$refs.name.focus()
    },
    toggleModal(){
      this.showModal = !this.showModal
    }
  }
}
</script>

