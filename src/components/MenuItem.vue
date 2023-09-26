<script setup>
    import { ref } from 'vue';
    defineProps({

    })

    const emit = defineEmits(["clicked", 'clickedOff']);
    function emitItem(item) {
        console.log(item)
        emit("clicked", item);
    }


</script>


<template>
    <div class="menuParent">
        <div class="menuItem" @click="$emit('clicked', 'about')">
            ABOUT
        </div>
        <div class="menuItem" @click="emitItem('work')">
            WORK
        </div>
        <div class="menuItem" @click="emitItem('contact')">
            CONTACT
        </div>
    </div>
</template>


<style scoped>
    .menuParent{
        display: flex;
        flex-direction: column;
        gap: 5vh;
        justify-content: center;
        align-items: center;
        height: 100%;
        padding-left:5vw;
    }
    .menuItem{
        font-size: 120px;
        font-weight: 300;
        color: #d4b0fa;
        transition: .4s;
        cursor: default;
        letter-spacing: -9px;
        z-index: 2;
    }

    .menuItem:hover{
        color: #d0c9f3;
        transform: scale(110%);
        letter-spacing: -5px;
    }

    @media screen and (max-width: 1100px) {
        .menuParent{
            padding: 0;
            padding-top: 10vh;
        }
        .menuItem{
        font-size: 85px;
        font-weight: 300;
        color: #d4b0fa;
        transition: .4s;
        cursor: default;
        letter-spacing: -9px;
    }
    }
</style>