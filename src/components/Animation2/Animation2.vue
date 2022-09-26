@<template>
    <div>
        <div class="f ais mb15" style="width : 500px">
            <div>
                <svg width="196" height="203" viewBox="0 0 196 203" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path d="M0 0V50H5V40H15V30H25V20H35V15H45V9.995H90V188H61V203H141V188H110V10H151V15H161V20H171V30H181V40H191V50H196V0H0Z" fill="white"/>
                </svg>
            </div>
            <div class="f fdc ais w100 ml15" style="gap : 1.5em">
                <div 
                    class="w100"
                    v-for="(item, index) in [1,2,3,4,5,6,7]" :key="index">
                    <div 
                        class="w100 bg-white-1" 
                        style="height : 10px"
                        :class="'animation' + Math.floor(Math.random() * 5)"></div>
                </div>
            </div>
        </div>
        <div class="f fdc ais w100" style="gap : 1.5em">
            <div 
                class="w100"
                v-for="(item, index) in [1,2,3,4,5,6,7]" :key="index">
                <div 
                    class="width-white w100 bg-white-1" 
                    style="height : 10px"
                    :class="'animation' + Math.floor(Math.random() * 5)"
                   ></div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    computed : {
        randomNumber () {
            var number = Math.floor(Math.random() * 5) + 1
            return number
        }
    }
}
</script>

<style scoped lang='scss'>
    @import 'Animation2.scss';
</style>