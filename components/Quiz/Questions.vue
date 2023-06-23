<script setup lang="ts">
defineProps({
  questions: Array,
})
</script>

<template>
  <div class="questions-ctr">
    <div class="progress">
      <div class="bar"></div>
      <div class="status">1 out of 3 questions answered</div>
    </div>

    <div
      v-for="({ q, answers }, index) in questions"
      :key="index"
      class="single-question"
    >
      <div class="question">{{ q }}</div>
      <div v-for="{ text } in answers" class="answers">
        <p class="answer">{{ text }}</p>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss"></style>
