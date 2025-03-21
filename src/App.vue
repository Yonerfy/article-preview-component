<script setup>
  import ArticleCard from './components/ArticleCard.vue'
  import ShareToast from './components/ShareToast.vue'
  import { ref } from 'vue'
  const show = ref(false)

  const toggleToast = () => {
    show.value = !show.value; // Toggle visibility
  };
  
</script>

<template>
  <ArticleCard 
    title="Shift the overall look and feel by adding these wonderful touches to furniture in your home"
    content="Ever been in a room and felt like something was missing? Perhaps it felt slightly bare and uninviting. I’ve got some simple tips to help you make any room feel complete."
    author="Michelle Appleton"
    articleDate="28 Jun 2020"
    @toggle-toast="toggleToast" 
  />
  
  <ShareToast  :show="show" />
</template>
<style scoped>

</style>
