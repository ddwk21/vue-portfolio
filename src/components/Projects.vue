<template>
    <div id="ProjectContainer">
        <div class="headerContainer">
            <font-awesome-icon :icon="['far', 'circle-xmark']" transform="shrink-6" class="xIcon2" @click="$emit('closeMenu')"/>
            <h2>PROJECTS</h2>
            

        </div>
        

        <div class="cardContainer">

            <div class="carousel">
                <div class="card">
                    <img src="../assets/cycloneScreen.png" alt="">
                    <div class="overlay"><p>MERN</p></div>
                </div>
                <div class="card">
                    <img src="../assets/wedo.jpg" alt="">
                    <div class="overlay"><p>MySQL/Handlebars/Express/Node</p></div>
                </div>
                <div class="card">
                    <img src="../assets/arthub.jpg" alt="">
                    <div class="overlay"><p>Vanilla JS</p></div>
                </div>
                <div class="card">
                    <img src="../assets/splashPosterFinal.png" alt="">
                    <div class="overlay"><p>Photoshop print marketing</p></div>
                </div>
                <div class="card">
                    <img src="../assets/projects.png" alt="">
                    <div class="overlay"><p>Photoshop print marketing</p></div>
                </div>
            </div>
            
        </div>
        <p>scroll 	&#8594;</p>
    </div>
</template>

<style scoped>

    #projectContainer{
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
        margin: 200px;
        transform: rotate(90deg);
        height: auto;
        width: auto;
        object-fit: cover;
        scroll-snap-align: center;
        position: relative;
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
        height: 93%;
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


</style>