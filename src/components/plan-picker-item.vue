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
  //Macro es una funcion especialidad en vue que me permite crear defineProps (que ya las importa), no se tiene que intregrar porque Vue ya lo hace, para agregar  nombre propiedades siempre usar camelcasing
  defineProps({
    name: {type: String, 
      required: true,}
  });
  //Esquema de propiedades de manera mas avanzada (objeto), las propiedades van dentro de las llaves {} 
  //con el objetivo de proveer un objeto, no un arreglo
  </script>
