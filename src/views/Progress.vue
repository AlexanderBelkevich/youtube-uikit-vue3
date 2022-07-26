<script setup>
import {ref} from 'vue'
import ProgressBar from '@/components/Progress/ProgressBar.vue'
import ProgressCircle from '@/components/Progress/ProgressCircle.vue'
import Button from '@/components/Button.vue'

const percentBar = ref(40)
const percentCircle = ref(60)

const addPercentBar = () => {
  percentBar.value += 10
  if (percentBar.value > 100) {
    percentBar.value = 100
  }
}

const addPercentCircle = () => {
  percentCircle.value += 10
  if (percentCircle.value > 100) {
    percentCircle.value = 100
  }
}
</script>

<template>
  <h1 class="heading-1">Progress</h1>
  <h2 class="heading-2">Progress Bar</h2>
  <div class="line line_block">
    <ProgressBar maxWidth="400px" :percent="percentBar" color="danger"/>
    <Button label="Add 10%" @click="addPercentBar"/>
  </div>
  <h2 class="heading-2">Progress Circle</h2>
  <div class="line line_block">
    <ProgressCircle :percent="percentCircle" color="warning"/>
    <Button label="Add 10%" @click="addPercentCircle"/>
  </div>
</template>