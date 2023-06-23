<script setup lang="ts">
defineProps({
  result: { type: Number, require: true },
})
</script>

<template>
  <div class="result">
    <div class="title">You got sample result {{ result }}!</div>
    <div class="desc">Enter a short description here about the result.</div>
  </div>
</template>

<style scoped lang="scss"></style>
