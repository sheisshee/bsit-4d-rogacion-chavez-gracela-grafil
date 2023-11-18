
<script setup>
import { ref } from 'vue';

// Data property
const colors = ref(['#FDE5D4', '#D6CC99', '#445D48', '#001524', '#22668D', '#EDB7ED', '#82A0D8', '#8DDFCB', '#ECEE81', '#F9DEC9', '#D80032', '#F78CA2']);
const newColor = ref('');

// Method to add a new color
const addColor = () => {
  if (newColor.value) {
    colors.value.push(newColor.value);
    newColor.value = '';
  }
};

// Method to remove a color
const removeColor = (index) => {
  colors.value.splice(index, 1);
};
</script>

<template>
</template>
