<script setup lang="ts">
import { ref, inject, watch } from 'vue'

const inputText = ref('')

const setInputText = inject('setInputText') as (text: string) => void

function resetExcursionName() {
  const inputElement = document.getElementById('input-search')
  if (inputElement instanceof HTMLInputElement) {
    inputElement.value = ''
    inputText.value = ''
  } else {
    console.error('Not found input with id "input-search"')
  }
}

watch(inputText, newText => {
  setInputText(newText)
})
</script>

<template>
  <input
    id="input-search"
    placeholder="Введите название экскурсии"
    v-model="inputText"
  />
  <svg
    @click="resetExcursionName"
    width="10"
    height="10"
    viewBox="0 0 10 10"
    fill="none"
    xmlns="http://www.w3.org/2000/svg"
  >
    <path
      d="M0.195262 0.195262C0.455612 -0.0650874 0.877722 -0.0650874 1.13807 0.195262L4.66667 3.72386L8.19527 0.195262C8.45562 -0.0650874 8.87773 -0.0650874 9.13808 0.195262C9.39843 0.455612 9.39843 0.877722 9.13808 1.13807L5.60948 4.66667L9.13807 8.19526C9.39842 8.45561 9.39842 8.87772 9.13807 9.13807C8.87772 9.39842 8.45561 9.39842 8.19526 9.13807L4.66667 5.60948L1.13808 9.13807C0.877726 9.39842 0.455616 9.39842 0.195266 9.13807C-0.0650833 8.87772 -0.0650833 8.45561 0.195266 8.19526L3.72386 4.66667L0.195262 1.13807C-0.0650874 0.877722 -0.0650874 0.455612 0.195262 0.195262Z"
      fill="#999999"
    />
  </svg>
</template>

<style scoped>
input {
  width: 300px;
  height: 50px;
  padding: 14.5px 19.67px 14.5px 15px;
  box-sizing: border-box;
  font-weight: 400;
  font-size: 16px;
  line-height: 21px;
  color: #999999;
  border: 1px solid #00000026;
}

input:focus {
  outline: none;
}

svg {
  position: relative;
  right: 35px;
  cursor: pointer;
}
</style>
