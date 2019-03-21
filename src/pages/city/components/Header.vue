<template>
  <div class="header">
    <router-link
      to="/"
      tag="div"
      class="header-left"
    >
        <div class="iconfont back-icon">&#xe624;</div>
    </router-link>
    <div class="header-title">
      城市选择
    </div>
  </div>
</template>

<script>
export default {
  name: 'CityHeader',
  data () {
    return {

    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header
    line-height: $headerHeight
    background: $bgColor
    color: #fff
    position: relation
    .header-left
      width: .64rem
      position: absolute
      top: 0
      left: 0
      .back-icon
        font-size: .24rem
        text-align: center
    .header-title
      width: 100%
      height: $headerHeight
      line-height: $headerHeight
      text-align: center
      color:#fff;
      font-size: .32rem

</style>
