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
  data () {
    return {
      list: [{
        id: '001',
        title: '鸟巢',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1508/fe/434ee530e21f1c11bad088e8cc8d5e93.water.jpg_200x200_912ce9f4.jpg',
        desc: '北京的地标，中华民族崛起的象征'
      }, {
        id: '002',
        title: '故宫',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_200x200_1bc99086.jpg',
        desc: '世界五大宫之首，穿越与您近在咫尺'
      }, {
        id: '003',
        title: '北京野生动物园',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1507/36/ce3d2d6c9ab44d67ae68d940b8781829.water.jpg_200x200_0938a8f2.jpg',
        desc: '敢与森林之王近距离接触吗？'
      },]
    }
  },
  computed: {

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
