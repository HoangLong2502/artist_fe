@<template>
    <div class="direction__container pt5">
        <div class="direction__item f aic w100">
            <div class="item-1 w50 pl5 f fdc ais jcc">
                <div class="h2 gray">[/> No 1]</div>
                <div class="h4 mb1">
                    Creative Direction
                </div>
                <div class="h2 mb1 align-l">
                    A small team, tight deadlines, and a bootstraps-first approach to production <br>
                    led me and my colleagues to wear many hats, often several at a time. Having <br>
                    become an ACD in such an environment, i’m proud to have learned how to <br>
                    manage and mediate diverse creative personalities with unique talents, create <br> 
                    and iterate upon the great work they help produce, and always manage to <br>
                    somehow do more with less
                </div>
            </div>
            <div class="item-2 w50 f jcc aic">
                <Animation1 />
            </div>
        </div>

        <div class="direction__item f aic w100">
            <div class="item-1 w50 pl5 f fdc ais jcc">
                <div class="h2 gray">[/> No 2]</div>
                <div class="h4 mb1">
                    Information Architecture
                </div>
                <div class="h2 mb1 align-l">
                    Conduct user research using various techniques to gather information about <br>
                    user desires and needs. Analyze user researched data, then decide on the <br>
                    best solutions to make the final product as user-friendly and engaging as <br>
                    possible. Apply visual hierarchy in the presentation of product content allows <br>
                    users to understand the importance of all content elements on a page based on <br>
                    his/her brain's ability to discern differences in color, size, and alignment. <br>
                </div>
            </div>
            <div class="item-2 w50 f jcc aic">
                <Animation2 />
            </div>
        </div>

        <div class="direction__item f aic w100">
            <div class="item-1 w50 pl5 f fdc ais jcc">
                <div class="h2 gray">[/> No 3]</div>
                <div class="h4 mb1">
                    Collaboration
                </div>
                <div class="h2 mb1 align-l">
                    <pre>
In addition to the above professional skills, to bring a product to market 
requires the coordination of many departments from Sales, Marketing, PM, PO, 
Design, Dev, QA..
                    </pre>
                    <pre>
As a UX/UI Designer, I often engage in coordinating with different teams to 
define business goals, project timelines and prioritizing features, type of 
programming language used..
                    </pre>
                    <pre> 
Besides, teamwork helps me get feedback a long with other perspectives that 
I myself may have overlooked in my design process.
                    </pre>
                </div>
            </div>
            <div class="item-2 w50 f jcc aic">
                <Animation3 />
            </div>
        </div>

        <div class="direction__item f aic w100">
            <div class="item-1 w50 pl5 f fdc ais jcc">
                <div class="h2 gray">[/> No 2]</div>
                <div class="h4 mb1">
                    Communication & Presentation
                </div>
                <div class="h2 mb1 align-l">
                    This is a soft skill needed in all areas, not just UX/UI. You may have excellent <br>
                    ideas but what if you can't interpret them well to your stakeholders? Since my <br>
                    work as a UX/UI Designer requires me to coordinate with multiple teams and <br>
                    make critical arguments for the product, I have developed a confident <br>
                    communication style together with a fluid presentation flow that will inevitably <br>
                    help me make a positive impact and build trust with the audience.
                </div>
            </div>
            <div class="item-2 w50 f jcc aic">
                <Animation4 />
            </div>
        </div>
    </div>
</template>

<script>
import Animation1 from '@/components/Animation1/Animation1.vue'
import Animation2 from '@/components/Animation2/Animation2.vue'
import Animation3 from '@/components/Animation3/Animation3.vue'
import Animation4 from '@/components/Animation4/Animation4.vue'
export default {
    components : {
        Animation1,
        Animation2,
        Animation3,
        Animation4
    }
    // data () {
    //     return {
    //         dataDirection [
    //             {

    //             }
    //         ]
    //     }
    // }
}
</script>

<style scoped lang='scss'>
    @import 'DirectionList.scss';
</style>