<template>
  <div>
    <div class="header">
      <div class="header-left"><div class="iconfont icon-back">&#xe624;</div></div>
      <div class="header-input"><span class="iconfont">&#xe632;</span>输入城市/景点/游玩主题</div>
      <div class="header-right">城市<span class="iconfont arrow-icon">&#xe64a;</span></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header
    display flex
    line-height .86rem
    background $bgColor
    color #fff
    .header-left
      width .64rem
      float left
      .icon-back
        text-align center
        font-size .4rem
    .header-input
      flex 1
      background #fff
      border-radius .1rem
      height .64rem
      line-height .64rem
      margin-top .12rem
      margin-left .2rem
      color #ccc
      padding-left .2rem
    .header-right
      width 1.24rem
      float right
      text-align:center
      .arrow-icon
        font-size .24rem
</style>
