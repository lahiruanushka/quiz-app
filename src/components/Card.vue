<script setup>
	import {defineProps} from "vue"

	const { quiz } = defineProps(['quiz'])
</script>

<template>
	<div class="card">
      <img :src="quiz.img" alt="">
      <div class="card-text">
        <h2>{{ quiz.name }}</h2>
        <p>{{ quiz.questions.length }}</p>
      </div>
    </div>
</template>

<style scoped>
	
.card {
  background-color: #fff;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  width: calc(33.333% - 20px);
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
}

.card img {
  width: 100%;
  height: auto;
}

.card-text {
  padding: 20px;
}

.card-text h2 {
  margin: 0 0 10px;
  font-size: 1.5rem;
  color: #333;
}

.card-text p {
  margin: 0;
  color: #666;
  font-size: 1rem;
}

</style>