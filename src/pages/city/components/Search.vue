<template>
  <div class="search">
    <input type="text" class="search-input" placeholder="请输入汉字或者拼音">
  </div>
</template>

<script>
export default {
  name: 'CitySearch'
}
</script>

<style scoped lang="stylus">
  @import '~styles/varibles.styl'
  .search{
    height: .72rem;
    padding: .1rem;
    background-color: $bgColor;
  }
  .search-input{
    box-sizing: border-box;
    width: 100%;
    height: .62rem;
    line-height: .62rem;
    text-align: center;
    border-radius: .06rem;
    color: #666;
    padding: 0 .1rem;
  }

</style>
