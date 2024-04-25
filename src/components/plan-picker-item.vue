<template>
  <div
        @click="select"
        :class="{'selected-plan':selected}" 
        class="plan">
       <div class="description">
         <span class="title">  
           {{ name }} {{ selected ? "👍" :"" }}
         </span>
       </div>
     </div>
</template>


<script setup>
import {ref} from 'vue';

//Creando Eventos
const emit = defineEmits(['select']);

//Macro es una funcion especialidad en vue que me permite crear defineProps (que ya las importa), no se tiene que intregrar porque Vue ya lo hace, para agregar  nombre propiedades siempre usar camelcasing
const props = defineProps({
 name: {type: String,
   required: true,}
});

//Definir una variable, permitiendo a cada item saber si a sido seleccionada o no
const selected = ref(false);

//metodo para cambiar a true
const select = ()=> {
 selected.value = true
 //Detonando el Evento
 emit('select', props.name);
}

//Esquema de propiedades de manera mas avanzada (objeto), las propiedades van dentro de las llaves {}
//con el objetivo de proveer un objeto, no un arreglo
</script>

<style scoped>
.selected-plan {
  background-color: blue;
}
</style>


