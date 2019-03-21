<template>
  <div class="list">
    <div class="item"
      v-for="(index, key) in cities"
      :key = "key"
    >
      {{key}}
    </div>
  </div>
</template>

<script>
export default {
  name: 'CityAlphabet',
  props: {
    cities: Object
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
    top 1.72rem
    right 0
    bottom 0
    .item
      line-height .4rem
      color $bgColor
</style>
