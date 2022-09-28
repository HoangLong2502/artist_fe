<template>
  <div 
    class="home">
    <HeaderView />
    <div 
      id="sessionContainer"
      class="session__container">
      <div 
        id="session-1"
        class="session-1"
        :style="'width :' + 2*widthScreen + 'px'">
        <div 
          class="ele ele-1__container"
          :style="'width :' + widthScreen + 'px'">
          <HomeSession />
        </div>
        <div 
          class="ele ele-2__container"
          :style="'width :' + widthScreen + 'px'">
          <AboutMe />
        </div>
      </div>

      <div 
        :style="'width :' + widthScreen + 'px'"
        class="session-2">
        <div class="ele ele-3__container">
          <ProjectList />
        </div>
      </div>

      <div 
        id="session-3"
        :style="'width :' + 2*widthScreen + 'px'"
        class="session-3 f">
        <div class="ele ele-4__container">
          <OrderProject />
        </div>
        <div class="ele ele-4__container">
          <div class="h100 f jcc aic">
            <div class="h1">
              <div style="margin-bottom: 50px">My</div>
              Capabilities
            </div>
          </div>
        </div>
      </div>
      <div 
        :style="'width :' + widthScreen + 'px'"
        class="session-3">
        <div class="ele ele-4__container">
          <DirectionList />
        </div>
      </div>
    </div>

    <IntroAnimation />
  </div>
</template>

<script>
import HeaderView from '@/components/HeaderView/HeaderView.vue'

import HomeSession from '@/components/HomeSession/HomeSession.vue'
import AboutMe from '@/components/AboutMe/AboutMe.vue'
import ProjectList from '@/components/ProjectList/ProjectList.vue'
import OrderProject from '@/components/OrderProject/OrderProject.vue'
import DirectionList from '@/components/DirectionList/DirectionList.vue'

import IntroAnimation from '@/components/IntroAnimation/IntroAnimation.vue'

export default {
  name: 'HomeView',
  components: {
    HeaderView,
    HomeSession,
    AboutMe,
    ProjectList,
    OrderProject,
    DirectionList,
    IntroAnimation
  },

  data () {
    return {
      pointScrollY : 0,
      heightScreen : 0,
      widthScreen : 0,

      pointTranslate3d_Y : 0,
    }
  },

  mounted () {
    window.addEventListener('scroll', this.handleScroll);
    this.heightScreen = window.innerHeight;
    this.widthScreen = window.innerWidth
  },

  // watch : {
  //   'pointTranslate3d_Y' : function () {
  //     console.log(1);
  //   }
  // },

  methods: {
    async handleScroll () {
      // this.pointScrollY > window.scrollY ? this.pointTranslate3d_Y++ : this.pointTranslate3d_Y--
      
      this.pointScrollY = (window.scrollY/4)

      var number = ((window.scrollY/4)*(this.widthScreen/this.heightScreen))/(this.widthScreen*2) > 0.5 ? 0.5 : ((window.scrollY/4)*(this.widthScreen/this.heightScreen))/(this.widthScreen*2)

      var numberSession_3 = (((window.scrollY/4)*(this.widthScreen/this.heightScreen))/(this.widthScreen*2)) >= 2 ? 2 : (((window.scrollY/4)*(this.widthScreen/this.heightScreen))/(this.widthScreen*2))

      var session_1 = document.getElementById('session-1')

      var sessionContainer = document.getElementById('sessionContainer')

      var session_3 = document.getElementById('session-3')

      if (number < 0.5 && numberSession_3 < 1.5) {
        sessionContainer.style.transform = `translate3d(0, 0, 0)`
        session_1.style.transform = `translate3d(-${number*100}%, 0, 0)`
      } else if (number === 0.5 && numberSession_3 < 1.5) {
        session_1.style.transform = `translate3d(-${50}%, 0, 0)`
        sessionContainer.style.transform = `translate3d(0, -${(window.scrollY/4) - this.heightScreen}px, 0)`
        session_3.style.transform = `translate3d(-0, 0, 0)`
      } else if (number === 0.5 && 1.5 <= numberSession_3 < 1.9) {
        window.screenY = 3*this.heightScreen
        sessionContainer.style.transform = `translate3d(0, -${2*this.heightScreen}px, 0)`
        session_3.style.transform = `translate3d(-${(numberSession_3 - 1.5)*100}%, 0, 0)`
      } 
        
      if (number === 0.5 && numberSession_3 == 2) {
        // window.scroll(0, 3*this.heightScreen);
        // console.log((window.scrollY/4),'123');
        session_3.style.transform = `translate3d(-${50}%, 0, 0)`
        sessionContainer.style.transform = `translate3d(0, -${(window.scrollY/4) - 2*this.heightScreen}px, 0)`
      }
      // else if (number = 0.5) {
      //   sessionContainer.style.transform = `translate3d(0, -${window.scrollY - this.widthScreen}px, 0)`
      // }
    } 
  },


}
</script>

<style scoped lang='scss'>
  @import 'HomeView.scss';
</style>