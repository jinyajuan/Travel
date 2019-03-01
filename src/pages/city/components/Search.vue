<template>
  <div>
    <div class="search">
      <input type="text" v-model="keyWord" class="search-input" placeholder="请输入汉字或者拼音">
    </div>
    <div class="search-content" ref="search" v-show="keyWord">
      <ul>
        <li class="search-item border-bottom" v-for="item of this.list" :key="item.id">{{item.name}}</li>
        <li class="search-item border-bottom search-item-no-data" v-show="hasNoData">没有找到匹配数据</li>
      </ul>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
export default {
  name: 'CitySearch',
  props: {
    cities: Object
  },
  data () {
    return {
      keyWord: '',
      list: [],
      timer: null
    }
  },
  computed: {
    hasNoData () {
      return !this.list.length
    }
  },
  watch: {
    keyWord: function () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      if (!this.list) {
        this.list = []
        return
      }
      this.timer = setTimeout(() => {
        const result = []
        for (let i in this.cities) {
          this.cities[i].forEach((value) => {
            if (value.spell.indexOf(this.keyWord) > -1 ||
                value.name.indexOf(this.keyWord) > -1) {
              result.push(value)
            }
          })
        }
        this.list = result
      }, 100)
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.search)
  }
}
</script>

<!--<style scoped >-->
<style scoped lang="stylus">
  @import '~styles/varibles.styl'
  .search{
    height: .6rem;
    padding: .1rem;
    background-color: $bgColor;
  }
  .search-input{
    box-sizing: border-box;
    width: 100%;
    height: .52rem;
    line-height: .62rem;
    text-align: center;
    border-radius: .06rem;
    color: #666;
    padding: 0 .1rem;
  }
  .search-content{
    z-index: 1;
    overflow: hidden;
    position: absolute;
    top: 1.58rem;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: #eee;
  }
  .search-item{
    line-height: .62rem;
    padding-left: .2rem;
    color: #666;
    background-color: #fff;
  }
  .search-item-no-data{
    text-align: center;
  }

</style>
