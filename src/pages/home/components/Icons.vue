<template>
  <div class="icons">
    <swiper :options="swiperOption" v-if="isList">
      <swiper-slide v-for="(page, indexs) in pages" :key="indexs">
        <div class="icon" v-for="(item, index) in page" :key="index">
          <div class="icon-img">
            <img class="icon-img-content" :src="item.imgUrl" />
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        // 所有的参数同 swiper 官方 api 参数
        pagination: '.swiper-pagination',
        autoplay: false
      }
    }
  },
  computed: {
    pages () {
      const pages = []
      this.list.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    },
    isList () {
      return this.list.length
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
  .icons >>> .swiper-container
    height: 0
    padding-bottom: 50%
  .icons >>> .swiper-pagination-bullet-active{
    background: $bgColor
  }
  .icons >>> .swiper-pagination-bullet {
    width: 6px;
    height: 6px;
  }
  .icon
    float: left
    width: 25%
    height: 0
    padding-bottom: 22%
    position: relative
    .icon-img
      position: absolute
      top:.1rem
      left:0
      right: 0
      bottom: .5rem
      box-sizing: border-box
      .icon-img-content
        display: block
        margin: 0 auto
        height: 100%
    .icon-desc
      font-size: .26rem;
      color: $darkTextColor
      height :.34rem
      line-height :.44rem
      position: absolute
      bottom:.1rem
      left:0
      right: 0
      box-sizing: border-box
      text-align: center
      ellipsis()
</style>
