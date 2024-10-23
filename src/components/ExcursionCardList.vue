<script setup lang="ts">
import { ref, onMounted, inject, watch, type Ref } from 'vue'
import ExcursionCard from './ExcursionCard.vue'
import Button from './Button.vue'

const apiUrl =
  'http://localhost:5173/v1/products?api_key=873fa71c061b0c36d9ad7e47ec3635d9&username=frontend@sputnik8.com'

const excursions = ref<any[]>([])
const filteredExcursions = ref<any[]>([])
const selectedCity = inject('selectedCity') as Ref<string | null>
const inputText = inject('inputText') as Ref<string>

function fetchExcursions(cityId: string | null) {
  let url = apiUrl
  if (cityId) {
    url += `&city_id=${cityId}`
  }

  fetch(url)
    .then(response => {
      if (!response.ok) {
        throw new Error('Network response was not ok')
      }
      return response.json()
    })
    .then(data => {
      excursions.value = data
      filterExcursions()
    })
    .catch(error => {
      console.error('Error:', error)
    })
}

function filterExcursions() {
  const searchTerm = inputText.value.toLowerCase()
  if (searchTerm) {
    filteredExcursions.value = excursions.value.filter(excursion =>
      excursion.title.toLowerCase().includes(searchTerm),
    )
  } else {
    filteredExcursions.value = excursions.value
  }
}

function getTypeText(type: string) {
  switch (type) {
    case 'tour':
      return 'за экскурсию'
    case 'entry_ticket':
      return 'за входной билет'
    case 'transfer':
      return 'за трансфер'
    case 'composite_activity':
      return 'за сборную экскурсию'
    default:
      return ''
  }
}

function priceConversion(price: string) {
  let split_price = price.split(' ')
  price = split_price[0].slice(0, -3) + ' ' + split_price[1]
  return price
}

onMounted(() => {
  fetchExcursions(null)
})

watch(selectedCity, newCity => {
  fetchExcursions(newCity)
})

watch(inputText, () => {
  filterExcursions()
})
</script>

<template>
  <div class="cards">
    <ExcursionCard
      v-for="excursion in filteredExcursions"
      :key="excursion.id"
      :img-url="excursion.cover_photo.big"
      :ratingValue="excursion.customers_review_rating"
      :ratingNumber="excursion.recommendation"
      :title="excursion.title"
      :costNumber="priceConversion(excursion.netto_price)"
      :type="getTypeText(excursion.activity_type)"
    />
  </div>
  <Button
    v-if="
      filteredExcursions.length === 0 &&
      (selectedCity !== '' || inputText !== '')
    "
  />
</template>

<style scoped>
.cards {
  display: grid;
  grid-template-columns: repeat(3, 395px);
  gap: 50px;
  margin-bottom: 20px;
}
</style>
