<template>
  <div class="notice">
    <div class="notice-left">
      <div class="iconfont notice-left-icon">&#xe61d;</div>
    </div>
    <div class="notice-center">
      <marquee behavior="" direction="">注意：02.01~02.28 [08:00~22:00]内前来参观，
        周末：儿童免费，成人八五折折；周内：儿童八折，成人九折；特惠票数量有限，售完为止。</marquee>
    </div>
    <div class="notice-right">
      <div class="iconfont notice-right-icon">&#xe624;</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailNotice'
}
</script>

<style scoped>
.notice{
  display: flex;
  width: 100%;
  height: .76rem;
  line-height: .76rem;
  margin-top: .2rem;
  font-size: .32rem;
  background: #facfff;
  color: #ff5388;
}
  .notice-left{
    width: .64rem;
    float: left;
    /*background: red;*/
  }
  .notice-left-icon {
    text-align: center;
    font-size: .4rem;
    transform: rotateY(180deg);
  }
  .notice-center{
    flex: 1;
    /*background: blue;*/
  }
  .notice-right{
    width: .64rem;
    float: right;
    text-align: center;
    /*background: lawngreen;*/
  }
  .notice-right-icon{
    /*background-color: lawngreen;*/
    text-align: center;
    font-size: .32rem;
    transform: rotateY(180deg);
  }
</style>
