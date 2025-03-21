<script setup>
    import { defineProps, defineEmits } from 'vue';
    defineProps({
        title: String,
        content: String,
        author: String,
        articleDate: String
    })
    const emit = defineEmits(['toggle-toast']);

    const toggleToast = () => {
        emit('toggle-toast'); // Emit the event when the button is clicked
    };

</script>
<template>
    <div class="article-card max-w-[45.625em]">
        <div class="article-container rounded-s-lg">
            <img class="article-img rounded-s-lg w-full h-full object-cover" src="../assets/drawers.jpg" alt="article image">
        </div>
        <div class="article-content rounded-r-lg bg-white p-[1.875em]">
            <h2 class="text-preset-1 mb-[1.5em]">{{ title }}</h2>
            <p class="text-preset-2 grey-500 mb-[2.5em]">{{ content }}</p>
           
            <div class="author-container flex justify-between items-center">
                <div class="author-info flex items-center">
                    <img class="w-10 h-10 rounded-full mr-[1em]" src="../assets/avatar-michelle.jpg" alt="michelle avatar">
                    <div class="author-info-container">
                        <p class="text-preset-2-bold">{{ author }}</p>
                        <p class="text-preset-2 grey-400">{{ articleDate }}</p>
                    </div>
                </div>
                
                <button @click="toggleToast"  class="rounded-full bg-[#ECF2F8] p-[.8em] flex justify-center items-center"><img src="../assets/icon-share.svg" alt=""></button>
            </div>
        </div>
    </div>
</template>