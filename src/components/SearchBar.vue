<template>
  <div class="search-container">
    <div class="search-input-wrapper">
      <input
        type="text"
        v-model="searchQuery"
        @input="handleInput"
        @focus="showSuggestions = true"
        placeholder="Search for a legal term..."
        class="search-input"
      />
      <div v-if="showSuggestions && filteredTerms.length > 0" class="suggestions">
        <div
          v-for="term in filteredTerms"
          :key="term.term"
          @click="selectTerm(term)"
          class="suggestion-item"
        >
          {{ term.term }}
          <span class="category">{{ term.category }}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, computed, onMounted, onUnmounted } from 'vue'
import terms from '../data/terms.json'

const searchQuery = ref('')
const showSuggestions = ref(false)
const emit = defineEmits(['search'])

const filteredTerms = computed(() => {
  if (!searchQuery.value) return []
  const query = searchQuery.value.toLowerCase()
  return terms.filter(term => 
    term.term.toLowerCase().includes(query)
  ).slice(0, 5)
})

const handleInput = () => {
  showSuggestions.value = true
}

const selectTerm = (term) => {
  searchQuery.value = term.term
  showSuggestions.value = false
  emit('search', term)
}

// Close suggestions when clicking outside
const handleClickOutside = (event) => {
  if (!event.target.closest('.search-container')) {
    showSuggestions.value = false
  }
}

onMounted(() => {
  document.addEventListener('click', handleClickOutside)
})

onUnmounted(() => {
  document.removeEventListener('click', handleClickOutside)
})
</script>

<style scoped>
.search-container {
  position: relative;
  width: 100%;
}

.search-input-wrapper {
  position: relative;
}

.search-input {
  width: 100%;
  padding: 12px 16px;
  font-size: 1rem;
  border: 2px solid #e2e8f0;
  border-radius: 8px;
  outline: none;
  transition: border-color 0.2s;
}

.search-input:focus {
  border-color: #4a90e2;
}

.suggestions {
  position: absolute;
  top: 100%;
  left: 0;
  right: 0;
  background: white;
  border: 1px solid #e2e8f0;
  border-radius: 8px;
  margin-top: 4px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  z-index: 10;
}

.suggestion-item {
  padding: 12px 16px;
  cursor: pointer;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.suggestion-item:hover {
  background-color: #f7fafc;
}

.category {
  font-size: 0.8rem;
  color: #666;
  background: #f0f0f0;
  padding: 2px 8px;
  border-radius: 12px;
}
</style> 