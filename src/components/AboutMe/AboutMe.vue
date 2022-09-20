@<template>
    <div class="about-me__container relative pt5 pl5 f jcb aic h100">
        <div class="about-me-left h100 f fdc ais jcc">
            <div 
                ref="title"
                class="about-me-left__title align-l h4 mb05">
Passionate about web technologies. I love working at the <br>
intersection of creativity and user friendly interfaces. <br>
I create memorable web experiences
            </div>
            <div 
                ref="depscription"
                class="about-me-left__depscription align-l h2 gray mb2">
With a background in design, I work closely with design focused teams to build <br>
websites and microsites for companies and individuals. I have years of <br>
experience working and collaborating on product teams and leading <br>
engineering efforts. With my experience in UI and product engineering, I solve <br>
product problems and build appealing usable web experiences.
            </div>
            <div 
                ref="experience"
                class="about-me-left__experience f aic jcc" style="gap: 5em">
                <div class="about-me-left__experience-item f fdc aic">
                    <div class="h6 mb05">
                        2+
                    </div>
                    <div class="h5">Years of UX/UI Design</div>
                </div>
                <div class="about-me-left__experience-item f fdc aic">
                    <div class="h6 mb05">
                        2+
                    </div>
                    <div class="h5">Years of Leader Design</div>
                </div>
                <div class="about-me-left__experience-item f fdc aic">
                    <div class="h6 mb05">
                        1+
                    </div>
                    <div class="h5">Years of Project Manager</div>
                </div>
            </div>
        </div>  
        <div 
            ref="aboutme"
            class="about-me-img f jce aie h100">
            <img src="../../assets/about-me.png" alt="">
        </div>

        <div 
            ref="bgaboutme"
            class="about-me-bg absolute">
            <!-- <div class="p2">
                SELECTED <br>
                WORK
            </div> -->
        </div>
    </div>
</template>

<script>
export default {
    data () {
        return {
            heightScreen : 0,
            widthScreen : 0,
        }
    },
    methods : {
        handleScroll () {
            var number = ((window.scrollY/4)*(this.widthScreen/this.heightScreen))/(this.widthScreen*2) > 0.5 ? 0.5 : ((window.scrollY/4)*(this.widthScreen/this.heightScreen))/(this.widthScreen*2)

            var numberSession_3 = (((window.scrollY/4)*(this.widthScreen/this.heightScreen))/(this.widthScreen*2)) >= 2 ? 2 : (((window.scrollY/4)*(this.widthScreen/this.heightScreen))/(this.widthScreen*2))
            
            if (number <= 0.5) {
                this.$refs.title.style.transform = `translate3d(${300*(1 - 2*number)}px, 0, 0)`
                this.$refs.depscription.style.transform = `translate3d(${400*(1 - 2*number)}px, 0, 0)`
                this.$refs.experience.style.transform = `translate3d(${400*(1 - 2*number)}px, 0, 0)`
                this.$refs.bgaboutme.style.bottom = `${100*(1 - 2*number)}px`
                this.$refs.aboutme.style.transform = `translate3d(-${(this.widthScreen - 600)*(1 - 2*number)}px, 0, 0)`
            }
        } 
    },

    mounted () {
        window.addEventListener('scroll', this.handleScroll)
        this.heightScreen = window.innerHeight;
        this.widthScreen = window.innerWidth
    }
}
</script>

<style scoped lang='scss'>
    @import 'AboutMe.scss';
</style>