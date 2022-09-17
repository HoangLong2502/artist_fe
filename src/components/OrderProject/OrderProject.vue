@<template>
    <div class="order-project__container pt5 pl5 pr5">
        <div class="order-project__title align-l h2 mb2">
            Older project
        </div>
        <div class="order-project__body">
            <div 
                v-for="(item, index) in dataProject"
                :key="index"
                class="order-project__item px15 border-radius f jcb ais bg-white-1">
                <div class="infor f fdc ais">
                    <div class="mb15">
                        <img :src="require(`${item.logo}`)" alt="">
                    </div>
                    <div class="mb05 black">
                        <div class="h2">
                            {{item.title}}
                        </div>
                    </div>
                    <div class="black">
                        <div class="h3">
                            {{item.time}}
                        </div>
                    </div>
                </div>

                <div class="position relative border-radius pl1 pr1">
                    <div class="p4 black">
                        UI Design
                    </div>
                    <img 
                        src="./ListProject/8bit.png" alt="" 
                        class="bit-border bit-top-left">
                    <img 
                        src="./ListProject/8bit.png" alt="" 
                        class="bit-border bit-top-right">
                    <img 
                        src="./ListProject/8bit.png" alt="" 
                        class="bit-border bit-bottom-right">
                    <img 
                        src="./ListProject/8bit.png" alt="" 
                        class="bit-border bit-bottom-left">
                    <img 
                        src="./ListProject/8bit_width.png" alt="" 
                        class="bit-border bit-width-top">
                    <img 
                        src="./ListProject/8bit_width.png" alt="" 
                        class="bit-border bit-width-bottom">
                    <img 
                        src="./ListProject/8bit_height.png" alt="" 
                        class="bit-border bit-height-top">
                    <img 
                        src="./ListProject/8bit_height.png" alt="" 
                        class="bit-border bit-height-bottom">
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data () {
        return {
            dataProject : [
                {
                    title : 'Men Project',
                    logo : './ListProject/Men.png',
                    time : '2019 - Outsource'
                },
                {
                    title : 'Nothan',
                    logo : './ListProject/Nothan.png',
                    time : '2019 - Product'
                }
                ,
                {
                    title : 'Samacom',
                    logo : './ListProject/Samacom.png',
                    time : '2019 - Outsource'
                }
                ,
                {
                    title : 'MRN Trading',
                    logo : './ListProject/MRN Trading.png',
                    time : '2020 - Outsource'
                }
                ,
                {
                    title : 'Brilliant Fashion',
                    logo : './ListProject/Brilliant Fashion.png',
                    time : '2018 - Theme'
                }
                ,
                {
                    title : 'Hosoren',
                    logo : './ListProject/Hosoren.png',
                    time : '2018 - Theme'
                }
                ,
                {
                    title : 'Caruso',
                    logo : './ListProject/Caruso.png',
                    time : '2018 - Theme'
                }
            ]
        }
    }
}
</script>

<style scoped lang='scss'>
    @import 'OrderProject.scss';
</style>