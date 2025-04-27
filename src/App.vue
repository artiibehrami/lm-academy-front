<template>
  <p>{{ message }}</p>
</template>

<script setup>
import { ref } from 'vue'
const message = ref('Arti')

setTimeout(() => {
  message.value = 'Perfundoj kursi per sot!'
}, 5000)
</script>

<style>
p {
  color: red;
}
</style>
