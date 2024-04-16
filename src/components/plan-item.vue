<template>
    <div class="plan">
        <div class="description">
          <span class="title">
            {{ name }} 👍Likes: {{ likes }}
          </span>
        </div>
    </div>
</template>

<script setup>
defineProps({
  name: {
    type: String,
    required: true,
  },

  likes: {
    type: Number,
    default: 0,
  }
});

//Funcion ya especializada que permite crear propiedades y no se debe de importar (Macro)
//Kabeh o CamelCassing

</script>
