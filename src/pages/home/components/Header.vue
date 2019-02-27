<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-iconfont">&#xe624;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
      <span>输入城市/景点/默认主题</span>
    </div>
    <div class="header-right">
      <span>城市</span>
      <span class="iconfont">&#xe6aa;</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader'
}
</script>

<style scoped lang="stylus">
  @import '~styles/varibles.styl'
.header{
  display: flex;origin
  line-height: .86rem;
  background-color: $bgColor;
  color: #fff;
}
.header-left{
  width: .64rem;
  float: left;
}
.back-iconfont{
  text-align: center;
  font-size: .4rem;
}
.header-input{
  flex: 1;
  height: .64rem;
  line-height: .64rem;
  background-color: #fff;
  border-radius: .1rem;
  margin-top: .12rem;
  margin-left: .2rem;
  padding-left: .2rem;
  color: #ccc;
}
.header-right{
  width: 1.24rem;
  text-align: center;
}
</style>
