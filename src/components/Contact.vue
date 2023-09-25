<script setup>
import { ref } from "vue";
import emailjs from '@emailjs/browser';


    const sent = ref(null);
    const form = ref(null)

function sendEmail() {
        console.log(form.value)
      emailjs.sendForm('service_xm4pvrz', 'template_klr71jn', form.value, '5qgiNh7uar6FZhZMQ')
        .then((result) => {
            console.log('SUCCESS!', result.text);
            sent.value = true;
        }, (error) => {
            console.log('FAILED...', error.text);
            sent.value = false;
        });
}

</script>


<template>

    <div class="contactWrapper">

        <form ref="form" @submit.prevent="sendEmail" class="contact">
            <font-awesome-icon :icon="['far', 'circle-xmark']" class="xIcon3 icon" transform="grow-6" @click="$emit('closeMenu')"/>
            <!-- <label for="name">name</label> -->
            <input type="text" id="name" name="name" placeholder="Name">
            <br>
            <br>
            <input type="text" id="email" name="email" placeholder="Email">
            <br>
            <br>
   
            <br>
            <label for="message">Send me an e-mail, you will receive a copy to the entered address, and I will be in touch shortly!</label>
            <br>
            <input type="text" id="message" name="message" placeholder="Enter your message here!">
            <br><br>
            <input type="submit" id="submit" value="Contact">
            <div v-if="success === true" class="success">
                Message Sent!
            </div>
            <div v-if="success === false" class="failure">
                Message failed to send, please try again.
            </div>
        </form>

    </div>
    
</template>

<style scoped>

    label{
        width: 50%;
        font-size: 18px;
    }

    .contactWrapper{
        height: 100vh;
        display: flex;
        align-items: center;
        font-size: 20px;
        width:50vw;
    }

    .contact{
        height: 80%;
        width: 100%;
        border: 1px solid #6c5e7b3e;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        gap: 0px;
        border-radius: 10px;
        position: relative;
    }

    input{
        background-color: rgba(49, 37, 61, 0.684);
        border: 1px solid #937aae;
        color: #dbbdfbdc;
        text-align: center;
        border-radius: 10px;
        font-family: 'Montserrat', sans-serif;
        font-size: 17px;
        font-weight: 500;
    }

    ::placeholder{
        color: #806a98b5;
    }

    #name{
        height: 50px;
    }

    #email{
        height: 50px;
    }

    #message{
        width: 50%;
        height: 30%;
    }

    #submit{
        height: 50px;
        padding: 15px;
        background-color: #7c679249;
        transition: .5s ease;
    }

    #submit:hover{
        background-color: #725e88a5;
        color: #d9b8ff;
    }


</style>
