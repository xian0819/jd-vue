<template>
<!-- 每一个组件都需要一个根元素 -->
    <div class="navbar">
      <router-link to='/home'>
      <!-- 制作导航切换的高亮 -->
      <div v-if="index==0">
        <img :src="img.icon1on" alt="">
      </div>
        <div v-else><img :src="img.icon1" alt=""></div>
      </router-link>
      <!-- 分类的高亮切换 -->
      <router-link to='/cate'>
        <div v-if="index==1"><img :src="img.icon2on" alt=""></div>
        <div v-else><img :src="img.icon2" alt=""></div>
      </router-link>
      <router-link to='/jdm'>
        <div><img :src="img.icon3" alt=""></div>
      </router-link>
      <router-link to='/cart'>
        <div><img :src="img.icon4" alt=""></div>
      </router-link>
       <!-- 个人的高亮切换 -->
      <router-link to='/user'>
        <div v-if="index==4"><img :src="img.icon5on" alt=""></div>
         <div v-else><img :src="img.icon5" alt=""></div>
      </router-link>
    </div>
</template>
<script>

import { navicons } from "@/assets/index";
export default {
  props:['index'],//用于实现高亮样式
   data:function(){
     return{
           img:navicons
       }
   }
};
</script>

<style lang='scss' scoped>//sass的lang记得配置为scss 不然sass没有样式出来，scoped表示局部作用域
.navbar {
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
  height: 1.33rem;
  line-height: 1.33rem;
  background: white;
  z-index: 9999;
  div {
    float: left;
    width: 20%;
    text-align: center;
    box-sizing: border-box;
    img {
      display: inline-block;
      width: 1.6rem;
      height: 1.23rem;
    }
  }
}
</style>
