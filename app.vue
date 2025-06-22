<template>
  <div class="container">
    <Header />
    <MainBlock />
    <Footer />
  </div>
</template>

<script setup>
import Header from '@/components/Header.vue'
import MainBlock from '@/components/MainBlock.vue'
import Footer from '@/components/Footer.vue'
</script>

<style lang="scss">

.container {
  max-width: 100%;
  margin: 0 auto;
  padding: 20px;
}

:root {
  --font-title: 'Montserrat', sans-serif;
  --font-text: 'Open Sans', sans-serif;

  font-family: var(--font-text), sans-serif;
}

</style>