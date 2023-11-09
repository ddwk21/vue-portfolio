<script setup>
    import Modal from './Modal.vue';
    import {ref} from 'vue';
    import splashPosterFinal from '../assets/splashPosterFinal.png';
    import triColor from '../assets/projects.png'

    const useModal = ref(false)
    const modalImage = ref(null)

    function toggleModal(filePath){
        //if I'm clicking on an image to display, set filepath
        if(filePath){
            modalImage.value = filePath;
        }

        //either way toggle modal
        useModal.value = !useModal.value
    }
</script>


<template>
    <div id="ProjectContainer">
        <div class="headerContainer">
            <font-awesome-icon :icon="['far', 'circle-xmark']" transform="shrink-6" class="xIcon2" @click="$emit('closeMenu')"/>
            <h2>PROJECTS</h2>
            

        </div>
        

        <div v-if="!useModal" class="cardContainer">

            <div class="carousel">
                
                <a href="https://github.com/ddwk21/hotline-chat" target="_blank" class="card">
                    <img src="../assets/chatSnip.png" alt="">
                    <div class="overlay"><p>WIP Firebase/React Chat App</p></div>
                </a>

                <a href="https://fierce-sands-41595.herokuapp.com/" target="_blank" class="card">
                    <img src="../assets/cycloneScreen.png" alt="">
                    <div class="overlay"><p>MERN with massive data ingestion</p></div>
                </a>
                <a href="https://we-do-application.herokuapp.com/" target="_blank" class="card">
                    <img src="../assets/wedo.jpg" alt="">
                    <div class="overlay"><p>MySQL/ Handlebars/ Express/ Node</p></div>
                </a>
                <a href="https://ddwk21.github.io/art-hub/" target="_blank" class="card">
                    <img src="../assets/arthub.jpg" alt="">
                    <div class="overlay"><p>Vanilla JS</p></div>
                </a>
                <div class="card" @click="toggleModal(splashPosterFinal)">
                    <img src="../assets/splashPosterFinal.png" alt="">
                    <div class="overlay"><p>Photoshop print marketing</p></div>
                </div>
                <div class="card" @click="toggleModal(triColor)">
                    <img src="../assets/projects.png" alt="">
                    <div class="overlay"><p>Photoshop print marketing</p></div>
                </div>
            </div>
            
        </div>

        <Modal class="modalImg" v-if="useModal" :image="modalImage" @click="toggleModal"></Modal>
        <p>scroll 	&#8594;</p>
    </div>
</template>

<style scoped>

    .modalImg{
        position: absolute;
        top: 0;
        left: 0;
    }

    #projectContainer{
        position: relative;
        height: 100vh;
        width: 100vw;
        display: flex;
        flex-direction: column;
        align-items: center;
    }
    .cardContainer{
        height: 50%;
        width: 100%;
        display: flex;
        justify-content: center;
        padding-top: 200px;
    }
    .carousel{
        width: 500px;
        height: 700px;
        display: flex;
        flex-direction: column;
        align-items: center;
        overflow: scroll;
        transform: rotate(-90deg);
        margin-top: -200px;
        scroll-snap-type: y mandatory;
        
    }

    .card{
        margin: 400px;
        transform: rotate(90deg);
        height: auto;
        width: auto;
        object-fit: cover;
        scroll-snap-align: center;
        position: relative;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .card img{
        width: auto;
        height: 300px;
        filter: brightness(80%);
        border-radius: 10px;
        border: 1px solid rgb(54, 42, 63);
    }



    p{
        font-weight: 400;
    }

    .card p{
        padding: 30px;
    }

    .xIcon2{
        position:fixed;
        margin-left: -360px;
        margin-top: 38px;
    }


    .overlay{
        position: absolute;
        top: 0;
        bottom: 0;
        left: 0;
        right: 0;
        height: 100%;
        width: 100%;
        opacity: 0;
        transition: .5s ease;
        background-color: #151117ba;
        border-radius: 10px;
        font-size: 20px;
    }

    .card:hover .overlay{
        opacity: 1;
    }

    h2{
        font-weight: 300;
    }

    @media screen and (max-width: 1100px){
        .card img{
            height: 200px;
        }

        .carousel{
            height: 400px;
        }

        h2{
            font-size: 50px;
        }

        .xIcon2{
            margin: 0;
            position: relative;
            margin-bottom: 50px;

        }
        .headerContainer{
            display: flex;
            flex-direction: column;
        }
    }


</style>