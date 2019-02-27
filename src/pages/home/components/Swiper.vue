<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <swiper-slide v-for="item of swiperList" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl" alt="">
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HeaderSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true,
        autoplay: 3000,
        autoplayDisableOnInteraction: false
      },
      swiperList: [
        {
          id: '001',
          imgUrl: 'https://userimg.qunarzz.com/imgs/201812/16/C._M0DCiii8DRUHX9Ni480.jpg'
        }, {
          id: '002',
          imgUrl: 'https://userimg.qunarzz.com/imgs/201703/08/C._M0DCiccJVdImZIei480.jpg'
        }, {
          id: '003',
          imgUrl: 'https://userimg.qunarzz.com/imgs/201812/16/C._M0DCiiges-VurbHi480.jpg'
        }
      ]
    }
  }
}
</script>

<style lang="stylus" scoped>
.wrapper >>> .swiper-pagination-bullet-active{
  background-color: white !important;
}
.wrapper{
  overflow: hidden;
  width: 100%;
  height: 0;
  padding-bottom: 31.25%;
  background-color: #ccc;
}
.swiper-img{
  width: 100%;
}
</style>
