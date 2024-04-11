<template>
    <div class="plan">
        <div class="description">
          <span class="title">
            {{ name }}
          </span>
        </div>
    </div>
</template>

<script setup>
defineProps([ 'name' ]);
//Funcion ya especializada que permite crear propiedades y no se debe de importar (Macro)
//Kabeh o CamelCassing
</script>
