<template>
  <div>
    <router-link class="header-abs" tag="div" to="/" v-show="showAbs"><div class="iconfont icon-back">&#xe624;</div></router-link>
    <div class="header-fixed" v-show="!showAbs" :style="opacityStyle">景点详情
      <router-link to="/">
        <div class="iconfont header-back">&#xe624;</div>
      </router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Header',
  data () {
    return {
      showAbs: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop
      if (top > 60) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = { opacity }
        this.showAbs = false
        console.log(scroll)
      } else {
        this.showAbs = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header-abs
    position absolute
    top .2rem
    left .2rem
    width .8rem
    height .8rem
    border-radius .4rem
    background rgba(0, 0, 0, .6)
    text-align center
    line-height .8rem
    .icon-back
      color #fff
      font-size .4rem
  .header-fixed
    position fixed
    top 0
    left 0
    right 0
    overflow hidden
    height $headerHeight
    line-height $headerHeight
    text-align center
    color #fff
    background $bgColor
    font-size .32rem
    z-index 2
    .header-back
      width .64rem
      text-align center
      font-size .4rem
      position absolute
      left 0
      top 0
      color #fff
</style>
