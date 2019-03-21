<template>
  <div class="list" ref='wrapper'>
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <ul class="bottom-list">
          <li class="bottom-wrapper">
            <span class="button">上海</span>
          </li>
        </ul>
      </div>
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <ul class="bottom-list">
          <li class="bottom-wrapper"
            v-for="item in hot"
            :key = "item.id"
          >
            <span class="button">{{item.name}}</span>
          </li>
        </ul>
      </div>
      <div class="area"
       v-for="(item,key) of cities"
       :key = "key"
      >
        <div class="title border-topbottom">{{key}}</div>
        <ul class="item-list">
          <li class="item border-bottom"
           v-for="info of item"
           :key = "info.id"
          >
            {{info.name}}
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'
export default {
  name: 'CityList',
  props: {
    hot: Array,
    cities: Object
  },
  mounted () {
    this.scroll = new BScroll(this.$refs.wrapper)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .border-topbottom
    &:before
      border-color: #ccc
    &:after
      border-color: #ccc
  .list
    overflow hidden
    width 100%
    position absolute
    top 1.72rem
    left 0
    bottom 0
    right 0
    .title
      height .54rem
      line-height .54rem
      background #eee
      padding-left .2rem
      font-size .26rem
    .bottom-list
      padding .1rem .6rem .1rem .1rem
      overflow hidden
      .bottom-wrapper
        float  left
        width 33.3%
        .button
          display block
          margin .1rem
          padding .1rem 0
          text-align center
          border-radius .06rem
          border .02rem solid #ccc
    .item-list
      .item
        padding-left .2rem
        line-height .76rem
</style>
