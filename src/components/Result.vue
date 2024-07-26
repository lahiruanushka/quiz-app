<script setup>
	import {defineProps} from "vue"
	import {RouterLink} from "vue-router"

	const {quizQuestionsLength,numberOfCorrectAnswers} = defineProps(["quizQuestionsLength","numberOfCorrectAnswers"]);
</script>

<template>
  <div class="results-container">
    <div class="results">
      <p>Your Results</p>
      <h1>
      {{ numberOfCorrectAnswers }}/{{ quizQuestionsLength }}
  	 </h1>
    </div>
    <div class="button-container">
      <RouterLink
      to="/"
      ><button class="back-button">
      Go Back</button>
  	  </RouterLink>
    </div>
  </div>
</template>

<style scoped>
.results-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 40px auto;
  padding: 20px;
  background-color: #f9f9f9;
  border-radius: 10px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  width: 50%;
}

.results {
  text-align: center;
}

.results p {
  font-size: 1.25rem;
  color: #333;
  margin-bottom: 10px;
}

.results h1 {
  font-size: 2.5rem;
  color: #76c7c0;
  margin: 0;
}

.button-container {
  margin-top: 20px;
}

.back-button {
  padding: 10px 20px;
  background-color: #76c7c0;
  color: #fff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 1rem;
  transition: background-color 0.3s ease;
}

.back-button:hover {
  background-color: #5fa8a7;
}
</style>
