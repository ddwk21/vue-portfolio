<script setup>

    defineProps({
        info:{
            type:String,
            required:true,
        }
    })

    const emit = defineEmits(['clickedOff']);

    function emitClose() {
        emit('clickedOff')
    }

</script>


<template>
    <div class="modalParent" @click="emitClose">

    </div>
</template>

<style scoped>
    .modalParent{
        width: 100vw;
        height: 100vh;
        background: rgba(0, 0, 0, 0.739);
        position: absolute;
        top: 0;
        left: 0;
        z-index: 3;
    }
</style>