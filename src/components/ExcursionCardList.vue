<script setup lang="ts">
import ExcursionCard from './ExcursionCard.vue'
</script>

<template>
  <div class="cards">
    <ExcursionCard
      img-url="https://7d9e88a8-f178-4098-bea5-48d960920605.selcdn.net/c44a3072-297f-47ac-88b8-c5ccb81cbf3d/-/quality/best/"
      ratingValue="4,8"
      :ratingNumber="467"
      title="Храм Василия Блаженного: аудиоэкскурсия с билетом"
      :costNumber="2500"
      type = "за экскурсию"
    />
    <ExcursionCard
      img-url="https://7d9e88a8-f178-4098-bea5-48d960920605.selcdn.net/c44a3072-297f-47ac-88b8-c5ccb81cbf3d/-/quality/best/"
      ratingValue="4,8"
      :ratingNumber="467"
      title="Храм Василия Блаженного: аудиоэкскурсия с билетом"
      :costNumber="2500"
      type = "за экскурсию"
    />
    <ExcursionCard
      img-url="https://7d9e88a8-f178-4098-bea5-48d960920605.selcdn.net/c44a3072-297f-47ac-88b8-c5ccb81cbf3d/-/quality/best/"
      ratingValue="4,8"
      :ratingNumber="467"
      title="Храм Василия Блаженного: аудиоэкскурсия с билетом"
      :costNumber="2500"
      type = "за экскурсию"
    />
    <ExcursionCard
      img-url="https://7d9e88a8-f178-4098-bea5-48d960920605.selcdn.net/c44a3072-297f-47ac-88b8-c5ccb81cbf3d/-/quality/best/"
      ratingValue="4,8"
      :ratingNumber="467"
      title="Храм Василия Блаженного: аудиоэкскурсия с билетом"
      :costNumber="2500"
      type = "за экскурсию"
    />
    <ExcursionCard
      img-url="https://7d9e88a8-f178-4098-bea5-48d960920605.selcdn.net/c44a3072-297f-47ac-88b8-c5ccb81cbf3d/-/quality/best/"
      ratingValue="4,8"
      :ratingNumber="467"
      title="Храм Василия Блаженного: аудиоэкскурсия с билетом"
      :costNumber="2500"
      type = "за экскурсию"
    />
    <ExcursionCard
      img-url="https://7d9e88a8-f178-4098-bea5-48d960920605.selcdn.net/c44a3072-297f-47ac-88b8-c5ccb81cbf3d/-/quality/best/"
      ratingValue="4,8"
      :ratingNumber="467"
      title="Храм Василия Блаженного: аудиоэкскурсия с билетом"
      :costNumber="2500"
      type = "за экскурсию"
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
