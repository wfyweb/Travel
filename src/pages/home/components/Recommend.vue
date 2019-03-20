<template>
  <div>
    <div class="title">
      热销推荐
    </div>
    <ul>
      <li class="item border-bottom" v-for="(item, index) in list" :key="index">
        <img  class="item-img" :src="item.imgUrl" />
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  props: {
    list: Array
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .title
    line-height .8rem
    background #eee
    text-indent .2rem
  .item
    overflow hidden
    display flex
    height 1.9rem
    margin-bottom .1rem
    .item-img
      width 1.7rem
      height 1.7rem
      padding  .2rem
    .item-info
      flex 1
      padding .2rem
      padding-left 0
      min-width 0
      .item-title
        line-height .54rem
        font-size .32rem
        ellipsis()
      .item-desc
        line-height .4rem
        color #ccc
        ellipsis()
      .item-button
        margin-top .16rem
        padding 0 .2rem
        line-height .44rem
        background linear-gradient(130deg,#ffab1e 37%,#ff8c12 100%);
        border-radius .06rem
        color #fff
</style>
