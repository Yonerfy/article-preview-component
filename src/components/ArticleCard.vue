<script setup>
    import { defineProps, defineEmits } from 'vue';
    import { ref } from 'vue';
    const show = ref(false);
    const showAuthor = ref(true);
    defineProps({
        title: String,
        content: String,
        author: String,
        articleDate: String,
    
    })
    const emit = defineEmits(['toggle-toast']);

    const toggleToast = () => {
        emit('toggle-toast'); // Emit the event when the button is clicked
    };

    const toggleToastMobile = () => {
        show.value = !show.value; // Toggle visibility
        showAuthor.value = !showAuthor.value;
        if(show.value === false) {
            showAuthor.value = true; 
        }
    };



</script>
<template>
    <div class="article-card max-w-[45.625em]">
        <div class="article-container rounded-s-lg">
            <img class="article-img rounded-t-lg md:rounded-s-lg w-full h-full object-cover" src="../assets/drawers.jpg" alt="article image">
        </div>
        <div class="article-content md:rounded-r-lg bg-white p-[1.875em]" :class="{ 'rounded-b-lg': !show }">
            <h2 class="text-preset-1 mb-[1.5em]">{{ title }}</h2>
            <p class="text-preset-2 grey-500 mb-[2.5em]">{{ content }}</p>
           
            <div  :style="{visibility: showAuthor ? 'visible' : 'hidden'}" class="author-container justify-between items-center md:hidden sm:flex flex">
                <div class="author-info flex items-center">
                    <img class="w-10 h-10 rounded-full mr-[1em]" src="../assets/avatar-michelle.jpg" alt="michelle avatar">
                    <div class="author-info-container">
                        <p class="text-preset-2-bold">{{ author }}</p>
                        <p class="text-preset-2 grey-400">{{ articleDate }}</p>
                    </div>
                </div>
                
                <button @click="() => { toggleToast(); toggleToastMobile(); }" class="rounded-full bg-[#ECF2F8] p-[.8em] flex justify-center items-center"><img src="../assets/icon-share.svg" alt=""></button>
            </div>
            
            <div class="author-container justify-between items-center hidden md:flex">
                <div class="author-info flex items-center">
                    <img class="w-10 h-10 rounded-full mr-[1em]" src="../assets/avatar-michelle.jpg" alt="michelle avatar">
                    <div class="author-info-container">
                        <p class="text-preset-2-bold">{{ author }}</p>
                        <p class="text-preset-2 grey-400">{{ articleDate }}</p>
                    </div>
                </div>
                
                <button @click="() => { toggleToast();}" class="rounded-full bg-[#ECF2F8] p-[.8em] flex justify-center items-center"><img src="../assets/icon-share.svg" alt=""></button>
            </div>

        </div>
        <div :style="{visibility: show ? 'visible' : 'hidden'}"  class="share-mobile-btn md:hidden visible">
            <div class=" bg-[#48556A] text-white px-[2em] py-[1.5em] rounded-b-lg shadow-lg flex justify-between items-center">
                <h2 class="text-preset-3 grey-400">SHARE</h2>
                <img class="" src="../assets/icon-facebook.svg" alt="">
                <img class="" src="../assets/icon-pinterest.svg" alt="">
                <img class="pr-[3em]" src="../assets/icon-twitter.svg" alt="">
                <button @click="toggleToastMobile" class="rounded-full bg-[#6E8098] p-[.8em] flex justify-center items-center"><img class="" src="../assets/icon-share-white.svg" alt=""></button>
            </div>
        </div>
    </div>
</template>