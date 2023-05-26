<script>
import Modal from './components/Modal.vue'
import $ from 'jquery'
export default {
  name: 'App',
  components: {
    Modal
  },
  data(){
    return{
      title: 'This is Vue',
      foo: 'This is text from vue',
      header: 'This is a new header passed',
      text: 'On the other hand social economic development allows to appreciate the value of further ways of development.',
      showModal: false

    }
  },
  methods: {
    handleClick(){
      // Element Reffs 
      // console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
      if(this.$refs.name.classList.contains('active')){
        alert(document.getElementById("Input").value)
        console.log(document.getElementById("Input").value)
      }
    },
    handleReset(){
      $("input:text").val("")
    },
    toggleModal(){
      this.showModal = !this.showModal
    }
  }
}
</script>

<template>
  <div class="flex flex-col items-center justify-center">
    <h1 class="pb-3 pt-3 text-lg font-bold">{{ title }}</h1>
    <div class="flex">
      <input id="Input" class="border border-1 border-black rounded-md" type="text" ref="name">
      <button class="ml-4 text-sm bg-green-700 p-2 rounded-md hover:bg-green-600 text-white" @click="handleClick">Click me</button>
      <button class="ml-4 text-sm bg-red-700 p-2 rounded-md hover:bg-red-600 text-white" @click="handleReset">Reset</button>
    </div>
    <button @click="toggleModal" class="ml-4 mt-8 text-sm bg-blue-700 p-2 rounded-md hover:bg-blue-600 text-white">Show Modal</button>
  </div>
  <!-- ? Prop of the modal -->
  <div v-if="showModal">
    <Modal :header="header" :text="text" theme="sale" @close="toggleModal()" />
  </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
