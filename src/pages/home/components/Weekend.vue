<template>
  <div>
    <div class="weekend-title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
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
  data () {
    return {
      recommendList: [
        {
          id: '0001',
          imgUrl: 'https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=4210357361,3764590159&fm=27&gp=0.jpg',
          title: '最美沙滩',
          desc: '大连浪费主题海滩首站，浪漫主题公园'
        }, {
          id: '0002',
          imgUrl: 'https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=4210357361,3764590159&fm=27&gp=0.jpg',
          title: '最美沙滩',
          desc: '大连浪费主题海滩首站，浪漫主题公园'
        }, {
          id: '0003',
          imgUrl: 'https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=4210357361,3764590159&fm=27&gp=0.jpg',
          title: '最美沙滩',
          desc: '大连浪费主题海滩首站，浪漫主题公园'
        }
      ]
    }
  }
}
</script>

<style scoped lang="stylus">
  @import '~styles/mixins.styl'
  .weekend-title{
    margin-top: .2rem;
    line-height: .8rem;
    font-weight: bolder;
    background-color: #eee;
    text-indent: .2rem;
  }
  .item-img-wrapper{
    height: 0;
    overflow: hidden;
    padding-bottom: 33.9%;
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
