<template>
  <div class="search">
    <input type="text" placeholder="输入城市名或拼音" class="search-input" />
  </div>
</template>

<script>
export default {
  name: 'CitySearch',
  data () {
    return {

    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .search
    height $headerHeight
    background $bgColor
    padding 0 .2rem
    .search-input
      box-sizing border-box
      padding 0 .1rem
      width 100%
      height .64rem
      line-height .64rem
      border-radius .1rem
      background #fff
      color #666
      text-align center
</style>
