<template>
  <div class="container">
    <MainNavigation></MainNavigation>
    <MainContent></MainContent>
  </div>
  
</template>

<script>
import MainContent from './components/MainContent.vue'
import MainNavigation from './components/MainNavigation.vue'

export default {
  components: {
    MainContent,
    MainNavigation
  }
}
</script>

<style scoped>
.container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}
</style>