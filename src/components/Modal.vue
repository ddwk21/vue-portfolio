<script setup>

    import { onMounted } from 'vue';


    const props = defineProps([
        'info',
    ])

    const emit = defineEmits(['clickedOff']);


    onMounted(() => {
        console.log(props.info)
    })

    // onUpdated(() =>{
    //     console.log('Update!')
    // })

    function emitClose() {
        emit('clickedOff')
    }

</script>


<template>
    <div class='modalParent' @click="emitClose">

        <div v-if='props.info==="about"' class="modalContent aboutContent">
            <h2>About Me</h2>
            <div class="contentContainer">

                <div class="imgContainer">
                    <img src="../assets/mitchAnime2.png"/>
                </div>
                
                <div class="modalText">
                    <p>My name is Mitchell Lemieux. I love creating unique designs with cutting edge technology, like this profile photo processed using Midjourney AI.</p>
                    <br/>

                    <p>I write in a handful of JS frameworks including Vue.js and React, and am extremely capable of building a robust back-end with Node.js, Express.Js, GraphQL, mySQL, or any noSQL database technology.</p>
                    <br>
                    <p>I grew up in rural Wisconsin where I was drawn into coding at a young age, pushed by a love of game development. Out of highschool, I enrolled in a software engineering program at the local technical school - but driven by health issues, dropped out and moved to central China where I spent four years living with Daoist Kung Fu monks, and later, building a successful business.</p>
                    <br/>    
                    <p>Forced out of my home in Wuhan by the Covid-19 pandemic, I returned to pursuing a career in software, building independent projects and enrolling in a bootcamp through the University of Wisconsin.</p>
                </div>     

            </div>
        </div>

    </div>
</template>

<style scoped>
    .modalParent{
        display: flex;
        justify-content: center;
        align-items: center;
        width: 100vw;
        height: 100vh;
        background: rgba(0, 0, 0, 0.739);
        position: absolute;
        top: 0;
        left: 0;
        z-index: 3;
        padding: 20px;
    }

    .modalContent{
        height: 80%;
        width: 60%;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        background: rgba(48, 38, 60, 0.413);
        border: 2px solid rgb(113, 80, 132);
        border-radius: 10px;
        box-shadow: 5px 0px 5px rgba(0, 0, 0, 0.518);
        backdrop-filter: blur(10px);
    }

    .modalContent h2{
        font-size: 35px;
    }

    .contentContainer{
        display: flex;
        width: 100%;
        height: auto;
        padding: 60px;
        padding-left: 120px;
        padding-right: 120px;
    }

    .modalText{
        flex: 5 5 500px;
        display: flex;
        flex-direction: column;
        padding-left: 40px;

    }
    .modalText p{
        text-indent: 15px;
        line-height: 30px;
    }
    .imgContainer{
        flex: 3 3 300px;
        object-fit: cover;
        border-radius: 50%;
        
        }
    .imgContainer img{
        width: 100%;
        height: auto;
        border-radius: 50%;
    }
</style>