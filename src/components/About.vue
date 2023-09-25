<template>

    <div class="contentContainer">
        <h1>MITCHELL LEMIEUX</h1>
        <p class="engage">-engineer-designer-developer-</p>
        <font-awesome-icon :icon="['far', 'circle-xmark']" transform="shrink-6" class="xIcon" @click="$emit('closeMenu')"/>
        <div class="imgContainer">
            <img src='../assets/midjourneyMitch.png'/>
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

</template>

<style scoped>
    .imgContainer{
        margin-top:50px;
    }

    .engage{
        top: 15px;
    }

</style>