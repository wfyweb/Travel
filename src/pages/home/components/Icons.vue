<template>
  <div class="icons">
    <swiper :options="swiperOption">
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
  data () {
    return {
      swiperOption: {
        // 所有的参数同 swiper 官方 api 参数
        pagination: '.swiper-pagination'
      },
      iconsList: [{
        id: '001',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
        desc: '景点门票'
      }, {
        id: '002',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
        desc: '一日游'
      }, {
        id: '003',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
        desc: '北京必游'
      }, {
        id: '004',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/47/c2b659e048b11602.png',
        desc: '溜娃儿'
      }, {
        id: '005',
        imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20191/0334cf5430b9b5505fd79e2b8d7e8670.png',
        desc: '爬长城'
      }, {
        id: '006',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/6c/9e54a8540fee0102.png',
        desc: '故宫'
      }, {
        id: '007',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/e3/67df61427c8e1302.png',
        desc: '茶馆相声'
      }, {
        id: '008',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/bd/9f7b9b2b60c1502.png',
        desc: '踏青赏花'
      }, {
        id: '009',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/ab/6f7d6e44963c9302.png',
        desc: '泡温泉'
      }, {
        id: '010',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
        desc: '动植物园'
      }]
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconsList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
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
      bottom: .44rem
      box-sizing: border-box
      .icon-img-content
        display: block
        margin: 0 auto
        height: 100%
    .icon-desc
      font-size: .24rem;
      color: $darkTextColor
      height :.44rem
      line-height :.44rem
      position: absolute
      bottom:.1rem
      left:0
      right: 0
      box-sizing: border-box
      text-align: center
      ellipsis()
</style>
