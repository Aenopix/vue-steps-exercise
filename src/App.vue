<script setup>
import VSteps from '@/components/VSteps.vue'

const messages = [
  "Learn React ⚛️",
  "Apply for jobs 💼",
  "Invest your new income 🤑",
];
</script>

<template>
  <div>
    <VSteps :messages="messages" />
  </div>
</template>
