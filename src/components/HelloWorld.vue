<script setup>
import { ref } from 'vue'

defineProps({
  msg: String,
})

const count = ref(0)
</script>

<template>
  <div class="flex-col justify-center">
    <h1>{{ msg }}</h1>
  
    <div class="flex-1">
      <button class= "bg-transparent hover:bg-blue-500 text-blue-700 font-semibold hover:text-white py-2 px-4 border border-blue-500 hover:border-transparent rounded" type="button" @click="count++">count is {{ count }}</button>
      <p>
        Edit
        <code>components/HelloWorld.vue</code> to test HMR
      </p>
    </div>

    <div class="flex-1">
      <p class="text-red-500 text-lg">
        Check out
        <a href="https://vuejs.org/guide/quick-start.html#local" target="_blank"
          >create-vue</a
        >, the official Vue + Vite starter
      </p>
    </div>
    
    <div class="flex-1">
      <p>
        Install
        <a href="https://github.com/vuejs/language-tools" target="_blank">Volar</a>
        in your IDE for a better DX
      </p>
      <p class="read-the-docs">Click on the Vite and Vue logos to learn more</p>
    </div>

  </div>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
