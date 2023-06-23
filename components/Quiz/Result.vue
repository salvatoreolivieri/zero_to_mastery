<script setup lang="ts">
defineProps({
  result: { type: Number, required: true },
})
</script>

<template>
  <div class="result">
    <div class="title">You got sample result {{ result }}!</div>
    <div class="desc">Enter a short description here about the result.</div>
  </div>
</template>

