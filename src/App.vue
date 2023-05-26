<script setup>
import HelloWorld from './components/HelloWorld.vue'
</script>

<script>
import $ from 'jquery'
export default {
  name: 'App',
  data(){
    return{
      title: 'This is Vue',
      foo: 'This is text from vue'
    }
  },
  methods: {
    handleClick(){
      // console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
      if(this.$refs.name.classList.contains('active')){
        console.log(document.getElementById("Input").value)
      }
    },
    handleReset(){
      $("input:text").val("")
    }
  }
}
</script>

<template>
  <div class="flex flex-col items-center justify-center">
    <h1>{{ title }}</h1>
    <div class="flex">
      <input id="Input" class="border border-black rounded-md" type="text" ref="name">
      <button class="ml-4 text-sm bg-green-700 p-2 rounded-md hover:bg-green-600 text-white" @click="handleClick">Click me</button>
      <button class="ml-4 text-sm bg-red-700 p-2 rounded-md hover:bg-red-600 text-white" @click="handleReset">Reset</button>
      
    </div>


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
