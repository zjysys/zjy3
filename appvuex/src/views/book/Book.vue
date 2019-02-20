<template>
    <div>
        <!-- 徜徉书海📕 -->
        <!-- <swipe class="my-swipe">
            <swipe-item class="slide1"></swipe-item>
            <swipe-item class="slide2"></swipe-item>
            <swipe-item class="slide3"></swipe-item>
        </swipe> -->
        <slide :imgs="imgs"></slide>


    </div>
</template>

<script>
    import 'vue-swipe/dist/vue-swipe.css';
    import {Swipe, SwipeItem } from 'vue-swipe';
    import Slide from '@/components/Slide.vue';
    export default {
        data(){
            return {
                imgs:[
                    "https://img3.doubanio.com/lpic/s24468373.jpg",
                    "https://img3.doubanio.com/lpic/s27102925.jpg",
                    "https://img3.doubanio.com/lpic/s6989253.jpg"

                ],
            }
        },
        components: {
            Swipe,
            SwipeItem,
            Slide
        }
        
    }
</script>

<style scoped>
.my-swipe {
  height: 200px;
  color: #fff;
  font-size: 30px;
  text-align: center;
}

.slide1 {
  background-color:mediumturquoise;
  color: #fff;
}

.slide2 {
  background-color:mediumvioletred;
  color: #000;
}

.slide3 {
  background-color:midnightblue;
  color: #fff;
}


</style>