<script setup>
import { RouterLink } from "vue-router";

const { numberOfCorrectAnswers, numberOfQuestions } = defineProps([
  "numberOfCorrectAnswers",
  "numberOfQuestions",
]);
</script>

<template>
  <div class="results">
    <p>Your results...</p>
    <h1>{{ numberOfCorrectAnswers }}/{{ numberOfQuestions }}</h1>
    <RouterLink to="/"> Back</RouterLink>
  </div>
</template>

<style scoped>
.results {
  text-align: center;
  padding: 50px 0;
}

p {
  font-size: 25px;
  margin: 0;
  padding: 20px 0;
}

h1 {
  font-size: 80px;
  margin: 0;
}
</style>
