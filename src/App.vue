<script setup>

  import Menu from './components/MenuItem.vue'
  import Modal from './components/Modal.vue'
  import { reactive } from 'vue';

  const modalObj = reactive({
    showModal: false,
    selection: '',
  })

  function toggleModal(item) {
    modalObj.showModal = !modalObj.showModal;
    modalObj.selection = item;
    console.log(modalObj.selection)
    console.log(modalObj.showModal)
  }


</script>

<template>
  <main>
    <div class="sidebar">
      <font-awesome-icon :icon="['fab', 'github']" size="2x" class="icon"/>
      <font-awesome-icon :icon="['fab', 'linkedin']" size="2x" class="icon"/>
      <font-awesome-icon :icon="['fas', 'envelope']" size="2x" class="icon"/>
    </div>
    <div class="summary">
      <div class="summaryContent">
        <h1>MITCHELL LEMIEUX</h1>
        <p>-engineer-designer-developer-</p>
      </div>
    </div>
    <div class="hero">
      <Menu @clicked="toggleModal"/>
    </div>

    <div class="circle" id="Circle1">Circle</div>
    <div id="Circle2"></div>
    <Modal v-if="modalObj.showModal" @clickedOff="toggleModal" :info="modalObj.selection"/>
  </main>
</template>


<style scoped>




</style>
