<script setup>
  import q from "./data/quizes.json";
  import {ref, watch} from "vue";
  import Card from "./components/Card.vue"

  const quizes = ref(q);
  const search = ref("")

  watch(search, () => {
    quizes.value = q.filter(quiz => quiz.name.toLowerCase().includes(search.value.toLowerCase()));
  });

</script>

<template>
  <div class="container">
    <header class="header">
      <h1>Quizes</h1>
      <input v-model="search" type="text" placeholder="Search..." class="search-input">
    </header>
  </div>
  <div class="options-container">
    <Card v-for="quiz in quizes" :key="quiz.id" :quiz="quiz" />
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
</style>
