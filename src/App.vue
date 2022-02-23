<template>
  <h1 :style="[{ fontSize: fontSize + 'px' }, color]">Bonjour le monde !</h1>
  <button @click="fontSize += 10">Grossir</button>
  <button @click="fontSize -= 10">Réduire</button>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const fontSize = ref(20);
const color = ref('color: red');
</script>

<style scoped></style>
