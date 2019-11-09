<template>
  <div class="banner">
    <div v-for="(item,idx) in ads" :key="idx">
      <img :src="item" />
    </div>
  </div>
</template>

<script>
import { ads } from "@/assets/index";
export default {
  data: function() {
    return {
      ads
    };
  }
};
</script>

<style lang='scss' scoped>
.banner {
  display: flex;
  width: 100%;
  height: 2.67rem;
  img {
    flex: 1;
  }
}
</style>