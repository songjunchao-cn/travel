<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <li class="item" border-bottom v-for="item of recommendList" :key="item.id">
        <img class="item-img" :src=item.imgUrl>
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
  props: {
    recommendList: Array
  }
}
</script>

<style lang="stylus" scoped>
  .title
    margin-top  .2rem
    line-height .8rem
    background  #eee
    text-indent .2rem
  .item
    display flex
    overflow hidden
    height 1.9rem
    .item-img
      width 1.8rem
      height 1.8rem
      padding .1rem
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
      .item-button
        font-size .25rem
        line-height .44 rem
        margin-top .16rem
        background rgba(0,0,0,.6)
        padding 0 .2rem
        border-radius .06rem
        color #fff
</style>
