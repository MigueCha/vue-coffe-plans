<script setup>
import { ref } from 'vue';
const hover = ref(false);
</script>
 
<template>
<div class="content">
    <button 
    @mouseenter="hover = true"
    @mouseleave="hover = false"> 
    <slot name="icon" :hover="hover"> ⚠️ </slot>
    <slot>No Message</slot> 
  </button>
</div>
</template>
 
<style scoped>
.content{
  text-align: center;
}

.button{
  width: 10rem;
  margin: 10px auto;
  font-size: 2rem;
}
</style>