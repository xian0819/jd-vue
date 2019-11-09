<template>
  <div class="home">
    <!-- 顶部搜索框 -->
    <NavBar index='0'></NavBar>
    <!-- 底部导航组件 -->
    <SearchBar></SearchBar>>
    <!-- 轮播图组件 -->
    <div class="swiper_box">
      <Swiper></Swiper>
    </div>
    <!-- 分类 -->
    <Cates></Cates>
    <!-- banner -->
    <Banner></Banner>
    <!-- 秒杀组件 -->
    <Skill></Skill>
    <!-- 东家小院 -->
    <div class="Ad">
      <AdStore v-for="(item,idx) in adArr" :key="idx" :item="item"></AdStore>
    </div>
    <!-- 为你推荐 -->
  <div class="rcmd_wrap">
      <div class="rcmd_wrap_title">
        <img :src="icons.rcmdIcon" alt="1">
      </div>
      <Rcmd v-for='(item, idx) in rcmdArr' :key='idx' :item='item'></Rcmd>
    </div>
  </div>
</template>

<script>
import NavBar from "@/components/NavBar.vue";
import SearchBar from "@/views/home/components/SearchBar.vue";
import Swiper from "./components/Swiper.vue";
import Cates from "./components/Cates.vue";
import Banner from "./components/Banner.vue";
import Skill from "./components/Skill.vue";
import AdStore from "./components/AdStore.vue";
import Rcmd from "./components/Rcmd.vue";

import { mapActions, mapState } from "vuex";
import {icons} from '@/assets/index'
import BScroll from '@better-scroll/core'
export default {
  data:function(){
    return{
      icons,
      page:1,
    }
  },
  components: {
    NavBar,
    SearchBar,
    Swiper,
    Cates,
    Banner,
    Skill,
    AdStore,
    Rcmd,
  },
  computed: {
    ...mapState(["adArr","rcmdArr"])
  },
  mounted() {
        // 实现数据缓存
    if (this.rcmdArr.length === 0) {
      this.getRcmd(this.page)
    }
    if (this.adArr.length === 0) {
      this.getAds()
    }
    // 实现滚动加载功能
let bs = new BScroll('.rcmd_wrap',{
       probeType:3,
       pullUpLoad:true
      })
      bs.on('scroll',()=>{
        console.log('scroll')
      })
      bs.on('scrollEnd',()=>{
        this.page++
        this.timer = setTimeout(()=>{
          bs.refresh()
        },1000)
        this.getRcmd()
      })
  },
  methods: {
    ...mapActions(["getAds",'getRcmd'])
  }
};
</script>
<style>
.swiper_box {
  width: 100%;
  height: 3.733333rem;
  background: red;
  box-sizing: border-box;
}
.Ad {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
}
</style>