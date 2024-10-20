<script setup lang="ts">
import LogoSputnik8 from './components/LogoSputnik8.vue'
import Heading from './components/Heading.vue'
import ExcursionCard from './components/ExcursionCard.vue'
</script>

<template>
  <header>
    <div class="logo">
      <LogoSputnik8 />
    </div>
    <div class="heading">
      <Heading />
    </div>
  </header>

  <main>
    <div class="cards">
      <ExcursionCard/>
      <ExcursionCard/>
      <ExcursionCard/>
      <ExcursionCard/>
      <ExcursionCard/>
      <ExcursionCard/>
    </div>
  </main>
</template>

<style scoped>
header {
  display: flex;
  justify-content: center;
  flex-direction: column; 
  align-items: center;
  margin-bottom: 50px;
}

.logo {
  margin-top: 50px;
  margin-bottom: 30px;
}

.cards{
  display: grid;
  grid-template-columns: repeat(3, 395px);
  gap: 50px;
  margin-bottom: 20px;
}


</style>
