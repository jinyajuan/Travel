<template>
   <div>
     <div class="recommend-title">热销推荐</div>
     <ul>
       <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
         <img class="item-img" :src="item.imgUrl" alt="">
         <div class="item-info">
           <p class="item-title">{{item.title}}</p>
           <p class="item-desc">{{item.desc}}</p>
           <button class="item-button">查看详情</button>
         </div>
       </li>
     </ul>
   </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  data () {
    return {
      recommendList: [
        {
          id: '0001',
          imgUrl: 'https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=214975775,4001050315&fm=27&gp=0.jpg',
          title: '最美沙滩',
          desc: '大连浪费主题海滩首站，浪漫主题公园'
        }, {
          id: '0002',
          imgUrl: 'https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=214975775,4001050315&fm=27&gp=0.jpg',
          title: '最美沙滩',
          desc: '大连浪费主题海滩首站，浪漫主题公园'
        }, {
          id: '0003',
          imgUrl: 'https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=214975775,4001050315&fm=27&gp=0.jpg',
          title: '最美沙滩',
          desc: '大连浪费主题海滩首站，浪漫主题公园'
        }, {
          id: '0004',
          imgUrl: 'https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=214975775,4001050315&fm=27&gp=0.jpg',
          title: '最美沙滩',
          desc: '大连浪费主题海滩首站，浪漫主题公园'
        }, {
          id: '0005',
          imgUrl: 'https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=214975775,4001050315&fm=27&gp=0.jpg',
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
