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
        autoplay: 5000,
        autoplayDisableOnInteraction: false
      },
      swiperList: [
        {
          id: '01',
          imgUrl: 'https://ss1.baidu.com/6ONXsjip0QIZ8tyhnq/it/u=864957796,1879425933&fm=85&app=63&f=JPEG?w=121&h=75&s=782260D82E2A172E48B9BA48030060D5'
        }, {
          id: '02',
          imgUrl: 'https://userimg.qunarzz.com/imgs/201703/08/C._M0DCiccJVdImZIei480.jpg'
        }, {
          id: '03',
          imgUrl: 'https://userimg.qunarzz.com/imgs/201703/08/C._M0DCiccJVdImZIei480.jpg'
        }, {
          id: '04',
          imgUrl: 'hhttps://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=1805190957,1621072218&fm=27&gp=0.jpg'
        }, {
          id: '05',
          imgUrl: 'https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=3169300040,1868474930&fm=27&gp=0.jpg'
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
