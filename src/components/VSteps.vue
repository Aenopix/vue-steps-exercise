<script setup>
import { ref } from 'vue';
import { vAutoAnimate } from '@formkit/auto-animate'
import VStepsMessage from './VStepsMessage.vue';

const props = defineProps({
  messages: {
    type: Array,
    default: () => []
  },
  step: {
    type: Number,
    default: 1
  }
})

const currStep = ref(props.step)
const isOpen = ref(true)

function handlePrevious() {
  if (currStep.value > 1) currStep.value -= 1
}
function handleNext() {
  if (currStep.value < props.messages.length) currStep.value += 1
}
function showAlert() {
  alert(`Learn how to ${props.messages[currStep.value - 1]}`)
}
</script>

<template>
  <div v-auto-animate>
    <button class="close" @click="isOpen = !isOpen">
      &times;
    </button>

    <div v-if="isOpen" class="steps">
      <div class="numbers">
        <div v-for="(_msg, idx) in messages" :key="idx" :class="currStep > idx ? 'active' : ''">{{ idx + 1 }}</div>
      </div>
      <VStepsMessage :step="currStep">
        {{ messages[currStep - 1] }}
        <div class="buttons">
          <button :style="{ backgroundColor: '#e7e7e7', color: '#333' }" @click="showAlert">Learn how</button>
        </div>
      </VStepsMessage>
      <div class="buttons">
        <button :style="{ backgroundColor: '#7950F2', color: '#fff' }" @click="handlePrevious"><span>👈</span>
          Previous</button>
        <button :style="{ backgroundColor: '#7950F2', color: '#fff' }" @click="handleNext">Next
          <span>👉</span></button>
      </div>
    </div>
  </div>
</template>