<template>
  <input
    class="input"
    :class="{ inputOngoing, inputError, inputValid }"
    type="text"
    @focus="
      input.focus = true;
      input.touched = true;
    "
    @blur="input.focus = false"
    v-model="input.value"
  />
</template>

<script setup lang="ts">
import { reactive, computed } from 'vue';

const input = reactive({
  value: '',
  focus: false,
  touched: false,
});

const inputOngoing = computed(() => input.focus && input.value.length);
const inputError = computed(
  () => !input.focus && input.touched && input.value.length < 5
);
const inputValid = computed(
  () => !input.focus && input.touched && !inputError.value
);
</script>

<style scoped>
input {
  outline: 0;
  border: 2px solid black;
  border-radius: 4px;
}
.inputOngoing {
  border-color: blue;
}
.inputError {
  border-color: red;
}
.inputValid {
  border-color: green;
}
</style>
