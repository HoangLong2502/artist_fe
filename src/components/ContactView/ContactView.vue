@<template>
    <div class="popup">
        <div class="popup-contact f jcb aic">
            <div class="align-l">
                <div class="h1" style="margin-bottom: 32px">Get</div> <br>
                <div class="h1">
                    in touch.
                </div>
            </div>
            <div class="f aic">
                <div class="f fdc ais px2" style="background-color: #FFFFFF15; width: 576px;">
                    <div>
                        <img src="./Default.png" alt="">
                    </div>
                    <form  
                        ref="form"
                        @submit.prevent="sendEmail"
                        class="w100 f fdc ais" style="gap : 0.75em">
                        <div class="h4">Information</div>
                        <input 
                            v-model='name'
                            class="w100 h3 border-bottom"
                            type="text" placeholder="Name">
                        <input 
                            class="w100 h3 border-bottom"
                            type="text" placeholder="Phone number">
                        <input 
                            v-model="email"
                            class="w100 h3 border-bottom"
                            type="text" placeholder="Email">
                        <input 
                            v-model="message"
                            class="w100 h3 border-bottom"
                            type="text" placeholder="Additional information">
                    </form >
                    <div 
                        @click="sendEmail"    
                        class="mt15">
                        <img src="./Default1.png" alt="">
                    </div>
                </div>
                <div>
                    <img src="./Group6.png" alt="">
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import emailjs from 'emailjs-com';
export default {
    data () {
        return {
            name: '',
            email: '',
            message: ''
        }
    },

    methods : {
        sendEmail() {
            try {
                emailjs.sendForm('service_8urgvlp', 'template_x9cumaa', this.$refs.form,
                    'U3jhmBonp1lPEhXzX', {
                    name: this.name,
                    email: this.email,
                    message: this.message
                })

            } catch(error) {
                console.log({error})
            }
            // Reset form field
            this.name = ''
            this.email = ''
            this.message = ''
        },
    }
}
</script>

<style scoped lang='scss'>
    @import 'ContactView.scss';
</style>