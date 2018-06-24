<template>
  <div>
    <div class="title">周末去哪</div>
    <ul>
      <li class="item" border-bottom v-for="item of recommendList" :key="item.id">
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
  data () {
    return {
      recommendList: [{
        id: '0001',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1505/4e/3e87ee62e59cdb.jpg_r_640x214_fe6cc902.jpg',
        title: '杭州必游TOP10',
        desc: '杭州，前世今生与你有一场美丽约会'},
      {
        id: '0002',
        imgUrl: '//img1.qunarzz.com/sight/source/1505/9f/7d45cc38259e0.jpg_r_640x214_156f4299.jpg',
        title: '承载杭城的历史之地',
        desc: '饱经沧桑的地方诉述着这座城的段段衷肠'
      },
      {
        id: '0003',
        imgUrl: '//img1.qunarzz.com/sight/source/1505/ae/4fe23c6b6679e2.jpg_r_640x214_368a18d8.jpg',
        title: '美仑美奂的演出',
        desc: '一座有故事的城，天天有“戏”在上演'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .title
    margin-top  .2rem
    line-height .8rem
    background  #eee
    text-indent .2rem
  .item
    background white
    .item-img-wrapper
      overflow hidden
      height 0
      padding-bottom 33.9%
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
