<template>
  <div class="detail">
    <detail-banner></detail-banner>
    <detail-header></detail-header>
    <detail-notice></detail-notice>
    <detail-score></detail-score>
    <div class="content">
      <detail-list :list="list"></detail-list>
    </div>
  </div>
</template>

<script>
import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
import DetailNotice from './components/Notice'
import DetailScore from './components/Score'
import DetailList from './components/List'
export default {
  name: 'Detail',
  components: {
    DetailBanner,
    DetailHeader,
    DetailScore,
    DetailNotice,
    DetailList
  },
  data () {
    return {
      list: [{
        title: '成人票',
        children: [{
          title: '成人三馆联票',
          children: [{
            title: '成人三馆联票————雨湖区分店'
          }]
        }, {
          title: '成人五馆联票'
        }, {
          title: '成人全馆联票'
        }]
      }, {
        title: '儿童票'
      }, {
        title: '特惠票'
      }]
    }
  }
}
</script>

<style scoped lang="stylus">
  .detail{
    background-color: #eee;
  }
.content{
  height 50rem
}
</style>
