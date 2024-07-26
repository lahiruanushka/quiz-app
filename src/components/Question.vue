<script setup>
	import {defineProps, defineEmits} from "vue"

	const emit = defineEmits(["selectOption"])

	const {question} = defineProps(['question'])

	const emitSelectedOption = (isCorrect) => {
		emit("selectOption",isCorrect)
	}
</script>
<template>
  <div class="question-container">
	    <h1 class="question">
	      {{ question.text }}
	    </h1>
  </div>
  <div class="option-container">
    <div 
    	class="option"
    	v-for="option in question.options" 
    	:key="option.id"
    	@click="emitSelectedOption(option.isCorrect)"
    >
      <p class="option-label">{{ option.label  }}</p>
      <div class="option-value">
        <p>{{ option.text }}</p>
      </div>
    </div>
</div>
</template>

<style scoped>
.question-container {
  text-align: center;
  margin: 40px 20px;
}

.question {
  font-size: 2rem;
  color: #333;
}

.option-container {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  margin: 20px;
}

.option {
  display: flex;
  align-items: center;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 10px 20px;
  margin: 10px;
  width: calc(50% - 40px);
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  transition: background-color 0.3s ease;
}

.option:hover {
  background-color: #f1f1f1;
}

.option-label {
  font-size: 1.5rem;
  font-weight: bold;
  margin-right: 10px;
  color: #76c7c0;
}

.option-value {
  flex-grow: 1;
}

.option-value p {
  margin: 0;
  font-size: 1.25rem;
  color: #333;
}

</style>