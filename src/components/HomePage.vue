<template>
  <div class="home">
    <h1>Welcome to the Spelling Practice App!</h1>
    <button @click="startQuiz">Start Quiz</button>
  </div>
</template>

<script>
export default {
  name: 'HomePage',
  methods: {
    startQuiz() {
      // Logic to start quiz
    }
  }
}
</script>

<style scoped>
.home {
  text-align: center;
  margin-top: 50px;
}
button {
  padding: 10px 20px;
  font-size: 16px;
}
</style>