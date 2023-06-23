<script setup lang="ts">
defineProps({
  questions: { type: Array, required: true },
  questionsAnswered: {
    type: Number,
    required: true,
    default: 1,
  },
})

const selectAnswer = (isCorrect: boolean) => {
  emit("onChooseAnswer", isCorrect)
}

const emit = defineEmits<{
  (e: "onChooseAnswer", isCorrect: boolean): void
}>()
</script>

<template>
  <div class="questions-ctr">
    <div class="progress">
      <div
        :style="{ width: `${(questionsAnswered / questions.length) * 100}% ` }"
        class="bar"
      ></div>
      <div class="status">
        {{ questionsAnswered + 1 }} out of 3 questions answered
      </div>
    </div>

    <div
      v-for="({ q, answers }, index) in questions"
      :key="index"
      v-show="index === questionsAnswered"
      class="single-question"
    >
      <div class="question">{{ q }}</div>
      <div class="answers">
        <p
          v-for="{ text, is_correct } in answers"
          @click="selectAnswer(is_correct)"
          class="answer"
        >
          {{ text }}
        </p>
      </div>
    </div>
  </div>
</template>
