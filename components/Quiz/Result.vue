<script setup lang="ts">
const props = defineProps({
  results: {
    type: Array,
    required: true,
  },
  correctAnswer: {
    type: Number,
    required: true,
  },
})

const resultIndex = computed(() => (props.correctAnswer > 2 ? 1 : 0))

const result = computed(() => props.results[resultIndex.value].desc)
</script>

<template>
  <div class="result">
    <div class="title">You got sample result {{ correctAnswer }}!</div>
    <div class="desc">{{ result }}</div>
  </div>
</template>
