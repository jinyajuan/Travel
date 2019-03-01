<template>
  <div>
    <div class="banner" @click="handleGallaryClick">
      <img class="banner-img" src="https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=935292084,2640874667&fm=27&gp=0.jpg" alt="">
      <div class="banner-info">
        <div class="banner-title">大连圣亚海洋世界(AAAA景区)</div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe608;</span>
          39
        </div>
      </div>
    </div>
    <common-gallary :imgs="imgs" v-show="show" @close="handleGallaryClolse"></common-gallary>
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: 'DetailBanner',
  components: {
    CommonGallary
  },
  data () {
    return {
      show: false,
      imgs: ['https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=2781242817,1385549877&fm=27&gp=0.jpg', 'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=2292714402,4282228802&fm=27&gp=0.jpg']
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
