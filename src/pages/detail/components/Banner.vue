<template>
  <div>
    <div class="banner" @click="handleGallaryClick">
      <img class="banner-img" :src="this.bannerImg" alt="">
      <div class="banner-info">
        <div class="banner-title">{{this.sightName}}</div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe608;</span>
          {{this.gallaryImgs.length}}
        </div>
      </div>
    </div>
    <fade-animation>
      <common-gallary :gallaryImgs="gallaryImgs"
                      v-show="show"
                      @close="handleGallaryClolse"></common-gallary>
    </fade-animation>
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
import FadeAnimation from 'common/fade/Fade'
export default {
  name: 'DetailBanner',
  components: {
    CommonGallary,
    FadeAnimation
  },
  props: {
    sightName: String,
    bannerImg: String,
    gallaryImgs: Array
  },
  data () {
    return {
      show: false
    }
  },
  methods: {
    handleGallaryClick () {
      this.show = true
    },
    handleGallaryClolse () {
      this.show = false
    }
  }
}
</script>

<style scoped>
.banner{
  position: relative;
  overflow: hidden;
  height: 0;
  padding-bottom: 55%;
}
.banner-img{
  width: 100%;
}
  .banner-info{
    display: flex;
    position: absolute;
    left: 0;
    right: 0;
    bottom: 0;
    line-height: .6rem;
    color: #ffffff;
    background-image: linear-gradient(top, rgba(0,0,0,0), rgba(0,0,0,.8));
  }
  .banner-title{
    flex: 1;
    font-size: .32rem;
    padding: 0 .2rem;
  }
  .banner-number{
    margin: .14rem .1rem 0 0;
    padding: 0 .4rem;
    line-height: .32rem;
    height: .32rem;
    font-size: .24rem;
    border-radius: .2rem;
    background-color: rgba(0,0,0,.8);
  }
  .banner-icon{
    font-size: .24rem;
  }
</style>
