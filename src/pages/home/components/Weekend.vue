<template>
  <div>
    <div class="weekend-title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom" v-for="item of this.weekendList" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl" alt="">
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  props: {
    weekendList: Array
  },
  data () {
    return {
    }
  }
}
</script>

<style scoped lang="stylus">
  @import '~styles/mixins.styl'
  .weekend-title{
    /*margin-top: .2rem;*/
    line-height: .8rem;
    font-weight: bolder;
    background-color: #eee;
    text-indent: .2rem;
  }
  .item-img-wrapper{
    height: 0;
    overflow: hidden;
    padding-bottom: 37.09%;
  }
  .item-img{
    width: 100%;
  }
  .item-info{
    padding: .1rem;
    /*min-width: 0;*/
    /*background-color: green;*/
  }
  .item-title{
    line-height: .54rem;
    font-size: .32rem;
    ellipse();
  }
  .item-desc{
    line-height: .4rem;
    color: #ccc;
    ellipse();
  }
</style>
