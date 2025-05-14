<template>
  <div class="result-card">
    <div class="term-header">
      <h2>{{ term.term }}</h2>
      <span class="category">{{ term.category }}</span>
    </div>
    
    <div class="content">
      <div class="section">
        <h3>Plain English Explanation</h3>
        <p>{{ term.explanation }}</p>
      </div>
      
      <div class="section">
        <h3>Example Usage</h3>
        <div class="example">
          <p>{{ term.example }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  term: {
    type: Object,
    required: true
  }
})
</script>

<style scoped>
.result-card {
  margin-top: 2rem;
  background: white;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  overflow: hidden;
}

.term-header {
  background: #f8fafc;
  padding: 1.5rem;
  border-bottom: 1px solid #e2e8f0;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.term-header h2 {
  margin: 0;
  color: #2c3e50;
  font-size: 1.5rem;
}

.category {
  background: #e2e8f0;
  color: #4a5568;
  padding: 4px 12px;
  border-radius: 16px;
  font-size: 0.875rem;
}

.content {
  padding: 1.5rem;
}

.section {
  margin-bottom: 1.5rem;
}

.section:last-child {
  margin-bottom: 0;
}

.section h3 {
  color: #4a5568;
  font-size: 1.1rem;
  margin-bottom: 0.75rem;
}

.example {
  background: #f8fafc;
  padding: 1rem;
  border-radius: 6px;
  border-left: 4px solid #4a90e2;
}

.example p {
  margin: 0;
  color: #4a5568;
  font-style: italic;
}
</style> 