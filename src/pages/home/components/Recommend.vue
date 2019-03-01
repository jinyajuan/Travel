<template>
   <div>
     <div class="recommend-title">热销推荐</div>
     <ul>
       <router-link :to="'/detail/' + item.id" tag="li"
                    class="item border-bottom"
                    v-for="item of this.recommendList" :key="item.id">
         <img class="item-img" :src="item.imgUrl" alt="">
         <div class="item-info">
           <p class="item-title">{{item.title}}</p>
           <p class="item-desc">{{item.desc}}</p>
           <button class="item-button">查看详情</button>
         </div>
       </router-link>
     </ul>
   </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  props: {
    recommendList: Array
  },
  data () {
    return {
    }
  }
}
</script>

<style scoped lang="stylus">
  @import '~styles/mixins.styl'
.recommend-title{
  margin-top: .2rem;
  font-weight: bolder;
  line-height: .8rem;
  background-color: #eee;
  text-indent: .2rem;
}
  .item{
    overflow: hidden;
    display: flex;
    height: 1.9rem;
    /*background-color: red;*/
  }
  .item-img{
    width: 1.7rem;
    height: 1.7rem;
    padding: .1rem;
  }
  .item-info{
    flex: 1;
    padding: .1rem;
    min-width: 0;
    /*background-color: green;*/
  }
  .item-title{
    line-height: .54rem;
    font-size: .32rem
    ellipse();
  }
  .item-desc{
    line-height: .4rem;
    color: #ccc;
    ellipse();
  }
  .item-button{
    line-height: .44rem;
    margin-top: .16rem;
    background-color: #ff9300;
    padding: 0 .1rem;
    border-radius: .06rem;
    color: #fff;
  }
</style>
