<template>
  <div class="score">
    <div class="score-left">
      <div class="iconfont score-left-icon">&#xe737;</div>
    </div>
    <div class="score-center">
      <span class="iconfont score-center-icon"
            v-for="(item, index) in starList" :key="index"
            v-html="item"
      >
      </span>
      <span class="iconfont score-center-icon">4.9分</span>
    </div>
    <div class="score-right">
      <div class="iconfont score-right-icon">&#xe624;</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailScore',
  data () {
    return {
      starList: []
    }
  },
  mounted () {
    for (let i = 0; i < 5; i++) {
      this.starList.push('&#xe60a;')
    }
  }
}
</script>

<style scoped lang="stylus">
  @import '~styles/varibles.styl'
.score{
  display: flex;
  width: 100%;
  height: .76rem;
  line-height: .76rem;
  margin-top: .2rem;
  font-size: .32rem;
  background: #fff;
}
.score-left{
  width: .64rem;
  float: left;
  color: $bgColor;
  /*background-color: #25a4bb;*/
}
  .score-left-icon{
    text-align: center;
    font-size: .4rem;
  }
.score-center{
  flex: 1;
  /*background-color: lawngreen;*/
}
.score-center-icon{
  color: #f8cc08;
  font-size: .35rem;
}
  .score-right{
    width: .64rem;
    float: right;
    text-align: center;
  }
  .score-right-icon{
    text-align: center;
    font-size: .32rem;
    transform: rotateY(180deg);
  }
</style>
