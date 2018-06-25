<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">A</div>
        <div class="item-list">
          <div class="item border-bottom">ale</div>
          <div class="item border-bottom">ale</div>
          <div class="item border-bottom">ale</div>
          <div class="item border-bottom">ale</div>
          <div class="item border-bottom">ale</div>
          <div class="item border-bottom">ale</div>
          <div class="item border-bottom">ale</div>
          <div class="item border-bottom">ale</div>
          <div class="item border-bottom">ale</div>
          <div class="item border-bottom">ale</div>
          <div class="item border-bottom">ale</div>
          <div class="item border-bottom">ale</div>
          <div class="item border-bottom">ale</div>
          <div class="item border-bottom">ale</div>
          <div class="item border-bottom">ale</div>
          <div class="item border-bottom">ale</div>
          <div class="item border-bottom">ale</div>
          <div class="item border-bottom">ale</div>
          <div class="item border-bottom">ale</div>
          <div class="item border-bottom">ale</div>
          <div class="item border-bottom">ale</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'
export default {
  name: 'List',
  mounted () {
    this.scroll = new BScroll(this.$refs.wrapper)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .border-topbottom
    &:before
      border-color #ccc
    &:after
      border-color #ccc
  .list
    position absolute
    top 1.6rem
    left 0
    right 0
    bottom 0
    overflow hidden
    .border-bottom
      &:before
        border-color #ccc
    .title
      height .6rem
      line-height .6rem
      background #eee
      padding-left .2rem
      color #666
      font-size .26rem
     .button-list
       padding .1rem .6rem .1rem .1rem
       overflow hidden
       .button-wrapper
         float left
         width 33.3%
         .button
           margin .1rem
           padding .1rem 0
           text-align center
           border .02rem solid #ccc
           border-radius .06rem
    .item-list
      .item
        line-height .76rem
        padding-left .2rem
</style>
