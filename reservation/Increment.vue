<script setup>
import { ref } from 'vue'

/* Increment */
const number = ref(0);
const increment = () => {
  number.value++
}

/* Route Emit */
const emit = defineEmits(['emit']);
const routeTo = () => {
  emit('emit');
};

/* Show Alert Button */
const showAlert = () => {
  alert('hello world');
};


</script>

<template>
  <h1>{{ number }}</h1>
  <button style="margin-right: 10px;" @click="increment">increment</button>
  <button @click="routeTo">Route</button>

  <slot name="buttonCustom">
    <button @click="showAlert" style="background: green;">
      click me
    </button>
  </slot>
</template>