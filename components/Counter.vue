<!-- Create a counter component -->
<template>
  <div>
    <h1>Counter</h1>
    <p>{{ count }}</p>
    <button @click="decrement">Decrement</button>
    <button @click="increment">Increment</button>
  </div>
</template>

<script setup>
// Add logic for the counter component
const count = ref(0);
const increment = () => count.value++;
const decrement = () => count.value--;
</script>
