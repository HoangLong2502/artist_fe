@<template>
    <div 
        v-if="showIntro"
        ref="intro"
        class="intro fixed f jcc aic z10">
        <div class="h1 relative ml075">
            <span>T</span><span style="margin-left: 5px">rung</span>
            <div class="intro--dot absolute bg-white-1 z2"></div>
            <div class="intro--bg absolute z1"></div>
        </div>
    </div>
</template>

<script>
export default {
    data () {
        return {
            showIntro : true
        }
    },

    mounted () {
        setTimeout(() => {
            this.$refs.intro.classList.add('visible')
        }, 2100),
        setTimeout(() => {
            this.showIntro = false
        }, 2500)
    }
}
</script>

<style scoped lang='scss'>
    @import 'IntroAnimation.scss';
</style>