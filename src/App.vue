<script setup lang="ts">
import LogoSputnik8 from './components/LogoSputnik8.vue'
import Heading from './components/Heading.vue'
import ExcursionCardList from '././components/ExcursionCardList.vue'
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
    <ExcursionCardList />
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
</style>
