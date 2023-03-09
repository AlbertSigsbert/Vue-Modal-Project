<template>
<h1>{{ title }}</h1>
<input type="text" ref="name">
<button @click="handleClick">Click Me</button>
<Modal :header="header" :text="text" theme="sale"/>
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
      text:"Welcome to Vue Masterclass."
    }
  },
  methods:{
    handleClick(){
      this.$refs.name.focus()
    }
  }
}
</script>

