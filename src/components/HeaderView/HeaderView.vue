@<template>
    <div class="header__container f jcb ais fixed w100 z10 bg-black border-bottom">
        <div class="h2">
            Trung Phan.
        </div>
        <div class="header-action">
            <marquee 
                width="350"
                hspace='50%'>
                <div class="f aic" style="gap: 1em">
                    <div class="f aic">
                        <div class="h3">
                        AVAILABLE FOR WORK
                        </div>
                        <div class="icon--heart ml05"></div>
                    </div>
                    <div class="f aic">
                        <div class="h3">
                        AVAILABLE FOR WORK
                        </div>
                        <div class="icon--heart ml05"></div>
                    </div>
                    <div class="f aic">
                        <div class="h3">
                        AVAILABLE FOR WORK
                        </div>
                        <div class="icon--heart ml05"></div>
                    </div>
                </div>
            </marquee>
        </div>

        <div 
            @click="contactStatus = true"
            class="h2 cursor">Contact</div>

        <!-- <div class="header-nav absolute f fdc ais" style="gap: 0.5em">
            <div class="h2 cursor">Home</div>
            <div class="h2 cursor">About me</div>
            <div class="h2 cursor">Work</div>
            <div class="h2 cursor">Contact</div>
        </div> -->
        <ContactView 
            v-if="contactStatus"
            @closePopup='closePopup'/>
    </div>
</template>

<script>
import ContactView from '../ContactView/ContactView.vue'
export default {
  components: { ContactView },
    data () {
        return {
            contactStatus : false
        }
    },

    methods : {
        closePopup () {
            this.contactStatus = false
        }
    }
}
</script>

<style scoped lang='scss'>
    @import 'HeaderView.scss';
</style>