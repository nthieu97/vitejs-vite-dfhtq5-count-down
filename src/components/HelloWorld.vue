<script setup>
import { reactive, computed } from 'vue'

const state = reactive({count:10})
const handleClick = computed(()=>{
  let interval = setInterval(()=>{
    if(state.count == 0){
       clearInterval(interval);
      state.count = 10
      return
    }
    state.count--
  },1000)
})
</script>

<template>
  <h1>{{state.count }}</h1>

  <div class="card">
    <button v-if="state.count ==10" type="button" @click="handleClick">Start</button>
   
  </div>

 
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
