<template>
  <div class="list">
    <div class="item"
      v-for="(item, index) in letters"
      :key = "item"
      :ref = "item"
      @click="handleLetterClick(item, index)"
      @touchstart="handleTouchStart"
      @touchmove="handleTouchMove"
      @touchend="handleTochEnd"
    >
      <span :data-index="index" :class = "{active: currentIndex == index}">{{item}}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CityAlphabet',
  props: {
    cities: Object
  },
  data () {
    return {
      currentIndex: 0,
      touchStatus: false
    }
  },
  computed: {
    letters () {
      const letters = []
      for (let i in this.cities) {
        letters.push(i)
      }
      return letters
    }
  },
  methods: {
    // 点击向City组件 暴露Change事件
    handleLetterClick (key, index) {
      this.currentIndex = index
      this.isColor = !this.isColor
      this.$emit('change', key)
    },
    handleTouchStart () {
      this.touchStatus = true
    },
    handleTouchMove (e) {
      if (this.touchStatus) {
        const startY = this.$refs['A'][0].offsetTop
        const touchY = e.touches[0].clientY - 86
        const index = Math.floor((touchY - startY) / 20)
        if (index >= 0 && index < this.letters.length) {
          this.$emit('change', this.letters[index])
        }
      }
    },
    handleTochEnd () {
      this.touchStatus = false
    }
  },
  watch: {
    letters (val) {
      console.log(val)
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
    top 1.72rem
    right 0
    bottom 0
    .item
      line-height .4rem
      color $bgColor
      .active
        color #3631ee

</style>
