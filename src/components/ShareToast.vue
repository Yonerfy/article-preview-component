<script setup>
    import { defineProps } from 'vue';

    defineProps({
        show: Boolean
    });

</script>
<template>
    <div   :style="{ visibility: show ? 'visible' : 'hidden' }"  class="share-icon-container w-[15.5em] bg-[#48556A] text-white px-[1.125em] py-[1em] rounded-lg shadow-lg flex justify-between items-center">
        <h2 class="text-preset-3 grey-400">SHARE</h2>
        <img class="" src="../assets/icon-facebook.svg" alt="">
        <img class="" src="../assets/icon-pinterest.svg" alt="">
        <img class="" src="../assets/icon-twitter.svg" alt="">
    </div>
    
</template>