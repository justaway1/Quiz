<script setup>
const { question } = defineProps(["question"]);
const emit = defineEmits(["selectOption"]);

const emitSelectedOption = (isCorrect) => {
  emit("selectOption", isCorrect);
};
</script>

<template>
  <div class="question-container">
    <h1 class="question">{{ question.text }}</h1>
  </div>
  <div class="options-container">
    <div
      v-for="option in question.options"
      :key="option.id"
      class="option"
      @click="emitSelectedOption(option.isCorrect)"
    >
      <p class="option-label">{{ option.label }}</p>
      <div class="option-value">
        <p>{{ option.text }}</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.options-container {
  margin-top: 30px;
}

.option {
  display: flex;
  margin-bottom: 30px;
  cursor: pointer;
}

.option-label {
  width: 50px;
  height: 50px;
  background-color: rgba(172, 74, 17, 0.852);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 30px;
  color: wheat;
  margin: 0;
}

.option-value {
  width: 100%;
  background-color: rgb(240, 230, 233);
  font-size: 30px;
  padding: 0 20px;
  display: flex;
  align-items: center;
}

.option-value p {
  margin: 0;
}
</style>
