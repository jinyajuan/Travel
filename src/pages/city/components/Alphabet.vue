<template>
  <ul class="list">
    <li class="item" v-for="(item, key) of cities"  :key="key">{{key}}</li>
  </ul>
</template>

<script>
export default {
  name: 'CityAlphabet',
  props: {
    cities: Object
  }
}
</script>

<!--<style scoped>-->
<style scoped lang="stylus">
  @import '~styles/varibles.styl'
.list{
  position: absolute;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  right: 0;
  top: 1.58rem;
  bottom: 0;
  /*background-color: red;*/
  width: .4rem;
}
  .item{
    line-height: .4rem;
    color: $bgColor;
  }
</style>
