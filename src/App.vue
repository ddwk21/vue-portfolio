<script setup>

  import { far } from '@fortawesome/free-regular-svg-icons';
  import Menu from './components/MenuItem.vue';
  import Modal from './components/Modal.vue';
  import About from './components/About.vue';
  import Projects from './components/Projects.vue';
  import Contact from './components/Contact.vue';
  import { reactive, ref } from 'vue';

  const modalObj = reactive({
    showModal: false,
    selection: '',
  })

  const showMenu = ref(true)
  const showPage = ref('')

  function toggleModal(item) {
    modalObj.showModal = !modalObj.showModal;
    modalObj.selection = item;
    console.log(modalObj.selection)
    console.log(modalObj.showModal)
  }

  function handleMenu(item) {
    
    console.log(item)
    if(item){
      showPage.value = item;
      showMenu.value = !showMenu.value;
    }

    else{
      showPage.value = ''
      showMenu.value = !showMenu.value;
    }

  }


</script>

<template>
  <main>
    <div class="sidebar">
      <font-awesome-icon :icon="['fab', 'github']" size="2x" class="icon"/>
      <font-awesome-icon :icon="['fab', 'linkedin']" size="2x" class="icon"/>
      <font-awesome-icon :icon="['fas', 'envelope']" size="2x" class="icon"/>
    </div>
    <div :class="['summary', {'onPage': !showMenu}]">
      <div :class="['summaryContent', {'aboutPage': !showMenu}]">
      <Transition>
        <h1 v-if="!showPage">MITCHELL LEMIEUX</h1>
      </Transition>
      <Transition>
        <p v-if="!showPage">-engineer-designer-developer-</p>
      </Transition>
      <Transition>
        <!-- <div class="contentContainer" v-if="showPage==='about'"> -->
        <About v-if="showPage==='about'" @closeMenu="handleMenu" class="page"></About>

      </Transition>
      <Transition>
        <Projects class="page" v-if="showPage==='work'" @closeMenu="handleMenu"></Projects>
      </Transition>

      <Transition>
        <Contact  class="page" v-if="showPage==='contact'"  @closeMenu="handleMenu"/>
      </Transition>
    </div>
    </div>
    <Transition>
    <div class="hero" v-if="showMenu">

        <Menu @clicked="handleMenu"/>
        
    </div>
    </Transition>

    <div class="circle" id="Circle1">Circle</div>
    <div id="Circle2"></div>
    <Modal v-if="modalObj.showModal" @clickedOff="toggleModal" :info="modalObj.selection"/>
  </main>
</template>


<style scoped>

  .projects{
    height:100vh;
    width:100vw
  }

  .v-enter-active{
    transition: all .8s ease;
  }
  .v-leave-active {
    transition: all 0s ease;
    opacity: 0;
  }
  .v-enter-from{
    opacity: 0;
  }
  .v-enter-to{
    opacity:1;
  }
  .v-leave-from{
    opacity:0;
  }
  .v-leave-to{
    opacity:0;
  }


</style>
