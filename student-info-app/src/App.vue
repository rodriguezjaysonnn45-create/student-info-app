<template>
    <HeaderComponent />
    <main class="container">
      <router-view />
    </main>
  </template>
  
  <script>
  import HeaderComponent from './components/HeaderComponent.vue'
  
  export default {
    components: {
      HeaderComponent
    }
  }
  </script>
  
  <style scoped>
  .container {
    max-width: 900px;
    margin: 30px auto;
    padding: 0 20px;
  }
  </style>
  