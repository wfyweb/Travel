<template>
  <div class="list">
    <div class="item">
      A
    </div>
    <div class="item">
      B
    </div>
    <div class="item">
      C
    </div>
    <div class="item">
      D
    </div>
  </div>
</template>

<script>
export default {
  name: 'CityAlphabet',
  data () {
    return {

    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .list
    display flex
    flex-direction column
    justify-content center
    width .5rem
    position absolute
    top 1.56rem
    right 0
    bottom 0
    .item
      line-height .4rem
      color $bgColor
</style>
