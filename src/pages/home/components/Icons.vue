<template>
    <div class="icons">
      <swiper :options="swiperOption">
        <swiper-slide v-for="(page, index) of pages" :key="index">
          <div class="icon" v-for="item of page" :key="item.id">
            <div class="icon-img">
              <img class="icon-img-content" :src="item.imgUrl" alt="">
            </div>
            <p class="icon-desc">{{item.desc}}</p>
          </div>
        </swiper-slide>
      </swiper>
    </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  props: {
    iconList: Array
  },
  data () {
    return {
      swiperOption: {
        autoplay: false
      }
    }
  },
  computed: {
    pages () {
      var pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style scoped lang="stylus">
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
.icons>>> .swiper-container{
  /*overflow: hidden;*/
  width: 100%;
  height: 0;
  padding-bottom: 50%;
  /*background-color: green;*/
}
  .icons{
    margin-top: .2rem;
  }
  .icon{
    position: relative;
    overflow: hidden;
    width: 25%;
    height: 0;
    padding-bottom: 25%;
    float: left;
    /*background-color: red;*/
  }
  .icon-img{
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: .44rem;
    box-sizing: border-box;
    padding: .1rem;
    /*background-color: #25a4bb;*/
  }
  .icon-img-content{
    display: block;
    margin: 0 auto;
    height: 100%;
    /*width: 100%;*/
  }
  .icon-desc{
    position: absolute;
    left: 0;
    right: 0;
    bottom: 0;
    line-height: .44rem;
    height: .44rem;
    text-align: center;
    color: $darkTextColor;
    ellipse()
  }
</style>
