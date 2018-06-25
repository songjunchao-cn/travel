<template>
  <div>
    <div class="title">周末去哪</div>
    <ul>
      <li class="item border-bottom"  v-for="item of weekendList" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src=item.imgUrl>
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
  props: {
    weekendList: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .title
    line-height .8rem
    background  #eee
    text-indent .2rem
  .border-bottom
    margin-bottom .01rem
    &:before
      border-color #666
    .item-img-wrapper
      overflow hidden
      height 0
      padding-bottom 37.09%
      .item-img
        width 100%
    .item-info
      flex 1
      padding .1rem
      min-width 0
      .item-title
        line-height .54rem
        font-size .3rem
        ellipsis()
      .item-desc
        margin-top .1rem
        line-height .44rem
        color #ccc
        font-size .2rem
        ellipsis()
</style>
