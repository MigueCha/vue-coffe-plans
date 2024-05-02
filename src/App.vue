<script setup>
  import FancyButton from './components/FancyButton.vue';
</script>
 
<template>
  <FancyButton>
    <template v-slot:icon="slotProps">
    {{ slotProps.hover ? '🚀' : '🪅' }}
    </template>
    <template v-slot:default>
    Enviar
    </template>
  </FancyButton>

  <br>

  <FancyButton>
    <template #icon="{ hover }">
    {{ hover ? '🚀' : '🪅' }}
    </template>
    <template #default>
    Cancelar
    </template>
  </FancyButton>
</template>
 
<style scoped>

</style>


