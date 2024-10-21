<script setup lang="ts">
import { ref, onMounted } from 'vue'
import ExcursionCard from './ExcursionCard.vue'

const apiUrl =
  'http://localhost:5173/v1/products?api_key=873fa71c061b0c36d9ad7e47ec3635d9&username=frontend@sputnik8.com'

const excursions = ref<any[]>([])

onMounted(() => {
  fetch(apiUrl)
    .then(response => {
      if (!response.ok) {
        throw new Error('Network response was not ok')
      }
      return response.json()
    })
    .then(Data => {
      excursions.value = Data
    })
    .catch(error => {
      console.error('Error:', error)
    })
})
</script>

<template>
  <div class="cards">
    <ExcursionCard
      v-for="excursion in excursions"
      :key="excursion.id"
      :img-url="excursion.cover_photo.big"
      :ratingValue="excursion.customers_review_rating"
      :ratingNumber="excursion.recommendation"
      :title="excursion.title"
      :costNumber="excursion.netto_price"
      type="за экскурсию"
    />
  </div>
</template>

<style scoped>
.cards {
  display: grid;
  grid-template-columns: repeat(3, 395px);
  gap: 50px;
  margin-bottom: 20px;
}
</style>
