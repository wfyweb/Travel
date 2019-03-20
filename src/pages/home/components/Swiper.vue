<template>
   <div class="wrapper">
    <swiper :options="swiperOption" >
      <swiper-slide v-for="(item, index) in list" :key="index">
        <img class="swiper-img" :src="item.imgUrl" />
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
   </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        // 所有的参数同 swiper 官方 api 参数
        pagination: '.swiper-pagination',
        loop: true
      }
    }
  },
  mounted () {

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active{
    background: #fff
  }
  .wrapper >>> .swiper-pagination-bullet {
    width: 6px;
    height: 6px;
  }
  .wrapper
    overflow: hidden
    width: 100%
    height: 0
    padding-bottom: 31.2%
    bcakground: #ccc
    .swiper-img
      width: 100%
</style>
