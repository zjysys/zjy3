<template>
  <div id="app">
      <c-header></c-header>
      <div id="content">
          <router-view></router-view>
      </div>
      <c-footer :menu="menu"></c-footer>
  </div>
</template>
<script>
import CHeader from "@/components/CHeader.vue";
import CFooter from "@/components/CFooter.vue";
import {mapMutations} from "vuex";
export default {
  data(){
    return {
       menu:[
         {
           path:"/movie",
           name:"电影",
           bgColor:"pink"
         },
         {
           path:"/music",
           name:"音乐",
           bgColor:"#FFA07A"
         },{
           path:"/book",
           name:"书籍",
           bgColor:"#104E8B"
         },{
           path:"/photo",
           name:"图片",
           bgColor:"#303030"
         }
       ]

    }
  },
  components: {
    CHeader,
    CFooter
  },
  methods:mapMutations(["change"]),
    
      //bg是footer中传过来的颜色  bg放到data中  再传给header
     // console.log(bg);
  created(){
    //过滤出menu数组中path值是  this.$route.path的， filter返回的是一个新数组
    //console.log(this.$route.path);

    let result = this.menu.filter((obj,index)=>{
      return obj.path == this.$route.path;
    });
    //如果数组中匹配到了  才修改obj的值 ，否则用obj的默认值
    if(result.length){
      this.change(result[0]);
    }
  }
};
</script>
<style>
#content {
  margin: 1rem 0;
}
</style>
