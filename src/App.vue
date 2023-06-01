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
      title: "This is Vue",
      foo: "This is text from vue",
      header: "🐟",
      text: "It should be noted that the implementation of the planned tasks plays an important part in the formation of the position that is taken by the participants in relation to tasks. There's no doubt that social economic development allows to complete important implementation tasks of the tasks given by the society and government. There's no doubt that the implementation of the planned tasks directly depends on the position that is taken by the participants in relation to tasks.",
      showModal1:false,
      showModal2:false,

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
    toggleModal1(){
      this.showModal1 = !this.showModal1
    },
    toggleModal2(){
      this.showModal2 = !this.showModal2
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
  </div>
  <div class="flex items-center justify-center">
    <button @click="toggleModal1" class="ml-4 mt-8 text-sm bg-blue-700 p-2 rounded-md hover:bg-blue-600 text-white">Show Modal1 </button>
    <button @click="toggleModal2" class="ml-4 mt-8 text-sm bg-blue-700 p-2 rounded-md hover:bg-blue-600 text-white">Show Modal2</button>
  </div>
  <!-- ? Prop of the modal -->
  <div v-if="showModal1">
    <Modal  theme="sale" @close="toggleModal1()">
      <template v-slot:links>
        <a class="mr-4" href="google.com"> this link is google</a>
        <a href="google.com"> this link is youtube</a>
      </template>
      <h1>🐟</h1>
      <p>The significance of such problems is so obvious that further development of various forms of activity allows to complete important implementation tasks of the tasks given by the society and government. However, one should not forget the understanding of nature of resource saving technologies allows to appreciate the value of economic practicability of decisions made. Thus the bounds and place of personnel training directly depends on forms of influence.</p>
      <br>
    </Modal>
  </div>

  <div v-if="showModal2">
    <Modal @close="toggleModal2()">
      <h1>🌱</h1>
      <p>However, one should not forget the bounds and place of personnel training requires the clarification of the step-by-step consistent development of the society. On the other hand the understanding of nature of resource saving technologies allows to appreciate the value of the step-by-step consistent development of the society. It should be noted that constant quantitive growth and the scope of our activity contributes to the preparing and implementation of the step-by-step consistent development of the society.</p>
    </Modal>
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
