<template>
  <div class="swiper">
    <mt-swipe :auto="2000">
      <mt-swipe-item v-for="(item,idx) in swiper" :key="idx">
        <img :src="item.src" />
      </mt-swipe-item>
    </mt-swipe>
  </div>
</template>

<script>
import { swiper } from "@/assets/index";
export default {
  data: function() {
    return {
      swiper
    };
  }
};
</script>

<style>
.swiper {
  width: 9.333333rem;
  height: 3.73333rem;
  margin: 0 auto;
  padding-top: 0.106667rem;
  padding-bottom: 0.186667rem;
  box-sizing: border-box;
}
img {
  width: 100%;
  height: 100%;
  border-radius: 0.13rem;
}
</style>