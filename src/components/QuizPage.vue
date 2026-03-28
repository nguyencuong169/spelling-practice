<template>
  <div class="quiz-page">
    <h1>Quiz Interface</h1>
    <div class="question-container">
      <p v-if="currentQuestion">{{ currentQuestion.text }}</p>
      <ul>
        <li v-for="option in currentQuestion.options" :key="option.id">
          <button @click="selectOption(option)">{{ option.text }}</button>
        </li>
      </ul>
    </div>
    <button v-if="isLastQuestion" @click="submitQuiz">Submit Quiz</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentQuestionIndex: 0,
      questions: [
        { text: 'What is the capital of France?', options: [
          { id: 1, text: 'Paris' },
          { id: 2, text: 'London' },
          { id: 3, text: 'Berlin' },
          { id: 4, text: 'Madrid' }
        ] },
        { text: 'What is 2 + 2?', options: [
          { id: 5, text: '3' },
          { id: 6, text: '4' },
          { id: 7, text: '5' },
          { id: 8, text: '6' }
        ] }
      ]
    };
  },
  computed: {
    currentQuestion() {
      return this.questions[this.currentQuestionIndex];
    },
    isLastQuestion() {
      return this.currentQuestionIndex === this.questions.length - 1;
    }
  },
  methods: {
    selectOption(option) {
      // Handle option selection
      console.log('Selected option:', option);
      if (!this.isLastQuestion) {
        this.currentQuestionIndex++;
      }
    },
    submitQuiz() {
      // Handle quiz submission
      console.log('Quiz submitted!');
    }
  }
};
</script>

<style scoped>
.quiz-page {
  padding: 20px;
  font-family: Arial, sans-serif;
}
.question-container {
  margin-bottom: 20px;
}
button {
  margin: 5px;
  padding: 10px;
}
</style>
