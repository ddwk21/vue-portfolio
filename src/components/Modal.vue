<script setup>
    const props = defineProps({
        image: String
    })
</script>

<template>
    <div class="galleryParent">

        <div class="gallery">
            <img class="galleryImg" :src='image' alt="">
        </div>

    </div>
</template>

<style scoped>
    .galleryParent{
        width: 100vw;
        height: 100vh;
        background-color: rgba(0, 0, 0, 0.608);
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .gallery{
        width: 80%;
        height: 80%;
    }
    .galleryImg{
        height: 80%;
        width: auto;
    }
</style>