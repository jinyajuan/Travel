<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">{{this.currentCity}}</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="button-list">
          <div class="button-wrapper" v-for="item of this.hotCities" :key="item.id">
            <div class="button" @click="handleCityClick(item.name)">{{item.name}}</div>
          </div>
        </div>
      </div>
      <div class="area" v-for="(item, key) of this.cities" :key="key" :ref="key">
        <div class="title border-topbottom">{{key}}</div>
        <div class="item-list" v-for="innerItem of item" :key="innerItem.id">
          <div class="item border-bottom" @click="handleCityClick(innerItem.name)">{{innerItem.name}}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'
import { mapState, mapMutations } from 'vuex'
export default {
  name: 'CityList',
  props: {
    hotCities: Array,
    cities: Object,
    letter: String
  },
  mounted () {
    this.scroll = new BScroll(this.$refs.wrapper)
  },
  computed: {
    ...mapState({
      currentCity: 'city'
    })
  },
  methods: {
    handleCityClick (city) {
      this.changeCity(city)
      // this.$store.dispatch('changeCity', city)
      this.$router.push('/')
    },
    ...mapMutations(['changeCity'])
  },
  watch: {
    letter () {
      if (this.letter) {
        const element = this.$refs[this.letter][0]
        // console.log(element)
        this.scroll.scrollToElement(element)
      }
      // console.log(this.letter)
    }
  }
}
</script>

<style scoped lang="stylus">
  @import '~styles/varibles.styl'
  .border-topbottom{
    &:before{
      border-color: #ccc;
     }
    &:after{
      border-color: #ccc;
    }
  }
  .border-bottom{
  &:before{
     border-color: #ccc;
   }
  &:after{
     border-color: #ccc;
   }
  }
  .list {
    position: absolute;
    overflow: hidden;
    top: 1.68rem;
    left: 0;
    right: 0;
    bottom: 0;
    /*background-color: green;*/
  }
  .title{
    line-height: .54rem;
    background-color: #eee;
    padding-left: .2rem;
    color: #666;
    font-size: .26rem;
    font-weight: bolder;
  }
  .button-list{
    padding: .1rem .6rem .1rem .1rem;
    overflow: hidden;
  }
  .button-wrapper{
    width: 33.33%;
    float: left;
  }
  .button{
    margin: .1rem;
    padding: .1rem 0;
    text-align: center;
    border: .02rem solid #ccc;
    border-radius: .06rem;
  }
  .item-list .item{
    line-height: .76rem;
    /*color: #666;*/
    padding-left: .2rem;
  }
</style>
