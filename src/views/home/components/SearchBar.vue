<template>
  <div class="top">
    <span>
      <i class="fa fa-navicon"></i>
    </span>
    <div class="inp">
      <span class="jd">JD</span>
      <span class="line"></span>
      <i class="fa fa-search"></i>
      <input type="text" placeholder="监控摄像头" />
    </div>
    <span>登录</span>
  </div>
</template>

<script>
export default {};
</script>

<style lang='scss' scoped>
.top {
  display: flex;
  justify-content: space-around;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  height: 1.173333rem;
  background: red;
  z-index: 999;
  .inp {
    flex: 1;
    height: 0.8rem;
    line-height: 0.8rem;
    text-align: center;
    background: white;
    margin: 0.176667rem 0.193333rem 0rem;
    border-radius: 0.283333rem;
    .jd {
      font-size: 0.5rem;
      color: rgba(228, 49, 48, 1);
      font-weight: bold;
      margin-left: 0.4rem;
      float: left;
      line-height: 0.9rem;
    }
    .line {
      float: left;
      width: 0.03rem;
      height: 0.4rem;
      background-color: #ccc;
      margin-top: 0.2rem;
      margin-left: 0rem;
    }
    .fa-search {
      font-size: 0.4rem;
      color: gray;
      float: left;
      line-height: 0.9rem;
      margin: 0 0.2rem;
    }
    input {
      float: left;
      margin-top: 0.199999rem;
      outline: none;
      border: none;
    }
  }
  span {
    width: 1.066667rem;
    height: 1.173333rem;
    line-height: 1.173333rem;
    text-align: center;
    font-size: 0.38rem;
    color: white;
    .fa-navicon {
      line-height: 1.173333rem;
      font-size: 0.6rem;
    }
  }
}
</style>