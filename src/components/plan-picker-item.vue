<template>
  <div
        @click="select"
        :class="{'selected-plan': isSelected }" 
        class="plan">
       <div class="description">
         <span class="title">  
           {{ name }}
         </span>
       </div>
     </div> 
</template>


<script setup>
import { computed } from 'vue';

//Crea una propiedad selectedPlan
//Creando Eventos
const emit = defineEmits(['select']);

//Macro es una funcion especialidad en vue que me permite crear defineProps (que ya las importa), no se tiene que intregrar porque Vue ya lo hace, para agregar  nombre propiedades siempre usar camelcasing
const props = defineProps({
 name: {
  type: String,
   required: true,},

   selectedPlan: {
    type: String
   },
});

//Definir una variable, permitiendo a cada item saber si a sido seleccionada o no

//metodo para cambiar a true
const select = ()=> {
 //Detonando el Evento
 emit('select', props.name);
}

//Esquema de propiedades de manera mas avanzada (objeto), las propiedades van dentro de las llaves {}
//con el objetivo de proveer un objeto, no un arreglo

//Creando propiedad computada
const isSelected = computed(() => {
  return props.name === props.selectedPlan;
})

</script>

<style scoped>
.selected-plan {
  background-color: blue;
}
</style>


