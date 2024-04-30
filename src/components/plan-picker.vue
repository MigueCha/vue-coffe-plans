<template>
      <div ref="plansWrapper" class="plans">
      <plan-picker-item
      @select="printSelected"
      :selectedPlan="selectedPlan"
            v-for="plan in plans"
            :name="plan"
            v-bind:key="plan"/>
            <p>Counter: {{ counter }}</p>
      </div>
      </template>
       
      <script setup>
      import {ref, onMounted, onUnmounted } from 'vue';
      import planPickerItem from './plan-picker-item.vue';
      const plans = ref([
      "El soltero",
      "El adicto",
      "El viajero",
      "El colombiano"]);
      const selectedPlan= ref(null);

      const plansWrapper = ref(null);
     
      const printSelected=(playload) => {
        selectedPlan.value=playload;
      }

      //Creando una referencia reactiva para un contador
      const counter = ref(0);
      //Creando un metodo para incrementar el contador
      const processId = setInterval(() => {
            console.log('Incrementando Contador');
            counter.value++;
      }, 1000);

      //Registrando el CB (Call Back) Funcion que se ejecuta cuando un evento onMounted
      onMounted(() => {
      console.log('Componente Plan Picker montado');
      //console.log(plansWrapper.value);
      })

      //Registrando el CB de OnUnmounted
      onUnmounted (() => {
            console.log('Componente Plan Picker Desmontado');
            clearInterval(processId);
      })

      </script>
    