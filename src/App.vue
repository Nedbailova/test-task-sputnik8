<script setup lang="ts">
import LogoSputnik8 from './components/LogoSputnik8.vue'
import Heading from './components/Heading.vue'
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
</template>

<style scoped>
header {
  display: flex;
  justify-content: center;
  flex-direction: column; 
  align-items: center;
}

.logo {
  margin-top: 50px;
  margin-bottom: 30px;
}


</style>
