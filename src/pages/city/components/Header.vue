<template>
  <div class="header">
    城市选择
    <router-link to="/">
      <div class="iconfont header-iconfont">&#xe624;</div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style scoped lang="stylus">
  @import '~styles/varibles.styl'
.header{
  overflow: hidden;
  /*position: relative;*/
  height: .86rem;
  line-height: .86rem;
  text-align: center;
  color: #ffffff;
  background-color: red;
  font-size: .32rem;
}
  .header-iconfont{
    text-align: center;
    font-size: .4rem;
    width: .64rem;
    position: absolute;
    top: 0;
    left: 0;
    color: #fff;
  }
</style>
