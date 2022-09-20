@<template>
    <div class="project-list pl2 pr2">
        <div 
            v-for="(item, index) in dataWork"
            :key="index"
            @mouseover="item.showSlide = true"
            @mouseleave="item.showSlide = false"
            class="project-list__item relative cursor">
            <div 
                class="item-title f jcb aic">
                <div class="p3 white align-l">
                    {{item.title}}
                </div>
                <div class="f fdc ais">
                    <div class="h5 mb05" style="color: #646464">
                        [/> Role]
                    </div>
                    <div class="h2">
                        {{item.role}}
                    </div>
                </div>
            </div>
            <marquee 
                scrollamount
                scrolldelay='20'
                truespeed
                vspace='1000px'
                class="item-slide absolute f aic"
                style="gap : 1em">
                <div 
                    class="f aic" style="gap: 1em">
                    <div 
                        class="f aic" style="gap: 1em">
                        <div class="black p3">
                            {{item.title}}
                        </div>
                        <div>
                            <img 
                                :src="require(`${item.img}`)" alt="">
                        </div>
                    </div>
                    <div 
                        class="f aic" style="gap: 1em">
                        <div class="black p3">
                            {{item.title}}
                        </div>
                        <div>
                            <img 
                                :src="require(`${item.img}`)" alt="">
                        </div>
                    </div>
                    <div 
                        class="f aic" style="gap: 1em">
                        <div class="black p3">
                            {{item.title}}
                        </div>
                        <div>
                            <img 
                                :src="require(`${item.img}`)" alt="">
                        </div>
                    </div>
                    <div 
                        class="f aic" style="gap: 1em">
                        <div class="black p3">
                            {{item.title}}
                        </div>
                        <div>
                            <img 
                                :src="require(`${item.img}`)" alt="">
                        </div>
                    </div>
                </div>
            </marquee>
        </div>
    </div>
</template>

<script>
export default {
    data () {
        return {
            dataWork : [
                {
                    title : 'TP Bank',
                    img : './ListWork/TPBank.png',
                    role : 'UX/UI Design',
                },
                {
                    title : 'BZI Project',
                    img : './ListWork/BZI.png',
                    role : 'Project Manager'
                },
                {
                    title : 'Dr.Mom Project',
                    img : './ListWork/Dr.Mom.png',
                    role : 'Project Manager'
                },
                {
                    title : '3s Edu',
                    img : './ListWork/3s Edu App.png',
                    role : 'UX/UI Design'
                },
                {
                    title : 'MAS Training',
                    img : './ListWork/MAS Training.png',
                    role : 'UX/UI Design'
                }
            ]
        }
    }
}
</script>

<style scoped lang='scss'>
    @import 'ProjectList.scss';
</style>