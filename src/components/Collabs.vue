<template>
  <div class="companies-row">
    <div class="company" v-for="company in companies" :key="company">
      {{ company }}
    </div>
  </div>
</template>

<script setup>
const companies = [
  'Ford', 'Peugeot', 'Mazda', 'Citron', 'Volks',
  'Fiat', 'Tesla', 'BMW', 'Mercedes', 'Toyota', 'MAN', 'Renault'
]
</script>

<style scoped>
.companies-row {
  justify-content: center;
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;     
  overflow-x: auto;    
  padding: 0;
  margin: 0;
  background-color: #B1AB86;
}

.company {
  padding: 10px 20px;
  white-space: nowrap;      
  border: none !important; 
  flex-shrink: 1;
  text-align: center;
}
</style>
