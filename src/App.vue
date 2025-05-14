<template>
  <div class="app">
    <header>
      <h1>Legal Phrase Explainer</h1>
      <p class="subtitle">Understand legal terms in plain English</p>
    </header>
    
    <main>
      <SearchBar @search="handleSearch" />
      <ResultCard v-if="selectedTerm" :term="selectedTerm" />
    </main>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import SearchBar from './components/SearchBar.vue'
import ResultCard from './components/ResultCard.vue'
import terms from './data/terms.json'

const selectedTerm = ref(null)

const handleSearch = (term) => {
  selectedTerm.value = term
}
</script>

<style>
.app {
  max-width: 800px;
  margin: 0 auto;
  padding: 2rem;
  font-family: Arial, sans-serif;
}

header {
  text-align: center;
  margin-bottom: 2rem;
}

h1 {
  color: #2c3e50;
  margin-bottom: 0.5rem;
}

.subtitle {
  color: #666;
  font-size: 1.1rem;
}

main {
  background: #fff;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  padding: 1.5rem;
}
</style> 