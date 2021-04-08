<template>
  <div>
    <div class="bg-green-300 w-62 h-48">
      <div class="">{{ currentNumber + 1 }} / {{ questions.length }}</div>
      <div>{{ currentQuestion }}</div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    questions: {
      type: Array,
      required: true
    }
  },
  data () {
    return {
      currentNumber: 0
    }
  },
  computed: {
    currentQuestion () {
      return this.questions[this.currentNumber].question
    }
  }
}
</script>
