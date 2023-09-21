<template>
    <div id="ProjectContainer">
        <h2>PROJECTS</h2>

        <div class="cardContainer">

            <div class="carousel">
                <div class="card">
                    <img src="../assets/encyclone.png" alt="">
                </div>
                <div class="card">
                    card
                </div>
                <div class="card">
                    card
                </div>
                <div class="card">
                    card
                </div>
                <div class="card">
                    card
                </div>
            </div>
        </div>
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
        height: 800px;
        display: flex;
        flex-direction: column;
        align-items: center;
        overflow: scroll;
        transform: rotate(-90deg);
        margin-top: -200px;
        
    }

    .card{
        margin: 200px;
        transform: rotate(90deg);
        height: 500px;
        width: 700px;
        object-fit: cover;
    }
    .card img{
        width: 100%;
        height: auto;
    }
</style>