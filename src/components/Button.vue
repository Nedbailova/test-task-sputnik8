<script setup lang="ts">
import { ref, inject, type Ref } from 'vue'


const inputText = inject('inputText') as Ref<string>
const selectedCity = inject('selectedCity') as Ref<string | null>

function resetExcursionName() {
  const inputElement = document.getElementById('input-search')
  if (inputElement instanceof HTMLInputElement) {
    inputElement.value = ''
    inputText.value = ''
  } else {
    console.error('Not found input with id "input-search"')
  }
}

function resetSelection() {
  selectedCity.value = ''
  const dropdown = document.getElementById('city-dropdown')
  if (dropdown instanceof HTMLSelectElement) {
    dropdown.selectedIndex = 0
  } else {
    console.error('Not found input with id "city-dropdown"')
  }
}

function resetFilters() {
  resetExcursionName()
  resetSelection()
}
</script>

<template>
  <div class="button-block">
    <h2>Поиск не дал результатов</h2>
    <button @click="resetFilters">Сбросить фильтры</button>
  </div>
</template>

<style scoped>
.button-block {
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
}

button {
  width: 199px;
  height: 40px;
  background-color: #00a7ff;
  font-weight: 400;
  font-size: 14px;
  line-height: 40px;
  color: #fff;
  border: none;
  border-radius: 3px;
}

h2 {
  font-weight: 400;
  font-size: 24px;
  line-height: 34px;
  margin-bottom: 30px;
  margin-top: 110px;
}
</style>
