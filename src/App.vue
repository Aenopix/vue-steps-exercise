<script setup>
import VSteps from '@/components/VSteps.vue'

const messages = [
  "Learn React ⚛️",
  "Apply for jobs 💼",
  "Invest your new income 🤑",
];
const messages2 = [
  "Learn React ⚛️",
  "Apply for jobs 💼",
  "Invest your new income 🤑",
  "Do another shit 😀",
  "What is wrong 😃",
  "Do it 🙌"
];
</script>

<template>
  <div>
    <VSteps :messages="messages" />
    <VSteps :messages="messages2" />
  </div>
</template>
