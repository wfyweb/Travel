<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe624;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
      输入城市/景点/游玩主题
    </div>
    <router-link to='/city'>
      <div class="header-right">
        城市
        <span class="iconfont font-icon">&#xe64a;</span>
      </div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header
    display: flex
    line-height: $headerHeight
    background: $bgColor
    color: #fff
    .header-left
      width: .64rem
      float: left
      .back-icon
        font-size: .24rem
        text-align: center
    .header-input
      flex: 1
      height: .64rem
      line-height: .63rem
      padding-left: .2rem
      margin-top: .11rem
      margin-left: .2rem
      background: #fff;
      color:#ccc;
      border-radius: .1rem
    .header-right
      color: #fff
      width: 1.24rem
      float: right
      text-align: center
      .font-icon
        font-size: .24rem
</style>
