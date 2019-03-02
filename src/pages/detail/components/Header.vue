<template>
  <div>
    <router-link tag="div" to="/" v-show="showAbs" class="header-abs">
      <div class="iconfont header-abs-back-iconfont">&#xe624;</div>
    </router-link>
    <div class="header-fixed" v-show="!showAbs" :style="opacityStyle">
      <router-link to="/">
        <div class="iconfont header-fixed-back-iconfont">&#xe624;</div>
      </router-link>
      景点详情
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showAbs: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      // console.log('scroll')
      // console.log(document.documentElement.scrollTop)
      const top = document.documentElement.scrollTop
      if (top > 60) {
        const opacity = top / 150
        // console.log(opacity)
        this.opacity = this.opacity > 1 ? 1 : this.opacity
        this.opacityStyle = {opacity}
        this.showAbs = false
      } else {
        this.showAbs = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style scoped lang="stylus">
  @import '~styles/varibles.styl'
.header-abs{
  position: absolute;
  left: .2rem;
  top: .2rem;
  width: .8rem;
  height: .8rem;
  line-height: .8rem;
  text-align: center;
  border-radius: .4rem;
  background-color: rgba(0,0,0,.8);
}
  .header-abs-back-iconfont{
    color: white;
    font-size: .4rem;
  }
  .header-fixed{
    position: fixed;
    z-index: 3;
    top: 0;
    left: 0;
    right: 0;
    overflow: hidden;
    height: .86rem;
    line-height: .86rem;
    text-align: center;
    color: #ffffff;
    background-color: $bgColor;
    font-size: .32rem;
  }
  .header-fixed-back-iconfont{
    text-align: center;
    font-size: .4rem;
    width: .64rem;
    position: absolute;
    top: 0;
    left: 0;
    color: #fff;
  }
</style>
