<script setup>
const { questionStatus, barPercentage } = defineProps([
  "questionStatus",
  "barPercentage",
]);
</script>

<template>
  <header>
    <h4>Question {{ questionStatus }}</h4>
    <div class="bar">
      <div class="completion" :style="{ width: barPercentage }"></div>
    </div>
  </header>
</template>

<style scoped>
header {
  margin-top: 20px;
}

header h4 {
  font-size: 2rem;
  background-color: rgba(172, 74, 17, 0.852);
  padding: 5px;
  border-radius: 5px;
  font-style: bold;
  width: 50%;
  color: wheat;
  margin-bottom: 5px;
}

.bar {
  width: 300px;
  height: 30px;
  border: 3px solid rgba(172, 74, 17, 0.852);
}

.completion {
  height: 100%;
  width: 0%;
  background-color: rgba(172, 74, 17, 0.852);
}
</style>
