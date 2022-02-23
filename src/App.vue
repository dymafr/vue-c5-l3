<template>
  <h1 :style="[fontSize, color]">Bonjour le monde !</h1>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const fontSize = ref('font-size: 50px');
const color = ref('color: red');
</script>

<style scoped></style>
