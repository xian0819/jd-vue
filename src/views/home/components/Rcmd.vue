<template>
  <div class="rcmd">
    <div>
      <img :src="item.src" alt />
    </div>
    <div v-text="item.desc"></div>
    <div>
      <span v-text="item.current_price"></span>
      <span>看相似</span>
    </div>
  </div>
</template>

<script>
export default {
  props: ["item"]
};
</script>

<style lang='scss' scoped>
.rcmd {
  width: 4.67rem;
  height: 7.07rem;
  box-sizing: border-box;
  display: inline-block;
  overflow: hidden;
  background: white;
  padding: 0.13rem;
  margin: 0 0.07rem;
  > div:nth-child(1) {
    img {
      display: inline-block;
      width: 4.67rem;
      height: 4.67rem;
    }
  }
  > div:nth-child(2) {
    color: #232336;
    font-size: 0.35rem;
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-line-clamp: 2;
    overflow: hidden;
    text-align: left;
    line-height: 0.48rem;
  }
  > div:nth-child(3) {
    height: 0.8rem;
    width: 100%;
    line-height: 0.8rem;
    margin-top: 0.16rem;
    > span:nth-child(1) {
      float: left;
      color: #f23030;
      font-weight: bold;
      font-size: 0.43rem;
    }
    > span:nth-child(2) {
      float: right;
      color: #686868;
      font-size: 0.32rem;
      height: 0.64rem;
      line-height: 0.64rem;
      border: 1px solid #686868;
      padding: 0 0.13rem;
      border-radius: 0.07rem;
    }
  }
}
</style>