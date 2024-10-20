<script setup lang="ts">
defineProps({
    imgUrl: String,
    ratingValue: String,
    ratingNumber: Number,
    title: String,
    costNumber: Number,
    type: String,
})
</script>

<template>
  <div class="excursion-card">
    <img :src="imgUrl" alt="imgExcursion" />
    <div class="container">
      <div class="rating">
        <svg
          width="16"
          height="16"
          viewBox="0 0 16 16"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            fill-rule="evenodd"
            clip-rule="evenodd"
            d="M15.6324 7.01631H15.6327L11.6331 9.83514L13.1738 14.4214C13.1976 14.493 13.211 14.5689 13.211 14.6482C13.211 15.049 12.8778 15.3734 12.4666 15.3734C12.3036 15.3734 12.1532 15.3222 12.0304 15.2356L12.0301 15.2359L8 12.3955L3.96989 15.2359L3.96964 15.2356C3.84706 15.3222 3.69643 15.3734 3.5334 15.3734C3.12223 15.3734 2.78897 15.049 2.78897 14.6482C2.78897 14.5689 2.80237 14.493 2.82644 14.4214L4.36717 9.83514L0.367334 7.01631H0.367582C0.180978 6.88456 0.0593872 6.67036 0.0593872 6.42861C0.0593872 6.02827 0.392645 5.70336 0.803819 5.70336H5.75479L7.28832 1.13909C7.38162 0.84246 7.665 0.626575 8 0.626575C8.33524 0.626575 8.61837 0.84246 8.71167 1.13909L10.2452 5.70336H15.1962C15.6073 5.70336 15.9406 6.02827 15.9406 6.42861C15.9406 6.67036 15.8193 6.88456 15.6324 7.01631Z"
            fill="#FFD300"
          />
        </svg>
        <p class="rating-value">{{ ratingValue }}</p>
        <p class="rating-number">({{ratingNumber}})</p>
      </div>
      <p class="title">{{ title }}</p>
    </div>
    <div class="cost">
      <p class="cost-number">от {{ costNumber }} ₽</p>
      <p class="type">{{ type }}</p>
    </div>
  </div>
</template>

<style scoped>
.excursion-card {
  width: 345px;
  height: 332px;
  display: flex;
  flex-direction: column;
  gap: 10px;
}

img {
  width: 345px;
  height: 200px;
  vertical-align: bottom;
  border-radius: 5%;
}

svg {
  display: block;
}

.rating {
  display: flex;
  flex-direction: row;
  gap: 3px;
  font-weight: 400;
  line-height: 22px;
  align-items: center;
}

.rating-value {
  font-size: 14px;
}

.rating-number {
  font-size: 12px;
  color: #999999;
}

.title {
  font-weight: 700;
  font-size: 16px;
  line-height: 24px;
}

.cost {
  display: flex;
  flex-direction: column;
}

.cost-number {
  font-weight: 700;
  font-size: 22px;
  line-height: 32px;
  color: #444444;
  margin-top: -3px;
  margin-bottom: -3px;
}

.type {
  font-weight: 400;
  font-size: 12px;
  line-height: 22px;
  color: #999999;
  margin-top: -3px;
}
</style>
