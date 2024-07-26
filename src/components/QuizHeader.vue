<script setup>
  import {defineProps} from "vue"

  const {
    questionStatus, 
    barPercentage 
  } = defineProps([
    'questionStatus',
    'barPercentage'
  ])
</script>

<template>
	  <header class="quiz-header">
      <h1>Question {{ questionStatus }}</h1>
      <div class="bar">
        <div class="completion" :style="{width: barPercentage}"></div>
      </div>
    </header>
</template>

<style scoped>
.quiz-header {
  text-align: center;
  padding: 20px;
  background-color: #f9f9f9;
  border-bottom: 2px solid #ddd;
  font-size: 1.5rem;
  font-weight: bold;
}

.bar {
  background-color: #e0e0e0;
  border-radius: 5px;
  overflow: hidden;
  height: 20px;
  margin-top: 10px;
}

.completion {
  height: 100%;
  background-color: #76c7c0;
  width: 66%; /* Adjust this dynamically */
  transition: width 0.3s ease;
}

</style>
