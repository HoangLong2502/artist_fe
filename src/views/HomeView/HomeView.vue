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
          <ProjectList />
        </div>
      </div>

      <div 
        :style="'width :' + widthScreen + 'px'"
        class="session-2">
        <div class="ele ele-3__container">
          3
        </div>
      </div>

      <div 
        :style="'width :' + widthScreen + 'px'"
        class="session-3">
        <div class="ele ele-4__container">
          4
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import HeaderView from '@/components/HeaderView/HeaderView.vue'

import HomeSession from '@/components/HomeSession/HomeSession.vue'
import ProjectList from '@/components/ProjectList/ProjectList.vue'

export default {
  name: 'HomeView',
  components: {
    HeaderView,
    HomeSession,
    ProjectList
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

  watch : {
    'pointTranslate3d_Y' : function () {
      console.log(1);
    }
  },

  methods: {
    async handleScroll () {
      this.pointScrollY > window.scrollY ? this.pointTranslate3d_Y++ : this.pointTranslate3d_Y--
      
      this.pointScrollY = window.scrollY

      var number = (window.scrollY*(this.widthScreen/this.heightScreen))/(this.widthScreen*2) > 0.5 ? 0.5 : (window.scrollY*(this.widthScreen/this.heightScreen))/(this.widthScreen*2)

      var session_1 = document.getElementById('session-1')

      var sessionContainer = document.getElementById('sessionContainer')

      if (number < 0.5) {
        sessionContainer.style.transform = `translate3d(0, 0, 0)`
        session_1.style.transform = `translate3d(-${number*100}%, 0, 0)`
      } else if (number = 0.5) {
        number = 0.5
        session_1.style.transform = `translate3d(-${50}%, 0, 0)`
        sessionContainer.style.transform = `translate3d(0, -${window.scrollY - this.heightScreen}px, 0)`
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