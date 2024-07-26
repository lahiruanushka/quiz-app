<script setup>
  import q from "./data/quizes.json";
  import {ref} from "vue";

  const quizes = ref(q);
  const search = ref("")

</script>

<template>
  <div class="container">
    <header class="header">
      <h1>Quizes</h1>
      <input v-mode="search" type="text" placeholder="Search..." class="search-input">
    </header>
  </div>
  <div class="options-container">
    <div v-for="quiz in quizes" :key="quiz.id" class="card">
      <img :src="quiz.img" alt="quiz.name">
      <div class="card-text">
        <h2>{{ quiz.name }}</h2>
        <p>{{ quiz.questions.lenght }}</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px;
  background-color: #f8f9fa;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.header h1 {
  color: orange;
  font-size: 2.5rem;
  margin: 0;
}

.search-input {
  padding: 10px 15px;
  border: 1px solid #ced4da;
  border-radius: 4px;
  font-size: 1rem;
}

.options-container {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  margin-top: 20px;
}

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
