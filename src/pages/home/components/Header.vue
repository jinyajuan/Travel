<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-iconfont">&#xe624;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
      <span>输入城市/景点/默认主题</span>
    </div>
    <router-link to="/city">
      <div class="header-right">
        <span>{{this.city}}</span>
        <span class="iconfont">&#xe6aa;</span>
      </div>
    </router-link>
  </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
  name: 'HomeHeader',
  computed: {
    ...mapState(['city'])
  }
}
</script>

<style scoped lang="stylus">
@import '~styles/varibles.styl'
@import '~styles/mixins.styl'
.header{
  display: flex;
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
  min-width: 1.04rem;
  padding: 0 .1rem;
  text-align: center;
  color: #ffffff;
}
</style>
