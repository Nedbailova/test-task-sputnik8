<script setup lang="ts">
const cities = [
  { id: 1, name: 'Москва' },
  { id: 2, name: 'Санкт-Петербург' },
  { id: 3, name: 'Казань' },
  { id: 4, name: 'Сочи' },
  { id: 5, name: 'Инта' },
]

document.addEventListener('DOMContentLoaded', () => {
  const cityDropdown = document.getElementById('city-dropdown')
  if (cityDropdown) {
    cities.forEach(city => {
      const option = document.createElement('option')
      option.value = String(city.id)
      option.text = city.name
      cityDropdown.appendChild(option)
    })
  } else {
    console.error('Not found select with id "city-dropdown"')
  }
})
</script>

<template>
  <svg
    width="12"
    height="6"
    viewBox="0 0 12 6"
    fill="none"
    xmlns="http://www.w3.org/2000/svg"
  >
    <path
      d="M1.20711 0C0.761654 0 0.538571 0.538571 0.853553 0.853553L5.64645 5.64645C5.84171 5.84171 6.15829 5.84171 6.35355 5.64645L11.1464 0.853554C11.4614 0.538571 11.2383 0 10.7929 0H1.20711Z"
      fill="#DDDDDD"
    />
  </svg>

  <select id="city-dropdown">
    <option value="" hidden>Выберите город</option>
  </select>
</template>

<style scoped>
select {
  width: 300px;
  height: 50px;
  padding: 14.5px 19.67px 14.5px 15px;
  box-sizing: border-box;
  font-weight: 400;
  font-size: 16px;
  line-height: 21px;
  color: #999999;
  appearance: none;
  border: none;
  outline: none;
  border: 1px solid #00000026;
}

svg {
  position: relative;
  left: 290px;
}
</style>
