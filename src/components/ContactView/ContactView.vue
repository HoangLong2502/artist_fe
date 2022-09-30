@<template>
    <div ref="popup" class="popup">
        <div class="popup-contact f jcb aic">
            <div class="align-l">
                <div class="h1" style="margin-bottom: 32px">Get</div> <br>
                <div class="h1">
                    in touch.
                </div>
            </div>
            <div class="f aic">
                <div class="f fdc ais px2" style="background-color: #FFFFFF15; width: 576px;">
                    <div class="w100 f aic jcb">
                        <img src="./Default.png" alt="">
                        <div 
                            @click="handleClose"
                            class="close-popup h3 cursor">
                            x
                        </div>
                    </div>
                    <form  
                        ref="form"
                        @submit.prevent="sendEmail"
                        class="w100 f fdc ais" style="gap : 0.75em">
                        <div class="h4">Information</div>
                        <input 
                            v-model='name'
                            name="from_name"
                            class="w100 h3 border-bottom"
                            type="text" placeholder="Name">
                        <input 
                            v-model="phone"
                            name="phone"
                            class="w100 h3 border-bottom"
                            type="text" placeholder="Phone number">
                        <input 
                            v-model="email"
                            name="email"
                            class="w100 h3 border-bottom"
                            type="text" placeholder="Email">
                        <input 
                            v-model="message"
                            name="message"
                            class="w100 h3 border-bottom"
                            type="text" placeholder="Additional information">
                    </form >
                    <div 
                        @click="sendEmail"    
                        class="f aic mt15 cursor">
                        <img src="./Default1.png" alt="">
                        <div 
                            class="h3 ml05 green"
                            v-if="statusSend">
                            Gửi thông tin thành công
                        </div>
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
            message: '',
            phone : '',

            statusSend : false
        }
    },

    methods : {
        sendEmail(e) {
            try {
                emailjs.sendForm('service_8urgvlp', 'template_x9cumaa', this.$refs.form,
                    'U3jhmBonp1lPEhXzX', {
                        from_name: this.name,
                        email: this.email,
                        message: `Số điện thoại : ${this.phone} \n Email : ${this.email} \n Lời nhắn : ${this.message}`
                })

            } catch(error) {
                console.log({error})
            }
            // Reset form field
            this.name = ''
            this.email = ''
            this.message = ''
            this.phone = ''
            this.statusSend = true
        },

        handleClose () {
            this.$refs.popup.classList.add('close')
            setTimeout(() => {
                this.$emit('closePopup')
            }, 400)
        }
    }
}
</script>

<style scoped lang='scss'>
    @import 'ContactView.scss';
</style>