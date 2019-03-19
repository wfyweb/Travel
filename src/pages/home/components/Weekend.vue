<template>
  <div>
    <div class="title">
      周末去哪儿
    </div>
    <ul>
      <li class="item border-bottom" v-for="(item, index) in list" :key="index">
        <div class="item-wraper">
          <img  class="item-img" :src="item.imgUrl" />
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  data () {
    return {
      list: [{
        id: '001',
        title: '北京赏花好地方',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1603/6d/2f67ae0659f41f.jpg_r_640x214_bf6cbd0b.jpg',
        desc: '乱花渐欲迷人眼，京城赏花大搜索'
      }, {
        id: '002',
        title: '京城周末撒欢',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1811/f3/86173f863bef61.jpg_r_640x214_52b003ac.jpg',
        desc: '在帝都过周末，不仅仅是城中游！'
      }, {
        id: '003',
        title: '京城溜娃必去',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1811/7e/476589267ebb41.jpg_r_640x214_bf599709.jpg',
        desc: '德智体美劳全面发展的亲子日，这些地方该去看看…'
      },]
    }
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
    .item-wraper
      overflow: hidden
      height: 0;
      padding-bottom 37.4375%
      .item-img
        width 100%
    .item-info
      padding .14rem .2rem .2rem .2rem
      min-width 0
      .item-title
        font-size .28rem
        line-height .48rem
        ellipsis()
      .item-desc
        line-height .4rem
        color #616161
        font-size .24rem
        ellipsis()
      .item-button
        margin-top .16rem
        padding 0 .2rem
        line-height .44rem
        background linear-gradient(130deg,#ffab1e 37%,#ff8c12 100%);
        border-radius .06rem
        color #fff
</style>
